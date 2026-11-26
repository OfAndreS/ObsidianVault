
---

```ad-quote
title: **Def: Equação do Plano que Passa por um Ponto e é Ortogonal a um Vetor**

A equação de um plano $\alpha$ que passa por um ponto conhecido $P_o(x_o, y_o, z_o)$ e é ortogonal a um **vetor normal** $\vec{n}(a, b, c)$ é derivada da condição de ortogonalidade.

---

**Princípio Fundamental:**
- Qualquer vetor contido no plano, como o vetor $(P - P_o)$ formado por um ponto genérico $P(x, y, z)$ do plano e o ponto dado $P_o$, será sempre **ortogonal** ao vetor normal $\vec{n}$.

**Condição de Ortogonalidade:**
- Dois vetores são ortogonais se o seu **produto interno (ou escalar)** for igual a zero.

1. $$(P - P_o) \cdot \vec{n} = 0$$
```

![[Pasted image 20250718083507.png]]

---

```ad-example
#### **Como Obter a Equação Geral?**
```

---
##### _Obtenção via Vetor Normal / Ortogonalidade_

```ad-quote
title: **Def**

Para um plano $\alpha$ que passa por um ponto $P_o(x_o, y_o, z_o)$ e é ortogonal a um vetor normal $\vec{n}(a, b, c)$.
```

```ad-quote
title: **Dedução**

**1 ) Definir os vetores:**

- Seja $P(x, y, z)$ um ponto genérico qualquer do plano $\alpha$.
O vetor que liga o ponto conhecido $P_o$ ao ponto genérico $P$ é:

1. $$(P - P_o) = (x - x_o, y - y_o, z - z_o)$$

- O vetor normal ao plano é dado:

2. $$\vec{n} = (a, b, c)$$

---

**2 ) Aplicar a condição de ortogonalidade:**

- O produto interno entre o vetor $(P - P_o)$ e o vetor normal $\vec{n}$ deve ser nulo.

3.  $$(P - P_o) \cdot \vec{n} = 0$$

---

**3 ) Desenvolver o produto interno:**

- A equação se expande para:

4. $$a(x - x_o) + b(y - y_o) + c(z - z_o) = 0$$

---

**4 ) Chegar à Equação Geral do Plano:**

- Distribuindo os coeficientes e agrupando os termos, obtemos a equação geral do plano:

5. $$ax + by + cz + (-ax_o - by_o - cz_o) = 0$$

- Onde o termo independente $d$ é igual a $d = -ax_o - by_o - cz_o$. Sendo sua forma final:

6. $$ax + by + cz + d = 0$$
```

---

> [!error] **Exemplo: Encontrando a Equação do Plano**

```ad-quote
title: **Def**

**Problema:**
- Encontrar a equação do plano $\alpha$ que passa pelo ponto $A = (1, 3, 5)$ e é ortogonal ao vetor $\vec{n} = (2, 4, 6)$.
```

```ad-quote
title: **Def**

**Resolução:**

**1. Identificar os dados:**
- Ponto $P_o = A(1, 3, 5) \implies x_o = 1, y_o = 3, z_o = 5$
- Vetor Normal $\vec{n} = (2, 4, 6) \implies a = 2, b = 4, c = 6$

---

**2. Escrever a equação a partir do produto interno:**
- A equação do plano é dada por $a(x-x_o) + b(y-y_o) + c(z-z_o) = 0$.
- Substituindo os valores:

1. $$2(x - 1) + 4(y - 3) + 6(z - 5) = 0$$

---

**3. Simplificar a equação para a forma geral ($ax + by + cz + d = 0$):**
- Distribuir os coeficientes:

2. $$2x - 2 + 4y - 12 + 6z - 30 = 0$$

- Agrupar os termos:

3. $$2x + 4y + 6z - 44 = 0$$

- O coeficiente $d$ é, portanto, $d = -44$.

---

**Resposta:**
- A equação geral do plano $\alpha$ é:
4. $$2x + 4y + 6z - 44 = 0$$
```

---