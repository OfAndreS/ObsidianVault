
---

```ad-quote
title: **Def: Tabela de Dupla Entrada**

Uma **Tabela de Dupla Entrada** 
- Ou Tabela de Contingência é uma ferramenta estatística para exibir a frequência de duas variáveis categóricas simultaneamente. O seu objetivo é visualizar e analisar a relação entre elas.
```

---

```ad-example

#### **Analisando a Tabela de Pacientes**
```

---

```ad-quote
title: **Def**
Problema: 
- Como interpretar os dados da tabela que relaciona internações $(I)$ e crises $(C)$?

---

**I ) - Número de Internações:** 
  - Representada nas linhas.

**C ) - Número de Crises com Infecções Oportunistas:** 
- Representada nas colunas.
```

```ad-quote
title: **Def**

|I/C|0|1|2|3|4|
|---|---|---|---|---|---|
|**0**|84|21|8|2|0|
|**1**|20|59|35|14|2|
|**2**|6|11|43|28|12|

```

```ad-quote
title: **Def**

**Linhas - Variável I:**
- **Linha "0":** Pacientes que tiveram **0 internações**.
- **Linha "1":** Pacientes que tiveram **1 internação**.
- **Linha "2":** Pacientes que tiveram **2 internações**.

**Colunas - Variável C:**
- **Coluna "0":** Pacientes que tiveram **0 crises**.
- **Coluna "1":** Pacientes que tiveram **1 crise**.
- ...e assim por diante.
```

```ad-quote
title: **Def**

**Células Internas - Frequência Conjunta:**

$(I=0, C=0)$: 
- **84 pacientes** não tiveram internações e nem crises.

$(I=1, C=2)$: 
- **35 pacientes** tiveram 1 internação e 2 crises.

$(I=2, C=4)$: 
- **12 pacientes** tiveram 2 internações e 4 crises.
```

---

> [!example] **Resultado: Tabela Completa com as Marginais**

```ad-quote
title: **Def**

| I / C | **0** | **1** | **2** | **3** | **4** | **Total Marginal de I** |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **0** | 84 | 21 | 8 | 2 | 0 | **115** |
| **1** | 20 | 59 | 35 | 14 | 2 | **130** |
| **2** | 6 | 11 | 43 | 28 | 12 | **100** |
| **Total Marginal de C** | **110** | **91** | **86** | **44** | **14** | `345` |
```

```ad-quote
title: **Def:**

As Marginais são os totais de cada linha e de cada coluna. Elas representam a distribuição de frequência de cada variável individualmente, ignorando o efeito da outra.

**Verificação:** 
- A soma das marginais de I ($115+130+100$) e a soma das marginais de C ($110+91+86+44+14$) resultam no total de participantes do estudo: **345**.
```

```ad-quote
title: **Def**
**Cálculo da Marginal de I (Total por Linha):**
- **I = 0:** $84 + 21 + 8 + 2 + 0 = 115$
- **I = 1:** $20 + 59 + 35 + 14 + 2 = 130$
- **I = 2:** $6 + 11 + 43 + 28 + 12 = 100$

**Cálculo da Marginal de C (Total por Coluna):**
- **C = 0:** $84 + 20 + 6 = 110$
- **C = 1:** $21 + 59 + 11 = 91$
- **C = 2:** $8 + 35 + 43 = 86$
- **C = 3:** $2 + 14 + 28 = 44$
- **C = 4:** $0 + 2 + 12 = 14$
```

---

```ad-example

#### **Calculos relacionados**
```

```ad-quote
title: **Objetivos**


**Determinar a constante c:** 
- Garantir que a função seja uma distribuição de probabilidade válida.

---

**Determinar EX e EY:** 
- Encontrar o centro de gravidade (média) de cada variável.

---

**Determinar VX e VY:** 
- Medir a dispersão (risco ou incerteza) de cada variável.

---

**Determinar Cov(X,Y):** 
- Medir a direção da relação linear entre X e Y.

---

**Determinar rXY (correlação):** 
- Medir a força e a direção da relação linear entre X e Y.

```

