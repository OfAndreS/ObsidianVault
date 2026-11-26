
---

````ad-quote
title:

##### **Scikit-learn: A Biblioteca Fundamental para Machine Learning Clássico em Python**

```ad-quote
title:
<p align="justify"><b>Scikit-learn</b> (ou `sklearn`) é a biblioteca de machine learning mais popular e robusta para Python. Com foco em algoritmos de aprendizado clássico, ela se destaca por sua API limpa, consistente e unificada, que permite treinar, avaliar e implantar modelos com poucas linhas de código. Construída sobre o ecossistema científico do Python (<b>NumPy</b>, <b>SciPy</b> e <b>Matplotlib</b>), a Scikit-learn é a ferramenta ideal para tarefas de classificação, regressão, clusterização e pré-processamento de dados.</p>

<p align="justify">Abaixo estão as principais funcionalidades da Scikit-learn, categorizadas para facilitar o entendimento e com exemplos práticos de código.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Pré-processamento e Transformação de Dados (`sklearn.preprocessing`)

```ad-quote
title:
<p align="justify">Antes de treinar um modelo, os dados brutos precisam ser limpos e transformados em um formato numérico adequado. Este módulo fornece uma vasta gama de transformadores para essa finalidade.</p>
```

```ad-quote
title:

| Classe / Método | Descrição | Exemplo de Código |
|---|---|---|
| `StandardScaler` | Padroniza as features removendo a média e escalonando para a variância unitária. | `from sklearn.preprocessing import StandardScaler; scaler = StandardScaler(); scaled = scaler.fit_transform([[1], [2], [3]])` |
| `MinMaxScaler` | Normaliza as features, escalonando-as para um intervalo específico (geralmente [0, 1]). | `from sklearn.preprocessing import MinMaxScaler; scaler = MinMaxScaler(); scaled = scaler.fit_transform([[1], [5], [10]])` |
| `OneHotEncoder` | Converte variáveis categóricas em uma representação numérica binária (dummy). | `from sklearn.preprocessing import OneHotEncoder; enc = OneHotEncoder(); encoded = enc.fit_transform([['gato'], ['cão']])` |
| `LabelEncoder` | Converte rótulos (labels) categóricos em valores inteiros. | `from sklearn.preprocessing import LabelEncoder; enc = LabelEncoder(); encoded = enc.fit_transform(['sp', 'rj', 'mg'])` |
| `SimpleImputer` | Preenche valores ausentes (NaN) usando uma estratégia (média, mediana, etc). | `import numpy as np; from sklearn.impute import SimpleImputer; imputer = SimpleImputer(); imputed = imputer.fit_transform([[1], [np.nan]])` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Seleção e Extração de Características (`sklearn.feature_selection` e `sklearn.decomposition`)

```ad-quote
title:
<p align="justify">Nem todas as características (features) são úteis. Esses módulos ajudam a selecionar as mais relevantes ou a criar novas características a partir das existentes para melhorar o desempenho do modelo.</p>
```
```ad-quote
title:
| Classe / Método | Descrição | Exemplo de Código |
|---|---|---|
| `SelectKBest` | Seleciona as `k` melhores features com base em testes estatísticos. | `from sklearn.feature_selection import SelectKBest; selector = SelectKBest(k=1); X_new = selector.fit_transform(X, y)` |
| `RFE` | Seleciona features removendo recursivamente as menos importantes. | `from sklearn.feature_selection import RFE; from sklearn.linear_model import LinearRegression; selector = RFE(LinearRegression(), n_features_to_select=1); X_new = selector.fit_transform(X, y)` |
| `PCA` | Reduz a dimensionalidade extraindo componentes principais não correlacionados. | `from sklearn.decomposition import PCA; pca = PCA(n_components=2); X_new = pca.fit_transform(X)` |
| `CountVectorizer`| Converte textos em uma matriz de contagem de tokens (palavras).| `from sklearn.feature_extraction.text import CountVectorizer; vec = CountVectorizer(); X_counts = vec.fit_transform(['gato cão', 'gato gato'])`|
| `TfidfVectorizer`| Converte textos em uma matriz de features TF-IDF.| `from sklearn.feature_extraction.text import TfidfVectorizer; vec = TfidfVectorizer(); X_tfidf = vec.fit_transform(['gato cão', 'gato gato'])` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Modelos de Aprendizado Supervisionado

```ad-quote
title:
<p align="justify">Esta é a categoria mais comum de algoritmos, onde o objetivo é aprender uma função que mapeia entradas (`X`) para saídas conhecidas (`y`).</p>
```
```ad-quote
title:

###### **Modelos de Regressão (Prever um valor contínuo)**

| Modelo | Descrição | Exemplo de Código |
|---|---|---|
| `LinearRegression`| Modelo linear simples. | `from sklearn.linear_model import LinearRegression; model = LinearRegression(); model.fit(X, y)` |
| `RandomForestRegressor`| Modelo de ensemble (árvores de decisão) robusto contra overfitting. | `from sklearn.ensemble import RandomForestRegressor; model = RandomForestRegressor(); model.fit(X, y)` |
| `SVR` | Máquina de Vetores de Suporte para regressão. | `from sklearn.svm import SVR; model = SVR(); model.fit(X, y)` |

