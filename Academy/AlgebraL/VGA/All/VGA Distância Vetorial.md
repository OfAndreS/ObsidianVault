
---

```ad-example
#### **Distância de Ponto a Plano**
```

---

```ad-quote
title: **Definição**

A **distância de um ponto a um plano** é o menor caminho entre eles, medido pelo segmento de reta perpendicular que os une.
```

---
#### **01 ) - Distância como Projeção Escalar**

```ad-quote
title: **Definição**

A **Distância Orientada** $d(P, \alpha)$ de um ponto $P$ a um plano $\alpha$ é a projeção escalar do vetor $\vec{AP}$ sobre o **vetor normal** $\hat{n}$ do plano, onde $A$ é um ponto qualquer do plano. Geometricamente, é o comprimento com sinal do segmento $\vec{NP}$, onde $N$ é a projeção ortogonal de $P$ sobre $\alpha$.
```

```ad-quote
title: **Fórmulas**

A fórmula para a **distância orientada** é:

1. $$d(P, \alpha) = (P - A) \cdot \hat{n}$$

A **distância não orientada** (sempre positiva) é:

2. $$d(P, \alpha) = |(P - A) \cdot \hat{n}|$$

---

**Componentes:**
- $P$: O ponto fora do plano.
- $A$: Um ponto qualquer pertencente ao plano $\alpha$.
- $\hat{n}$: O vetor normal **unitário** ao plano.
```

```ad-quote
title: **Observação sobre a Distância Orientada**

O sinal da distância $d(P, \alpha)$ indica de que lado do plano o ponto $P$ se encontra, em relação à orientação de $\hat{n}$:

**Sinal Positivo (+):**
- O segmento $\vec{NP}$ tem o **mesmo sentido** de $\hat{n}$.

**Sinal Negativo (-):**
- O segmento $\vec{NP}$ tem **sentido contrário** ao de $\hat{n}$.
```

---
#### **2 ) - Distância via Volume do Paralelepípedo**

```ad-quote
title: **Definição**

Esta abordagem usa o conceito de volume para calcular a distância. Se $A, B, C$ são três pontos no plano $\alpha$, e $P$ é o ponto fora do plano, a distância $d(P, \alpha)$ é a altura do paralelepípedo formado pelos vetores $(B-A)$, $(C-A)$ e $(P-A)$.
```

```ad-quote
title: **Fórmulas**

A fórmula para a distância é:

1. $$d(P, \alpha) = \frac{|(B-A) \times (C-A) \cdot (P-A)|}{|(B-A) \times (C-A)|}$$

Uma forma mais comum e direta, que não exige o vetor normal:

2. $$d(P, \alpha) = \frac{|(P - A) \cdot \vec{n}|}{|\vec{n}|}$$

---

**Componentes:**

$P$: 
- O ponto fora do plano.

$A$: 
- Um ponto qualquer pertencente ao plano $\alpha$.

$\vec{n}$: 
- Um vetor normal qualquer (não necessariamente unitário) ao plano.

$B, C$: 
- Outros dois pontos quaisquer pertencentes ao plano (usados na primeira fórmula).

```

---
#### **03 ) - Relação com o Pé da Normal (N)**

```ad-quote
title: **Definição**

O **pé da normal ($N$)** é a projeção ortogonal do ponto $P$ sobre o plano $\alpha$. É o ponto do plano que está mais próximo de $P$.
```
##### *A ) Fórmula da projeção ortogonal (geral):*

```ad-quote
title: **Fórmulas para o Pé da Normal**
Fórmula: 
1. $$N = P - \left( \frac{(P - A) \cdot \vec{n}}{\vec{n} \cdot \vec{n}} \right) \vec{n}$$

---

**Componentes:**

$N$ (O Resultado): 
  - É o pé da normal, a projeção de $P$ no plano.

$P$ (O Ponto de Fora): 
  - É o ponto que você está projetando.

$A$: Um ponto qualquer 
  - que você já conhece no plano.

$\vec{n}$ (A Direção): 
  - É o vetor normal ao plano.

```
##### *B ) Fórmula usando a distância orientada e o vetor normal unitário:*

```ad-quote
title: **Def**

Se $d(P, \alpha)$ é a **distância orientada** e $\hat{n}$ é o **vetor normal unitário** ao plano:

2. $$N = P - d(P, \alpha) \cdot \hat{n}$$
```

---

```ad-example
#### **Distância de Ponto a Reta**
```

---

```ad-quote
title: **Definição**

A **distância de um ponto a uma reta** é o menor caminho entre eles, medido pelo segmento de reta perpendicular que os une.
```

---
#### **01 ) - Distância via Produto Vetorial**

```ad-quote
title: **Definição**

A **Distância** $d(A, r)$ de um ponto $A$ a uma reta $r$ é a **altura do paralelogramo** formado pelo vetor $\vec{PA}$ e pelo vetor diretor da reta $\vec{v}$, onde $P$ é um ponto qualquer da reta.
```

```ad-quote
title: **Fórmula**

A fórmula para a distância, deduzida a partir da definição de produto vetorial, é:

1. $$d(A, r) = \frac{|(A - P) \times \vec{v}|}{|\vec{v}|}$$

---

**Componentes:**
- $A$ (O Ponto de Fora): É o ponto que você está projetando.
- $P$ (O Ponto de Partida): É um ponto qualquer que você já conhece na reta $r$.
- $\vec{v}$ (A Direção): É o vetor que mostra a direção da reta $r$.
```

---
#### **02 ) - Distância via Área do Triângulo**

```ad-quote
title: **Definição**

Esta fórmula utiliza o **produto vetorial** e relaciona a distância com a área de um triângulo.
```

