
---

```ad-quote
title: **Def**

**Probabilidade Condicional** e seus conceitos derivados são ferramentas para calcular a probabilidade de eventos quando já possuímos alguma informação prévia ou quando analisamos a ocorrência simultânea de múltiplos eventos.

**Importância:**
- Modela cenários realistas onde uma informação afeta outra.
- Base para o Teorema de Bayes e inferência estatística.
- Permite calcular a probabilidade de sequências de eventos.
```

---

```ad-example

#### **Probabilidade Condicional**
```

---

```ad-quote
title: **Def**

A **Probabilidade Condicional** calcula a chance de um evento $E$ ocorrer, **dado que** um outro evento $F$ já aconteceu. É a atualização da probabilidade com base em nova informação.

**Características:**

✔️ **Vantagens:**
- Ajusta probabilidades com base em conhecimento parcial.
- Fundamental para modelar eventos dependentes.

❌ **Limitações:**
- Requer que o evento condicionante ($F$) tenha probabilidade maior que zero.
- Frequentemente confundida com a probabilidade da interseção.
```
##### **Fórmula:**

```ad-quote
title: **Def**

**Fórmula Base:**

1. $$P(E|F) = \frac{P(E \cap F)}{P(F)}$$

**Caso especial (espaço amostral equiprovável):**

2. $$P(E|F) = \frac{\text{Número de resultados em } E \cap F}{\text{Número de resultados em } F} = \frac{|E \cap F|}{|F|}$$

**Onde:**
- $P(E|F)$ = probabilidade de $E$ ocorrer dado que $F$ ocorreu.
- $P(E \cap F)$ = probabilidade de $E$ e $F$ ocorrerem juntos.
- $P(F)$ = probabilidade do evento condicionante.
```

> [!error] **Exemplo**:

```ad-quote
title: **Def**

**Pergunta:** Qual a probabilidade de obter um "3" no lançamento de um dado, sabendo que o resultado foi ímpar?

---

- **Evento E:** Obter "3" $\rightarrow E = \{3\}$
- **Evento F:** Obter número ímpar $\rightarrow F = \{1, 3, 5\}$
- **Interseção $E \cap F$:** $\{3\}$

**Cálculo:** 

1. $$P(E|F) = \frac{|E \cap F|}{|F|} = \frac{1}{3}$$
```

---

```ad-example

#### **Independência de Eventos**
```

---

```ad-quote
title: **Def**

Dois eventos são **independentes** se a ocorrência de um não altera a probabilidade de ocorrência do outro.

**Características:**

✔️ **Vantagens:**
- Simplifica drasticamente o cálculo da probabilidade conjunta (interseção).

❌ **Limitações:**
- Assumir independência quando não há é um erro comum e grave na modelagem.
- Eventos disjuntos (mutuamente exclusivos) com $P>0$ **nunca** são independentes.
```
##### **Condição de Teste:**

```ad-quote
title: **Def**

Dois eventos $E$ e $F$ são independentes se qualquer uma destas condições for verdadeira:

1. $$P(E|F) = P(E)$$

ou, de forma equivalente:

2. $$P(E \cap F) = P(E) \cdot P(F)$$
```

> [!error] **Exemplo**:

```ad-quote
title: **Def**

**Eventos:** Lançar uma moeda e um dado.
- **E:** Obter "Cara" na moeda $\rightarrow P(E) = 1/2$
- **F:** Obter "5" no dado $\rightarrow P(F) = 1/6$

---

**Probabilidade de ambos ocorrerem:** 

1. $$P(E \cap F) = P(E) \cdot P(F) = \frac{1}{2} \cdot \frac{1}{6} = \frac{1}{12}$$
```

---

```ad-example

 #### **Teorema da Multiplicação (Regra do Produto)**
```

---

```ad-quote
title: **Def**

É uma reorganização da fórmula da probabilidade condicional, usada para calcular a probabilidade da **interseção** de eventos (a chance de todos ocorrerem).

**Características:**

✔️ **Vantagens:**
- Essencial para calcular a probabilidade de eventos sequenciais.
- Generaliza para múltiplos eventos.

❌ **Limitações:**
- Exige o conhecimento das probabilidades condicionais em cada etapa.
```

##### **Fórmula:**

```ad-quote
title: **Def**

**Para 2 eventos (dependentes):**

1. $$P(A \cap B) = P(A) \cdot P(B|A)$$

**Para 3 eventos (dependentes):**

2. $$P(A \cap B \cap C) = P(A) \cdot P(B|A) \cdot P(C|A \cap B)$$
```

> [!error] **Exemplo**:

```ad-quote
title: **Def**

**Pergunta:** Qual a probabilidade de retirar 2 cartas de Rei de um baralho de 52 cartas, sem reposição?

---
- **A:** Tirar um Rei na 1ª carta $\rightarrow P(A) = 4/52$
- **B|A:** Tirar um Rei na 2ª carta, dado que a 1ª foi um Rei $\rightarrow P(B|A) = 3/51$

**Cálculo da Interseção:** 

1. $$P(A \cap B) = P(A) \cdot P(B|A) = \frac{4}{52} \cdot \frac{3}{51} \approx 0.45\%$$
```

---
