
---

```ad-quote
title:
###### Res 4.2 ) - Q1
```

Proposição:
- $A - (A \cap B) = A - B$

Prova ida:

Seja $x$ um elemento arbitrário pertencente a $A - (A \cap B)$.
1. Pela propriedade da subtração entre conjuntos, se $x \in A - (A \cap B)$ então $x \in A$ e $x \notin (A \cap B)$.
2. Pela lei de De Morgan, se $x \notin (A \cap B)$ então $x \notin A$ ou $x \notin B$.
3. Como já está demostrado que $x \in A$ na linha 1 temos que $x \notin B$.
4. Organizando os termos temos que $x \in A$ e $x \notin B$.
5. Pela propriedade de subtração entre conjuntos, se $x \in A$ e $x \notin B$, então $x \in A - B$.
6. Logo, está demonstrado que $A - (A \cap B) \subseteq A - B$

Prova Volta:

Seja $x$ um elemento arbitrário pertencente a $A - B$.
1. Pela propriedade da subtração entre conjuntos, se $x \in A - B$, então $x \in A$ e $x \notin B$.
2. Pela propriedade da intersecção entre conjuntos, se $x \notin B$, então $x \notin (A \cap B)$.
3. Pela propriedade da subtração entre conjuntos, se $x \in A$ e $x \notin (A \cap B)$, então $x \in A - (A \cap B)$.
4. Logo, está demonstrado que $A - B \subseteq A - (A \cap B)$.

Portanto, a proposição é verdadeira. 

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 4.2 ) - Q2
```

Proposição:
- $(A ∩ B) ∪ A = A$

Prova ida:

Seja $x$ um elemento arbitrário tal que $x \in (A \cap B) \cup A$. 
1. Pela definição de união, extraem-se duas hipóteses $x \in (A \cap B)$ ou $x \in A$. 
2. Caso 1: Se $x \in (A \cap B)$, infere-se pela definição de intersecção que $x \in A$ e $x \in B$. Logo, por simplificação lógica, $x \in A$.
3. Caso 2: Se $x \in A$, a afirmação satisfaz a condição trivialmente. 
4. Portanto, como nos dois casos $x \in A$, está provado que $(A ∩ B) ∪ A \subseteq A$.

Prova volta: 

Seja $x$ um elemento arbitrário tal que $x \in A$.
1. Pela regra da adição lógica, se $x \in A$, então $x \in (A \cap B)$ ou $x \in A$.
2. Pela definição de união, essa disjunção traduz-se em $x \in (A \cap B) \cup A$.
3. Portanto, está provado que $A \subseteq (A \cap B) \cup A$.

Dessa forma, como ambas as partes da igualdade foram provadas, a proposição é verdadeira.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 6 ) - Q1
```

Proposição 
- Sejam as funções $f: A \rightarrow B$ e $g: B \rightarrow C$. Se $f$ e $g$ são funções injetivas, então a função composta $(g \circ f): A \rightarrow C$ também é injetiva.

$Hip \ I$ - $f$ é injetiva.
$Hip \ II$ - $g$ é injetiva.

Supunha dois elementos arbitrários $x_1, x_2 \in A$ tal que $(g \circ f)(x_1) = (g \circ f)(x_2)$.
1. Pela propriedade de função composta podemos reescrever a expressão como $g(f(x_1)) = g(f(x_2))$.
2. Pela $Hip \ II$, como $g$ é injetiva, se $g(f(x_1)) = g(f(x_2))$, então $f(x_1) = f(x_2)$.
3. Pela $Hip \ I$, como $f$ é injetiva, se $f(x_1) = f(x_2)$, então $x_1 = x_2$.
4. Logo, partimos $(g \circ f)(x_1) = (g \circ f)(x_2)$ e chegamos que $x_1 = x_2$. Dessa forma, está provado que $(g \circ f): A \rightarrow C$ é uma função injetiva.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 6 ) - Q3
```

Proposição 
- Sejam as funções $f: A \rightarrow B$ e $g: B \rightarrow C$. Se $f$ e $g$ são sobrejetivas, então $(g \circ f)$ é sobrejetiva.

$Hip \ I$ - $f$ é sobrejetiva.
$Hip \ II$ - $g$ é sobrejetiva.

Suponha $y$ como um elemento arbitrário tal que $y \in C$.
1. $Hip \ II$, como $g$ é sobrejetiva, se $y \in C$, então existe um elemento $z \in B$ tal que $g(z) = y$.
2. $Hip \ I$, como $f$ é sobrejetiva, se $z \in B$, então existe um elemento $x \in A$ tal que $f(x) = z$.
3. Substituindo $z$ por $f(x)$ na primeira igualdade, obtemos $g(f(x)) = y$.
4. Pela propriedade da função composta, podemos reescrever a expressão $g(f(x))$ como $(g \circ f)(x)$. Logo, $(g \circ f)(x) = y$.
5. Portanto, partimos de um $y$ arbitrário pertencente a $C$ e encontramos um $x$ pertencente a $A$ que satisfaz a igualdade. Dessa forma, está provado que $(g \circ f)$ é sobrejetiva.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 15 ) - Q2 T4
```

Proposição
- $\overline{f^{−1}(C)} = f^{−1}(\overline{C})$

Prova ida

