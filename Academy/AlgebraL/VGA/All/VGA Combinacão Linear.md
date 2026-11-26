
---

```ad-quote
title: **Def**

Em um sistema de coordenadas cartesianas (como o plano ℝ² ou o espaço ℝ³), vetores são representados por suas componentes. Uma **combinação linear** de vetores é uma soma ponderada desses vetores, onde os pesos são escalares (números reais).
```

>[!quote] **YouTube:** [Combinação Linear](https://www.youtube.com/watch?v=sob2AS_sBKc&list=PLt9oVGXH7c4COFg9wZu2DjZ8X2JXZIO8r&index=5)

---
#### **01 )** - *Para que serve a Combinação Linear entre Vetores*

```ad-quote
title: **Def**

A combinação linear entre vetores é um conceito fundamental na álgebra linear e tem diversas utilidades e aplicações. Essencialmente, ela permite **criar novos vetores a partir de um conjunto existente**, escalonando-os (multiplicando por um número) e somando-os.
```

---
#### **02 )** -  Entendendo o Conceito

```ad-quote
title: **Def**

Geometricamente, uma combinação linear permite alcançar diferentes pontos ou direções no espaço.

* Com **um vetor**, as combinações lineares geram todos os vetores na mesma **linha** (todos os múltiplos escalares desse vetor).
* Com **dois vetores não colineares** (que não estão na mesma linha), as combinações lineares podem gerar qualquer vetor em um **plano**.
* Com **três vetores não coplanares** (que não estão no mesmo plano) em um espaço tridimensional, as combinações lineares podem gerar qualquer vetor nesse **espaço**.
```

---

```ad-example

#### **Linearidade L.D. / L.I.**
```

---

```ad-quote
title: **Def**

**Bases:** 
- Vetores LI são os blocos de construção para formar uma **base** de um espaço vetorial.

**Dimensão:** 
- O número de vetores em qualquer base para um espaço vetorial é a **dimensão** desse espaço.

**Soluções Únicas:** 
- A independência linear está relacionada à existência e unicidade de soluções em sistemas de equações lineares.

Em resumo:
* **LD = Redundância**: Pelo menos um vetor é uma combinação dos outros. 🔗
* **LI = Sem Redundância**: Cada vetor é essencial e adiciona uma nova direção. 🧱
```

---
#### **03 )** -  *Vetores Linearmente Dependentes / L.D.*

```ad-quote
title: **Def**

Um conjunto de vetores $\{v_1, v_2, \dots, v_n\}$ é dito **Linearmente Dependente** se existem escalares (números) $a_1, a_2, \dots, a_n$, onde pelo menos um deles não é zero, tais que:

1. $$c_1v_1 + c_2v_2 + \dots + c_nv_n = \vec{0}$$

**Obs:** Aqui, $\mathbf{0}$ representa o vetor nulo
```

![[Pasted image 20250601104319.png]]
###### ***O que isso significa na prática?***

```ad-quote
title: **Def**

Se um conjunto de vetores é LD, significa que: 
- **Pelo menos um dos vetores no conjunto pode ser expresso como uma combinação linear dos outros**. 
  
Em outras palavras, há uma "redundância" no conjunto; um dos vetores não adiciona uma nova "direção" ou informação que já não esteja contida nos outros.
```

> [!error] **Interpretação )** - *Geométrica:*

```ad-quote
title: **Def**

**Dois vetores LD:**
- Eles são **colineares**, ou seja, estão sobre a mesma linha (um é um múltiplo escalar do outro).
  
Exemplo: $v_1 = (1, 2)$ e $v_2 = (2, 4)$ são LD pois $v_2 = 2v_1$. (Equação: $2v_1 - v_2 = \mathbf{0}$)

---

**Três vetores LD (no espaço $\mathbb{R}^3$):**
- Eles são **coplanares**, ou seja, todos estão contidos no mesmo plano (quando suas origens coincidem).

Exemplo: $v_1 = (1, 0, 0)$, $v_2 = (0, 1, 0)$, e $v_3 = (2, 3, 0)$ são LD pois $v_3 = 2v_1 + 3v_2$.

---

**Caso especial:** 
- Qualquer conjunto de vetores que contenha o **vetor nulo** é automaticamente linearmente dependente.
```

