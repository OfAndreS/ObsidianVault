
---

>[!example] **01 ) - Retas Coplanares e Paralelas**

```ad-quote
title:

##### _Definição_

```ad-quote
title: 

Duas retas, $r$ e $s$, são **Coplanares e Paralelas** ($r \parallel s$) quando pertencem ao mesmo plano. Elas podem ser:

**Paralelas Distintas:** 
- Não possuem nenhum ponto em comum.

**Paralelas Coincidentes:** 
- Possuem todos os pontos em comum (são a mesma reta).
```

![[Pasted image 20250719192352.png]]

>[!example] **02 ) - Retas Coplanares e Concorrentes**

```ad-quote
title:
##### _Definição_

```ad-quote
title: **Def**

Duas retas, $r$ e $s$, são **Coplanares e Concorrentes** quando pertencem ao mesmo plano e se interceptam em um único ponto, chamado de ponto de interseção.
```

![[Pasted image 20250719205433.png]]

>[!example] **03 ) -** Retas Reversas

```ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

Duas retas, $r$ e $s$, são **Reversas** quando não existe nenhum plano que contenha ambas simultaneamente. Elas não são paralelas e não se interceptam.
```

![[Pasted image 20250719192458.png]]

---

```ad-example

#### **01 ) - Condição de Paralelismo da Reta**
```

---

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

Duas retas $r_1$ e $r_2$ são paralelas se seus vetores diretores $\vec{v_1}=(l_1, m_1, n_1)$ e $\vec{v_2}=(l_2, m_2, n_2)$ forem paralelos. Isso ocorre quando as componentes dos vetores são proporcionais:

1. $$\frac{l_1}{l_2} = \frac{m_1}{m_2} = \frac{n_1}{n_2}$$

```

![[Pasted image 20250719193848.png]]

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Verificar se as retas $r_1: \frac{x-1}{2} = \frac{y}{4} = \frac{z+1}{6}$ e $r_2: \frac{x}{1} = \frac{y-2}{2} = \frac{z}{3}$ são paralelas.

---

**Resolução:**
- Vetor diretor de $r_1$: $\vec{v_1} = (2, 4, 6)$
- Vetor diretor de $r_2$: $\vec{v_2} = (1, 2, 3)$

- Verificando a proporcionalidade das componentes:
1. $$\frac{2}{1} = 2$$
2. $$\frac{4}{2} = 2$$
3. $$\frac{6}{3} = 2$$

**Resposta:**
- Como as razões entre as componentes correspondentes são iguais, os vetores diretores são paralelos e, portanto, as retas $r_1$ e $r_2$ são paralelas.
```

---

```ad-example

#### **02 ) - Condição de Ortogonalidade da Reta**
```

---

```ad-quote
title:

##### _Definição_

```ad-quote
title: **Def**

É importante diferenciar os conceitos de retas ortogonais e perpendiculares:

**Ortogonais:** 
- Duas retas são ortogonais se seus vetores diretores formam um ângulo de $90^\circ$. Elas podem ou não se cruzar no espaço.

**Perpendiculares:** 
- Duas retas são perpendiculares se, além de serem ortogonais, elas também forem concorrentes (se cruzam em um ponto).

```

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

A condição de ortogonalidade entre as retas $r_1$ e $r_2$ coincide com a dos vetores diretores $\vec{v_1}=(l_1, m_1, n_1)$ e $\vec{v_2}=(l_2, m_2, n_2)$. O produto escalar entre eles deve ser nulo:

1. $$\vec{v_1} \cdot \vec{v_2} = 0$$
2. $$l_1l_2 + m_1m_2 + n_1n_2 = 0$$
```

![[Pasted image 20250719193944.png]]

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Verificar se as retas $r_1$, que passa por $A(1,0,2)$ com vetor diretor $\vec{v_1}=(2, 3, -1)$, e $r_2$, com vetor diretor $\vec{v_2}=(4, -2, 2)$, são ortogonais.

---

**Resolução:**
- Vetor diretor de $r_1$: $\vec{v_1} = (2, 3, -1)$
- Vetor diretor de $r_2$: $\vec{v_2} = (4, -2, 2)$

- Calculando o produto escalar:
1. $$\vec{v_1} \cdot \vec{v_2} = (2)(4) + (3)(-2) + (-1)(2)$$
2. $$\vec{v_1} \cdot \vec{v_2} = 8 - 6 - 2 = 0$$

**Resposta:**
- Como o produto escalar é zero, as retas $r_1$ e $r_2$ são **ortogonais**. Para saber se são também perpendiculares, seria necessário verificar se elas se interceptam.
```

---

```ad-example

#### **03 ) - Condição de Coplanaridade de Duas Retas**
```

---

```ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

Duas retas, $r_1$ e $r_2$, são Coplanares quando existe um plano que contém ambas simultaneamente.

Isso acontece se, e somente se, o vetor que liga um ponto de uma reta a outra ($\vec{P_1P_2}$) e os vetores diretores de cada reta ($\vec{v_1}$ e $\vec{v_2}$) forem coplanares (pertencerem ao mesmo plano).
```

![[Pasted image 20250719203811.png]]

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

A condição de coplanaridade é verificada quando o produto misto entre os vetores $\vec{P_1P_2}$, $\vec{v_1}$ e $\vec{v_2}$ é nulo. Isso é calculado através do seguinte determinante:

$$
\begin{vmatrix}
x_2 - x_1 & y_2 - y_1 & z_2 - z_1 \\
l_1 & m_1 & n_1 \\
l_2 & m_2 & n_2
\end{vmatrix}
= 0
$$
Onde:
- $P_1(x_1, y_1, z_1)$ é um ponto de $r_1$.
- $P_2(x_2, y_2, z_2)$ é um ponto de $r_2$.
- $\vec{v_1}=(l_1, m_1, n_1)$ é o vetor diretor de $r_1$.
- $\vec{v_2}=(l_2, m_2, n_2)$ é o vetor diretor de $r_2$.
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Verificar se as retas $r_1: \frac{x-1}{1} = \frac{y-2}{0} = \frac{z-1}{2}$ e $r_2: \frac{x-2}{2} = \frac{y-2}{0} = \frac{z}{1}$ são coplanares.

---

**Resolução:**

**Dados da reta $r_1$**:
- Ponto $P_1 = (1, 2, 1)$
- Vetor diretor $\vec{v_1} = (1, 0, 2)$


**Dados da reta $r_2$**:
- Ponto $P_2 = (2, 2, 0)$
- Vetor diretor $\vec{v_2} = (2, 0, 1)$


**Vetor $\vec{P_1P_2}$**:
- $\vec{P_1P_2} = P_2 - P_1 = (2-1, 2-2, 0-1) = (1, 0, -1)$


**Cálculo do determinante**:
1. $$
\begin{vmatrix}
1 & 0 & -1 \\
1 & 0 & 2 \\
2 & 0 & 1
\end{vmatrix} =$$
2. $$(1 \cdot 0 \cdot 1) + (0 \cdot 2 \cdot 2) + (-1 \cdot 1 \cdot 0) - ((-1) \cdot 0 \cdot 2) - (1 \cdot 2 \cdot 0) - (0 \cdot 1 \cdot 1) = 0
$$

**Resposta:**
- Como o resultado do determinante (produto misto) é zero, os vetores são coplanares e, portanto, as retas $r_1$ e $r_2$ **são coplanares**.
```

---