---

```ad-quote
title: **Def**

Com $c=1/36$, a função é $f(x,y) = \frac{xy}{36}$. 
- A tabela abaixo mostra as probabilidades conjuntas (miolo) e as probabilidades marginais (totais de linha/coluna), que usaremos nos próximos cálculos.
```

```ad-quote
title: **Def**

| **x \ y** | **1** | **2** | **3** | **P(X=x)** Marginal de X |
| :--- | :-: | :-: | :-: | :---: |
| **1** | 1/36 | 2/36 | 3/36 | **6/36** |
| **2** | 2/36 | 4/36 | 6/36 | **12/36** |
| **3** | 3/36 | 6/36 | 9/36 | **18/36** |
| **P(Y=y)** Marginal de Y | **6/36** | **12/36** | **18/36** | **1** |
```

---
#### **01 ) -** Determinar a constante c

```ad-quote
title: **Def**

**Para que serve?** 
- A soma de todas as probabilidades em uma distribuição deve ser igual a 1. A constante `c` é um Fator de normalização que ajusta a função para que ela cumpra essa regra fundamental.
```

```ad-quote
title:
**Cálculo:** A soma de todos os $f(x,y)$ deve ser 1.

1. $$ \sum_{x=1}^{3} \sum_{y=1}^{3} cxy = 1 $$

2. $$ c \left( \sum_{x=1}^{3} \sum_{y=1}^{3} xy \right) = 1 $$

O somatório de $xy$ é a soma de todos os produtos possíveis:

3. $$(1+2+3) + (2+4+6) + (3+6+9) = 36$$

4. $$c \cdot 36 = 1 \implies c = \frac{1}{36}$$
```

---
#### **2 ) -** Determinar a Esperança (Média) EX e EY

```ad-quote
title: **Def**

**Para que serve?**
- A Esperança ($E$) representa o valor médio esperado para cada variável a longo prazo. É a medida de **tendência central**.
```

```ad-quote
title: 
**Cálculo de EX:**

1. $$EX = \sum x \cdot P(X=x)$$

2. $$EX = \left(1 \cdot \frac{6}{36}\right) + \left(2 \cdot \frac{12}{36}\right) + \left(3 \cdot \frac{18}{36}\right) = \frac{6 + 24 + 54}{36} = \frac{84}{36} = \frac{7}{3}$$

**Cálculo de EY:**

1. $$EY = \sum y \cdot P(Y=y)$$

2. $$EY = \left(1 \cdot \frac{6}{36}\right) + \left(2 \cdot \frac{12}{36}\right) + \left(3 \cdot \frac{18}{36}\right) = \frac{84}{36} = \frac{7}{3}$$
```

---
#### **3 ) -** Determinar a Variância VX e VY

```ad-quote
title: **Def**

**Para que serve?**
- A Variância ($V$) mede a dispersão dos dados em torno da média. É a principal medida de **risco** ou **incerteza** de uma variável.
```

```ad-quote
title: 
**Cálculo de VX:**

1. $$VX = E[X^2] - (EX)^2$$

Primeiro, calculamos $E[X^2]$:
   
   2. $$E[X^2] = \sum x^2 \cdot P(X=x) = \left(1^2 \cdot \frac{6}{36}\right) + \left(2^2 \cdot \frac{12}{36}\right) + \left(3^2 \cdot \frac{18}{36}\right) = 6$$

Agora, a variância:
   
   3. $$VX = 6 - \left(\frac{7}{3}\right)^2 = \frac{5}{9}$$

**Cálculo de VY:**
- Pela simetria do problema, $VY = VX = \frac{5}{9}$.
```

---
#### **4 ) -** Determinar a Covariância $Cov(X,Y)$

```ad-quote
title: **Def**

**Para que serve?**
- A Covariância mede a **direção** da relação linear entre X e Y. Um valor positivo indica que elas se movem na mesma direção; negativo, em direções opostas.
```

