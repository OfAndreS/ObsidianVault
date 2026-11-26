---
banner: "![[Pasted image 20260311140138.png]]"
---
---

````ad-quote
title:
##### **10 ) -** Relação de Ordem Parcial

```ad-quote
title:
Uma relação que estabelece uma hierarquia de precedência ou dependência, permitindo que existam elementos incomparáveis.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
$R$ é ordem parcial se $\forall a, b, c \in A$:
1. Reflexiva      
   - $aRa$
1. Antissimétrica 
   - $(aRb \land bRa) \implies a = b$
1. Transitiva     
   - $(aRb \land bRc) \implies aRc$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação de ordem parcial. Logo, $R$ é obrigatoriamente reflexiva, antissimétrica e transitiva.
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
A relação de divisibilidade em $\mathbb{N}$. Nem todo número divide outro (ex: 2 e 3 são *incomparáveis*), mas as regras de hierarquia são mantidas.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **11 ) -** Relação de Ordem Total

```ad-quote
title:
Uma variação restrita da ordem parcial onde a linearidade é absoluta, impedindo ramificações.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $R$ é ordem total se for ordem parcial e satisfizer a *comparabilidade*:
    $\forall a, b \in A, (aRb \lor bRa)$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação de ordem total. Logo, dados dois elementos quaisquer $a$ e $b$, é obrigatório que exista uma conexão entre eles em pelo menos um sentido.
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
A relação de menor ou igual ($\le$) nos números reais. Dados quaisquer dois números, sempre podemos determinar qual é o menor ou se são iguais.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **12.1 ) -** Menor Elemento - Mínimo Global

```ad-quote
title:
O elemento que ocupa a base absoluta da estrutura, precedendo todos os outros.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $b \in A$ é o menor elemento se $\forall x \in A, bRx$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $b$ é o menor elemento de $A$. Logo, para qualquer elemento $x$ selecionado no conjunto, a relação $bRx$ é obrigatoriamente verdadeira.
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
No conjunto $A = \{1, 2, 3\}$ com a relação $\le$, o elemento 1 é o menor elemento pois $1 \le 1, 1 \le 2$ e $1 \le 3$.
```
````

> [!done] _New_

````ad-quote
title:
##### **12.2) -** Minimo Local - Minimal

```ad-quote
title:
Um elemento que não possui nenhum antecessor diferente de si próprio na hierarquia.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $b \in A$ é minimal se $\neg \exists x \in A \mid (x \neq b \land xRb)$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $b$ é um elemento minimal. Logo, se assumirmos a existência de um $x$ tal que $xRb$, obrigatoriamente este $x$ deve ser igual a $b$.
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
No conjunto $\{2, 3, 4, 6\}$ sob divisibilidade, tanto 2 quanto 3 são minimais, pois nenhum outro número do conjunto divide eles.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **13.1 ) -** Maior Elemento - Máximo Global

```ad-quote
title:
O elemento que se posiciona no topo absoluto, sendo precedido por todos os outros.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $b \in A$ é o maior elemento se $\forall x \in A, xRb$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $b$ é o maior elemento. Logo, qualquer elemento $x$ do conjunto atua obrigatoriamente como origem de uma conexão para $b$.
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
No conjunto $\{1, 2, 3, 6\}$ sob divisibilidade, o 6 é o maior elemento, pois todos os outros números do conjunto dividem o 6.
```
````

> [!done] _New_

````ad-quote
title:
##### **13.2 ) -** Máximo Local - Maximal

```ad-quote
title:
Um elemento que não atua como origem para nenhum sucessor diferente de si mesmo.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $b \in A$ é maximal se $\neg \exists x \in A \mid (x \neq b \land bRx)$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $b$ é um elemento maximal. Logo, se assumirmos que $bRx$ é verdadeiro, concluímos obrigatoriamente que $x = b$.
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
No conjunto $\{2, 3, 4, 6\}$ sob divisibilidade, 4 e 6 são maximais, pois não dividem nenhum outro elemento do conjunto.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **14.1 ) -** Cota Superior

```ad-quote
title:
Elemento do conjunto universal que serve como limite superior (destino) para todos os elementos de um subconjunto específico.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- Cota Superior: $a \in A \mid \forall x \in B, xRa$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $a$ é uma cota superior do subconjunto $B$. Logo, para todo elemento $x$ pertencente a $B$, a relação $xRa$ deve ser obrigatoriamente satisfeita.
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
Para $B = \{2, 3\}$ no universo $\{1, 2, 3, 4, 6, 12\}$ sob a relação de divisibilidade, as cotas superiores são $\{6, 12\}$.
```
````

> [!done] _New_

````ad-quote
title:
##### **14.2 ) -** Cota Inferior

```ad-quote
title:
Elemento do conjunto universal que serve como limite inferior (origem) para todos os elementos de um subconjunto específico.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- Cota Inferior: $a \in A \mid \forall x \in B, aRx$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $a$ é uma cota inferior do subconjunto $B$. Logo, para todo elemento $x$ pertencente a $B$, a relação $aRx$ deve ser obrigatoriamente satisfeita.
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
Para $B = \{2, 3\}$ no universo $\{1, 2, 3, 4, 6, 12\}$ sob a relação de divisibilidade, a única cota inferior é $\{1\}$.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **15) -** Supremo e Ínfimo

```ad-quote
title:
Os limites mais ajustados (extremos) dentro dos conjuntos de cotas.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- Supremo: O menor elemento do conjunto de cotas superiores.
- Ínfimo: O maior elemento do conjunto de cotas inferiores.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $s$ é o supremo de $B$. Logo, $s$ é uma cota superior e, para qualquer outra cota superior $c$, deve valer $sRc$.
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
No exemplo anterior, entre as cotas superiores $\{6, 12\}$, o supremo é 6 (pois 6 divide 12). O ínfimo é 1, sendo a única cota inferior disponível.
```
````

---


