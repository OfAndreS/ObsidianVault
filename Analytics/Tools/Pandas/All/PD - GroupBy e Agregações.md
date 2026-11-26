---
banner: "![[Pasted image 20260118174047.png]]"
---
---

````ad-quote
title:
##### **Intro ) -** Agrupamento e o Paradigma Split-Apply-Combine

```ad-quote
title:
O groupby é uma das ferramentas mais poderosas da biblioteca pandas, funcionando com base no conceito Split-Apply-Combine. Ele permite segmentar seus dados em grupos para realizar cálculos específicos em cada parte de forma independente.
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **01 ) -** O Fluxo do Processamento

```ad-quote
title:
<p align="justify">A operação de agrupamento não é um passo único, mas uma sequência de três estágios que transformam o dado bruto em informação sumarizada.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Split - Dividir
```

```ad-quote
title:
Nesta fase, o pandas separa o DataFrame original em grupos menores com base em uma ou mais chaves (colunas). Se você agrupar por Cidade, o pandas criará internamente um grupo para cada cidade distinta na sua tabela.
```
````

````ad-quote
title:
```ad-quote
title:
##### B ) Apply - Aplicar
```

```ad-quote
title:
Após a divisão, você aplica uma função a cada grupo. As operações comuns incluem Agregação (estatística única), Transformação (mesmo tamanho original) e Filtragem (descarte de grupos por critério).
```
````

````ad-quote
title:
```ad-quote
title:
##### C ) Combine - Combinar
```

```ad-quote
title:
Finalmente, o pandas junta os resultados de todas as operações de Apply em uma nova estrutura de dados, geralmente resultando em um novo DataFrame ou Series.
```
````

````ad-quote
title:

```ad-quote
title:
###### Código em Python:
```

```python
import pandas as pd

# Criando dados de exemplo
df = pd.DataFrame({
    'Categoria': ['Eletrônicos', 'Roupas', 'Eletrônicos', 'Roupas', 'Eletrônicos'],
    'Vendas': [1000, 200, 1500, 300, 1200]
})

# Agrupando e somando
resultado = df.groupby('Categoria')['Vendas'].sum()

print(resultado)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
Categoria
Eletrônicos    3700
Roupas          500
Name: Vendas, dtype: int64
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **02 ) -** Catálogo de Agregações

```ad-quote
title:
<p align="justify">Uma vez que o objeto GroupBy é criado, diversos métodos otimizados podem ser invocados para extrair métricas sobre os segmentos definidos.</p>
```

```ad-quote
title:

|**Função**|**Descrição**|
|---|---|
|**.mean()**|Calcula a média de cada grupo.|
|**.sum()**|Calcula a soma dos valores.|
|**.count()**|Conta o número de itens (incluindo valores nulos).|
|**.size()**|Conta o tamanho do grupo (linhas totais).|
|**.agg()**|Permite aplicar múltiplas funções ao mesmo tempo.|
```

````

---

> [!done] _New_

---

````ad-quote
title:

##### **03 ) -** Arquitetura e Performance

```ad-quote
title:
<p align="justify">Entender a natureza técnica do objeto gerado é fundamental para lidar com grandes volumes de dados sem comprometer a memória do sistema.</p>
```

```ad-quote
title:
Ao executar df.groupby('coluna'), o pandas não cria novos DataFrames imediatamente. Ele gera um objeto DataFrameGroupBy, que funciona como um mapeamento lógico. A computação pesada é adiada (lazy evaluation) até que uma função de agregação seja chamada.
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **04 ) -** Agrupamento por Múltiplas Colunas

```ad-quote
title:
<p align="justify">Para análises mais granulares, o Pandas permite passar uma lista de colunas ao groupby. Isso cria um índice hierárquico (MultiIndex), organizando os dados em níveis de subgrupos que facilitam a leitura de dados multidimensionais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) A Estrutura de Níveis
```

```ad-quote
title:
Ao agrupar por mais de uma chave, o resultado retém a hierarquia das colunas passadas. O primeiro elemento da lista torna-se o nível primário e o segundo o subnível.
```
````

````ad-quote
title:

```ad-quote
title:
###### Código em Python:
```

```python
import pandas as pd

df = pd.DataFrame({
    'Região': ['Norte', 'Norte', 'Sul', 'Sul', 'Norte'],
    'Vendedor': ['Ana', 'Bruno', 'Ana', 'Bruno', 'Ana'],
    'Vendas': [500, 300, 700, 400, 200]
})

# Agrupando por Região e depois por Vendedor
mult_grupo = df.groupby(['Região', 'Vendedor'])['Vendas'].sum()

print(mult_grupo)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
Região  Vendedor
Norte   Ana         700
        Bruno       300
Sul     Ana         700
        Bruno       400
Name: Vendas, dtype: int64
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **05 ) -** O Motor .agg() para Cálculos Customizados

```ad-quote
title:
<p align="justify">O método .agg() é a forma mais flexível de aplicar operações. Ele permite realizar múltiplos cálculos diferentes em colunas distintas simultaneamente ou injetar lógica personalizada via funções anônimas.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) Mapeamento por Dicionário
```

```ad-quote
title:
Esta é a forma mais eficiente de realizar agregações distintas para cada coluna em uma única chamada de código, evitando múltiplas passagens pelos dados.
```

```python
# Definindo métricas diferentes para cada coluna
operacoes = {
    'Vendas': ['sum', 'mean'],
    'Vendedor': 'count'
}

resultado_custom = df.groupby('Região').agg(operacoes)
print(resultado_custom)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
         Vendas             Vendedor
            sum        mean    count
Região                              
Norte      1000  333.333333        3
Sul        1100  550.000000        2
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) Flexibilidade com Lambda
```

```ad-quote
title:
Quando as funções integradas não atendem à necessidade, utilizamos expressões lambda para definir cálculos específicos, como a amplitude térmica ou o desvio percentual.
```

```python
# Calculando a amplitude (máximo - mínimo) de cada grupo
amplitude = df.groupby('Região')['Vendas'].agg(lambda x: x.max() - x.min())

print("Amplitude de vendas por região:")
print(amplitude)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
Amplitude de vendas por região:
Região
Norte    300
Sul      300
Name: Vendas, dtype: int64
```
````

---
