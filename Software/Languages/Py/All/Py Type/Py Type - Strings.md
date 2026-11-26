---
banner: "![[Pasted image 20251215191705.png]]"
banner-x: 50
banner-y: 40
---

---

````ad-quote
title:

##### **Intro )** - Definição de Strings

```ad-quote
title:
<p align="justify">Strings são sequências imutáveis de caracteres Unicode em Python, utilizadas para representar texto. Elas são uma das estruturas de dados mais fundamentais e amplamente utilizadas na linguagem, oferecendo uma variedade de métodos para manipulação e formatação de texto.</p>
```

```ad-quote
title:
<p align="justify"><b>Link:</b> <a href="https://www.w3schools.com/python/python_strings.asp">Python Strings</a></p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Boas Práticas e Limitações

```ad-quote
title:
**Boas Práticas**
```

```ad-quote
title:

| Índice | Boa prática |
| --- | --- |
| 1 ) | Use f-strings para formatação moderna e legível (Python 3.6+) |
| 2 ) | Prefira métodos de string em vez de manipulação manual |
| 3 ) | Utilize raw strings (r"") para caminhos de arquivo e regex |
| 4 ) | Considere interpolação de strings para templates complexos |

```

```ad-quote
title:
**Limitações e Alternativas**
```

```ad-quote
title:

| Condição | Alternativa |
| --- | --- |
| Manipulação intensiva de strings | Use io.StringIO para eficiência |
| Strings muito grandes | Considere leitura por chunks ou generators |
| Concatenação em loops | Use list comprehension com join() |
| Texto com emojis/unicode complexo | Garanta encoding UTF-8 |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Fundamentos das Strings

```ad-quote
title:
**Definição e Características:**
```

```ad-quote
title:

| Definição | Explicação |
| --- | --- |
| Sequência imutável | Não pode ser alterada após criação |
| Unicode por padrão | Suporte a caracteres internacionais |
| Indexável | Acessível por índices numéricos |
| Iterável | Pode ser percorrida em loops |

```

```ad-quote
title:
<p align="justify"><b>Estrutura Básica:</b></p>
```

```python
string = "Texto entre aspas"
string = 'Texto entre aspas simples'
string = """Texto com
múltiplas linhas"""
```

```ad-quote
title:
<p align="justify"><b>Exemplo:</b></p>
```

```python
mensagem = "Olá, mundo!"
nome = "Maria Silva"
email = "maria@exemplo.com"
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Criação de Strings

```ad-quote
title:
**Tipos de Strings:**
```

```ad-quote
title:

| Tipo | Explicação |
| --- | --- |
| Strings simples | "texto" ou 'texto' |
| Strings multilinha | """texto""" ou '''texto''' |
| Raw strings | r"texto" (ignora escape sequences) |
| Bytes strings | b"texto" (para dados binários) |
| f-strings | f"texto {variavel}" (formatação) |

```

```ad-quote
title:
<p align="justify"><b>Métodos de Criação:</b></p>
```

```python
# Método literal (mais comum)
s1 = "Hello World"
s2 = 'Python Programming'

# Usando str()
s3 = str(42)  # Converte número para string
s4 = str([1, 2, 3])  # Converte lista para string

# f-strings (Python 3.6+)
nome = "Ana"
idade = 25
s5 = f"{nome} tem {idade} anos"

# Raw strings
s6 = r"C:\Users\Documentos\novo.txt"
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Operações Básicas

```ad-quote
title:
Strings em Python suportam operações como concatenação (+), repetição (*), fatiamento ([inicio:fim:passo]), e métodos para busca, substituição e verificação. São imutáveis, então operações que "modificam" retornam novas strings.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Acesso a Caracteres
```

```ad-quote
title:
Acesso direto usando índices. Índices negativos contam a partir do final.
```

```python
texto = "Python"
print(texto[0])    # 'P'
print(texto[-1])   # 'n'
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Fatiamento - Slicing
```

```ad-quote
title:
Extrai substrings usando [inicio:fim:passo]. Valores omitidos usam padrões.
```

