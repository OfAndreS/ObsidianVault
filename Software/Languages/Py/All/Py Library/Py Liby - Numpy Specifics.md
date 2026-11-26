
---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify"><b>NumPy</b> (Numerical Python) é a biblioteca fundamental para computação científica em Python. Seu principal objeto é o <b>`ndarray`</b> (n-dimensional array), uma estrutura de dados eficiente que permite armazenar e operar em grandes arrays e matrizes de dados homogêneos (todos do mesmo tipo). Seu poder reside na execução de operações matemáticas vetorizadas, que são significativamente mais rápidas do que os laços `for` nativos do Python.</p>
```

```ad-quote
title:
<p align="justify"><b>Link:</b> <a href="[https://numpy.org/doc/stable/](https://numpy.org/doc/stable/)">NumPy Documentation</a></p>
```

>[!quote] **Colab:** [Numpy Colab](https://drive.google.com/drive/folders/1HnenLFQTMSa1GtBMExkRrMtXXT7tIh-a)

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Fundamentos dos Arrays NumPy

```ad-quote
title:
**Características Básicas:**
```

```ad-quote
title:

| Característica | Explicação |
| --- | --- |
| Homogêneos | Todos os elementos de um array devem ser do mesmo tipo de dado. |
| Tamanho Fixo | O tamanho de um array NumPy é fixado no momento da sua criação. |
| Multidimensional | Podem ter múltiplas dimensões (eixos), permitindo criar vetores, matrizes e tensores. |
| Otimizado | As operações são implementadas em C, resultando em alto desempenho. |
| Vetorização | Permite aplicar operações a arrays inteiros de uma só vez, sem laços explícitos. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Criação de Arrays

```ad-quote
title:
<p align="justify"><b>A partir de Listas Python:</b></p>
```

```python
import numpy as np

# Array 1D a partir de uma lista
vetor = np.array([1, 2, 3])

# Array 2D (matriz) a partir de uma lista de listas
matriz = np.array([[1, 2, 3], [4, 5, 6]])
```

```ad-quote
title:
<p align="justify"><b>Arrays Especiais (Funções Nativas):</b></p>
```

```python
# Array de zeros
zeros = np.zeros((2, 3)) # Matriz 2x3 de zeros

# Array de uns
uns = np.ones((3, 2)) # Matriz 3x2 de uns

# Array em um intervalo
sequencia = np.arange(0, 10, 2) # [0, 2, 4, 6, 8]

# Array com espaçamento linear
espacado = np.linspace(0, 1, 5) # [0., 0.25, 0.5, 0.75, 1.]

# Array com números aleatórios
aleatorio = np.random.rand(2, 2) # Matriz 2x2 com valores entre 0 e 1
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Atributos e Acesso a Elementos

```ad-quote
title:
Arrays NumPy possuem atributos que descrevem suas características e um sistema de indexação poderoso, similar ao das listas, mas estendido para múltiplas dimensões.
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
Acessam metadados do array sem alterar seus dados.
```

```python
matriz = np.array([[1, 2, 3], [4, 5, 6]])

print(matriz.shape) # (2, 3) -> 2 linhas, 3 colunas
print(matriz.ndim)  # 2      -> número de dimensões
print(matriz.size)  # 6      -> número total de elementos
print(matriz.dtype) # int64  -> tipo de dado dos elementos
```
````

````ad-quote
title:
```ad-quote
title:
###### **Indexação e Slicing**
```

```ad-quote
title:
Usa-se `[linha, coluna]` para acessar elementos em 2D. O slicing funciona em cada dimensão.
```

```python
matriz = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

print(matriz[1, 2])     # 6 (elemento na linha 1, coluna 2)
print(matriz[0, :])     # [1 2 3] (toda a linha 0)
print(matriz[:, 1])     # [2 5 8] (toda a coluna 1)
print(matriz[:2, 1:])   # [[2 3]
                        #  [5 6]] (sub-matriz)
```
````

````ad-quote
title:
```ad-quote
title:
###### **Indexação Booleana**
```

```ad-quote
title:
Permite selecionar elementos de um array que satisfazem uma condição.
```

```python
arr = np.arange(10) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
maiores_que_5 = arr[arr > 5]
print(maiores_que_5) # [6 7 8 9]
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Operações e Manipulação

