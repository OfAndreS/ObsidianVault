---
banner: "![[Pasted image 20260311140138.png]]"
---

---

````ad-quote
title:

##### **intro )** - Redução ao Absurdo

```ad-quote
title:
<p align="justify">A Demonstração por Absurdo, ou Contradição, é um método de prova matemática profundo e elegante, essencial em Fundamentos de Matemática para a Computação (FMC I). Essa técnica consiste em estabelecer a veracidade de uma proposição ao assumir temporariamente que ela é falsa. A partir dessa suposição de falsidade, desenvolve-se uma sequência de passos lógicos dedutivos até encontrar uma contradição flagrante (como _0 = 1_, ou afirmar que um número é par e ímpar simultaneamente). O encontro desse absurdo lógico prova que a suposição inicial estava errada, logo, a proposição original deve ser verdadeira.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Estrutura Lógica da Redução ao Absurdo

```ad-quote
title:
Uma demonstração por absurdo de uma proposição condicional na forma $P \rightarrow Q$ exige que neguemos a implicação inteira. Na lógica matemática, a negação de _Se P, então Q_ é a afirmação de que _P é verdadeiro E Q é falso_. Portanto, o roteiro inicia-se assumindo a hipótese original P como verdadeira e a tese Q como falsa (não Q). A partir da veracidade simultânea de P e _não Q_, utiliza-se o encadeamento dedutivo fundamentado em axiomas e teoremas. O objetivo não é chegar a uma expressão específica, mas sim esbarrar em uma impossibilidade matemática, que chamamos de _contradição_. Ao encontrar a contradição, demonstra-se que é impossível P ser verdadeiro e Q ser falso ao mesmo tempo, validando a proposição $P \rightarrow Q$.
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
Para construir uma demonstração por absurdo de forma rigorosa, os seguintes passos são recomendados:
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
A primeira etapa é analisar a proposição a ser provada e identificar a hipótese (P) e a tese (Q). Em seguida, formula-se a premissa do absurdo: assumir que P é verdadeiro e que a negação de Q também é verdadeira.
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
Deve-se expressar a condição _P e não Q_ em linguagem matemática formal. Isso frequentemente envolve aplicar definições algébricas para criar o ponto de partida das equações que serão manipuladas.
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
Partindo da formalização anterior, desenvolve-se a álgebra e a lógica de forma impecável. O foco é buscar uma falha no sistema, ou seja, chegar a uma conclusão que viole uma propriedade fundamental dos números ou que contradiga a própria hipótese inicial assumida.
```
````

---

Snippet de código

```
title:

#### Exemplos ) - Provas por Absurdo

```

---

````ad-quote
title:

##### **Ex 01 )** - Implicação de Paridade

```ad-quote
title:
_Proposição:_ 
- Se _n_ é um número inteiro e $3n + 2$ é um número ímpar, então _n_ é um número ímpar.
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
_Hipótese (P):_ 
- $3n + 2$ é um número inteiro ímpar.

_Tese (Q):_ 
- _n_ é um número inteiro ímpar.
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

_Suposição para o Absurdo (P e não Q):_ 
- Suponha que $3n + 2$ é ímpar e, simultaneamente, que _n_ é par (negação da tese).

_Usar a definição:_ 
- Como assumimos que _n_ é par, por definição, existe um inteiro k tal que $n = 2k$.

_Desenvolver a dedução:_ 
- Vamos substituir _n_ na expressão original que assumimos ser ímpar:

1. $$3n + 2 = 3(2k) + 2$$  
2. $$3n + 2 = 6k + 2$$
3. $$3n + 2 = 2(3k + 1)$$

_Encontrar a Contradição:_ 
- Sendo k um inteiro, $(3k + 1)$ também é um inteiro. Logo, a expressão resultou na forma 2 vezes um inteiro, o que define um número par. 
- _Absurdo:_ Chegamos à conclusão de que $3n + 2$ é par, o que contradiz frontalmente nossa hipótese inicial P (onde afirmamos que $3n + 2$ é ímpar). Como a suposição lógica gerou uma falha, ela é inválida. Logo, a proposição original é verdadeira.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Ex 02 )** - Irracionalidade da Raiz de 2

```ad-quote
title:
_Proposição:_ 
- O número $\sqrt{2}$ é um número irracional.
- _Nota: Provas de irracionalidade são os exemplos mais clássicos de redução ao absurdo._
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
_Proposição a ser testada (Q):_ 
- $\sqrt{2}$ é irracional.
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

_Suposição para o Absurdo (não Q):_ 
- Suponha, por absurdo, que $\sqrt{2}$ é um número racional.

_Usar a definição:_ 
- Por definição de número racional, $\sqrt{2}$ pode ser escrito como a fração de dois inteiros _a_ e _b_ (com _b_ diferente de zero). 
- _Condição crucial:_ Podemos assumir que a fração $\frac{a}{b}$ está em sua forma irredutível, ou seja, _a_ e _b_ não possuem divisores comuns além de 1.
- Logo, $\sqrt{2} = \frac{a}{b}$.

_Desenvolver a dedução:_
    
1. Elevando ambos os lados ao quadrado: $$2 = \frac{a^2}{b^2}$$   
2. Multiplicando cruzado: $$a^2 = 2b^2$$   
3. _Primeira conclusão:_ A equação acima indica que $a^2$ é par. Se o quadrado de um número é par, a base também é. Logo, _a_ é par. Sendo _a_ par, podemos escrevê-lo como $a = 2k$.
4. Substituindo _a_ na equação do passo 2: $$(2k)^2 = 2b^2$$
5. $$4k^2 = 2b^2$$
6. Dividindo por 2: $$b^2 = 2k^2$$
7. _Segunda conclusão:_ A equação indica que $b^2$ também é par, logo, _b_ é par.

_Encontrar a Contradição:_ 
- Deduzimos que tanto _a_ quanto _b_ são números pares, o que significa que ambos são divisíveis por 2.
- _Absurdo:_ Isso contradiz diretamente a nossa condição inicial de que a fração $\frac{a}{b}$ era irredutível (sem divisores em comum). Essa contradição destrói a premissa de que $\sqrt{2}$ é racional, provando, portanto, que ele é irracional.
```
````