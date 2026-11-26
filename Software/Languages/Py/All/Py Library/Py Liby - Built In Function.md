
---

````ad-quote
title:

```ad-quote
title:
<p align="justify"><b>Python</b> vem equipado com um poderoso conjunto de <b>funções embutidas (built-in)</b> que estão sempre disponíveis, sem a necessidade de importação de bibliotecas. Elas são a base da linguagem e fornecem ferramentas essenciais para manipulação de dados, entrada/saída, operações matemáticas e muito mais. Conhecê-las é fundamental para escrever código eficiente e idiomático.</p>

<p align="justify">A seguir, apresentamos uma lista categorizada das principais funções embutidas do Python 3, demonstrando seu propósito e com exemplos práticos de uso.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Conversão de Tipos e Construtores

```ad-quote
title:
<p align="justify">Essas funções são usadas para criar ou converter objetos para diferentes tipos de dados.</p>
```

```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `int()` | Converte um valor para um número inteiro. | `numero = int("10")` |
| `float()` | Converte um valor para um número de ponto flutuante. | `decimal = float(5)` |
| `str()` | Converte um valor para uma string (texto). | `texto = str(123.45)` |
| `list()` | Cria uma lista a partir de um iterável. | `minha_lista = list((1, 2, 3))` |
| `tuple()` | Cria uma tupla a partir de um iterável. | `minha_tupla = tuple([1, 2, 3])` |
| `dict()` | Cria um dicionário. | `meu_dict = dict(nome="Ana", idade=25)` |
| `set()` | Cria um conjunto (coleção de itens únicos). | `conjunto = set([1, 2, 2, 3])` |
| `frozenset()` | Cria um conjunto imutável. | `conjunto_imutavel = frozenset([1, 2, 3])` |
| `bool()` | Converte um valor para um booleano (`True` ou `False`). | `verdadeiro = bool(1)` |
| `complex()` | Cria um número complexo. | `num_complexo = complex(2, 5)` |
| `bytes()` | Cria um objeto de bytes imutável. | `dados_bin = bytes(5)` |
| `chr()` | Retorna o caractere de um código Unicode. | `letra = chr(65)` |
| `ord()` | Retorna o código Unicode de um caractere. | `codigo = ord('A')` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Entrada e Saída (I/O)

```ad-quote
title:
<p align="justify">Funções para interagir com o usuário e exibir informações.</p>
```

```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `print()` | Imprime objetos na tela. | `print("Olá, Mundo!")` |
| `input()` | Lê uma linha de texto do usuário. | `nome = input("Digite seu nome: ")` |
| `open()` | Abre um arquivo e retorna um objeto de arquivo. | `arquivo = open("texto.txt", "r")` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Operações Matemáticas

```ad-quote
title:
<p align="justify">Funções para realizar cálculos numéricos.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `abs()` | Retorna o valor absoluto de um número. | `valor = abs(-10)` |
| `sum()` | Soma os itens de um iterável. | `total = sum([1, 2, 3, 4])` |
| `max()` | Retorna o maior item de um iterável. | `maior = max(10, 25, 5)` |
| `min()` | Retorna o menor item de um iterável. | `menor = min(10, 25, 5)` |
| `round()` | Arredonda um número. | `arredondado = round(3.14159, 2)` |
| `pow()` | Retorna `x` elevado à potência `y`. | `potencia = pow(2, 3)` |
| `divmod()` | Retorna o par (quociente, resto) da divisão. | `resultado = divmod(10, 3)` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Iteração e Sequências

```ad-quote
title:
<p align="justify">Funções essenciais para trabalhar com listas, tuplas e outros objetos iteráveis.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `len()` | Retorna o número de itens (comprimento) de um objeto. | `tamanho = len("python")` |
| `range()` | Gera uma sequência imutável de números. | `for i in range(5): print(i)` |
| `enumerate()` | Retorna pares (índice, valor) de um iterável. | `for i, v in enumerate(['a','b','c']): print(i, v)` |
| `zip()` | Agrega elementos de múltiplos iteráveis em tuplas. | `for item in zip([1,2], ['a','b']): print(item)` |
| `sorted()` | Retorna uma nova lista ordenada. | `nova_lista = sorted([3, 1, 2])` |
| `reversed()` | Retorna um iterador que percorre na ordem inversa. | `for i in reversed([1,2,3]): print(i)` |
| `map()` | Aplica uma função a cada item de um iterável. | `dobros = list(map(lambda x: x*2, [1,2,3]))` |
| `filter()` | Filtra elementos de um iterável. | `pares = list(filter(lambda x: x%2==0, [1,2,3,4]))` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Introspecção e Atributos de Objetos

```ad-quote
title:
<p align="justify">Funções que permitem examinar objetos e suas propriedades em tempo de execução.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `type()` | Retorna o tipo de um objeto. | `print(type(10))` |
| `id()` | Retorna o endereço de memória de um objeto. | `print(id(10))` |
| `dir()` | Retorna uma lista de atributos e métodos de um objeto. | `print(dir([]))` |
| `help()` | Invoca o sistema de ajuda integrado. | `help(list)` |
| `isinstance()` | Verifica se um objeto é uma instância de uma classe. | `print(isinstance(10, int))` |
| `issubclass()` | Verifica se uma classe é uma subclasse de outra. | `print(issubclass(bool, int))` |
| `hasattr()` | Verifica se um objeto possui um determinado atributo. | `print(hasattr("texto", "upper"))` |
| `callable()` | Verifica se um objeto pode ser chamado (como uma função). | `print(callable(print))` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Verificação Lógica

```ad-quote
title:
<p align="justify">Funções que operam sobre valores booleanos em iteráveis para retornar um único resultado.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `all()` | Retorna `True` se **todos** os elementos forem verdadeiros. | `print(all([True, True, 1]))` |
| `any()` | Retorna `True` se **pelo menos um** elemento for verdadeiro. | `print(any([False, False, 1]))` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Funções Avançadas e de Programação Orientada a Objetos

```ad-quote
title:
<p align="justify">Funções mais específicas ou relacionadas a paradigmas de programação e execução de código.</p>
```
```ad-quote
title:

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `super()` | Permite chamar métodos da classe pai (superclasse). | `class B(A): def __init__(self): super().__init__()` |
| `property()` | Usado para criar propriedades gerenciadas em classes. | `class C: @property def x(self): return self._x` |
| `classmethod()`| Transforma um método em um método de classe. | `class D: @classmethod def m(cls): ...` |
| `staticmethod()`| Transforma um método em um método estático. | `class E: @staticmethod def m(): ...` |
| `eval()` | Executa uma string como uma expressão Python. **(Use com cuidado!)**| `resultado = eval("2 + 2")` |
| `exec()` | Executa um bloco de código Python. **(Use com cuidado!)**| `exec("x = 10; print(x)")` |
| `globals()` | Retorna um dicionário com as variáveis globais. | `print(globals())` |
| `locals()` | Retorna um dicionário com as variáveis locais. | `def f(): print(locals())` |

```
````

---