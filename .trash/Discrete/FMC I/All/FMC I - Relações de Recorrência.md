
---

````ad-quote
title:

##### **01 )** - A Lógica da Fórmula Geral

```ad-quote
title:
<p align="justify">A fórmula geral pode parecer intimidadora à primeira vista, mas ela conta uma história muito lógica sobre o processo recursivo. Vamos decompô-la para entender o que cada parte significa.</p>
```

```ad-quote
title:
A fórmula é a solução para qualquer recorrência no formato:

1. $$S(n)=C \cdot S(n-1)+g(n)$$

Pense nela como o resultado de um processo que acontece em etapas. A cada etapa n, você pega o resultado da etapa anterior $S(n-1)$, o multiplica por um fator de escala C, e então adiciona uma nova quantidade g(n).
```

```ad-quote
title:
A solução geral, elegantemente calcula o resultado final desse processo e pode ser dividida em duas partes principais.

1. $$S(n) = C^{n-1} \cdot S(1) + \sum_{i=2}^{n} C^{n-i} g(i)$$
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Parte 1: A Influência do Ponto de Partida

```ad-quote
title:
Esta primeira parte da fórmula nos diz qual é o impacto do valor inicial, $S(1)$, no resultado final, $S(n)$.
```

```ad-quote
title:

1. $$C^{n-1} \cdot S(1)$$
```

```ad-quote
title:
**S(1):**
- É o seu ponto de partida, o valor "semente".

**Por que $C^{n-1}$?:**
- Em cada etapa da recorrência, de $S(1)$ até $S(n)$, o valor da etapa anterior é multiplicado por C.
- Para calcular $S(2)$, $S(1)$ é multiplicado por C uma vez.
- Para calcular $S(3)$, o resultado de $S(2)$ (que já continha $S(1) \cdot C$) é multiplicado por C de novo, resultando em $S(1) \cdot C^2$.
- Para chegar a $S(n)$ a partir de $S(1)$, você aplica essa multiplicação n-1 vezes.

**Intuição:**
- Imagine que você fez um investimento inicial de $S(1)$ em uma conta que rende juros. O termo C seria como (1 + taxa de juros). Esta parte da fórmula calcula quanto valeria esse investimento inicial sozinho, após n-1 períodos, sem que nada mais fosse adicionado. É a "propagação" pura do valor inicial ao longo do tempo.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Parte 2: A Soma das Contribuições de Cada Etapa
```ad-quote
title:

1. $$\sum_{i=2}^{n} C^{n-i} g(i)$$
```

```ad-quote
title:
Esta segunda parte é a mais engenhosa. Ela calcula o impacto acumulado de tudo o que foi adicionado em cada etapa do processo (os termos g(n)).
```

```ad-quote
title:
**g(i):**
- É a quantidade nova que foi adicionada na etapa i. Por exemplo, g(2) foi adicionado no passo 2, g(3) no passo 3, e assim por diante.

**Por que $C^{n-i}$?:**
- Este termo representa o "envelhecimento" de cada contribuição. Quando a quantidade g(i) é adicionada na etapa i, ela não fica parada. Nas etapas seguintes, ela também será multiplicada pelo fator C.
- A quantidade g(2) que entrou no cálculo de $S(2)$, será multiplicada por C um total de $n-2$ vezes até chegar ao resultado final de $S(n)$.
- A quantidade g(3) será multiplicada por C um total de $n-3$ vezes.
- A última quantidade, g(n), que entrou na última etapa, é multiplicada por $C^{n-n} = C^0 = 1$ (ou seja, ela não tem tempo de "envelhecer").

**Intuição:**
- Voltando à analogia do investimento. Além do seu investimento inicial, a cada período i (a partir do segundo), você faz um novo depósito de valor g(i).
- O depósito g(2) que você fez no segundo período terá $n-2$ períodos para render juros.
- O depósito g(3) terá $n-3$ períodos para render.
- E assim por diante, até o último depósito g(n) que você acabou de fazer.
- O somatório ($\sum$) simplesmente calcula o valor futuro de cada um desses depósitos e os soma para obter a contribuição total deles para o saldo final.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Conclusão: Unindo as Partes
```ad-quote
title:
A fórmula geral junta essas duas ideias:
```

```ad-quote
title:
S(n) = (Valor futuro do seu ponto de partida) + (Soma dos valores futuros de tudo que foi adicionado no caminho)
```

```ad-quote
title:
<p align="justify">Ela é poderosa porque, em vez de recalcular cada passo um por um (como fizemos no método de iteração), ela vai diretamente para a resposta final, calculando de forma inteligente como o valor inicial e cada adição subsequente contribuíram para o resultado em S(n).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Resumo do Método

