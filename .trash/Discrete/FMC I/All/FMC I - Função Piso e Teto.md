---
banner: "![[Pasted image 20251024201601.png]]"
---

---

````ad-quote
title:

##### **Intro )** - As Ferramentas de Conversão Real-Inteiro

```ad-quote
title:
<p align="justify">Na matemática e computação, precisamos frequentemente "converter" um número real (como 3.14) em um inteiro. As funções PISO, TETO e TRUNCAMENTO são as ferramentas precisas e inequívocas para isso. Elas estabelecem uma relação formal entre o contínuo (números reais, R) e o discreto (números inteiros, Z). O Tópico 16 mostrou que a escolha entre elas (especialmente PISO vs. TRUNCAMENTO) tem consequências matemáticas profundas.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Definições Formais

```ad-quote
title:
###### **Função Piso - Floor**
```

```ad-quote
title:
Pense no PISO como "arredondar para baixo" ou "o elevador que SEMPRE desce" para o próximo inteiro na direção de menos infinito ($-\infty$).
```

```ad-quote
title:
A função PISO de um número real $x$, denotada por $\lfloor x \rfloor$, é definida como o MAIOR inteiro que é MENOR OU IGUAL a $x$.
```

```ad-quote
title:
1. $$\lfloor x \rfloor = \max \{ n \in \mathbb{Z} \mid n \le x \}$$
```

```ad-quote
title:
###### **Função Teto - Ceiling**
```

```ad-quote
title:
Pense no TETO como "arredondar para cima" ou "o elevador que SEMPRE sobe" para o próximo inteiro na direção de mais infinito ($+\infty$).
```

```ad-quote
title:
A função TETO de um número real $x$, denotada por $\lceil x \rceil$, é definida como o MENOR inteiro que é MAIOR OU IGUAL a $x$.
```

```ad-quote
title:
1. $$\lceil x \rceil = \min \{ n \in \mathbb{Z} \mid n \ge x \}$$
```

```ad-quote
title:
###### **Função Truncamento - Truncate**
```

```ad-quote
title:
<p align="justify">Pense no TRUNCAMENTO como uma "compressão" da linha numérica que empurra todos os números (positivos e negativos) em direção ao ponto 0.</p>
```

```ad-quote
title:
A função TRUNCAMENTO de um número real $x$, denotada por $\text{trunc}(x)$ (ou às vezes $\text{int}(x)$ em linguagens de programação), é definida como o inteiro obtido ao "cortar" a parte fracionária, movendo o número EM DIREÇÃO A ZERO.
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Tabela Comparativa (Visualização)

```ad-quote
title:
<p align="justify">A diferença crucial entre as três funções torna-se óbvia com números negativos.</p>
```

```ad-quote
title:
| Valor de $x$ | Exemplo na Linha Numérica | PISO $\lfloor x \rfloor$ (Para $-\infty$) | TETO $\lceil x \rceil$ (Para $+\infty$) | TRUNCAMENTO $\text{trunc}(x)$ (Para $0$) |
| :--- | :--- | :--- | :--- | :--- |
| $x = 2.8$ | `... [2] ... (2.8) ... [3] ...` | $2$ | $3$ | $2$ |
| $x = -2.8$| `... [-3] ... (-2.8) ... [-2] ...`| $-3$ | $-2$ | $-2$ |
| $x = 2$ | `... [2] ...` | $2$ | $2$ | $2$ |
| $x = -2$ | `... [-2] ...` | $-2$ | $-2$ | $-2$ |
```

```ad-quote
title:
###### **Observações CRUCIAIS da Tabela**
```

```ad-quote
title:
Para números POSITIVOS ($x \ge 0$), PISO e TRUNCAMENTO são idênticos: $\lfloor 2.8 \rfloor = 2$ e $\text{trunc}(2.8) = 2$.
```

```ad-quote
title:
Para números NEGATIVOS ($x < 0$), TETO e TRUNCAMENTO são idênticos: $\lceil -2.8 \rceil = -2$ e $\text{trunc}(-2.8) = -2$.
```

```ad-quote
title:
A GRANDE DIFERENÇA (do Tópico 16) está entre PISO e TRUNCAMENTO para números negativos: $\lfloor -2.8 \rfloor = -3$, mas $\text{trunc}(-2.8) = -2$.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Propriedades e Identidades (Piso e Teto)

```ad-quote
title:
###### **A) As Desigualdades Fundamentais**
```

```ad-quote
title:
<p align="justify">As definições podem ser reescritas como desigualdades, que são extremamente úteis em provas:</p>
```

```ad-quote
title:
1. $\lfloor x \rfloor \le x < \lfloor x \rfloor + 1$
```

```ad-quote
title:
2. $x - 1 < \lfloor x \rfloor \le x$
```

```ad-quote
title:
3. $\lceil x \rceil - 1 < x \le \lceil x \rceil$
```

```ad-quote
title:
4. $x \le \lceil x \rceil < x + 1$
```

```ad-quote
title:
###### **B) A Relação de Oposição (A "Inversão" Negativa)**
```

```ad-quote
title:
<p align="justify">Esta é a identidade que formaliza a intuição de que PISO e TETO são "opostos". Uma "inverte" a outra através da negação.</p>
```

```ad-quote
title:
$$\lfloor x \rfloor = -\lceil -x \rceil$$
```

```ad-quote
title:
$$\lceil x \rceil = -\lfloor -x \rfloor$$
```

```ad-quote
title:
###### **Prova com Exemplo ($x = 2.8$):**
```

```ad-quote
title:
1. $$\lfloor 2.8 \rfloor = 2$$

