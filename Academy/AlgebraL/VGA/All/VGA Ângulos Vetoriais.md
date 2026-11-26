
---

```ad-quote
title: **Def**

Ângulos vetoriais descrevem a relação angular entre dois vetores que partilham uma origem comum.
```

```ad-quote
title: **Def**

O ângulo entre dois vetores $\vec{a}$ e $\vec{b}$ (não nulos) é o menor ângulo $\theta$ formado entre eles quando suas origens coincidem. 
 - $0^\circ \le \theta \le 180^\circ$ / ou $0 \le \theta \le \pi$ radianos.

---

 Se $\theta = 0^\circ$: 
 - vetores com mesma direção e sentido.

 Se $\theta = 180^\circ$: 
 - vetores com mesma direção e sentidos opostos.

 Se $\theta = 90^\circ$: 
 - vetores ortogonais (perpendiculares).
```

---
#### **02 )** - *Cálculo do Ângulo Vetorial*

```ad-quote
title: **Def**

O ângulo $\theta$ é calculado usando o produto escalar (produto interno).
A fórmula base é:


1. $$\vec{a} \cdot \vec{b} = |\vec{a}| |\vec{b}| \cos \theta$$
Isolando $\theta:$
2. $$\theta = \arccos\left(\frac{\vec{a} \cdot \vec{b}}{|\vec{a}| |\vec{b}|}\right)$$
```

---
#### **03 )** - *Em Termos de Componentes*

```ad-quote
title: **Def**

###### **Vetores 2D**

---

Sejam $\vec{a} = (a_x, a_y)$ e $\vec{b} = (b_x, b_y)$:
 
 Produto escalar:
 
 1. $$\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y$$
 
 Módulo de $\vec{a}$: 
 
 2. $$|\vec{a}| = \sqrt{a_x^2 + a_y^2}$$
 
 Módulo de $\vec{b}:$
 
 3. $$|\vec{b}| = \sqrt{b_x^2 + b_y^2}$$

---

**Fórmula:**

1. $$\theta = \arccos\left(\frac{a_x b_x + a_y b_y}{\sqrt{a_x^2 + a_y^2} \sqrt{b_x^2 + b_y^2}}\right)$$
```

```ad-quote
title: **Def**

###### **Vetores 3D**

---

Sejam $\vec{a} = (a_x, a_y, a_z)$ e $\vec{b} = (b_x, b_y, b_z):$
 
 Produto escalar: 
 
 1. $$\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z$$
 
 Módulo de $\vec{a}$: 
 
 2. $$|\vec{a}| = \sqrt{a_x^2 + a_y^2 + a_z^2}$$
 
 Módulo de $\vec{b}$: 
 
 3. $$|\vec{b}| = \sqrt{b_x^2 + b_y^2 + b_z^2}$$
---

**Fórmula:**

1. $$\theta = \arccos\left(\frac{a_x b_x + a_y b_y + a_z b_z}{\sqrt{a_x^2 + a_y^2 + a_z^2} \sqrt{b_x^2 + b_y^2 + b_z^2}}\right)$$
```

---
#### **04 )** - *Propriedades*

 ```ad-quote
title: **Def**

**Comutatividade:** 
 - O ângulo de $\vec{a}$ para $\vec{b}$ é o mesmo que de $\vec{b}$ para $\vec{a}$.
 
 **Sinal do Produto Escalar e Ângulo:**
   * $\vec{a} \cdot \vec{b} > 0 \implies 0^\circ \le \theta < 90^\circ$ (agudo)
   * $\vec{a} \cdot \vec{b} < 0 \implies 90^\circ < \theta \le 180^\circ$ (obtuso)
   * $\vec{a} \cdot \vec{b} = 0 \implies \theta = 90^\circ$ (ortogonais, se não nulos)
 
 **Vetores Paralelos $(\vec{a} \parallel \vec{b})$:**
   * $\theta = 0^\circ$ (mesmo sentido)
   * $\theta = 180^\circ$ (sentidos opostos)
   * Neste caso, $\vec{a} = k\vec{b}$ para algum escalar k.

 **Ângulos Diretores:** 
 - Em 3D, são os ângulos $(\alpha, \beta, \gamma)$ que um vetor forma com os eixos positivos $x$, $y$, $z$, respectivamente. Os cossenos desses ângulos $(\cos \alpha, \cos \beta, \cos \gamma)$ são os cossenos diretores.
```

---

