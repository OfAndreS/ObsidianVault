
---

```ad-example

#### **Adição / Subtração Vetorial**
```

---

```ad-quote
title: **Def**

A **soma** de dois vetores: 
- $\vec{u} + \vec{v}$, resulta em um vetor **deslocamento resultante**. ➕
  
Geometricamente, usa-se a **Regra do Paralelogramo** ou a **Regra do Polígono**.
Na Regra do Polígono, a **origem** do segundo vetor coincide com a **extremidade** do primeiro.

---

A **subtração de vetores:** 
- $\vec{u} - \vec{v}$ é definida como a soma de $\vec{u}$: com o **oposto** de $\vec{v}$: $\vec{u} + (-\vec{v})$. ➖

O vetor $-\vec{v}$ tem o mesmo módulo e direção de $\vec{v}$, mas **sentido oposto**.
Geometricamente, representa o vetor que vai da **extremidade** de $\vec{v}$ à extremidade de $\vec{u}$.
Algebricamente, subtraem-se as **componentes correspondentes**: $(u_x-v_x, u_y-v_y, u_z-v_z)$.
É útil para encontrar o vetor que **liga** dois pontos.
```

---

>[!tip] #### **Adição de Vetores )** - _Definição_

---

```ad-quote
title: **Def**

Dados dois vetores $\mathbf{A}$ e $\mathbf{B}$ em $\mathbb{R}^n$, a soma $\mathbf{A} + \mathbf{B}$ é calculada componente a componente:  
$$
\mathbf{A} + \mathbf{B} = (A_1 + B_1, A_2 + B_2, \dots, A_n + B_n)
$$

```

>[!error] **Ex )** - *Exemplo em $\mathbb{R}^2$:*

```ad-quote
title: **Def**

**Dado:**
$$
\mathbf{A} = (3, 2), \quad \mathbf{B} = (1, -4)
$$

**Logo:**

$$ 
\mathbf{A} + \mathbf{B} = (3 + 1, 2 + (-4)) = (4, -2)
$$

```

>[!error] **Ex )** - *Exemplo em $\mathbb{R}^4$:*

```ad-quote
title: **Def**

**Dado:**
1. $$\mathbf{A} = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}, \ \mathbf{B} = \begin{bmatrix} 4 \\ 3 \\ 2 \\ 1 \end{bmatrix}$$

**Logo:**

2. $$ 
\mathbf{A} + \mathbf{B} = \begin{bmatrix} 4 + 1 \\ 3 + 2 \\ 2 + 3 \\ 1 + 4 \end{bmatrix} = \begin{bmatrix} 5 \\ 5 \\ 5 \\ 5 \end{bmatrix}
$$

```

---
#### **Visualização Geométrica )** - *Geométrica* 

![[Pasted image 20250530190854.png]]

---
#### **Propriedades )** - *Adição Vetorial*  

```ad-quote
title: **Def**

**Comutatividade:** 
- $\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}$

**Associatividade:** 
- $(\mathbf{A} + \mathbf{B}) + \mathbf{C} = \mathbf{A} + (\mathbf{B} + \mathbf{C})$

**Elemento neutro:** 
- $\mathbf{A} + \mathbf{0} = \mathbf{A}$

**Inverso aditivo:** 
- $\mathbf{A} + (-\mathbf{A}) = \mathbf{0}$  
```

---
#### **Representação Geométrica )** - *Após Adição*  

```ad-quote
title: **Def**

**a) Método do Paralelogramo**  
- Vetores partem da mesma origem.  
- Resultante é a diagonal do paralelogramo.  

**b) Método Ponta-a-Cauda** 
- A origem de $\mathbf{B}$ na ponta de $\mathbf{A}$.  
- Resultante liga a origem de $\mathbf{A}$ à ponta de $\mathbf{B}$.  
```

---

>[!tip] #### **Subtração de Vetores )** - _Definição_

---

```ad-quote
title: **Def**

A **subtração de vetores** é definida como a adição de um vetor pelo **vetor oposto** (ou inverso aditivo).

Dados dois vetores $\mathbf{A}$ e $\mathbf{B}$ em $\mathbb{R}^n$, a subtração $\mathbf{A} - \mathbf{B}$ é calculada como:

1. $$\mathbf{A} - \mathbf{B} = \mathbf{A} + (-\mathbf{B})$$

Onde $-\mathbf{B}$ é o vetor oposto a $\mathbf{B}$, obtido multiplicando cada componente de $\mathbf{B}$ por $-1$:

3. $$-\mathbf{B} = (-B_1, -B_2, \dots, -B_n)$$

Portanto, a subtração componente a componente é:

5. $$\mathbf{A} - \mathbf{B} = (A_1 - B_1, A_2 - B_2, \dots, A_n - B_n)$$

```

>[!error] **Ex )** - *Exemplo em $\mathbb{R}^2$:*

```ad-quote
title: **Def**

**Dado:**
$$\mathbf{A} = (3, 2), \quad \mathbf{B} = (1, -4)$$

**Logo:**

Primeiro, encontramos o vetor oposto de $\mathbf{B}$:
$$-\mathbf{B} = (-1, -(-4)) = (-1, 4)$$
Então, realizamos a soma:
$$ \mathbf{A} - \mathbf{B} = \mathbf{A} + (-\mathbf{B}) = (3 + (-1), 2 + 4) = (2, 6)$$
Ou diretamente pela subtração de componentes:
$$\mathbf{A} - \mathbf{B} = (3 - 1, 2 - (-4)) = (2, 2 + 4) = (2, 6)$$

```

