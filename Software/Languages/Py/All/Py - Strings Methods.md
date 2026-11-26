
---
#### **Criação de Strings**

```python
# Aspas simples ou duplas
nome = 'Alice'
mensagem = "Olá, mundo!"

# Multilinha (preserva quebras de linha)
poema = """Rosas são vermelhas,
Violetas são azuis,
Python é incrível,
E você também!"""

# Raw strings (ignora escapes)
# Não interpreta \n como newline
caminho = r'C:\novo\diretorio\arquivo.txt'
```

>[!quote] **Link: ** [Python Strings](https://www.w3schools.com/python/python_strings.asp)

---

```ad-example

#### **Resumo**
```

---
#### **Criação e Básicos**

```ad-quote
title: **Def**

Strings são sequências imutáveis de caracteres criadas com:

Aspas simples: 
- `'texto'`
  
Aspas duplas: 
- `"texto"`
  
Triplas aspas para múltiplas linhas: 
- `"""texto"""`
  
Raw strings (ignoram escapes): 
- `r'C:\caminho'`
  
```

---
#### **Operações Principais**

```ad-quote
title: **Def**

**Concatenação**: 
- `"Py" + "thon"` → `'Python'`
  
**Repetição**: 
- `"Ha" * 3` → `'HaHaHa'`
  
**Indexação**: 
- `"Python"[0]` → `'P'`
  
**Fatiamento**: 
- `"Python"[2:5]` → `'tho'`, `[::-1]` inverte a string
  
```

---
#### **Modificação de Case**

```ad-quote
title: **Def**

`.upper()`: 
- Maiúsculas

---

`.lower()`: 
- Minúsculas

---

`.capitalize()`: 
- Primeira letra maiúscula

---

`.title()`: 
- Cada palavra com inicial maiúscula

---

`.swapcase()`: 
- Inverte maiúsculas/minúsculas
  
```

---
#### **Busca e Verificação**

```ad-quote
title: **Def**

`.find(sub)`: 
- Retorna posição ou -1

---

`.index(sub)`: 
- Como find mas gera erro se não encontrar

---

`.count(sub)`: 
- Conta ocorrências

---

`.startswith()`/.`endswith()`: 
- Verifica início/fim

---

`.isalpha()`/.`isdigit()`/.`isalnum()`: 
- Testa composição

```

---
#### **Manipulação**

```ad-quote
title: **Def**

`.split()`: 
- Divide em lista

---

`.join()`: 
- Une iterável com separador

---

`.strip()`: 
- Remove espaços/extremos

---

`.replace(old, new)`: 
- Substitui texto

---

`.zfill(width)`: 
- Preenche com zeros

```

---
#### **Formatação**

```ad-quote
title: **Def**

**f-strings**: 
- `f"Valor: {var}"` (Python 3.6+)
  
---

**.format()**: 
- `"{}".format(valor)`

---

- **Alinhamento**: 
  - `.ljust()`: Alinha à esquerda
  - `.rjust()`: Alinha à direita
  - `.center()`: Centraliza
```

---
#### **Unicode e Codificação**

```ad-quote
title: **Def**

Suporte nativo a caracteres especiais e emojis

`.encode()`: 
- Converte para bytes
  
---

`.decode()`: 
- Converte bytes para string
  

```

---

```ad-example

#### **Métodos de Strings**
```

---
## **Métodos de Formatação**

---

```ad-quote
title: **Def**

#### `str.capitalize()`
- **Função**: Retorna uma cópia da string com o primeiro caractere em maiúsculo e os demais em minúsculo
```
###### ***Exemplo***:

  ```python
  "python".capitalize()  # 'Python'
  "hELLO wORLD".capitalize()  # 'Hello world'
  ```

---

```ad-quote
title: **Def**

#### `str.title()`
- **Função**: Converte a primeira letra de cada palavra para maiúscula
```
###### ***Exemplo***:

  ```python
  "hello world".title()  # 'Hello World'
  "python_programming".title()  # 'Python_Programming'
  ```

---

```ad-quote
title: **Def**

#### `str.lower()` e `str.upper()`
- **Funções**:
  - `lower()`: Converte todos caracteres para minúsculo
  - `upper()`: Converte todos caracteres para maiúsculo
```
###### ***Exemplo***:

  ```python
  "Python".lower()  # 'python'
  "Python".upper()  # 'PYTHON'
  ```

---

```ad-quote
title: **Def**

#### `str.swapcase()`
- **Função**: Inverte o case de todos os caracteres
```
###### ***Exemplo***:

  ```python
  "PyThOn".swapcase()  # 'pYtHoN'
  ```

---
## **Métodos de Busca**

---

```ad-quote
title: **Def**

#### `str.find(sub[, start[, end]])`

**Função**: 
- Retorna o índice mais baixo onde a substring é encontrada (-1 se não encontrar)

**Parâmetros**:
  - `sub`: Substring a ser buscada
  - `start` (opcional): Índice inicial
  - `end` (opcional): Índice final
```
###### ***Exemplo***:

  ```python
  "banana".find("na")        # 2
  "banana".find("na", 3)     # 4
  "banana".find("na", 1, 3)  # 2
  ```

---

```ad-quote
title: **Def**

#### `str.index(sub[, start[, end]])`

**Função**: 
- Similar ao `find()`, mas levanta `ValueError` se não encontrar
```
###### ***Exemplo***:

  ```python
  "banana".index("na")     # 2
  "banana".index("na", 3)  # 4
  "banana".index("he")     #valueError
  ```

---

```ad-quote
title: **Def**

 #### `str.count(sub[, start[, end]])`
 
**Função**: 
- Conta ocorrências de uma substring
```
###### ***Exemplo***:

  ```python
  "banana".count("a")   # 3
  "banana".count("na")  # 2
  ```

---
## **Métodos de Divisão e Junção**

---

```ad-quote
title: **Def**

#### `str.split([sep[, maxsplit]])`

**Função**: 
- Divide a string usando um separador
  
**Parâmetros**:
  - `sep`: Separador (default: whitespace)
  - `maxsplit`: Número máximo de divisões
```
###### ***Exemplo***:

  ```python
  "a,b,c".split(",")  # ['a', 'b', 'c']
  "a b c".split()  # ['a', 'b', 'c']
  "a,b,c".split(",", maxsplit=1)  # ['a', 'b,c']
  ```

---

```ad-quote
title: **Def**

#### `str.rsplit([sep[, maxsplit]])`

**Função**: 
- Similar ao `split()`, mas começa pela direita
```
###### ***Exemplo***:

  ```python
  "a,b,c".rsplit(",", maxsplit=1)  # ['a,b', 'c']
  ```

---

```ad-quote
title: **Def**

#### `str.join(iterable)`

**Função**: 
- Junta elementos de um iterável com a string como separador
```
###### ***Exemplo***:

  ```python
  ", ".join(["a", "b", "c"])  # 'a, b, c'
  "".join(["P", "y", "t", "h", "o", "n"])  # 'Python'
  ```

---
## **Métodos de Limpeza**

---

```ad-quote
title: **Def**

#### `str.strip([chars])`

**Função**: 
- Remove caracteres especificados (ou whitespace) dos extremos
```
###### ***Exemplo***:

  ```python
  "   hello   ".strip()  # 'hello'
  "xxhelloxx".strip("x")  # 'hello'
  ```

---

```ad-quote
title: **Def**

#### `str.lstrip([chars])` e `str.rstrip([chars])`

**Funções**:
  - `lstrip()`: Remove apenas à esquerda
  - `rstrip()`: Remove apenas à direita
```
###### ***Exemplo***:

  ```python
  "   hello   ".lstrip()  # 'hello   '
  "xxhelloxx".rstrip("x")  # 'xxhello'
  ```

---
## **Métodos de Verificação**

---

```ad-quote
title: **Def**

#### `str.isdigit()`

**Função**: 
- Verifica se todos caracteres são dígitos
```
###### ***Exemplo***:

  ```python
  "123".isdigit()  # True
  "12a".isdigit()  # False
  ```

---

```ad-quote
title: **Def**

#### `str.isalpha()`

**Função**: 
- Verifica se todos caracteres são letras
```
###### ***Exemplo***:

  ```python
  "abc".isalpha()  # True
  "ab1".isalpha()  # False
  ```

---

```ad-quote
title: **Def**

#### `str.isalnum()`

**Função**: 
- Verifica se todos caracteres são alfanuméricos
```
###### ***Exemplo***:

  ```python
  "abc123".isalnum()  # True
  "abc 123".isalnum()  # False
  ```

---
## **Métodos de Substituição**

---

```ad-quote
title: **Def**

#### `str.replace(old, new[, count])`

**Função**: 
- Substitui ocorrências de uma substring

**Parâmetros**:
  - `old`: Substring a ser substituída
  - `new`: Nova substring
  - `count` (opcional): Número máximo de substituições
```
###### ***Exemplo***:

  ```python
  "banana".replace("a", "o")  # 'bonono'
  "banana".replace("a", "o", 2)  # 'bonana'
  ```

---

```ad-quote
title: **Def**

#### `str.translate(table)`

**Função**: 
- Realiza substituições usando uma tabela de tradução
```
###### ***Exemplo***:

  ```python
  trans = str.maketrans("aeiou", "12345")
  "banana".translate(trans)  # 'b1n1n1'
  ```

---
## **Métodos de Alinhamento**

---

```ad-quote
title: **Def**

#### `str.ljust(width[, fillchar])`

**Função**: 
- Justifica à esquerda em um campo de tamanho `width`
```
###### ***Exemplo***:

  ```python
  "hello".ljust(10, "-")  # 'hello-----'
  ```

---

```ad-quote
title: **Def**

#### `str.rjust(width[, fillchar])`

**Função**: 
- Justifica à direita em um campo de tamanho `width`
```
###### ***Exemplo***:

  ```python
  "hello".rjust(10)  # '     hello'
  ```

---

```ad-quote
title: **Def**

#### `str.center(width[, fillchar])`

**Função**: 
- Centraliza em um campo de tamanho `width`
```
###### ***Exemplo***:

  ```python
  "hello".center(11, "*")  # '***hello***'
  ```

---

```ad-quote
title: **Def**

#### `str.zfill(width)`

**Função**: 
- Preenche com zeros à esquerda
```
###### ***Exemplo***:

  ```python
  "42".zfill(5)  # '00042'
  "-3.14".zfill(8)  # '-0003.14'
  ```

---
## **Métodos para Unicode**

---

```ad-quote
title: **Def**

#### `str.encode(encoding='utf-8', errors='strict')`

**Função**: 
- Codifica a string para bytes
```
###### ***Exemplo***:

  ```python
  "café".encode()  # b'caf\xc3\xa9'
  "こんにちは".encode('utf-8')  # b'\xe3\x81\x93\xe3\x82\x93\xe3\x81\xab\xe3\x81\xa1\xe3\x81\xaf'
  ```

---

```ad-quote
title: **Def**

#### `str.isascii()`

**Função**: 
- Verifica se todos caracteres são ASCII (Python 3.7+)
```
###### ***Exemplo***:

  ```python
  "Python".isascii()  # True
  "café".isascii()  # False
  ```

---
## **Métodos de Transformação**

---

```ad-quote
title: **Def**

#### `str.expandtabs(tabsize=8)`

**Função**: 
- Substitui tabs por espaços
```
###### ***Exemplo***:

  ```python
  "a\tb".expandtabs(4)  # 'a   b'
  ```

---

```ad-quote
title: **Def**

#### `str.maketrans(x[, y[, z]])`

**Função**: 
- Cria tabela de tradução para `translate()`
```
###### ***Exemplo***:

  ```python
  trans = str.maketrans({'a': '1', 'e': '2'})
  "abcde".translate(trans)  # '1bcd2'
  ```

---
