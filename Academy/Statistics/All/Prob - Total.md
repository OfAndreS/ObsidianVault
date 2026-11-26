

---

```ad-quote
title: **Def**

O **Teorema da Probabilidade Total** é uma ferramenta poderosa para calcular a probabilidade de um evento $A$ quando seu resultado depende de vários cenários intermediários, mutuamente exclusivos, que formam uma **partição** do espaço amostral.

**Importância:**
- Permite "quebrar" um problema de probabilidade complexo em partes mais simples.
- Essencial para calcular a probabilidade geral de um evento em processos de múltiplos estágios.
- Serve como denominador e base para o Teorema de Bayes.
```

---

```ad-example

#### **Lei da Probabilidade Total**
```

---

```ad-quote
title: **Def**

A lei calcula a probabilidade total de um evento $A$ somando as probabilidades de $A$ ocorrer dentro de cada cenário (ou partição) $B_i$, ponderadas pela probabilidade de cada cenário.

**Características (Quando Usar):**

✔️ **Cenários Múltiplos:** 
- O problema envolve dois ou mais cenários que cobrem todas as possibilidades (ex.: produto vem da fábrica A ou B; paciente tem ou não tem a doença).

✔️ **Probabilidades Condicionais Conhecidas:** 
- Você conhece a probabilidade do evento de interesse ocorrer *dado cada cenário* (ex.: % de defeito da fábrica A; % de teste positivo para doentes).

✔️ **Pergunta sobre o Geral:** 
- O objetivo é encontrar a probabilidade *total* do evento, sem saber qual cenário ocorreu (ex.: Qual a chance de um produto aleatório ser defeituoso?).
```

##### **Fórmula:**

```ad-quote
title: **Def**

**Forma Geral (para uma partição $B_1, B_2, \dots, B_n$):**

1. $$P(A) = \sum_{i=1}^{n} P(A|B_i) \cdot P(B_i)$$

**Caso Comum (partição com 2 eventos, $B$ e seu complementar $B^c$):**

2. $$P(A) = P(A|B) \cdot P(B) + P(A|B^c) \cdot P(B^c)$$

**Onde:**
- $P(A)$ = probabilidade total do evento de interesse.
- $B_i$ = eventos que formam a partição (cenários).
- $P(B_i)$ = probabilidade de cada cenário ocorrer.
- $P(A|B_i)$ = probabilidade de $A$ ocorrer dentro de um cenário específico.
```

---

> [!error] **Exemplo: Urnas e Bolas**

```ad-quote
title: **Def**

**Problema:** Temos duas urnas. **Urna 1:** 3 bolas vermelhas, 2 azuis. **Urna 2:** 1 vermelha, 4 azuis. Escolhemos uma urna ao acaso ($P=0.5$ cada) e sorteamos uma bola. Qual a probabilidade de a bola ser vermelha?

---
**Eventos:**
- $A$: A bola sorteada é vermelha.
- $U_1$: A urna escolhida foi a 1. ($P(U_1)=0.5$)
- $U_2$: A urna escolhida foi a 2. ($P(U_2)=0.5$)

**Probabilidades Condicionais:**
- $P(A|U_1) = 3/5 = 0.6$
- $P(A|U_2) = 1/5 = 0.2$

**Cálculo:**
1. $$P(A) = P(A|U_1)P(U_1) + P(A|U_2)P(U_2)$$
2. $$P(A) = (0.6 \cdot 0.5) + (0.2 \cdot 0.5) = 0.3 + 0.1 = 0.4$$

**Resposta:** A probabilidade de sortear uma bola vermelha é de **40%**.
```

---

> [!error] **Exemplo: Seguro Automotivo**

```ad-quote
title: **Def**

**Problema:** Uma seguradora tem segurados de risco baixo (60%), médio (30%) e alto (10%). A chance anual de acidente é 1% para risco baixo, 5% para médio e 15% para alto. Qual a probabilidade de um segurado qualquer sofrer um acidente?

---
**Eventos:**
- $AC$: Segurado sofre acidente.
- $B, M, A$: Segurado é de risco Baixo, Médio ou Alto.
- $P(B)=0.6, P(M)=0.3, P(A)=0.1$

**Probabilidades Condicionais:**
- $P(AC|B)=0.01$
- $P(AC|M)=0.05$
- $P(AC|A)=0.15$

**Cálculo:**
1. $$P(AC) = P(AC|B)P(B) + P(AC|M)P(M) + P(AC|A)P(A)$$
2. $$P(AC) = (0.01 \cdot 0.60) + (0.05 \cdot 0.30) + (0.15 \cdot 0.10)$$
3. $$P(AC) = 0.006 + 0.015 + 0.015 = 0.036$$

**Resposta:** A probabilidade de um segurado sofrer um acidente é de **3.6%**.
```

---

> [!error] **Exemplo: Teste Diagnóstico**

```ad-quote
title: **Def**

**Problema:** Uma doença afeta 2% da população. Um teste acerta 95% das vezes para quem tem a doença, mas dá falso positivo em 3% dos casos para quem não tem. Qual a probabilidade de uma pessoa aleatória ter um resultado positivo?

---
**Eventos:**
- $Pos$: Teste dá resultado positivo.
- $D$: Pessoa tem a doença. ($P(D) = 0.02$)
- $D^c$: Pessoa não tem a doença. ($P(D^c) = 0.98$)

**Probabilidades Condicionais:**
- $P(Pos|D) = 0.95$ (Sensibilidade do teste)
- $P(Pos|D^c) = 0.03$ (Taxa de falso positivo)

**Cálculo:**
1. $$P(Pos) = P(Pos|D)P(D) + P(Pos|D^c)P(D^c)$$
2. $$P(Pos) = (0.95 \cdot 0.02) + (0.03 \cdot 0.98)$$
3. $$P(Pos) = 0.019 + 0.0294 = 0.0484$$

**Resposta:** A probabilidade de uma pessoa ter um teste positivo é de **4.84%**.
```

---