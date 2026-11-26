
---

```ad-quote
title: **Def**

O **Teorema de Bayes** é uma fórmula fundamental que descreve como **atualizar a probabilidade de uma hipótese com base em novas evidências**. Em vez de calcular a chance de um efeito dada uma causa, ele nos permite calcular a probabilidade da causa, dado que observamos o efeito.

**Importância:**
- Permite "inverter" probabilidades condicionais.
- É a base da estatística Bayesiana, um campo focado na atualização de crenças.
- Essencial em diagnósticos médicos, filtros de spam, inteligência artificial e inferência científica.
```

---

```ad-example

#### **Teorema de Bayes**
```

---

```ad-quote
title: **Def**

O teorema calcula a **probabilidade posterior** de um evento $A$ (a hipótese), após a observação de um evento $B$ (a evidência), usando a **probabilidade a priori** de $A$ e a **verossimilhança** de observar $B$ se $A$ for verdadeiro.

**Características:**

✔️ **Inversão de Probabilidades:** Sua principal força é calcular $P(\text{Causa}|\text{Efeito})$ a partir de $P(\text{Efeito}|\text{Causa})$.
✔️ **Atualização de Crenças:** Formaliza o processo de aprendizado, onde uma crença inicial (*a priori*) é refinada em uma crença final (*a posteriori*) após a coleta de dados.
✔️ **Quantificação da Incerteza:** Fornece um resultado probabilístico sobre a validade de uma hipótese, em vez de uma resposta binária (certo/errado).
```

##### **Fórmula:**

```ad-quote
title: **Def**

**Forma Padrão:**
$$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$$

**Onde:**
- $P(A|B)$ = **Probabilidade Posterior:** A probabilidade atualizada de $A$ após observar $B$.
- $P(B|A)$ = **Verossimilhança (Likelihood):** A probabilidade de observar $B$ se $A$ for verdadeiro.
- $P(A)$ = **Probabilidade a Priori:** A probabilidade inicial de $A$ (antes da evidência).
- $P(B)$ = **Evidência (Probabilidade Marginal):** A probabilidade total de observar $B$. Frequentemente calculada usando a Lei da Probabilidade Total.

**Forma Generalizada (para uma partição $A_1, A_2, \dots, A_n$):**
$$P(A_i|B) = \frac{P(B|A_i) \cdot P(A_i)}{\sum_{j=1}^{n} P(B|A_j) \cdot P(A_j)}$$
```

---

> [!error] **Exemplo: Teste Diagnóstico**

```ad-quote
title: **Def**

**Problema:** Uma doença afeta 1% da população. Um teste para detectá-la tem 99% de acerto (se a pessoa está doente, dá positivo) e 99% de especificidade (se não está, dá negativo, ou seja, 1% de falso positivo). Se você testar positivo, qual a chance real de ter a doença?

---
**Eventos:**
- $D$: A pessoa tem a doença. ($P(D) = 0.01$)
- $D^c$: A pessoa não tem a doença. ($P(D^c) = 0.99$)
- $Pos$: O teste deu positivo.

**Probabilidades Conhecidas:**
- $P(Pos|D) = 0.99$ (Sensibilidade)
- $P(Pos|D^c) = 0.01$ (Taxa de Falso Positivo)

**Cálculo:**
1. **Calcular a Evidência $P(Pos)$ (Probabilidade Total):**
$$P(Pos) = P(Pos|D)P(D) + P(Pos|D^c)P(D^c)$$
$$P(Pos) = (0.99 \cdot 0.01) + (0.01 \cdot 0.99) = 0.0099 + 0.0099 = 0.0198$$

2. **Aplicar o Teorema de Bayes:**
$$P(D|Pos) = \frac{P(Pos|D) \cdot P(D)}{P(Pos)} = \frac{0.99 \cdot 0.01}{0.0198} = \frac{0.0099}{0.0198} = 0.5$$

**Resposta:** Mesmo com um teste 99% preciso, a chance de você ter a doença, dado um resultado positivo, é de apenas **50%**. Isso ocorre porque a baixa probabilidade inicial (priori) da doença tem um peso enorme no resultado.
```

---

> [!error] **Exemplo: Alarme de Incêndio**

```ad-quote
title: **Def**

**Problema:** A probabilidade de haver um incêndio em um dia é de 1%. Um alarme de incêndio soa em 99% das vezes que há fogo, mas também soa em 5% dos dias sem fogo (alarme falso). Se o alarme soar, qual a chance real de haver um incêndio?

---
**Eventos:**
- $F$: Há um incêndio. ($P(F) = 0.01$)
- $F^c$: Não há incêndio. ($P(F^c) = 0.99$)
- $A$: O alarme soa.

**Probabilidades Conhecidas:**
- $P(A|F) = 0.99$
- $P(A|F^c) = 0.05$

**Cálculo:**
1. **Calcular a Evidência $P(A)$ (Probabilidade Total):**
$$P(A) = P(A|F)P(F) + P(A|F^c)P(F^c)$$
$$P(A) = (0.99 \cdot 0.01) + (0.05 \cdot 0.99) = 0.0099 + 0.0495 = 0.0594$$

2. **Aplicar o Teorema de Bayes:**
$$P(F|A) = \frac{P(A|F) \cdot P(F)}{P(A)} = \frac{0.99 \cdot 0.01}{0.0594} = \frac{0.0099}{0.0594} \approx 0.1667$$

**Resposta:** Se o alarme soar, a probabilidade de realmente haver um incêndio é de apenas **16.7%**. A alta taxa de alarmes falsos em dias comuns supera a precisão do alarme durante um incêndio real.
```

---
