
---

````ad-quote
title:

##### **NumPy: Os Métodos Essenciais para Computação Científica em Python**

```ad-quote
title:
<p align="justify"><b>NumPy</b>, uma abreviação para "Numerical Python", é uma biblioteca fundamental para a computação científica em Python. Ela fornece suporte para arrays e matrizes multidimensionais, juntamente com uma vasta coleção de funções matemáticas de alto nível para operar nesses arrays. Seus métodos eficientes e fáceis de usar a tornam a espinha dorsal de muitas outras bibliotecas de ciência de dados, como <b>Pandas</b>, <b>Matplotlib</b> e <b>Scikit-learn</b>.</p>

<p align="justify">Abaixo estão os principais métodos e funcionalidades do NumPy, categorizados para facilitar o entendimento.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Criação de Arrays

```ad-quote
title:
<p align="justify">A base do NumPy é o seu objeto <b>ndarray</b> (array n-dimensional). Existem diversas maneiras de criar arrays a partir do zero.</p>
```

```ad-quote
title:

| Método | Descrição | Exemplo de Código |
|---|---|---|
| `np.array()` | Cria um array a partir de uma lista ou tupla. | `import numpy as np; arr = np.array([1, 2, 3])` |
| `np.arange()` | Cria um array com valores em um intervalo especificado. | `arr = np.arange(0, 10, 2)` |
| `np.zeros()` | Cria um array preenchido com zeros. | `arr = np.zeros((2, 3))` |
| `np.ones()` | Cria um array preenchido com uns. | `arr = np.ones((3, 2))` |
| `np.linspace()` | Cria um array com valores igualmente espaçados. | `arr = np.linspace(0, 1, 5)` |
| `np.eye()` | Cria uma matriz identidade. | `arr = np.eye(3)` |
| `np.random.rand()`| Cria um array com números aleatórios uniformes [0, 1).| `arr = np.random.rand(2, 2)` |
| `np.random.randn()`| Cria um array com números aleatórios de uma distribuição normal.| `arr = np.random.randn(2, 2)` |
| `np.empty()` | Cria um array sem inicializar suas entradas. | `arr = np.empty((2, 3))` |
| `np.full()` | Cria um array preenchido com um valor escalar. | `arr = np.full((2, 2), 7)` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Atributos de Arrays

```ad-quote
title:
<p align="justify">Uma vez que um array é criado, você pode acessar suas informações através de seus atributos.</p>
```

```ad-quote
title:

| Atributo | Descrição |
|---|---|
| `arr.shape` | Retorna uma tupla com as dimensões do array. |
| `arr.ndim` | Retorna o número de dimensões (eixos) do array. |
| `arr.size` | Retorna o número total de elementos no array. |
| `arr.dtype` | Retorna o tipo de dado dos elementos do array. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Manipulação de Arrays

```ad-quote
title:
<p align="justify">O NumPy oferece uma gama de funções para modificar a estrutura, o conteúdo e a organização dos arrays. É importante notar que a maioria dessas funções Não altera o array original, mas sim retorna um novo array modificado. Essa característica, conhecida como imutabilidade, é fundamental para a previsibilidade e segurança no código.</p>
```
```ad-quote
title:
| Método | Descrição | Exemplo de Código |
|---|---|---|
| `arr.reshape()` | Modifica a forma (dimensões) do array sem alterar seus dados. | `a = np.arange(6); b = a.reshape(Arrray,(2, 3))` |
| `arr.flatten()` | Retorna uma cópia do array colapsada em uma única dimensão (1D). | `a = np.array([[1,2],[3,4]]); b = a.flatten()`|
|`arr.T`| Permuta as dimensões do array (transpõe). Troca linhas por colunas e vice-versa. | `a = np.array([[1,2],[3,4]]); b = a.T` |
| `np.concatenate()`| Junta uma sequência de arrays ao longo de um eixo existente. | `a=np.array([1,2]); b=np.array([3,4]); np.concatenate((a,b))` |
| `np.vstack()` | Empilha arrays verticalmente (linha sobre linha). Atalho para `concatenate` com `axis=0`. | `a=np.array([1,2]); b=np.array([3,4]); np.vstack((a,b))` |
| `np.hstack()` | Empilha arrays horizontalmente (lado a lado). Atalho para `concatenate` com `axis=1`. | `a=np.array([[1],[2]]); b=np.array([[3],[4]]); np.hstack((a,b))` |
| `np.split()` | Divide um array em múltiplos sub-arrays. | `a = np.arange(9); np.split(a, 3)` |
| `np.append()` | Adiciona elementos ao final de um array, retornando um novo array. | `a = np.array([1, 2]); b = np.append(a, [3, 4])` |
| `np.insert()` | Insere valores em um array antes de um determinado índice. Retorna um novo array. | `a = np.array([1, 2, 4]); np.insert(a, 2, 3)` |
| `np.delete()` | Remove elementos de um array. Retorna um novo array. | `a = np.arange(5); np.delete(a, 2)` |
| `np.sort()` | Retorna uma cópia ordenada do array. | `a = np.array([3, 1, 2]); np.sort(a)` |
| `np.unique()` | Retorna os elementos únicos de um array, em ordem crescente. | `a = np.array([1, 2, 2, 3, 1]); np.unique(a)` |
| `arr.astype()` | Cria uma cópia do array com o tipo de dado (dtype) especificado. | `a = np.array([1.1, 2.2]); a.astype(int)` |
| `np.resize()` | Retorna um novo array com uma nova forma. Se a forma for maior, o novo array é preenchido com cópias repetidas do original. | `a = np.array([1,2,3]); np.resize(a, (3, 2))` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Operações Matemáticas e Estatísticas

