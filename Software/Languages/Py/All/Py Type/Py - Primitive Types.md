
---

```ad-quote
title: **Def**

Python é uma linguagem de programação com tipagem dinâmica, o que significa que você não precisa declarar o tipo de uma variável explicitamente. O interpretador Python infere o tipo automaticamente com base no valor atribuído. Vamos explorar os principais tipos de dados em Python.
```

>[!quote] **Link** [Python Data Types](https://www.w3schools.com/python/python_datatypes.asp)

---
#### **Considerações sobre Tipos em Python**

```ad-quote
title: **Def**

**Mutabilidade**:
   - Mutáveis: listas, dicionários, conjuntos, bytearray
   - Imutáveis: números, strings, tuplas, booleanos, frozenset

---

**Operações**:
   - Diferentes tipos suportam operações diferentes
   - Por exemplo, você pode somar números e concatenar strings, mas não pode somar strings com números sem conversão

---

**Métodos**:
   - Cada tipo tem seus próprios métodos
   - Exemplo: strings têm métodos como `.upper()`, `.split()`, listas têm `.append()`, `.sort()`, etc.
```

---

```ad-example

#### **Tipos de Dados Básicos / Primitivos**
```

---
#### **Numeric Types**

```ad-quote
title: **Def**

**int (inteiros)**: 
- Números inteiros (positivos ou negativos)

```

  ```python
  x = 10
  y = -5
  ```

```ad-quote
title: **Def**

**float (ponto flutuante)**: 
- Números decimais
```

  ```python
  pi = 3.14159
  temperatura = -10.5
  ```

```ad-quote
title: **Def**

**complex (números complexos)**: 
- Números com parte real e imaginária
```

  ```python
  z = 3 + 5j
  ```

---
#### **Boolean / Bool**

>[!quote] Representa valores lógicos True ou False

```python
ativo = True
desligado = False
```

---
#### **Strings / str**

>[!quote]  Sequências de caracteres entre aspas simples ou duplas

```python
nome = "João"
mensagem = 'Olá, mundo!'
```

>[!quote] [[Py - Strings Methods]]

>[!quote]  [[Py Strings Operations]]

---

```ad-example

#### **Tipos de Dados Compostos**
```

---
#### **Listas / List**

>[!quote]  Coleções ordenadas e mutáveis de itens (podem conter tipos diferentes)

```python
frutas = ['maçã', 'banana', 'laranja']
numeros = [1, 2, 3, 4, 5]
misturado = [1, 'texto', 3.14, True]
```

---
#### **Tuplas Tuple**

>[!quote]  Coleções ordenadas e imutáveis de itens

```python
coordenadas = (10.0, 20.0)
cores = ('vermelho', 'verde', 'azul')
```

---
#### **Conjuntos Set**

>[!quote]  Coleções não ordenadas de itens únicos

```python
vogais = {'a', 'e', 'i', 'o', 'u'}
numeros = {1, 2, 3, 4, 5}
```

---
#### **Dicionários Dict**

>[!quote]  Coleções de pares chave-valor

```python
pessoa = {'nome': 'Maria', 'idade': 25, 'cidade': 'São Paulo'}
```

---

```ad-example

#### **Tipos de Dados Especiais**
```

---
#### **NoneType**

>[!quote]  Representa a ausência de valor (similar a null em outras linguagens)

```python
valor = None
```

---
#### **Bytes e Bytearray**

>[!quote]  Para trabalhar com dados binários

```python
dados_brutos = b'algum dado'
dados_mutaveis = bytearray(b'algum dado')
```

---

```ad-example

#### **Verificando Tipos de Dados**
```

---
#### **Verificação de tipos**

>[!quote]  Você pode verificar o tipo de uma variável usando a função `type()`:

```python
print(type(10))        # <class 'int'>
print(type(3.14))      # <class 'float'>
print(type(True))      # <class 'bool'>
print(type("texto"))   # <class 'str'>
print(type([1, 2, 3])) # <class 'list'>
```

---
#### **Conversão entre Tipos Type Casting**

>[!quote]  Python permite conversão entre tipos usando funções como:

>[!quote] **Link:** [Python Casting](https://www.w3schools.com/python/python_casting.asp)

```python
int()    # converte para inteiro
float()  # converte para float
str()    # converte para string
list()   # converte para lista
tuple()  # converte para tupla
set()    # converte para conjunto
dict()   # converte para dicionário
```
###### **Exemplos:**

```python
numero = int("10")       # converte string para int
texto = str(3.14)        # converte float para string
lista = tuple([1, 2, 3]) # converte lista para tupla
```

---

