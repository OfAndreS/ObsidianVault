
---

```ad-quote
title: **Def**

**Distribuição de Poisson** 
- Foca na Contagem de Eventos em um intervalo contínuo (tempo, área, etc.).

**Distribuição Geométrica** 
- Foca no Número de Ensaios de Bernoulli até o primeiro sucesso.
```

---

```ad-example

#### **Distribuição de Poisson**
```

---
#### **01 )** - Distribuição de Poisson

```ad-quote
title: **Def**

A **Distribuição de Poisson** é um modelo de probabilidade discreta que descreve o número de vezes que um evento ocorre em um intervalo fixo de tempo ou espaço, dada uma taxa média de ocorrência conhecida e constante.
```

>[!quote] **YouTube: ** [Distribuição Poisson](https://www.youtube.com/watch?v=VYIjpV2coU0)

![[Pasted image 20250626125218.png]]

---
#### **02 )** - Características Principais:

```ad-quote
title: **Def**

**Contagem de Eventos:** 
- Modela a probabilidade de um número específico de eventos ocorrer em um intervalo. Exemplos incluem o número de chamadas recebidas por um call center em uma hora ou o número de defeitos em um metro de tecido.

**Parâmetro ($\lambda$):** 
- A distribuição é definida por um único parâmetro, $\lambda$ (lambda), que representa a taxa média de ocorrência (o número esperado de eventos) no intervalo.
```

```ad-quote
title: **Def**

**Função de Probabilidade:** 
- A probabilidade de ocorrerem exatamente $k$ eventos no intervalo é dada por: 

1. $$P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$$


Onde:

$\lambda:$
- $\lambda=n\cdot p$
  
$P(X=k)$ 
  - É a probabilidade de ter exatamente $k$ sucessos.
```

```ad-quote
title: **Def**
**Valor Esperado (Média):** 

2. $$E[X] = \lambda$$

**Variância:** 

3. $$Var(X) = \lambda$$
```

---

```ad-example

#### **Distribuição Geométrica**
```

---
#### **01 )** - Distribuição Geométrica

```ad-quote
title: **Def**

A **Distribuição Geométrica** 
- É um modelo de probabilidade discreta que descreve o número de ensaios de Bernoulli independentes necessários para se obter o primeiro sucesso.
```

>[!quote] **YouTube:** [Distribuição Geométricas](https://www.youtube.com/watch?v=9mMoL0yZqa0&t=348s)

![[Pasted image 20250626125322.png]]

---
#### **02 )** - Características Principais

```ad-quote
title: **Def**

**Ensaios até o Sucesso:** 
- Utilizada quando se está interessado em saber "quantas tentativas até o primeiro sucesso?". Por exemplo, o número de lançamentos de uma moeda até a primeira "cara" ou o número de vezes que um jogador tenta um arremesso até acertar a primeira cesta.

**Parâmetro ($p$):** 
- A distribuição é definida pelo parâmetro $p$, a probabilidade de sucesso em um único ensaio, que é constante para todas as tentativas.
  
**Obs:**
- A distribuição geométrica guarda "mémoria dos eventos anteriores".
- Portanto, se depois de 10 jogadas de moeda não ocorreu nenhum cara, qual a probabilidade da 12º moeda ser cara? Ou seja, $P(X = 12 | X > 10) = P(X = 2)$"
```

```ad-quote
title: **Def**

**Função de Probabilidade:** 
- A probabilidade de o primeiro sucesso ocorrer na $k$-ésima tentativa é:

1. $$P(X=k) = (1-p)^{k-1} p$$

- A probabilidade do fracasso dado $k$-ésima tentativas é:

2. $$P(\text{Não Acertar})=(1-P)^k$$

```

```ad-quote
title: **Def**
**Valor Esperado (Média):** 

3. $$E[X] = \frac{1}{p}$$

**Variância:** 

4. $$Var(X) = \frac{1-p}{p^2}$$

```

---

```ad-error

#### **Resolução de Poisson**
```

---
#### **Ex )** - Condições para a Distribuição de Poisson


```ad-quote
title: **Def**

Um experimento pode ser modelado por uma Distribuição de Poisson se satisfaz as seguintes condições:
```

```ad-quote
title: **Def**

**Eventos Independentes:** 
- A ocorrência de um evento em um intervalo não afeta a probabilidade de ocorrência de outro evento em um intervalo distinto.

**Taxa Média Constante ($\lambda$):** 
- A taxa média de ocorrência dos eventos, denotada por $\lambda$ (lambda), é constante para o tipo de intervalo considerado (seja tempo, área, distância, etc.).

**Ocorrências Não Simultâneas:**
- É virtualmente impossível que dois eventos ocorram exatamente no mesmo instante de tempo ou ponto no espaço.

**Probabilidade Proporcional ao Intervalo:**
- Para um intervalo muito pequeno, a probabilidade de ocorrer um evento é proporcional ao tamanho desse intervalo.
```

---
##### 01 ) - _Probabilidade de EXATAMENTE k eventos_

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de ocorrer precisamente $k$ eventos no intervalo definido. Se a pergunta for "exatamente 5 chamadas", calcula-se $P(X=5)$.

---

**Notação:** 
- $P(X=k)$
```
##### 02 ) - _Probabilidade de NO MÁXIMO k eventos_

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de ocorrer $k$ eventos ou menos. É a soma das probabilidades de 0 eventos, 1 evento, ..., até $k$ eventos.

---

**Cálculo:** 
- $P(X \le k) =P(X=0) + P(X=1) + \dots + P(X=k)$

**Notação:** 
- $P(X \le k)$

```
##### 03 ) - _Probabilidade de PELO MENOS k eventos_

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de ocorrer $k$ eventos ou mais. É a soma das probabilidades de $k$ eventos, $k+1$ eventos, e assim por diante, teoricamente até o infinito.

---

**Cálculo:** 
- $P(X \ge k) = P(X=k) + P(X=k+1) + \dots + P(X=\infty)$

**Notação:** 
- $P(X \ge k)$

```
##### 04 ) - _Uso da Regra do Complemento_

```ad-quote
title: **Def**

**Significado:** 
- Como o cálculo de $P(X≥k)$ envolve uma soma infinita, ele é quase sempre resolvido com a regra do evento complementar.

---

**Cálculo (Exemplo "Pelo menos 1"):** 

- $P(X \ge 1) = 1 - P(X=0)$

**Notação (Geral):** 

- $P(X \ge k) = 1 - P(X < k)

```

---

```ad-error

#### **Resolução Geométrica**
```

---
#### **Ex )** - Condições para a Distribuição Geométrica

```ad-quote

Um experimento pode ser modelado por uma Distribuição Geométrica se satisfaz as seguintes condições:
```

```ad-quote

**Natureza Dicotômica:** 
- Cada tentativa (ou ensaio) admite apenas dois resultados mutuamente exclusivos: "sucesso" ou "fracasso".

**Probabilidade de Sucesso Constante (`p`):** 
- A probabilidade de um sucesso, denotada por $p$, permanece constante para todas as tentativas. Consequentemente, a probabilidade de um fracasso é $q=1−p$.

**Independência das Tentativas:** 
- O resultado de qualquer tentativa é independente dos resultados das demais.

**Variável de Interesse (`X`):**
- O experimento continua **até que o primeiro sucesso seja observado**. A variável aleatória $X$ representa o **número da tentativa** em que o primeiro sucesso ocorre.
```

---
##### 01 ) - _Probabilidade de o 1º sucesso ocorrer na tentativa k_

```ad-quote

**Significado:** 
- A probabilidade de as primeiras $k-1$ tentativas serem "fracassos" e a $k$-ésima tentativa ser o primeiro "sucesso". Se a pergunta for "a primeira compra ocorrer na 5ª visita", calcula-se $P(X=5)$.

---
**Cálculo:**
- $P(X=k) = (1-p)^{k-1} \cdot p$

**Notação:** 
- $P(X=k)$
```
##### 02 ) - _Probabilidade de o 1º sucesso ocorrer EM ATÉ k tentativas_

```ad-quote

**Significado:** 
- A probabilidade de o primeiro sucesso ocorrer na tentativa 1, OU na 2, ..., OU na k-ésima tentativa.

---

**Cálculo:** 
- $P(X \le k) = P(X=1) + P(X=2) + \dots + P(X=k)$
- **Forma Simplificada:** $P(X \le k) = 1 - (1-p)^k$

**Notação:** 
- $P(X \le k)$

```
##### 03 ) - _Probabilidade de precisar de MAIS DE k tentativas_

```ad-quote

**Significado:** 
- A probabilidade de que o primeiro sucesso ocorra somente **após** a k-ésima tentativa. Isso é o mesmo que dizer que as primeiras $k$ tentativas foram todas "fracassos".

---

**Cálculo:** 
- $P(X > k) = (1-p)^k$

**Notação:** 
- $P(X > k)$

```
##### 04 ) - _Uso da Regra do Complemento_

```ad-quote
title: **Def**

**Significado:** 
- Na distribuição geométrica, a relação complementar é fundamental. A probabilidade de precisar de **mais de k** tentativas é o complemento da probabilidade de conseguir o sucesso **em até k** tentativas.

---

**Cálculo:** 

- $P(X \le k) = 1 - P(X > k)$

**Notação:** 
- $P(X > k) = 1 - P(X \le k)$

```

---