```python
texto = "Programação"
print(texto[0:7])    # "Program"
print(texto[::2])    # "Pormçã" (cada 2º caractere)
print(texto[::-1])   # "õaçamargorP" (invertida)
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Concatenação e Repetição
```

```ad-quote
title:
+ para juntar strings, * para repetir.
```

```python
nome = "Ana"
sobrenome = "Silva"
nome_completo = nome + " " + sobrenome  # "Ana Silva"

risadas = "ha" * 3  # "hahaha"
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) Métodos de Busca
```

```ad-quote
title:
find(), index(), count() para localizar substrings.
```

```python
texto = "Python é fantástico"
print(texto.find("th"))     # 2
print(texto.index("é"))     # 7
print(texto.count("a"))     # 2
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Métodos Principais

```ad-quote
title:
<p align="justify"><b>Métodos de Transformação:</b></p>
```

```python
texto = "  Python Programming  "

# Remoção de espaços
print(texto.strip())        # "Python Programming"
print(texto.rstrip())       # "  Python Programming"
print(texto.lstrip())       # "Python Programming  "

# Alteração de case
print("python".upper())     # "PYTHON"
print("PYTHON".lower())     # "python"
print("python".title())     # "Python"

# Substituição
print("banana".replace("a", "o"))  # "bonono"
```

```ad-quote
title:
<p align="justify"><b>Métodos de Verificação:</b></p>
```

```python
# Verificações booleanas
print("123".isdigit())      # True
print("abc".isalpha())      # True
print("abc123".isalnum())   # True
print(" ".isspace())        # True
print("Python".istitle())   # True
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Formatação de Strings

```ad-quote
title:
<p align="justify"><b>Métodos de Formatação:</b></p>
```

```python
# f-strings (moderno)
nome = "Carlos"
idade = 30
print(f"{nome} tem {idade} anos")  # "Carlos tem 30 anos"

# format()
print("{} tem {} anos".format(nome, idade))

# % formatting (legado)
print("%s tem %d anos" % (nome, idade))
```

```ad-quote
title:
<p align="justify"><b>Formatação Avançada:</b></p>
```

```python
# Alinhamento e preenchimento
print(f"{nome:>10}")    # "    Carlos"
print(f"{nome:<10}")    # "Carlos    "
print(f"{nome:^10}")    # "  Carlos  "

# Formatação numérica
preco = 99.999
print(f"{preco:.2f}")   # "100.00"
print(f"{preco:08.2f}") # "00100.00"
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Técnicas Avançadas

```ad-quote
title:
**Strings Multilinha**
```

```ad-quote
title:
Triplas aspas para texto com quebras de linha preservadas.
```

```python
texto = """Linha 1
Linha 2
Linha 3"""

html = """
<html>
    <body>
        <h1>Título</h1>
    </body>
</html>
"""
```

```ad-quote
title:
**Raw Strings e Escape**
```

```ad-quote
title:
r-prefix ignora caracteres de escape, útil para regex e caminhos.
```

```python
# Sem raw string
caminho = "C:\\Users\\Documentos\\arquivo.txt"

# Com raw string
caminho = r"C:\Users\Documentos\arquivo.txt"
```

```ad-quote
title:
**Join e Split**
```

```ad-quote
title:
Métodos eficientes para juntar e separar strings.
```

```python
# Join - eficiente para concatenação múltipla
palavras = ["Python", "é", "incrível"]
frase = " ".join(palavras)  # "Python é incrível"

# Split - separação em partes
texto = "um,dois,três"
partes = texto.split(",")  # ["um", "dois", "três"]
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **08 )** - Performance e Casos de Uso

```ad-quote
title:

| Operação | Complexidade |
| --- | --- |
| Acesso por índice | O(1) |
| Concatenação | O(n + m) |
| Fatiamento | O(k) para slice de tamanho k |
| Busca (find/index) | O(n) |

```

```ad-quote
title:
**Manipulação de Texto**
```

```python
# Processamento de texto
texto = "Python é uma linguagem de programação"
palavras = texto.split()
palavras_maiusculas = [p.upper() for p in palavras]
```

```ad-quote
title:
**Validação de Entrada**
```

