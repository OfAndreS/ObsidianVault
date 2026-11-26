
---

```python

# 1 ) Waveform

# 2 ) FFT - Spectrum

# 3 ) STFT - Spectrogram

# 4 ) MFCCs

```

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Intro )** - O Guia Completo sobre Pré-processamento de Dados de Áudio para Deep Learning

```ad-quote
title:
<p align="justify">No universo da Inteligência Artificial e do Deep Learning (DL), a capacidade de extrair informações significativas de dados de áudio abriu portas para uma vasta gama de aplicações, desde assistentes de voz e reconhecimento de fala até análise de sentimentos e classificação de sons ambientais. Contudo, antes que um modelo de DL possa "ouvir" e "entender" o áudio, os dados brutos precisam passar por uma etapa crucial: o pré-processamento. Este processo transforma as complexas ondas sonoras em representações numéricas estruturadas, otimizadas para o aprendizado das redes neurais.</p>
```

```ad-quote
title:
<p align="justify">Este artigo explora em detalhes as quatro representações fundamentais no pré-processamento de dados de áudio, desde a sua forma mais básica até características mais sofisticadas e perceptualmente relevantes: a Waveform, a transformação para o domínio da frequência com a FFT (resultando no Espectro), a análise tempo-frequência com a STFT (gerando o Espectrograma) e a extração de características inspirada na audição humana, os MFCCs.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Waveform: A Representação Fundamental no Domínio do Tempo

```ad-quote
title:
<p align="justify">A forma mais básica e direta de representar um sinal de áudio é a Waveform (forma de onda). Trata-se de um gráfico que ilustra a variação da amplitude (intensidade ou "volume") do som ao longo do tempo. O Eixo Horizontal (X) representa o tempo, enquanto o Eixo Vertical (Y) representa a amplitude da onda sonora. Picos altos indicam sons altos, vales profundos indicam sons baixos, e a linha zero representa o silêncio.</p>
```

```ad-quote
title:
###### **Digitalização do Áudio:**
<p align="justify">O som no mundo real é um sinal analógico contínuo. Para que um computador possa processá-lo, ele precisa ser convertido em um formato digital. Esse processo envolve duas etapas principais:</p>
```

```ad-quote
title:
<p align="justify">A Amostragem (Sampling) é o processo onde a amplitude da onda sonora é medida em intervalos de tempo regulares. A frequência com que essas medições são feitas é chamada de Taxa de Amostragem (Sample Rate), medida em Hertz (Hz). Uma taxa de amostragem comum para CDs de áudio é de 44.100 Hz, o que significa que 44.100 amostras da amplitude do som são capturadas a cada segundo.</p>
```

```ad-quote
title:
A Quantização (Quantization) ocorre quando cada amostra de amplitude é mapeada para o valor discreto mais próximo dentro de uma faixa predeterminada. A precisão dessa representação é definida pela Profundidade de Bits (Bit Depth). Por exemplo, um áudio de 16 bits pode representar $2^{16}$ (65.536) níveis de amplitude diferentes.
```

```ad-quote
title:
<p align="justify">A waveform, portanto, é essencialmente uma longa sequência de números que representam a amplitude do som em cada ponto de amostragem. Embora seja a representação mais fiel ao sinal original, ela não é ideal para a maioria das tarefas de Deep Learning, pois as informações mais relevantes, como as frequências que compõem o som, não são explicitamente representadas.</p>
```
````

![[Pasted image 20250826224036.png]]

```python

	# 1 ) WaveForm
	
    librosa.display.waveshow(signal, sr=sr)

```

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - FFT (Transformada Rápida de Fourier): Do Tempo para a Frequência -> Espectro

```ad-quote
title:
<p align="justify">O ouvido humano não percebe o som como uma sequência de amplitudes, mas sim como uma combinação de diferentes frequências (tons graves, médios e agudos). Para que um modelo de DL possa analisar o áudio de forma semelhante, precisamos converter a waveform do domínio do tempo para o domínio da frequência. A ferramenta matemática para isso é a Transformada de Fourier, e em sua versão computacionalmente eficiente, a Transformada Rápida de Fourier (FFT).</p>
```

```ad-quote
title:
<p align="justify">A FFT decompõe um sinal (um trecho da waveform) em suas frequências constituintes. O resultado dessa transformação é o Espectro (Spectrum). O Espectro é um gráfico que mostra a quantidade de energia (amplitude) presente em cada frequência de um sinal de áudio, com o Eixo Horizontal (X) representando a frequência e o Eixo Vertical (Y) representando a magnitude de cada frequência.</p>
```

```ad-quote
title:
<p align="justify">Ao aplicar a FFT a um sinal de áudio, obtemos uma visão de quais "notas" ou tons compõem aquele som. Por exemplo, a FFT de uma gravação de um violão tocando um acorde mostraria picos de energia nas frequências correspondentes a cada nota do acorde.</p>
```

```ad-quote
title:
###### **Limitação da FFT:**
<p align="justify">A FFT, quando aplicada a todo o sinal de áudio de uma vez, nos dá um resumo das frequências presentes, mas perde toda a informação temporal. Não sabemos quando essas frequências ocorreram. Para sinais que mudam ao longo do tempo, como a fala ou a música, essa representação é inadequada.</p>
```
````

![[Pasted image 20250826224151.png]]

```python

    # 2 ) FFT - Spectrum
    
    fft = np.fft.fft(signal)
    magnitude = np.abs(fft)
    frequency = np.linspace(0, sr, len(magnitude))

    # O espectro é espelhado, então pegamos apenas a primeira metade
    left_frequency = frequency[:int(len(frequency)/2)]
    left_magnitude = magnitude[:int(len(magnitude)/2)]
    
