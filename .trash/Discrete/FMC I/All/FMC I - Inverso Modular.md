---
banner: "![[Pasted image 20251201181229.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O Conceito Teórico

```ad-quote
title:
<p align="justify">Diferente da aritmética real, onde o inverso de um número é uma fração (ex: o inverso de 5 é 0,2), na Aritmética Modular trabalha-se apenas com números inteiros.</p>
```



```ad-quote
title:
###### Definição Algébrica
```

```ad-quote
title:
O Inverso Modular de um número a (em um módulo m) é um inteiro $\bar{a}$ que satisfaz a propriedade de anulação:
```

```ad-quote
title:
$$a \cdot \bar{a} \equiv 1 \pmod m$$
```

```ad-quote
title:
###### A Regra de Existência (Teorema da Coprimalidade)
```

```ad-quote
title:
<p align="justify">A existência do inverso não é garantida para todos os números. Ela depende estritamente da relação genética entre o número e o módulo.</p>
```

```ad-quote
title:
Teorema: O inverso existe se, e somente se:
$$\text{mdc}(a, m) = 1$$
```

```ad-quote
title:
Conclusões Lógicas:
- Primos Entre Si (MDC = 1): Existe um único inverso.
- Não Primos (MDC > 1): O inverso é inexistente (Impossível).
```
````

---

```ad-done
title:

##### **Fase 02 ) -** MDC = 1

```

---

````ad-quote
title:

##### **A ) -** Método da Soma 

```ad-quote
title:
Princípio: Em aritmética modular, $b$ é equivalente a $b + m$, $b + 2m$, etc. O objetivo é encontrar um fator $k$ tal que a divisão por $a$ seja exata.
```

```ad-quote
title:
Definição Algébrica:

- $$ax \equiv (b + k \cdot m) \pmod m$$

Onde buscamos o menor $k \in \mathbb{N}$ tal que:

- $$a \mid (b + k \cdot m)$$
```

```ad-quote
title:
Cálculo da Solução:

Uma vez encontrado o $k$ satisfatório, a congruência linear torna-se uma divisão simples nos inteiros:

- $$x = \frac{b + k \cdot m}{a}$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **B )** - Modelo Geral - mdc(a, m) = 1

```ad-quote
title:
###### O Problema
```

```ad-quote
title:

- $$ax \equiv b \pmod m$$
```

```ad-quote
title:
###### Passo 1 - Algoritmo de Euclides Estendido
```

```ad-quote
title:
Utilizamos o algoritmo estendido para expressar o mdc (1) como Combinação Linear de $a$ e $m$ (Identidade de Bézout)

- $$a \cdot s + m \cdot t = 1$$

Escrevendo em forma de congruência (módulo $m$, o termo $m \cdot t$ desaparece):

- $$a \cdot s \equiv 1 \pmod m$$

Neste ponto, como o resultado é 1, o coeficiente $s$ recebe o nome especial de INVERSO MULTIPLICATIVO ($\bar{a}$ ou $a^{-1}$).
```

```ad-quote
title:
###### Passo 2 - Aplicação do Inverso
```

```ad-quote
title:
Diferente do caso expandido, não precisamos de fator de escala (pois $d=1$). Multiplicamos o INVERSO ($s$) diretamente pelo ALVO ($b$).

1. $$x \equiv s \cdot b \pmod m$$

Calculando o $x_0$ (Solução Particular):

- $$x_0 = s \cdot b$$
```

```ad-quote
title:
###### Passo 3 - Normalização e Solução Única
```

```ad-quote
title:
Como $\text{mdc}(a, m) = 1$, existe apenas UMA solução congruente módulo $m$.

<p align="justify">Se o valor encontrado for negativo ou maior que o módulo, realizamos o ajuste:</p>

- $$x_{final} \equiv x_0 \pmod m$$

<p align="justify">Organizando o conjunto:</p>

- $$S = \{x_{final}\}$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **C )** - Aplicação na Resolução de Equações

```ad-quote
title:
<p align="justify">Com o inverso calculado, a resolução de equações lineares de congruência torna-se uma operação direta de multiplicação.</p>
```

```ad-quote
title:
###### Fórmula Geral
```

```ad-quote
title:
- $$x \equiv (\text{Inverso}) \cdot (\text{Alvo}) \pmod m$$

- $$x \equiv (\bar{a}) \cdot b \pmod m$$
```
````

---

```ad-done
title:

##### **Fase 02 ) -** MDC > 1

```

