
---
#### **1 ) Introdução** - *O Que São e Por Que Usar Variáveis Aleatórias?*

```ad-quote
title: **Def**

Em muitos experimentos aleatórios, os resultados podem não ser números (ex: "cara" ou "coroa", "doente" ou "sadio"). A análise matemática e estatística se torna muito mais poderosa quando podemos associar **valores numéricos** a esses resultados. É aqui que entram as variáveis aleatórias.
```
##### *Definição Formal*

```ad-quote
title: **Def**

Uma **variável aleatória (V.A.)** é uma função $X$ que mapeia cada resultado $s$ de um espaço amostral $\Omega$ a um número real.

$$
X: \Omega \rightarrow \mathbb{R}
$$

Onde:
* $\Omega$ é o conjunto de todos os resultados possíveis de um experimento aleatório.
* $s$ é um elemento de $\Omega$ ($s \in \Omega$).
* $\mathbb{R}$ é o conjunto dos números reais.
* $X(s)$ é o número real associado ao resultado $s$.
```

```ad-quote
title: **Def**

Essencialmente, uma V.A. **quantifica** os resultados de um experimento, permitindo-nos:

**01 )**
- Calcular probabilidades de eventos numéricos.

**02 )**
- Descrever distribuições de probabilidade usando funções matemáticas.

**03 )**
- Calcular medidas resumo, como **média (valor esperado)** e **variância**, que caracterizam o fenômeno.

**04 )**
- Construir modelos probabilísticos e realizar inferência estatística.

```

>[!error] **Ex )** *Exemplo Clássico: Três moedas*

![[Pasted image 20250525174639.png]]

```ad-quote
title: **Def**

Para toda variável aleatória sempre existira: 
- O espaço amostral $\Omega$ contendo todas as possibilidades do evento ocorrer
- A distribuição das probabilidáde denotada por $P(X = x)$
- Gráfico com a distribuição de probabilidades
```

>[!error] **Ex )** *Exemplo Clássico: Uma moeda*

![[Pasted image 20250615104505.png]]

![[Pasted image 20250615110904.png]]

```ad-quote
title: **Def**

Para o gráfico é desejável que:
- As colunas representem as possibilidades 
- As linhas o $x$
```

---
#### **2 )** - *Tipos de Variáveis Aleatórias*

```ad-quote
title: **Def**

As variáveis aleatórias são classificadas com base na natureza do conjunto de valores que podem assumir (sua *imagem*).
```

```ad-quote
title: **Def**

###### **Variáveis Aleatórias Discretas**

Uma V.A. é **discreta** se o conjunto de seus valores possíveis (sua imagem) é **finito** ou **infinito enumerável**. Geralmente, estão associadas a processos de **contagem**.

- **Finito** 


- **Infinito Enumerável** 

```

```ad-quote
title: **Def**

###### **Variáveis Aleatórias Contínuas**

Uma V.A. é **contínua** se o conjunto de seus valores possíveis é **infinito não enumerável**, geralmente correspondendo a um **intervalo** de números reais. Estão associadas a processos de **medição**.
```

---
#### **3 )** - *Distribuição de Probabilidade Discreta 📈*

```ad-quote
title: **Def**

Para uma V.A. discreta, sua distribuição de probabilidade descreve como a probabilidade total (1) está distribuída entre seus possíveis valores. A principal ferramenta para isso é a **Função Massa de Probabilidade (FMP)**.
```

##### **3.1 )** - *Função Massa de Probabilidade (FMP)*

```ad-quote
title: **Def**

A FMP, denotada por $p_X(x)$ ou $P(X=x)$, dá a probabilidade de que a V.A. $X$ assuma *exatamente* o valor $x$.

1. $$p_X(x) = P(X = x)$$

---

**Propriedades da FMP:**

Não-negatividade: 
- $p_X(x) \ge 0$ para todo $x$.

Soma Unitária: 
- $\sum_{x} p_X(x) = 1$, onde a soma é sobre todos os valores $x$ que $X$ pode assumir.
```
##### **3.2 )** - *Representações da Distribuição*

