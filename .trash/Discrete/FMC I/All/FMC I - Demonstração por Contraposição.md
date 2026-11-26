---
banner: "![[Pasted image 20260311140138.png]]"
---

---

````ad-quote
title:

##### **intro )** - Demonstração por Contraposição

```ad-quote
title:
<p align="justify">A Demonstração por Contraposição é um método indireto de prova matemática, constituindo um pilar fundamental no estudo de Fundamentos de Matemática para a Computação (FMC I). Essa técnica consiste em estabelecer a veracidade de uma proposição condicional do tipo _Se P, então Q_ ao assumir que a negação da tese (_não Q_) é verdadeira e, através de uma sequência lógica de passos dedutivos, chegar à negação da hipótese (_não P_).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Estrutura Lógica da Contraposição

```ad-quote
title:
Uma demonstração por contraposição de uma proposição na forma $P \rightarrow Q$ (lê-se _P implica Q_ ou _Se P, então Q_) segue um roteiro bem definido. O ponto de partida é sempre assumir que a negação da condição Q, chamada de _nova hipótese_, é verdadeira. A partir da veracidade de _não Q_, utiliza-se um encadeamento de argumentos lógicos, onde cada passo deve ser justificado por definições matemáticas previamente estabelecidas, axiomas, teoremas já demonstrados ou regras de inferência lógica. O objetivo é, após esta série de passos dedutivos, chegar à negação de P, também chamada de _nova tese_. Ao alcançar _não P_, demonstra-se por equivalência lógica que a veracidade da contrapositiva acarreta necessariamente a veracidade da condicional original.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Metodologia Passo a Passo

```ad-quote
title:
Para construir uma demonstração por contraposição de forma clara e rigorosa, os seguintes passos são recomendados:
```
````

````ad-quote
title:
```ad-quote
title:
###### **A ) Análise e Identificação**
```

```ad-quote
title:
A primeira etapa é analisar a proposição a ser provada, identificar claramente a hipótese original (P) e a tese original (Q), e então formular as suas respectivas negações matemáticas.
```
````

````ad-quote
title:
```ad-quote
title:
###### **B ) Formalização Matemática**
```

```ad-quote
title:
Deve-se expressar a nova hipótese e a nova tese em linguagem matemática formal, o que frequentemente envolve aplicar definições (como paridade) para representar algebricamente as negações.
```
````

````ad-quote
title:
```ad-quote
title:
###### **C ) Desenvolvimento Dedutivo**
```

```ad-quote
title:
Partindo da representação matemática da nova hipótese, aplica-se manipulações algébricas, propriedades conhecidas e outras ferramentas lógicas para transformar a expressão inicial passo a passo. Ao chegar rigorosamente à representação matemática da negação de P, a demonstração está completa.
```
````

---

```ad-done
title:

#### Exemplos ) - Provas por Contraposição

```

---

````ad-quote
title:

##### **Ex 01 )** - A Paridade do Quadrado Implica a Paridade da Base

```ad-quote
title:
_Proposição:_ 
- Se $n^2$ é um número inteiro par, então n é um número inteiro par.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Hipótese e Tese**
```

```ad-quote
title:
_Nova Hipótese assumida_ (não Q): 
- n é um número inteiro ímpar.

_Nova Tese a provar_ (não P): 
- $n^2$ é um número inteiro ímpar.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Demonstração**
```

```ad-quote
title:

_Assumir a negação de Q:_ 
- Suponha que n é um número inteiro ímpar.

_Usar a definição:_ 
- Por definição de número ímpar, existe um inteiro k tal que $n = 2k + 1$.

_Desenvolver a dedução:_ 
- Vamos analisar o quadrado de n:

1. $$n^2 = (2k + 1)^2$$  
2. $$n^2 = 4k^2 + 4k + 1$$
3. $$n^2 = 2(2k^2 + 2k) + 1$$

_Concluir a negação de P:_ 
- Como k é um inteiro, a expressão $(2k^2 + 2k)$ também resulta em um inteiro j. Portanto, $n^2$ pode ser escrito na forma $2j + 1$, o que, por definição, significa que $n^2$ é um número ímpar. Logo, a contrapositiva é verdadeira e a proposição original está demonstrada.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Ex 02 )** - Implicação de Paridade em Expressão Linear

```ad-quote
title:
_Proposição:_ 
- Se $3n + 2$ é um número inteiro ímpar, então n é um número inteiro ímpar.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Hipótese e Tese**
```

```ad-quote
title:
_Nova Hipótese assumida_ (não Q): 
- n é um número inteiro par.
  
_Nova Tese a provar_ (não P): 
- $3n + 2$ é um número inteiro par.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Demonstração**
```

```ad-quote
title:

_Assumir a negação de Q:_ 
- Suponha que n é um número inteiro par.

_Usar a definição:_ 

- Por definição de número par, existe um inteiro k tal que $n = 2k$.

_Desenvolver a dedução:_ Vamos analisar a expressão $3n + 2$:
    
1. $$3n + 2 = 3(2k) + 2$$   
2. $$3n + 2 = 6k + 2$$   
3. $$3n + 2 = 2(3k + 1)$$

_Concluir a negação de P:_ Seja $j = 3k + 1$. 

- Como k é um inteiro, j também é um inteiro. Assim, $3n + 2$ pode ser escrito na forma $2j$, o que, por definição, atesta que $3n + 2$ é um número par. Pela equivalência lógica, a proposição original é demonstrada.
```
````