```python
def validar_email(email):
    return "@" in email and "." in email.split("@")[1]

def validar_senha(senha):
    return (len(senha) >= 8 and 
            any(c.isdigit() for c in senha) and
            any(c.isalpha() for c in senha))
```

```ad-quote
title:
**Template Strings**
```

```python
from string import Template

template = Template("Olá, $nome! Seu saldo é: $${saldo}")
mensagem = template.substitute(nome="João", saldo=100.50)
```
````

---

```ad-example

#### **Py Strings** - Funções de Manipulação

```

---

````ad-quote
title:
```ad-quote
title:
Em Python, strings (sequências de texto) são um dos tipos de dados mais utilizados e vêm com uma vasta coleção de métodos para manipulação e análise. Diferente de listas e dicionários, strings são imutáveis, o que significa que nenhum método modifica a string original. Em vez disso, eles sempre retornam uma nova string com o resultado da operação.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### 01 ) - Métodos de String: Transformação de Caixa

```ad-quote
title:
Métodos que alteram a capitalização dos caracteres, retornando novas strings.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `upper()` | Retorna cópia com todos os caracteres em maiúsculas. | `"texto".upper() -> "TEXTO"` |
| `lower()` | Retorna cópia com todos os caracteres em minúsculas. | `"TEXTO".lower() -> "texto"` |
| `capitalize()` | Retorna cópia com primeiro caractere maiúsculo. | `"texto".capitalize() -> "Texto"` |
| `title()` | Retorna cópia com primeiro caractere de cada palavra maiúsculo. | `"texto exemplo".title() -> "Texto Exemplo"` |
| `swapcase()` | Retorna cópia com a caixa de cada caractere invertida. | `"TeXTo".swapcase() -> "tExTO"` |
| `casefold()` | Retorna versão para comparações sem distinção de caixa. | `"STRASSE".casefold() -> "strasse"` |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### 02 ) - Métodos de String: Busca e Verificação

```ad-quote
title:
Métodos para localizar substrings e verificar condições, retornando booleanos ou índices.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `startswith()` | Retorna True se a string começa com o prefixo. | `"texto".startswith("tex") -> True` |
| `endswith()` | Retorna True se a string termina com o sufixo. | `"texto".endswith("to") -> True` |
| `find()` | Retorna índice da substring ou -1 se não encontrada. | `"texto".find("ex") -> 1` |
| `rfind()` | Similar ao find(), mas busca do final. | `"texto texto".rfind("ex") -> 7` |
| `index()` | Similar ao find(), mas gera erro se não encontrar. | `"texto".index("ex") -> 1` |
| `rindex()` | Similar ao index(), mas busca do final. | `"texto texto".rindex("ex") -> 7` |
| `count()` | Retorna número de ocorrências da substring. | `"texto".count("t") -> 2` |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### 03 ) - Métodos de String: Divisão e Junção

```ad-quote
title:
Métodos para dividir strings em partes ou juntar iteráveis em strings.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `split()` | Divide string em lista usando separador. | `"a,b,c".split(",") -> ["a","b","c"]` |
| `rsplit()` | Similar ao split(), mas começa do final. | `"a,b,c".rsplit(",", 1) -> ["a,b","c"]` |
| `splitlines()` | Divide string em lista de linhas. | `"linha1\nlinha2".splitlines() -> ["linha1","linha2"]` |
| `partition()` | Divide string na primeira ocorrência do separador. | `"nome=valor".partition("=") -> ("nome","=","valor")` |
| `rpartition()` | Similar ao partition(), mas busca do final. | `"dir/arquivo.txt".rpartition("/") -> ("dir","/","arquivo.txt")` |
| `join()` | Concatena iterável usando string como separador. | `",".join(["a","b","c"]) -> "a,b,c"` |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### 04 ) - Métodos de String: Limpeza e Preenchimento

