---
banner: "![[Pasted image 20251103153324.png]]"
banner-x: 48
banner-y: 12
---

---

````ad-quote
title:

##### **Intro )** - Cenários de Exemplo Desbalanceados

```ad-quote
title:
###### **Supervisionado:**
```

```ad-quote
title:
<p align="justify">Todas essas métricas (Acurácia, Recall, F1) são SUPERVISIONADAS, pois exigem um GABARITO (os rótulos reais) para fazer a comparação.</p>
```

```ad-quote
title:
###### **Preditivo:**
```

```ad-quote
title:
<p align="justify">Elas medem o desempenho de modelos PREDITIVOS (que tentam ACERTAR uma resposta). Elas não se aplicam a modelos GENERATIVOS (que CRIAM conteúdo novo e são medidos por realismo/diversidade, ex: FID, Perplexity).</p>
```
>[!quote] **Link:** [Gemini](https://gemini.google.com/app/596dc1b3de7483b1?hl=pt-BR)

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **00 )** - Definição dos exemplos

```ad-quote
title:
###### **Exemplo A - Detecção de Doença**
```

```ad-quote
title:
Um FALSO NEGATIVO (dizer que um doente está saudável) é CATASTRÓFICO.
```

```ad-quote
title:

|Conceito|Definição|
| --- | --- |
|Contexto|Um teste para uma doença RARA.|
|Objetivo|Encontrar os doentes.|
|Dataset|1.000 pacientes.|
|Rótulos Reais|10 pacientes estão DOENTES (Positivo), 990 são SAUDÁVEIS (Negativo).|

```

```ad-quote
title:
###### **Exemplo B - Filtro de SPAM**
```

```ad-quote
title:
Um FALSO POSITIVO (dizer que um e-mail importante é spam) é CATASTRÓFICO.
```

```ad-quote
title: 
|Conceito|Definição| 
| --- | --- | 
|Contexto|Um filtro de e-mail.| 
|Objetivo|Bloquear spam.| 
|Dataset|1.000 e-mails.| 
|Rótulos Reais|950 IMPORTANTES (Negativos) <br> 50 SPAM (Positivos)|
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - O Ponto de Partida: A Insuficiência da Acurácia

```ad-quote
title:
<p align="justify">A ACURÁCIA é a métrica mais simples: "Quantas vezes o modelo acertou no total?"</p>
```

```ad-quote
title:
###### **Fórmula:**
```

```ad-quote
title:
1. $$Acurácia = (Total \, de \, Acertos) / (Total \, de \, Amostras)$$
```

```ad-quote
title:
###### **Exemplo A / Doença:**
```

```ad-quote
title:
<p align="justify">Imagine um modelo preguiçoso que, por saber que a doença é rara, simplesmente prevê "SAUDÁVEL" (Negativo) para TODOS os 1.000 pacientes.</p>
```

```ad-quote
title:
###### **Cálculo:**
```

```ad-quote
title:

Acurácia: 

1. $$990 / 1000 = 99\%$$
   
Ele acerta os 990 pacientes SAUDÁVEIS.
Ele erra os 10 pacientes DOENTES.
```

```ad-quote
title:
###### **Conclusão:**
```

```ad-quote
title:
<p align="justify">O modelo tem 99% de acurácia, mas é COMPLETAMENTE INÚTIL, pois falha em 100% do seu objetivo principal (encontrar os doentes). Isso prova que precisamos de métricas melhores.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - A Fundação: A Matriz de Confusão

```ad-quote
title:
<p align="justify">Para entender os tipos de erro, usamos a Matriz de Confusão. Vamos aplicar ao Exemplo A (Doença) com um modelo um POUCO melhor, que tentou fazer previsões. Os resultados foram:</p>
```

![[Pasted image 20251103145513.png]]


