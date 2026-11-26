
---

>[!example] ### **Média Aritrimétrica**

---

```ad-quote
title: **Def**

A **média** (ou média aritmética) é a soma de todos os valores dividida pelo número de observações.

 **Características:**

✔️ **Vantagem:** 
- Leva em conta todos os valores.
  
❌ **Desvantagem:** 
- É sensível a valores extremos (outliers).
```
##### **Fórmula:**

```ad-quote
title: **Def**

$$\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}$$

**Onde:**

* $\bar{x}$ = média
* $x_i$ = cada valor do conjunto de dados
* $n$ = número de observações
```

>[!error] **Exemplo**:  

```ad-quote
title: **Def**

**Dados:** 4, 6, 8, 10

---

**Média Aritmétrica:** 

$$\frac{4+6+8+10}{4} = \frac{28}{4} = 7$$

```

---

>[!example] #### **Média Ponderada**

---

```ad-quote
title: **Def**

A **média ponderada** atribui pesos diferentes a cada valor do conjunto de dados, refletindo sua importância relativa.

**Características:**

✔️ **Vantagem:** 
- Permite dar maior ou menor importância a certos valores.

❌ **Desvantagem:** 
- A escolha dos pesos pode ser subjetiva.
```
##### **Fórmula:**

```ad-quote
title: **Def**

$$\bar{x}_w = \frac{\sum_{i=1}^{n} w_i x_i}{\sum_{i=1}^{n} w_i}$$

**Onde:**

* $\bar{x}_w$ = média ponderada
* $x_i$ = cada valor do conjunto de dados
* $w_i$ = peso associado a cada valor
* $n$ = número de observações
```

>[!error] **Exemplo**:  

```ad-quote
title: **Def**

**Dados:** Valores = 5, 7, 9; Pesos = 2, 3, 1

---

**Média Ponderada:** 

$$\frac{(5 \times 2) + (7 \times 3) + (9 \times 1)}{2 + 3 + 1} = \frac{10 + 21 + 9}{6} = \frac{40}{6} \approx 6,67$$


```

---

>[!example] #### **Média Geométrica**

---

```ad-quote
title: **Def**

A **média geométrica** é a raiz n-ésima do produto de todos os valores, útil para taxas de crescimento e proporções.

**Características:**

✔️ **Vantagem:** 
- Adequada para dados multiplicativos ou com variações percentuais.
  
❌ **Desvantagem:** 
- Não pode ser usada com valores negativos ou zero.
```
##### **Fórmula:**

```ad-quote
title: **Def**

$$G = \sqrt[n]{x_1 \times x_2 \times \cdots \times x_n}$$

**Onde:**

* $G$ = média geométrica
* $x_i$ = cada valor do conjunto de dados
* $n$ = número de observações
```

>[!error] **Exemplo**:  

```ad-quote
title: **Def**

**Dados:** 2, 8, 32

---

**Média Geométrica:** 

$$\sqrt[3]{2 \times 8 \times 32} = \sqrt[3]{512} = 8$$

```

---

>[!example] #### **Média Harmônica**

---

```ad-quote
title: **Def**

A **média harmônica** é o inverso da média aritmética dos inversos dos valores, usada para taxas e razões.

**Características:**

✔️ **Vantagem:** 
- Ideal para situações envolvendo médias de velocidades ou taxas.
  
❌ **Desvantagem:** 
- Sensível a valores próximos de zero.
```
##### **Fórmula:**

```ad-quote
title: **Def**

$$H = \frac{n}{\sum_{i=1}^{n} \frac{1}{x_i}}$$

**Onde:**

* $H$ = média harmônica
* $x_i$ = cada valor do conjunto de dados
* $n$ = número de observações
```

>[!error] **Exemplo**:  

```ad-quote
title: **Def**

**Dados:** 2, 4, 8

---

**Média Harmônica:** 

$$\frac{3}{\frac{1}{2} + \frac{1}{4} + \frac{1}{8}} = \frac{3}{\frac{7}{8}} = \frac{24}{7} \approx 3,43$$


```

