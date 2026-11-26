
---

```ad-example
title: **Def**

#### **Multiplicação de um Vetor por um Escalar**
```

---

#### **01 )** - *Definição*

```ad-quote
title: **Def**

Multiplicar um vetor $\vec{v}$ por um escalar $k$ resulta em um novo vetor $k\vec{v}$. Esta operação altera o módulo (comprimento) e, possivelmente, o sentido do vetor original, mas não a sua direção fundamental (a linha sobre a qual o vetor se assenta).
```

---
#### **02 )** - *Cálculo / Componentes*

```ad-quote
title: **Def**

Se $\vec{v} = (v_x, v_y, v_z)$ em um espaço tridimensional (ou $\vec{v} = (v_1, v_2, ..., v_n)$ em $n$ dimensões) e $k$ é um escalar, então:

1. $$k\cdot\vec{v} = (kv_x, kv_y, kv_z)$$

De forma geral para $n$ dimensões:

2. $$k\cdot\vec{v} = (kv_1, kv_2, ..., kv_n)$$
```

---
#### **03 )** - *Resultado*

```ad-quote
title: **Def**

O resultado da multiplicação de um vetor por um escalar é sempre um:
- **Vetor**
```

---
#### **04 )** - *Interpretação Geométrica*

```ad-quote
title: **Def**

**Módulo (Comprimento):**
 - O módulo do novo vetor é $|k|$ vezes o módulo do vetor original.
 - $$|k\cdot\vec{v}| = |k|\cdot|\vec{v}|$$

**Direção:**
 - A direção do vetor $k\cdot\vec{v}$ é a mesma de $\vec{v}$ (são paralelos).

**Sentido:**
 - Se $k > 0$: $k\cdot\vec{v}$ tem o mesmo sentido de $\vec{v}$.
 - Se $k < 0$: $k\cdot\vec{v}$ tem o sentido oposto ao de $\vec{v}$.
 - Se $k = 0$: $k\cdot\vec{v} = \vec{0}$ (o vetor nulo).
```

---
#### **05 )** - *Propriedades*

```ad-quote
title: **Def**

Sejam $k$ e $m$ escalares, e $\vec{u}$ e $\vec{v}$ vetores:

1. **Associatividade com multiplicação de escalares:**
   $$(km)\vec{v} = k(m\vec{v})$$
2. **Distributividade em relação à adição de vetores:**
   $$k(\vec{u} + \vec{v}) = k\vec{u} + k\vec{v}$$
3. **Distributividade em relação à adição de escalares:**
   $$(k + m)\vec{v} = k\vec{v} + m\vec{v}$$
4. **Elemento neutro da multiplicação por escalar:**
   $$1\vec{v} = \vec{v}$$
5. **Multiplicação por zero escalar:**
   $$0\vec{v} = \vec{0}$$
6. **Multiplicação pelo escalar -1:**
   $$(-1)\vec{v} = -\vec{v}$$ (vetor oposto)
```

---

>[!error] **06 )** - *Exemplo*

---

```ad-quote
title: **Def**

Se $\vec{v} = (1, -2, 3)$ e $k = -2$, então:
$$-2\vec{v} = (-2 \cdot 1, -2 \cdot (-2), -2 \cdot 3) = (-2, 4, -6)$$
O novo vetor $(-2, 4, -6)$ tem o dobro do comprimento de $(1, -2, 3)$, a mesma direção (paralelo), mas sentido oposto.
```

---

```ad-example
title: **Def**

#### **Produto Escalar (ou Produto Interno / Dot Product)**
```

---
#### **01 )** - *Definição*

```ad-quote
title: **Def**

O produto escalar de dois vetores $\vec{a}$ e $\vec{b}$ é uma operação que resulta em uma grandeza escalar. Ele mede a projeção de um vetor sobre o outro, multiplicada pelo módulo do outro vetor, ou, de forma intuitiva, o quanto os dois vetores "apontam na mesma direção geral".
É denotado por $\vec{a} \cdot \vec{b}$.
```

---
#### **02 )** - *Cálculo*