```ad-quote
title:
|Sigla|Aplicação|
| --- | --- |
|Verdadeiro Positivo (TP)|8 pacientes DOENTES foram corretamente identificados.|
|Verdadeiro Negativo (TN)|985 pacientes SAUDÁVEIS foram corretamente identificados.|
|Falso Positivo (FP)|5 pacientes SAUDÁVEIS foram erroneamente diagnosticados como doentes (alarme falso).|
|Falso Negativo (FN)|2 pacientes DOENTES foram erroneamente liberados como saudáveis (o erro PERIGOSO).|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - As Métricas Essenciais / O "Trade-Off"

```ad-quote
title:
<p align="justify">Agora podemos calcular as métricas reais usando essa matriz.</p>
```
````

````ad-quote
title:
###### **A ) -** RECALL / Sensibilidade ou Revocação

```ad-quote
title:
###### **Pergunta:**
```

```ad-quote
title:
<p align="justify">"De todos os que ESTAVAM REALMENTE DOENTES, quantos o modelo encontrou?"</p>
```

```ad-quote
title:
###### **Foco:**
```

```ad-quote
title:
<p align="justify">Minimizar FALSOS NEGATIVOS (FN).</p>
```

```ad-quote
title:
###### **Fórmula:**
```

```ad-quote
title:
1. $$Recall = VP / (VP + FN)$$
```

```ad-quote
title:
###### **Cálculo:**
```

```ad-quote
title:
1. $$8 / (8 + 2) = 8 / 10 = 80\%$$
```

```ad-quote
title:
###### **Interpretação:**
```

```ad-quote
title:
<p align="justify">O nosso modelo conseguiu "revocar" ou encontrar 80% de todos os pacientes que realmente estavam doentes. Os outros 20% (os FNs) ele "deixou passar".</p>
```
````

````ad-quote
title:
###### **PRECISÃO / Precision**

```ad-quote
title:
###### **Pergunta:**
```

```ad-quote
title:
<p align="justify">"De todas as vezes que o modelo previu 'DOENTE', quantas vezes ele estava certo?"</p>
```

```ad-quote
title:
###### **Foco:**
```

```ad-quote
title:
<p align="justify">Minimizar FALSOS POSITIVOS (FP).</p>
```

```ad-quote
title:
###### **Fórmula:**
```

```ad-quote
title:
1. $$Precisão = VP / (VP + FP)$$
```

```ad-quote
title:
###### **Cálculo:**
```

```ad-quote
title:
1. $$8 / (8 + 5) = 8 / 13 = 61.5\%$$
```

```ad-quote
title:
###### **Interpretação:**
```

```ad-quote
title:
<p align="justify">Das 13 vezes que o modelo deu um alarme de "DOENTE", ele estava correto em apenas 61.5% das vezes. Os outros 38.5% eram Falsos Positivos.</p>
```

```ad-quote
title:
###### **Exemplo B / SPAM:**
```

```ad-quote
title:
<p align="justify">Vamos aplicar a PRECISÃO ao filtro de SPAM. Um alarme falso (FP) aqui é perder um e-mail importante.</p>
```

```ad-quote
title:
###### **Cenário:**
```

```ad-quote
title:
<p align="justify">O modelo previu "SPAM" para 50 e-mails. Desses, 45 eram realmente SPAM (VP=45) e 5 eram IMPORTANTES (FP=5).</p>
```

```ad-quote
title:
###### **Cálculo:**
```

```ad-quote
title:
1. $$Precisão = 45 / (45 + 5) = 45 / 50 = 90\%$$
```

```ad-quote
title:
###### **Interpretação:**
```

```ad-quote
title:
<p align="justify">90% das previsões de SPAM estão corretas. Isso é bom, mas significa que 10% dos e-mails marcados como SPAM eram, na verdade, importantes.</p>
```
````

````ad-quote
title:
###### **C ) -** ESPECIFICIDADE / Specificity

```ad-quote
title:
###### **Pergunta:**
```

```ad-quote
title:
<p align="justify">"De todos os que ESTAVAM REALMENTE SAUDÁVEIS (Negativos), quantos o modelo acertou?"</p>
```

```ad-quote
title:
###### **Foco:**
```

```ad-quote
title:
<p align="justify">É o "Recall da classe Negativa". Também foca em evitar FALSOS POSITIVOS (FP).</p>
```

```ad-quote
title:
###### **Fórmula:**
```

```ad-quote
title:
1. $$Especificidade = VN / (VN + FP)$$
```

```ad-quote
title:
###### **Cálculo:**
```

```ad-quote
title:
1. $$985 / (985 + 5) = 985 / 990 = 99.5\%$$
```

```ad-quote
title:
###### **Interpretação:**
```

```ad-quote
title:
<p align="justify">O modelo foi EXCELENTE em inocentar corretamente os pacientes saudáveis (99.5% de acerto nesse grupo).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - A Métrica de Equilíbrio: F1-Score

```ad-quote
title:
<p align="justify">Vimos que no Exemplo A, o Recall foi 80% e a Precisão foi 61.5%. Um é bom, o outro é mediano. Como saber se o modelo é bom no geral? Usamos o F1-Score (Média Harmônica), que penaliza modelos desequilibrados.</p>
```

```ad-quote
title:
###### **Fórmula:**
```

```ad-quote
title:
1. $$F1 = 2 \cdot (Precisão \cdot Recall) / (Precisão + Recall)$$
```

```ad-quote
title:
###### **Exemplo A / Doença:**
```

```ad-quote
title:
Cálculo: 

1. $$F1 = 2 \cdot (0.615 \cdot 0.80) / (0.615 + 0.80)$$

2. $$F1 = 2 \cdot (0.492) / (1.415)$$

3. $$F1 = 0.984 / 1.415 \approx 69.5\%$$
```

```ad-quote
title:
###### **Comparação:**
```

```ad-quote
title:
Média Aritmética: $(80\% + 61.5\%) / 2 = 70.75\%$ (uma nota "OK"). Média Harmônica (F1): $69.5\%$ (uma nota um pouco MAIS BAIXA, sendo "puxada" para baixo pelo valor menor da Precisão. Se a Precisão fosse 1%, o F1-Score despencaria para quase 2%, enquanto a média aritmética ainda ficaria em 50%).
```

```ad-quote
title:
<p align="justify">O F1-Score é uma avaliação mais HONESTA e PESSIMISTA do equilíbrio do modelo.</p>
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Adaptação para Classificação MULTICLASSE 


````

---