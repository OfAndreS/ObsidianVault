---
banner: "![[Pasted image 20260115190114.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Imputação pela Moda

```ad-quote
title:
<p align="justify">A imputação pela moda é uma técnica de tratamento de dados faltantes que consiste em substituir os valores nulos pelo valor mais frequente observado na coluna. É o método padrão para o preenchimento de variáveis qualitativas ou categóricas, visando manter a estrutura de classes sem introduzir categorias inexistentes.</p>
```

````

> [!quote] **Link:** [Categorical - Mode Imputation](https://feature-engine.trainindata.com/en/1.8.x/user_guide/imputation/CategoricalImputer.html)

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
<p align="justify">A técnica baseia-se na probabilidade de massa, assumindo que, na ausência de informação, o valor mais frequente é o que melhor representa a provável realidade da observação.</p>
```

```ad-quote
title:
|**Requisito**|**Descrição Técnica**|**Restrição Aplicada**|
|---|---|---|
|**Tipo de Dado**|Predominante para variáveis categóricas ou numéricas discretas.|Ineficaz para dados numéricos contínuos de alta precisão.|
|**Mecanismo MCAR**|A falta de dado deve ser independente do valor real (totalmente ao acaso).|Se a falta for estrutural (MNAR), a moda reforçará o erro.|
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
<p align="justify">A moda é a ferramenta de escolha quando lidamos com categorias nominais onde não existe uma ordem lógica (como cores ou estados), servindo como uma solução simples e de baixíssimo custo computacional.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Baixo Volume de Ausência
```

```ad-quote
title:
<p align="justify">O método é ideal quando a proporção de nulos é inferior a 5%. Nesse patamar, o impacto na frequência relativa das classes é minimizado, evitando que o modelo "se esqueça" das classes minoritárias durante o treinamento.</p>
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Presença de Classe Dominante
```

```ad-quote
title:
<p align="justify">A técnica é extremamente eficaz quando uma das categorias detém uma maioria clara no dataset. Isso garante que a substituição pelo valor mais comum tenha uma alta probabilidade estatística de acerto em relação ao dado original perdido.</p>
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
<p align="justify">Ao contrário de medidas de tendência central quantitativa, a moda afeta a distribuição de frequências e a entropia da variável, podendo mascarar a diversidade real dos dados.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Superestimação da Moda
```

```ad-quote
title:
A categoria mais frequente torna-se artificialmente mais pesada dentro da amostra total.
```

```ad-quote
title:
Isso pode induzir o algoritmo de machine learning a desenvolver um viés, tendendo a predizer a classe majoritária com mais frequência do que deveria (over-representation).
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Redução da Variabilidade (Entropia)
```

```ad-quote
title:
Ao substituir a incerteza de diversos registros por um único valor repetitivo, a diversidade da informação cai.
```

```ad-quote
title:
A variância e a entropia diminuem, o que pode levar o modelo a subestimar a complexidade e a variabilidade real das características dos indivíduos ou objetos analisados.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Subestimação de Minorias
```

```ad-quote
title:
O preenchimento pela moda ignora sistematicamente a existência de categorias raras ou menos frequentes.
```

```ad-quote
title:
Se o dado faltante pertencia originalmente a uma classe minoritária, essa informação é perdida para sempre, prejudicando a sensibilidade do modelo para detectar padrões em grupos pequenos.
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

##### **04 )** - Métrica de Impacto - Distribuições e Multimodalidade

```ad-quote
title:
<p align="justify">A aplicação da moda requer atenção especial à forma como os dados se agrupam, especialmente quando não há um "vencedor" claro na contagem de frequência.</p>
```


````

````ad-quote
title:

```ad-quote
title:
###### A ) Distribuição Multimodal
```

```ad-quote
title:
Ocorre quando dois ou mais valores possuem a mesma frequência máxima. Exige critério de desempate (primeira ocorrência ou critério de negócio).
```

```ad-quote
title:
- $$Mo(X) = \{x \in X \mid f(x) = \max(f)\}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Imputação em Dados Numéricos
```

```ad-quote
title:
Representa o valor que maximiza a função de massa de probabilidade. É raramente usada em dados contínuos devido à baixa taxa de repetição.
```

```ad-quote
title:
- $$x_{i} = \text{argmax}_{x} P(X=x)$$
```
````

---