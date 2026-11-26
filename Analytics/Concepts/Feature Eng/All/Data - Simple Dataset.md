
---

````ad-quote
title:

##### **Intro )** - Datasets Clássicos para Aprendizado Supervisionado

```ad-quote
title:
<p align="justify">Aqui está uma lista de datasets clássicos, simples e já tratados (ou que exigem tratamento mínimo), perfeitos para quem está começando a treinar redes neurais em tarefas de aprendizado supervisionado.</p>
```

```ad-quote
title:
<p align="justify">Eles são amplamente utilizados em cursos e tutoriais exatamente por serem "prontos para usar".</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **A )** - Datasets para Classificação (Prever uma Categoria)

```ad-quote
title:
<p align="justify">Estes são problemas onde a saída é um rótulo discreto (ex: "gato", "cachorro"; "tipo A", "tipo B").</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **1. Iris Dataset**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Classificar espécies de flores (Setosa, Versicolor, Virginica) com base nas medidas de suas pétalas e sépalas.</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">É o "Hello, World!" dos datasets de machine learning. Pequeno, limpo e muito fácil de entender.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">4 características numéricas, 150 amostras, 3 classes.</p>
```
```ad-quote
title:
**Como carregar (usando Scikit-learn):**
```
```python
from sklearn.datasets import load_iris
iris = load_iris()
X, y = iris.data, iris.target
```
````

````ad-quote
title:
```ad-quote
title:
###### **2. Wine Dataset**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Determinar a origem de vinhos (3 tipos diferentes) com base em sua análise química.</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">Um passo além do Iris, com mais características. Continua sendo um dataset pequeno e limpo.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">13 características numéricas, 178 amostras, 3 classes.</p>
```
```ad-quote
title:
**Como carregar (usando Scikit-learn):**
```
```python
from sklearn.datasets import load_wine
wine = load_wine()
X, y = wine.data, wine.target
```
````

````ad-quote
title:
```ad-quote
title:
###### **3. Wisconsin Breast Cancer Dataset**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Diagnosticar se um tumor é maligno ou benigno com base em características extraídas de imagens.</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">Excelente para praticar classificação binária (apenas duas classes). Os dados são numéricos e limpos.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">30 características numéricas, 569 amostras, 2 classes (maligno/benigno).</p>
```
```ad-quote
title:
**Como carregar (usando Scikit-learn):**
```
```python
from sklearn.datasets import load_breast_cancer
cancer = load_breast_cancer()
X, y = cancer.data, cancer.target
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **B )** - Datasets para Regressão (Prever um Valor Numérico)

```ad-quote
title:
<p align="justify">Estes são problemas onde a saída é um número contínuo (ex: preço, temperatura, idade).</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **1. California Housing Dataset**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Prever o valor mediano de uma casa em um distrito da Califórnia com base em características demográficas e geográficas.</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">É o substituto moderno do clássico "Boston Housing". É um problema de regressão claro, com dados limpos e um bom número de amostras.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">8 características numéricas, 20.640 amostras.</p>
```
```ad-quote
title:
**Como carregar (usando Scikit-learn):**
```
```python
from sklearn.datasets import fetch_california_housing
housing = fetch_california_housing()
X, y = housing.data, housing.target
```
````

````ad-quote
title:
```ad-quote
title:
###### **2. Diabetes Dataset**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Prever a progressão da diabetes um ano após o início, com base em variáveis fisiológicas.</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">É um dataset de regressão muito pequeno e as 10 características já vêm normalizadas, o que facilita muito o treinamento de redes neurais.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">10 características numéricas (já normalizadas), 442 amostras.</p>
```
```ad-quote
title:
**Como carregar (usando Scikit-learn):**
```
```python
from sklearn.datasets import load_diabetes
diabetes = load_diabetes()
X, y = diabetes.data, diabetes.target
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **C )** - Datasets de Imagens (Clássicos para Redes Neurais Convolucionais - CNNs)

```ad-quote
title:
<p align="justify">Embora sejam problemas de classificação, os datasets de imagem são uma categoria especial e fundamental para o estudo de redes neurais.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **1. MNIST Handwritten Digits**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Reconhecer dígitos de 0 a 9 escritos à mão.</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">É o "Hello, World!" das redes neurais para visão computacional. Imagens pequenas (28x28 pixels), em escala de cinza e já pré-processadas.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">60.000 imagens de treino e 10.000 de teste, 10 classes (dígitos 0-9).</p>
```
```ad-quote
title:
**Como carregar (usando Keras/TensorFlow):**
```
```python
from tensorflow.keras.datasets import mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()
```
````

````ad-quote
title:
```ad-quote
title:
###### **2. Fashion-MNIST**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Classificar 10 tipos de artigos de vestuário (camisetas, calças, sapatos, etc.).</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">É um substituto direto do MNIST, com o mesmo formato, mas um pouco mais desafiador, forçando a criação de modelos melhores.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">60.000 imagens de treino e 10.000 de teste, 10 classes (tipos de roupa).</p>
```
```ad-quote
title:
**Como carregar (usando Keras/TensorFlow):**
```
```python
from tensorflow.keras.datasets import fashion_mnist
(x_train, y_train), (x_test, y_test) = fashion_mnist.load_data()
```
````

````ad-quote
title:
```ad-quote
title:
###### **3. CIFAR-10**
```

```ad-quote
title:
**Objetivo:**
```
```ad-quote
title:
<p align="justify">Classificar pequenas imagens coloridas em 10 categorias (avião, carro, pássaro, gato, etc.).</p>
```
```ad-quote
title:
**Por que é bom?:**
```
```ad-quote
title:
<p align="justify">É o próximo passo lógico após o MNIST. As imagens são coloridas (3 canais de cor) e o problema é significativamente mais complexo, sendo um ótimo benchmark para arquiteturas de CNNs.</p>
```
```ad-quote
title:
**Características:**
```
```ad-quote
title:
<p align="justify">Imagens coloridas (32x32 pixels), 50.000 de treino e 10.000 de teste, 10 classes.</p>
```
```ad-quote
title:
**Como carregar (usando Keras/TensorFlow):**
```
```python
from tensorflow.keras.datasets import cifar10
(x_train, y_train), (x_test, y_test) = cifar10.load_data()
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">Esses datasets são o ponto de partida ideal. Eles estão disponíveis nas principais bibliotecas de machine learning e permitem que você foque em entender e construir os modelos de redes neurais, em vez de se preocupar com a limpeza e o pré-processamento dos dados.</p>
```
````

---