```ad-quote
title: **Def**

###### **Forma Geométrica**

1. $$\vec{a} \cdot \vec{b} = |\vec{a}| |\vec{b}| \cos(\theta)$$

- $|\vec{a}|$ e $|\vec{b}|$ são os módulos (comprimentos) dos vetores.
- $\theta$ é o menor ângulo ($0 \le \theta \le \pi$) entre eles.

---

###### **Forma Algébrica (Componentes)**

Se $\vec{a} = (a_x, a_y, a_z)$ e $\vec{b} = (b_x, b_y, b_z)$ em $\mathbb{R}^3$:
1. $$\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z$$

Para $n$ dimensões, $\vec{a} = (a_1, ..., a_n)$ e $\vec{b} = (b_1, ..., b_n)$:
1. $$\vec{a} \cdot \vec{b} = \sum_{i=1}^{n} a_i b_i$$

```

---
#### **03 )** - *Resultado*

```ad-quote
title: **Def**

O resultado do produto escalar é sempre um:
- **Escalar** \ Um número real.
```

---
#### **04 )** - *Interpretação Geométrica e Aplicações*

```ad-quote
title: **Def**

**Relação com o Ângulo $\theta$:**
 - Se $\theta = 0^\circ$ (mesma direção e sentido): $\cos(\theta) = 1 \implies \vec{a} \cdot \vec{b} = |\vec{a}| |\vec{b}|$.
 - Se $\theta = 90^\circ$ (ortogonais): $\cos(\theta) = 0 \implies \vec{a} \cdot \vec{b} = 0$. (Teste de ortogonalidade)
 - Se $\theta = 180^\circ$ (mesma direção, sentidos opostos): $\cos(\theta) = -1 \implies \vec{a} \cdot \vec{b} = -|\vec{a}| |\vec{b}|$.

**Projeção Vetorial:**
 - A projeção escalar de $\vec{a}$ sobre $\vec{b}$ (não nulo) é:
   $$\text{comp}_{\vec{b}}\vec{a} = \frac{\vec{a} \cdot \vec{b}}{|\vec{b}|} = |\vec{a}|\cos(\theta)$$
 - O vetor projeção de $\vec{a}$ sobre $\vec{b}$ é:
   $$\text{proj}_{\vec{b}}\vec{a} = \left(\frac{\vec{a} \cdot \vec{b}}{|\vec{b}|^2}\right)\vec{b}$$

**Trabalho em Física:**
 - O trabalho $W$ realizado por uma força constante $\vec{F}$ ao longo de um deslocamento $\vec{d}$ é:
   $$W = \vec{F} \cdot \vec{d}$$

**Cálculo do Ângulo entre Vetores:**
 - $$\theta = \arccos\left(\frac{\vec{a} \cdot \vec{b}}{|\vec{a}| |\vec{b}|}\right)$$
```

---
#### **05 )** - *Propriedades*

```ad-quote
title: **Def**

Sejam $\vec{a}$, $\vec{b}$, $\vec{c}$ vetores e $k$ um escalar:

1. **Comutatividade:**
   $$\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$$
2. **Distributividade em relação à adição de vetores:**
   $$\vec{a} \cdot (\vec{b} + \vec{c}) = \vec{a} \cdot \vec{b} + \vec{a} \cdot \vec{c}$$
3. **Associatividade com multiplicação por escalar:**
   $$(k\vec{a}) \cdot \vec{b} = k(\vec{a} \cdot \vec{b}) = \vec{a} \cdot (k\vec{b})$$
4. **Positividade definida (para vetores não nulos):**
   $$\vec{a} \cdot \vec{a} = |\vec{a}|^2 \ge 0$$
   E $\vec{a} \cdot \vec{a} = 0$ se e somente se $\vec{a} = \vec{0}$.

```

---

>[!error] **06 )** - *Exemplo*

---

```ad-quote
title: **Def**

Encontre:

$$\theta = \arccos\left(\frac{\vec{a} \cdot \vec{b}}{|\vec{a}| |\vec{b}|}\right)$$

Sejam $\vec{a} = (1, 2, -1)$ e $\vec{b} = (3, 0, 2)$.

O produto escalar é:
1. $$\vec{a} \cdot \vec{b} = (1)(3) + (2)(0) + (-1)(2) = 3 + 0 - 2 = 1$$Os módulos são:
   
2. $$|\vec{a}| = \sqrt{1^2 + 2^2 + (-1)^2} = \sqrt{1+4+1} = \sqrt{6}$$

3. $$|\vec{b}| = \sqrt{3^2 + 0^2 + 2^2} = \sqrt{9+0+4} = \sqrt{13}$$O ângulo $\theta$ entre eles é:

4. $$\theta = \arccos\left(\frac{1}{\sqrt{6}\sqrt{13}}\right) = \arccos\left(\frac{1}{\sqrt{78}}\right)$$
```

