
---

```ad-example

#### **01 ) -** Equação Paramétrica da Reta
```

---
##### *Explicação do conceito*

```ad-quote
title: **Def**

A equação paramétrica descreve:
- As coordenadas de qualquer ponto $P(x,y,z)$ de uma reta com base em um ponto conhecido $P_0​(x_0 \ ​,y_0​\ ,z_0​)$ pelo qual a reta passa e na direção de um **vetor diretor** $v=(l,m,n)$. Cada coordenada é expressa em função de uma variável real, o **parâmetro** $t$.
```

![[Pasted image 20250719175405.png]]
##### *Aplicabilidade*

```ad-quote
title: **Def**

- É extremamente útil para descrever o movimento de um objeto ao longo de uma trajetória retilínea, onde t pode representar o tempo. Também facilita a geração de pontos pertencentes à reta, bastando variar o valor de t.
```

>[!example] **Fórmula**

```ad-quote
title: **Def**

- A partir da equação vetorial $P=P0​+tv$, derivamos as equações paramétricas:

1. $$r:
\begin{cases}
x=x_0+lt \\
y=y_0+mt \\
z=z_0+nt & 
\end{cases}(t\in\mathbb{R})$$
```

 >[!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:** 
- Encontre as equações paramétricas da reta que passa pelo ponto $A(3,2,−1)$ e tem vetor diretor $v=(1,−2,4)$.

---

**Resolução:**

- Ponto inicial: $P0​=(3,2,−1)$  

- Vetor diretor: $v=(1,−2,4)$  

**Resposta:**

1. $$r:
\begin{cases}
x=3+t \\
y=2-2t \\
z=-1+4t & 
\end{cases}$$

```

---

```ad-example

#### **02 ) -** Equação Simétrica da Reta
```

---
##### _Explicação do conceito_

```ad-quote
title: **Def**

- A equação simétrica é obtida ao isolar o parâmetro $t$ em cada uma das equações paramétricas e, em seguida, igualar as expressões resultantes. Isso cria uma relação de igualdade direta entre as coordenadas $x, y, z$.
```
##### _Aplicabilidade_

```ad-quote
title: **Def**

- É útil para verificar rapidamente se um ponto pertence a uma reta (substituindo $x,y,z$ e checando a igualdade) e para identificar o ponto de passagem e o vetor diretor de forma imediata. Requer que todas as componentes do vetor diretor ($l,m,n$) sejam diferentes de zero.
```

> [!example] **Fórmula**

```ad-quote
title: **Def**

- A partir do isolamento de $t$ nas equações paramétricas, obtemos:

1. $$\frac{x-x_0}{l} = \frac{y-y_0}{m} = \frac{z-z_0}{n}$$
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Obtenha a equação simétrica da reta que passa pelo ponto $P_0(3,2,-1)$ e tem vetor diretor $v=(1,−2,4)$.

---

**Resolução:**

- Das equações paramétricas ($x=3+t, y=2-2t, z=-1+4t$):

1. $t = x-3$
2. $t = \frac{y-2}{-2}$
3. $t = \frac{z+1}{4}$

- Igualando as expressões:

**Resposta:**

1. $$\frac{x-3}{1} = \frac{y-2}{-2} = \frac{z+1}{4}$$

```

---

```ad-example

#### **03 ) -** Equação Simétrica da Reta por Dois Pontos
```

---
##### _Explicação do conceito_

```ad-quote
title: **Def**

- É um caso particular da equação simétrica. Se uma reta é definida por dois pontos distintos, $P_1(x_1, y_1, z_1)$ e $P_2(x_2, y_2, z_2)$, podemos usar um deles como o ponto de passagem (ex: $P_1$) e o vetor que os une, $v = \vec{P_1P_2} = (x_2-x_1, y_2-y_1, z_2-z_1)$, como o vetor diretor.
```

![[Pasted image 20250719175253.png]]
##### _Aplicabilidade_

```ad-quote
title: **Def**

- Ideal para quando a reta é definida por dois pontos no espaço, em vez de um ponto e uma direção. É uma forma direta de encontrar a equação da reta que conecta dois locais conhecidos.
```

> [!example] **Fórmula**

```ad-quote
title: **Def**

- Substituindo o ponto $P_1$ e o vetor diretor $\vec{P_1P_2}$ na fórmula da equação simétrica:

1. $$\frac{x-x_1}{x_2-x_1} = \frac{y-y_1}{y_2-y_1} = \frac{z-z_1}{z_2-z_1}$$
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Encontre a equação simétrica da reta que passa pelos pontos $P_1(2,4,−1)$ e $P_2(5,0,7)$.

---

**Resolução:**

- Ponto de passagem: $P_1(2,4,−1)$

- Vetor diretor: $v = (5-2, 0-4, 7-(-1)) = (3, -4, 8)$

**Resposta:**

1. $$\frac{x-2}{3} = \frac{y-4}{-4} = \frac{z+1}{8}$$

```

---

```ad-example

#### **04 ) -** Equação da Reta Determinada pela Interseção de Dois Planos
```

---
##### _Explicação do conceito_

```ad-quote
title: **Def**

- Uma reta no espaço tridimensional pode ser definida como o local geométrico onde dois planos não paralelos se cruzam. A equação da reta é, portanto, representada simultaneamente pelas equações gerais dos dois planos.
```

![[Pasted image 20250719175226.png]]
##### _Aplicabilidade_

```ad-quote
title: **Def**

- Usada em problemas de geometria e engenharia onde estruturas são definidas por faces planas que se encontram, como a aresta de um telhado ou o canto de uma sala.
```

> [!example] **Fórmula**

```ad-quote
title: **Def**

- A reta $r$ é representada pelo sistema de equações dos planos $\alpha_1$ e $\alpha_2$:

1. $$r:
\begin{cases}
\alpha_1: a_1x+b_1y+c_1z+d_1=0 \\
\alpha_2: a_2x+b_2y+c_2z+d_2=0
\end{cases}$$
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Encontre a equação paramétrica da reta *r* definida pela interseção dos planos:
  $$
  r:
  \begin{cases}
  x + y + z - 2 = 0 \\
  x + 3y - z - 2 = 0
  \end{cases}
  $$

---

**Resolução:**

- **Ponto de passagem:** 
  
1. Fazendo $y=0$ no sistema, encontramos o ponto $P(2, 0, 0)$.

- **Vetor diretor:** 
  
2. O vetor diretor $v$ é o produto vetorial dos vetores normais dos planos, $n_1(1,1,1)$ e $n_2(1,3,-1)$.
  $v = n_1 \times n_2 = (-4, 2, 2)$, que simplificamos para $v = (-2, 1, 1)$.

**Resposta:**

1. $$
   r:
   \begin{cases}
   x = 2 - 2t \\
   y = t \\
   z = t
   \end{cases}
   $$
```

---

```ad-example

#### **05 ) -** Equação Reduzida da Reta
```

---
##### _Explicação do conceito_

```ad-quote
title: **Def**

- A equação reduzida expressa duas das variáveis em função de uma terceira, chamada de **variável independente** (comumente $x$). Ela é obtida a partir da equação simétrica, desmembrando-a em duas igualdades separadas e isolando as variáveis.
```
##### _Aplicabilidade_

```ad-quote
title: **Def**

- Facilita a visualização das projeções da reta nos planos coordenados. Por exemplo, $y=p_1x+q_1$ é a projeção da reta no plano $xy$, e $z=p_2x+q_2$ é a projeção no plano $xz$.
```

> [!example] **Fórmula**

```ad-quote
title: **Def**

- Com $x$ como variável independente:

1. $$r:
\begin{cases}
y=p_1x+q_1 \\
z=p_2x+q_2
\end{cases}$$
```

> [!error] **Exemplo**

```ad-quote
title: **Def**

**Problema:**
- Encontre a equação reduzida da reta 
1. $$r: \frac{x-2}{2} = \frac{y-5}{3} = \frac{z-4}{1}$$

---

**Resolução:**

- Isolar $y$ em função de $x$:
1. $$\frac{x-2}{2} = \frac{y-5}{3} \implies 3(x-2) = 2(y-5) \implies$$ 
2. $$3x-6 = 2y-10 \implies 2y = 3x+4 \implies y = \frac{3}{2}x+2$$

- Isolar $z$ em função de $x$:
1. $$\frac{x-2}{2} = \frac{z-4}{1} \implies x-2 = 2(z-4) \implies $$ 
2. $$x-2 = 2z-8 \implies 2z = x+6 \implies z = \frac{1}{2}x+3$$

**Resposta:**

1. $$r:
\begin{cases}
y=\frac{3}{2}x+2 \\
z=\frac{1}{2}x+3
\end{cases}$$
```

---