Seja $x$ um elemento arbitrário tal que $x \in \overline{f^{-1}(C)}$.
1. Pela definição de conjunto complementar, se $x \in \overline{f^{-1}(C)}$, então $x \notin f^{-1}(C)$.
2. Pela definição de imagem inversa, se a origem não pertence ao conjunto que atira para dentro de $C$, então o seu resultado não aterrissa lá. Logo, $f(x) \notin C$.
3. Pela definição de conjunto complementar, se $f(x) \notin C$, então $f(x) \in \overline{C}$.
4. Pela definição de imagem inversa, se o alvo atingido reside em $\overline{C}$, a sua origem matemática obrigatoriamente reside no agrupamento de retorno desse destino. Logo, $x \in f^{-1}(\overline{C})$.
5. Portanto, partimos de um elemento no primeiro agrupamento e atestamos a sua presença exata no segundo, provando definitivamente a inclusão $\overline{f^{-1}(C)} \subseteq f^{-1}(\overline{C})$.

Prova volta

Seja $x$ um elemento arbitrário tal que $x \in f^{-1}(\overline{C})$.
1. Pela definição de imagem inversa, se $x \in f^{-1}(\overline{C})$, então $f(x) \in \overline{C}$.
2. Pela definição de conjunto complementar, se $f(x) \in \overline{C}$, então $f(x) \notin C$.
3. Pela definição de imagem inversa, se $f(x) \notin C$, então $x \notin f^{-1}(C)$.
4. Pela definição de conjunto complementar, se $x \notin f^{-1}(C)$, então $x \in \overline{f^{-1}(C)}$.
5. Portanto, partimos de um elemento no primeiro agrupamento e atestamos a sua presença no segundo, provando definitivamente a inclusão $f^{-1}(\overline{C}) \subseteq \overline{f^{-1}(C)}$.

Logo, como a dupla inclusão foi provada a proposição inicial é verdadeira.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 15 ) - Q2 T5
```

Proposição
- Sejam $A$ e $B$ conjuntos quaisquer, $W$ e $Z$ subconjuntos de B e considere uma função qualquer $f : A → B$. Prove ou refute: $f^{-1}(W - Z) = f^{-1}(W) - f^{-1}(Z)$.

Prova ida

Seja $x$ um elemento arbitrário tal que $x \in f^{-1}(W - Z)$.
1. Pela propriedade da imagem inversa, se $x \in f^{-1}(W - Z)$, então $f(x) \in (W - Z)$.
2. Pela propriedade da subtração entre conjuntos, se $f(x) \in (W - Z)$, então $f(x) \in W \land f(x) \notin Z$.
3. Pela propriedade da imagem inversa, se $f(x) \in W \land f(x) \notin Z$, então $x \in f^{-1}(W) \land x \notin f^{-1}(Z)$.
4. Pela propriedade da subtração entre conjuntos, se $x \in f^{-1}(W) \land x \notin f^{-1}(Z)$, então $x \in f^{-1}(W) - f^{-1}(Z)$.
5. Logo, está demonstrado que $f^{-1}(W - Z) \subseteq f^{-1}(W) - f^{-1}(Z)$

Prova volta

Seja $x$ um elemento arbitrário tal que $x \in f^{-1}(W) - f^{-1}(Z)$.
1. Pela propriedade da subtração entre conjuntos, se $x \in f^{-1}(W) - f^{-1}(Z)$, então $x \in f^{-1}(W) \land x \notin f^{-1}(Z)$.
2. Pela propriedade da imagem inversa, se $x \in f^{-1}(W) \land x \notin f^{-1}(Z)$, então $f(x) \in W \land f(x) \notin Z$.
3. Pela propriedade da subtração entre conjuntos, se $f(x) \in W \land f(x) \notin Z$, então $f(x) \in W - Z$.
4. Pela propriedade da imagem inversa, se $f(x) \in W - Z$, então $x \in f^{-1}(W - Z)$.
5. 5. Logo, está demonstrado que $f^{-1}(W) - f^{-1}(Z) \subseteq f^{-1}(W - Z)$.

Portanto, como ambas as partes da igualde foram demostradas, a proposição é válida.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 15 ) - Q2 T6
```

Proposição
- Sejam $A$ e $B$ conjuntos quaisquer, $W$ e $Z$ subconjuntos de B e considere uma função qualquer $f : A → B$. Prove ou refute: $f(f^{-1}(W)) = W \cap f(A)$.

Prova ida

Seja $y$ um elemento arbitrário tal que $y \in f(f^{-1}(W))$.
1. Pela definição de imagem, se $y \in f(f^{-1}(W))$, então existe um elemento $x \in f^{-1}(W)$ tal que $f(x) = y$.
2. Pela propriedade da imagem inversa o conjunto $f^{-1}(W) \in A$, temos que $x \in A$.  
3. Pela propriedade da imagem inversa, se $x \in f^{-1}(W)$, então $f(x) \in W$. Como $f(x) = y$, temos que $y \in W$.
4. Uma vez que $x \in A$, pela definição de imagem $f(x) \in f(A)$. Como $f(x) = y$, temos que $y \in f(A)$.
5. Portanto, $y \in W \land y \in f(A)$.
6. Pela propriedade da intersecção entre conjuntos, se $y \in W \land y \in f(A)$, então $y \in W \cap f(A)$.
7. Logo, está demonstrado que $f(f^{-1}(W)) \subseteq W \cap f(A)$.

Prova volta