---

```ad-example

#### **Produto Vetorial (ou Produto Externo / Cross Product)**
```

---
#### **01 )** - *Definição*

```ad-quote
title: **Def**

O produto vetorial de dois vetores $\vec{a}$ e $\vec{b}$ (definido primariamente em $\mathbb{R}^3$) é um terceiro vetor, denotado por $\vec{a} \times \vec{b}$.
Este vetor resultante é:
- Perpendicular ao plano formado por $\vec{a}$ e $\vec{b}$.
- Seu módulo é igual à área do paralelogramo com lados $\vec{a}$ e $\vec{b}$.
- Seu sentido é dado pela regra da mão direita.
```

---
#### **02 )** - *Cálculo*

```ad-quote
title: **Def**

###### **Módulo**

1. $$|\vec{a} \times \vec{b}| = |\vec{a}| |\vec{b}| \sin(\theta)$$
   - $\theta$ é o menor ângulo ($0 \le \theta \le \pi$) entre $\vec{a}$ e $\vec{b}$.

```

```ad-quote
title: **Def**
###### **Direção e Sentido**

**Direção:** 
- Perpendicular ao plano que contém $\vec{a}$ e $\vec{b}$.
  Isso implica que $(\vec{a} \times \vec{b}) \cdot \vec{a} = 0$ e $(\vec{a} \times \vec{b}) \cdot \vec{b} = 0$.

**Sentido:** 
- Determinado pela **regra da mão direita**. Se os dedos da mão direita curvam de $\vec{a}$ para $\vec{b}$ pelo menor ângulo, o polegar aponta na direção de $\vec{a} \times \vec{b}$.
```

```ad-quote
title: **Def**
###### **Forma Algébrica (Componentes)**

Se $\vec{a} = (a_x, a_y, a_z)$ e $\vec{b} = (b_x, b_y, b_z)$, e $\hat{i}, \hat{j}, \hat{k}$ são os vetores unitários canônicos:
1. $$\vec{a} \times \vec{b} = (a_y b_z - a_z b_y)\hat{i} + (a_z b_x - a_x b_z)\hat{j} + (a_x b_y - a_y b_x)\hat{k}$$
Ou, usando o determinante de uma matriz simbólica:
2. $$\vec{a} \times \vec{b} = \begin{vmatrix} \hat{i} & \hat{j} & \hat{k} \\ a_x & a_y & a_z \\ b_x & b_y & b_z \end{vmatrix}$$
```

---
#### **03 )** - *Resultado*

```ad-quote
title: **Def**

O resultado do produto vetorial é sempre um **vetor** 
- (especificamente, um pseudovetor ou vetor axial).
```

---
#### **04 )** - *Interpretação Geométrica e Aplicações*

```ad-quote
title: **Def**

**Área:**
 - O módulo $|\vec{a} \times \vec{b}|$ é a área do paralelogramo formado por $\vec{a}$ e $\vec{b}$.
 - A área do triângulo com lados adjacentes $\vec{a}$ e $\vec{b}$ é $\frac{1}{2}|\vec{a} \times \vec{b}|$.

**Paralelismo:**
 - Se $\vec{a}$ e $\vec{b}$ são paralelos ($\theta = 0^\circ$ ou $\theta = 180^\circ$), então $\sin(\theta) = 0$, e $\vec{a} \times \vec{b} = \vec{0}$ (vetor nulo). (Teste de paralelismo).

**Aplicações em Física:**
 - **Torque (Momento de uma Força):** $\vec{\tau} = \vec{r} \times \vec{F}$
 - **Momento Angular:** $\vec{L} = \vec{r} \times \vec{p}$ (onde $\vec{p}$ é o momento linear)
 - **Força de Lorentz (componente magnética):** $\vec{F}_m = q(\vec{v} \times \vec{B})$

**Geometria:**
 - Encontrar um vetor normal a um plano.
```

---
#### **05 )** - *Propriedades*