> [!error] **Exemplo )** - *Completo:*

```ad-quote
title: **Def**

Consideremos os seguintes três vetores em $\mathbb{R}^3$:
* $v_1 = (1, 2, 1)$
* $v_2 = (1, 0, 1)$
* $v_3 = (3, 4, 3)$

**Verificação da Dependência Linear usando Matrizes:**
Procuramos escalares $c_1, c_2, c_3$, não todos nulos, tais que $c_1v_1 + c_2v_2 + c_3v_3 = \mathbf{0}$.
Podemos escrever isso como uma equação matricial $A\mathbf{c} = \mathbf{0}$, onde $A$ é a matriz cujas colunas são os vetores $v_1, v_2, v_3$, e $\mathbf{c}$ é o vetor coluna dos escalares:

1. $$A = \begin{pmatrix}
1 & 1 & 3 \\
2 & 0 & 4 \\
1 & 1 & 3
\end{pmatrix}, \quad
\mathbf{c} = \begin{pmatrix} c_1 \\ c_2 \\ c_3 \end{pmatrix}, \quad
\mathbf{0} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$$

A equação é:

2. $$\begin{pmatrix}
1 & 1 & 3 \\
2 & 0 & 4 \\
1 & 1 & 3
\end{pmatrix}
\begin{pmatrix} c_1 \\ c_2 \\ c_3 \end{pmatrix}
=
\begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$$

Para resolver este sistema homogêneo, formamos a matriz aumentada $[A|\mathbf{0}]$ e aplicamos a eliminação gaussiana:

3. $$\left[ \begin{array}{ccc|c}
1 & 1 & 3 & 0 \\
2 & 0 & 4 & 0 \\
1 & 1 & 3 & 0
\end{array} \right]$$

Aplicando operações de linha:
- $R_2 \leftarrow R_2 - 2R_1$
- $R_3 \leftarrow R_3 - R_1$

4. $$\left[ \begin{array}{ccc|c}
1 & 1 & 3 & 0 \\
0 & -2 & -2 & 0 \\
0 & 0 & 0 & 0
\end{array} \right]$$

Agora, podemos simplificar a segunda linha $R_2 \leftarrow R_2 / (-2)$:

5. $$\left[ \begin{array}{ccc|c}
1 & 1 & 3 & 0 \\
0 & 1 & 1 & 0 \\
0 & 0 & 0 & 0
\end{array} \right]$$

O sistema de equações correspondente é:
1. $c_1 + c_2 + 3c_3 = 0$
2. $c_2 + c_3 = 0$

Da equação (2), $c_2 = -c_3$.
Substituindo $c_2$ na equação (1): $c_1 + (-c_3) + 3c_3 = 0 \implies c_1 + 2c_3 = 0 \implies c_1 = -2c_3$.

Como a terceira coluna não possui um pivô, $c_3$ é uma variável livre. Seja $c_3 = t$.
Então, $c_1 = -2t$, $c_2 = -t$, $c_3 = t$.
Para qualquer valor de $t \neq 0$, obtemos uma solução não trivial. Por exemplo, se $t=1$:
$c_1 = -2$, $c_2 = -1$, $c_3 = 1$.

Como existem soluções não triviais (onde nem todos os $c_i$ são zero), os vetores $v_1, v_2, v_3$ são **linearmente dependentes**.

**Interpretação:**
Isso confirma que $v_3 = 2v_1 + v_2$. A presença de uma linha de zeros na forma escalonada da matriz $A$ (sem a coluna aumentada) indica que o determinante de $A$ é zero e que os vetores colunas são linearmente dependentes.

```

---
## Vetores Linearmente Independentes (LI)

```ad-quote
title: **Def**

Um conjunto de vetores $\{v_1, v_2, \dots, v_n\}$ é dito **linearmente independente** se a única maneira de a combinação linear deles resultar no vetor nulo é se **todos os escalares forem zero**:

$c_1v_1 + c_2v_2 + \dots + c_nv_n = \mathbf{0} \quad \text{implica que} \quad c_1 = c_2 = \dots = c_n = 0$
```
###### ***O que isso significa na prática?***

