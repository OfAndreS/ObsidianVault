---
banner: "![[Pasted image 20251013130404.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Inicialização de Pesos: O Guia Definitivo com Fórmulas e Código

```ad-quote
title:
<p align="justify">A inicialização de pesos é o processo de definir os valores iniciais para os parâmetros (pesos e biases) de uma rede neural antes do início do treinamento. É um dos passos mais críticos, pois uma escolha inadequada pode levar a um treinamento lento, instável ou até mesmo a uma falha completa na aprendizagem.</p>
```

```ad-quote
title:
###### O objetivo de uma boa inicialização
```

```ad-quote
title:


| Conceito | Definição |
| --- | --- |
|Quebrar a Simetria:|Garantir que neurônios diferentes aprendam características diferentes.|
|Manter a Variância do Sinal:|Evitar que as saídas das camadas (ativações) e os gradientes se tornem nulos (gradiente evanescente) ou infinitos (gradiente explosivo) à medida que se propagam pela rede.|
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Inicialização com Zeros - Não recomendada

```ad-quote
title:
<p align="justify">A ideia mais simples, porém a mais problemática.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Intuição**
```
```ad-quote
title:
<p align="justify">Começar do "zero", um ponto neutro. O problema é que essa neutralidade é uma armadilha. Se todos os pesos são zero, todos os neurônios em uma camada produzem a mesma saída. Durante o backpropagation, todos recebem o mesmo gradiente e, portanto, são atualizados da mesma maneira. Eles nunca se diferenciam, e a rede perde sua capacidade de aprender.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **A Fórmula**
```
```ad-quote
title:
1. $$W_{ij} = 0 \quad \text{para todo } i, j$$
```
````

````ad-quote
title:
```ad-quote
title:
###### **Equivalência em Keras**
```
```python
from tensorflow.keras.layers import Dense
from tensorflow.keras import initializers

# Usando a string de atalho
dense_layer = Dense(64, kernel_initializer='zeros')

# Ou usando a classe do inicializador (para mais controle)
dense_layer = Dense(64, kernel_initializer=initializers.Zeros())
```
````

````ad-quote
title:
```ad-quote
title:
###### **Recomendação**
```
```ad-quote
title:
<p align="justify">NUNCA use para inicializar pesos em camadas ocultas. É a receita para a falha do treinamento.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Inicialização Aleatória Simples

```ad-quote
title:
<p align="justify">A primeira solução real para o problema da simetria, mas que requer cuidado.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Intuição**
```
```ad-quote
title:
<p align="justify">Se os pesos começam com valores aleatórios pequenos e diferentes, cada neurônio seguirá um caminho de aprendizado único. O desafio é escolher a "magnitude" correta desses valores. Valores muito grandes causam explosão de gradientes; valores muito pequenos causam o desaparecimento.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **A Fórmula**
```
```ad-quote
title:
<p align="justify">Os pesos são amostrados de uma distribuição.</p>
```
```ad-quote
title:
**Distribuição Normal (Gaussiana):**

1. $$W \sim \mathcal{N}(\mu, \sigma^2)$$

- <p align="justify">Onde a média μ é tipicamente 0 e o desvio padrão σ é um valor pequeno (ex: 0.01).</p>
```
```ad-quote
title:
**Distribuição Uniforme:**

1. $$W \sim U[-limit, limit]$$

- <p align="justify">Onde limit é um valor pequeno (ex: 0.05).</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Equivalência em Keras**
```
```python
# Inicialização a partir de uma distribuição Normal
dense_layer = Dense(64, kernel_initializer=initializers.RandomNormal(mean=0.0, stddev=0.05))

# Inicialização a partir de uma distribuição Uniforme
dense_layer = Dense(64, kernel_initializer=initializers.RandomUniform(minval=-0.05, maxval=0.05))
```
````

````ad-quote
title:
```ad-quote
title:
###### **Recomendação**
```
```ad-quote
title:
<p align="justify">Funciona para redes muito rasas, mas é frágil e inadequada para redes profundas (Deep Learning), pois não garante a estabilidade da variância.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Inicialização de Xavier / Glorot

```ad-quote
title:
<p align="justify">Uma abordagem inteligente que se tornou padrão para certas arquiteturas. Foi projetada para manter a variância das ativações e dos gradientes constante entre as camadas.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Intuição**
```
```ad-quote
title:
<p align="justify">A variância dos pesos é ajustada com base no número de neurônios de entrada (fan_in) e de saída (fan_out) da camada. Isso cria um equilíbrio que impede o sinal de diminuir ou aumentar drasticamente.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Funções de Ativação Ideais**
```
```ad-quote
title:
<p align="justify">tanh e sigmoid, que são simétricas em torno de zero.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **A Fórmula**
```
```ad-quote
title:
**Uniforme (Glorot Uniform):**

