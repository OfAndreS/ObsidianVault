---
banner: "![[Pasted image 20251020192016.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify">A divisibilidade é um conceito central na Teoria dos Números que descreve a relação entre dois inteiros quando sua divisão resulta em um quociente inteiro, sem resto. É a base para o estudo de tópicos mais avançados como primalidade, congruência e máximo divisor comum.</p>
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Definição Formal de Divisibilidade

```ad-quote
title:
<p align="justify">A noção de divisibilidade é formalizada através de uma relação algébrica precisa, que elimina a ambiguidade do conceito de "divisão exata".</p>
```

```ad-quote
title:
###### Definição
```

```ad-quote
title:
Sejam a e b dois números inteiros, com a condição de que a≠0. Diz-se que "a divide b" se, e somente se, existe um terceiro inteiro k que satisfaz a seguinte equação:
```

```ad-quote
title:
$$b = a \cdot k$$
```

```ad-quote
title:
<p align="justify">A condição essencial nesta definição é a existência de um multiplicador k que pertença ao conjunto dos números inteiros (ℤ). Se para satisfazer a equação for necessário um k racional não inteiro ou irracional, então a relação de divisibilidade não se aplica.</p>
```

```ad-quote
title:
###### Exemplos Ilustrativos
```

```ad-quote
title:

8 divide 56? 
- Sim, pois é possível escrever a equação $56=(−8)⋅k$. Resolvendo para $k$, encontramos $k=−7$. Como $−7$ é um número inteiro, a definição é satisfeita.

4 divide 9? 
- Não. A equação correspondente seria $9=4⋅k$. A única solução para $k$ é $k=9/4=2.25$. Visto que $2.25$ não é um inteiro, conclui-se que $4$ não divide $9$.
```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Notação e Terminologia Padrão

```ad-quote
title:
<p align="justify">Para expressar a relação de divisibilidade de forma concisa, a matemática utiliza uma notação específica:</p>
```

![[Pasted image 20251020105105.png]]

```ad-quote
title:
Se a divide b, a notação é:

1. $$a | b$$
```

```ad-quote
title:
Se a não divide b, a notação é:

2. $$a \nmid b$$
```

```ad-quote
title:
Quando a relação a | b é verdadeira, os seguintes termos são sinônimos e podem ser usados de forma intercambiável:
- a é um divisor de b.
- a é um fator de b.
- b é um múltiplo de a.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Propriedades Fundamentais da Divisibilidade

```ad-quote
title:
<p align="justify">A partir da definição formal, uma série de propriedades pode ser deduzida e provada. Estas propriedades formam a base para a manipulação algébrica em problemas de Teoria dos Números. Sejam a, b, c, m e n números inteiros.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### Propriedade Reflexiva:
```

```ad-quote
title:
<p align="justify">Todo inteiro não nulo divide a si mesmo.</p>
```

```ad-quote
title:
1. $$a | a \ \ \ \text{(para }a \neq 0\text{)}$$
```

```ad-quote
title:
###### Prova:
```

```ad-quote
title:

2. $$\text{pois} \ \ \ a = a \cdot 1$$