```ad-quote
title: **Def**

Se um conjunto de vetores é LI, significa que **nenhum vetor no conjunto pode ser expresso como uma combinação linear dos outros**. Cada vetor contribui com uma "direção" única e essencial para o espaço que eles geram.
```

![[Pasted image 20250601104523.png]]

> [!error] **Interpretação )** - *Geométrica:*

```ad-quote
title: **Def**

**Dois vetores LI:**
- Eles **não são colineares**. Apontam em direções diferentes.

Exemplo: $v_1 = (1, 0)$ e $v_2 = (0, 1)$ são LI.

---

**Três vetores LI (no espaço $\mathbb{R}^3$):**
- Eles **não são coplanares**. Juntos, podem "alcançar" qualquer ponto no espaço tridimensional.

Exemplo: Os vetores da base canônica $\mathbf{i}=(1,0,0)$, $\mathbf{j}=(0,1,0)$ e $\mathbf{k}=(0,0,1)$ são LI.
```

> [!error] **Exemplo )** - *Completo:*

```ad-quote
title: **Def**


Consideremos os seguintes três vetores em $\mathbb{R}^3$:
* $u_1 = (1, 0, 0)$
* $u_2 = (0, 1, 1)$
* $u_3 = (1, 1, 2)$

**Verificação da Independência Linear usando Matrizes:**
Testamos se a única solução para $c_1u_1 + c_2u_2 + c_3u_3 = \mathbf{0}$ é $c_1 = c_2 = c_3 = 0$.
A equação matricial é $B\mathbf{c} = \mathbf{0}$:


1. $$B = \begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
0 & 1 & 2
\end{pmatrix}, \quad
\mathbf{c} = \begin{pmatrix} c_1 \\ c_2 \\ c_3 \end{pmatrix}$$

A matriz aumentada é $[B|\mathbf{0}]$:

2. $$\left[ \begin{array}{ccc|c}
1 & 0 & 1 & 0 \\
0 & 1 & 1 & 0 \\
0 & 1 & 2 & 0
\end{array} \right]$$

Aplicando operações de linha:
- $R_3 \leftarrow R_3 - R_2$


2. $$\left[ \begin{array}{ccc|c}
1 & 0 & 1 & 0 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 0
\end{array} \right]$$

O sistema de equações correspondente é:
1. $c_1 + c_3 = 0$
2. $c_2 + c_3 = 0$
3. $c_3 = 0$

Da equação (3), $c_3 = 0$.
Substituindo $c_3=0$ na equação (2): $c_2 + 0 = 0 \implies c_2 = 0$.
Substituindo $c_3=0$ na equação (1): $c_1 + 0 = 0 \implies c_1 = 0$.

A única solução é $c_1 = 0, c_2 = 0, c_3 = 0$.

Portanto, os vetores $u_1, u_2, u_3$ são **linearmente independentes**.

**Interpretação:**
A forma escalonada da matriz $B$ possui um pivô em cada coluna correspondente aos vetores. Isso significa que o determinante de $B$ é não nulo e a única solução para $B\mathbf{c} = \mathbf{0}$ é a solução trivial $\mathbf{c} = \mathbf{0}$. Nenhum vetor pode ser expresso como combinação linear dos outros.
```

---

![[Pasted image 20250601100514.png]]

---

## Principais Utilidades e Conceitos Relacionados

A combinação linear é a base para entender vários conceitos cruciais em matemática e suas aplicações:

### 1. Espaço Gerado (Span) 🗺️
O conjunto de todas as combinações lineares possíveis de um conjunto de vetores é chamado de **espaço gerado** por esses vetores. Isso nos diz quais vetores podem ser "alcançados" ou "formados" a partir do conjunto original. Por exemplo, os vetores $\mathbf{i}=(1,0)$ e $\mathbf{j}=(0,1)$ geram todo o plano $\mathbb{R}^2$, pois qualquer vetor $(x,y)$ pode ser escrito como $x\mathbf{i} + y\mathbf{j}$.

### 2. Dependência e Independência Linear 🔗
* Um conjunto de vetores é **linearmente dependente** (LD) se pelo menos um deles pode ser escrito como uma combinação linear dos outros. Isso significa que há redundância no conjunto; um dos vetores não adiciona uma nova "direção" ou dimensão ao espaço gerado.
* Um conjunto de vetores é **linearmente independente** (LI) se nenhum vetor no conjunto pode ser expresso como uma combinação linear dos outros. Vetores LI são essenciais para formar uma "base".