Suponha $y$ como um elemento arbitrário tal que $y \in W \cap f(A)$.
1. Pela propriedade da interseção entre conjuntos, se $y \in W \cap f(A)$, então $y \in W$ e $y \in f(A)$.
2. Como $y \in f(A)$, a definição de imagem direta garante que existe uma origem $x \in A$ tal que $f(x) = y$.
3. Como atestamos que $f(x) = y$ e sabemos que $y \in W$, a substituição direta prova que $f(x) \in W$.
4. Pela propriedade da imagem inversa, se o alvo $f(x)$ atinge o conjunto $W$, a sua origem obrigatoriamente mora no agrupamento de retorno. Logo, $x \in f^{-1}(W)$.
5. Pela definição de imagem, se a origem $x$ pertence ao agrupamento $f^{-1}(W)$, o seu destino obrigatoriamente habitará a imagem desse conjunto. Isso significa que $f(x) \in f(f^{-1}(W))$.
6. Como $f(x) = y$, a substituição final atesta que $y \in f(f^{-1}(W))$.
7. Logo, a inclusão $W \cap f(A) \subseteq f(f^{-1}(W))$ está demonstrada com sucesso.

Portanto, como ambas as partes da igualde foram demostradas, a proposição é válida.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 15 ) - Q2 T7
```

Proposição
- Sejam $A$ e $B$ conjuntos quaisquer, $W$ e $Z$ subconjuntos de B e considere uma função qualquer $f : A → B$. Prove ou refute se $C \subseteq A$ então $C \subseteq f^{-1}(f(C))$.

$Hip \ I$ - $C \subseteq A$.

Seja $x$ um elemento arbitrário tal que $x \in C$.
1. Pela definição de imagem, se $x \in C$, então $f(x) \in f(C)$.
2. Como pela $Hip \ I, \ C \subseteq A$. Temos que pela definição de imagem inversa, se $f(x) \in f(C)$, então $x \in f^{-1}(f(C))$.
3. Logo, está provado que $C \subseteq f^{-1}(f(C))$

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 15 ) - Q6 LA
```

Para a sequência {$2,4,8,16,...$} ache a fórmula recursiva, fechada e prove a fórmula fechada por indução.

Fórmula recursiva:
- $a_1 = 2, a_n = a_{n-1} \cdot 2$; para todo $n \geq 2$.

Fórmula fechada
- $f(n) = 2 \cdot 2^{n-1} \Rightarrow 2^n$

Prova por indução

Caso base:

- Substituindo $n$ por 1 para testar o caso base da fórmula fechada temos que

$$2^n = 2^1 = 2 = a_1$$

- Logo, temos que a fórmula fechada foi validada pelo caso base.

Hipótese da indução:

- Suponha que a fórmula seja válida para algum inteiro $k \ge 1$.

$$a_k = 2^k$$

Passo indutivo:

- Partindo da forma recursiva e avaliando para um $k+1$

$$a_{k + 1} = a_k \cdot 2$$

- Substituímos o termo $a_k$ pela nossa Hipótese de Indução

$$a_{k + 1} = 2^k \cdot 2$$
$$a_{k + 1} = 2^{k+1}$$

Dessa forma, a fórmula fechada está provada para qualquer $k + 1$.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Res 15 ) - Q6 LC
```

Para a sequência {$1, 2, 6, 24, 120, 720, . . .$} ache a fórmula recursiva, fechada e prove a fórmula fechada por indução.

Fórmula recursiva:
-  $a_n = a_{n-1} \cdot n$

Fórmula fechada
- $f(n) = n!$

---


---

```ad-done
title:  

#### Fase 02 ) - Lista
```

---

```ad-quote
title:
###### List ) - Q2 - LB
```

Proposição
$$f(x) = \begin{cases} x^2 + 3x & \text{se } x \geq 0 \\ \frac{3x}{2} & \text{se } x < 0 \end{cases}$$
Prova injetividade

Para provar a injetividade devemos demonstrar que a igualdade das imagens resulta na igualdade do domínio. Portanto, suponha que $f(x_1) = f(x_2)$.

Para $x \ge$ 0.

$$f(x_1) = f(x_2)$$
$$\Rightarrow x_1^2 + 3x_1 = x_2^2 + 3x_2$$
$$\Rightarrow x_1^2 + 3x_1 - x_2^2 - 3x_2 = 0$$
$$\Rightarrow x_1^2 - x_2^2 + 3x_1 - 3x_2 = 0$$
$$\Rightarrow (x_1 - x_2)(x_1 + x_2) + 3(x_1 - x_2)= 0$$
$$\Rightarrow (x_1 - x_2)(x_1 + x_2 + 3) = 0$$

Como $x_1 \geq 0$ e $x_2 \geq 0$, o termo $(x_1 + x_2 + 3)$ é maior ou igual a $3$, logo nunca será zero. Para que o produto seja nulo, o primeiro fator deve ser zero:

$$x_1 - x_2 = 0 \implies x_1 = x_2$$
Para $x <$ 0.

$$f(x_1) = f(x_2)$$
$$\Rightarrow \frac{3x_1}{2} = \frac{3x_2}{2}$$
$$\Rightarrow \frac{3x_1}{2} \cdot2 = \frac{3x_2}{2} \cdot2$$
$$\Rightarrow 3x_1 = 3x_2$$
$$\Rightarrow \frac{3x_1}{3} = \frac{3x_2}{3}$$
$$\Rightarrow x_1 = x_2$$

Logo, está provado que a função $f$ é injetiva.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Gemini
```

Seja a função $f: [-2, +\infty) \rightarrow [1, +\infty)$ definida pela equação:

$$f(x) = x^2 + 4x + 5$$

Para provar a injetividade da função $f$ devemos demostrar que a igualdade das imagens resulta na igualdade do domínio. Portanto, suponha que $f(x_1) = f(x_2)$.

