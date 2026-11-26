
---

```ad-quote
title: **Def**

De forma resumida, uma **variável aleatória contínua** pode assumir qualquer valor dentro de um intervalo, sendo descrita por uma curva de densidade de probabilidade. As distribuições Uniforme e Normal são exemplos fundamentais.
```

---
#### **Diferença Chave**

```ad-quote
title: **Def**

**Variável aleatória contínua** 
- Pode assumir um número infinito de valores dentro de um intervalo específico. Diferente das variáveis discretas (que são contáveis), as contínuas são mensuráveis. A probabilidade não é atribuída a pontos específicos, mas a intervalos.
```

>[!quote] **YouTube:** [Variáveis Aleatórias](https://www.youtube.com/watch?v=9yHbl7p-yIY)

```ad-quote
title: **Def**

A distinção fundamental reside na natureza dos valores que a variável pode assumir.
- **Variável Discreta** assume valores contáveis (ex: 0, 1, 2, 3...).
- **Variável Contínua** assume qualquer valor em um intervalo (ex: altura, peso, tempo).

A probabilidade de uma variável contínua assumir um valor *exato* é zero. Por isso, sempre calculamos a probabilidade para um **intervalo de valores**.
```

---

```ad-example

#### **Distribuição Uniforme**
```

---
#### **01 )** - Distribuição Uniforme

```ad-quote
title: **Def**

A **Distribuição Uniforme Contínua** é o modelo mais simples para uma variável aleatória contínua. Nela, todos os resultados possíveis dentro de um intervalo $[a, b]$ são igualmente prováveis.
```

![[Pasted image 20250626125459.png]]

---
#### **02 )** - Características Principais:

```ad-quote
title: **Def**

**Intervalo Fixo:** 
- Descreve eventos onde cada ponto dentro de um intervalo tem a mesma chance de ocorrer. Por exemplo, o tempo de espera por um ônibus que chega a cada 15 minutos (o tempo de espera está uniformemente distribuído entre 0 e 15 minutos).
```

```ad-quote
title: **Def**

**Função Densidade de Probabilidade (FDP):** 
- A FDP, que descreve a curva de probabilidade, é constante dentro do intervalo $[a, b]$ e zero fora dele.

1. $$f(x) = \begin{cases} \frac{1}{b-a} & \text{para } a \le x \le b \\ 0 & \text{para } x < a \text{ ou } x > b \end{cases}$$

---

**Função de Distribuição Acumulada (FDA):**
- É obtida ao integrar a Função Densidade de Probabilidade (FDP, denotada por $f(t)$) desde o menor valor possível $(-\infty)$ até um ponto $x$.

2. $$F(x) = P(X \leq x) = \int_{-\infty}^{x} f(t) dt$$

```

```ad-quote
title: **Def**

**Esperança $E(X)$**

- A fórmula para a Esperança, ou valor esperado, de uma variável aleatória contínua $X$ é dada pela integral do produto de $x$ e sua função de densidade de probabilidade $f(x)$.


1. $$E(X) = \int_{-\infty}^{+\infty} f(x) \cdot x \, dx$$

---

2. $$E(X)=\frac{a+b}{2}$$

```

```ad-quote
title: **Def**

**Variância $V(X)$**

- Através da integral do quadrado da diferença entre $x$ e a média $(μ)$, ponderada pela função de densidade de probabilidade $f(x)$.

1. $$V(X) = \int_{-\infty}^{+\infty} f(x) \cdot (x - \mu)^2 \, dx$$

---

2. $$V(X)=\frac{(b-a)^2}{12}$$

```

---

```ad-example

#### **Distribuição Normal**
```

---
#### **01 )** - Distribuição Normal

```ad-quote
title: **Def**

**Distribuição Normal**
- Também conhecida como "curva de sino" ou Gaussiana, é a distribuição de probabilidade contínua mais importante em estatística. Ela descreve muitos fenômenos naturais e sociais, onde os valores tendem a se agrupar em torno de uma média central.
```

![[Pasted image 20250626125526.png]]

---
#### **02 )** - Características Principais

```ad-quote
title: **Def**

**Simetria em torno da Média:** 
- A curva é simétrica em relação à sua média. Média, mediana e moda são todas iguais.

**Parâmetros:** 
- É definida por dois parâmetros: a **média** ($\mu$), que localiza o centro da distribuição, e o **desvio padrão** ($\sigma$), que mede a dispersão ou largura da curva.
```

```ad-quote
title: **Def**

**Função Densidade de Probabilidade:**
  
  1. $$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}$$

 **Função de Probabilidade Acumulada:**
  
  2. $$F(x) = P(X \le x) = \int_{-\infty}^{x} \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{t-\mu}{\sigma}\right)^2} dt$$
```

 ```ad-quote
title: **Def**

**Valor Esperado (Média):**
  
  1. $$E[X] = \mu$$
 
 **Variância:**
  
  2. $$Var(X) = \sigma^2$$ 
```

---
#### **03 )** - $Z$-Score

```ad-quote
title: **Def**

O $Z$-Score transforma qualquer distribuição normal em uma: 
- Distribuição normal padrão, que tem média 0 e desvio padrão 1.

1. $$z = \frac{x - \mu}{\sigma}$$
```

```ad-quote
title: **Def**

**O que ela recebe Entradas:**

$x$ - Valor Individual: 
- É o ponto de dado ou o valor específico que você deseja analisar. 

$\mu$ - Média: 
- É a média de todos os valores no conjunto de dados (a média da população).

$\sigma$ - Desvio Padrão: 
- Ele mede o quão dispersos os dados estão em relação à média.

---

**O que ela retorna Saída:**

$z$ - $Z$-Score: 
-  ($x$) está distante da média ($\mu$).
```

```ad-quote
title: **Def**

 $Z$-Score - Positivo: 
 - O valor $x$ está acima da média. 
 - Um $Z$-Score de +2 significa que o valor está 2 desvios padrão acima da média.
 
 $Z$-Score - Negativo: 
 - O valor $x$ está abaixo da média. 
 - Um $Z$-Score de -1.5 significa que o valor está 1,5 desvios padrão abaixo da média.
 
 $Z$-Score - Igual a zero: 
 - O valor $x$ é exatamente igual à média.
```

---

