
---

```ad-example
#### **Interseção de um Plano com os Eixos e Equação Segmentária**
```

---

```ad-quote
title: **Def**

Os **interceptos** de um plano são os pontos onde sua superfície cruza os eixos coordenados (x, y, z). Encontrar esses pontos é um método fundamental para esboçar a posição e a orientação de um plano no espaço 3D.
```

![[Pasted image 20250717194956.png]]

```ad-quote
title: **Def: Interceptos de um Plano**

**Princípio Fundamental:**
- Para encontrar o ponto de interseção com um eixo, as coordenadas dos outros dois eixos são definidas como zero na equação geral do plano ($ax+by+cz+d=0$).

---

**Interseção com o Eixo X (Abscissas):**
- O intercepto no eixo x, $A(p, 0, 0)$, é encontrado com $p$:

1. $$p = -\frac{d}{a}$$

**Interseção com o Eixo Y (Ordenadas):**
- O intercepto no eixo y, $B(0, q, 0)$, é encontrado com $q$:

2. $$q = -\frac{d}{b}$$

**Interseção com o Eixo Z (Cotas):**
- O intercepto no eixo z, $C(0, 0, r)$, é encontrado com $r$:

3. $$r = -\frac{d}{c}$$
```

---

> [!error] **Exemplo: Determinando os Pontos de Interseção**

```ad-quote
title: **Def**

**Problema:**
- Determinar os pontos de interseção do plano $\alpha: 4x + 3y - z - 12 = 0$ com os eixos coordenados.

---

**Resolução:**

- Para encontrar cada ponto, zeramos as coordenadas dos outros dois eixos na equação do plano.

**Intercepto no Eixo X fazer $y=0$ e $z=0$:**
- O cálculo da coordenada x é:

2. $$4x - 12 = 0 \implies x = 3$$

**Intercepto no Eixo Y (fazer x=0 e z=0):**
- O cálculo da coordenada y é:

4. $$3y - 12 = 0 \implies y = 4$$

**Intercepto no Eixo Z (fazer x=0 e y=0):**
- O cálculo da coordenada z é:

6. $$-z - 12 = 0 \implies z = -12$$

**Resposta:**
- Os pontos de interseção do plano com os eixos coordenados são:
  - **Eixo x: $A(3, 0, 0)$**
  - **Eixo y: $B(0, 4, 0)$**
  - **Eixo z: $C(0, 0, -12)$**
- Estes três pontos definem a posição do plano no espaço e podem ser usados para esboçar sua representação gráfica.
```

---

```ad-example
#### **Equação Segmentária do Plano**
```

---

```ad-quote
title: **Def: Equação Segmentária**

A **Equação Segmentária do Plano** é uma forma de representar a equação de um plano com base nos comprimentos dos segmentos que ele intercepta nos eixos coordenados. É particularmente útil para visualizar rapidamente esses interceptos.

---

**Fórmula:**
- Se um plano intercepta os eixos coordenados nos pontos $A(p, 0, 0)$, $B(0, q, 0)$ e $C(0, 0, r)$, com $p, q, r \neq 0$, sua equação segmentária é:

1. $$\frac{x}{p} + \frac{y}{q} + \frac{z}{r} = 1$$

**Como obter a partir da Equação Geral ($ax+by+cz+d=0$):**
1. Mova o termo independente ($d$) para o lado direito da equação: $ax+by+cz = -d$.
2. Divida toda a equação por $-d$ para que o lado direito seja igual a 1.
3. Simplifique a equação para a forma segmentária.
```

---

> [!error] **Exemplo: Conversão da Equação Geral para Segmentária**

```ad-quote
title: **Def**

**Problema:**
- Obter a equação segmentária do plano $\alpha: 4x + 3y - z - 12 = 0$.

---

**Resolução:**

**Isolar o termo independente:**

2. $$4x + 3y - z = 12$$

**Dividir todos os termos por 12 (o valor do termo independente isolado) para igualar a 1:**

4. $$\frac{4x}{12} + \frac{3y}{12} - \frac{z}{12} = \frac{12}{12}$$

**Simplificar as frações para obter a forma segmentária:**

6. $$\frac{x}{3} + \frac{y}{4} + \frac{z}{-12} = 1$$

**Resposta:**
- A equação segmentária do plano é **$\frac{x}{3} + \frac{y}{4} + \frac{z}{-12} = 1$**.
- A partir dela, podemos ver diretamente os interceptos:
  - **p = 3** (no eixo x)
  - **q = 4** (no eixo y)
  - **r = -12** (no eixo z)
```

---
