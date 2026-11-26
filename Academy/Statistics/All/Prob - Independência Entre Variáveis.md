
---

```ad-quote
title: **Def**

A **independência entre variáveis** é um conceito fundamental em probabilidade e estatística. Em termos simples, duas variáveis são independentes se o valor de uma **não fornece nenhuma informação** sobre o valor da outra. Saber o resultado de uma não altera a probabilidade dos resultados da outra.
```

---
#### **01 )** *Definição Formal*

```ad-quote
title: **Def**

A definição matemática de independência varia ligeiramente dependendo se estamos falando de eventos ou de variáveis aleatórias:
```
##### **Para )** *Eventos:* 

```ad-quote
title: **Def**

Dois eventos A e B são independentes se a probabilidade de ambos ocorrerem é igual ao produto de suas probabilidades individuais:

1. $$P(A∩B)=P(A)×P(B)$$

Isso também implica que a probabilidade condicional é igual à probabilidade marginal:

 
 1. $$P(A∣B)=P(A)$$
 
 2. $$P(B∣A)=P(B)$$
 
**Obs:** Desde que $P(A)$ e $P(B)$ sejam maiores que zero
```
##### **Para )** *Variáveis*

```ad-quote
title: **Def**

Aleatórias (Discretas): Duas variáveis aleatórias X e Y são independentes se a probabilidade conjunta é o produto das probabilidades marginais para todos os possíveis valores x e y:

$$P(X=x,Y=y)=P(X=x)×P(Y=y)$$

- Para Variáveis Aleatórias (Contínuas): Duas variáveis aleatórias X e Y são independentes se a função de densidade de probabilidade conjunta é o produto das funções de densidade marginais para todos os x e y:

$$f(x,y)=fX​(x)×fY​(y)$$

```

---
#### **02 )** *Características e Implicações Principais*

```ad-quote
title: **Def**

**Ausência de Associação:** 
- Se duas variáveis são independentes, elas não estão associadas. Não há padrão ou relação previsível entre elas.

---

**Simplificação de Cálculos:** 
- A independência permite simplificar muitas fórmulas em estatística:
  
    - **Esperança:** 
      - Se X e Y são independentes, $E[XY]=E[X]×E[Y]$.
    - **Variância:** 
      - Se X e Y são independentes, $Var[X+Y]=Var[X]+Var[Y]$.

---

**Covariância e Correlação:** 
- Se $X$ e $Y$ são independentes, a covariância entre elas é zero $(Cov(X,Y)=0)$, e, consequentemente, a correlação também é zero $(Corr(X,Y)=0)$.
```

---
#### **03 )** *Independência vs. Correlação Nula*

```ad-quote
title: **Def**

É **crucial** entender a diferença:

**Independência implica Correlação Nula:** 
- Se duas variáveis são independentes, sua correlação _sempre_ será zero.

**Correlação Nula NÃO implica Independência:** 
- Duas variáveis podem ter correlação zero, mas _ainda assim serem dependentes_. A correlação mede apenas a _relação linear_. Se existir uma relação não-linear forte (como Y=X2, onde X é simétrico em torno de zero), a correlação pode ser zero, mas Y é claramente dependente de X.
    - _Exceção:_ Para variáveis com distribuição Normal (Gaussiana), correlação zero _implica_ independência.
```

---