$$f(x_1) = f(x_2)$$
$$\Rightarrow x_1^2 + 4x_1 + 5 = x_2^2 + 4x_2 + 5$$
$$\Rightarrow x_1^2 - x_2^2 - 4x_2 + 4x_1 = 0$$
$$\Rightarrow (x_1 - x_2)(x_1 + x_2) + 4(x_1 - x_2) = 0$$
$$\Rightarrow (x_1 - x_2)(x_1 + x_2 + 4) = 0$$

Como $x_1 \geq 0$ e $x_2 \geq 0$, o termo $(x_1 + x_2 + 4)$ é maior ou igual a $3$, logo nunca será zero. Para que o produto seja nulo, o primeiro fator deve ser zero:

$$x_1 - x_2 = 0 \implies x_1 = x_2$$

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q07
```

Proposição
- Seja $f : A \to B$ e $X, Y \subseteq A$. Prove ou refute $f(X \cup Y) = f(X) \cup f(Y)$.

- $Hip \ I$ - $f : A \to B$
- $Hip \ II$ - $X, Y \subseteq A$

Prova ida

Seja $y$ um elemento arbitrário tal que $y \in f(X \cup Y)$. 
1. Pela definição de imagem de um conjunto, existe um $x \in X \cup Y$ tal que $f(x) = y$. 
2. Pela definição de união, se $x \in X \cup Y$, então $x \in X$ ou $x \in Y$. 
3. Como $f(x) = y$, pela definição de imagem de um conjunto que, se $x \in X$ então $y \in f(X)$, e se $x \in Y$ então $y \in f(Y)$. 
4. Logo, conclui-se que $y \in f(X)$ ou $y \in f(Y)$. Pela definição de união, a disjunção obtida traduz-se em $y \in f(X) \cup f(Y)$. Portanto, está demonstrado que $f(X \cup Y) \subseteq f(X) \cup f(Y)$.

Prova volta

Seja $y$ um elemento arbitrário tal que $y \in f(X) \cup f(Y)$.

1. Pela definição de união, $y \in f(X)$ ou $y \in f(Y)$.
2. Caso 1: Se $y \in f(X)$, pela definição de imagem existe $x \in X$ tal que $f(x) = y$. Pela adição lógica, como $x \in X$, conclui-se que $x \in X \cup Y$.
3. Caso 2: Se $y \in f(Y)$, pela definição de imagem, existe $x \in Y$ tal que $f(x) = y$. Pela adição lógica, como $x \in Y$, conclui-se que $x \in X \cup Y$.
4. Como em ambos os cenários existe $x \in X \cup Y$ tal que $f(x) = y$, infere-se pela definição de imagem que $y \in f(X \cup Y)$.
5. Logo, $f(X) \cup f(Y) \subseteq f(X \cup Y)$.

Conclusão

- Com a garantia de que $f(X \cup Y) \subseteq f(X) \cup f(Y)$ provada na ida, e $f(X) \cup f(Y) \subseteq f(X \cup Y)$ provada na volta, a exigência de dupla continência foi atendida. Logo, $f(X \cup Y) = f(X) \cup f(Y)$.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q10
```

Proposição
- Sejam $A$, $B$, $C$ e $D$ conjuntos quaisquer. Demostre, ou refute $(A \cup C) \times (B \cup D) \subseteq (A \times B) \cup (C \times D)$

Seja $(x,y)$ um par ordenado arbitrário tal que $(x,y) \in (A \cup C) \times (B \cup D)$.
1. $x \in (A \cup C)$ e $y \in (B \cup D)$. (Produto cartesiano)
2. $(x \in A$ ou $x \in C)$ e $(y \in B$ ou $y \in D)$. (União de conjuntos)
3. $((x \in A$ ou $x \in C)$ e $y \in B$) ou  $((x \in A$ ou $x \in C)$ e $y \in D$) (Distributividade)
4. $((x \in A$ e $y \in B$) ou ($x \in C$ e $y \in B$)) ou (($x \in A$ e $y \in D$) ou $(x \in C$ e $y \in D))$ (Distributividade)
5. $(x,y) \in (A \times B) \cup (C \times B) \cup (A \times D) \cup (C \times D)$ 

---

Assuma as seguintes definições arbitrárias pontuais:
- $A = \{1\}$
- $B = \emptyset$
- $C = \emptyset$
- $D = \{2\}$
Aplicando as definições ao lado esquerdo da proposição original:
5. $A \cup C = \{1\}$
6. $B \cup D = \{2\}$
7. $(A \cup C) \times (B \cup D) = \{(1, 2)\}$
Aplicando as definições ao lado direito da proposição original:
8. $A \times B = \emptyset$
9. $C \times D = \emptyset$
10. $(A \times B) \cup (C \times D) = \emptyset$
O passo final:
- $\{(1, 2)\} \not\subseteq \emptyset$