1. $$W \sim U \left[ -\sqrt{\frac{6}{fan_{in} + fan_{out}}}, \sqrt{\frac{6}{fan_{in} + fan_{out}}} \right]$$
```
```ad-quote
title:
**Normal (Glorot Normal):** Os pesos são amostrados de $\mathcal{N}(0, \sigma^2)$ com variância:

1. $$\sigma^2 = \frac{2}{fan_{in} + fan_{out}}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### **Equivalência em Keras**
```
```python
# Usando a string de atalho (Glorot Uniform é o padrão para Dense, Conv2D, etc.)
dense_layer = Dense(64, activation='tanh', kernel_initializer='glorot_uniform')

# Usando a versão Normal
dense_layer = Dense(64, activation='tanh', kernel_initializer='glorot_normal')

# Usando a classe do inicializador
dense_layer = Dense(64, activation='tanh', kernel_initializer=initializers.GlorotNormal())
```
````

````ad-quote
title:
```ad-quote
title:
###### **Recomendação**
```
```ad-quote
title:
<p align="justify">Excelente escolha para redes que usam tanh ou sigmoid. Por ser o padrão em Keras, muitas vezes já está sendo usada sem que o programador precise especificá-la.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Inicialização de He (Kaiming)

```ad-quote
title:
<p align="justify">A evolução da inicialização de Xavier, adaptada para a função de ativação mais popular da atualidade: a ReLU.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Intuição**
```
```ad-quote
title:
<p align="justify">A ReLU zera todas as ativações negativas, o que corta a variância pela metade em comparação com uma função como a tanh. A inicialização de He compensa isso dobrando a variância dos pesos, mantendo a energia do sinal estável através da rede.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Funções de Ativação Ideais**
```
```ad-quote
title:
<p align="justify">ReLU e suas variantes (Leaky ReLU, PReLU, ELU).</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **A Fórmula**
```
```ad-quote
title:
<p align="justify">A variância é baseada apenas no número de entradas (fan_in).</p>
```
```ad-quote
title:
**Uniforme (He Uniform):**

1. $$W \sim U \left[ -\sqrt{\frac{6}{fan_{in}}}, \sqrt{\frac{6}{fan_{in}}} \right]$$
```
```ad-quote
title:
**Normal (He Normal):** Os pesos são amostrados de $\mathcal{N}(0, \sigma^2)$ com variância:

1. $$\sigma^2 = \frac{2}{fan_{in}}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### **Equivalência em Keras**
```
```python
# Usando a string de atalho para a versão Normal
dense_layer = Dense(64, activation='relu', kernel_initializer='he_normal')

# Usando a string de atalho para a versão Uniforme
dense_layer = Dense(64, activation='relu', kernel_initializer='he_uniform')

# Usando a classe do inicializador
dense_layer = Dense(64, activation='relu', kernel_initializer=initializers.HeNormal())
```
````

````ad-quote
title:
```ad-quote
title:
###### **Recomendação**
```
```ad-quote
title:
<p align="justify">O padrão ouro e a escolha mais segura para qualquer rede neural profunda moderna. Se você está usando ReLU, esta deve ser sua primeira opção.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Tabela Resumo: Guia Rápido de Escolha

```ad-quote
title:

| Técnica de Inicialização | Função de Ativação Ideal | Nome em Keras (String) | Quando Usar |
| --- | --- | --- | --- |
| Zeros | Nenhuma | `'zeros'` | NUNCA para pesos (talvez para biases) |
| Random Uniform/Normal | Todas (com cuidado) | (via classe) | Redes muito rasas ou para experimentação |
| Glorot / Xavier | `tanh`, `sigmoid` | `'glorot_uniform'` (padrão), `'glorot_normal'` | Redes com ativações simétricas |
| He / Kaiming | `relu`, `leaky_relu` | `'he_normal'`, `'he_uniform'` | A ESCOLHA PADRÃO para redes profundas modernas |

```
````

---
