---
banner: "![[Pasted image 20251118212610.png]]"
---

---

````ad-quote
title:

##### **01 )** - Catálogo de Layers para CNNs

```ad-quote
title:
<p align="justify">As camadas da biblioteca Keras, agora integrada ao TensorFlow, são essenciais para a construção de Redes Neurais Convolucionais (CNNS). Abaixo, elas estão organizadas por CATEGORIA DE FUNÇÃO para facilitar o entendimento, cobrindo desde a extração de características até a classificação final.</p>
```

```python
# Exemplo de importação padrão para utilizar as camadas listadas
from tensorflow.keras import layers, models, Input
```

```ad-quote
title:
**Links:**
```

```ad-quote
title:
https://www.tensorflow.org/api_docs/python/tf
```

```ad-quote
title:
**Fluxo do Modelo**
```

```python
# Estrutura conceitual de uma CNN
modelo = keras.Sequential([
    # Entrada
    keras.Input(shape=(224, 224, 3)),
    
    # Bloco de Extração (Repetido algumas vezes)
    keras.layers.Conv2D(32, (3,3), activation='relu'),
    keras.layers.BatchNormalization(),
    keras.layers.MaxPooling2D((2,2)),
    
    # Bloco de Classificação
    keras.layers.Flatten(),
    keras.layers.Dense(128, activation='relu'),
    keras.layers.Dropout(0.5),
    keras.layers.Dense(10, activation='softmax') # Saída Final
])
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Camadas de Convolução

```ad-quote
title:
**Função**
```

```ad-quote
title:
<p align="justify">São a base das CNNS. Estas camadas são responsáveis por extrair as CARACTERÍSTICAS (FEATURES) dos dados, como bordas, texturas e formas em imagens.</p>
```

```ad-quote
title:
**Principais Variantes**
```

```ad-quote
title:

| Camada | Descrição |
| --- | --- |
| CONV2D | A mais importante. Realiza convolução espacial em imagens (2D). Define-se o número de FILTROS e o tamanho do KERNEL. |
| CONV1D | Usada para dados sequenciais como ÁUDIO ou TEXTO (NLP). A convolução ocorre em apenas uma dimensão (tempo). |
| CONV3D | Usada para dados volumétricos, como VÍDEO ou imagens médicas (ressonância magnética 3D). |
| SEPARABLECONV2D | Versão otimizada da CONV2D. Separa a convolução em duas etapas (DEPTHWISE e POINTWISE), tornando o modelo mais LEVE e RÁPIDO. |

```

```ad-quote
title:
**Exemplo de Código**
```

```python
# Exemplo de uma Conv2D padrão
keras.layers.Conv2D(filters=32, kernel_size=(3, 3), activation='relu')
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Camadas de Pooling

```ad-quote
title:
**Função**
```

```ad-quote
title:
<p align="justify">Servem para realizar a subamostragem, reduzindo a dimensionalidade da imagem. Isso diminui o custo computacional e ajuda a evitar o OVERFITTING.</p>
```

```ad-quote
title:
**Principais Variantes**
```

```ad-quote
title:

| Camada | Descrição |
| --- | --- |
| MAXPOOLING2D | A mais comum. Pega o MAIOR valor dentro de uma janela. Preserva as características mais fortes. |
| AVERAGEPOOLING2D | Calcula a MÉDIA dos valores na janela. Suaviza mais a imagem que o MAXPOOL. |
| GLOBALAVERAGEPOOLING2D | Transforma mapas 2D em um vetor 1D calculando a média total. Substitui o FLATTEN para reduzir parâmetros. |

```

```ad-quote
title:
**Exemplo de Código**
```

```python
# Reduzindo a dimensão pela metade com Max Pooling
keras.layers.MaxPooling2D(pool_size=(2, 2))
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Camadas de Regularização e Normalização

```ad-quote
title:
**Função**
```

```ad-quote
title:
<p align="justify">Essenciais para treinar redes profundas de forma estável e eficiente, atuando no controle dos pesos e ativações durante o processo de aprendizado.</p>
```

```ad-quote
title:
**Uso Típico**
```

```ad-quote
title:
<p align="justify">Utilizadas entre camadas de convolução ou antes das camadas densas para acelerar a convergência e prevenir que a rede decore os dados.</p>
```

```ad-quote
title:
**Principais Variantes**
```

```ad-quote
title:

| Camada | Descrição |
| --- | --- |
| BATCHNORMALIZATION | Normaliza as ativações da camada anterior. Permite usar TAXAS DE APRENDIZADO mais altas. |
| DROPOUT | Desliga aleatoriamente alguns neurônios durante o treinamento. Principal técnica contra OVERFITTING. |

```

```ad-quote
title:
**Exemplo de Código**
```

```python
# Normalizando e aplicando Dropout de 25%
model.add(keras.layers.BatchNormalization())
model.add(keras.layers.Dropout(0.25))
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Camadas de Formatação e Conexão

```ad-quote
title:
**Função**
```

```ad-quote
title:
<p align="justify">Fazem a ponte entre a parte convolucional (extração de características) e a parte densa (classificação), além de definir a estrutura de entrada e saída.</p>
```

```ad-quote
title:
**Principais Variantes**
```

```ad-quote
title:

| Camada | Descrição |
| --- | --- |
| FLATTEN | Achata a saída 3D das camadas de convolução/pooling em um vetor 1D longo. |
| DENSE | Camada clássica (FULLY CONNECTED). Geralmente usada no FINAL para dar a classificação (ex: probabilidade de classes). |
| INPUT | Camada explícita para definir o formato de entrada dos dados (ex: 224, 224, 3). |

```

```ad-quote
title:
**Exemplo de Código**
```

```python
# Transição típica de Convolução para Classificação
model.add(keras.layers.Flatten())
model.add(keras.layers.Dense(units=10, activation='softmax'))
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Camadas para Arquiteturas Avançadas

```ad-quote
title:
**Função**
```

```ad-quote
title:
<p align="justify">Utilizadas em projetos específicos que envolvem gerar imagens (GANS) ou realizar segmentação de imagem (como U-NET).</p>
```

```ad-quote
title:
**Principais Variantes**
```

```ad-quote
title:

| Camada | Descrição |
| --- | --- |
| CONV2DTRANSPOSE | Conhecida erroneamente como DECONVOLUÇÃO. Aumenta a dimensão espacial (UPSCALING) aprendendo pesos. |
| UPSAMPLING2D | Apenas aumenta o tamanho da imagem (ex: duplicando pixels) sem aprender pesos. |

```
````

---