A proposição está refutada.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q11
```

Proposição
- Sejam $A, B$ e $C$ conjuntos quaisquer. Demonstre que: Se $A \subseteq C$, então $A \cup (B \cap C) = (A \cup B) \cap C$.

- $Hip \ I$ - $A \subseteq C$.

Prova da Ida

Seja $x$ um elemento arbitrário tal que $x \in A \cup (B \cap C)$.
1. Pela definição de união e intersecção, $x \in A \lor (x \in B \land x \in C)$.
2. Pela propriedade da distributividade, $(x \in A \lor x \in B) \land (x \in A \lor x \in C)$.
3. Pela $Hip \ I$ ($A \subseteq C$), se $x \in A$, então $x \in C$. Logo, a disjunção $(x \in A \lor x \in C)$ reduz-se para $x \in C$.
4. Substituindo o termo na expressão principal, temos que $(x \in A \lor x \in B) \land x \in C$.
5. Pela propriedade da união e intersecção, $x \in (A \cup B) \cap C$.
6. Portanto, está provado que $A \cup (B \cap C) \subseteq (A \cup B) \cap C$.

Prova da Volta

Seja $x$ um elemento arbitrário tal que $x \in (A \cup B) \cap C$.
1. Pela propriedade da intersecção, $x \in (A \cup B) \land x \in C$.
2. Pela propriedade da união, $(x \in A \lor x \in B) \land x \in C$.
3. Pela propriedade da distributividade, $(x \in A \land x \in C) \lor (x \in B \land x \in C)$.
4. Pela $Hip \ I$ ($A \subseteq C$), se $x \in A$, então $x \in C$. Logo, a conjunção $(x \in A \land x \in C)$ simplifica-se para $x \in A$.
5. Substituindo o termo na expressão principal, temos que $x \in A \lor (x \in B \land x \in C)$.
6. Pela propriedade da intersecção e união, $x \in A \cup (B \cap C)$.
7. Portanto, está provado que $(A \cup B) \cap C \subseteq A \cup (B \cap C)$.

Conclusão
- Dessa forma, como ambas as partes da igualdade foram provadas, a proposição é verdadeira.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q12
```

Proposição
- Sejam $A$, $B$ e $C$ conjuntos. Demostre ou refute se $A \subseteq B$ e $A \cap B = \varnothing$, então $A \subseteq (B - C)$. 

- $Hip \ I$ - $A \subseteq B$.
- $Hip \ II$ - $A \cap B = \varnothing$.

Prova
1. Pela $Hip \ I$ ($A \subseteq B$), sabe-se pela propriedade da intersecção que $A \cap B = A$. 
2. Substituindo essa igualdade na $Hip \ II$ ($A \cap B = \emptyset$), obtém-se diretamente que $A = \emptyset$. 
3. Pela propriedade de vacuidade do conjunto vazio, sabe-se que o conjunto vazio é subconjunto de qualquer conjunto ($\forall M, \emptyset \subseteq M$). 
4. Logo, como $A = \emptyset$, conclui-se diretamente que $A \subseteq (B - C)$. Portanto, a proposição é verdadeira.


---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q13 - LA
```

Proposição

Proposição: Dada uma função _injetiva_ $f: U \to U$, com os subconjuntos $C, D \subseteq \text{Dom}(f)$, demonstre que $f(D) \subseteq f(C) \implies D \subseteq C$.

- $Hip \ I$ - $C, D \subseteq \text{Dom}(f)$ e $f$ é uma função _injetiva_.
- $Hip \ II$ - $f(D) \subseteq f(C)$.

Seja $x$ um elemento arbitrário tal que $x \in D$.

1. Por definição da imagem de um conjunto, ao aplicar a função $f$ ao elemento $x \in D$, tem-se que $f(x) \in f(D)$.
2. Pela Hipótese II, é dado que $f(D) \subseteq f(C)$. Portanto, a partir da constatação de que $f(x) \in f(D)$, resulta logicamente que $f(x) \in f(C)$.
3. Pela definição de imagem aplicada ao conjunto $C$, a condição $f(x) \in f(C)$ implica a existência de pelo menos um elemento $z \in C$ tal que $f(z) = f(x)$.
4. Pela Hipótese I, a função $f$ possui a propriedade _injetiva_. A definição matemática formal de injetividade dita que se as imagens de dois elementos são iguais, os elementos de origem no domínio correspondentes devem ser estritamente idênticos. Logo, uma vez que $f(z) = f(x)$, deduz-se obrigatoriamente que $z = x$.
5. Como $z \in C$ e $z = x$ foi comprovada, conclui-se por substituição que $x \in C$.
6. A premissa inicial tomou um elemento arbitrário $x \in D$ e a dedução lógica chegou à conclusão de que este mesmo $x \in C$. Isso satisfaz a definição formal de subconjunto, provando que $D \subseteq C$.
7. A demonstração está concluída. A implicação $f(D) \subseteq f(C) \implies D \subseteq C$ é verdadeira sob a exigência estrutural de que $f$ seja _injetiva_.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q13 - LB
```

Proposição

- Dada uma função _injetiva_ $f: U \to U$, com os subconjuntos $C, D \subseteq \text{Dom}(f)$, demonstre que $D \subseteq C \implies f(D) \subseteq f(C)$.

- $Hip \ I$ - $C, D \subseteq \text{Dom}(f)$ e $f$ é uma função _injetiva_.
- $Hip \ II$ - $D \subseteq C$.

Seja $y$ um elemento arbitrário tal que $y \in f(D)$.
1. Por definição de imagem, a condição $y \in f(D)$ implica que existe pelo menos um elemento $x \in D$ tal que $f(x) = y$.
2. Pela Hipótese II, é dado que $D \subseteq C$. Pela definição de subconjunto, uma vez que $x \in D$, conclui-se diretamente que $x \in C$.
3. Por definição da imagem do conjunto $C$, a constatação de que $x \in C$ garante que a imagem mapeada $f(x)$ pertence ao conjunto $f(C)$. Logo, $f(x) \in f(C)$.
4. Como foi estabelecido no segundo passo que $f(x) = y$, aplica-se a substituição para concluir que $y \in f(C)$.
5. Partiu-se da premissa de um elemento arbitrário $y \in f(D)$ e a dedução lógica demonstrou que este mesmo elemento cumpre $y \in f(C)$. Isso satisfaz integralmente a definição de subconjunto.
6. Logo, está demonstrado que $D \subseteq C \implies f(D) \subseteq f(C)$.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q14
```

A afirmação é falsa.

Considere os conjuntos $A = \{1\}$, $B = \{2\}$ e $C = \{1\}$.

Lado esquerdo
1. $B \cap C = \emptyset$, logo $A \times (B \cap C) = \emptyset$.
Lado direito
2. $A \times B = \{(1, 2)\}$ e $C \times B = \{(1, 2)\}$, logo a interseção $(A \times B) \cap (C \times B) = \{(1, 2)\}$.

Como $\emptyset \neq \{(1, 2)\}$, a igualdade não se sustenta. A propriedade distributiva correta é $A \times (B \cap C) = (A \times B) \cap (A \times C)$.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q15 - LA
```