```ad-quote
title: **Def**

Sejam $\vec{a}$, $\vec{b}$, $\vec{c}$ vetores e $k$ um escalar:

1. **Anticomutatividade:**
   $$\vec{a} \times \vec{b} = -(\vec{b} \times \vec{a})$$
2. **Distributividade em relação à adição de vetores:**
   $$\vec{a} \times (\vec{b} + \vec{c}) = (\vec{a} \times \vec{b}) + (\vec{a} \times \vec{c})$$  $$(\vec{a} + \vec{b}) \times \vec{c} = (\vec{a} \times \vec{c}) + (\vec{b} \times \vec{c})$$
3. **Associatividade com multiplicação por escalar:**
   $$(k\vec{a}) \times \vec{b} = k(\vec{a} \times \vec{b}) = \vec{a} \times (k\vec{b})$$
4. **Não é associativo para três vetores:**
   Em geral, $(\vec{a} \times \vec{b}) \times \vec{c} \neq \vec{a} \times (\vec{b} \times \vec{c})$.
5. **Produto vetorial de um vetor com ele mesmo:**
   $$\vec{a} \times \vec{a} = \vec{0}$$
6. **Identidade de Jacobi:**
   $$\vec{a} \times (\vec{b} \times \vec{c}) + \vec{b} \times (\vec{c} \times \vec{a}) + \vec{c} \times (\vec{a} \times \vec{b}) = \vec{0}$$
7. **Identidade de Lagrange (relação com produto escalar):**
   $$|\vec{a} \times \vec{b}|^2 = |\vec{a}|^2 |\vec{b}|^2 - (\vec{a} \cdot \vec{b})^2$$

```

---

>[!error] **06 )** - *Exemplo*

---

```ad-quote
title: **Def**

Sejam $\vec{a} = (2, 1, -1)$ e $\vec{b} = (-3, 4, 1)$.
$$\begin{align*} \vec{a} \times \vec{b} &= \begin{vmatrix} \hat{i} & \hat{j} & \hat{k} \\ 2 & 1 & -1 \\ -3 & 4 & 1 \end{vmatrix} \\ &= \hat{i}(1 \cdot 1 - (-1) \cdot 4) - \hat{j}(2 \cdot 1 - (-1) \cdot (-3)) + \hat{k}(2 \cdot 4 - 1 \cdot (-3)) \\ &= \hat{i}(1 + 4) - \hat{j}(2 - 3) + \hat{k}(8 + 3) \\ &= 5\hat{i} + 1\hat{j} + 11\hat{k} \\ &= (5, 1, 11)\end{align*}$$
O vetor $(5, 1, 11)$ é perpendicular a $\vec{a}$ e $\vec{b}$.
```

---

4. Produto Misto (ou Produto Triplo Escalar)
01 ) - Definição
title: **Def**

O produto misto de três vetores $\vec{a}$, $\vec{b}$, e $\vec{c}$ (em $\mathbb{R}^3$) é uma operação que combina o produto vetorial e o produto escalar.
É denotado por $[\vec{a}, \vec{b}, \vec{c}]$ ou $\vec{a} \cdot (\vec{b} \times \vec{c})$.

02 ) - Cálculo
title: **Def**

1.  Primeiro, calcule o produto vetorial $\vec{d} = \vec{b} \times \vec{c}$.
2.  Então, calcule o produto escalar $\vec{a} \cdot \vec{d}$.

###### **Forma Algébrica (Componentes)**
---
Se $\vec{a}=(a_x,a_y,a_z)$, $\vec{b}=(b_x,b_y,b_z)$, e $\vec{c}=(c_x,c_y,c_z)$, o produto misto é dado pelo determinante da matriz cujas linhas (ou colunas) são os componentes dos vetores:
1. $$\vec{a} \cdot (\vec{b} \times \vec{c}) = \begin{vmatrix} a_x & a_y & a_z \\ b_x & b_y & b_z \\ c_x & c_y & c_z \end{vmatrix}$$

03 ) - Resultado
title: **Def**

O resultado do produto misto é sempre um **escalar**.

04 ) - Interpretação Geométrica e Aplicações
title: **Def**

