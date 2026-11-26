---
banner: "![[Pasted image 20260118174047.png]]"
---

---

````ad-quote
title:
##### **Intro ) -** Fundamentos do Pandas

```ad-quote
title:
Este tópico servirá como a fundação estrutural do conhecimento em Pandas. Não vamos apenas pegar dados, mas entender a anatomia de um DataFrame e como a biblioteca organiza as informações na memória para permitir um acesso eficiente.
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **01 ) -** A Anatomia do DataFrame

```ad-quote
title:
<p align="justify">Para navegar com eficiência, é necessário visualizar o DataFrame não como uma planilha solta, mas como um sistema de coordenadas cartesianas, regido por dois eixos principais. A mágica do Pandas é que cada eixo possui rótulos, permitindo seleção semântica.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Eixos e Rótulos
```

```ad-quote
title:
O Eixo 0 (Index) é o eixo vertical que representa as linhas. O Eixo 1 (Columns) é o eixo horizontal que representa as colunas ou variáveis. Diferente de matrizes NumPy puras, essa rotulagem é o que define a estrutura.
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **02 ) -** O Conceito de Index

```ad-quote
title:
<p align="justify">O Index é o componente mais poderoso para navegação, funcionando como o identificador único de cada linha. Por padrão, cria-se um RangeIndex numérico, mas o verdadeiro poder surge com índices semânticos (como ID ou Nome) ou temporais (DatetimeIndex).</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Manipulando o Index
```

```ad-quote
title:
Abaixo transformamos uma coluna comum em índice usando set_index. Note que o parâmetro inplace=True aplica a alteração no próprio objeto, sem criar cópias.
```

```python
import pandas as pd

data = {
    'Nome': ['André', 'Bia', 'Carlos'],
    'Idade': [20, 25, 30],
    'Peso': [86, 60, 90],
    'Altura': [1.85, 1.65, 1.80]
}
df = pd.DataFrame(data)

# Transformação: Definindo 'Nome' como índice (Eixo 0)
df.set_index('Nome', inplace=True)

print(df)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
        Idade  Peso  Altura
Nome
André      20    86    1.85
Bia        25    60    1.65
Carlos     30    90    1.80
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **03 ) -** Seleção de Colunas

```ad-quote
title:
<p align="justify">A operação mais frequente é selecionar subconjuntos de variáveis usando colchetes. Existem distinções técnicas importantes no retorno dependendo da sintaxe utilizada.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Selecionando uma Única Coluna (Series)
```

```ad-quote
title:
Ao passar o nome da coluna como string, o retorno é uma Series (estrutura unidimensional). Ela preserva o índice e os valores, mas não possui colunas.
```

```python
# Sintaxe: df['Nome_da_Coluna']
pesos = df['Peso']

print(pesos)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
Nome
André     86
Bia       60
Carlos    90
Name: Peso, dtype: int64
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) Selecionando Múltiplas Colunas (DataFrame)
```

```ad-quote
title:
Ao passar uma lista de strings (colchetes duplos), o retorno é um DataFrame. O resultado mantém a estrutura tabular bidimensional.
```

```python
# Sintaxe: df[['Col1', 'Col2']]
subconjunto = df[['Peso', 'Altura']]

print(subconjunto)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
        Peso  Altura
Nome
André     86    1.85
Bia       60    1.65
Carlos    90    1.80
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **04 ) -** Sintaxe Alternativa

```ad-quote
title:
<p align="justify">A notação de ponto permite acessar colunas como atributos. Embora prática para análises rápidas, deve ser evitada em produção.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Notação de Ponto e Riscos
```

```ad-quote
title:
Este método falha se houver espaços no nome da coluna e gera erros silenciosos em caso de conflito com métodos nativos (como count ou sum).
```

```python
# Equivalente a df['Idade']
idade = df.Idade

print(idade)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
Nome
André     20
Bia       25
Carlos    30
Name: Idade, dtype: int64
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **05 ) -** O Alinhamento Intrínseco

```ad-quote
title:
<p align="justify">Este é o conceito vital onde as operações respeitam o rótulo do índice, e não a posição numérica. O Pandas alinha os dados semanticamente antes de calcular.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Operação com Índices Alinhados
```

```ad-quote
title:
Ao realizar uma divisão entre duas séries (exemplo abaixo), o Pandas procura o rótulo André no peso e divide pelo rótulo André na altura, garantindo a integridade do dado mesmo se estiver desordenado.
```

```python
# Fórmula: IMC = Peso / Altura
# O cálculo respeita a identidade de cada registro (Index)
imc = df['Peso'] / df['Altura']

print(imc)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
Nome
André     46.486486
Bia       36.363636
Carlos    50.000000
dtype: float64
```
````

---