Seja $f: A \to B$ e $W, Z \subseteq B$. Demostre que $f^{-1}(W \cap Z) = f^{-1}(W) \cap f^{-1}(Z)$.

Prova ida $f^{-1}(W \cap Z) \subseteq f^{-1}(W) \cap f^{-1}(Z)$

Suponha um elemento arbitrário $x$ tal que $x \in f^{-1}(W \cap Z)$.
1. Pela definição de imagem inversa, temos que $f(x) \in (W \cap Z)$.
2. Pela definição de intersecção entre conjuntos, isso implica que $f(x) \in W \land f(x) \in Z$.
3. Como $f(x) \in W$, a definição de imagem inversa garante que $x \in f^{-1}(W)$.
4. Como $f(x) \in Z$, a definição de imagem inversa garante que $x \in f^{-1}(Z)$.
5. Portanto, pela definição de intersecção, concluímos que $x \in f^{-1}(W) \cap f^{-1}(Z)$.

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q16 
```

Considere a sequência 5, 13, 29, 61, 125... Ache a fórmula recursiva, e a fórmula fechada. Prove a fórmula fechada por indução.

Fórmula recursiva
$$a_1 = 5$$
$$a_n = (a_{n-1} \cdot 2) + 3$$
Fórmula fechada

$$a_n = a_1 \cdot q^{n-1} + c \cdot \frac{q^{n-1} - 1}{q - 1}$$
$$a_n = 5 \cdot 2^{n-1} + 3 \cdot \frac{2^{n-1} - 1}{1}$$
$$a_n = 5 \cdot 2^{n-1} + 3 \cdot (2^{n-1} - 1)$$
$$a_n = 5 \cdot 2^{n-1} + 3 \cdot 2^{n-1} - 3$$
$$a_n = 8 \cdot 2^{n-1} - 3$$
$$a_n = 2^{n+2} - 3$$
Prova por indução
- Caso base para $n = 1$

$$f(n) = 2^{n+2}-3$$
$$\Rightarrow f(1) = 2^{1+2}-3$$
$$\Rightarrow f(1) = 2^{3}-3$$
$$\Rightarrow f(1) = 8-3$$
$$\Rightarrow f(1) = 5$$

Hipótese da indução
- Suponha que a fórmula fechada seja válida para algum inteiro $k \geq 1$. Logo
$$a_k = 2^{k+2}-3$$
Passo indutivo
- Para o passo indutivo, expandimos o termo $a_{k+1}$ via recorrência
$$a_{k+1} = (a_{k} \cdot 2) +3$$
- Substituindo o termo $a_k$ pela hipótese de indução
$$a_{k+1} = ((2^{k+2}-3) \cdot 2)+3$$
$$\Rightarrow a_{k+1} = ((2^{k+2}-3) \cdot 2)+3$$
$$\Rightarrow a_{k+1} = 2 \cdot 2^{k+2}-6+3$$
$$\Rightarrow a_{k+1} = 2^{2(k+1)}-3$$
Logo, está provado que a fórmula fechada é válida para qualquer $n \geq 1$.
 

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q17 
```

Gael comprou um saquinho com jujubas vermelhas, laranjas, amarelas, verdes e roxas, com 8 de cada cor. Ele tirava e comia as jujubas uma a uma de forma aleatória, sem reposição. Com base nessa situação hipotética, qual é o número mínimo de jujubas que ele precisa comer para garantir que terminou todas as jujubas de uma mesma cor?

Resolução

- Tipo 2 - Repetição de k Elementos

$P = C \cdot (k - 1) +1$
=>$5 \cdot (8 - 1) + 1$
=>$5 \cdot 7 + 1$
=> $36$

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q18
```

Em uma escola, as notas dos alunos em cada disciplina são atribuídas por meio dos conceitos A, B, C, D e E, sendo A o melhor conceito e E o pior. Qual é o número mínimo de alunos que uma turma deve ter para que seja possível garantir que nela haja pelo menos sete alunos com o mesmo conceito em uma disciplina específica?

Resolução:

- Tipo 2 - Repetição de k Elementos

5 Categorias.

$P = C \cdot (k - 1) + 1$

=> $5 \cdot (7 - 1) + 1$
=> $5 \cdot 6 + 1$
=> $31$

---

> [!done] **_New_**

---

```ad-quote
title:
###### List ) - Q19
```

Em determinada livraria, os exemplares recém-adquiridos foram marcados com identificações numéricas de 25 a 91, todas distintas. Cada identificação pertence a um único exemplar. Qual é a menor quantidade de exemplares que precisa ser escolhida para assegurar que, entre eles, pelo menos dois possuam números sucessivos

Resolução

- Tipo 1 - Garantia de um Par

- Para garantir que dois números sejam sucessivos, o segredo é tentar criar o pior cenário possível sem que nenhum se toque. Separamos os 67 números em 33 pares consecutivos: (25, 26), (27, 28) até (89, 90), sobrando o 91 sozinho. Isso resulta em 34 grupos isolados. Se pegarmos um livro de cada um desses grupos, teremos 34 livros sem nenhum sucessivo. O próximo livro que você escolher (o 35º) vai obrigatoriamente repetir um grupo e formar um par consecutivo.

$C = 34$
$P = C + 1$
=> $P = 34 + 1$
=> $P = 35$

---

```ad-done
title:  

