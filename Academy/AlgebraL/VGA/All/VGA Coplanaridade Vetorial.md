
---

```ad-quote
title: **Def**

A **coplanaridade de vetores** é um conceito fundamental na geometria analítica e na álgebra linear, que descreve a condição em que três ou mais vetores estão contidos no mesmo plano. Isso significa que esses vetores são **linearmente dependentes (LD)** em relação a um plano, ou seja, um deles pode ser expresso como uma combinação linear dos outros dois.

```

---
#### **1 )** - *Definição Matemática*

```ad-quote
Três vetores $\vec{v}_1 = (x_1, y_1, z_1)$, $\vec{v}_2 = (x_2, y_2, z_2)$ e $\vec{v}_3 = (x_3, y_3, z_3)$ são coplanares se um deles for combinação linear dos outros dois. Ipso facto, o seu determinante deve ser nulo:
$$\begin{vmatrix}
x_1 & y_1 & z_1 \\
x_2 & y_2 & z_2 \\
x_3 & y_3 & z_3
\end{vmatrix}
= 0$$
Exemplo:
Os vetores $\vec{u} = (2, 3, 5)$, $\vec{v} = (3, 0, -1)$ e $\vec{w} = (7, 6, 9)$ são coplanares.
```

---
#### **2 )** - *Verificação da Coplanaridade*

```ad-quote
title: **Def**

Existem três métodos principais para verificar se três vetores são coplanares:
```

#### **2.1 )** *Método do Determinante*

```ad-quote
title: **Def**

O método mais direto é calcular o **determinante da matriz** formada pelas componentes dos vetores. Se o determinante for zero, os vetores são coplanares.

Dados $(mathbf{u} = (u_x, u_y, u_z)), (mathbf{v} = (v_x, v_y, v_z)), (mathbf{w} = (w_x, w_y, w_z))$, construímos a matriz:


1. $$M = \begin{bmatrix}
u_x & u_y & u_z \\
v_x & v_y & v_z \\
w_x & w_y & w_z \\
\end{bmatrix}$$


A condição de coplanaridade é:


2. $\det(M) = 0$

```
#### **Interpretação Geométrica**

```ad-quote
title: **Def**

O determinante representa o **volume do paralelepípedo** formado pelos três vetores. Se o volume for zero, significa que os vetores estão "achatados" no mesmo plano.
```

---
#### **2.2. Método do Produto Misto**

```ad-quote
title: **Def**

O **produto misto** de três vetores é dado por:

$$
(\mathbf{u} \times \mathbf{v}) \cdot \mathbf{w}
$$

Se o produto misto for zero, os vetores são coplanares.
```
##### *Por quê?*

```ad-quote
title: **Def**

- $\mathbf{u} \times \mathbf{v}$ resulta em um vetor perpendicular ao plano formado por $\mathbf{u}$ e $\mathbf{v}$.
- Se $\mathbf{w}$ pertence ao mesmo plano, então ele é perpendicular a $\mathbf{u} \times \mathbf{v}$, logo, o produto escalar é zero.
```

---

### **2.3. Método da Combinação Linear**
Se um dos vetores puder ser escrito como combinação linear dos outros dois, então eles são coplanares. Por exemplo:

$$
\mathbf{w} = \alpha \mathbf{u} + \beta \mathbf{v}
$$

Isso significa que `$ \mathbf{w} $` está no mesmo plano que `$ \mathbf{u} $` e `$ \mathbf{v} $`.

---

## **3. Exemplo Prático**
**Verifique se os vetores `$ \mathbf{u} = (1, 0, 1) $`, `$ \mathbf{v} = (2, 1, 0) $` e `$ \mathbf{w} = (0, 1, 2) $` são coplanares.**

### **Solução pelo Determinante**
Construímos a matriz:

$$
M = \begin{bmatrix}
1 & 0 & 1 \\
2 & 1 & 0 \\
0 & 1 & 2
\end{bmatrix}
$$

Calculamos o determinante:

$$
\det(M) = 1 \cdot (1 \cdot 2 - 0 \cdot 1) - 0 \cdot (2 \cdot 2 - 0 \cdot 0) + 1 \cdot (2 \cdot 1 - 1 \cdot 0) = 2 + 0 + 2 = 4
$$

Como `$ \det(M) = 4 \neq 0 $`, os vetores **não são coplanares**.

---

## **4. Casos Especiais**
- **Se dois vetores são paralelos**, qualquer terceiro vetor será coplanar com eles, pois já estão em um plano degenerado.
- **Se os três vetores são LD (Linearmente Dependentes)**, então são coplanares.
- **Se um vetor é nulo**, automaticamente os outros dois são coplanares com ele.

---

## **5. Aplicações**
A coplanaridade é útil em:
- **Geometria computacional** (verificação de planos em gráficos 3D).
- **Física** (análise de forças no mesmo plano).
- **Engenharia** (cálculo de estruturas planas).

---

## **Conclusão**
A coplanaridade de vetores é verificada quando:
1. O **determinante da matriz** dos vetores é zero.
2. O **produto misto** é zero.
3. Um vetor é **combinação linear** dos outros dois.

Essa análise é essencial para problemas de geometria espacial e álgebra linear.