
---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify">Listas são uma das estruturas de dados mais fundamentais e versáteis em Python. Elas funcionam como contêineres que armazenam uma coleção de itens em uma sequência ordenada e mutável, permitindo a manipulação eficiente de conjuntos de dados.</p>
```

```ad-quote
title:
<p align="justify"><b>Link:</b> <a href="[https://www.w3schools.com/python/python_lists.asp](https://www.w3schools.com/python/python_lists.asp)">Python Lists</a></p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Fundamentos das Listas

```ad-quote
title:
**Características Básicas:**
```

```ad-quote
title:

| Característica | Explicação |
| --- | --- |
| Mutáveis | Podem ser alteradas após a sua criação |
| Ordenadas | Mantêm a ordem em que os elementos foram inseridos |
| Indexáveis | Cada elemento é acessível através de um índice numérico |
| Dinâmicas | Podem crescer ou diminuir de tamanho conforme a necessidade |
| Heterogêneas | Podem conter diferentes tipos de dados (números, strings, etc.) |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Criação de Listas

```ad-quote
title:
<p align="justify"><b>Lista Vazia:</b></p>
```

```python
# Lista vazia
lista_vazia = []
lista_vazia2 = list()
```

```ad-quote
title:
<p align="justify"><b>Lista com Elementos:</b></p>
```

```python
# Lista com elementos
numeros = [1, 2, 3, 4, 5]
misturada = [1, "texto", 3.14, True]
```

```ad-quote
title:
<p align="justify"><b>Listas Aninhadas - Duplas:</b></p>
```

```python
# Listas duplas
Numeros_1_5 = [1, 2, 3, 4, 5]
Numeros_5_10 = [6, 7, 8, 9, 10]

merge_Numbers = [Numeros_1_5, Numeros_5_10]
#OutPut: [[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]]
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Acesso a Elementos

```ad-quote
title:
Listas em Python permitem acessar elementos de forma flexível através de índices positivos, negativos e fatiamento (slicing), facilitando a extração de um ou mais itens da sequência.
```
````

````ad-quote
title:

```ad-quote
title:
###### **Acesso por Índice Positivo**
```

```ad-quote
title:
O acesso é feito por um índice que começa em 0 para o primeiro elemento.
```

```python
frutas = ['maçã', 'banana', 'laranja', 'uva']
print(frutas[0]) # 'maçã'
print(frutas[2]) # 'laranja'
```
````

````ad-quote
title:
```ad-quote
title:
###### **Acesso por Índice Negativo**
```

```ad-quote
title:
Índices negativos contam a partir do final da lista, onde -1 se refere ao último elemento.
```

```python
frutas = ['maçã', 'banana', 'laranja', 'uva']
print(frutas[-1]) # 'uva'
print(frutas[-2]) # 'laranja'
```
````

````ad-quote
title:
```ad-quote
title:
###### **Slicing - Fatiamento Básico**
```

```ad-quote
title:
Permite Extrair Subconjuntos De Uma Lista Utilizando Apenas Os Índices De Início E Fim. O Índice De Início É Inclusivo, Enquanto O Índice De Fim É Exclusivo.
```

```python
# Lista base: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# 1. Cria uma Cópia Completa da lista
splitList = list[:]
# Resultado: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# 2. Do início até o índice 1 (Exclusivo)
splitList = list[:1]
# Resultado: [1]

# 3. Do índice 1 até o final da lista
splitList = list[1:]
# Resultado: [2, 3, 4, 5, 6, 7, 8, 9, 10]

# 4. Todos os elementos exceto o último (Índice Negativo)
splitList = list[:-1]
# Resultado: [1, 2, 3, 4, 5, 6, 7, 8, 9]

# 5. Apenas o último elemento da lista
splitList = list[-1:]
# Resultado: [10]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Slicing - Fatiamento Com Passo**
```

```ad-quote
title:
O Terceiro Parâmetro Define O Intervalo Entre Os Elementos Selecionados. Ele Também Determina A Direção Da Leitura, Permitindo Percorrer A Lista No Sentido Inverso.
```

```python
# Lista base: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# 1. Seleciona elementos pulando de 2 em 2 (Índices Pares)
splitList = list[::2] 
# Resultado: [1, 3, 5, 7, 9]

# 2. Começa no índice 1 e pula de 2 em 2
splitList = list[1::2] 
# Resultado: [2, 4, 6, 8, 10]

# 3. Inverte a ordem da lista (Passo Negativo)
splitList = list[::-1] 
# Resultado: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

# 4. Inverte a lista pulando um elemento
splitList = list[::-2] 
# Resultado: [10, 8, 6, 4, 2]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Acesso em Listas Aninhadas**
```

```ad-quote
title:
Para acessar elementos dentro de listas aninhadas, utiliza-se múltiplos índices.
```