```ad-quote
title: **Fórmula**

1. $$d(A, r) = \frac{|(A - P_1) \times (P_2 - P_1)|}{|P_2 - P_1|}$$

---

**Componentes:**
- $A$: O ponto fora da reta.
- $P_1$: Um ponto qualquer pertencente à reta $r$.
- $P_2$: Outro ponto qualquer pertencente à reta $r$.
    - (Note que $(P_2 - P_1)$ forma o vetor diretor da reta.)
```

---
#### **03 ) - Relação com o Pé da Normal (N)**

```ad-quote
title: **Definição**

O **pé da normal ($N$):** 
- É a projeção ortogonal do ponto $A$ sobre a reta $r$. É o ponto da reta que está mais próximo de $A$.
```

```ad-quote
title: **Fórmula para o Pé da Normal**

**Fórmula da projeção vetorial:**

1. $$N = P_1 + \left(\frac{(A - P_1) \cdot \vec{v}}{\vec{v} \cdot \vec{v}}\right) \vec{v}$$

---

**Componentes:**

$N$ (O Resultado): 
- É o ponto que você quer encontrar: a projeção de $A$ na reta.

$A$ (O Ponto de Fora): 
- É o ponto que você está projetando.

$P_1$ (O Ponto de Partida): 
- É um ponto qualquer que você já conhece na reta.

$\vec{v}$ (A Direção): 
- É o vetor que mostra a direção da reta.

```

---

```ad-example
#### **Distância entre Duas Retas**
```

---

```ad-quote
title: **Definição**

A distância entre duas retas é o comprimento do menor segmento de reta que as une, sendo este segmento perpendicular a ambas as retas.
```

---
#### **01 ) - Retas Intersecionantes**

```ad-quote
title: **Definição**

Duas retas são intersecionantes se possuem um único ponto em comum.
```

```ad-quote
title: **Distância**

A distância entre retas intersecionantes é **zero**.
$$d(r_1, r_2) = 0$$
```

---
#### **02 ) - Retas Paralelas**

```ad-quote
title: **Definição**

Duas retas são paralelas se seus vetores diretores são paralelos e elas não possuem pontos em comum.
```

```ad-quote
title: **Distância**

A distância entre retas paralelas é a distância de um ponto qualquer de uma das retas à outra reta.

Sejam as retas $r_1$ e $r_2$:
- $r_1$: passa por $P_1$ com vetor diretor $\vec{v}$.
- $r_2$: passa por $P_2$ com vetor diretor $\vec{v}$ (ou um múltiplo paralelo).

$$d(r_1, r_2) = \frac{|(P_1 - P_2) \times \vec{v}|}{|\vec{v}|}$$

---

**Componentes:**
- $P_1$: Um ponto qualquer em $r_1$.
- $P_2$: Um ponto qualquer em $r_2$.
- $\vec{v}$: O vetor diretor comum (ou paralelo) das retas.
```

---
#### **03 ) - Retas Reversas (Esquivas)**

```ad-quote
title: **Definição**

Duas retas são reversas se não são paralelas e não se intersecionam. Elas não estão no mesmo plano.
```
##### *A ) Distância via Produto Misto / Fórmula Direta*

```ad-quote
title: **Def**

A distância é a altura do paralelepípedo formado pelos vetores diretores das retas e um vetor que conecta pontos das retas.

Sejam as retas:
- $r_1$: passa por $P_1$ e tem vetor diretor $\vec{v}_1$.
- $r_2$: passa por $P_2$ e tem vetor diretor $\vec{v}_2$.

1. $$\mathrm{d}(\mathrm{r}_1,\mathrm{~r}_2)=\frac{|(\mathrm{P}_2-\mathrm{P}_1)\cdot(\vec{\mathrm{v}}_1\times\vec{\mathrm{v}}_2)|}{|\vec{\mathrm{v}}_1\times\vec{\mathrm{v}}_2|}$$

---

**Componentes:**

$P_1$: 
- Um ponto qualquer em $r_1$.

$P_2$: 
- Um ponto qualquer em $r_2$.

$\vec{v}_1$: 
- O vetor diretor da reta $r_1$.

$\vec{v}_2$: 
- O vetor diretor da reta $r_2$.

$|\vec{v}_1 \times \vec{v}_2|$: 
- O módulo do vetor normal, representando a área da base do paralelepípedo.

$|(P_2 - P_1) \cdot (\vec{v}_1 \times \vec{v}_2)|$: 

- O módulo do produto misto, representando o volume do paralelepípedo.
```
##### *B ) Distância via Planos Paralelos / Perspectiva Conceitual*

```ad-quote
title: **Def**

Para retas reversas, podemos imaginar dois planos paralelos, cada um contendo uma das retas. A distância entre as retas é a distância entre esses planos. O vetor normal a esses planos é $\vec{n} = \vec{v}_1 \times \vec{v}_2$. A distância é então calculada como a distância de um ponto de um plano ao outro plano, o que naturalmente leva à mesma fórmula do Produto Misto.
```

---

```ad-quote
title: **Def**

**Fórmula**
$$\left\{\begin{array}{l}
k_{1} \vec{r}_{1} \cdot \vec{r}_{1} - k_{2} \vec{r}_{1} \cdot \vec{r}_{2} = \left(P_{2} - P_{1}\right) \cdot \vec{r}_{1} \\
k_{1} \vec{r}_{1} \cdot \vec{r}_{2} - k_{2} \vec{r}_{2} \cdot \vec{r}_{2} = \left(P_{2} - P_{1}\right) \cdot \vec{r}_{2}
\end{array}\right.$$
**Logo:**

2. $$N_{1} = P_{1} + k_{1} \vec{r}_{1}$$

3. $$N_{2} = P_{2} + k_{2} \vec{r}_{2}$$
```