```ad-quote
title:
O poder do NumPy vem das operações vetorizadas e da flexibilidade para remodelar e manipular arrays.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Operações Matemáticas Elemento a Elemento**
```

```ad-quote
title:
As operações aritméticas são aplicadas a cada elemento individualmente.
```

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b) # [5 7 9]
print(a * 2) # [2 4 6]
print(np.sqrt(a)) # Raiz quadrada de cada elemento
```
````

````ad-quote
title:
```ad-quote
title:
###### **Broadcasting**
```

```ad-quote
title:
Permite operações entre arrays de formas diferentes, onde o array menor é "esticado" para se ajustar ao maior.
```

```python
matriz = np.array([[1, 2], [3, 4]])
vetor = np.array([10, 20])
# O vetor é somado a cada linha da matriz
resultado = matriz + vetor # [[11 22], [13 24]]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Remodelagem e Transposição**
```

```ad-quote
title:
Altera a forma de um array sem mudar seus dados.
```

```python
arr = np.arange(6) # [0, 1, 2, 3, 4, 5]
matriz = arr.reshape(2, 3) # [[0, 1, 2], [3, 4, 5]]

# Transposição (troca linhas por colunas)
transposta = matriz.T # [[0, 3], [1, 4], [2, 5]]
```
````

````ad-quote
title:
```ad-quote
title:
###### **Agregação (Soma, Média, etc.)**
```

```ad-quote
title:
Funções que resumem os dados em um array, podendo operar no array todo ou por eixo (`axis`).
```

```python
matriz = np.array([[1, 2], [3, 4]])
print(matriz.sum())       # 10 (soma de todos)
print(matriz.sum(axis=0)) # [4 6] (soma das colunas)
print(matriz.mean(axis=1))# [1.5 3.5] (média das linhas)
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
<p align="justify"><b>Funções Matemáticas Universais (ufuncs):</b></p>
```

```python
arr = np.array([0, np.pi/2, np.pi])

# Funções trigonométricas
print(np.sin(arr))

# Exponenciais e logarítmicas
print(np.exp([1, 2])) # e^1, e^2
print(np.log([1, np.e])) # ln(1), ln(e)
```

```ad-quote
title:
<p align="justify"><b>Ordenação e Manipulação:</b></p>
```

```python
arr = np.array([3, 1, 2, 5, 4])

# Ordena o array (in-place)
arr.sort() # arr se torna [1, 2, 3, 4, 5]

# Concatena arrays
a = np.array([1, 2])
b = np.array([3, 4])
print(np.concatenate((a, b))) # [1 2 3 4]
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Álgebra Linear

```ad-quote
title:
**Submódulo `linalg`**
```

```ad-quote
title:
O NumPy inclui um submódulo (`np.linalg`) com funções essenciais de álgebra linear.
```

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([5, 6])

# Produto de matrizes (dot product)
print(A @ A) # Multiplicação de A por A

# Determinante
print(np.linalg.det(A))

# Inversa da matriz
print(np.linalg.inv(A))

# Solução de sistema linear Ax = B
x = np.linalg.solve(A, B)
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Performance

```ad-quote
title:

| Operação | Complexidade (Big O) | Explicação |
| --- | --- | --- |
| Acesso por índice: `arr[i]` | O(1) | Acesso direto à memória, independente do tamanho. |
| Operação Vetorizada: `arr + 2` | O(n) | A operação é aplicada a cada um dos 'n' elementos. |
| Produto de Matrizes: `A @ B` | O(n³) | Para matrizes NxN, é uma operação computacionalmente intensiva. |
| Ordenação: `arr.sort()` | O(n log n)| Usa um algoritmo de ordenação eficiente (introsort). |

```

```ad-quote
title:
<p align="justify">A principal vantagem de performance do NumPy vem da vetorização, que evita o overhead do interpretador Python ao executar laços em código C compilado e otimizado. Para operações com grandes volumes de dados numéricos, NumPy é quase sempre a escolha mais eficiente.</p>
```
````

---