>[!error] **Ex )** - *Exemplo em $\mathbb{R}^4$:*

```ad-quote
title: **Def**

**Dado:**
1. $$\mathbf{A} = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}, \ \mathbf{B} = \begin{bmatrix} 4 \\ 3 \\ 2 \\ 1 \end{bmatrix}$$

**Logo:**

Primeiro, encontramos o vetor oposto de $\mathbf{B}$:

2. $$-\mathbf{B} = \begin{bmatrix} -4 \\ -3 \\ -2 \\ -1 \end{bmatrix}$$
Então, realizamos a soma:
 
3. $$\mathbf{A} - \mathbf{B} = \mathbf{A} + (-\mathbf{B}) = \begin{bmatrix} 1 + (-4) \\ 2 + (-3) \\ 3 + (-2) \\ 4 + (-1) \end{bmatrix} = \begin{bmatrix} -3 \\ -1 \\ 1 \\ 3 \end{bmatrix}$$
Ou diretamente pela subtração de componentes:
 
4. $$\mathbf{A} - \mathbf{B} = \begin{bmatrix} 1 - 4 \\ 2 - 3 \\ 3 - 2 \\ 4 - 1 \end{bmatrix} = \begin{bmatrix} -3 \\ -1 \\ 1 \\ 3 \end{bmatrix}$$

```

---
#### **Visualização )** - *Geométrica*

![[Pasted image 20250530193603.png]]

---
#### **Propriedades )** - *Subtração Vetorial*  

```ad-quote
title: **Def**

A subtração vetorial não possui as mesmas propriedades que a adição. Em geral:

**Não Comutativa:** 
- $\mathbf{A} - \mathbf{B} \neq \mathbf{B} - \mathbf{A}$ (exceto em casos especiais onde $\mathbf{A} = \mathbf{B}$ ou $\mathbf{A} = \mathbf{B} + \mathbf{0}$)
- Na verdade, $\mathbf{A} - \mathbf{B} = -(\mathbf{B} - \mathbf{A})$

**Não Associativa:** 
- $(\mathbf{A} - \mathbf{B}) - \mathbf{C} \neq \mathbf{A} - (\mathbf{B} - \mathbf{C})$

**Elemento Neutro (Inverso):** 
- A subtração não tem um elemento neutro como a adição. O vetor nulo $(\mathbf{0})$ se comporta como um inverso aditivo quando subtraído:
    - $\mathbf{A} - \mathbf{0} = \mathbf{A}$
    - $\mathbf{0} - \mathbf{A} = -\mathbf{A}$

**Relação com a Adição:**
- A subtração é fundamentalmente uma forma de adição com o vetor oposto, herdando indiretamente algumas propriedades da adição por meio dessa relação. Por exemplo, a distribuição de um escalar sobre a subtração:
    - $k(\mathbf{A} - \mathbf{B}) = k\mathbf{A} - k\mathbf{B}$
```

---

>[!example] #### **Multiplicação de um Vetor por um escalar**

---
#### **Definição )** - *Matemática*

```ad-quote
title: **Def**

Dado um vetor **v** e um escalar **k** ∈ ℝ, a multiplicação é definida por:

**Em notação matricial:**

$k \cdot \mathbf{v} = k \cdot \begin{bmatrix} v_x \\ v_y \end{bmatrix} = \begin{bmatrix} k \cdot v_x \\ k \cdot v_y \end{bmatrix}$


**Em notação cartesiana (ℝ²):**

$k \cdot \vec{v} = k \cdot (v_x, v_y) = (k \cdot v_x, k \cdot v_y)$

```

---
#### **Representação Geométrica )** - *Após a Multiplicação*  

```ad-quote
title: **Def**
**01 ) Dilatação:** $k > 1$
- Vetor "Esticado"
1. $$2·(3,1) = (6,2)$$

---

**02 ) Contração:** $0 < k < 1$
- Vetor "Encolhido"
1. $$0.5·(4,2) = (2,1)$$

---

**03 ) Identidade:** $k = 1$
- Vetor inalterado
1. $$1·(5,3) = (5,3)$$

---

**04 ) Contração com inversão:** $-1 < k < 0$
1. $$-0.5·(6,4) = (-3,-2)$$

---

**05 ) Inversão pura:** $k = -1$ 
- Vetor Espelhado
1. $$-1·(2,5) = (-2,-5)$$

---

** 06 ) Dilatação com inversão:** $k < -1$
1. $$-2·(1,3) = (-2,-6)$$ 
```

---
#### **Propriedades )** - *Fundamentais*

```ad-quote
title: **Def**

**Linearidade**:

1. $$k \cdot (\mathbf{u} + \mathbf{v}) = k\mathbf{u} + k\mathbf{v}$$

---

**Associatividade Escalar**:

2. $$(k_1 k_2)\mathbf{v} = k_1(k_2 \mathbf{v})$$

---

**Distributividade**:

3. $$(k_1 + k_2)\mathbf{v} = k_1\mathbf{v} + k_2\mathbf{v}$$

```

---
#### **Aplicações Imediatas**

```ad-quote
title: **Def**


 **Normalização de Vetores**:

   $$\hat{v} = \frac{1}{|\mathbf{v}|} \mathbf{v}$$

---

**Razão de Segmentos**:

- Dados pontos A e B, o ponto P que divide AB na razão r:s:

  $$\vec{OP} = \frac{s}{r+s}\vec{OA} + \frac{r}{r+s}\vec{OB}$$
```

---

