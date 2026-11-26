
---

````ad-quote
title:

##### **Pandas: A Ferramenta Essencial para Análise de Dados em Python**

```ad-quote
title:
<p align="justify"><b>Pandas</b> é uma biblioteca de código aberto construída sobre o NumPy, projetada especificamente para manipulação e análise de dados. Ela introduz duas estruturas de dados rápidas, flexíveis e expressivas: o <b>DataFrame</b> (uma tabela bidimensional, heterogênea e com rótulos) e a <b>Series</b> (um array unidimensional com rótulos). Pandas é a ferramenta padrão para praticamente qualquer tarefa de limpeza, transformação, análise e visualização de dados estruturados em Python, formando a base do ecossistema de Data Science.</p>

<p align="justify">Abaixo estão os principais métodos e funcionalidades do Pandas, categorizados para facilitar o entendimento.</p>
```

>[!quote] **Colab:** [Pandas Colab](https://colab.research.google.com/drive/1_rmo89NgUX_JEs0AHJbvqFOzK_QSGcdF)

>[!quote] **Link:** [Generate Data](https://www.mockaroo.com/)
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### Intro ) - Um Guia Abrangente de Funções do Pandas
```ad-quote
title:
<p align="justify">Com certeza. Entendido. O objetivo é criar a lista mais completa e abrangente possível, unindo as funções essenciais com as mais avançadas e especializadas que discutimos, em um único guia de referência.</p>
```
```ad-quote
title:
<p align="justify">É importante notar que listar todas as funções existentes no Pandas é impraticável (são centenas, incluindo muitas internas ou de uso raro). Em vez disso, esta lista representa um compêndio de praticamente todas as funções que você precisará para a grande maioria das tarefas de análise de dados, do básico ao avançado.</p>
```
```ad-quote
title:
<p align="justify">Aqui está a lista consolidada, organizada por tópicos.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### 01 ) - Leitura e Escrita de Dados (I/O)

```ad-quote
title:
<p align="justify">Para carregar dados de diversas fontes para um DataFrame ou salvar um DataFrame em um arquivo.</p>
```

```ad-quote
title:

| Função | Descrição |
| :--- | :--- |
| `pd.read_csv()` | Lê um arquivo de valores separados por vírgula (CSV) para um DataFrame. |
| `df.to_csv()` | Escreve o DataFrame em um arquivo CSV. |
| `pd.read_excel()` | Lê um arquivo do Microsoft Excel (.xls, .xlsx) para um DataFrame. |
| `df.to_excel()` | Escreve o DataFrame em um arquivo do Microsoft Excel. |
| `pd.read_sql()` | Lê dados de uma tabela ou consulta SQL para um DataFrame. |
| `df.to_sql()` | Escreve os registros de um DataFrame em um banco de dados SQL. |
| `pd.read_json()` | Converte uma string JSON em um objeto DataFrame. |
| `df.to_json()` | Converte o DataFrame para uma representação em string JSON. |
| `pd.read_html()` | Lê tabelas HTML de uma página da web para uma lista de DataFrames. |
| `pd.read_parquet()`| Carrega um arquivo no formato Parquet para um DataFrame. |
| `df.to_parquet()` | Escreve o DataFrame no formato Parquet. |
| `pd.read_pickle()`| Carrega um objeto Python serializado (pickle) do disco. |
| `df.to_pickle()` | Salva um objeto Python (como um DataFrame) em formato pickle. |
| `pd.read_feather()`| Lê um arquivo no formato Feather. Rápido e eficiente. |
| `df.to_feather()` | Escreve o DataFrame no formato Feather. |
| `pd.read_stata()` | Lê um arquivo no formato Stata. |
| `df.to_stata()` | Escreve o DataFrame no formato Stata. |
| `pd.read_clipboard()`| Lê o texto da área de transferência e o passa para o read_csv(). |
| `df.to_clipboard()`| Copia o objeto para a área de transferência do sistema. |

```

```ad-quote
title:
<p align="justify">Nota: Funções de leitura como read_csv possuem parâmetros importantes como chunksize para ler arquivos grandes em pedaços.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### 02 ) - Seleção, Indexação e Fatiamento

```ad-quote
title:
<p align="justify">Para acessar e selecionar subconjuntos específicos dos seus dados.</p>
```

```ad-quote
title:
###### Acessores Principais
```

```ad-quote
title:

| Acessor | Descrição |
| :--- | :--- |
| `df[]` | Usado para selecionar colunas por nome ou múltiplas colunas. Também pode fatiar linhas. |
| `df.loc[]` | Acessa um grupo de linhas e colunas por rótulos (nomes) ou uma máscara booleana. |
| `df.iloc[]`| Acessa um grupo de linhas e colunas por posição inteira (de 0 a n-1). |
| `df.at[]` | Acessa um valor escalar único usando rótulos. Mais rápido que loc para um único valor. |
| `df.iat[]` | Acessa um valor escalar único usando posições inteiras. Mais rápido que iloc para um único valor. |

```

```ad-quote
title:
###### Seleção Condicional e Filtragem
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.query(expr)` | Filtra linhas usando uma expressão booleana em formato de string. Ex: df.query('coluna_A > 5'). |
| `df.where(cond, other)` | Substitui valores onde a condição cond é False. |
| `df.mask(cond, other)` | O oposto de where. Substitui valores onde a condição cond é True. |
| `df.isin(values)` | Retorna um booleano indicando se cada elemento do DataFrame está contido em values. |

```

```ad-quote
title:
###### Visualização e Amostragem
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.head(n)` | Retorna as primeiras n linhas do DataFrame (padrão é 5). |
| `df.tail(n)` | Retorna as últimas n linhas do DataFrame (padrão é 5). |
| `df.sample(n)`| Retorna uma amostra aleatória de n itens. |

```

```ad-quote
title:
###### Indexação Avançada (MultiIndex)
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.set_index([c1, c2])` | Cria um MultiIndex (índice hierárquico) a partir de colunas existentes. |
| `df.reset_index()` | Converte os níveis do índice de volta em colunas. |
| `df.swaplevel()` | Troca a ordem de dois níveis em um MultiIndex. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### 03 ) - Limpeza e Tratamento de Dados

```ad-quote
title:
###### Dados Ausentes (Missing Data)
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.isnull()` / `df.isna()` | Retorna um DataFrame booleano indicando quais valores são nulos (NaN, None). |
| `df.notnull()` / `df.notna()`| O oposto de isnull(), retorna True para valores não nulos. |
| `df.dropna()` | Remove linhas ou colunas com valores ausentes. |
| `df.fillna(valor)` | Preenche valores ausentes com um valor específico, média, mediana, etc. |
| `df.interpolate()`| Preenche valores NaN usando diferentes métodos de interpolação (ex: linear). |

```

```ad-quote
title:
###### Duplicatas e Substituições
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.duplicated()` | Retorna uma Series booleana indicando se cada linha é uma duplicata. |
| `df.drop_duplicates()`| Remove linhas duplicadas do DataFrame. |
| `df.replace(a, b)` | Substitui valores a por valores b. |
| `df.rename(columns={...})`| Altera os nomes das colunas ou dos índices. |
| `df.clip()` | Limita os valores a um intervalo especificado (limites inferior e superior). |

```

```ad-quote
title:
###### Tipos de Dados e Strings
```

```ad-quote
title:

| Acessor/Função | Descrição |
| :--- | :--- |
| `df.astype(tipo)` | Converte o tipo de dados de uma ou mais colunas. |
| `pd.to_numeric()` | Converte um argumento para um tipo numérico de forma robusta. |
| `pd.to_datetime()`| Converte um argumento para o tipo datetime. |
| `pd.to_timedelta()`| Converte um argumento para o tipo Timedelta. |
| `pd.Categorical()`| Cria um tipo de dado categórico para otimizar memória e desempenho. |
| `series.str.*` | Acessor para aplicar funções de string (ex: .str.lower(), .str.contains(), .str.split()). |
| `series.cat.*` | Acessor para aplicar funções em dados do tipo Categórico. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### 04 ) - Manipulação e Transformação de Dados

```ad-quote
title:
###### Combinação de DataFrames
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `pd.concat()` | Concatena (junta) múltiplos DataFrames ao longo de um eixo. |
| `df.merge()` | Combina DataFrames com base em valores de colunas comuns (similar a um JOIN de SQL). |
| `df.join()` | Combina DataFrames com base nos seus índices. |

```

```ad-quote
title:
###### Remodelagem e Pivoteamento
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.pivot()` | Remodela dados com base nos valores das colunas. |
| `df.pivot_table()` | Cria uma tabela dinâmica (pivot table) que pode agregar dados. |
| `pd.melt()` | Transforma um DataFrame de um formato "largo" para um "longo". |
| `df.stack()` | "Empilha" as colunas, transformando-as em um novo nível de índice. |
| `df.unstack()` | "Desempilha" o último nível do índice, transformando-o em colunas. |
| `df.explode(column)` | Transforma cada elemento de um objeto tipo lista em uma nova linha. |
| `pd.crosstab()` | Cria uma tabela de referência cruzada (tabela de frequência). |

```

```ad-quote
title:
###### Ordenação e Funções Gerais
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.sort_values()` | Ordena o DataFrame por valores em uma ou mais colunas. |
| `df.sort_index()` | Ordena o DataFrame com base nos rótulos do índice. |
| `df.apply(func)` | Aplica uma função func ao longo de um eixo do DataFrame. |
| `df.map(func)` | (Apenas para Series) Aplica uma função func elemento por elemento. |
| `df.pipe(func)` | Permite encadear operações, passando o DataFrame para uma função func. |
| `pd.get_dummies()`| Converte variáveis categóricas em variáveis "dummy" (one-hot encoding). |

```

```ad-quote
title:
###### Discretização (Binning)
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `pd.cut()` | Segmenta valores em "bins" de largura fixa com base nos valores. |
| `pd.qcut()` | Segmenta valores em "bins" com base em quantis (cada bin tem ~ o mesmo n° de observações). |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### 05 ) - Agrupamento e Agregação (GroupBy)

```ad-quote
title:
<p align="justify">Funcionalidades baseadas no processo "Split-Apply-Combine".</p>
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.groupby(by=...)` | Divide o DataFrame em grupos com base nos critérios especificados. |
| `.agg()` / `.aggregate()`| Aplica uma ou mais funções de agregação aos grupos. |
| `.transform(func)` | Aplica uma função a cada grupo e retorna um objeto com o mesmo índice do original. |
| `.filter(func)` | Filtra e retorna os grupos que satisfazem uma condição. |

```

```ad-quote
title:
###### Agregações Comuns
```

```ad-quote
title:
<p align="justify">sum(), mean(), median(), count(), size(), min(), max(), std(), var(), first(), last(), nunique().</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### 06 ) - Análise Estatística e Computacional

```ad-quote
title:
###### Estatísticas Descritivas
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.describe()` | Gera estatísticas descritivas (contagem, média, desvio padrão, min, max, quartis). |
| `df.corr()` | Calcula a correlação de Pearson entre as colunas. |
| `df.cov()` | Calcula a covariância entre as colunas. |
| `df.value_counts()`| (Apenas para Series) Retorna uma contagem de cada valor único. |
| `df.rank()` | Calcula o ranking dos dados (ex: 1°, 2°, 3°). |
| `df.pct_change()` | Calcula a variação percentual entre elementos. |
| `df.cumsum()` / `cumprod()`| Calcula a soma / produto cumulativo. |

```

```ad-quote
title:
###### Funções de Janela (Window Functions)
```

```ad-quote
title:

| Função/Método | Descrição |
| :--- | :--- |
| `df.rolling(window=...)`| Fornece funcionalidade de janela móvel para cálculos (ex: média móvel). |
| `df.expanding()` | Fornece funcionalidade de janela expansiva (cálculos cumulativos desde o início). |
| `df.ewm()` | Fornece funcionalidade de janela móvel ponderada exponencialmente. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### 07 ) - Funcionalidades de Séries Temporais

```ad-quote
title:

| Acessor/Função | Descrição |
| :--- | :--- |
| `series.dt.*` | Acessor para extrair propriedades de data/hora (ex: .dt.year, .dt.month, .dt.weekday). |
| `pd.date_range()` | Cria um índice de datas (DatetimeIndex) com uma frequência específica. |
| `pd.bdate_range()`| Cria um índice de datas contendo apenas dias úteis. |
| `df.resample(rule)`| Reamostra dados de séries temporais para converter frequências (ex: de diário para mensal). |
| `df.shift(periods)`| Desloca os dados por um número periods de períodos. |
| `df.asfreq(freq)` | Converte a série temporal para uma frequência especificada. |
| `series.tz_localize()`| Adiciona informação de fuso horário a uma série temporal. |
| `series.tz_convert()`| Converte uma série temporal para um fuso horário diferente. |

```
````

---