```python
matriz = [
 [1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]
]
print(matriz[1][2]) # 6
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Operações de Modificação

```ad-quote
title:
A natureza mutável das listas permite a adição e remoção de elementos de várias maneiras, seja no final, em uma posição específica ou pela remoção de itens baseados em seu valor ou índice.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Adicionando com append()**
```

```ad-quote
title:
Adiciona um único elemento ao final da lista.
```

```python
lista = [1, 2, 3]
lista.append(4) # [1, 2, 3, 4]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Adicionando com insert()**
```

```ad-quote
title:
Insere um elemento em uma posição específica, deslocando os demais.
```

```python
lista = [1, 2, 3, 4]
lista.insert(1, 1.5) # [1, 1.5, 2, 3, 4]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Adicionando com extend() ou +**
```

```ad-quote
title:
`extend()` adiciona todos os itens de um iterável ao final da lista. O operador `+` cria uma nova lista concatenada.
```

```python
lista = [1, 1.5, 2, 3, 4]
lista.extend([5, 6]) # [1, 1.5, 2, 3, 4, 5, 6]

nova_lista = lista + [7, 8]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Removendo com remove()**
```

```ad-quote
title:
Remove a primeira ocorrência de um valor específico.
```

```python
lista = [1, 2, 3, 2, 4]
lista.remove(2) # [1, 3, 2, 4]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Removendo com pop()**
```

```ad-quote
title:
Remove e retorna o elemento de um índice específico (o último, por padrão).
```

```python
lista = [1, 3, 2, 4]
elemento = lista.pop(1) # elemento = 3, lista = [1, 2, 4]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Removendo com del e clear()**
```

```ad-quote
title:
`del` remove um item ou uma fatia pelo índice. `clear()` esvazia a lista completamente.
```

```python
lista = [1, 2, 4]
del lista[0] # [2, 4]

lista.clear() # []
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Métodos Úteis e Funções

```ad-quote
title:
<p align="justify"><b>Métodos de Lista:</b></p>
```

```python
lista = [3, 1, 4, 1, 5, 9, 2]

# Contar ocorrências
print(lista.count(1)) # 2

# Encontrar índice da primeira ocorrência
print(lista.index(4)) # 2

# Ordenação (in-place)
lista.sort() # lista se torna [1, 1, 2, 3, 4, 5, 9]

# Inversão (in-place)
lista.reverse() # lista se torna [9, 5, 4, 3, 2, 1, 1]
```

```ad-quote
title:
<p align="justify"><b>Funções Nativas:</b></p>
```

```python
lista = [1, 2, 3, 4, 5]

# Tamanho da lista
print(len(lista)) # 5

# Retorna uma nova lista ordenada
nova_ordenada = sorted(lista)

# Soma, máximo, mínimo
print(sum(lista)) # 15
print(max(lista)) # 5
print(min(lista)) # 1
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Técnicas Avançadas

```ad-quote
title:
**List Comprehension**
```

```ad-quote
title:
Oferece uma sintaxe concisa para criar listas a partir de iteráveis, aplicando expressões e condições.
```

```python
# Quadrados dos números de 0 a 9
quadrados = [x**2 for x in range(10)]

# Números pares de 0 a 20
pares = [x for x in range(21) if x % 2 == 0]

# Lista de tuplas com condição
combinacoes = [(x, y) for x in [1,2,3] for y in [3,1,4] if x != y]
```

```ad-quote
title:
**Copiando Listas**
```

```ad-quote
title:
É crucial distinguir entre cópias superficiais (shallow), que não duplicam objetos internos, e profundas (deep), que criam cópias independentes de todos os elementos.
```

```python
original = [1, 2, [3, 4]]

# Cópia superficial (shallow copy)
copia = original.copy()
copia2 = original[:]

# Cópia profunda (para listas com objetos mutáveis)
import copy
profunda = copy.deepcopy(original)
```

```ad-quote
title:
**Desempacotamento de Listas**
```

```ad-quote
title:
Permite atribuir os elementos de uma lista a múltiplas variáveis de uma só vez.
```

```python
lista = [1, 2, 3, 4, 5]

# Desempacotamento simples
a, b, c, d, e = lista

# Desempacotamento com *
primeiro, *meio, ultimo = lista
# primeiro = 1, meio = [2, 3, 4], ultimo = 5
```

```ad-quote
title:
**Funções `map` e `filter`**
```

```ad-quote
title:
`map` aplica uma função a todos os itens de uma lista, enquanto `filter` cria uma nova lista com os itens que satisfazem uma condição.
```

```python
lista = [1, 2, 3, 4]

# Mapeamento
dobro = list(map(lambda x: x*2, lista)) # [2, 4, 6, 8]

# Filtro
maiores_que_2 = list(filter(lambda x: x > 2, lista)) # [3, 4]
```

```ad-quote
title:
**Função `enumerate`**
```

```ad-quote
title:
Útil em loops `for` para obter tanto o índice quanto o valor de cada elemento da lista.
```

```python
itens = ['a', 'b', 'c']
for indice, valor in enumerate(itens):
    print(f"Índice: {indice}, Valor: {valor}")
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Performance

