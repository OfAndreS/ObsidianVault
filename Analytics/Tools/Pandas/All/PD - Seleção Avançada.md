---
banner: "![[Pasted image 20260118174047.png]]"
---

---

````ad-quote
title:
##### **Intro ) -** Seleção Avançada e Arquitetura

```ad-quote
title:
Neste nível, deixamos de ver o DataFrame apenas como uma tabela e passamos a encará-lo como uma coleção de Arrays NumPy alinhados. A eficiência da análise depende do domínio sobre como extrair e modificar esses vetores utilizando Rótulos, Posições e Lógica Booleana.
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **01 ) -** A Dualidade do Acesso

```ad-quote
title:
<p align="justify">Mesmo com um índice numérico padrão, existe uma distinção fundamental entre o nome da linha (rótulo) e o lugar físico que ela ocupa na memória (posição).</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) .loc - Baseado em Rótulos
```

```ad-quote
title:
O .loc é a ferramenta primária porque é semântico. Ele opera no espaço dos nomes definidos pelo índice. Se o índice for [10, 20, 30], o comando .loc[10] busca a linha cujo rótulo é 10, e não a décima linha.
```

```ad-quote
title:
##### B ) .iloc - Baseado em Posição
```

```ad-quote
title:
O .iloc opera estritamente no espaço dos inteiros de 0 a N-1, ignorando o significado dos rótulos. É a única forma segura de selecionar dados quando a ordem física importa, independentemente dos IDs.
```

```python
import pandas as pd

# DataFrame com índice numérico não sequencial
df = pd.DataFrame({'Nota': [9.5, 7.0, 8.0]}, index=[10, 20, 30])

# .loc busca pelo RÓTULO 10
print("Saída do .loc[10]:")
print(df.loc[10])

# .iloc busca pela POSIÇÃO 0 (primeira linha)
print("\nSaída do .iloc[0]:")
print(df.iloc[0])
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
Saída do .loc[10]:
Nota    9.5
Name: 10, dtype: float64

Saída do .iloc[0]:
Nota    9.5
Name: 10, dtype: float64
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **02 ) -** Álgebra da Filtragem Booleana

```ad-quote
title:
<p align="justify">A filtragem no Pandas é uma operação de vetorização. Quando aplicamos uma condição, a biblioteca cria uma máscara (vetor de True/False) e a sobrepõe aos dados originais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Lógica Bitwise
```

```ad-quote
title:
Diferente do Python puro (and, or), o Pandas exige operadores que funcionam elemento-a-elemento. É obrigatório o uso de parênteses para separar as condições devido à precedência de operadores.
```

```python
data = {
    'Nome': ['André', 'Bia', 'Carlos'],
    'Idade': [20, 25, 30],
    'Peso': [86, 60, 90]
}
df = pd.DataFrame(data)

# Interseção (&) equivale ao AND
# Parênteses são obrigatórios: (condição A) & (condição B)
mask = (df['Idade'] > 20) & (df['Peso'] < 90)

print(df[mask])
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
   Nome  Idade  Peso
1   Bia     25    60
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **03 ) -** Métodos Otimizados de Filtro

```ad-quote
title:
<p align="justify">Escrever múltiplas condições com símbolos bitwise pode se tornar ilegível. O Pandas oferece abstrações que, além de mais limpas, podem ser mais eficientes no uso de memória.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) O Motor .query()
```

```ad-quote
title:
Permite escrever expressões como strings. É possível referenciar variáveis do ambiente Python usando o símbolo @.
```

```python
limite_peso = 80

# Sintaxe limpa (similar a SQL)
resultado = df.query('Idade > 20 and Peso < @limite_peso')

print(resultado)
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) Pertinência com .isin()
```

```ad-quote
title:
Para filtrar baseando-se em uma lista de valores permitidos, o método .isin() é superior em performance e legibilidade comparado a múltiplos operadores OR.
```

```python
# Filtragem categórica
filtro_nomes = df[df['Nome'].isin(['André', 'Carlos'])]

print(filtro_nomes)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
     Nome  Idade  Peso
0   André     20    86
2  Carlos     30    90
```
````

````ad-quote
title:

```ad-quote
title:
##### C ) Interseção de .isin()
```

```ad-quote
title:
<p align="justify">A lógica de pertinência pode ser aplicada a múltiplas colunas simultaneamente. No exemplo abaixo, filtramos o DataFrame para encontrar apenas registros que satisfaçam as duas listas de permissão ao mesmo tempo: nomes específicos e idades específicas. O uso de parênteses é crucial para garantir a precedência correta do operador E bitwise.</p>
```

```python
import pandas as pd

mask = (df['Nome'].isin(['André', 'Carlos'])) & (df['Idade'].isin([20, 30]))

df_final = df[mask]

print(df_final)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
     Nome  Idade  Peso  Altura
0   André     20    86    1.85
2  Carlos     30    90    1.80
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **04 ) -** Acessores de Tipos Específicos

```ad-quote
title:
<p align="justify">Para colunas que não são numéricas, usamos acessores específicos para criar máscaras booleanas complexas sem loops manuais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Acessores .str e .dt
```

```ad-quote
title:
O .str permite operações vetorizadas de texto (como contains), enquanto o .dt permite extrair propriedades de datas (como ano ou dia da semana).
```

```python
# Exemplo de filtro de texto
# Cria máscara para nomes que contêm "An"
mask_texto = df['Nome'].str.contains('An')

print(df[mask_texto])
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
    Nome  Idade  Peso
0  André     20    86
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **05 ) -** Modificação e View vs Copy

```ad-quote
title:
<p align="justify">A distinção mais técnica e perigosa na seleção avançada é entender quando você está operando no dado original ou em uma cópia. Modificações em cópias são descartadas pelo Python silenciosamente.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Modificação Atômica
```

```ad-quote
title:
Para garantir a escrita no dado original, a operação deve ser atômica (feita de uma só vez) usando .loc, evitando o encadeamento de colchetes (chained indexing).
```

```python
# Correto: df.loc[linhas, colunas] = valor
df.loc[df['Nome'] == 'André', 'Peso'] = 87

print(df.loc[0])
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) Lógica Condicional (np.where)
```

```ad-quote
title:
Para criar novas colunas baseadas em lógica Se-Então-Senão vetorizada, o .loc é insuficiente. Utilizamos a função where do NumPy.
```

```python
import numpy as np

# Se idade < 30 é 'Jovem', senão 'Maduro'
df['Status'] = np.where(df['Idade'] < 30, 'Jovem', 'Maduro')

print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
     Nome  Idade  Peso  Status
0   André     20    87   Jovem
1     Bia     25    60   Jovem
2  Carlos     30    90  Maduro
```
````

---