```

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - STFT (Transformada de Fourier de Curto Período): A Análise Dinâmica -> Espectrograma

```ad-quote
title:
<p align="justify">Para resolver a limitação da FFT, utilizamos a Transformada de Fourier de Curto Período (Short-Time Fourier Transform - STFT). A ideia é simples e poderosa: em vez de analisar o sinal de áudio inteiro de uma só vez, a STFT o divide em pequenos segmentos (ou "janelas"), geralmente com sobreposição, e aplica a FFT em cada um desses segmentos.</p>
```

```ad-quote
title:
<p align="justify">Esse processo nos permite ver como o espectro de frequência do áudio muda ao longo do tempo. A representação visual do resultado da STFT é o Espectrograma. Ele é uma das representações mais importantes e utilizadas no pré-processamento de áudio para Deep Learning, sendo um gráfico tridimensional onde o Eixo Horizontal (X) representa o tempo, o Eixo Vertical (Y) representa a frequência, e a Cor/Intensidade representa a amplitude ou energia de cada frequência em um determinado instante de tempo.</p>
```

```ad-quote
title:
<p align="justify">O espectrograma pode ser visto como uma sequência de espectros empilhados ao longo do tempo. Para modelos de Deep Learning, especialmente Redes Neurais Convolucionais (CNNs), os espectrogramas são extremamente úteis, pois podem ser tratados como "imagens" do som, permitindo que a rede aprenda padrões visuais que correspondem a diferentes características sonoras.</p>
```
````

![[Pasted image 20250826224252.png]]

```python

    # 3 ) STFT - Spectrogram
    
    n_fft = 2048
    hop_length = 512

    stft = librosa.stft(signal, n_fft=n_fft, hop_length=hop_length)
    spectrogram = np.abs(stft)
    log_spectrogram = librosa.amplitude_to_db(spectrogram)
    
```

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - MFCCs (Coeficientes Cepstrais na Escala Mel): Mimetizando a Audição Humana

```ad-quote
title:
<p align="justify">Embora os espectrogramas sejam poderosos, eles representam as frequências em uma escala linear (em Hz). No entanto, a percepção humana da frequência não é linear. Nós somos muito mais sensíveis a diferenças entre frequências baixas do que a diferenças entre frequências altas. Para criar uma representação de áudio que se assemelhe mais à forma como os humanos ouvem, foram desenvolvidos os Coeficientes Cepstrais na Escala Mel (Mel-Frequency Cepstral Coefficients - MFCCs). Eles são uma das features (características) mais populares e eficazes, especialmente para tarefas de reconhecimento de fala.</p>
```

```ad-quote
title:
###### **Cálculo dos MFCCs:**
<p align="justify">O cálculo dos MFCCs é um processo de múltiplas etapas:</p>

|Etapa&nbsp;    | Descrição    |
| --- | --- |
|**STFT:**|O processo começa com o cálculo do espectrograma do sinal de áudio.|
|**Banco de Filtros Mel:**|O espectro de potência de cada janela de tempo é passado por um banco de filtros triangulares espaçados de acordo com a Escala Mel, que mapeia as frequências lineares (Hz) para uma escala que se aproxima da percepção auditiva humana.|
|**Energia Logarítmica:**|A energia em cada um dos filtros Mel é calculada e, em seguida, seu logaritmo é obtido. Isso também se alinha à percepção humana, que não percebe a intensidade do som de forma linear.|
|**Transformada Discreta de Cosseno (DCT):**|A DCT é aplicada às energias logarítmicas do banco de filtros para decorrelacionar as energias e compactar a informação nos primeiros coeficientes.|

```

```ad-quote
title:
<p align="justify">O resultado é um conjunto de vetores (um para cada janela de tempo) contendo os MFCCs. Tipicamente, são utilizados de 13 a 40 coeficientes por janela, o que representa uma compactação significativa da informação contida no espectrograma, mantendo as características mais relevantes para a percepção da fala.</p>
```

```ad-quote
title:
###### **Vantagens dos MFCCs:**

|Vantagem&nbsp;    | Descrição    |
| --- | --- |
|**Perceptualmente Relevantes:**|Modelam a percepção não linear da frequência pelo ouvido humano.|
|**Compactos:**|Reduzem a dimensionalidade dos dados em comparação com o espectrograma.|
|**Decorrelacionados:**|A etapa da DCT torna as características mais independentes, o que pode ser benéfico para alguns modelos de Machine Learning.|

```
````

![[Pasted image 20250826224328.png]]

```python

# 4 ) MFCCs

MFCCs = librosa.feature.mfcc(y=signal, sr=sr, n_fft=n_fft, hop_length=hop_length, n_mfcc=13)

```

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">Em resumo, a jornada do pré-processamento de áudio para Deep Learning é uma série de transformações que convertem a complexa e contínua waveform em representações cada vez mais abstratas e informativas. A escolha da representação ideal — seja um espectrograma detalhado ou os compactos MFCCs — dependerá da tarefa específica, do modelo de Deep Learning utilizado e dos recursos computacionais disponíveis. Dominar essas técnicas é fundamental para o sucesso de qualquer projeto que envolva a análise inteligente de áudio.</p>
```
````

---
