
---

```ad-example

#### **01 ) - Condição de Paralelismo de Reta e Plano**
```

---

```ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

Uma reta $r$ é paralela a um plano $\alpha$ se o vetor diretor da reta, $\vec{v} = (l, m, n)$, for ortogonal (perpendicular) ao vetor normal do plano, $\vec{n} = (a, b, c)$.

Isso significa que o vetor que define a direção da reta não tem componente na direção "para fora" do plano, mantendo-se sempre à mesma distância dele.
```

![[Pasted image 20250719210555.png]]

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

A condição de paralelismo entre a reta $r$ e o plano $\alpha$ é verificada pela condição de ortogonalidade entre seus vetores $\vec{v}$ e $\vec{n}$. O produto escalar entre eles deve ser nulo:

1. $$\vec{v} \cdot \vec{n} = 0$$
2. $$al + bm + cn = 0$$
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Verificar se a reta $r: \frac{x-1}{2} = \frac{y}{3} = \frac{z+2}{-4}$ é paralela ao plano $\alpha: 5x + 2y + 4z - 1 = 0$.

---

**Resolução:**
- Vetor diretor da reta $r$: $\vec{v} = (2, 3, -4)$
- Vetor normal do plano $\alpha$: $\vec{n} = (5, 2, 4)$

- Calculando o produto escalar:
1. $$\vec{v} \cdot \vec{n} = (2)(5) + (3)(2) + (-4)(4)$$
2. $$\vec{v} \cdot \vec{n} = 10 + 6 - 16 = 0$$

**Resposta:**
- Como o produto escalar é zero, o vetor diretor da reta é ortogonal ao vetor normal do plano. Portanto, a reta $r$ **é paralela** ao plano $\alpha$.
```

---

```ad-example

#### **02 ) - Condição de Ortogonalidade de Reta e Plano**
```

---

```ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

Uma reta $r$ é ortogonal (ou perpendicular) a um plano $\alpha$ se o seu vetor diretor, $\vec{v} = (l, m, n)$, tiver a mesma direção do vetor normal do plano, $\vec{n} = (a, b, c)$. Ou seja, os dois vetores devem ser paralelos.
```

![[Pasted image 20250719210509.png]]

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

A condição de ortogonalidade entre a reta $r$ e o plano $\alpha$ é verificada pela condição de paralelismo entre os vetores $\vec{v}$ e $\vec{n}$. Suas componentes devem ser proporcionais:

1. $$\frac{l}{a} = \frac{m}{b} = \frac{n}{c}$$
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema 1:**
- Achar as equações da reta que passa por $P_0 = (3, 5, 0)$ e é ortogonal ao plano $\alpha: 2x + 4y - z + 1 = 0$.

---

**Resolução:**
- **a)** A equação da reta que passa por $P_0$ é $r: \frac{x-3}{l} = \frac{y-5}{m} = \frac{z-0}{n}$.
- **b)** Pela condição de ortogonalidade, o vetor diretor da reta $\vec{v}=(l,m,n)$ é paralelo ao vetor normal do plano $\vec{n}=(2,4,-1)$. Portanto, podemos usar $\vec{n}$ como o vetor diretor da reta:
  - $l=a=2$
  - $m=b=4$
  - $n=c=-1$
- **c) Resposta:**
  $$r: \frac{x-3}{2} = \frac{y-5}{4} = \frac{z}{-1}$$

---

**Problema 2:**
- Obter a equação do plano que passa por $P_0 = (3, 5, 0)$ e é ortogonal à reta $r: \frac{x-1}{1} = \frac{y}{2} = \frac{z+2}{4}$.

---

**Resolução:**
- **a)** Pela condição de ortogonalidade, o vetor normal do plano $\vec{n}=(a,b,c)$ é paralelo ao vetor diretor da reta $\vec{v}=(1,2,4)$. Então:
  - $a=l=1$
  - $b=m=2$
  - $c=n=4$
- A equação do plano é da forma $\alpha: 1x + 2y + 4z + d = 0$.
- **b)** Como o ponto $P_0(3,5,0)$ pertence ao plano, podemos substituir suas coordenadas para achar $d$:
  $$1(3) + 2(5) + 4(0) + d = 0$$
  $$3 + 10 + 0 + d = 0 \implies d = -13$$
- **c) Resposta:**
  $$\alpha: x + 2y + 4z - 13 = 0$$
```

---