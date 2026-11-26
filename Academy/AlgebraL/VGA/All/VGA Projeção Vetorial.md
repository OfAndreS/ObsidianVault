
---

```ad-example

#### **Projeção de um Vetor sobre outro Vetor**
```

---

```ad-quote
title: **Def**

A **projeção do vetor $\vec{u}$ sobre o vetor $\vec{v}$** (com $\vec{v} \neq \vec{0}$) é a componente vetorial de $\vec{u}$ na direção de $\vec{v}$. Geometricamente, corresponde à "sombra" ortogonal de $\vec{u}$ sobre a linha suporte de $\vec{v}$.
```

---
#### **01 )** - *A Fórmula da Projeção*

```ad-quote
title: **Def**

O vetor que representa a projeção de $\vec{u}$ sobre $\vec{v}$ é obtido pela fórmula:

1. $$\text{proj}_{\vec{v}}\vec{u} = \left( \frac{\vec{u} \cdot \vec{v}}{|\vec{v}|^2} \right) \vec{v}$$

**Produto Escalar:** 
- O numerador $\vec{u} \cdot \vec{v}$ é o produto escalar entre os vetores.

**Módulo ao Quadrado:** 
- O denominador $|\vec{v}|^2$ é o quadrado do **módulo** do vetor $\vec{v}$. Note que $|\vec{v}|^2 = \vec{v} \cdot \vec{v}$.

**Componente Escalar:** 
- O escalar $\left( \frac{\vec{u} \cdot \vec{v}}{|\vec{v}|^2} \right)$ é a **componente escalar** de $\vec{u}$ sobre $\vec{v}$.

```

```ad-quote
title: **Def**

Outra forma de apresentar a fórmula, utilizando o **versor** de $\vec{v}$ (o vetor unitário $\frac{\vec{v}}{|\vec{v}|}$), é:

$$
\text{proj}_{\vec{v}}\vec{u} = \left(\vec{u} \cdot \frac{\vec{v}}{|\vec{v}|}\right) \frac{\vec{v}}{|\vec{v}|}
$$

```

![[Pasted image 20250612191629.png]]

---
#### **02 )** - *Decomposição Ortogonal de Vetores*

```ad-quote
title: **Def**

A **Decomposição Ortogonal** é a ideia central que qualquer vetor $\vec{v}$ pode ser "quebrado" em duas componentes que são perpendiculares entre si, em relação à direção de um outro vetor $\vec{u}$.


**Componente Paralela ($\vec{v}_1$)**: 
- Esta é a **projeção vetorial** de $\vec{v}$ sobre $\vec{u}$. É a "sombra" de $\vec{v}$ na direção de $\vec{u}$ e, portanto, paralela a $\vec{u}$.


**Componente Ortogonal ($\vec{v}_2$)**: 
- Esta é a parte de $\vec{v}$ que "sobra" e é perpendicular (ortogonal) a $\vec{u}$.
```

```ad-quote
title: **Def**

A soma vetorial das duas componentes reconstrói o vetor original:

1. $$\vec{v}_1 + \vec{v}_2 = \vec{v}$$

Portanto, para encontrar a componente ortogonal ($\vec{v}_2$), basta subtrair a componente paralela ($\vec{v}_1$) do vetor original:

2. $$\vec{v}_2 = \vec{v} - \vec{v}_1$$

```

---
#### **03 )** - *Medida Algébrica  / Projeção Escalar*

```ad-quote
title: **Def**

A **Medida Algébrica**, é o mesmo que **Projeção Escalar**. Diferente da projeção vetorial (que é um vetor), a projeção escalar é um **Número** que representa o **Comprimento com sinal** da projeção.

A fórmula para a projeção de $\vec{u}$ sobre $\vec{v}$ é:

$$
\text{Medida Algébrica} = \frac{\vec{u} \cdot \vec{v}}{|\vec{u}|}
$$

```
###### ***O que esse número significa?***

```ad-quote
title: **Def**

**Valor Numérico:** 
- Representa o comprimento do vetor projeção.

$\theta$ é obtuso, $90^\circ < \theta \le 180^\circ$).
- Zero (0): Os vetores são ortogonais ($\theta = 90^\circ$), e a projeção é nula.

**Sinal Positivo (+):** 
- A projeção tem o mesmo sentido de $\vec{u}$ (ângulo $\theta$ entre os vetores é agudo, $0^\circ \le \theta < 90^\circ$).

**Negativo (-):** 
- A projeção tem o sentido oposto ao de $\vec{u}$ (ângulo 
```

