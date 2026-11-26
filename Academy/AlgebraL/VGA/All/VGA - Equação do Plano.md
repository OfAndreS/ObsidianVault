
---

```ad-example

#### **01 ) - Equação Geral do Plano**
```

---

````ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A **Equação Geral do Plano** é uma equação linear da forma $ax+by+cz+d=0$ que descreve uma superfície plana infinita no espaço tridimensional. Seus componentes são:

**Coeficientes $(a, b, c)$:** 
- Representam as coordenadas de um **Vetor Normal** $\vec{n}$, que é sempre ortogonal (perpendicular) ao plano.

**Termo independente $(d)$:** 
- Está relacionado à posição do plano no espaço e sua distância em relação à origem $(0,0,0)$
````

````ad-quote
title: **Def**

##### _Aplicabilidade_

```ad-quote
title: **Def**

Esta é a forma mais comum de representar um plano, permitindo:
- A verificação rápida do pertencimento de um ponto ao plano.
- A determinação da orientação do plano no espaço através do seu vetor normal.

É fundamental em áreas como computação gráfica, física e engenharia para definir superfícies e limites.
````

````ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

A forma canônica da equação geral do plano é:

1. $$ax+by+cz+d=0$$
````

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Um plano $\alpha$ possui vetor normal $\vec{n}=(2, 3, -1)$ e passa pelo ponto $A(1, 2, 5)$. Encontre sua equação geral.

---

**Resolução:**
- **1. Utilizar a fórmula da equação do plano dado um ponto e um vetor normal:**
  $$a(x-x_0) + b(y-y_0) + c(z-z_0) = 0$$ $$2(x-1) + 3(y-2) -1(z-5) = 0$$

- **2. Simplificar a expressão:**
  $$2x - 2 + 3y - 6 - z + 5 = 0$$ $$2x + 3y - z - 3 = 0$$

**Resposta:**
- A equação geral do plano é $$2x + 3y - z - 3 = 0$$
```

---

```ad-example

#### **02 ) - Obtenção da Equação Geral do Plano**
```

---

````ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A equação geral de um plano pode ser obtida por dois métodos principais:


**Coplanaridade (via Determinantes):** 
- Baseia-se na ideia de que os vetores que definem o plano (formados a partir de pontos e vetores diretores) e o vetor de um ponto genérico no plano devem ser coplanares. Isso é verificado se o determinante da matriz formada por esses vetores é nulo.

**Ortogonalidade (via Vetor Normal):** 
- Baseia-se no fato de que qualquer vetor contido no plano é perpendicular (ortogonal) ao vetor normal do plano. Isso é verificado se o produto escalar entre eles é nulo.
````

````ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

Para obter a equação geral do plano, podemos usar as seguintes fórmulas:

**Obtenção via Determinantes / Coplanaridade:**

-   **Caso 1: Um ponto $P_0(x_0, y_0, z_0)$ e dois vetores diretores $\vec{v_1}(l_1, m_1, n_1)$ e $\vec{v_2}(l_2, m_2, n_2)$**

1.  $$\begin{vmatrix} x-x_{0} & y-y_{0} & z-z_{0} \\ l_{1} & m_{1} & n_{1} \\ l_{2} & m_{2} & n_{2} \end{vmatrix} = 0$$

-   **Caso 2: Três pontos não colineares $P_1(x_1, y_1, z_1)$, $P_2(x_2, y_2, z_2)$ e $P_3(x_3, y_3, z_3)$**

2.  $$\begin{vmatrix} x-x_{1} & y-y_{1} & z-z_{1} \\ x_{2}-x_{1} & y_{2}-y_{1} & z_{2}-z_{1} \\ x_{3}-x_{1} & y_{3}-y_{1} & z_{3}-z_{1} \end{vmatrix} = 0$$

**Obtenção via Vetor Normal / Ortogonalidade:**

-   Para um plano $\alpha$ que passa por $P_0(x_0, y_0, z_0)$ e tem vetor normal $\vec{n}(a,b,c)$:

3.  $$(P-P_{0}) \cdot \vec{n} = 0$$

-   Desenvolvendo o produto escalar, obtemos:

4.  $$a(x-x_{0})+b(y-y_{0})+c(z-z_{0})=0$$
````

---

```ad-example

#### **03 ) - Equação Segmentária do Plano**
```

---

````ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A **Equação Segmentária do Plano** é uma forma da equação que evidencia diretamente os pontos onde o plano intercepta os eixos coordenados. Sua forma é $\frac{x}{p}+\frac{y}{q}+\frac{z}{r}=1$, onde $p$, $q$ e $r$ são as coordenadas das interceptações nos eixos $x$, $y$ e $z$, respectivamente.
````

````ad-quote
title: **Def**

##### _Aplicabilidade_

```ad-quote
title: **Def**

Esta equação é extremamente útil para esboçar rapidamente a posição de um plano no espaço, pois os pontos de interceptação $(p,0,0)$, $(0,q,0)$ e $(0,0,r)$ fornecem referências visuais imediatas. No entanto, só é aplicável se o plano **não passar pela origem** e **não for paralelo a nenhum dos eixos**.
````

````ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

A fórmula da equação segmentária do plano é:

1. $$\frac{x}{p}+\frac{y}{q}+\frac{z}{r}=1$$
Onde $p, q, r \neq 0$.
````

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Obter a equação segmentária do plano $4x-3y+2z-12=0$.

---

**Resolução:**
- **1. Isolar o termo independente no lado direito da equação:**
  $$4x-3y+2z=12$$

- **2. Dividir todos os termos pelo termo independente (12) para igualar a 1:**
  $$\frac{4x}{12}-\frac{3y}{12}+\frac{2z}{12}=1$$

- **3. Simplificar as frações:**

**Resposta:**
- A equação segmentária do plano é:
1. $$\frac{x}{3}+\frac{y}{-4}+\frac{z}{6}=1$$
  Isso indica que o plano intercepta o eixo x em $(3,0,0)$, o eixo y em $(0,-4,0)$ e o eixo z em $(0,0,6)$.
```

---

```ad-example

#### **04 ) - Pertencimento de Ponto ao Plano**
```

---

````ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A condição de pertencimento verifica se um ponto específico $P_0(x_0, y_0, z_0)$ está contido em um plano $\alpha$ dado pela equação $ax + by + cz + d = 0$.
````

![[Pasted image 20250716180658.png]]

````ad-quote
title: **Def**

##### _Aplicabilidade_

```ad-quote
title: **Def**

É uma operação fundamental para resolver problemas geométricos, como:
- Verificar se um ponto está em uma superfície.
- Determinar se uma trajetória cruza um plano em um ponto específico.
- Confirmar se vértices de um poliedro estão no plano correto.
````

````ad-quote
title: **Def**

##### _Fórmula da Condição_

```ad-quote
title: **Def**

O ponto $P_0(x_0, y_0, z_0)$ pertence ao plano se, e somente se, suas coordenadas satisfazem a equação do plano:

1. $$ax_0 + by_0 + cz_0 + d = 0$$
````

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Verificar se o ponto $A(3, 1, 2)$ pertence ao plano $\alpha: 2x + y - 3z - 1 = 0$.

---

**Resolução:**
- **1. Substituir as coordenadas do ponto $A(x=3, y=1, z=2)$ na equação do plano:**
  $$2(3) + (1) - 3(2) - 1 = 0$$

- **2. Calcular o resultado da expressão:**
  $$6 + 1 - 6 - 1 = 0$$

- **3. Verificar se a igualdade é verdadeira:**
  $$0 = 0$$

**Resposta:**
- Como a igualdade $0 = 0$ é verdadeira, a condição foi satisfeita. Portanto, o ponto $A(3, 1, 2)$ **pertence** ao plano $\alpha$.
```

---