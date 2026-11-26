---

---

---

```ad-quote
title: **Def: Esperança e Variância**

A **Esperança $E(X)$** e a **Variância $V(X)$** são as duas medidas mais importantes de uma distribuição de probabilidade.

- **Esperança (Média, $\mu$):** É o "centro de gravidade" da distribuição. Indica o resultado médio esperado de um fenômeno se ele for repetido inúmeras vezes.
- **Variância (Dispersão, $\sigma^2$):** Mede o quão espalhados os resultados estão em torno da esperança. É a medida fundamental de **risco** ou **incerteza**.

**Importância:**
- Permitem resumir uma distribuição de probabilidade complexa em dois números: onde ela se centra e quão dispersa ela é.
- Essenciais para tomada de decisão em cenários de incerteza (ex.: finanças, seguros, jogos).
```

---

```ad-example
#### **Quando usar Esperança e Variância?**
```

```ad-quote
title: **Def**

**Use Esperança para encontrar:**
✔️ O retorno médio de um investimento.
✔️ O valor justo a se pagar por um jogo ou aposta.
✔️ A previsão de longo prazo para um resultado médio (ex.: média de vendas).

**Use Variância (e Desvio Padrão) para medir:**
✔️ O risco de um ativo financeiro (volatilidade).
✔️ A consistência de um processo (ex.: controle de qualidade em uma fábrica).
✔️ A incerteza ou o erro associado a uma previsão.
```

---
##### *Variáveis Discretas*

```ad-quote
title: **Def**

Para uma variável $X$ que assume valores $x_i$ com probabilidades $P(X=x_i)$.

---

**Esperança:** 

1. $$E(X) = \sum_{i} x_i \cdot P(X=x_i)$$

**Variância (Fórmula Computacional):** 

2. $$V(X) = E(X^2) - [E(X)]^2$$
	- Onde $E(X^2) = \sum_{i} x_i^2 \cdot P(X=x_i)$.

**Desvio Padrão:** 

3. $$\sigma = \sqrt{V(X)}$$
	- *O Desvio Padrão é a medida de dispersão na mesma unidade de $X$, sendo mais fácil de interpretar.*
```
##### *Variáveis Contínuas*

```ad-quote
title: **Def**

Para uma variável $X$ com função de densidade de probabilidade $f(x)$.

---

**Esperança:** 

1. $$E(X) = \int_{-\infty}^{+\infty} x \cdot f(x) \, dx$$

**Variância (Fórmula Computacional):** 

2. $$V(X) = E(X^2) - [E(X)]^2$$
    - Onde $E(X^2) = \int_{-\infty}^{+\infty} x^2 \cdot f(x) \, dx$.

**Desvio Padrão:** 

3. $$\sigma = \sqrt{V(X)}$$
```

---

> [!error] **Exemplo: Jogo de Dados**

```ad-quote
title: **Def**

**Problema:** Você paga R$ 2,00 para jogar. Se sair 6, você ganha R$ 10,00. Se sair 5, ganha R$ 4,00. Se sair qualquer outro número, não ganha nada. Vale a pena jogar este jogo?

---
**Eventos (Lucro $X$):**
- $X_1 = 10 - 2 = +R\$ 8$ (saiu 6). $P(X_1) = 1/6$.
- $X_2 = 4 - 2 = +R\$ 2$ (saiu 5). $P(X_2) = 1/6$.
- $X_3 = 0 - 2 = -R\$ 2$ (outros). $P(X_3) = 4/6$.

**Cálculo da Esperança (Lucro Médio):**
1. $$E(X) = (8 \cdot \frac{1}{6}) + (2 \cdot \frac{1}{6}) + (-2 \cdot \frac{4}{6})$$
2. $$E(X) = \frac{8 + 2 - 8}{6} = \frac{2}{6} \approx 0.33$$

**Resposta:** 
- A esperança de lucro é de **R$ 0,33 por jogada**. A longo prazo, o jogo é favorável ao jogador. Portanto, sim vale a pena jogar esse jogo. 
- O valor esperado do jogo é de aproximadamente **R$ 0,33 positivos**. Isso significa que, em média, para cada vez que você joga, a expectativa matemática é de um ganho de 33 centavos.
```

---

> [!error] **Exemplo: Análise de Dados de Permanência**

![[Pasted image 20250711123747.png]]

```ad-quote
title: **Def**

**Problema:** Usando os dados da tabela de permanência, qual o tempo médio de estadia e qual o seu desvio padrão (variabilidade)?
- *Dados da tabela: $P(X=4)=0.038, P(X=5)=0.114, P(X=6)=0.430$, etc.*

---
**Cálculo da Esperança (Média):**
1. $$E(X) = (4 \cdot 0.038) + (5 \cdot 0.114) + \dots + (10 \cdot 0.008)$$
2. $$E(X) = 0.152 + 0.57 + 2.58 + 2.1 + 0.64 + 0.27 + 0.08 = 6.392$$

---

**Cálculo da Variância:**

Primeiro, $E(X^2)$:
   
   1. $$E(X^2) = (4^2 \cdot 0.038) + (5^2 \cdot 0.114) + \dots + (10^2 \cdot 0.008) = 41.988$$

Agora, a Variância:
   
   2. $$V(X) = E(X^2) - [E(X)]^2 = 41.988 - (6.392)^2 = 1.13$$

E o Desvio Padrão:
   
   3. $$\sigma = \sqrt{1.13} \approx 1.06$$

**Resposta:** O tempo médio de permanência é de **6,39 dias**, com um desvio padrão de **1,06 dias**, indicando uma baixa variabilidade em torno da média.
```

---
