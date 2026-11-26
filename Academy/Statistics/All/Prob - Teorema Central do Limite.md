
---

```ad-quote
title: **Def**

O Teorema Central do Limite é a base para a inferência estatística (como testes de hipóteses e intervalos de confiança). Ele permite que façamos previsões e tiremos conclusões sobre a média de uma população a partir de uma única amostra, usando a bem compreendida e previsível **Distribuição Normal** como nossa ferramenta de análise.
```

---

```ad-example

#### **Teorema Central do Limite**
```

---
#### **01 )** - O que é o Teorema Central do Limite?

```ad-quote
title: **Def**

O **Teorema Central do Limite (TCL):** 
- É um dos resultados mais importantes da estatística. Ele afirma que, independentemente da distribuição original de uma população, a Distribuição das médias das Amostras retiradas dessa população se aproximará de uma Distribuição Normal à medida que o tamanho da amostra ($n$) aumenta.

Em resumo: 
- Não importa se a população original segue uma distribuição Uniforme, Exponencial ou qualquer outra forma; as médias de suas amostras grandes se comportarão como uma Distribuição Normal.
```

---
#### **02 )** - Ingredientes e Condições

```ad-quote
title: **Def**

**População Original:**
- Pode ter **qualquer distribuição** de probabilidade, contanto que tenha uma média ($\mu$) e uma variância ($\sigma^2$) finitas e bem definidas.

**Amostras Aleatórias:**
- As amostras devem ser retiradas de forma independente e idêntica da população.

**Tamanho da Amostra ($n$):**
- A aproximação para a Normalidade se torna melhor à medida que o tamanho da amostra ($n$) cresce. Na prática, uma amostra de tamanho **$n \ge 30$** é frequentemente considerada suficiente.
```

---
#### **03 )** - As Consequências (O que o Teorema nos Diz)

```ad-quote
title: **Def**

Seja $X_1, X_2, \ldots, X_n$ uma amostra aleatória de tamanho $n$ de uma população com média $\mu$ e variância $\sigma^2$. A média da amostra é denotada por: 

1. $$\bar{X} = \frac{1}{n}\sum_{i=1}^{n} X_i$$ 

Ou

2. $$\bar{X} = \frac{X_1 + X_2 + \ldots + X_n}{n}$$
```

---

```ad-quote
title: **Def**

**A Distribuição das Médias Amostrais é Normal:**
- A variável aleatória $\bar{X}$ (a média da amostra) segue aproximadamente uma distribuição Normal.

**Esperança (Média) das Médias Amostrais:**
- A média de todas as possíveis médias amostrais é igual à média da população original.

1. $$E(\bar{X}) = \mu$$

```

```ad-quote
title: **Def**

**Variância das Médias Amostrais:**
- A variância das médias amostrais é a variância da população original dividida pelo tamanho da amostra. Isso significa que, quanto maior a amostra, menor a dispersão das médias em torno da média da população.

1. $$V(\bar{X}) = \frac{\sigma^2}{n}$$

- Consequentemente, o desvio padrão das médias amostrais (conhecido como **erro padrão**) é: 
  
2. $$\text{DP}(\bar{X}) = \frac{\sigma}{\sqrt{n}}$$

```

---
#### **04 )** - A Ponte com o $Z$-Score

```ad-quote
title: **Def**

O poder do TCL é que ele nos permite usar as ferramentas da Distribuição Normal Padrão:
- (com média 0 e desvio padrão 1) 
  
para analisar a média de uma amostra, mesmo sem conhecer a distribuição da população.
```

```ad-quote
title: **Def**

**Média de uma amostra ($\bar{x}$)**:

1. $$z = \frac{\bar{x} - \mu}{\frac{\sigma}{\sqrt{n}}}$$
```

```ad-quote
title: **Def**

**O que ela recebe (Entradas):**
- $\bar{x}$: A média calculada da sua amostra específica.
- $\mu$: A média da população original (muitas vezes, é o valor que estamos testando).
- $\sigma$: O desvio padrão da população original.
- $n$: O tamanho da sua amostra.

**O que ela retorna (Saída):**
- $z$ ($Z$-Score): O resultado indica quantos **erros padrão** ($\frac{\sigma}{\sqrt{n}}$) a média da sua amostra ($\bar{x}$) está distante da média da população ($\mu$).
```

---

