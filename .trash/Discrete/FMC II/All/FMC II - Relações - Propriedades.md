---
banner: "![[Pasted image 20260311140138.png]]"
---

---

````ad-quote
title:
###### 01 ) - Reflexividade

```ad-quote
title:
Uma relação onde cada elemento do conjunto está obrigatoriamente relacionado consigo mesmo.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\forall a \in A, (a, a) \in R$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação reflexiva sobre $A$. Logo, dado um elemento arbitrário $a \in A$, temos obrigatoriamente que o par idêntico $(a, a) \in R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

No conjunto $A = \{1, 2, 3\}$, a relação $R = \{(1, 1), (2, 2), (3, 3)\}$ é reflexiva. 
```

```ad-quote
title:  
A relação "ser da mesma cor que" ilustra a definição: se pegarmos um objeto qualquer, ele terá sempre a mesma cor que ele próprio.
```
````

---

> [!done] _New_

---

````ad-quote
title:
###### 02 ) - Irreflexividade

```ad-quote
title:
Uma relação onde nenhum elemento do conjunto pode estar relacionado consigo mesmo.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\forall a \in A, (a, a) \notin R$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação irreflexiva sobre $A$. Logo, dado um elemento arbitrário $a \in A$, temos obrigatoriamente que o par $(a, a) \notin R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  
No conjunto $A = \{1, 2\}$, a relação $R = \{(1, 2)\}$ é irreflexiva.
```

```ad-quote
title: 
A relação "ser filho biológico de" ilustra a definição: é biologicamente impossível que um indivíduo seja seu próprio pai ou mãe.
```
````

---

> [!done] _New_

---

````ad-quote
title:
###### 03 ) - Simetria

```ad-quote
title:
Se existe uma conexão de um elemento para outro, a conexão inversa deve obrigatoriamente existir.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\forall a, b \in A, (a, b) \in R \implies (b, a) \in R$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação simétrica. Logo, ao assumirmos que o par $(a, b) \in R$, concluímos obrigatoriamente que o seu inverso $(b, a) \in R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

No conjunto $A = \{1, 2, 3\}$, a relação $R = \{(1, 2), (2, 1), (2, 3), (3, 2)\}$ é simétrica.
```

```ad-quote
title:  
A relação "ser casado com" é simétrica: se a Pessoa A é casada com a Pessoa B, então a Pessoa B é obrigatoriamente casada com a Pessoa A.
```
````

---

> [!done] _New_

---

````ad-quote
title:
###### 04 ) - Antissimetria

```ad-quote
title:
A relação nunca ocorre nos dois sentidos entre elementos diferentes. Se houver relação de ida e volta, os elementos são necessariamente o mesmo.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\forall a, b \in A, ((a, b) \in R \land (b, a) \in R) \implies a = b$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação antissimétrica. Logo, se assumirmos a existência simultânea dos caminhos $(a, b) \in R$ e $(b, a) \in R$, concluímos obrigatoriamente que $a = b$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

A relação "divisor de" nos números naturais é antissimétrica: se $x$ divide $y$ e $y$ divide $x$, então $x = y$. 
```
```ad-quote
title:  
Em um jogo de xadrez, se o Jogador A venceu o Jogador B, o Jogador B não pode ter vencido o Jogador A na mesma partida.
```
````

---

> [!done] _New_

---

````ad-quote
title:
###### 05 ) - Transitividade

```ad-quote
title:
Se existe uma relação em cadeia (de A para B e de B para C), deve existir uma relação direta do primeiro para o último.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\forall a, b, c \in A, ((a, b) \in R \land (b, c) \in R) \implies (a, c) \in R$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação transitiva. Logo, ao assumirmos que $(a, b) \in R$ e que $(b, c) \in R$, concluímos obrigatoriamente o salto direto $(a, c) \in R$.
```
````

````ad-quote
title:  

###### Ex ) Exemplo  

```ad-quote
title:  

Se $(1, 2) \in R$ e $(2, 3) \in R$, a transitividade exige que $(1, 3) \in R$. 
```

```ad-quote
title:  
A relação "estar ao norte de" é transitiva: se a cidade A fica ao norte da cidade B, e a cidade B fica ao norte da cidade C, então a cidade A fica obrigatoriamente ao norte da cidade C.
```
````

---

```ad-done
title:
#### **Fase 3 ) - Exclusções**
```

---

````ad-quote
title:
##### **Prop 1 ) -** Propriedades Exclusivas - Reflexividade & Irreflexividade

```ad-quote
title:  

<p align="justify">Estas duas propriedades são mutuamente exclusivas para qualquer conjunto que não seja vazio. A razão lógica é simples e baseia-se na presença ou ausência dos elementos da diagonal (os pares onde um elemento se relaciona consigo próprio, como (a, a)):</p>
```

```
Reflexiva 
- Todos os elementos do conjunto possuem um laço consigo mesmos.
   
Irreflexiva: 
- Nenhum elemento do conjunto possui um laço consigo mesmo.
```

```ad-quote
title:  

<p align="justify">Portanto, se existir pelo menos um elemento no conjunto, uma relação não pode exigir a presença de todos os laços e a ausência de todos os laços simultaneamente. Note, contudo, que uma relação pode não ser nenhuma das duas (basta que alguns elementos tenham laços e outros não).</p>
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **Prop 2 ) -** Falsa Exclusão - Simetria & Antissimetria 

```ad-quote
title:  

<p align="justify">É um erro comum pensar que a simetria e a antissimetria são opostas ou exclusivas. Na verdade, elas podem coexistir na mesma relação:</p>
```

```
Simetria: 
- Se existe a ida, tem de existir a volta.

Antissimetria: 
- Se existir a ida e a volta, os elementos têm de ser o mesmo.
```

```ad-quote
title:  

<p align="justify">A relação de identidade (onde cada elemento só se relaciona consigo próprio) é um exemplo perfeito de uma relação que é simétrica e antissimétrica ao mesmo tempo. Da mesma forma, uma relação pode não possuir nenhuma destas duas propriedades.</p>
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **Prop 3 ) -** Fecho Transitivo

```ad-quote
title:
A menor relação transitiva possível que engloba a relação original, construída através da adição de conexões diretas entre elementos que possuíam apenas ligações indiretas.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- Denotado algebraicamente por $R^+$. Se existe uma sequência de conexões $(x_0, x_1), (x_1, x_2), \dots, (x_{n-1}, x_n)$ em $R$, a regra impõe que a conexão direta $(x_0, x_n) \in R^+$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, a conexão $(a, c)$ pertence ao fecho transitivo $R^+$. Logo, obrigatoriamente existe um caminho sequencial válido na relação base $R$ que tem origem no elemento $a$ e alcança o elemento $c$.
```

```ad-quote
title:  
###### Ex ) Exemplo  
```

```ad-quote
title:  
Para o conjunto $A = \{1, 2, 3\}$ e a relação $R = \{(1, 2), (2, 3)\}$, a transitividade falha. O fecho transitivo corrige a falha estrutural inserindo a ponte direta ausente: $R^+ = \{(1, 2), (2, 3), (1, 3)\}$.
```
````

---