```ad-quote
title: **Def**

Podemos representar uma distribuição discreta de várias formas:

**Tabela:** 
- Útil para V.A. com poucos valores.

**Gráfico de Barras:** 
- Visualiza a FMP, com barras em cada valor $x$ e altura $p_X(x)$.

**Fórmula:** 
- Uma função matemática que define $p_X(x)$.

**Exemplo:** $P(X=x) = x/10$ para $x \in \{1, 2, 3, 4\}$.
```

| X        | P(X=x) = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = |
| :------- | :------------------------------------------------------------------------------- |
| 1        | 0.1                                                                              |
| 2        | 0.2                                                                              |
| 3        | 0.3                                                                              |
| 4        | 0.4                                                                              |
| **Soma** | **1.0**                                                                          |
##### **3.3 )** - *Tipos Comuns de Distribuições Discretas*

```ad-quote
title: **Def**

* **Uniforme Discreta:** Todos os $n$ valores têm a mesma probabilidade $1/n$.
* **Bernoulli:** Um único ensaio com dois resultados (sucesso/fracasso). $X \in \{0, 1\}$.
* **Binomial:** Número de sucessos em $n$ ensaios de Bernoulli independentes.
* **Poisson:** Número de eventos em um intervalo (tempo/espaço).
* **Geométrica:** Número de ensaios até o primeiro sucesso (como o exemplo das figurinhas).
```

---
#### **4 )** - *Função de Distribuição Acumulada (FDA)*

```ad-quote
title: **Def**

A FDA (ou CDF - Cumulative Distribution Function), $F_X(x)$, é uma ferramenta poderosa que funciona para **ambos** os tipos de V.A. (discretas e contínuas). Ela nos dá a probabilidade de que a V.A. $X$ assuma um valor **menor ou igual a $x$**.
```