### 3. Base de um Espaço Vetorial 🧱
Uma **base** de um espaço vetorial é um conjunto de vetores linearmente independentes que geram todo o espaço. Isso significa que qualquer vetor no espaço pode ser escrito como uma **combinação linear única** dos vetores da base. Pense neles como os "blocos de construção" fundamentais do espaço. Os vetores $\mathbf{i}, \mathbf{j}, \mathbf{k}$ formam a base canônica para o espaço tridimensional.

### 4. Sistemas de Equações Lineares ⚙️
Resolver um sistema de equações lineares é equivalente a encontrar os coeficientes (escalares) que permitem escrever um vetor como uma combinação linear de outros vetores. Por exemplo, o sistema:
$ax_1 + bx_2 = c$
$dx_1 + ex_2 = f$
Pode ser visto como tentar encontrar $x_1$ e $x_2$ tais que $x_1(a,d) + x_2(b,e) = (c,f)$.

---
#### **Definição Formal**

```ad-quote
title: **Def**

Dado um conjunto de vetores $\{\vec{v}_1, \vec{v}_2, ..., \vec{v}_k\}$ em $\mathbb{R}^n$ e escalares $\{a_1, a_2, ..., a_k\} \in \mathbb{R}$, uma **combinação linear** é:

$$
\vec{w} = \sum_{i=1}^k a_i \vec{v}_i = a_1 \vec{v}_1 + a_2 \vec{v}_2 + \cdots + a_k \vec{v}_k
$$

```
##### *Exemplo no $\mathbb{R}^2$*

```ad-quote
title: **Def**

**Vetores dados:**
$$
\vec{v}_1 = \begin{pmatrix} 1 \\ 2 \end{pmatrix}, \quad \vec{v}_2 = \begin{pmatrix} 3 \\ 1 \end{pmatrix}
$$

**Verificar se $\vec{b} = \begin{pmatrix} 7 \\ 8 \end{pmatrix}$ é combinação linear:**

1. Montar o sistema:
   $$
   \begin{cases}
   1a_1 + 3a_2 = 7 \\
   2a_1 + 1a_2 = 8
   \end{cases}
   $$

2. Solução matricial:
   $$
   \begin{pmatrix}
   1 & 3 \\
   2 & 1
   \end{pmatrix}
   \begin{pmatrix}
   a_1 \\
   a_2
   \end{pmatrix}
   =
   \begin{pmatrix}
   7 \\
   8
   \end{pmatrix}
   $$

3. Resultado:
   $$
   a_1 = \frac{17}{5}, \quad a_2 = \frac{6}{5}
   $$

**Conclusão:**  
$\vec{b} = \frac{17}{5}\vec{v}_1 + \frac{6}{5}\vec{v}_2$ é combinação linear 

```
##### *Exemplo no $\mathbb{R}^3$*

```ad-quote
title: **Def**

**Vetores dados:**
$$
\vec{v}_1 = \begin{pmatrix} 1 \\ 0 \\ 2 \end{pmatrix}, \quad \vec{v}_2 = \begin{pmatrix} 3 \\ 1 \\ -1 \end{pmatrix}, \quad \vec{v}_3 = \begin{pmatrix} 0 \\ 2 \\ 5 \end{pmatrix}
$$

**Verificar se $\vec{b} = \begin{pmatrix} 4 \\ 3 \\ 1 \end{pmatrix}$ é combinação linear:**

1. Sistema resultante:
   $$
   \begin{cases}
   1a_1 + 3a_2 + 0a_3 = 4 \\
   0a_1 + 1a_2 + 2a_3 = 3 \\
   2a_1 - 1a_2 + 5a_3 = 1
   \end{cases}
   $$

2. Solução:
   $$
   a_1 = -\frac{11}{19}, \quad a_2 = \frac{29}{19}, \quad a_3 = \frac{14}{19}
   $$

**Conclusão:**  
$\vec{b} = -\frac{11}{19}\vec{v}_1 + \frac{29}{19}\vec{v}_2 + \frac{14}{19}\vec{v}_3$ é combinação linear 
```

---