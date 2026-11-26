---
banner: "![[Pasted image 20260311140138.png]]"
---

---

````ad-quote
title:
##### **16 ) -** Estrutura Base da Relação de Equivalência

```ad-quote
title:
Uma relação que agrupa elementos de um conjunto que compartilham uma mesma característica fundamental, operando de forma _indistinguível_ sob a regra avaliada.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
$R$ é uma relação de equivalência se $\forall a, b, c \in A$:
1. reflexiva 
	- $aRa$
2. simétrica 
	- $aRb \implies bRa$
3. transitiva
	- $(aRb \land bRc) \implies aRc$ 
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $R$ é uma relação de equivalência. Logo, $R$ é obrigatoriamente _reflexiva_, _simétrica_ e _transitiva_, exigindo que o caminho de volta exista para qualquer conexão.
```

```ad-quote
title:  
###### Ex ) Exemplo  
```

```ad-quote
title:  
A relação semântica "ter a mesma idade" em um conjunto de pessoas. Se a Pessoa A tem a mesma idade que a Pessoa B, a Pessoa B obrigatoriamente tem a mesma idade que a Pessoa A.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **17 ) -** Cálculo de Classes de Equivalência ($[x]_{\mathcal{R}}$)

```ad-quote
title:
O subconjunto formado exclusivamente por todos os elementos do domínio que se relacionam com um elemento representativo específico sob a regra da relação.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $[a]_R = \{x \in A \mid xRa\}$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $x \in [a]_R$. Logo, pela definição de classe de equivalência, a relação $xRa$ é obrigatoriamente verdadeira.
```

```ad-quote
title:  
###### Ex ) Exemplo  
```

```ad-quote
title:  
No conjunto $\mathbb{Z}$ com a relação "possuir a mesma paridade", a classe do número 1 é representada por $[1]_R$ e contém obrigatoriamente todos os números ímpares do universo.
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **18 ) -** Lógica de Partição de um Conjunto

```ad-quote
title:
A divisão estrita do conjunto universal em blocos isolados, onde nenhum elemento pertence a mais de um bloco e absolutamente nenhum elemento fica de fora.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- Uma partição de $A$ é uma família de subconjuntos não vazios $A_i$ tais que:
    1. $A_i \cap A_j = \emptyset$ (para $i \neq j$).
    2. $\bigcup A_i = A$.
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $P$ é uma partição de $A$. Logo, a intersecção entre quaisquer duas classes distintas pertencentes a $P$ resulta obrigatoriamente em um conjunto vazio.
```

```ad-quote
title:  
###### Ex ) Exemplo  
```

```ad-quote
title:  
Separar as cartas de um baralho por naipes. Cada carta pertence a exatamente um único naipe (_intersecção vazia_) e a união de todos os naipes reconstrói o baralho completo (_união total_).
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **19 ) -** Conjunto Quociente ($A/\mathcal{R}$)

```ad-quote
title:
Um novo conjunto construído ao agrupar todas as classes de equivalência distintas geradas pela relação. Os elementos deste conjunto são as próprias _classes_ (subconjuntos), e não os elementos individuais de origem.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $A/R = \{[x]_R \mid x \in A\}$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $X \in A/R$. Logo, $X$ é obrigatoriamente uma classe de equivalência completa gerada pela relação $R$ atuando sobre o conjunto $A$.
```

```ad-quote
title:  
###### Ex ) Exemplo  
```

```ad-quote
title:  
No conjunto $A = \{1, 2, 3, 4, 5, 6\}$ sob a relação de "mesma paridade", o conjunto quociente consolida as duas únicas classes distintas formadas: $A/R = \{\{1, 3, 5\}, \{2, 4, 6\}\}$.
```
````

---