```

````

````ad-quote
title:
```ad-quote
title:
###### Propriedade Transitiva:
```
```ad-quote
title:
<p align="justify">Se um número a divide b e b divide c, então a necessariamente divide c.</p>
```
```ad-quote
title:
1. $$(a | b \land b | c) \Rightarrow a | c$$
```
```ad-quote
title:
###### Prova:
```
```ad-quote
title:
2. $$\text{Se } a | b \text{, então } b = a k_1$$ 
3. $$\text{Se } b | c \text{, então } c = b k_2$$ 
4. $$\text{Substituindo, obtém-se } c = (a k_1)k_2 = a(k_1 k_2)$$ 
5. $$\text{Como o produto de dois inteiros é um inteiro, } a|c \text{.}$$
``` 
````

````ad-quote
title:
```ad-quote
title:
###### Propriedade da Combinação Linear:
```

```ad-quote
title:
<p align="justify">Se a divide tanto b quanto c, então a divide qualquer combinação linear de b e c.</p>
```

```ad-quote
title:
1. $$(a | b \land a | c) \Rightarrow a | (m \cdot b + n \cdot c) \text{ para quaisquer inteiros } m, n \text{.}$$
```

```ad-quote
title:
###### Exemplo:
```

```ad-quote
title:
2. $$\text{Dado que } 3 | 6 \text{ e } 3 | 15$$ 
3. $$\text{então } 3 \text{ deve dividir } (2 \cdot 6 + 4 \cdot 15) = 12 + 60 = 72$$ 
4. $$\text{De fato, } 72 = 3 \cdot 24 \text{.}$$
```

````

````ad-quote
title:
```ad-quote
title:
###### Divisão do Zero:
```

```ad-quote
title:
<p align="justify">Qualquer inteiro não nulo é um divisor de zero.</p>
```

```ad-quote
title:
1. $$a | 0 \ \ \ \text{(para }a \neq 0\text{)}$$
```

```ad-quote
title:
###### Prova:
```

```ad-quote
title:
2. $$\text{pois} \ \ \ 0 = a \cdot 0$$
```
````

````ad-quote
title:
```ad-quote
title:
###### Divisão por 1 e -1:
```

```ad-quote
title:
<p align="justify">Os números 1 e -1 dividem qualquer inteiro.</p>
```

```ad-quote
title:
1. $$1 | a \ \ \text{ e } -1 | a$$
```

```ad-quote
title:
###### Prova:
```

```ad-quote
title:
2. $$\text{pois} \ \ \ a = 1 \cdot a \text{ e } a = (-1) \cdot (-a)$$
```

````

````ad-quote
title:
```ad-quote
title:
###### Relação de Módulo - Valor Absoluto:
```

```ad-quote
title:
<p align="justify">Se a divide b e b não é zero, o valor absoluto de a não pode ser maior que o valor absoluto de b.</p>
```

```ad-quote
title:
1. $$(a | b \land b \neq 0) \Rightarrow |a| \leq |b|$$
```

```ad-quote
title:
###### Propriedade da Simetria:
```

```ad-quote
title:
<p align="justify">Se a divide b e b divide a, então a e b são iguais ou opostos.</p>
```

```ad-quote
title:
1. $$(a | b \land b | a) \Rightarrow a = \pm b$$
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - O Algoritmo da Divisão - A Formalização do Resto

```ad-quote
title:
<p align="justify">O Teorema do Algoritmo da Divisão (ou Divisão Euclidiana) estabelece uma ponte formal entre a divisibilidade e a operação de divisão com resto.</p>
```

```ad-quote
title:
###### Teorema:
```

```ad-quote
title:
Para quaisquer dois inteiros a (dividendo) e d (divisor), com d > 0, existem inteiros únicos q (quociente) e r (resto) que satisfazem a relação:
```

```ad-quote
title:
$$a = d \cdot q + r \quad \text{onde} \quad 0 \leq r < d$$
```

```ad-quote
title:
<p align="justify">A conexão direta deste teorema com o conceito de divisibilidade é a seguinte: A relação d | a é verdadeira se, e somente se, o resto r obtido através do Algoritmo da Divisão for igual a zero.</p>
```

```ad-quote
title:
###### Exemplos:
```

```ad-quote
title:
- Análise de 56÷8: 56=8⋅7+0. O resto r é 0. Portanto, confirma-se que 8∣56.
- Análise de 9÷4: 9=4⋅2+1. O resto r é 1. Como r≠0, confirma-se que 4∤9.
```

```ad-quote
title:
<p align="justify">Este arcabouço teórico fornece as ferramentas necessárias para analisar as relações estruturais entre os números inteiros de maneira rigorosa e sistemática.</p>
```
````

```python

def divisao_manual(dividendo: int, divisor: int) -> tuple[int, int]: 

""" Implementa a divisão inteira e o resto usando subtrações sucessivas. 

Args: 
	dividendo: O número a ser dividido. divisor: O número pelo qual dividir. 

Returns: 
	Uma tupla contendo (quociente, resto). Raises: ValueError: Se o divisor for zero. 
	
"""
```

---