**Volume do Paralelepípedo:**
 - O valor absoluto do produto misto, $|\vec{a} \cdot (\vec{b} \times \vec{c})|$, representa o volume do paralelepípedo cujas arestas adjacentes são os vetores $\vec{a}$, $\vec{b}$, e $\vec{c}$.
 - Volume do Tetraedro: $\frac{1}{6} |\vec{a} \cdot (\vec{b} \times \vec{c})|$ (com $\vec{a}, \vec{b}, \vec{c}$ partindo do mesmo vértice).

**Coplanaridade:**
 - Se o produto misto é zero, $[\vec{a}, \vec{b}, \vec{c}] = 0$, então os três vetores são **coplanares** (estão no mesmo plano), assumindo que nenhum par de vetores é colinear e nenhum vetor é nulo. (O "volume" do paralelepípedo seria zero).

**Orientação:**
 - O sinal do produto misto indica a orientação do triedro $(\vec{a}, \vec{b}, \vec{c})$ (dextrógiro ou levógiro).

05 ) - Propriedades
title: **Def**

1. **Permutação Cíclica:**
   $$\vec{a} \cdot (\vec{b} \times \vec{c}) = \vec{b} \cdot (\vec{c} \times \vec{a}) = \vec{c} \cdot (\vec{a} \times \vec{b})$$
   (Não altera o valor).
2. **Troca de Posição de Dois Vetores Adjacentes:**
   $$\vec{a} \cdot (\vec{b} \times \vec{c}) = - \vec{a} \cdot (\vec{c} \times \vec{b})$$  $$\vec{a} \cdot (\vec{b} \times \vec{c}) = - \vec{b} \cdot (\vec{a} \times \vec{c})$$
   (Inverte o sinal).
3. **Equivalência de Notação:**
   $$\vec{a} \cdot (\vec{b} \times \vec{c}) = (\vec{a} \times \vec{b}) \cdot \vec{c}$$
   (O ponto e o cruz podem ser trocados de lugar sem alterar o resultado).
4. **Vetores Iguais ou Paralelos:**
   Se quaisquer dois dos três vetores são iguais ou paralelos, o produto misto é zero.

06 ) - Exemplo
title: **Def**

Sejam $\vec{a}=(1,0,2)$, $\vec{b}=(0,3,1)$, $\vec{c}=(4,1,0)$.
$$\begin{align*} \vec{a} \cdot (\vec{b} \times \vec{c}) &= \begin{vmatrix} 1 & 0 & 2 \\ 0 & 3 & 1 \\ 4 & 1 & 0 \end{vmatrix} \\ &= 1 \begin{vmatrix} 3 & 1 \\ 1 & 0 \end{vmatrix} - 0 \begin{vmatrix} 0 & 1 \\ 4 & 0 \end{vmatrix} + 2 \begin{vmatrix} 0 & 3 \\ 4 & 1 \end{vmatrix} \\ &= 1(0 - 1) - 0 + 2(0 - 12) \\ &= -1 - 24 = -25\end{align*}$$
O volume do paralelepípedo formado por estes vetores é $|-25| = 25$ unidades cúbicas. Os vetores não são coplanares.

5. Produto Tensorial (ou Produto Diádico / Produto Exterior)
01 ) - Definição
title: **Def**

O produto tensorial de dois vetores $\vec{u}$ (de um espaço vetorial $U$) e $\vec{v}$ (de um espaço vetorial $V$) é uma operação que resulta em um tensor de ordem superior, denotado por $\vec{u} \otimes \vec{v}$. Este tensor pertence ao espaço produto tensorial $U \otimes V$.
Para vetores $\vec{u} \in \mathbb{R}^m$ e $\vec{v} \in \mathbb{R}^n$, o produto tensorial $\vec{u} \otimes \vec{v}$ pode ser representado como uma matriz $m \times n$.

**Tensor (simplificado):**
- Escalares: tensores de ordem 0.
- Vetores: tensores de ordem 1.
- Matrizes: podem representar tensores de ordem 2.
Tensores generalizam esses conceitos e descrevem relações multilineares.

02 ) - Cálculo (para vetores coluna)
title: **Def**