#### Fase 03 ) - Prova
```

---

```ad-quote
title:
###### Prov T ) - Q1
```

Considere uma função qualquer $f: A \to B, C, D \subseteq A$ e $W, Z \subseteq B$. Prove ou refute que se $f$ for injetiva, então $f(C) \cap f(D) \subseteq f(C \cap D)$.

Seja $y$ um elemento arbitrário tal que $y \in f(C) \cap f(D)$. 
1. Pela definição de intersecção entre conjuntos, se $y \in f(C) \cap f(D)$, então $y \in f(C) \land y \in f(D)$.
2. Pela definição de imagem, se $y \in f(C)$, então existe um $x_1 \in C$ tal que $f(x_1) = y$.
3. Pela definição de imagem, se $y \in f(D)$, então existe um $x_2 \in D$ tal que $f(x_2) = y$.
4. Por hipótese, $f$ é um função injetiva. Portanto, como $f(x_1) = y \land f(x_2) = y$, temos que $f(x_1) = f(x_2)$. Dessa forma, como a igualdade das imagens resulta na igualdade nos elementos pela função injetiva temos que $x_1 = x_2$. Vamos chamar tanto $x_1$ quanto $x_2$ de apenas $x$.
5. Logo, $x \in C \land x \in D$.
6. Pela definição de intersecção, se $x \in C \land x \in D$, então $x \in C  \cap D$.
7. Pela definição de imagem, se $x \in C  \cap D$, então $f(x) \in f(C \cap D)$.
8. Como $f(x) \in f(C \cap D)$ e $f(x) = y$, temos que $y \in f(C \cap D)$. 
9. Portanto, está provado que $f(C) \cap f(D) \subseteq f(C \cap D)$.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Prov T ) - Q3
```

Mostre que a função $f$ é sobrejetiva.
$$f(x) = \begin{cases} x^2 + 3x & \text{se } x \geq 0 \\ \frac{3x}{2} & \text{se } x < 0 \end{cases}$$





---

> [!done] **_New_**

---

```ad-quote
title:
###### Prov M ) - Q1
```

Considere a sequência $\{5, 8, 11, 14, 17 \dots\}$. Encontre uma forma recursiva e uma forma fechada que descreva $a_n$. Prove por indução que a fórmula fechada que você encontrou está correta.

Fórmula recursiva
- $a_n = a_{n-1} + 3$.

Fórmula fechada
- $f(n) = 5 + 3(n - 1) = 5 + 3n -3 = 3n + 2$

Prova por indução

Caso base
- Substituindo $n$ por $1$ visando provar o caso base

$$f(1) = 3(1) + 2 = 5 = a_1$$
Hipótese indutiva
- Suponha que a fórmula fechada seja válida para algum inteiro $k \geq 1$

$$a_k = 3k + 2$$

Passo indutivo
- Para o passo indutivo, expandimos o termo $a_{k+1}$ via recorrência

$$a_{k+1} = a_{k}  + 3$$

- Substituímos o termo $a_k$ pela nossa Hipótese de Indução

$$a_{k+1} = (3k + 2) + 3$$
$$a_{k+1} = (3k + 3) + 2$$
$$a_{k+1} = 3(k + 1) + 2$$
Portanto, está provado a fórmula fechada por indução.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Prov M ) - Q4
```

Um almoxarifado possui 60 caixas, cada uma contendo parafusos de apenas uma cor. Sabe-se que 23 caixas contêm parafusos prateados; 18 contêm parafusos pretos; 8 contêm parafusos verdes; e o restante contém parafusos dourados. Com base nessas informações, qual é o número mínimo de caixas que devem ser retiradas, aleatoriamente, para garantir que haja ao menos uma caixa de cada cor?

23 - 1 = 22
18 - 1 = 17
8 - 1 = 7
11 - 1 = 10

---

```ad-done
title:  

#### Fase 04 ) - Extra
```

---

```ad-quote
title:
###### Extra ) - 1
```

Seja $y$ um elemento arbitrário pertencente ao contradomínio $\mathbb{R} \setminus \{3\}$.

Para que a função seja _sobrejetiva_, deve existir um $x \in \mathbb{R} \setminus \{2\}$ tal que $f(x) = y$.

Iniciamos o isolamento da variável igualando a lei de formação a $y$:

$$\frac{3x+1}{x-2} = y$$

$$3x+1 = y(x-2)$$

$$3x+1 = xy - 2y$$

$$3x - xy = -2y - 1$$

$$x(3-y) = -2y - 1$$

Isolando o $x$ e multiplicando o numerador e o denominador por $-1$ para simplificar os sinais, obtemos:

$$x = \frac{2y+1}{y-3}$$

Como $y \neq 3$ pela restrição do contradomínio, o denominador da fração nunca será zero. Isso garante que o valor de $x$ gerado seja sempre um número real.

Por fim, é necessário testar se esse $x$ gerado obedece à restrição do domínio. Se assumirmos por absurdo que a fração resulta no valor proibido $2$, teremos o seguinte cenário:

$$\frac{2y+1}{y-3} = 2$$

$$2y+1 = 2(y-3)$$

$$2y+1 = 2y-6$$

$$1 = -6$$

Como a afirmação $1 = -6$ é uma contradição matemática insustentável, deduzimos obrigatoriamente que $x \neq 2$. Isso atesta que o elemento gerado pertence ao domínio válido $\mathbb{R} \setminus \{2\}$.

Como para qualquer $y$ arbitrário dentro do contradomínio foi possível encontrar um $x$ correspondente e perfeitamente válido no domínio, está formalmente provado que a função é _sobrejetiva_.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Extra ) - 2
```

