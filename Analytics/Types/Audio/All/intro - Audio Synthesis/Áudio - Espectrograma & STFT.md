
---

>[!quote] **Docs:** [librosa.stft](https://librosa.org/doc/latest/generated/librosa.stft.html#librosa.stft)

>[!quote] **Article:** [O que é Impressão Digital de Áudio](https://www.scrapeless.com/pt/blog/audio-fingerprinting)

>[!quote] **Article:** [Audio Processing For Machine Learning](https://www.kaggle.com/code/youknowjp/audio-processing-for-machine-learning)

>[!quote] **YouTube:** [Short-time Fourier Transform and the Spectogram](https://www.youtube.com/watch?v=NA0TwPsECUQ)

---

````ad-quote
title:

##### **01 )** - O Espectrograma: A Visualização da STFT

```ad-quote
title:

O resultado da STFT é um conjunto de valores complexos para cada janela de tempo e frequência. Para visualizarmos essa informação de forma intuitiva, utilizamos o **espectrograma**.
```


```ad-quote
title:

**Eixo X:** 
- Representa o tempo.

**Eixo Y:** 
- Representa a frequência.
 
**Cor/Intensidade:** 
- Representa a amplitude ou magnitude de uma determinada frequência em um determinado instante de tempo. Geralmente, cores mais quentes (como vermelho e amarelo) indicam maior amplitude, enquanto cores mais frias (como azul e preto) indicam menor amplitude.
```

````

![[Pasted image 20250731160910.png]]

````ad-quote
title:

##### **02 )** - Análise dos Resultados

```ad-quote
title:

###### A) Gráfico da Esquerda (Janela Curta)

<p align="justify">Observe como as duas "manchas" coloridas são largas e borradas no eixo da frequência (vertical). É difícil dizer que a frequência é <i>exatamente</i> 250 Hz ou 1000 Hz. No entanto, a transição entre as duas em 1.0 segundo é extremamente nítida e bem definida no eixo do tempo (horizontal): <b>A Resolução Temporal é Alta.</b></p>
```

```ad-quote
title: 

###### B) Gráfico da Direita (Janela Longa)
<p align="justify">Aqui, as faixas de frequência são linhas horizontais finas e precisas, localizadas exatamente em 250 Hz e 1000 Hz. A resolução de frequência é excelente. Contudo, a transição no meio do sinal é "arrastada" e borrada ao longo do tempo. Parece que a frequência muda gradualmente, o que não é verdade: <b>A Resolução Temporal é Baixa.</b></p>
```

````

---

```ad-example

#### **Conceitos Fundamentais**
```

---

````ad-quote
title:

##### **01 )** - A Limitação da Transformada de Fourier

```ad-quote
title:
<p align="justify">A Transformada de Fourier é uma poderosa ferramenta matemática que decompõe um sinal em suas frequências constituintes. No entanto, sua versão tradicional analisa o sinal em sua totalidade, fornecendo um espectro de frequência que representa todo o sinal de uma só vez. Isso significa que perdemos a informação de <b>quando</b> determinadas frequências ocorreram. Para um sinal de áudio, que é inerentemente dinâmico, saber apenas <i>quais</i> frequências estão presentes, sem saber <i>quando</i> elas aparecem, é uma grande limitação.</p>
```
````

---

> [!example]  **_New_**

---

````ad-quote
title:

##### **02 )** - A Solução: Transformada de Fourier de Curto Tempo (STFT)

```ad-quote
title:
<p align="justify">A STFT resolve essa limitação. A ideia central é dividir o sinal de áudio em pequenos segmentos de tempo sobrepostos, ou "janelas", e aplicar a Transformada de Fourier a cada um desses segmentos. Isso nos permite obter o conteúdo de frequência para cada pequeno instante de tempo, revelando como o espectro do sinal evolui.</p>
```

```ad-quote
A STFT de um sinal $x[n]$ é definida como:

$$\mathrm{STFT}\{x[n]\}(m,\omega)=\sum_{n=-\infty}^{\infty}x[n]w[n-m]e^{-j\omega n}$$

Onde:
- $x[n]$ é o sinal de entrada.
- $w[n]$ é a função de janela.
- $m$ representa o deslocamento da janela no tempo.
```

````

---

> [!example]  **_New_**

---

````ad-quote
title:

##### **03 )** - O Espectrograma: A Visualização da STFT

```ad-quote
title:
<p align="justify">O resultado da STFT é um conjunto de valores complexos para cada janela de tempo e frequência. Para visualizarmos essa informação de forma intuitiva, utilizamos o <b>espectrograma</b>. Ele é uma representação gráfica onde o eixo horizontal representa o tempo, o eixo vertical representa a frequência, e a cor/intensidade de cada ponto representa a amplitude (energia) daquela frequência naquele instante de tempo. Essencialmente, o espectrograma é a magnitude ao quadrado da STFT.</p>
```
````

---

```ad-example

#### **Parâmetros Cruciais da STFT e seu Impacto**
```

---

````ad-quote
title:

##### **01 )** - Tamanho da Janela (Window Size ou NFFT)

```ad-quote
title:
<p align="justify">Este é o parâmetro mais fundamental, definindo o número de amostras do sinal analisadas de uma só vez. Sua escolha resulta no famoso <b>trade-off tempo-frequência</b>.</p>
```
````

````ad-quote
title: 
**Janela Longa - Alta Resolução de Frequência**
```ad-quote
title: 
**Vantagem:**

- Analisa um trecho maior do sinal, permitindo distinguir com grande precisão frequências muito próximas. O resultado é um espectrograma com faixas de frequência nítidas no eixo vertical.

**Desvantagem:** 
- Toda a informação contida na janela é "achatada" em um único ponto no tempo. A resolução no eixo horizontal (tempo) é pobre, tornando difícil localizar eventos sonoros rápidos.
```


````

````ad-quote
title: 

**Janela Curta - Alta Resolução Temporal**
```ad-quote
title: 

**Vantagem:** 
- Analisa um trecho pequeno, permitindo localizar com grande precisão o momento exato de um evento sonoro transiente (como um clique). A resolução no eixo horizontal (tempo) é excelente.

**Desvantagem:** 
- Com poucas amostras, a análise de frequência é prejudicada. As faixas de frequência no espectrograma tornam-se "borradas" e largas no eixo vertical.
```

````

---

> [!example]  **_New_**

---

````ad-quote
title:

##### **02 )** - Comprimento do Pulo (Hop Length) e Sobreposição (Overlap)

```ad-quote
title:
<p align="justify">Estes parâmetros definem como a janela se move ao longo do sinal. O <b>Hop Length</b> é o número de amostras que a janela "pula" para frente para o próximo cálculo. O <b>Overlap</b> é a quantidade de amostras que uma janela compartilha com a anterior (<code>Overlap = Window Size - Hop Length</code>).</p>
<p align="justify">Uma sobreposição significativa (tipicamente 50-75%) é crucial. Ela garante que a informação nas bordas das janelas (onde o sinal é atenuado pela função de janela) não seja perdida, resultando em um espectrograma mais suave e contínuo.</p>
```
````

---

> [!example]  **_New_**

---

````ad-quote
title:

##### **03 )** - Tipo de Janela (Window Type)

```ad-quote
title:
<p align="justify">Se simplesmente "cortarmos" um segmento de sinal (usando uma janela retangular), criamos descontinuidades abruptas que geram um efeito indesejado chamado <b>vazamento espectral (spectral leakage)</b>. Isso faz com que a energia de uma frequência "vaze" para frequências vizinhas, criando artefatos no espectrograma.</p>
<p align="justify">Para mitigar isso, usamos funções de janela com formas suaves (como Hann, Hamming, Blackman) que atenuam o sinal gradualmente até zero nas bordas, eliminando as transições abruptas e resultando em um espectrograma muito mais "limpo".</p>
```
````

---

```ad-example

#### **Demonstração Prática com Python**
```

---

````ad-quote
title:

##### **01 )** - Geração do Sinal e Visualização

```ad-quote
title:
<p align="justify">Vamos visualizar o impacto do tamanho da janela. Criaremos um sinal de teste com duas frequências distintas que não se sobrepõem no tempo: um tom de 250 Hz na primeira metade e um tom de 1000 Hz na segunda metade.</p>
```
````

```python
# Data Manipulation and Analysis
import numpy as np

# Visualization Libraries
import matplotlib.pyplot as plt
import seaborn as sns

# Configurações do plot
sns.set_theme(style="whitegrid")
plt.rcParams['figure.figsize'] = (14, 8)

# --- Geração do Sinal de Teste ---
fs = 4000  # Frequência de amostragem (Hz)
T = 2.0    # Duração total do sinal (segundos)
t = np.linspace(0, T, int(T * fs), endpoint=False) # Vetor de tempo

# Primeira metade: seno de 250 Hz
signal_part1 = np.sin(2 * np.pi * 250 * t[:len(t)//2])

# Segunda metade: seno de 1000 Hz
signal_part2 = np.sin(2 * np.pi * 1000 * t[len(t)//2:])

# Sinal completo
signal = np.concatenate([signal_part1, signal_part2])

# --- Demonstração: Impacto do Tamanho da Janela (NFFT) ---
plt.figure(facecolor='lightgray')

# Janela Curta (Alta Resolução Temporal)
nfft_short = 128
hop_length_short = nfft_short // 4
plt.subplot(1, 2, 1)
plt.specgram(signal, NFFT=nfft_short, Fs=fs, noverlap=nfft_short - hop_length_short, cmap='viridis')
plt.title(f'Janela Curta (NFFT={nfft_short})')
plt.xlabel('Tempo [s]')
plt.ylabel('Frequência [Hz]')
plt.ylim(0, 1500)

# Janela Longa (Alta Resolução de Frequência)
nfft_long = 1024
hop_length_long = nfft_long // 4
plt.subplot(1, 2, 2)
plt.specgram(signal, NFFT=nfft_long, Fs=fs, noverlap=nfft_long - hop_length_long, cmap='viridis')
plt.title(f'Janela Longa (NFFT={nfft_long})')
plt.xlabel('Tempo [s]')
plt.ylabel('Frequência [Hz]')
plt.ylim(0, 1500)

plt.suptitle('Impacto do Tamanho da Janela no Espectrograma', fontsize=16, weight='bold')
plt.tight_layout(rect=[0, 0, 1, 0.96])
plt.show()

```

---
