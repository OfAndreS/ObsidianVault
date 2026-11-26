---
banner: "![[Pasted image 20260311140138.png]]"
---
---

````ad-quote
title:

##### **intro )** - Demonstração Direta

```ad-quote
title:
<p align="justify">A Demonstração Direta é um dos métodos mais fundamentais e intuitivos de prova matemática, constituindo um pilar no estudo de Fundamentos de Matemática para a Computação (FMC I). Essa técnica consiste em estabelecer a veracidade de uma proposição condicional do tipo "Se P, então Q" ao assumir que a hipótese P é verdadeira e, através de uma sequência lógica de passos dedutivos, chegar à conclusão Q.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Estrutura Lógica da Demonstração Direta

```ad-quote
title:
Uma demonstração direta de uma proposição na forma $P \rightarrow Q$ (lê-se "P implica Q" ou "Se P, então Q") segue um roteiro bem definido. O ponto de partida é sempre assumir que a condição P, chamada de *hipótese* ou *antecedente*, é verdadeira. A partir da veracidade de P, utiliza-se um encadeamento de argumentos lógicos, onde cada passo deve ser justificado por definições matemáticas previamente estabelecidas, axiomas, teoremas já demonstrados ou regras de inferência lógica. O objetivo é, após esta série de passos dedutivos, chegar à conclusão Q, também chamada de *tese* ou *consequente*. Ao alcançar Q, demonstra-se que a veracidade de P acarreta necessariamente a veracidade de Q.
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
Para construir uma demonstração direta de forma clara e rigorosa, os seguintes passos são recomendados:
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
A primeira etapa é analisar a proposição a ser provada e identificar claramente qual é a hipótese (P) e qual é a tese (Q).
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
Deve-se expressar a hipótese e a tese em linguagem matemática formal, o que frequentemente envolve o uso de variáveis e a aplicação de definições.
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
Partindo da representação matemática da hipótese, aplica-se manipulações algébricas, propriedades conhecidas e outras ferramentas lógicas para transformar a expressão inicial passo a passo, aproximando-se da forma matemática da tese. Ao chegar à representação matemática da tese, a demonstração está completa.
```
````

---

```ad-done
title:

#### Exemplos ) - Provas Diretas

```

---

````ad-quote
title:

##### **Ex 01 )** - A Soma de Dois Números Pares é Par

```ad-quote
title:
**Proposição:** 
- Se m e n são números inteiros pares, então m + n é um número inteiro par.
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
**Hipótese (P):** 
- m e n são números inteiros pares.

**Tese (Q):** 
- m + n é um número inteiro par.
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

**Hip - Assumir P:** 
- Suponha que m e n são números inteiros pares.

**Usar a definição:** 
- Por definição de número par, existem inteiros k e j tais que $m = 2k$ e $n = 2j$

**Desenvolver a dedução:** 
- Vamos analisar a soma $m + n$:

1. $$m + n = 2k + 2j$$  
2. $$m + n = 2(k + j)$$

**Concluir Q:** 
- Como k e j são inteiros, a soma deles, $(k + j)$, também é um inteiro. Portanto, $m + n$ pode ser escrito na forma 2 vezes um inteiro, o que, por definição, significa que $m + n$ é um número par.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Ex 02 )** - O Quadrado de um Número Ímpar é Ímpar

```ad-quote
title:
**Proposição:** 
- Se n é um número inteiro ímpar, então $n^2$ é um número inteiro ímpar.
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
**Hipótese (P):** 
- n é um número inteiro ímpar.
  
**Tese (Q):** 
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

**Assumir P:** 
- Suponha que n é um número inteiro ímpar.

**Usar a definição:** 

- Por definição de número ímpar, existe um inteiro k tal que $n = 2k + 1$.

**Desenvolver a dedução:** Vamos analisar $n^2$:
    

1. $$n^2 = (2k + 1)^2$$   

2. $$n^2 = 4k^2 + 4k + 1$$   

3. $$n^2 = 2(2k^2 + 2k) + 1$$

**Concluir Q:** Seja $j = 2k^2 + 2k$. 

- Como k é um inteiro, j também é um inteiro. Assim, $n^2$ pode ser escrito na forma $2j + 1$, o que, por definição, significa que $n^2$ é um número ímpar.
```
````

---
