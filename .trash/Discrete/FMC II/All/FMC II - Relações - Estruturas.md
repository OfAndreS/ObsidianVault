---
banner: "![[Pasted image 20260311140138.png]]"
---

---

````ad-quote
title:
##### **06 ) -** Composição de Relações
```ad-quote
title:
Considere três conjuntos $X = \{1, 2\}$, $Y = \{a, b, c\}$ e $Z = \{3, 4\}$. Sejam as relações $B$ definida de $X$ para $Y$ ($B \subseteq X \times Y$) e $A$ definida de $Y$ para $Z$ ($A \subseteq Y \times Z$).
```
````

````ad-quote
title:
###### A ) - Composição $A \circ B$

```ad-quote
title:
É a relação construída ao conectar diretamente os elementos do conjunto de partida aos do conjunto de chegada, passando obrigatoriamente por um elemento _intermediário_. Na notação $A \circ B$, a relação $B$ atua como o primeiro passo do trajeto e $A$ como o segundo.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $A \circ B = \{(x, z) \in X \times Z \mid \exists y \in Y, (x, y) \in B \land (y, z) \in A\}$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $(x, z) \in (A \circ B)$. Logo, pela definição de composição, obrigatoriamente existe um elemento intermediário $y$ tal que $(x, y) \in B$ e $(y, z) \in A$.
```

````

````ad-quote
title:  

###### Ex ) Numérico 

```ad-quote
title:  

Sendo a relação inicial $B = \{(1, a), (2, b)\}$ e a relação final $A = \{(a, 3), (b, 4), (c, 4)\}$, o trajeto conecta as pontas resultando em $A \circ B = \{(1, 3), (2, 4)\}$. O caminho originado em $2$, por exemplo, passa pelo intermediário $b$ na relação $B$ para atingir o destino final $4$ na relação $A$.s
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **07.1 ) -** Domínio de uma Relação
```ad-quote
title:
Considere o conjunto $A = \{a, b, c, d\}$ e a relação $R$ definida sobre $A$:

$R = \{(a, b), (b, c), (b, d)\}$
```
````

````ad-quote
title:
###### A ) - Domínio de $R$

```ad-quote
title:
É o subconjunto de $A$ composto exclusivamente pelos elementos que atuam como primeira coordenada nos pares ordenados.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $Dom(R) = \{x \in A \mid \exists y \in A, (x, y) \in R\}$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $x \in Dom(R)$. Logo, pela definição de domínio, obrigatoriamente existe um $y$ tal que $(x, y) \in R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

$Dom(R) = \{a, b\}$. Os elementos $c$ e $d$ não pertencem ao domínio pois não iniciam nenhuma conexão.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **07.2 ) -** Imagem de uma Relação
```ad-quote
title:
Considere o conjunto $A = \{a, b, c, d\}$ e a relação $R$ definida sobre $A$:

$R = \{(a, b), (b, c), (b, d)\}$
```
````

````ad-quote
title:
###### A ) - Imagem de $R$

```ad-quote
title:
É o subconjunto de $A$ composto pelos elementos que atuam como segunda coordenada nos pares ordenados.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $Img(R) = \{y \in A \mid \exists x \in A, (x, y) \in R\}$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $y \in Img(R)$. Logo, pela definição de imagem, obrigatoriamente existe um $x$ tal que $(x, y) \in R$.
```

````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

$Img(R) = \{b, c, d\}$. O elemento $a$ não pertence à imagem pois não é o destino de nenhuma conexão.
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **08 ) -** Relação Inversa
```ad-quote
title:
Considere o conjunto $A = \{a, b, c, d\}$ e a relação $R$ definida sobre $A$:

$R = \{(a, b), (b, c), (b, d)\}$
```
````

````ad-quote
title:
###### A ) - Relação Inversa $R^{-1}$

```ad-quote
title:
Obtém-se invertendo estritamente a posição dos elementos em todos os pares ordenados de $R$.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $R^{-1} = \{(y, x) \in A \times A \mid (x, y) \in R\}$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $(y, x) \in R^{-1}$. Logo, pela definição de relação inversa, o par invertido $(x, y) \in R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

$R^{-1} = \{(b, a), (c, b), (d, b)\}$. Note que o $Dom(R^{-1})$ é igual à $Img(R)$ e a $Img(R^{-1})$ é igual ao $Dom(R)$.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **09 ) -** Propriedades de Relações
```ad-quote
title:
Considere o conjunto $A = \{a, b, c, d\}$ e a relação $R$ definida sobre $A$:

$R = \{(a, b), (b, c), (b, d)\}$
```
````

````ad-quote
title:
###### A ) - Relação Total

```ad-quote
title:
A regra estrutural exige que $Dom(R) = A$. Todo elemento do conjunto deve ser a primeira coordenada em pelo menos um par ordenado.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $R$ é total $\iff Dom(R) = A$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação total sobre $A$. Logo, dado um $x \in A$ qualquer, obrigatoriamente existe um $y \in A$ tal que $(x, y) \in R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