```ad-quote
title: **Def**

Em resumo, a **Medida Algébrica** é o: 
- "Tamanho" da Projeção, 
  
Enquanto a **componente ortogonal** é o 
- Vetor que "Fecha" o triângulo retângulo com o vetor original e sua projeção.
```

![[Pasted image 20250612195302.png]]

---

```ad-example

#### **Projeção de um Ponto sobre um Plano**
```

---
#### **01 )** - _Projeção Ortogonal (Pé da Normal)_

```ad-quote
title: **Def**

A **projeção ortogonal** de um ponto $P$ sobre um plano $\alpha$ é o ponto $N$ no plano que corresponde à "sombra" perpendicular de $P$. O ponto $N$ é chamado de **pé da normal**.

A projeção ocorre na direção do **vetor normal** $\vec{n}$ do plano.
```

![[Pasted image 20250613175849.png]]

```ad-quote
title: **Fórmula da Projeção Ortogonal**

Para um plano $\alpha$ definido por um ponto $A$ e um vetor normal $\vec{n}$, a projeção $N$ do ponto $P$ é dada por:

1. $$N = P - \left( \frac{(P - A) \cdot \vec{n}}{\vec{n} \cdot \vec{n}} \right) \vec{n}$$

Se o vetor normal $\vec{n}$ for **unitário** ($|\vec{n}| = 1$), a fórmula se simplifica para:

2. $$N = P - [(P - A) \cdot \vec{n}] \vec{n}$$

**Componentes:**

$N$:
- É o ponto que queremos descobrir, o pé da normal (a projeção ortogonal de $P$ sobre o plano).

$P$:
- É o ponto que está sendo projetado sobre o plano.

$A$:
- É um ponto qualquer que pertence ao plano $\alpha$.

$\vec{n}$:
- É o vetor normal ao plano $\alpha$.
```

---
#### **02 )** - _Projeção Oblíqua_

```ad-quote
title: **Def**

Seja $\alpha$ um plano individualizado pelo ponto A e por um vetor normal $\vec{n}$ a ele ortogonal. Queremos as coordenadas de P' que é a projeção do ponto P sobre o plano $\alpha$, segundo a direção do vetor $\vec{v}$, dado.
```

![[Pasted image 20250613175550.png]]

```ad-quote
title: **Fórmula da Projeção Oblíqua**

A projeção $P'$ do ponto $P$ segundo uma direção $\vec{v}$ é dada por:

1. $$P' = P + \left( \frac{(A - P) \cdot \vec{n}}{\vec{v} \cdot \vec{n}} \right) \vec{v}$$

**Componentes:**

$P$:
- Ponto a ser projetado.

$A$: 
- Um ponto qualquer pertencente ao plano $\alpha$.

$\vec{n}$: 
- Vetor normal ao plano. (Não precisa ser unitário, mas é comum usá-lo assim).

$\vec{v}$: 
- Vetor que define a direção da projeção.
```

---

#### **03 )** - _Cálculo do Vetor Normal Unitário_

```ad-quote
title: **Def**

Se o plano $\alpha$ é definido por três pontos não colineares ($A$, $B$ e $C$), 
- **O vetor normal unitário $\vec{n}$** 

deve ser calculado antes de se poder usar as fórmulas de projeção.
```

![[Pasted image 20250613175959.png]]

```ad-quote
title: **Fórmula do Vetor Normal Unitário**

O vetor $\vec{n}$ é obtido pelo produto vetorial normalizado dos vetores formados pelos pontos:

1. $$\vec{n} = \frac{(B - A) \times (C - A)}{|(B - A) \times (C - A)|}$$

2. $$\vec{n} = \frac{\vec{a} \times \vec{b}}{|\vec{a} \times \vec{b}|}$$

```

```ad-quote
title: **Def**

**Passos:**

**Criar Vetores no Plano:**
- Forme os vetores $(B-A)$ e $(C-A)$.

**Produto Vetorial:**
- Calcule o produto vetorial entre eles para obter um vetor perpendicular ao plano.

**Normalização:**
- Divida o vetor resultante pelo seu próprio módulo para torná-lo unitário.
```

---
