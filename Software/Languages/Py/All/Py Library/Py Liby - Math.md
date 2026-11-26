
---

````ad-quote
title:
##### **Intro )** - Math Liby
```ad-quote
title:
<p align="justify">A Biblioteca Math é um componente fundamental da biblioteca padrão do Python, oferecendo um vasto conjunto de funções para a execução de operações matemáticas em números de ponto flutuante. Desde cálculos trigonométricos básicos até funções mais especializadas, o Módulo Math é uma ferramenta indispensável para desenvolvedores, cientistas de dados e qualquer pessoa que trabalhe com cálculos numéricos em Python.</p>

<p align="justify">Este guia detalha todas as funções disponíveis na Biblioteca Math, organizadas em categorias para facilitar a compreensão e a consulta.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Funções de Teoria dos Números e Representação

```ad-quote
title:
<p align="justify">Essas funções lidam com as propriedades e a representação de números.</p>
```

```ad-quote
title:

| Função | Descrição |
|---|---|
| `ceil(x)` | Retorna o menor inteiro maior ou igual a x. |
| `comb(n, k)` | Retorna o número de maneiras de escolher k itens de n itens sem repetição e sem ordem (combinação). |
| `copysign(x, y)` | Retorna um número de ponto flutuante com a magnitude de x e o sinal de y. |
| `fabs(x)` | Retorna o valor absoluto de x. |
| `factorial(n)` | Retorna o fatorial de um inteiro não negativo n. |
| `floor(x)` | Retorna o maior inteiro menor ou igual a x. |
| `fmod(x, y)` | Retorna o resto da divisão de x por y, conforme definido pela biblioteca C. |
| `frexp(x)` | Retorna a mantissa e o expoente de x como um par (m, e). |
| `fsum(iterable)` | Retorna uma soma de ponto flutuante precisa dos valores em um iterável. |
| `gcd(*integers)` | Retorna o máximo divisor comum dos argumentos inteiros. |
| `isclose(a, b, *, rel_tol=1e-09, abs_tol=0.0)` | Retorna True se os valores a e b estiverem próximos, False caso contrário. |
| `isfinite(x)` | Retorna True se x não for um infinito nem um NaN (Não é um Número). |
| `isinf(x)` | Retorna True se x for um infinito positivo ou negativo. |
| `isnan(x)` | Retorna True se x for um NaN. |
| `isqrt(n)` | Retorna a raiz quadrada inteira de um inteiro não negativo n. |
| `lcm(*integers)` | Retorna o mínimo múltiplo comum dos argumentos inteiros. |
| `ldexp(x, i)` | Retorna x * (2**i). É o inverso de frexp(). |
| `modf(x)` | Retorna as partes fracionária e inteira de x. |
| `nextafter(x, y)` | Retorna o próximo valor de ponto flutuante representável depois de x na direção de y. |
| `perm(n, k=None)` | Retorna o número de maneiras de escolher k itens de n itens sem repetição e com ordem (permutação). |
| `prod(iterable, *, start=1)` | Calcula o produto de todos os elementos no iterável de entrada. |
| `remainder(x, y)` | Retorna o resto da divisão no padrão IEEE 754 de x em relação a y. |
| `trunc(x)` | Retorna o valor de x com a parte fracionária removida, deixando a parte inteira. |
| `ulp(x)` | Retorna o valor do bit menos significativo de um ponto flutuante x. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Funções de Potência e Logarítmicas

```ad-quote
title:
<p align="justify">Funções relacionadas a operações exponenciais e logarítmicas.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `exp(x)` | Retorna e elevado à potência x. |
| `expm1(x)` | Retorna e elevado à potência x, menos 1. |
| `log(x[, base])` | Com um argumento, retorna o logaritmo natural de x (base e). Com dois argumentos, retorna o logaritmo de x na base especificada. |
| `log1p(x)` | Retorna o logaritmo natural de 1+x (base e). |
| `log2(x)` | Retorna o logaritmo de base 2 de x. |
| `log10(x)` | Retorna o logaritmo de base 10 de x. |
| `pow(x, y)` | Retorna x elevado à potência y. |
| `sqrt(x)` | Retorna a raiz quadrada de x. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Funções Trigonométricas

```ad-quote
title:
<p align="justify">Funções para cálculos envolvendo ângulos e suas relações em triângulos.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `acos(x)` | Retorna o arco cosseno de x, em radianos. |
| `asin(x)` | Retorna o arco seno de x, em radianos. |
| `atan(x)` | Retorna o arco tangente de x, em radianos. |
| `atan2(y, x)` | Retorna atan(y / x), em radianos. |
| `cos(x)` | Retorna o cosseno de x radianos. |
| `dist(p, q)` | Retorna a distância euclidiana entre dois pontos p e q. |
| `hypot(*coordinates)` | Retorna a norma euclidiana, sqrt(sum(x*x for x in coordinates)). |
| `sin(x)` | Retorna o seno de x radianos. |
| `tan(x)` | Retorna a tangente de x radianos. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Funções de Conversão Angular

```ad-quote
title:
<p align="justify">Funções para converter entre diferentes unidades de medida de ângulos.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `degrees(x)` | Converte o ângulo x de radianos para graus. |
| `radians(x)` | Converte o ângulo x de graus para radianos. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Funções Hiperbólicas

```ad-quote
title:
<p align="justify">Análogas às funções trigonométricas, mas baseadas em hipérboles.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `acosh(x)` | Retorna o cosseno hiperbólico inverso de x. |
| `asinh(x)` | Retorna o seno hiperbólico inverso de x. |
| `atanh(x)` | Retorna a tangente hiperbólica inversa de x. |
| `cosh(x)` | Retorna o cosseno hiperbólico de x. |
| `sinh(x)` | Retorna o seno hiperbólico de x. |
| `tanh(x)` | Retorna a tangente hiperbólica de x. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Funções Especiais

```ad-quote
title:
<p align="justify">Funções matemáticas que não se enquadram nas categorias anteriores, muitas vezes usadas em estatística e física.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `erf(x)` | Retorna a função de erro em x. |
| `erfc(x)` | Retorna a função de erro complementar em x. |
| `gamma(x)` | Retorna a função gama em x. |
| `lgamma(x)` | Retorna o logaritmo natural do valor absoluto da função gama em x. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Constantes

```ad-quote
title:
<p align="justify">A biblioteca math também fornece constantes matemáticas importantes.</p>
```
```ad-quote
title:

| Constante | Descrição | Valor Aproximado |
|---|---|---|
| `pi` | A constante matemática pi. | 3.141592... |
| `e` | A constante matemática e (base do logaritmo natural). | 2.718281... |
| `tau` | A constante matemática tau (2 * pi). | 6.283185... |
| `inf` | Um valor de ponto flutuante para infinito positivo. | |
| `nan` | Um valor de ponto flutuante para "Não é um Número" (NaN). | |

```
````

---
