
---
#### **O que é Probabilidade?**

```ad-quote
title: **Def**

**Probabilidade** é o ramo da matemática que estuda a chance de ocorrência de eventos. Ela é usada para quantificar incertezas e tomar decisões baseadas em evidências incompletas ou aleatórias.

Exemplo clássico: lançar uma moeda. A chance (ou probabilidade) de sair "cara" é 50%, ou 0,5.
```

---

```ad-example

#### **Fundamentos da Probabilidade**
```

---
#### 1. **Experimento Aleatório**

```ad-quote
title: **Def**

É um processo cujo resultado **não pode ser previsto com certeza**, mesmo sob condições controladas.

Exemplos:

- Jogar um dado;

- Escolher uma carta de um baralho;

- Medir a chuva amanhã.
```

---
#### 2. **Espaço Amostral (S)**

```ad-quote
title: **Def**

É o conjunto de **todos os resultados possíveis** de um experimento aleatório.

Exemplos:

- Jogar um dado: $S={1,2,3,4,5,6}$

- Jogar uma moeda: $S={cara,coroa}$
```

---
#### 3. **Evento**

```ad-quote
title: **Def**

É qualquer **subconjunto** do espaço amostral. Pode conter um ou mais resultados.

- Evento simples: ocorre um número par ao lançar um dado → $A={1, 2, 3, 4, 5, 6}$

- Evento composto: qualquer número maior que 3 → $B={4,5,6}$
```

---

```ad-example
title: **Def**

#### **Axiomas da Probabilidade (Axiomas de Kolmogorov)**
```

---

```ad-quote
title: **Def**

Os **axiomas da probabilidade** são as regras básicas que qualquer sistema de probabilidade deve seguir. Propostos por **Andrey Kolmogorov** em 1933, são a base formal da teoria.
```

---
#### **Axioma 1 )** – Não Negatividade

```ad-quote
title: **Def**

Para qualquer evento A, sua probabilidade é um número real não negativo:
$$P(A) \geq 0$$


```

---
#### **Axioma 2 )** – Probabilidade do Espaço Amostral

```ad-quote
title: **Def**

A probabilidade de que algum resultado do espaço amostral ocorra é igual a 1:
$$
P(S) = 1$$

```

---
#### **Axioma 3 )** - Aditividade (ou Adição para eventos mutuamente exclusivos)

```ad-quote
title: **Def**

Se A e B são eventos mutuamente exclusivos (ou seja, $A \cap B = \emptyset$), então:
$$P(A \cup B) = P(A) + P(B)$$
Generalizando: se $A_1, A_2, A_3, \ldots$ forem eventos disjuntos dois a dois, então:
$$
P\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i)$$

```

---

>[!tip] #### **Consequências dos Axiomas**

---

```ad-quote
title: **Def**

A partir desses axiomas, podemos deduzir várias propriedades importantes:
```

---
#### *Probabilidade do evento complementar*

```ad-quote
title: **Def**

Se $A$ é um evento, seu complementar $A^c$ (ou seja, o evento "não $A$") tem probabilidade:
$$P(A^c) = 1 - P(A)$$

```
#### *Probabilidade do evento impossível*

```ad-quote
title: **Def**

O evento impossível (conjunto vazio $\emptyset$) tem probabilidade zero:
$$
P(\emptyset) = 0$$

```
#### *Regra da adição geral*

```ad-quote
title: **Def**

Para quaisquer dois eventos $A$ e $B$:
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

```
#### *Regra da subtração geral*

```ad-quote
title: **Def**

Para quaisquer dois eventos $A$ e $B$:
$$P(A \cap B) = P(A) + P(B) -  P(A \cup B)$$

```

---
#### `P(A ∩ B)`

```ad-quote
title: **Def**

**1. Se $A$ e $B$ são independentes:**

Se os eventos $A$ e $B$ são **independentes** (a ocorrência de um não afeta a probabilidade do outro), então:

$$P(A \cap B) = P(A) \times P(B)$$

**Exemplo**:

Se $P(A) = 0.6$ e $P(B) = 0.4$, e $A$ e $B$ são independentes:

$$P(A \cap B) = 0.6 \times 0.4 = 0.24$$

```

---

>[!error] ###### **Exemplo Prático**

---

```ad-quote
title: **Def**

Problema: 
- Lançamos um dado. Qual a probabilidade de sair um número par ou maior que 4?

Definimos os eventos:
- $A = \{2, 4, 6\}$ (números pares)
- $B = \{5, 6\}$ (números > 4)

A união: $A \cup B = \{2, 4, 5, 6\}$

Interseção: $A \cap B = \{6\}$

Aplicando a fórmula da adição:

$P(A \cup B) = P(A) + P(B) - P(A \cap B) = \frac{3}{6} + \frac{2}{6} - \frac{1}{6} = \frac{4}{6} = \frac{2}{3}$

```

---
