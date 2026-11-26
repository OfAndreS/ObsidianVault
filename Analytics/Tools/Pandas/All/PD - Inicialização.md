---
banner: "![[Pasted image 20260118174047.png]]"
---

---

````ad-quote
title:
##### **Tip ) -** Dica de Performance

```ad-quote
title:
Se você estiver lidando com milhões de linhas no seu projeto de iniciação científica, evite criar o _DataFrame_ linha por linha em um loop (usando _append_ ou _loc_). O ideal é acumular os dados em uma _lista de dicionários_ pura do Python e, apenas no final, chamar o _pd.DataFrame(sua_lista)_. Isso é muito mais eficiente em termos de memória e processamento.
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **01 ) -** Usando o Construtor pd.DataFrame()

```ad-quote
title:
<p align="justify"> O construtor pd.DataFrame funciona como a porta de entrada principal da biblioteca. Ele é projetado para ser altamente flexível, permitindo que você transforme estruturas de dados nativas do Python, como listas e dicionários, em tabelas organizadas de forma quase instantânea.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Dicionário de Listas ou Arrays
```

```ad-quote
title:
O construtor principal é extremamente versátil e se adapta ao formato da entrada. Esta é a forma mais comum. As chaves do dicionário definem os nomes das colunas e as listas definem os dados das linhas.
```

```python
import pandas as pd
import numpy as np

dados = {
    'Projeto': ['QuickVote', 'EmotionsPatterns', 'FastDelivery'],
    'Linguagem': ['Java', 'Python', 'Java'],
    'Versão': [1.0, 2.1, 1.5]
}

df = pd.DataFrame(dados)
print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
            Projeto Linguagem  Versão
0        QuickVote      Java     1.0
1  EmotionsPatterns    Python     2.1
2     FastDelivery      Java     1.5
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) Lista de Dicionários
```

```ad-quote
title:
Muito útil quando você recebe dados de uma API onde cada objeto representa um registro completo.
```

```python
dados_api = [
    {'id': 1, 'sensor': 'A1', 'valor': 23.5},
    {'id': 2, 'sensor': 'B2', 'valor': 19.8},
    {'id': 3, 'sensor': 'A1', 'valor': 25.0, 'alerta': True}
]

df = pd.DataFrame(dados_api)
print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
   id sensor  valor alerta
0   1     A1   23.5    NaN
1   2     B2   19.8    NaN
2   3     A1   25.0   True
```

```ad-quote
title:
Nota: Repare que o pandas preenche automaticamente com NaN as chaves ausentes em alguns registros.
```
````

````ad-quote
title:

```ad-quote
title:
##### **C ) -** Lista de Listas / Matrizes
```

```ad-quote
title:
Quando você tem apenas os valores brutos, precisa nomear as colunas manualmente.
```

```python
matriz = [
    ['UFRN', 'Natal', 'RN'],
    ['UFRJ', 'Rio de Janeiro', 'RJ'],
    ['USP', 'São Paulo', 'SP']
]

df = pd.DataFrame(matriz, columns=['Instituição', 'Cidade', 'UF'])
print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
  Instituição          Cidade  UF
0        UFRN           Natal  RN
1        UFRJ  Rio de Janeiro  RJ
2         USP       São Paulo  SP
```
````

````ad-quote
title:

```ad-quote
title:
##### **D ) -** Array Bidimensional do NumPy
```

```ad-quote
title:
Como você estuda Machine Learning, frequentemente terá matrizes numéricas geradas por bibliotecas como Scikit-Learn ou NumPy.
```

```python
dados_random = np.random.rand(2, 3)
df = pd.DataFrame(dados_random, columns=['v1', 'v2', 'v3'], index=['A', 'B'])
print(df)
```

```ad-quote
title:
###### Output esperado (exemplo):
```

```Plaintext
         v1        v2        v3
A  0.452312  0.892312  0.123145
B  0.671234  0.221456  0.998231
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **2 ) -** Métodos de Classe Especializados

```ad-quote
title:
<p align="justify"> Nem sempre os dados estão em um formato que o construtor padrão consegue interpretar diretamente. Para esses casos, o Pandas oferece métodos de classe especializados que lidam com estruturas mais complexas, como arquivos JSON aninhados ou dicionários que precisam de uma orientação específica entre linhas e colunas.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) pd.DataFrame.from_dict()
```

```ad-quote
title:
Permite criar o DataFrame orientando os dados pelas linhas caso as chaves do dicionário devam ser o índice e não as colunas.
```

```python
dados_orientados = {
    'Linha1': [10, 20],
    'Linha2': [30, 40]
}

df = pd.DataFrame.from_dict(dados_orientados, orient='index', columns=['Col_A', 'Col_B'])
print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
        Col_A  Col_B
Linha1     10     20
Linha2     30     40
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) - pd.json_normalize()
```

```ad-quote
title:
Indispensável para dados JSON aninhados (complexos).
```

```python
dados_nested = [
    {'user': 'André', 'info': {'idade': 20, 'cargo': 'Bolsista'}},
    {'user': 'Maria', 'info': {'idade': 22, 'cargo': 'Analista'}}
]

df = pd.json_normalize(dados_nested)
print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
    user  info.idade info.cargo
0  André          20   Bolsista
1  Maria          22   Analista
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **3 ) -** Criando a partir de Objetos do Próprio Pandas

```ad-quote
title:
<p align="justify">Muitas vezes, você já está trabalhando dentro do ecossistema do Pandas e precisa converter um objeto existente em uma tabela completa. O exemplo mais comum é transformar uma Series, que representa uma única coluna, em um DataFrame para ter acesso a funcionalidades exclusivas de estruturas tabulares.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) - Criando a partir de Objetos do Próprio Pandas
```

```ad-quote
title:
Uma _Series_ é uma coluna isolada. Para transformá-la em tabela:
```

```python
s = pd.Series([100, 200, 300], name='Preço')
df = s.to_frame()
print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
   Preço
0    100
1    200
2    300
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **4 ) -** Carregamento de Fontes Externas

```ad-quote
title:
<p align="justify">No cenário profissional, a maioria dos dados vem de fontes externas. O Pandas disponibiliza uma vasta gama de funções de leitura que permitem conectar o seu código diretamente a arquivos locais, bancos de dados relacionais e até mesmo capturar informações copiadas na área de transferência do seu computador.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### pd.read_csv()
```

```ad-quote
title:
Este é o método mais utilizado para carregar arquivos delimitados por vírgulas ou outros separadores.
```

```python
import pandas as pd

# Carrega o arquivo csv padrão
df = pd.read_csv('arquivo.csv')
print(df.head())
```
````

````ad-quote
title:
```ad-quote
title:
###### pd.read_clipboard()
```

```ad-quote
title:
Uma ferramenta incrível para testes rápidos; você copia uma tabela de um site ou Excel e o pandas a transforma em DataFrame instantaneamente.
```

```python
# Após copiar dados com Ctrl+C de uma planilha ou site
df = pd.read_clipboard()
print(df)
```
````

````ad-quote
title:
```ad-quote
title:
###### pd.read_sql()
```

```ad-quote
title:
Cria o DataFrame diretamente de um banco de dados relacional através de uma consulta.
```

```python
query = "SELECT * FROM tabela_vendas"
# conexao deve ser um objeto sqlalchemy ou sqlite3
df = pd.read_sql(query, conexao)
print(df)
```
````

---