```ad-quote
title: 
**Cálculo de Cov(X,Y):**

1. $$Cov(X,Y) = E[XY] - (E[X])(E[Y])$$

Primeiro, calculamos $E[XY]$:
   
2. $$E[XY]=\sum_{x=1}^3\sum_{y=1}^3(xy)\cdot\left(\frac{xy}{36}\right)=\frac{1}{36}\sum_{x=1}^3\sum_{y=1}^3(xy)^2$$

Agora, a covariância:
   
3. $$Cov(X,Y) = \frac{49}{9} - \left(\frac{7}{3}\right)\left(\frac{7}{3}\right) = 0$$
```

>[!quote] **Vault** -  [[Prob - E(XY)]]

---
#### **5 ) -** Determinar a Correlação $rXY$

```ad-quote
title: **Def**

**Para que serve?** 
- A Correlação ($r$) padroniza a covariância, resultando em um valor entre $-1$ e $1$. Ela mede tanto a Direção quanto a Força da relação linear.
```

```ad-quote
title: 
**Cálculo de rXY:**

1. $$r_{XY} = \frac{Cov(X,Y)}{\sqrt{V(X) \cdot V(Y)}}$$

2. $$r_{XY} = \frac{0}{\sqrt{\frac{5}{9} \cdot \frac{5}{9}}} = 0$$
```

---

```ad-quote
title: **Conclusão Geral do Exercício**

A **Covariância** e a **Correlação** serem iguais a **0** 
- indica que **não existe uma relação linear** entre as variáveis X e Y.

Neste caso específico: 
- Como a função conjunta é um produto das marginais $f(x,y) = f(x) \cdot f(y))$, podemos ir além e afirmar que as variáveis são **estatisticamente independentes**. A correlação zero é um reflexo dessa independência.

```

---

> [!example]
> 
> #### **Análise de Independência**

---

```ad-quote
title: **Def**

**Princípio Teórico da Independência**
- Duas variáveis aleatórias $X$ e $Y$ são **independentes** se, e somente se, a probabilidade conjunta for igual ao produto de suas probabilidades marginais para **todos** os pares $(x, y)$.
- A condição formal é: $$P(X=x, Y=y) = P(X=x) \cdot P(Y=y)$$
- Para provar a dependência, basta encontrar **um único par** $(x,y)$ onde esta regra é violada.
```

---

```ad-quote
title: **Def**
| Salário / Ano  | 2        | 3        | 4        | 5        | **P(Sal = x)** |
| -------------- | -------- | -------- | -------- | -------- | -------------- |
| **2**          | 2/25     | 2/25     | 1/25     | 0        | **5/25**       |
| **3**          | 2/25     | 5/25     | 2/25     | 2/25     | **11/25**      |
| **4**          | 1/25     | 2/25     | 2/25     | 4/25     | **9/25**       |
| **P(Ano = y)** | **5/25** | **9/25** | **5/25** | **6/25** | **1**          |

```


```ad-quote
title: 
**Verificação da Condição de Independência**

Vamos testar a condição para o par $(x,y) = (2,2)$.

1. **Probabilidade Conjunta (valor da célula):**
   $$P(X=2, Y=2) = \frac{2}{25}$$

2. **Produto das Probabilidades Marginais (produto dos totais):**
   $$P(X=2) \cdot P(Y=2) = \left(\frac{5}{25}\right) \cdot \left(\frac{5}{25}\right) = \left(\frac{1}{5}\right) \cdot \left(\frac{1}{5}\right) = \frac{1}{25}$$

3. **Comparação dos Resultados:**
   $$ \frac{2}{25} \neq \frac{1}{25} $$
   $$ P(X=2, Y=y) \neq P(X=x) \cdot P(Y=y) $$
```

---

```ad-quote
title: **Conclusão**

**As variáveis não são independentes.**
- Como a condição de independência falhou para o par $(2,2)$, fica provado que existe uma **dependência estatística** entre o ano que o aluno cursa e a remuneração do seu estágio.
```

---