```ad-quote
title:
**Verificar: **
- A recorrência é da forma $S(n)=C \cdot S(n-1)+g(n)$?

**Identificar:** 
- Encontre os valores de $C$, $g(n)$ e $S(1)$.

**Substituir:** 
- Insira esses valores na fórmula geral.

**Simplificar:** 
- Calcule as potências e, principalmente, resolva o somatório para encontrar sua forma fechada.

**Finalizar:** 
- Combine os termos para obter a solução final.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Aplicação do Método
```ad-quote
title:
###### **Passo 1: Verificar a Compatibilidade**
```

```ad-quote
title:
Primeiro, confirme se a sua recorrência se encaixa no formato exigido pela fórmula geral:

1. $$S(n)=C \cdot S(n-1)+g(n)$$

A nossa recorrência é 

2. $$S(n)=1 \cdot S(n-1)+n$$ 

Ela se encaixa perfeitamente no modelo.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Passo 2: Identificar os Componentes C, g(n) e S(1)**
```

```ad-quote
title:
Analise sua recorrência e extraia cada parte correspondente ao modelo geral:
```

```ad-quote
title:

**Identificar C:**
- C é a constante que multiplica o termo recursivo $S(n-1)$. 
- Na nossa equação, $S(n-1)$ está multiplicado por 1. Portanto, $C=1$.

**Identificar $g(n)$:**
- $g(n)$ é a função que é somada ou subtraída no final. 
- Na nossa equação, somamos n. Portanto, $g(n)=n$.

**Identificar o Caso Base:** 
- Este é o valor inicial fornecido. 
- Foi dado que $S(1)=5$. Portanto, $S(1)=5$.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Passo 3: Substituir os Componentes na Fórmula Geral**
```

```ad-quote
title:
Agora, pegue a fórmula geral e substitua os valores que você acabou de encontrar.
```

```ad-quote
title:

**A Fórmula Geral:**

1. $$S(n) = C^{n-1} \cdot S(1) + \sum_{i=2}^{n} C^{n-i} g(i)$$

Substituindo $C=1$, $S(1)=5$ e $g(i)=i$:

- Lembre-se que dentro da soma, usamos a variável do somatório, i, então g(n) se torna g(i).

2. $$S(n) = (1)^{n-1} \cdot (5) + \sum_{i=2}^{n} (1)^{n-i} \cdot (i)$$
```
````

````ad-quote
title:
```ad-quote
title:
###### **Passo 4: Simplificar a Expressão Resultante**
```

```ad-quote
title:
Esta é a etapa mais importante, onde a maior parte da álgebra acontece.
```

```ad-quote
title:

**Simplifique as Potências:**
- O termo $(1)^{n-1}$ é igual a 1. O termo $(1)^{n-i}$ dentro da soma também é igual a 1. A equação se torna:

1. $$S(n) = 1 \cdot 5 + \sum_{i=2}^{n} 1 \cdot i$$
2. $$S(n) = 5 + \sum_{i=2}^{n} i$$

**Resolva o Somatório:**
- Precisamos encontrar o valor de $\sum_{i=2}^{n} i$, que é a soma $2+3+...+n$. Usamos a fórmula da soma de Gauss: $\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$. Ajustamos para a nossa soma, que começa em 2:
  
3. $$\sum_{i=2}^{n} i = \left(\sum_{i=1}^{n} i\right) - 1 = \frac{n(n+1)}{2} - 1$$
```
````

````ad-quote
title:
```ad-quote
title:
###### **Passo 5: Combinar Tudo e Finalizar**
```

```ad-quote
title:
Agora, substitua o resultado do somatório de volta na sua equação simplificada.

1. $$S(n) = 5 + \left(\frac{n(n+1)}{2} - 1\right)$$
2. $$S(n) = \frac{n(n+1)}{2} + 4$$
   
Você chegou à mesma solução de antes, mas de uma maneira mais estruturada e formal.
```
````

---

> [!example] **_New_**

---