Se $\vec{u} = \begin{pmatrix} u_1 \\ \vdots \\ u_m \end{pmatrix}$ (vetor coluna $m \times 1$) e $\vec{v} = \begin{pmatrix} v_1 \\ \vdots \\ v_n \end{pmatrix}$ (vetor coluna $n \times 1$).
O produto tensorial $\vec{u} \otimes \vec{v}^T$ (onde $\vec{v}^T$ é a transposta de $\vec{v}$, um vetor linha $1 \times n$) é a matriz $m \times n$:
1. $$\vec{u} \otimes \vec{v}^T = \vec{u} \vec{v}^T = \begin{pmatrix} u_1 \\ u_2 \\ \vdots \\ u_m \end{pmatrix} \begin{pmatrix} v_1 & v_2 & \cdots & v_n \end{pmatrix}$$2.$$= \begin{pmatrix}
   u_1 v_1 & u_1 v_2 & \cdots & u_1 v_n \\
   u_2 v_1 & u_2 v_2 & \cdots & u_2 v_n \\
   \vdots & \vdots & \ddots & \vdots \\
   u_m v_1 & u_m v_2 & \cdots & u_m v_n
   \end{pmatrix}$$
Os elementos da matriz resultante $M$ são $M_{ij} = u_i v_j$.

03 ) - Resultado
title: **Def**

O resultado do produto tensorial de dois vetores é um **tensor de ordem 2** (representável por uma matriz).
De forma mais geral, o produto tensorial de um tensor de ordem $k$ e um tensor de ordem $l$ é um tensor de ordem $k+l$.

04 ) - Propriedades
title: **Def**

Sejam $\vec{u}, \vec{v}, \vec{w}$ vetores e $k$ um escalar:

1. **Não Comutatividade:**
   Em geral, $\vec{u} \otimes \vec{v} \neq \vec{v} \otimes \vec{u}$.
2. **Associatividade com Multiplicação por Escalar:**
   $$k(\vec{u} \otimes \vec{v}) = (k\vec{u}) \otimes \vec{v} = \vec{u} \otimes (k\vec{v})$$
3. **Distributividade em relação à Adição Vetorial:**
   $$\vec{u} \otimes (\vec{v} + \vec{w}) = \vec{u} \otimes \vec{v} + \vec{u} \otimes \vec{w}$$  $$(\vec{u} + \vec{v}) \otimes \vec{w} = \vec{u} \otimes \vec{w} + \vec{v} \otimes \vec{w}$$
4. **Bilinearidade:** O produto tensorial é linear em cada um de seus argumentos.

05 ) - Aplicações
title: **Def**

**Física:**
 - **Mecânica dos Contínuos:** Tensor de tensões ($\sigma$), tensor de deformações ($\epsilon$).
 - **Relatividade Geral:** Tensor métrico ($g_{\mu\nu}$), tensor de energia-momento ($T_{\mu\nu}$).
 - **Mecânica Quântica:** Descrição de estados de sistemas multipartículas (ex: $\psi_A \otimes \psi_B$).
 - **Eletromagnetismo:** Tensor de campo eletromagnético $F^{\mu\nu}$.

**Engenharia:**
 - Análise de tensões e deformações.
 - Tensor de inércia (para rotação de corpos rígidos).

**Ciência de Dados e Aprendizado de Máquina:**
 - Tensores são estruturas de dados fundamentais para representar dados multidimensionais (ex: em TensorFlow, PyTorch).
 - Análise de Componentes Principais generalizada (Decomposição Tensorial).

06 ) - Exemplo
title: **Def**

Sejam $\vec{u} = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$ (vetor $2 \times 1$) e $\vec{v} = \begin{pmatrix} 3 \\ 4 \\ 5 \end{pmatrix}$ (vetor $3 \times 1$).
Então $\vec{v}^T = \begin{pmatrix} 3 & 4 & 5 \end{pmatrix}$ (vetor $1 \times 3$).
O produto tensorial $\vec{u} \otimes \vec{v}^T$ é:
$$\vec{u} \otimes \vec{v}^T = \begin{pmatrix} 1 \\ 2 \end{pmatrix} \begin{pmatrix} 3 & 4 & 5 \end{pmatrix} = \begin{pmatrix}
1 \cdot 3 & 1 \cdot 4 & 1 \cdot 5 \\
2 \cdot 3 & 2 \cdot 4 & 2 \cdot 5
\end{pmatrix} = \begin{pmatrix}
3 & 4 & 5 \\
6 & 8 & 10
\end{pmatrix}$$
O resultado é uma matriz $2 \times 3$, que é um tensor de ordem 2.