---

````ad-quote
title:
##### **A )** - Modelo Geral - mdc(a, m) > 1

```ad-quote
title:
###### O Problema
```

```ad-quote
title:

- $$ax \equiv b \pmod m$$
```

```ad-quote
title:
###### Passo 1 - Algoritmo de Euclides Estendido
```

```ad-quote
title:
Utilizamos o algoritmo estendido para expressar o mdc ($d$) como Combinação Linear de $a$ e $m$ (Identidade de Bézout)

- $$a \cdot s + m \cdot t = d$$

Escrevendo em forma de congruência (módulo $m$, o termo $m \cdot t$ desaparece):

- $$a \cdot s \equiv d \pmod m$$

Neste ponto, $s$ é o coeficiente que leva o $a$ ao MDC.
```

```ad-quote
title:
###### Passo 2 - Ajuste para o Alvo
```

```ad-quote
title:
Nós temos o resultado $d$, mas queremos o resultado $b$. Calculamos o Fator de Escala $k$:

- $$k = \frac{b}{d}$$

Devemos multiplicar toda a congruência anterior por esse fator $k$:

1. $$k \cdot [a \cdot s] \equiv k \cdot [d] \pmod m$$
2. $$a \cdot (s \cdot k) \equiv b \pmod m$$

Calculando o $x_0$:

- $$x_0 = s \cdot k$$
```

```ad-quote
title:
###### Passo 3 - Normalização e Solução Geral
```

```ad-quote
title:

Agora, encontramos as outras $d-1$ soluções somando o passo.

- $$\text{Passo} = \frac{m}{d}$$

<p align="justify">Gerando o conjunto solução s</p>

1. $$x_1 = x_0$$
2. $$x_2 = x_0 + \text{Passo}$$
3. $$x_3 = x_0 + 2 \cdot \text{Passo}$$
...
4. $$x_d = x_0 + (d-1) \cdot \text{Passo}$$

<p align="justify">Organizando o conjunto:</p>

- $$S = \{x_1, x_2, \dots, x_d\}$$
```
````

---

```ad-done
title:

##### **Fase 03 ) -** Resoluções

```

---

````ad-quote
title:

##### **03 )** - Método B: O Algoritmo de Euclides Estendido

```ad-quote
title:
<p align="justify">Para grandes números ou formalizações acadêmicas, utiliza-se a extensão do cálculo do MDC para expressar o número 1 como uma combinação linear.</p>
```


```ad-quote
title:
###### Exemplo de Execução
```

```ad-quote
title:
Encontrar o inverso de 12 módulo 67.
```

```ad-quote
title:
Fase 1: Descida (Divisões Sucessivas)
Escreve-se o resto em função dos operandos:
1. $$67 = 5 \cdot 12 + 7 \rightarrow \mathbf{7} = 67 - 5 \cdot 12$$
2. $$12 = 1 \cdot 7 + 5 \rightarrow \mathbf{5} = 12 - 1 \cdot 7$$
3. $$7 = 1 \cdot 5 + 2 \rightarrow \mathbf{2} = 7 - 1 \cdot 5$$
4. $$5 = 2 \cdot 2 + 1 \rightarrow \mathbf{1} = 5 - 2 \cdot 2$$
```

```ad-quote
title:
Fase 2: Subida (Substituição Reversa)
Parte-se da equação do 1 e substitui-se os restos anteriores:

Base:
$$1 = 5 - 2 \cdot (\mathbf{2})$$

Substituindo o 2:
$$1 = 5 - 2 \cdot (7 - 1 \cdot 5)$$
$$1 = 3 \cdot 5 - 2 \cdot 7$$

Substituindo o 5:
$$1 = 3 \cdot (12 - 1 \cdot 7) - 2 \cdot 7$$
$$1 = 3 \cdot 12 - 5 \cdot 7$$

Substituindo o 7:
$$1 = 3 \cdot 12 - 5 \cdot (67 - 5 \cdot 12)$$
$$1 = 28 \cdot 12 - 5 \cdot 67$$
```

```ad-quote
title:
###### Conclusão Algébrica
```

```ad-quote
title:
<p align="justify">A equação final indica que 28 vezes 12 menos um múltiplo de 67 resulta em 1. No contexto modular, o termo múltiplo de 67 torna-se nulo.</p>
```

```ad-quote
title:
$$28 \cdot 12 \equiv 1 \pmod{67}$$
```

```ad-quote
title:
O inverso é 28.
```
````
