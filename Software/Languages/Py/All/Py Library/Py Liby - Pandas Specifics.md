
---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify"><b>Pandas</b> é uma biblioteca de código aberto fundamental para análise e manipulação de dados em Python. Ela introduz duas estruturas de dados principais e de alta performance: o <b>`DataFrame`</b>, uma tabela bidimensional com colunas que podem ter tipos diferentes, similar a uma planilha ou tabela SQL, e a <b>`Series`</b>, que é essencialmente uma única coluna. O poder do pandas reside em sua capacidade de ler, processar, limpar e analisar dados tabulares de forma intuitiva e eficiente.</p>
```

>[!quote] **Doc:** [Pandas Doc](https://pandas.pydata.org/docs/getting_started/index.html)

>[!quote] **Colab:** [Pandas Colab](https://colab.research.google.com/drive/1_rmo89NgUX_JEs0AHJbvqFOzK_QSGcdF)

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Fundamentos das Estruturas de Dados

```ad-quote
title:
**Características Principais:**
```

```ad-quote
title:

| Característica | Explicação |
| --- | --- |
| Heterogêneos | As colunas de um DataFrame podem conter diferentes tipos de dados (int, float, string, etc.). |
| Tamanho Mutável | É possível adicionar ou remover colunas e linhas de um DataFrame. |
| Rótulos nos Eixos | Tanto as linhas (index) quanto as colunas possuem rótulos para acesso e manipulação. |
| Poderoso para Dados Ausentes | Possui ferramentas integradas para lidar com dados faltantes (NaN). |
| Orientado a Colunas | As operações são otimizadas para serem executadas em colunas (Series). |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Criação de DataFrames

```ad-quote
title:
<p align="justify"><b>A partir de Dicionários Python:</b></p>
```

```python
import pandas as pd

# DataFrame a partir de um dicionário de listas
dados = {'Nome': ['Ana', 'Bruno', 'Carla'],
         'Idade': [23, 34, 19],
         'Cidade': ['São Paulo', 'Rio de Janeiro', 'Belo Horizonte']}
df = pd.DataFrame(dados)
```

```ad-quote
title:
<p align="justify"><b>A partir de Arquivos Externos:</b></p>
```

```python
# Supondo que você tenha um arquivo 'dados.csv' no mesmo diretório

# Lendo um arquivo CSV
# df_csv = pd.read_csv('dados.csv')

# Lendo um arquivo Excel
# df_excel = pd.read_excel('dados.xlsx')
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Atributos e Seleção de Dados

```ad-quote
title:
DataFrames possuem atributos que descrevem seus metadados e métodos poderosos para indexação e seleção de dados, permitindo filtrar e fatiar as informações de múltiplas maneiras.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Principais Atributos**
```

```ad-quote
title:
Acessam as propriedades do DataFrame.
```

```python
# Usando o df criado anteriormente
print(df.shape)   # (3, 3) -> 3 linhas, 3 colunas
print(df.index)   # RangeIndex(start=0, stop=3, step=1) -> rótulos das linhas
print(df.columns) # Index(['Nome', 'Idade', 'Cidade'], dtype='object') -> rótulos das colunas
print(df.dtypes)  # Mostra o tipo de dado de cada coluna
```
````

````ad-quote
title:
```ad-quote
title:
###### **Seleção de Colunas e Linhas (`loc` e `iloc`)**
```

```ad-quote
title:
Usa-se `[]` para colunas e `.loc[]` (por rótulo) ou `.iloc[]` (por posição inteira) para linhas e colunas.
```

```python
# Selecionando uma coluna (retorna uma Series)
print(df['Nome'])

# Selecionando múltiplas colunas (retorna um DataFrame)
print(df[['Nome', 'Cidade']])

# Selecionando uma linha pelo rótulo do índice (loc)
print(df.loc[0])

# Selecionando uma linha pela posição inteira (iloc)
print(df.iloc[1])

# Selecionando um subconjunto de linhas e colunas
print(df.loc[0:1, ['Nome', 'Idade']]) # Linhas 0 e 1, colunas 'Nome' e 'Idade'
```
````

````ad-quote
title:
```ad-quote
title:
###### **Seleção Condicional (Filtros)**
```

```ad-quote
title:
Permite selecionar linhas com base em uma ou mais condições lógicas.
```

```python
# Filtra o DataFrame para mostrar apenas pessoas com mais de 20 anos
maiores_de_20 = df[df['Idade'] > 20]
print(maiores_de_20)
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Manipulação de Dados

```ad-quote
title:
Pandas se destaca na limpeza, transformação e agregação de dados.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Adicionar e Remover Colunas**
```

```ad-quote
title:
A criação de novas colunas é simples e a remoção é feita com o método `.drop()`.
```

```python
# Adicionando uma nova coluna
df['Salario'] = [5000, 8000, 3500]

# Removendo uma coluna (axis=1 indica que é uma coluna)
df = df.drop('Cidade', axis=1)
print(df)
```
````

````ad-quote
title:
```ad-quote
title:
###### **Tratamento de Dados Ausentes**
```

```ad-quote
title:
Oferece funções para remover ou preencher valores nulos (`NaN`).
```

```python
import numpy as np
df_com_nan = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, np.nan, 6]})

# Remove linhas com qualquer valor NaN
print(df_com_nan.dropna())

# Preenche valores NaN com a média da coluna
print(df_com_nan.fillna(df_com_nan.mean()))
```
````

````ad-quote
title:
```ad-quote
title:
###### **Agrupamento de Dados (Group By)**
```

```ad-quote
title:
Similar ao GROUP BY do SQL, permite agrupar dados e aplicar funções de agregação.
```

```python
dados_vendas = {'Vendedor': ['João', 'Maria', 'João', 'Maria', 'João'],
                'Valor': [250, 300, 350, 400, 150]}
df_vendas = pd.DataFrame(dados_vendas)

# Agrupa por vendedor e calcula o total de vendas de cada um
total_por_vendedor = df_vendas.groupby('Vendedor')['Valor'].sum()
print(total_por_vendedor)
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Métodos Úteis e Funções

```ad-quote
title:
<p align="justify"><b>Operações Comuns:</b></p>
```

```python
# Obtém contagem de valores únicos em uma coluna
print(df_vendas['Vendedor'].value_counts())

# Ordena o DataFrame pelos valores de uma coluna
print(df_vendas.sort_values(by='Valor', ascending=False))

# Aplica uma função a uma coluna
df['Idade_Dobrada'] = df['Idade'].apply(lambda x: x * 2)
```

```ad-quote
title:
<p align="justify"><b>Combinação de DataFrames:</b></p>
```

```python
df1 = pd.DataFrame({'ID': [1, 2, 3], 'Nome': ['A', 'B', 'C']})
df2 = pd.DataFrame({'ID': [1, 2, 4], 'Valor': [100, 200, 400]})

# Une dois DataFrames com base em uma coluna em comum (similar ao JOIN)
merged_df = pd.merge(df1, df2, on='ID', how='inner')
print(merged_df)
```
````

---