```ad-quote
title:
<p align="justify">O NumPy se destaca na execução de <b>operações matemáticas vetorizadas</b>, que são aplicadas a todos os elementos de um array de uma só vez, resultando em um desempenho muito superior ao de laços em Python puro.</p>
```

```ad-quote
title:

###### **Operações Aritméticas e Funções Universais (ufuncs)**

- **Soma:** `np.add()` ou `+`
- **Subtração:** `np.subtract()` ou `-`
- **Multiplicação:** `np.multiply()` ou `*`
- **Divisão:** `np.divide()` ou `/`
- **Raiz Quadrada:** `np.sqrt()`
- **Trigonométricas:** `np.sin()`, `np.cos()`, `np.tan()`
- **Exponenciais e Logarítmicas:** `np.exp()`, `np.log()`

###### **Métodos Estatísticos**

| Método | Descrição |
|---|---|
| `np.mean()` | Calcula a média dos elementos. |
| `np.median()` | Calcula a mediana dos elementos. |
| `np.std()` | Calcula o desvio padrão. |
| `np.sum()` | Calcula a soma dos elementos. |
| `np.min()` / `np.max()` | Retorna o valor mínimo / máximo. |
| `np.argmin()` / `np.argmax()` | Retorna o índice do valor mínimo / máximo. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Álgebra Linear

```ad-quote
title:
O submódulo `linalg` do NumPy oferece uma ampla gama de funções de álgebra linear essenciais para diversas áreas da ciência e engenharia.
```

```ad-quote
title:

| Método | Descrição |
|---|---|
| `np.linalg.inv()` | Calcula a inversa de uma matriz. |
| `np.linalg.det()` | Calcula o determinante de uma matriz. |
| `np.dot()` ou `@` | Realiza o produto de matrizes. |
| `np.linalg.eig()` | Calcula os autovalores e autovetores de uma matriz. |
| `np.linalg.solve()`| Soluciona um sistema de equações lineares. |

```
````

---

```bash
**Fundamentos e Estrutura de Dados**

1. Criação de Arrays
    
2. Tipos de Dados (dtypes)
    
3. Atributos de Arrays
    

**Acesso e Manipulação de Dados**

4. Indexação e Fatiamento (Slicing)
    
5. Manipulação de Arrays
    

**Computação Numérica e Matemática**

6. Operações Matemáticas e Vetorização (Ufuncs)
    
7. Broadcasting
    
8. Funções Estatísticas e de Agregação
    
9. Álgebra Linear (submódulo `numpy.linalg`)
    

**Funcionalidades Avançadas e Especializadas**

10. Geração de Números Aleatórios (submódulo `numpy.random`)
    
11. Arrays Estruturados (Structured Arrays)
    
12. Polinômios (submódulo `numpy.polynomial`)
    
13. Transformada de Fourier (submódulo `numpy.fft`)
    

**Interação e Performance**

14. Entrada e Saída (I/O) de Arquivos
    
15. Visões (Views) vs. Cópias (Copies) e Gerenciamento de Memória
    
16. Interoperabilidade
```