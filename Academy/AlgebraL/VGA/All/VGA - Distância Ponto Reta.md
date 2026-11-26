

---

```ad-example

#### **01 ) - Distância de Ponto a uma Reta**
```

---

```ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A distância de um ponto $A$ a uma reta $r$, denotada por $d(A,r)$, é a menor distância entre o ponto $A$ e qualquer ponto sobre a reta $r$. Essa distância é medida ao longo do segmento de reta que é perpendicular à reta $r$ e que conecta o ponto $A$ a ela.

```

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

Para calcular a distância entre um ponto $A$ e uma reta $r$ que passa por um ponto $P_0$ e tem vetor diretor $\vec{v}$, utilizamos a seguinte fórmula, baseada no produto vetorial:

1. $$d(A, r) = \frac{|\vec{P_0A} \times \vec{v}|}{|\vec{v}|}$$

Onde:
- $\vec{P_0A}$ é o vetor que liga o ponto $P_0$ da reta ao ponto externo $A$.
- $\vec{v}$ é o vetor diretor da reta $r$.
- $|\vec{P_0A} \times \vec{v}|$ é o módulo (magnitude) do produto vetorial entre os dois vetores.
- $|\vec{v}|$ é o módulo do vetor diretor.
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Calcular a distância do ponto $A = (2, 3, 5)$ à reta $r$ que passa pelo ponto $P_0 = (1, 1, 2)$ e tem vetor diretor $\vec{v} = (2, 4, 1)$.

---

**Resolução:**

**1 ) Encontrar o vetor $\vec{P_0A}$:**
  
  1. $$\vec{P_0A} = A - P_0 = (2-1, 3-1, 5-2) = (1, 2, 3)$$


**2 ) Calcular o produto vetorial $\vec{P_0A} \times \vec{v}$:**
  
  2. $$\vec{P_0A} \times \vec{v} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ 1 & 2 & 3 \\ 2 & 4 & 1 \end{vmatrix}$$
  
  3. $$= \vec{i}(2 \cdot 1 - 3 \cdot 4) - \vec{j}(1 \cdot 1 - 3 \cdot 2) + \vec{k}(1 \cdot 4 - 2 \cdot 2)$$
  
  4. $$= \vec{i}(2 - 12) - \vec{j}(1 - 6) + \vec{k}(4 - 4)$$
  
  5. $$= -10\vec{i} + 5\vec{j} + 0\vec{k} = (-10, 5, 0)$$


**3 ) Calcular os módulos:**
  - Módulo do produto vetorial:

6. $$|\vec{P_0A} \times \vec{v}| = \sqrt{(-10)^2 + 5^2 + 0^2} = \sqrt{100 + 25} = \sqrt{125} = 5\sqrt{5}$$
  - Módulo do vetor diretor:

7. $$|\vec{v}| = \sqrt{2^2 + 4^2 + 1^2} = \sqrt{4 + 16 + 1} = \sqrt{21}$$

- **4. Calcular a distância:**

8. $$d(A, r) = \frac{5\sqrt{5}}{\sqrt{21}}$$

**Resposta:**
- A distância do ponto A à reta r é $\frac{5\sqrt{5}}{\sqrt{21}}$ unidades de comprimento.
```

---