**Prova de Injetividade**

Para provar que a função é _injetiva_, devemos demonstrar que $f(x_1) = f(x_2)$ implica necessariamente que $x_1 = x_2$.

$$f(x_1) = f(x_2)$$

$$x_1^2 - 2x_1 - 3 = x_2^2 - 2x_2 - 3$$

$$x_1^2 - x_2^2 - 2x_1 + 2x_2 = 0$$

$$(x_1 - x_2)(x_1 + x_2) - 2(x_1 - x_2) = 0$$

$$(x_1 - x_2)(x_1 + x_2 - 2) = 0$$

Temos o produto de dois fatores resultando em zero. Como o domínio da função é o intervalo $[1, +\infty)$, sabemos que $x_1 \ge 1$ e $x_2 \ge 1$. Isso significa que a soma $x_1 + x_2$ sempre será maior ou igual a $2$.

Consequentemente, o termo $(x_1 + x_2 - 2)$ será sempre maior ou igual a zero. Ele assumirá o valor zero apenas na situação extrema onde $x_1 = 1$ e $x_2 = 1$, um cenário que já satisfaz a condição $x_1 = x_2$. Para qualquer outro valor numérico do domínio, esse fator será estritamente positivo. Isso nos obriga a assumir que o outro fator deve ser obrigatoriamente nulo para zerar a equação:

$$x_1 - x_2 = 0$$

$$x_1 = x_2$$

Portanto, a função é comprovadamente _injetiva_.

**Prova de Sobrejetividade**

Para provar que a função é _sobrejetiva_, devemos demonstrar que, para todo elemento arbitrário $y$ pertencente ao contradomínio $[-4, +\infty)$, existe um elemento $x$ válido no domínio $[1, +\infty)$ tal que $f(x) = y$.

Iniciamos o processo igualando a lei de formação a $y$:

$$x^2 - 2x - 3 = y$$

$$x^2 - 2x - (3 + y) = 0$$

Aplicamos a fórmula resolutiva para encontrar o valor de $x$. O discriminante da equação é calculado da seguinte forma:

$$\Delta = (-2)^2 - 4 \cdot 1 \cdot (-3 - y)$$

$$\Delta = 4 + 12 + 4y$$

$$\Delta = 16 + 4y$$

Substituindo esse resultado na fórmula, obtemos as raízes:

$$x = \frac{2 \pm \sqrt{16 + 4y}}{2}$$

$$x = \frac{2 \pm 2\sqrt{4 + y}}{2}$$

$$x = 1 \pm \sqrt{4 + y}$$

A hipótese inicial do problema define o contradomínio como $y \ge -4$. Isso assegura que a expressão dentro da raiz, $4 + y$, será sempre maior ou igual a zero. Essa condição garante que o resultado da operação seja um número real.

Para garantir que o $x$ gerado pertença ao domínio estabelecido de $[1, +\infty)$, tomamos a ramificação positiva da equação matemática:

$$x = 1 + \sqrt{4 + y}$$

Como o resultado numérico de uma raiz quadrada é sempre maior ou igual a zero, a soma de $1$ com essa raiz resultará sempre em um valor maior ou igual a $1$. Logo, $x \ge 1$. O valor de $x$ gerado reside inquestionavelmente dentro do domínio válido $[1, +\infty)$.

Como para todo $y$ arbitrário testado no contradomínio foi possível encontrar um $x$ correspondente perfeitamente válido no domínio, está provado que a função é _sobrejetiva_.

---

> [!done] **_New_**

---

```ad-quote
title:
###### Extra ) - 3
```

Prova injetividade

$$f(x_1) = f(x_2)$$
$$\frac{4x_1 - 5}{2x_1 - 1} = \frac{4x_2 - 5}{2x_2 - 1}$$
$$(4x_1 - 5)(2x_2 - 1) - (4x_2 - 5)(2x_1 - 1)= 0$$


$$(A \cup B) - (A \cup C) = (B - A) - C$$

Prova ida

seja $x$ um elemento arbitrário tal que $x \in (A \cup B) - (A \cup C)$.
1. Pela propriedade da subtração entre conjuntos, se $x \in (A \cup B) - (A \cup C)$, então $x \in (A \cup B) \land x \notin (A \cup C)$
2. Pela propriedade da união, se $x \in (A \cup B)$, então $x \in A \lor x \in B$.
3. Pela propriedade da união, se $x \notin (A \cup C)$, então $x \notin A \land x \notin C$.

---

$(A \cap C) - (B \cap C) = (A - B) \cap C$

Seja $x$ um elemento arbitrátio tal que $x \in (A \cap C) - (B \cap C)$.
1.  $x \in (A \cap C) x \notin (B \cap C)$
2. $x \in A \land x \in C \land x \notin B \lor x \notin C$
3. $x \in A \land x \in C \land x \notin B$
4. $x \in A \land x \notin B \land x \in C$
5. $x \in (A - B) \land C$
6. $x \in (A - B) \cap C$
