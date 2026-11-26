
---

> [!example]
> 
> #### **Cálculo do Valor Esperado do Produto E[XY]**

---

```ad-quote
title: **Def**

**Valor Esperado do Produto E[XY]**
- O termo $E[XY]$ representa a média de todos os valores possíveis do produto das variáveis $X$ e $Y$, ponderada pela frequência com que cada par $(x,y)$ ocorre.
- Ele é fundamental para o cálculo da covariância, que mede a relação linear entre duas variáveis.
```

---

```ad-quote
title: **Def**

**Fórmula de Cálculo para Tabelas de Frequência**
- A partir de uma tabela de frequências conjuntas, $E[XY]$ é calculado pela seguinte fórmula:
$$ E[XY] = \frac{\sum (x \cdot y \cdot \text{frequência}_{xy})}{\text{Total de Observações}} $$
- Onde $x$ é o valor da variável na linha, $y$ é o valor da variável na coluna e $\text{frequência}_{xy}$ é o valor da célula correspondente.

```

---

```ad-quote
title: **Tabela de Frequências de Exemplo**
Imagine um levantamento com 20 pessoas sobre horas de estudo (X) e copos de café (Y).

| Horas (X) / Café (Y) | 1 | 2 | **Total (X)** |
| :--- | :-: | :-: | :--- |
| **0** | 3 | 5 | **8** |
| **1** | 7 | 5 | **12** |
| **Total (Y)** | **10** | **10** | **20** |

```

```ad-quote
title: **Aplicação da Fórmula**

Vamos aplicar a fórmula passo a passo.

1.  **Calcular o produto ponderado $(x \cdot y \cdot \text{frequência})$ para cada célula:**

| X / Y | Y = 1 | Y = 2 |
| :--- | :--- | :--- |
| **X = 0** | $(0 \cdot 1 \cdot 3) = \textbf{0}$ | $(0 \cdot 2 \cdot 5) = \textbf{0}$ |
| **X = 1** | $(1 \cdot 1 \cdot 7) = \textbf{7}$ | $(1 \cdot 2 \cdot 5) = \textbf{10}$ |

2.  **Somar os resultados obtidos:**
    $$ \sum (x \cdot y \cdot \text{frequência}) = 0 + 0 + 7 + 10 = 17 $$

3.  **Dividir pelo total de observações:**
    $$ E[XY] = \frac{17}{20} = 0.85 $$
```

```ad-quote
title: **Resultado**

**O valor esperado do produto é 0.85.**
- Para os dados deste exemplo, a média do produto entre as horas de estudo e os copos de café é $E[XY] = 0.85$.
```

---