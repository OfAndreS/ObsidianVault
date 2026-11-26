
---

```ad-example
#### **Medidas de Variabilidade / Dispersão**
```

---

```ad-quote
title: **Def**

As **medidas de variabilidade** quantificam o grau de dispersão dos dados em relação à sua média, indicando se estão mais concentrados ou espalhados.

**Importância:**
- Complementam a análise descritiva
- Identificam homogeneidade/heterogeneidade
- Avaliam a representatividade da média
```

---

>[!tip] ### **Amplitude**

---

```ad-quote
title: **Def**

A **amplitude** é a diferença entre o maior e menor valor do conjunto.

**Características:**

✔️ **Vantagens:**
- Cálculo extremamente simples
- Boa para uma visão inicial da dispersão

❌ **Limitações:**
- Sensível a outliers
- Ignora a distribuição interna dos dados
```
##### **Fórmula:**

```ad-quote
title: **Def**

$$A = X_{max} - X_{min}$$

**Onde:**
- $A$ = amplitude
- $X_{max}$ = valor máximo
- $X_{min}$ = valor mínimo
```

>[!error] **Exemplo**:

```ad-quote
title: **Def**

**Dados:** 12, 15, 18, 22, 25

---

**Amplitude:** 

$$25 - 12 = 13$$
```

---

>[!tip] ### **Variância**

---

```ad-quote
title: **Def**

A **variância** mede o afastamento quadrático médio dos dados em relação à média.

**Características:**

✔️ **Vantagens:**
- Considera todos os valores
- Base para outras medidas

❌ **Limitações:**
- Unidade ao quadrado (dificulta interpretação)
- Sensível a outliers
```
##### **Fórmula:**

```ad-quote
title: **Def**

**Populacional:**
$$\sigma^2 = \frac{\sum_{i=1}^{N} (x_i - \mu)^2}{N}$$

**Amostral:**
$$s^2 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n-1}$$

**Onde:**
- $\sigma^2, s^2$ = variância
- $\mu, \bar{x}$ = média
- $N, n$ = tamanho da população/amostra
```

>[!error] **Exemplo**:

```ad-quote
title: **Def**

**Dados:** 3, 5, 7, 9 (amostra)

---

1. Média: $\bar{x} = 6$  
2. Soma dos quadrados: $(3-6)^2 + ... + (9-6)^2 = 20$  
3. **Variância:** $20/(4-1) \approx 6.67$
```

---

>[!tip] ### **Desvio Padrão**

---

```ad-quote
title: **Def**

O **desvio padrão** é a raiz quadrada da variância, retornando à unidade original dos dados.

**Características:**

✔️ **Vantagens:**
- Interpretação direta
- Base para regras empíricas

❌ **Limitações:**
- Ainda sensível a valores extremos
```
##### **Fórmula:**

```ad-quote
title: **Def**

**Populacional:**
$$\sigma = \sqrt{\sigma^2}$$

**Amostral:**
$$s = \sqrt{s^2}$$
```

>[!error] **Exemplo**:

```ad-quote
title: **Def**

**Continuando o exemplo anterior:**

$\sqrt{6.67} \approx 2.58$

**Interpretação:** Os dados desviam, em média, 2.58 unidades da média.
```

---

>[!tip] ### **Coeficiente de Variação**

---

```ad-quote
title: **Def**

O **CV** expressa o desvio padrão como porcentagem da média, permitindo comparações entre conjuntos diferentes.

**Características:**

✔️ **Vantagens:**
- Comparação entre escalas diferentes
- Análise de risco relativo

❌ **Limitações:**
- Perde sentido quando a média é próxima de zero
```
##### **Fórmula:**

```ad-quote
title: **Def**

$$CV = \left( \frac{s}{\bar{x}} \right) \times 100\%$$

**Interpretação:**
- CV < 15%: Baixa dispersão
- 15% < CV < 30%: Dispersão moderada
- CV > 30%: Alta dispersão
```

>[!error] **Exemplo**:

```ad-quote
title: **Def**

**Dados:** $\bar{x} = 50$, $s = 10$

---

**CV:** $(10/50) \times 100\% = 20\%$

**(Dispersão moderada)**
```

---
