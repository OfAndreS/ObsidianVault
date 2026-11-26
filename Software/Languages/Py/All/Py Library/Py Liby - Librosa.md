
---

````ad-quote
title:

```ad-quote
title:
<p align="justify">A Biblioteca Librosa é um pacote Python fundamental para análise e processamento de áudio. Ela fornece os blocos de construção necessários para criar sistemas de recuperação de informação musical (MIR - Music Information Retrieval) e de processamento de sinais de áudio em geral. Com uma API intuitiva e poderosa, a Librosa simplifica tarefas complexas como carregamento de áudio, extração de características, análise espectral e rastreamento de ritmo.</p>

<p align="justify">Este guia detalha as principais funções e módulos disponíveis na Biblioteca Librosa, organizados por suas funcionalidades centrais.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Carregamento e Manipulação de Áudio (Core)

```ad-quote
title:
<p align="justify">Essas são as funções essenciais para carregar arquivos de áudio do disco e prepará-los para análise.</p>
```

```ad-quote
title:

| Função | Descrição |
|---|---|
| `librosa.load(path, sr=22050)` | Carrega um arquivo de áudio do caminho *path*. Retorna uma série temporal de áudio (array NumPy) e a taxa de amostragem (*sr*). Por padrão, o áudio é convertido para mono e reamostrado para 22.050 Hz. |
| `librosa.to_mono(y)` | Converte uma série temporal de áudio estéreo *y* para mono, calculando a média dos canais. |
| `librosa.resample(y, orig_sr, target_sr)` | Reamostra uma série temporal de áudio *y* da taxa de amostragem original para a taxa de amostragem alvo. |
| `librosa.get_duration(y, sr)` | Calcula a duração de uma série temporal de áudio em segundos. |
| `librosa.autocorrelate(y)` | Calcula a autocorrelação de um sinal de áudio, útil para análise de pitch. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Extração de Características (Feature Extraction)

```ad-quote
title:
<p align="justify">Funções para extrair representações significativas do áudio. Essas características são a base para tarefas de machine learning, como classificação de gênero musical ou reconhecimento de fala.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `librosa.feature.mfcc(y, sr)` | Extrai os Coeficientes Cepstrais na Frequência Mel (MFCCs), uma das características mais importantes para análise de timbre e reconhecimento de voz. |
| `librosa.feature.chroma_stft(y, sr)` | Calcula um cromagrama a partir de uma Transformada de Fourier de Curto Tempo (STFT). Representa a energia das 12 classes de notas (C, C#, D, etc.). |
| `librosa.feature.spectral_centroid(y, sr)` | Calcula o centroide espectral, que indica onde o "centro de massa" do espectro está localizado. Relacionado com o brilho do som. |
| `librosa.feature.spectral_bandwidth(y, sr)` | Calcula a largura de banda espectral. |
| `librosa.feature.spectral_contrast(y, sr)` | Calcula o contraste espectral, que mede a diferença de amplitude entre picos e vales no espectro. |
| `librosa.feature.spectral_flatness(y, sr)` | Mede quão plano ou "ruidoso" é um espectro. |
| `librosa.feature.spectral_rolloff(y, sr)` | Calcula a frequência abaixo da qual uma porcentagem especificada da energia espectral total está concentrada. |
| `librosa.feature.rms(y)` | Calcula a energia RMS (Root-Mean-Square) de cada quadro de áudio. |
| `librosa.feature.zero_crossing_rate(y)` | Calcula a taxa de cruzamento por zero, que é um indicador da frequência e da "ruidosidade" de um sinal. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Análise Espectral (Spectral Representations)

```ad-quote
title:
<p align="justify">Funções para converter o sinal de áudio do domínio do tempo para o domínio da frequência, permitindo a análise de seu conteúdo harmônico.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `librosa.stft(y)` | Calcula a Transformada de Fourier de Curto Tempo (STFT). Retorna uma matriz complexa (espectrograma). |
| `librosa.istft(stft_matrix)` | Calcula a STFT Inversa para converter um espectrograma de volta ao domínio do tempo. |
| `librosa.magphase(D)` | Separa um espectrograma complexo *D* em sua magnitude e fase. |
| `librosa.amplitude_to_db(S)` | Converte um espectrograma de amplitude para a escala de decibéis (dB). |
| `librosa.db_to_amplitude(S_db)` | Converte um espectrograma de decibéis (dB) de volta para a escala de amplitude. |
| `librosa.cqt(y, sr)` | Calcula a Transformada Q Constante (CQT), que é similar à STFT mas com eixos de frequência logarítmicos, mais alinhados à percepção musical. |
| `librosa.mel_spectrogram(y, sr)` | Calcula um espectrograma na escala Mel. A escala Mel aproxima-se da percepção humana de pitch. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Ritmo e Batidas (Beat and Tempo)

```ad-quote
title:
<p align="justify">Funções especializadas na análise rítmica do áudio, como detecção de batidas e estimativa de andamento (BPM).</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `librosa.beat.beat_track(y, sr)` | Estima o andamento (BPM) e localiza as batidas no sinal de áudio. Retorna o BPM e um array com os instantes de tempo (em segundos) de cada batida detectada. |
| `librosa.beat.tempo(y, sr)` | Estima o andamento (BPM - Batidas Por Minuto) de um áudio. |
| `librosa.onset.onset_detect(y, sr)` | Detecta eventos de "onset" (início de notas ou eventos percussivos) no sinal de áudio. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Decomposição e Efeitos (Decomposition and Effects)

```ad-quote
title:
<p align="justify">Funções avançadas para separar componentes do áudio e aplicar efeitos, como time-stretching.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `librosa.decompose.hpss(S)` | Decompõe um espectrograma *S* em seus componentes harmônicos e percussivos. |
| `librosa.effects.harmonic(y)` | Extrai o componente harmônico de uma série temporal de áudio. |
| `librosa.effects.percussive(y)` | Extrai o componente percussivo de uma série temporal de áudio. |
| `librosa.effects.time_stretch(y, rate)` | Altera a velocidade do áudio por um fator *rate* sem alterar o pitch. |
| `librosa.effects.pitch_shift(y, sr, n_steps)` | Altera o pitch do áudio em *n_steps* semitons sem alterar a duração. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Plotagem e Visualização (Display)

```ad-quote
title:
<p align="justify">Funções utilitárias para visualizar dados de áudio e suas representações, construídas sobre o Matplotlib.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `librosa.display.waveshow(y, sr)` | Plota a forma de onda (waveform) de um sinal de áudio *y*. |
| `librosa.display.specshow(data)` | Plota dados espectrais como espectrogramas, cromagramas, etc., com eixos formatados adequadamente (tempo, frequência, notas). |

```
````

---