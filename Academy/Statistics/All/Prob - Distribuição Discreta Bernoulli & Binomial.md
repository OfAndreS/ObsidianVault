
---

```ad-quote
title: **Def**

Em estatística e teoria da probabilidade, uma: 
- **Distribuição de probabilidade discreta** 
  
Descreve a probabilidade de ocorrência de cada valor de uma variável aleatória que assume valores contáveis e distintos. As distribuições de Bernoulli e Binomial são exemplos fundamentais de distribuições discretas, aplicadas em cenários com resultados binários.
```

```ad-quote
title: **Def**

A distinção fundamental entre as duas distribuições reside no **número de ensaios**. 
- **Distribuição de Bernoulli** aplica-se a um **único ensaio**
- **Distribuição Binomial** descreve o **número de sucessos** em **múltiplos ensaios**. 

Em essência, a Distribuição Binomial é a soma de n distribuições de Bernoulli independentes e identicamente distribuídas.
```

>[!quote] **YouTubeEx:** [Distribuição de Bernoulli e Binomial - Exercício](https://www.youtube.com/watch?v=uXqnRAsZp70)

---

```ad-example

#### **Distribuição de Bernoulli**
```

---
#### **01 )** - Distribuição de Bernoulli

```ad-quote
title: **Def**

A **Distribuição de Bernoulli** é o modelo mais simples para um experimento aleatório com apenas dois resultados possíveis, rotulados como: 
- "Sucesso" (representado pelo valor 1) 
- "Fracasso" (representado pelo valor 0). 
  
Este experimento é conhecido como ensaio de Bernoulli.
```

>[!quote] **YouTube:** [Distribuição de Bernoulli](https://www.youtube.com/watch?v=7WVU8F-wLSU&t=128s)

![[Pasted image 20250626125027.png]]

---
#### **02 )** - Características Principais:

```ad-quote
title: **Def**

**Ensaio Único:** 
- Descreve a probabilidade de um único evento. Por exemplo, o lançamento de uma moeda (cara ou coroa), o resultado de um exame (positivo ou negativo) ou a aprovação de uma peça em um teste de qualidade (aprovada ou defeituosa).

**Parâmetro:** 
- A distribuição é definida por um único parâmetro, $p$, que representa a probabilidade de sucesso. A probabilidade de fracasso é, consequentemente, $1−p$.
```

```ad-quote
title: **Def**

**Função de Probabilidade:** 
- A probabilidade de se obter um resultado k (onde k pode ser 0 ou 1) é dada por: 

1. $$P(X=k)=p^{k}(1−p)^{1−k}$$

**Valor Esperado (Média):** 

2. $$E[X]=p$$

**Variância:** 

3. $$Var(X)=p(1−p)$$
```

---

```ad-example

#### **Distribuição Binomial**
```

---
#### **01 )** - Distribuição Binomial

```ad-quote
title: **Def**

A **Distribuição Binomial**, por sua vez, pode ser entendida como uma sequência de ensaios de Bernoulli. Ela modela o número de sucessos em uma quantidade fixa e independente de ensaios de Bernoulli, onde a probabilidade de sucesso é a mesma em cada ensaio.
```

>[!quote] **YouTube: ** [Distribuição Binomial](https://www.youtube.com/watch?v=dl-iS9dSn5M)

![[Pasted image 20250626124939.png]]

---
#### **03 )** - Fórmula

```ad-quote
title: **Def**

A fórmula da Distribuição Binomial é:

1. $$P(X=k) = C(n,k) \cdot p^k \cdot (1-p)^{n-k}$$

Onde:

$n$: 
  - É o número total de casos

$P(X=k)$ 
  - É a probabilidade de ter exatamente $k$ sucessos.

$C(n,k)$ 
  - É o coeficiente binomial o número de combinações de $n$ elementos tomados $k$.

```

---
#### **03 )** - Características Principais

```ad-quote
title: **Def**

**Múltiplos Ensaios:** 
- Utilizada quando se realiza um número fixo, n, de ensaios independentes. Por exemplo, o número de caras em 10 lançamentos de uma moeda, ou o número de peças defeituosas em um lote de 50.

**Valor Esperado (Média):** 

1. $$E[X]=np$$

**Variância:** 

2. $$Var(X)=np(1−p)$$
```

---

```ad-error

#### **Resolução Binomial**
```

---
#### **Ex )** - Condições para a Distribuição Binomial

```ad-quote
title: **Def**

Um experimento pode ser modelado por uma Distribuição Binomial se satisfaz as quatro condições seguintes:
```

```ad-quote
title: **Def**

**Número Fixo de Tentativas (`n`):** 
- O experimento consiste em um número fixo $n$ de tentativas idênticas.

**Natureza Dicotômica:** 
- Cada tentativa admite apenas dois resultados mutuamente exclusivos: "sucesso" ou "fracasso".

**Probabilidade de Sucesso Constante (`p`):** 
- A probabilidade de um sucesso, denotada por $p$, permanece constante para todas as $n$ tentativas. Consequentemente, a probabilidade de um fracasso é $q=1−p$.

**Independência das Tentativas:** 
- O resultado de qualquer tentativa é independente dos resultados das demais.
```

---
##### 01 ) - *Probabilidade de EXATAMENTE k sucessos*

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de ocorrer precisamente $k$ sucessos. Se a pergunta for "exatamente 5 sucessos", calcula-se $P(X=5)$.

---

**Notação:** 
- $P(X=k)$
```
##### 02 ) - *Probabilidade de NO MÁXIMO k sucessos*

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de ocorrer $k$ sucessos ou menos. É a soma das probabilidades de 0 sucessos, 1 sucesso, ..., até $k$ sucessos.

---

**Cálculo:** 
- $P(X≤k)=P(X=0)+P(X=1)+⋯+P(X=k)$

**Notação:** 
- $P(X≤k)$

```
##### 03 ) - *Probabilidade de PELO MENOS k sucessos*

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de ocorrer $k$ sucessos ou mais. É a soma das probabilidades de $k$ sucessos, $k+1$ sucessos, ..., até o máximo de $n$ sucessos.

---

**Cálculo:** 
- $P(X≥k)=P(X=k)+P(X=k+1)+⋯+P(X=n)$

**Notação:** 
- $P(X≥k)$

```
##### 03 ) - *Probabilidade de PELO MENOS k sucessos*

```ad-quote
title: **Def**

**Significado:** 
- Calcular $P(X≥k)$ pode ser trabalhoso. Muitas vezes, é mais fácil calcular a probabilidade do evento complementar e subtrair de 1.

---

**Cálculo:** 
-  $P(X≥1)=1−P(X=0)$

**Notação:** 
- $P(X≥k)=1−P(X<k)=1−P(X≤k−1)$ 

```

---