2. $$-\lceil -2.8 \rceil = -(-2) = 2$$

(Funciona!)
```

```ad-quote
title:
###### **C) Translação por Inteiros**
```

```ad-quote
title:
Se somarmos um inteiro $n$ dentro da função PISO ou TETO, é o mesmo que somá-lo fora dela. (Nota: esta propriedade NÃO é verdadeira para a função TRUNCAMENTO com números negativos).
```

```ad-quote
title:
$$\lfloor x + n \rfloor = \lfloor x \rfloor + n, \quad \text{para } n \in \mathbb{Z}$$
```

```ad-quote
title:
$$\lceil x + n \rceil = \lceil x \rceil + n, \quad \text{para } n \in \mathbb{Z}$$
```

```ad-quote
title:
###### **Exemplo:**
```

```ad-quote
title:
1. $$\lfloor 2.8 + 5 \rfloor = \lfloor 7.8 \rfloor = 7$$

2. $$\lfloor 2.8 \rfloor + 5 = 2 + 5 = 7$$

(Funciona!)
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Aplicações
```ad-quote
title:
###### **A) A Implementação CORRETA do Algoritmo da Divisão (Via PISO)**
```

```ad-quote
title:
<p align="justify">Como vimos no Tópico 16, a função PISO é a ferramenta matemática EXATA que implementa o Algoritmo da Divisão (Tópico 15) de forma consistente com a regra $0 \le r < |b|$.</p>
```

```ad-quote
title:
<p align="justify">O quociente $q$ e o resto $r$ (para $b > 0$) podem ser definidos usando a função PISO:</p>
```

```ad-quote
title:
Quociente: $q = \lfloor a/b \rfloor$
Resto: $r = a - b \cdot \lfloor a/b \rfloor$
```

```ad-quote
title:
###### **Teste (O Caso Difícil: $a = -10, b = 3$):**
```

```ad-quote
title:
$q = \lfloor -10 / 3 \rfloor = \lfloor -3.333... \rfloor = -4$
$r = -10 - (3 \cdot -4) = -10 - (-12) = 2$
```

```ad-quote
title:
###### **Veredito:**
```

```ad-quote
title:
<p align="justify">O resultado ($q = -4, r = 2$) é o ÚNICO que satisfaz a definição matemática. Esta é a abordagem do Python (// e %).</p>
```

```ad-quote
title:
###### **B) A Implementação INCONSISTENTE (Via TRUNCAMENTO)**
```

```ad-quote
title:
<p align="justify">Isto é o que acontece ao usar a abordagem do C ou Java, que usam TRUNCAMENTO para a divisão inteira.</p>
```

```ad-quote
title:
<p align="justify">O quociente $q$ e o resto $r$ são definidos assim:</p>
```

```ad-quote
title:
Quociente: $q = \text{trunc}(a/b)$
Resto: $r = a - b \cdot \text{trunc}(a/b)$
```

```ad-quote
title:
###### **Teste (O Caso Difícil: $a = -10, b = 3$):**
```

```ad-quote
title:
$q = \text{trunc}(-10 / 3) = \text{trunc}(-3.333...) = -3$
$r = -10 - (3 \cdot -3) = -10 - (-9) = -1$
```

```ad-quote
title:
###### **Veredito:**
```

```ad-quote
title:
<p align="justify">O resultado ($q = -3, r = -1$) VIOLA a regra de ouro do Tópico 15, que proíbe um resto negativo.</p>
```

```ad-quote
title:
###### **C) Aplicação Prática da Função TETO**
```

```ad-quote
title:
<p align="justify">A função TETO é a solução para qualquer problema do tipo "quantas unidades são necessárias para cobrir uma quantidade?".</p>
```

```ad-quote
title:
Exemplo: Você precisa armazenar 100 itens. Cada caixa armazena 8 itens. Quantas caixas você precisa comprar?
Cálculo: $100 / 8 = 12.5$
Análise:
Se usarmos PISO: $\lfloor 12.5 \rfloor = 12$ caixas. (Isso só armazena $12 \times 8 = 96$ itens. Faltam 4 itens).
Se usarmos TETO: $\lceil 12.5 \rceil = 13$ caixas. (Isso armazena $13 \times 8 = 104$ itens. Cobre todos os 100 itens com sobra).
```

```ad-quote
title:
<p align="justify">A função TETO é a ferramenta correta para problemas de alocação onde "faltar" não é uma opção.</p>
```
````

---