>[!quote] **Link:** [FDA](https://www.youtube.com/watch?v=F9fXrpqCttI&list=PLNG6I1M7eOuxtORJqqgIkUUbwuddrirb6&index=14)
##### *Definição*

```ad-quote
title: **Def**

**Fórmula:**

1. $$F_X(x) = P(X \le x)$$
```
##### *Cálculo para V.A. Discretas*

```ad-quote
title: **Def**

Para uma V.A. discreta, a FDA é calculada somando as probabilidades da FMP para todos os valores $u$ menores ou iguais a $x$:

1. $$F_X(x) = \sum_{u \le x} p_X(u)$$

```
##### *Propriedades Gerais da FDA*

```ad-quote
title: **Def**

**Limites:** 
- $F_X(-\infty) = 0$ e $F_X(+\infty) = 1$.

**Não-Decrescente:** 
- Se $a < b$, então $F_X(a) \le F_X(b)$.

**Contínua à Direita:** 
- $\lim_{h \to 0^+} F_X(x+h) = F_X(x)$.

Para V.A. discretas, a FDA é uma **função em escada**, com saltos nos valores $x$ onde $p_X(x) > 0$. A altura do salto em $x$ é igual a $p_X(x)$.
```

##### *Utilidade da FDA*

* Calcula probabilidades de intervalos: $P(a < X \le b) = F_X(b) - F_X(a)$.
* Permite encontrar a FMP: $p_X(x) = F_X(x) - F_X(x^-)$ (onde $x^-$ é o valor imediatamente anterior a $x$).
* Facilita a determinação de *quantis* ou *percentis*.

**Exemplo (Figurinhas):** $P(X=x) = (0.8)^{x-1} \times 0.2$.

| x | P(X=x) | F(x) = P(X <= x) |
| :-: | :----: | :--------------: |
| 1 | 0.200 | 0.200 |
| 2 | 0.160 | 0.360 |
| 3 | 0.128 | 0.488 |
| ... | ... | ... |
| 10 | ~0.027 | ~0.893 |
| 11 | ~0.021 | ~0.914 |

O gráfico da FMP é decrescente, enquanto o gráfico da FDA é uma escada crescente que se aproxima de 1.

---

#### **5 )** - *Valor Esperado e Variância (Características Numéricas)*

As variáveis aleatórias nos permitem calcular medidas resumo importantes:

### 5.1. Valor Esperado (Esperança Matemática)

O **valor esperado**, $E[X]$, é a média ponderada dos valores possíveis de $X$, onde os pesos são as probabilidades. Representa o valor médio que esperamos observar em muitas repetições do experimento.

Para V.A. Discretas:
$$
E[X] = \mu_X = \sum_x x \cdot p_X(x)
$$

### 5.2. Variância

A **variância**, $Var(X)$ ou $\sigma_X^2$, mede a dispersão dos valores de $X$ em torno do seu valor esperado. É a média do quadrado dos desvios.

Para V.A. Discretas:
$$
Var(X) = \sigma_X^2 = E[(X - \mu_X)^2] = \sum_x (x - \mu_X)^2 \cdot p_X(x)
$$
Uma fórmula de cálculo mais conveniente é:
$$
Var(X) = E[X^2] - (E[X])^2
$$
O **desvio padrão**, $\sigma_X = \sqrt{Var(X)}$, é a raiz quadrada da variância e tem a mesma unidade de medida de $X$.

---

#### **6 )** - *Exercícios e Aplicações*

Os conceitos de V.A., FMP e FDA são aplicados para resolver problemas práticos, como:
* Calcular a probabilidade de um número específico de sucessos ou falhas.
* Determinar a probabilidade de um evento ocorrer dentro de um certo intervalo.
* Encontrar a probabilidade acumulada até um ponto.
* Derivar uma função de distribuição a partir da descrição de um problema.
* Modelar fenômenos em finanças, engenharia, ciências sociais, etc.

---

#### **7 )** - *Revisão*

* **Variáveis Aleatórias** convertem resultados de experimentos em números.
* Elas podem ser **Discretas** (contáveis) ou **Contínuas** (intervalos).
* A **FMP** ($p_X(x)$) descreve a probabilidade de cada valor discreto.
* A **FDA** ($F_X(x)$) descreve a probabilidade acumulada $P(X \le x)$ para qualquer V.A.
* **Valor Esperado** e **Variância** são medidas numéricas chave que caracterizam a distribuição.

---

>[!done] **IMG )** - *Imagem Base*

---
###### *Imagem de referência)*

![[Pasted image 20250525082911.png]]

---

>[!error] **Ex )** *Exemplo Clássico*

---
###### *Problema 02)*

```ad-quote
title: **Def**
**Calcule:**

1. $$P(X \leq 1), P(X \leq 2) \text{ e } P(X \leq 3)$$

Vamos calcular as probabilidades solicitadas com base na tabela:
```

```ad-quote
title: **Def**

**P(X≤1):**
    
Esta é a probabilidade de João conseguir a figurinha que ele quer no primeiro pacote.
    
1. $$P(X≤1)=P(X=1)$$
    
2. $$P(X≤1)=0.2$$
    
---

**P(X≤2):**
    
Esta é a probabilidade de João conseguir a figurinha que ele quer no primeiro ou no segundo pacote.
    
1. $$P(X≤2)=P(X=1)+P(X=2)$$
    
2. $$P(X≤2)=0.2+0.16$$
    
3. $$P(X≤2)=0.36$$
    
---

**P(X≤3):**
    
Esta é a probabilidade de João conseguir a figurinha que ele quer no primeiro, segundo ou terceiro pacote.
    
1. $$P(X≤3)=P(X=1)+P(X=2)+P(X=3)$$
    
2. $$P(X≤3)=0.2+0.16+0.128$$
    
3. $$P(X≤3)=0.488$$
```

---

>[!error] **Ex )** *Exemplo Clássico*

---