---

>[!example] #### **Moda**

---

```ad-quote
title: **Def**

A **moda** é o valor que aparece com maior frequência em um conjunto de dados.
```
##### **Tipos de Moda:**

```ad-quote
title: **Def**


**Unimodal:** 
- Apenas uma moda.
  
**Bimodal:** 
- Duas modas.
  
**Multimodal:** 
- Várias modas.

**Amodal:** 
- Nenhuma moda (todos os valores têm a mesma frequência).

```

>[!error] **Exemplo**:  

```ad-quote
title: **Def**

Dados: 3, 5, 5, 7, 8 

---

Moda = **5** (aparece duas vezes).
```

---

>[!example] #### **Mediana**

---

```ad-quote
title: **Def**

A **mediana** é o valor central de um conjunto de dados ordenado.

**Características:**

✔️ **Vantagem:** 
- Não é sensível a valores extremos (outliers).
  
❌ **Desvantagem:** 
- Não leva em conta todos os valores do conjunto de dados.
```
##### **Como calcular:**

```ad-quote
title: **Def**

**1 ) Ordene** 
   - o conjunto de dados em ordem crescente.

**2 ) Se o número de observações (n) for ímpar:** 
   - A mediana é o valor central, que ocupa a posição $\frac{n+1}{2}$.

**3 ) Se o número de observações (n) for par:** 
   - A mediana é a média dos dois valores centrais, que ocupam as posições $\frac{n}{2}$ e $\frac{n}{2} + 1$.
```

>[!error] **Exemplo**:  

```ad-quote
title: **Def**

**Exemplo 1 (n ímpar):**

**Dados:** 3, 1, 5, 2, 4

**Ordenando:** 1, 2, **3**, 4, 5

**Mediana:** 3 (o valor central)
```

```ad-quote
title: **Def**

**Exemplo 2 (n par):**

**Dados:** 10, 20, 30, 40

**Ordenando:** 10, **20**, **30**, 40

**Mediana:** $\frac{20 + 30}{2} = \frac{50}{2} = 25$ (a média dos dois valores centrais)
```

---

>[!example] #### **Separatrizes**

---

```ad-quote
title: **Def**

As separatrizes são medidas que dividem o conjunto de dados em partes iguais.
```

![[Pasted image 20250414172247.png]]
##### **Tipos de Separatrizes:**

```ad-quote
title: **Def**

**Quartis (Q1, Q2, Q3)** → Dividem os dados em **4 partes iguais**.

**Q1 (1º Quartil)**: 
- 25% dos dados estão abaixo.

**Q2 (2º Quartil)**: 
- Igual à **mediana** (50%).

**Q3 (3º Quartil)**: 
- 75% dos dados estão abaixo.

---

**Também existem:**

**Decis (D1 a D9)** 
→ Dividem os dados em **10 partes iguais**.

**Percentis (P1 a P99)** 
→ Dividem os dados em **100 partes iguais**.
```
##### **Cálculo dos Quartis**

```ad-quote
title: **Def**


**01 )** - Ordene os dados.
**02 )** - Calcule a posição do quartil:

$$Posição\ de\ Q_k = \frac{k(n+1)}{4}$$

- Se a posição não for inteira, faça uma **interpolação** entre os valores mais próximos.
```

>[!error] **Exemplo**:  

```ad-quote
title: **Def**

Dados: 1, 3, 5, 7, 9, 11, 13, 15, 17, 19

* **Q1 (25%)**: Posição = $$\frac{1 \times (10+1)}{4} = 2,75 \rightarrow 3 + 0,75 \times (5 - 3) = 4,5$$
* **Q2 (50%)**: Mediana = $$\frac{9+11}{2} = 10$$
* **Q3 (75%)**: Posição = $$\frac{3 \times (10+1)}{4} = 8,25 \rightarrow 15 + 0,25 \times (17 - 15) = 15,5$$

```

---
