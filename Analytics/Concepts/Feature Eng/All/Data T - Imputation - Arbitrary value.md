---
banner: "![[Pasted image 20260115190114.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Imputação por Valor Arbitrário

```ad-quote
title:
<p align="justify">A imputação por valor arbitrário é uma técnica de tratamento de dados ausentes que consiste em substituir os campos nulos por uma constante pré-determinada. Ao contrário de métodos estocásticos ou baseados em medidas de tendência central, esta abordagem não tenta adivinhar o valor real, mas sim marcar a observação de forma que o algoritmo de machine learning possa distinguir claramente a ausência original da informação.</p>
```

````

> [!quote] **Link:** [Numerical - Arbitrary Value](https://feature-engine.trainindata.com/en/1.8.x/user_guide/imputation/ArbitraryNumberImputer.html)

---

```ad-done
title:

#### **Fase 1 ) - Caso Ideal**

```

---

````ad-quote
title:

##### **01 )** - Premissas e Contexto Teórico

```ad-quote
title:
<p align="justify">A principal premissa deste método é que a ausência do dado é informativa, permitindo que o modelo capture sinais ocultos sobre a observação através de um marcador numérico ou categórico.</p>
```

```ad-quote
title:
|**Conceito**|**Descrição Técnica**|**Impacto no Modelo**|
|---|---|---|
|**Mecanismo MNAR**|Os dados são Missing Not At Random (não faltam ao acaso).|A falta do dado carrega uma mensagem sobre a observação.|
|**Sinalização**|Uso de valores fora do domínio habitual da variável.|Cria uma distinção clara entre dado real e dado ausente.|
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Cenário Ideal de Aplicação

```ad-quote
title:
<p align="justify">Esta técnica atinge sua máxima eficiência em arquiteturas específicas onde a separação lógica de grupos é mais importante do que a preservação da média estatística original.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Tolerância de Dados Faltantes
```

```ad-quote
title:
<p align="justify">Diferente da imputação por média, este método suporta volumes maiores de ausência (acima de 5% ou 10%) sem invalidar o modelo, desde que o objetivo seja a classificação via árvore. Como o valor arbitrário atua como uma nova categoria lógica, o modelo o trata como um grupo distinto, transformando o "vazio" em uma característica útil para a predição.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Algoritmos de Árvore
```

```ad-quote
title:
<p align="justify">O cenário ideal ocorre com modelos como Random Forest ou XGBoost. Eles conseguem criar divisões nos nós especificamente para o valor arbitrário, isolando o efeito da ausência de forma cirúrgica.</p>
```

````

````ad-quote
title:
```ad-quote
title:
###### C ) Representação de Inexistência
```

```ad-quote
title:
<p align="justify">Útil quando o nulo representa algo que não ocorreu. Em tempo de experiência, preencher nulos com -1 permite que o modelo diferencie alguém sem experiência de alguém com 0 anos (recém-contratado).</p>
```
````

---

```ad-done
title:

#### **Fase 2 ) - Características da Técnica**

```

---

````ad-quote
title:

##### **03 )** - Impactos Estatísticos Completos

```ad-quote
title:
<p align="justify">A aplicação deste método gera distorções significativas que devem ser monitoradas, especialmente em modelos que dependem da forma da distribuição ou de relações lineares puras.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Deslocamento da Média
```

```ad-quote
title:
Se o valor arbitrário escolhido for muito distante do centro da massa de dados, a média resultante será severamente deslocada para esse extremo.
```

```ad-quote
title:
A nova média deixará de representar o comportamento típico da população, servindo apenas como um indicador ponderado pela quantidade de valores ausentes.
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Explosão da Variância
```

```ad-quote
title:
A variância tende a aumentar drasticamente se o valor escolhido for um outlier proposital, como 9999 ou -999.
```

```ad-quote
title:
Isso pode dificultar a convergência de algoritmos sensíveis à escala, como redes neurais ou regressões lineares, exigindo reescalonamento posterior.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Enfraquecimento da Correlação
```

```ad-quote
title:
A relação linear entre a variável imputada e as demais será enfraquecida, pois os valores constantes não variam em conjunto com outras características.
```

```ad-quote
title:
O valor arbitrário introduz um ruído estático que quebra a tendência de co-variação, mascarando correlações que existiam nos dados observados.
```
````

---

```ad-done
title:

#### **Fase 3 ) - Particularidade do Método**

```

---

````ad-quote
title:

##### **04 )** - Métrica de Impacto e Definição Matemática

```ad-quote
title:
<p align="justify">A maior particularidade reside na intervenção manual: o cientista deve escolher um valor que garantidamente não exista no conjunto de dados original.</p>
```

```ad-quote
title:

|**Métrica**|**Impacto Esperado**|
|---|---|
|**Média**|Desvio proporcional à distância do valor arbitrário.|
|**Variância**|Aumento artificial se o valor for um extremo.|
|**Distribuição**|Criação de um pico (moda) artificial e isolado.|
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Transformação Funcional
```

```ad-quote
title:
A transformação substitui cada ocorrência nula pela constante escolhida, mantendo os demais valores inalterados para preservar a informação original.
```

```ad-quote
title:
- $$x_{i} = \begin{cases} \alpha, & \text{se } x_i = \text{null} \\ x_i, & \text{caso contrário} \end{cases}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Restrição de Domínio
```

```ad-quote
title:
Para evitar a sobreposição com dados reais e confusão do modelo, a escolha do valor deve respeitar o intervalo observado da variável.
```

```ad-quote
title:
- $$\alpha \notin [\min(X), \max(X)]$$
```
````

---