$R_1 = \{(a, b), (b, c), (c, a), (d, d)\}$ é total. A relação original $R = \{(a, b), (b, c), (b, d)\}$ falha em ser total porque $c$ e $d$ não pertencem ao domínio.
```

````

> [!done] _New_

````ad-quote
title:
###### B ) - Relação Funcional

```ad-quote
title:
A regra estrutural exige que cada elemento possua no máximo uma única conexão de saída. Não podem existir dois pares distintos com a mesma primeira coordenada.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $R$ é funcional $\iff \forall x,y,z \in A, ((x,y) \in R \land (x,z) \in R) \Rightarrow y = z$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação funcional. Logo, como $(x, y) \in R$ e $(x, z) \in R$, obrigatoriamente $y = z$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

$R_2 = \{(a, c), (b, d), (d, a)\}$ é funcional. A relação $R$ do primeiro exemplo possui uma falha estrutural funcional porque $b$ mapeia simultaneamente para $c$ e $d$.
```

````

> [!done] _New_

````ad-quote
title:
###### C ) - Relação Injetiva

```ad-quote
title:
A regra estrutural exige que elementos distintos não convirjam para o mesmo destino. Não podem existir dois pares distintos com a mesma segunda coordenada.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $R$ é injetiva $\iff \forall x,y,z \in A, ((x,z) \in R \land (y,z) \in R) \Rightarrow x = y$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação injetiva. Logo, como $(x, z) \in R$ e $(y, z) \in R$, obrigatoriamente $x = y$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

$R_3 = \{(a, b), (b, c), (c, d)\}$ é injetiva. Uma relação como $\{(a, c), (b, c)\}$ falha no critério de injetividade porque origens distintas $a$ e $b$ colidem na mesma imagem $c$.
```

````

> [!done] _New_

````ad-quote
title:
###### D ) - Relação Sobrejetiva

```ad-quote
title:
A regra estrutural exige que $Img(R) = A$. Todo elemento do conjunto de chegada deve ser atingido por pelo menos um par ordenado.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $R$ é sobrejetiva $\iff Img(R) = A$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação sobrejetiva sobre $A$. Logo, dado um $y \in A$ qualquer, obrigatoriamente existe um $x \in A$ tal que $(x, y) \in R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

$R_4 = \{(a, b), (b, c), (c, d), (d, a)\}$ é sobrejetiva. Todos os elementos de $A$ figuram como segunda coordenada, satisfazendo a sobrejetividade.
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **... ) -** Relação Identidade

```ad-quote
title:
A relação mais restrita possível sobre um conjunto, onde a única conexão permitida é a ligação exata de um elemento com ele mesmo.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- Denotada algebraicamente por $I_A$. É definida pelo conjunto: $I_A = \{(x, x) \mid x \in A\}$.
- Operando sob a notação infixa: $\forall x, y \in A, xI_Ay \iff x = y$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, o par ordenado $(a, b)$ pertence à relação identidade $I_A$. Logo, pela definição estrutural da relação, conclui-se obrigatoriamente que $a = b$.
```
````

````ad-quote
title:
```ad-quote
title:  
###### Ex ) Exemplo  
```

```ad-quote
title:  
Para o conjunto $A = \{1, 2, 3\}$, a relação identidade é estritamente formada pelas conexões espelhadas: $I_A = \{(1, 1), (2, 2), (3, 3)\}$. A inserção de absolutamente qualquer outro par cruzado (como $(1, 2)$) destrói a identidade da relação.
```
````

---

````ad-quote
title:
##### **19 ) -** Relações Disjuntas

```ad-quote
title:
Duas relações avaliadas sobre o mesmo conjunto universal que não compartilham absolutamente nenhuma conexão em comum. Os seus conjuntos de pares ordenados são estritamente isolados.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- Duas relações $R$ e $S$ sobre um conjunto $A$ são disjuntas se, e somente se, a intersecção entre elas é vazia: $R \cap S = \emptyset$.
- Lógica proposicional: $\neg \exists (x, y) \mid (x, y) \in R \land (x, y) \in S$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ e $S$ são relações disjuntas e o par ordenado $(a, b)$ pertence à relação $R$. Logo, pela definição estrutural de disjunção, conclui-se obrigatoriamente que o par $(a, b)$ não pertence à relação $S$.
```

```ad-quote
title:  
###### Ex ) Exemplo  
```

```ad-quote
title:  
Considere o conjunto $A = \{1, 2, 3\}$. Avalie a relação $R$ definida por "estritamente menor que" ($<$) e a relação $S$ definida por "igualdade" ($=$). É matematicamente impossível que um número seja simultaneamente menor e igual a outro. Como nenhum par ordenado atende a ambas as regras, as relações $R$ e $S$ são disjuntas.
```
````