###### **Modelos de Classificação (Prever uma categoria discreta)**
| Modelo | Descrição | Exemplo de Código |
|---|---|---|
| `LogisticRegression` | Modelo linear para classificação binária ou multiclasse. | `from sklearn.linear_model import LogisticRegression; model = LogisticRegression(); model.fit(X, y)` |
| `RandomForestClassifier`| Modelo de ensemble (árvores de decisão) poderoso para classificação. | `from sklearn.ensemble import RandomForestClassifier; model = RandomForestClassifier(); model.fit(X, y)` |
| `SVC` | Máquina de Vetores de Suporte para classificação. | `from sklearn.svm import SVC; model = SVC(); model.fit(X, y)` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Modelos de Aprendizado Não-Supervisionado

```ad-quote
title:
<p align="justify">Utilizados quando não há rótulos de saída, esses algoritmos encontram padrões, estruturas e agrupamentos ocultos nos próprios dados.</p>
```

```ad-quote
title:
| Tarefa | Modelo | Exemplo de Código |
|---|---|---|
| **Clusterização**| `KMeans` | `from sklearn.cluster import KMeans; model = KMeans(n_clusters=3); clusters = model.fit_predict(X)` |
| **Clusterização**| `DBSCAN` | `from sklearn.cluster import DBSCAN; model = DBSCAN(eps=0.5); clusters = model.fit_predict(X)` |
| **Redução de Dim.** | `PCA` | `from sklearn.decomposition import PCA; pca = PCA(n_components=2); X_reduced = pca.fit_transform(X)` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Validação e Divisão de Dados (`sklearn.model_selection`)

```ad-quote
title:
<p align="justify">Avaliar um modelo nos mesmos dados em que foi treinado é um erro. Este módulo fornece ferramentas essenciais para dividir os dados corretamente e realizar a validação cruzada, garantindo que a performance do modelo seja generalizável.</p>
```
```ad-quote
title:
| Função / Classe | Descrição | Exemplo de Código |
|---|---|---|
| `train_test_split`| Divide os dados em conjuntos de treino e teste. | `from sklearn.model_selection import train_test_split; X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3)` |
| `cross_val_score` | Avalia uma métrica usando validação cruzada. | `from sklearn.model_selection import cross_val_score; scores = cross_val_score(model, X, y, cv=5)` |
| `GridSearchCV` | Busca exaustivamente a melhor combinação de hiperparâmetros. | `from sklearn.model_selection import GridSearchCV; params = {'C':[1, 10]}; gs = GridSearchCV(model, params, cv=5); gs.fit(X, y)` |
| `RandomizedSearchCV`| Busca a melhor combinação de hiperparâmetros de forma aleatória. | `from sklearn.model_selection import RandomizedSearchCV; params = {'C':[1, 10]}; rs = RandomizedSearchCV(model, params, cv=5); rs.fit(X, y)`|
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Métricas de Avaliação (`sklearn.metrics`)

```ad-quote
title:
Após treinar um modelo, é crucial quantificar seu desempenho. Este módulo contém dezenas de métricas para diferentes tipos de tarefas.
```
```ad-quote
title:
###### **Métricas de Classificação**
| Métrica | Descrição | Exemplo de Código (com `y_true`, `y_pred`) |
|---|---|---|
| `accuracy_score` | Percentual de acertos. | `from sklearn.metrics import accuracy_score; accuracy_score(y_true, y_pred)` |
| `precision_score` | Precisão dos rótulos positivos. | `from sklearn.metrics import precision_score; precision_score(y_true, y_pred)` |
| `recall_score` | Sensibilidade (taxa de verdadeiros positivos). | `from sklearn.metrics import recall_score; recall_score(y_true, y_pred)` |
| `confusion_matrix`| Matriz que mostra os erros e acertos entre as classes. | `from sklearn.metrics import confusion_matrix; confusion_matrix(y_true, y_pred)` |

###### **Métricas de Regressão**
| Métrica | Descrição | Exemplo de Código (com `y_true`, `y_pred`) |
|---|---|---|
| `mean_squared_error`| Média dos erros ao quadrado. | `from sklearn.metrics import mean_squared_error; mean_squared_error(y_true, y_pred)` |
| `mean_absolute_error`| Média do valor absoluto dos erros. | `from sklearn.metrics import mean_absolute_error; mean_absolute_error(y_true, y_pred)` |
| `r2_score` | Coeficiente de determinação ($R^2$). | `from sklearn.metrics import r2_score; r2_score(y_true, y_pred)` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Pipelines (`sklearn.pipeline`)

```ad-quote
title:
<p align="justify">Pipelines são uma das ferramentas mais poderosas da Scikit-learn para criar um fluxo de trabalho robusto e reprodutível. Eles permitem encadear múltiplos passos de processamento e modelagem em um único objeto.</p>
```

```ad-quote
title:
| Classe | Descrição | Exemplo de Código |
|---|---|---|
| `Pipeline` | Permite encadear uma sequência de transformadores e um estimador final, tratando todo o fluxo como um único objeto que pode ser treinado (`.fit()`) e usado para prever (`.predict()`). | `from sklearn.pipeline import Pipeline; from sklearn.preprocessing import StandardScaler; from sklearn.linear_model import LogisticRegression; pipe = Pipeline([('scaler', StandardScaler()), ('clf', LogisticRegression())]); pipe.fit(X_train, y_train)`|
```
````

---