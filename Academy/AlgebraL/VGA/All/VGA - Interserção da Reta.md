
---

```ad-example

#### **01 ) - Interseção de Reta e Plano**
```

---

```ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A interseção de uma reta $r$ com um plano $\alpha$, quando a reta não é paralela ao plano, é um único ponto $P(x,y,z)$. As coordenadas deste ponto devem satisfazer simultaneamente a equação da reta e a equação do plano.
```

![[Pasted image 20250719205346.png]]

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

Para encontrar o ponto de interseção, o método mais comum é:
- Escrever a reta em sua forma paramétrica:
1. $$r: \begin{cases} x = x_0 + lt \\ y = y_0 + mt \\ z = z_0 + nt \end{cases}$$
- Substituir as expressões de $x, y, z$ da reta na equação geral do plano:
2. $$\alpha: ax + by + cz + d = 0$$
- Resolver a equação resultante para encontrar o valor do parâmetro $t$.
- Substituir o valor de $t$ de volta nas equações paramétricas da reta para obter as coordenadas do ponto de interseção $P$.
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Calcular o ponto $P$ de interseção da reta $r: \frac{x+3}{1} = \frac{y+2}{2} = \frac{z+10}{3}$ com o plano $\alpha: 3x - 2y + 4z + 12 = 0$.

---

**Resolução:**
- **a) Equações paramétricas de r:**
1. $$r: \begin{cases} x = -3 + t \\ y = -2 + 2t \\ z = -10 + 3t \end{cases}$$

- **b ) Substituindo as equações paramétricas de r na equação do plano:**
2. $$3(-3+t) - 2(-2+2t) + 4(-10+3t) + 12 = 0$$
3. $$-9 + 3t + 4 - 4t - 40 + 12t + 12 = 0$$
4. $$11t - 33 = 0 \implies 11t = 33 \implies t = 3$$

- **c ) Levando o valor de t = 3 nas equações paramétricas:**
5. $$x = -3 + 3 = 0$$
6. $$y = -2 + 2(3) = -2 + 6 = 4$$
7. $$z = -10 + 3(3) = -10 + 9 = -1$$

**Resposta:**
- O ponto de interseção é $P=(0, 4, -1)$.
```

---

```ad-example

#### **02 ) - Interseção de Duas Retas**
```

---

```ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A interseção de duas retas concorrentes, $r$ e $s$, é um único ponto $P(x,y,z)$. As coordenadas deste ponto devem satisfazer as equações de ambas as retas simultaneamente.
```

![[Pasted image 20250719205425.png]]

```ad-quote
title: **Def**

##### _Fórmula_

```ad-quote
title: **Def**

No ponto de interseção $P$, as coordenadas $(x,y,z)$ são as mesmas para ambas as retas.

---

Para encontrar o ponto de interseção de duas retas $r$ e $s$ dadas na forma simétrica ou reduzida, o procedimento é:
- Montar um sistema de equações igualando as expressões correspondentes de $x, y, z$.
- Escolher duas das equações para formar um sistema com duas variáveis (por exemplo, $x$ e $y$) e resolvê-lo.
- Substituir os valores encontrados em uma das equações restantes para encontrar a terceira variável (por exemplo, $z$).
- É crucial verificar se a solução encontrada satisfaz todas as equações originais para confirmar a interseção.
```

> [!error] **Exemplo 01 )**

```ad-quote
title: **Def**

**Problema:**
- As retas $r: \frac{x-1}{2} = \frac{y-1}{0} = \frac{z+2}{1}$ e $s: \frac{x}{1} = \frac{y+1}{2} = \frac{z+1}{-1}$ se interceptam num ponto $P$. Achar as coordenadas de $P$.

---

**Resolução:**

**a) Equações paramétricas das retas:**

- Para a reta r (usando o parâmetro $t$), a expressão $\frac{y-1}{0}$ implica que a coordenada $y$ é constante e igual a 1.

1. $$r: \begin{cases} x = 1 + 2t \\ y = 1 \\ z = -2 + t \end{cases}$$

- Para a reta s (usando o parâmetro $k$):

2. $$s: \begin{cases} x = k \\ y = -1 + 2k \\ z = -1 - k \end{cases}$$


**b ) Igualando as equações para encontrar os parâmetros:**

- Para achar a interseção, as coordenadas $(x, y, z)$ devem ser iguais. Montamos o sistema:

3. $$\begin{cases} 1 + 2t = k \\ 1 = -1 + 2k \\ -2 + t = -1 - k \end{cases}$$

- Da segunda equação, encontramos $k$: $1 = -1 + 2k \implies 2 = 2k \implies k = 1$.

- Substituindo $k=1$ na primeira equação, encontramos $t$: $1 + 2t = 1 \implies 2t = 0 \implies t = 0$.

- **c ) Levando o valor de t = 0 nas equações de r:**
6. $$x = 1 + 2(0) = 1$$
7. $$y = 1$$
8. $$z = -2 + 0 = -2$$

**Resposta:**
- O ponto de interseção é $P=(1, 1, -2)$.
```

> [!error] **Exemplo 02 )**

```ad-quote
title: **Def**

**Problema:**
- Achar o ponto $P$ de interseção das retas $r: \frac{x-2}{3} = \frac{y-4}{5} = \frac{z}{2}$ e $s: \frac{x+1}{2} = \frac{y+1}{4} = \frac{z+2}{1}$.

---

**Resolução:**
- **a) Tomemos a primeira igualdade de r e s para formar um sistema com x e y:**
  $$\begin{cases} \frac{x-2}{3} = \frac{y-4}{5} \implies 5x - 10 = 3y - 12 \implies 5x - 3y = -2 \\ \frac{x+1}{2} = \frac{y+1}{4} \implies 4x + 4 = 2y + 2 \implies 4x - 2y = -2 \implies 2x - y = -1 \end{cases}$$
- Resolvendo o sistema (por exemplo, isolando $y$ na segunda equação, $y = 2x+1$, e substituindo na primeira):
  $$5x - 3(2x+1) = -2 \implies 5x - 6x - 3 = -2 \implies -x = 1 \implies x = -1$$
  $$y = 2(-1) + 1 \implies y = -1$$

- **b) Levemos x = -1 na equação de r (ou s) para obter z:**
- Usando a relação entre $x$ e $z$ da reta $r$:
  $$\frac{x-2}{3} = \frac{z}{2} \implies \frac{-1-2}{3} = \frac{z}{2} \implies \frac{-3}{3} = \frac{z}{2} \implies -1 = \frac{z}{2} \implies z = -2$$

**Resposta:**
- O ponto de interseção é $P=(-1, -1, -2)$.
```

---
