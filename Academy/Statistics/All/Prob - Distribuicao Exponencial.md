
---

```ad-quote
title: **Def**

**Distribuição de Poisson** foca na:
- **Contagem de eventos** em um intervalo contínuo (tempo, área, etc.).

**Distribuição Exponencial** foca no:
- **Tempo decorrido entre** esses eventos consecutivos.
```

---

```ad-example

#### **Distribuição Exponencial**
```

---

#### **01 )** - Distribuição Exponencial

```ad-quote
title: **Def**

A **Distribuição Exponencial** 
- É um modelo de probabilidade contínua que descreve a probabilidade do tempo até a ocorrência de um evento em um processo de Poisson. Em outras palavras, ela modela o tempo de espera entre eventos que acontecem a uma taxa média constante.
- A distribuição exponencial é a análoga contínua da distribuição geométrica e está intrinsecamente ligada à distribuição de Poisson.
```

![[Pasted image 20250626125547.png]]

---
#### **02 )** - Características Principais:

```ad-quote
title: **Def**

**Tempo Entre Eventos:** 
- Modela a probabilidade do tempo até um evento ocorrer. Exemplos incluem o tempo de vida de um componente eletrônico, o tempo até o próximo cliente chegar a uma loja, ou o tempo de espera para um ônibus.

**Parâmetro ($\lambda$):** 
- A distribuição é definida por um único parâmetro, $\lambda$ (lambda), que representa a **taxa média de ocorrência** de eventos por unidade de tempo. Este é o mesmo $\lambda$ da distribuição de Poisson.
```

---

```ad-quote
title: **Def**

**Função de Densidade de Probabilidade (FDP):** 
- A probabilidade de o tempo até o evento ser exatamente $x$ é dada por:

1. $$f(x; \lambda) = \lambda e^{-\lambda x}, \quad \text{para } x \ge 0$$

---

**Função cumulativa:** 
- Somatório das probabilidades até o evento

2. $$F(x < y) = 1 - e^{-\lambda x}$$

- Somatório das probabilidades após o evento

3. $$F(x > y) = e^{-\lambda x}$$

```

```ad-quote
title: **Def**

**Valor Esperado (Média):** 
- O tempo médio de espera até o próximo evento.

3. $$E[X] = \frac{1}{\lambda}$$

---

**Variância:** 
- A variância do tempo de espera.

4. $$Var(X) = \frac{1}{\lambda^2}$$
```

---
#### **03 )** - Propriedade de Falta de Memória

```ad-quote
title: **Def**

Uma característica crucial da distribuição exponencial é a **falta de memória**. Isso significa que a probabilidade de um evento ocorrer no futuro é independente do tempo que já se passou. Por exemplo, se um componente eletrônico já funcionou por 100 horas, a probabilidade de ele falhar na próxima hora é a mesma que a de um componente novo falhar na sua primeira hora de uso.

Matematicamente, para quaisquer $s, t \ge 0$:

$$P(X > s+t \mid X > s) = P(X > t)$$


```

---

```ad-error

#### **Resolução Exponencial**
```

---
#### **Ex )** - Condições para a Distribuição Exponencial

```ad-quote
title: **Def**

Um experimento pode ser modelado por uma Distribuição Exponencial se satisfaz as seguintes condições:
```

```ad-quote
title: **Def**

**Variável de Interesse (`X`):**
- A variável aleatória $X$ mede o **tempo** ou a **distância** até a ocorrência do **próximo evento** em um Processo de Poisson. Exemplos: tempo até a próxima chamada, distância até o próximo defeito.

**Taxa Média Constante ($\lambda$):** 
- Os eventos ocorrem a uma taxa média constante, denotada por $\lambda$ (lambda), por unidade de tempo ou espaço.

**Eventos Independentes:** 
- A ocorrência de um evento não influencia a ocorrência de outro. O tempo de espera para o próximo evento não depende de quanto tempo se passou desde o evento anterior (propriedade de falta de memória).
```

---
##### 01 ) - _Probabilidade de o tempo ser MENOR que x_

```ad-quote
title: **Def**

**Significado:** 
- Representa a probabilidade de o próximo evento ocorrer **antes** de um tempo (ou distância) específico $x$. Esta é a Função de Distribuição Acumulada (CDF).

---
**Cálculo:**
- $P(X \le x) = 1 - e^{-\lambda x}$

**Notação:** 
- $P(X \le x)$ ou $P(X < x)$
- *Para distribuições contínuas, $P(X \le x)$ é igual a $P(X < x)$.*
```
##### 02 ) - _Probabilidade de o tempo ser MAIOR que x_

```ad-quote
title: **Def**

**Significado:** 
- Representa a probabilidade de ter que esperar **mais** do que um tempo $x$ pelo próximo evento. É conhecida como Função de Sobrevivência.

---

**Cálculo:** 
- $P(X > x) = e^{-\lambda x}$

**Notação:** 
- $P(X > x)$ ou $P(X \ge x)$
- *Para distribuições contínuas, $P(X > x)$ é igual a $P(X \ge x)$.*

```
##### 03 ) - _Probabilidade de o tempo estar ENTRE a e b_

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de que o próximo evento ocorra em um intervalo específico, depois de um tempo $a$ e antes de um tempo $b$.

---

**Cálculo:** 
- $P(a < X < b) = P(X < b) - P(X < a)$
- $P(a < X < b) = (1 - e^{-\lambda b}) - (1 - e^{-\lambda a}) = e^{-\lambda a} - e^{-\lambda b}$

**Notação:** 
- $P(a < X < b)$

```
##### 04 ) - _Probabilidade de o tempo ser EXATAMENTE x_

```ad-quote
title: **Def**

**Significado:** 
- A probabilidade de o evento ocorrer em um instante de tempo *exato* e infinitesimal.

---

**Cálculo:** 
-  $P(X=x) = 0$

**Notação e Conceito:** 
- Em qualquer distribuição de probabilidade contínua, a probabilidade de a variável assumir um valor pontual específico é sempre **zero**. A probabilidade só é definida para **intervalos**.

```

---