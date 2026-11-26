---
banner: "![[Pasted image 20260118174047.png]]"
---

---

````ad-quote
title:
##### **Tip ) -** Dica de Performance para o Projeto GTZAN

```ad-quote
title:
No processamento de áudio, ao extrair MFCCs de vários arquivos, armazene cada resultado em uma lista de DataFrames e use o pd.concat() uma única vez ao final do loop. Isso evita a fragmentação de memória e acelera drasticamente o script. Para persistência de dados, considere o pd.read_pickle() ou pd.read_parquet(), que preservam os tipos de dados originais melhor que o CSV.
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **01 ) -** Adicionando Novas Colunas

```ad-quote
title:
<p align="justify">Adicionar colunas é a forma mais simples de enriquecer seu conjunto de dados com novas variáveis ou cálculos. Abaixo estão as principais técnicas para manipulação no eixo vertical.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Atribuição Direta
```

```ad-quote
title:
É a forma mais rápida. Você define o nome da nova coluna entre colchetes e atribui os valores (uma lista, uma Series ou um valor escalar).
```

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({'Produto': ['Monitor', 'Mouse'], 'Preço': [1200, 80]})

# Adicionando uma coluna com valor fixo
df['Estoque'] = 50

# Adicionando uma coluna calculada
df['Total_Valor'] = df['Preço'] * df['Estoque']

print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
   Produto  Preço  Estoque  Total_Valor
0  Monitor   1200       50        60000
1    Mouse     80       50         4000
```
````

````ad-quote
title:

```ad-quote
title:
##### D ) O Método insert()
```

```ad-quote
title:
Diferente da atribuição direta (que coloca a coluna no final), o insert permite escolher a posição exata através do índice da coluna.
```

```python
# Sintaxe: df.insert(posição, nome, valores)
df.insert(1, 'Categoria', 'Eletrônicos')

print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
   Produto    Categoria  Preço  Estoque  Total_Valor
0  Monitor  Eletrônicos   1200       50        60000
1    Mouse  Eletrônicos     80       50         4000
```
````

````ad-quote
title:

```ad-quote
title:
##### E ) O Método assign()
```

```ad-quote
title:
Este método é muito utilizado em encadeamento de funções (method chaining). Ele não altera o DataFrame original, mas retorna uma cópia com a nova coluna incluída.
```

```python
df_novo = df.assign(Imposto = df['Preço'] * 0.1)
print(df_novo[['Produto', 'Preço', 'Imposto']])
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
   Produto  Preço  Imposto
0  Monitor   1200    120.0
1    Mouse     80      8.0
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **02 ) -** Adicionando Novas Colunas NaN

```ad-quote
title:
<p align="justify">Uma vez que a lógica aplicada ao Pandas tem origem nos dados tubulares, se faz necessário adicionar todas as células de uma nova linha para o índice esteja completo. Entretanto, uma nova coluna a ser adicionada pode ter a quantidade de dados inferior ou superior aos dados já presentes no DataFrame atual. Essa sessão visa informar a melor maneira de se trabalhar nesse cenário.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) NaN nas Colunas Novas
```

```ad-quote
title:
Para adicionar mais uma coluna com diferentes valores de index, basta transformar a lista em um pd.Siries e passar a mesma como argumento para a nova coluna. O pandas irá preencher automaticamente as colunas restantes com NaN.
```

```python
import pandas as pd
import numpy as np

rValues = np.random.randint(100, size=(4,2))
cityNames = ['Paris', 'London']

dfTest = pd.DataFrame(rValues, columns=['A', 'B'])
dfTest['C'] = pd.Series(cityNames)

print(dfTest)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
    A    B      C
0  22  72   Paris
1  52  63  London
2  46  45     NaN
3  97  81     NaN
```
````

````ad-quote
title:

```ad-quote
title:
##### C ) NaN nas Colunas Antigas
```

```ad-quote
title:
Se o seu objetivo é que o _DataFrame_ cresça para aceitar todas as 6 cidades e, com isso, as colunas originais (A e B) recebam _NaN_ nos novos índices (4 e 5), você deve reindexar o próprio _DataFrame_ primeiro.
```

```python
import pandas as pd
import numpy as np

rValues = np.random.randint(100, size=(4,2))
cityNames = ['Paris', 'London', 'Chicago', 'Berlin', 'Lima', 'Toronto']

dfTest = pd.DataFrame(rValues, columns=['A', 'B'])

# 1. Reindexamos o DataFrame para ter o mesmo tamanho da lista de cidades
dfTest = dfTest.reindex(range(len(cityNames)))

# 2. Agora atribuímos a lista. Os índices 4 e 5 de A e B serão NaN
dfTest['C'] = cityNames

print(dfTest)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
      A     B        C
0  45.0  12.0    Paris
1  88.0  33.0   London
2  10.0  95.0  Chicago
3  67.0  41.0   Berlin
4   NaN   NaN     Lima
5   NaN   NaN  Toronto
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **03 ) -** Adicionando Novas Linhas

```ad-quote
title:
<p align="justify">Historicamente, usava-se o método append, mas ele foi depreciado. Hoje, a forma recomendada para expandir o DataFrame horizontalmente é o uso do concat ou loc.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Usando pd.concat()
```

```ad-quote
title:
Este método empilha dois ou mais DataFrames. É a forma mais eficiente para grandes volumes de dados.
```

```python
df1 = pd.DataFrame({'Nome': ['André'], 'Idade': [20]})
df2 = pd.DataFrame({'Nome': ['Maria'], 'Idade': [22]})

# ignore_index=True garante que o índice seja recalculado de 0 a N
df_final = pd.concat([df1, df2], ignore_index=True)

print(df_final)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
    Nome  Idade
0  André     20
1  Maria     22
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) Usando .loc[] para uma Única Linha
```

```ad-quote
title:
Ideal para quando você precisa adicionar apenas um registro manualmente em um índice específico.
```

```python
df_final.loc[2] = ['João', 25]
print(df_final)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
    Nome  Idade
0  André     20
1  Maria     22
2   João     25
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **03 ) -** Combinando Dados (Merge e Join)

```ad-quote
title:
<p align="justify">Quando os dados estão em tabelas separadas e precisam ser cruzados por uma chave comum, utilizamos operações de junção semelhantes ao SQL.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) O Método pd.merge()
```

```ad-quote
title:
Ideal para cruzamentos complexos (Inner, Left, Right, Outer Joins). O foco aqui é o conteúdo das colunas.
```

```python
df_alunos = pd.DataFrame({'ID': [1, 2], 'Nome': ['André', 'Maria']})
df_notas = pd.DataFrame({'ID': [1, 2], 'Nota': [9.5, 8.0]})

# Cruzando os dados pelo ID
df_relatorio = pd.merge(df_alunos, df_notas, on='ID')

print(df_relatorio)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
   ID   Nome  Nota
0   1  André   9.5
1   2  Maria   8.0
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **04 ) -** Métodos Avançados e Patching

```ad-quote
title:
<p align="justify">Para situações específicas como correção de dados ou estruturas hierárquicas, o Pandas oferece ferramentas de nicho altamente eficazes.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) combine_first() e update()
```

```ad-quote
title:
O combine_first() preenche valores nulos de uma tabela com os de outra. Já o update() substitui valores existentes de forma direta se os índices coincidirem.
```

```python
df1 = pd.DataFrame({'A': [1, None], 'B': [None, 4]})
df2 = pd.DataFrame({'A': [1, 10], 'B': [20, 4]})

df_patch = df1.combine_first(df2)
print(df_patch)
```
````

---