```ad-quote
title:
Métodos para remover caracteres indesejados ou ajustar o preenchimento da string.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `strip()` | Remove caracteres do início e fim. | `" texto ".strip() -> "texto"` |
| `lstrip()` | Remove caracteres apenas do início. | `" texto ".lstrip() -> "texto "` |
| `rstrip()` | Remove caracteres apenas do fim. | `" texto ".rstrip() -> " texto"` |
| `center()` | Retorna string centralizada com preenchimento. | `"txt".center(7, "-") -> "--txt--"` |
| `ljust()` | Retorna string alinhada à esquerda. | `"txt".ljust(5) -> "txt  "` |
| `rjust()` | Retorna string alinhada à direita. | `"txt".rjust(5) -> "  txt"` |
| `zfill()` | Preenche com zeros à esquerda. | `"42".zfill(5) -> "00042"` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 05 ) - Métodos de String: Substituição e Formatação

```ad-quote
title:
Métodos para substituir conteúdo ou formatar valores na string.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `replace()` | Substitui ocorrências de substring. | `"texto".replace("ex","ab") -> "tabto"` |
| `format()` | Formata string inserindo valores. | `"Olá, {}".format("Mundo") -> "Olá, Mundo"` |
| `format_map()` | Similar ao format() usando dicionário. | `"{nome}".format_map({"nome":"João"}) -> "João"` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 06 ) - Métodos de String: Classificação de Caracteres

```ad-quote
title:
Métodos que retornam True ou False baseado na classificação dos caracteres.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `isalnum()` | True se todos caracteres forem alfanuméricos. | `"abc123".isalnum() -> True` |
| `isalpha()` | True se todos caracteres forem alfabéticos. | `"abc".isalpha() -> True` |
| `isascii()` | True se todos caracteres forem ASCII. | `"abc".isascii() -> True` |
| `isdigit()` | True se todos caracteres forem dígitos. | `"123".isdigit() -> True` |
| `isnumeric()` | True se todos caracteres forem numéricos. | `"⅓".isnumeric() -> True` |
| `isdecimal()` | True se todos caracteres forem decimais. | `"123".isdecimal() -> True` |
| `islower()` | True se caracteres com caixa forem minúsculos. | `"texto".islower() -> True` |
| `isupper()` | True se caracteres com caixa forem maiúsculos. | `"TEXTO".isupper() -> True` |
| `isspace()` | True se todos caracteres forem espaços. | `"   ".isspace() -> True` |
| `istitle()` | True se string seguir formato de título. | `"Texto Exemplo".istitle() -> True` |
| `isprintable()` | True se todos caracteres forem imprimíveis. | `"texto".isprintable() -> True` |
| `isidentifier()` | True se for identificador Python válido. | `"var_name".isidentifier() -> True` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 07 ) - Funções Nativas: Operações com Strings

```ad-quote
title:
Funções gerais do Python que podem ser aplicadas a strings.
```

```ad-quote
title:
| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `len()` | Retorna número de caracteres. | `len("texto") -> 5` |
| `str()` | Converte objeto para string. | `str(42) -> "42"` |
| `sorted()` | Retorna lista com caracteres ordenados. | `sorted("cba") -> ["a","b","c"]` |
| `max()` | Retorna caractere com maior Unicode. | `max("abc") -> "c"` |
| `min()` | Retorna caractere com menor Unicode. | `min("abc") -> "a"` |
| `ord()` | Retorna código Unicode do caractere. | `ord("a") -> 97` |
| `chr()` | Retorna caractere do código Unicode. | `chr(97) -> "a"` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 08 ) - Módulo re: Expressões Regulares

```ad-quote
title:
Principais funções do módulo de expressões regulares para manipulação avançada.
```

```ad-quote
title:
| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `re.search()` | Busca por padrão na string. | `re.search(r"\d+", "abc123")` |
| `re.match()` | Verifica se padrão corresponde ao início. | `re.match(r"\d+", "123abc")` |
| `re.findall()` | Encontra todas ocorrências do padrão. | `re.findall(r"\d+", "a1b2") -> ["1","2"]` |
| `re.sub()` | Substitui ocorrências do padrão. | `re.sub(r"\d+", "#", "a1b2") -> "a#b#"` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">Strings são estruturas fundamentais em Python, oferecendo vasta funcionalidade para manipulação e formatação de texto. Seu domínio é essencial para qualquer desenvolvedor Python, desde processamento básico até operações avançadas de texto.</p>
```
````

---