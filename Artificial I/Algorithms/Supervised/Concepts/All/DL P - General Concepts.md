---
banner: "![[Pasted image 20250926094750.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Visão Geral do Aprendizado Supervisionado

```ad-quote
title:
<p align="justify">O Aprendizado Supervisionado é uma abordagem de Machine Learning na qual ensinamos um computador a tomar decisões ou fazer previsões com base em exemplos. A "supervisão" vem do fato de que fornecemos ao algoritmo um conjunto de dados previamente rotulados, ou seja, cada exemplo de entrada já possui a resposta correta (o "rótulo"). O objetivo é que o modelo aprenda a relação entre as entradas e as saídas para, então, prever a saída para novos dados que ele nunca viu antes.</p>
```

```ad-quote
title:
<p align="justify">Pense em como uma criança aprende a identificar animais. Você mostra a ela uma foto de um gato (entrada) e diz "isto é um gato" (rótulo). Depois de ver várias fotos de gatos e outros animais com seus respectivos nomes, a criança começa a aprender os padrões (pelos, orelhas pontudas, bigodes) e se torna capaz de identificar um gato em uma foto nova. O aprendizado supervisionado funciona de maneira análoga.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Fundamentos e Conceitos Essenciais

```ad-quote
title:
<p align="justify">A espinha dorsal do aprendizado supervisionado são Os Dados Rotulados (Labeled Data). Um conjunto de dados rotulados é composto por duas partes principais: As Features (Características ou Variáveis Independentes), que são os atributos de entrada que descrevem cada exemplo, e os Labels (Rótulos ou Variáveis-Alvo), que representam a resposta correta ou o resultado que queremos prever.</p>
```

```ad-quote
title:
###### **Tipos de Problemas Supervisionados:**
```

```ad-quote
title:

|Tipo&nbsp; | Definição&nbsp; | Exemplos | Algoritmos Comuns |
| :--- | :--- | :--- | :--- |
|**Classification**|O objetivo é prever um rótulo de categoria discreta. A saída é uma classe.|- Um e-mail é `spam` ou `não spam`? <br>- Uma transação é `fraudulenta` ou `legítima`? <br>- Uma imagem é de um `gato`, `cachorro` ou `pássaro`?|Regressão Logística, KNN, SVM, Árvores de Decisão, Random Forest, Naive Bayes.|
|**Regression**|O objetivo é prever um valor numérico contínuo. A saída é um número.|- Qual será o `preço de uma casa`? <br>- Qual será a `temperatura amanhã`? <br>- Quantas `vendas` ocorrerão no próximo trimestre?|Regressão Linear, Regressão Polinomial, Árvores de Decisão, Random Forest, SVR, Gradient Boosting.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - O Fluxo de Trabalho (Pipeline) de um Projeto

```ad-quote
title:
<p align="justify">Construir um modelo de aprendizado supervisionado segue um processo bem definido, desde a obtenção dos dados até a avaliação final. A primeira etapa envolve A Aquisição e Preparação dos Dados, que inclui a coleta de dados de diversas fontes e, crucialmente, A Limpeza e O Pré-processamento. Esta fase trata de dados ausentes, formata e padroniza informações, realiza a engenharia de features para criar novas variáveis e codifica variáveis categóricas em números, utilizando ferramentas como as bibliotecas PANDAS e NUMPY.</p>
```

![[Pasted image 20250926094904.png]]

```ad-quote
title:
<p align="justify">A segunda etapa é A Divisão dos Dados (Data Splitting). Para avaliar honestamente se um modelo aprendeu a generalizar, nunca devemos avaliá-lo com os mesmos dados que ele usou para treinar. Por isso, dividimos nosso conjunto de dados.</p>
```

```ad-quote
title:
###### **Abordagens para Divisão de Dados:**
```

```ad-quote
title:

|Abordagem&nbsp; | Definição&nbsp; | Componentes |
| :--- | :--- | :--- |
|**Simples (70/30 ou 80/20)**|Divide os dados em dois conjuntos.|**Conjunto de Treinamento (Training Set):** Usado para que o modelo aprenda os padrões. <br> **Conjunto de Teste (Test Set):** Guardado e usado uma única vez no final para a avaliação de desempenho. |
|**Robusta (Recomendada)**|Divide os dados em três conjuntos para uma avaliação mais precisa e para o ajuste do modelo.|**Conjunto de Treinamento:** Usado para o treinamento básico. <br> **Conjunto de Validação (Validation Set):** Usado para o ajuste de hiperparâmetros (as "configurações" do algoritmo). <br> **Conjunto de Teste:** Usado apenas para a avaliação final e definitiva do modelo. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Avaliação de Modelos e Generalização

```ad-quote
title:
<p align="justify">O objetivo final não é criar um modelo que decore perfeitamente os dados de treinamento, mas sim um que generalize bem para dados novos. Neste contexto, é vital entender dois problemas comuns: O Overfitting (Sobreajuste), que ocorre quando o modelo se ajusta demais aos dados de treino, perdendo a capacidade de generalizar, e O Underfitting (Subajuste), que ocorre quando o modelo é simples demais e não captura os padrões dos dados.</p>
```

```ad-quote
title:
<p align="justify">Uma técnica robusta para avaliação é A Validação Cruzada (Cross-Validation). O método mais comum, K-Fold, divide os dados de treinamento em K partes, usando K-1 partes para treinar e 1 para validar, repetindo o processo K vezes. A média dos resultados oferece uma estimativa de desempenho mais estável e confiável.</p>
```

```ad-quote
title:
###### **Métricas Essenciais de Desempenho para Classificação:**
```

```ad-quote
title:

|Métrica&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|**Acurácia**|Percentual de previsões corretas. Pode ser enganosa em classes desbalanceadas.|
|**Matriz de Confusão**|Tabela que mostra os acertos e erros (Verdadeiros/Falsos Positivos/Negativos).|
|**Precisão**|Dos que foram classificados como positivos, quantos eram realmente positivos? Importante quando o custo de um falso positivo é alto.|
|**Recall (Sensibilidade)**|Dos que eram realmente positivos, quantos o modelo conseguiu identificar? Importante quando o custo de um falso negativo é alto.|
|**F1-Score**|Média harmônica entre Precisão e Recall, buscando um balanço entre as duas.|

```

```ad-quote
title:
###### **Métricas Essenciais de Desempenho para Regressão:**
```

```ad-quote
title:

|Métrica&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|**Erro Absoluto Médio (MAE)**|A média da diferença absoluta entre os valores previstos e os reais.|
|**Erro Quadrático Médio (MSE)**|A média do quadrado das diferenças. Penaliza mais os erros grandes.|
|**Raiz do Erro Quadrático Médio (RMSE)**|A raiz quadrada do MSE, na mesma unidade da variável-alvo.|
|**Coeficiente de Determinação (R²)**|Indica a proporção da variância da variável-alvo que é explicada pelo modelo.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">Em resumo, o Aprendizado Supervisionado é um campo poderoso que segue um ciclo estruturado: coletar e preparar dados rotulados, dividir esses dados para um treinamento e avaliação honestos, treinar um algoritmo para aprender os padrões e, finalmente, avaliar seu desempenho em dados nunca vistos para garantir que ele seja útil no mundo real.</p>
```
````

---