```ad-quote
title:

| Operação | Complexidade (Big O) |
| --- | --- |
| Acesso por índice: `lista[i]` | O(1) |
| Adicionar/Remover no final: `append()`/`pop()` | O(1) |
| Busca por valor: `x in lista` | O(n) |
| Inserir/Remover no início/meio: `insert(i)`/`pop(i)` | O(n) |

```

```ad-quote
title:
<p align="justify">Para operações frequentes de adição e remoção em ambas as extremidades da sequência (início e fim), a estrutura `collections.deque` é mais eficiente, oferecendo complexidade O(1) para essas operações.</p>
```
````

---

```ad-done
title:
#### **Py Lits** - Funções de Manipulação

```

---

````ad-quote
title:

##### **01 )** - Métodos de Lista: Adição e Remoção

```ad-quote
title:
<p align="justify">Estes métodos modificam a lista diretamente (operações "in-place") para adicionar ou remover elementos.</p>
```

```ad-quote
title:

| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `append()` | Adiciona um único item ao final da lista. | `numeros = [1, 2]; numeros.append(3)` |
| `extend()` | Adiciona todos os itens de um iterável ao final da lista. | `numeros.extend([4, 5])` |
| `insert()` | Insere um item em uma posição específica. | `numeros.insert(0, 0)` |
| `remove()` | Remove a primeira ocorrência de um valor. | `numeros.remove(3)` |
| `pop()` | Remove e retorna o item de um índice (o último por padrão).| `item_removido = numeros.pop(1)` |
| `clear()` | Remove todos os itens da lista, deixando-a vazia. | `numeros.clear()` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Métodos de Lista: Organização, Busca e Cópia

```ad-quote
title:
<p align="justify">Métodos para reordenar, analisar o conteúdo e duplicar uma lista.</p>
```

```ad-quote
title:

| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `sort()` | Ordena os itens da própria lista (in-place). | `lista = [3, 1, 2]; lista.sort()` |
| `reverse()`| Inverte a ordem dos elementos da própria lista (in-place).| `lista.reverse()` |
| `index()` | Retorna o índice da primeira ocorrência de um valor. | `indice = lista.index(2)` |
| `count()` | Retorna o número de vezes que um valor aparece. | `contagem = lista.count(1)` |
| `copy()` | Retorna uma cópia "rasa" (shallow copy) da lista. | `lista_copia = lista.copy()` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Funções Nativas: Análise e Matemática

```ad-quote
title:
<p align="justify">Funções gerais do Python que recebem uma lista e retornam uma informação sobre ela, sem modificá-la.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `len()` | Retorna o número de itens na lista. | `tamanho = len([1, 2, 3])` |
| `sum()` | Soma os itens de um iterável (deve conter apenas números). | `total = sum([10, 20, 30])` |
| `max()` | Retorna o maior item de um iterável. | `maior = max([5, 42, 13])` |
| `min()` | Retorna o menor item de um iterável. | `menor = min([5, 42, 13])` |
| `list()` | Cria uma lista a partir de um iterável. | `nova_lista = list("abc")` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Funções Nativas: Iteração e Transformação

```ad-quote
title:
<p align="justify">Funções que criam novos iteráveis ou aplicam transformações aos elementos de uma lista.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `sorted()` | Retorna uma **nova lista** ordenada a partir de um iterável. | `ordenada = sorted([3, 1, 2])` |
| `reversed()`| Retorna um iterador que percorre a lista na ordem inversa. | `for i in reversed([1,2,3]): print(i)` |
| `enumerate()`| Retorna pares (índice, valor) de um iterável. | `for i, v in enumerate(['a','b']): print(i, v)` |
| `zip()` | Agrega elementos de múltiplos iteráveis em tuplas. | `pares = list(zip([1,2], ['a','b']))` |
| `map()` | Aplica uma função a cada item de um iterável. | `dobros = list(map(lambda x: x*2, [1,2]))` |
| `filter()` | Filtra elementos de um iterável com base em uma função. | `pares = list(filter(lambda x: x%2==0, [1,2,3]))` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Funções Nativas: Verificação Lógica

```ad-quote
title:
<p align="justify">Funções que avaliam o valor lógico dos elementos de uma lista para retornar um único resultado Booleano.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `all()` | Retorna `True` se **todos** os elementos do iterável forem verdadeiros. | `print(all([True, 1, "texto"]))` |
| `any()` | Retorna `True` se **pelo menos um** elemento do iterável for verdadeiro. | `print(any([False, 0, ""]))` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">As listas são uma ferramenta indispensável no arsenal de um desenvolvedor Python, oferecendo uma combinação poderosa de simplicidade e flexibilidade para gerenciar coleções de dados. Dominar suas operações, métodos e nuances de performance é um passo essencial para escrever código eficiente e pythônico.</p>
```
````

---
