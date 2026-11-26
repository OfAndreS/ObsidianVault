
---

```ad-example

#### **Formatação Avançada**
```

---

##### *f-strings (Python 3.6+)*

```python
nome = "Carlos"
idade = 30
print(f"{nome} tem {idade} anos e ganha R${1500.50:.2f}")
# Saída: Carlos tem 30 anos e ganha R$1500.50
```

---
##### *Método `.format()`*

```python
"{} + {} = {}".format(2, 3, 2+3)  # '2 + 3 = 5'
"{1} vem antes de {0}".format("b", "a")  # 'a vem antes de b'
```

---
##### *Alinhamento*

```python
"Python".ljust(10, '-')  # 'Python----'
"Python".center(10, '=') # '==Python=='
"Python".rjust(10)       # '    Python'
```

---

```ad-example

#### **Manipulação de Texto**
```

---

```python
# Junção e divisão
", ".join(["a", "b", "c"])  # 'a, b, c'
"um dois três".split()      # ['um', 'dois', 'três']

# Limpeza
"   espaços   ".strip()     # 'espaços'
"xxxOláxxx".strip('x')      # 'Olá'

# Preenchimento
"42".zfill(5)              # '00042'
```

---

```ad-example

#### **Operações com Strings**
```

---
#### **Concatenação**

```python
nome = "João" + " " + "Silva"  # "João Silva"
```

---
#### **Repetição**

```python
risos = "ha" * 3  # "hahaha"
```

---
#### **Acesso a caracteres**

```python
s = "Python"
primeiro_char = s[0]  # 'P'
ultimo_char = s[-1]   # 'n'
```

---
#### **Fatiamento (slicing)**

```python
s = "Python"
s[1:4]    # 'yth' (do índice 1 até 3)
s[:3]     # 'Pyt' (do início até 2)
s[3:]     # 'hon' (do 3 até o fim)
s[::2]    # 'Pto' (pulando de 2 em 2)
s[::-1]   # 'nohtyP' (inverte a string)
```

---
#### **Strings Brutas (raw strings)**

>[!quote] Ignoram caracteres de escape:

```python
r"C:\novo\diretorio"  # não interpreta \n como newline
```

---
#### **Imutabilidade**

>[!quote] Strings são imutáveis em Python:

```python
s = "hello"
s[0] = "H"  # TypeError
# Solução:
s = "H" + s[1:]
```

---
#### **Strings vs Bytes**

```python
# String Unicode
"olá"

# Bytes (dados brutos)
b"ol\xc3\xa1"
```

---
#### **Métodos Adicionais Úteis**

```python
"python".count("p")      # 1
"banana".index("a")     # 1
"123".zfill(5)          # '00123'
"Python".swapcase()     # 'pYTHON'
```

---
#### **Considerações de Performance**

>[!quote] Para concatenação de muitas strings, é mais eficiente usar, do que concatenação repetida com `+`.

```python
"".join(lista_de_strings)
```

---
#### **Unicode e Caracteres Especiais**

```python
# Caracteres Unicode
print("π ≈ 3.14159")       # π ≈ 3.14159
print("★ Avaliação")       # ★ Avaliação

# Emojis
print("Python é \U0001F60E")  # Python é 😎

# Codificação/Decodificação
"café".encode('utf-8')     # b'caf\xc3\xa9'
b'caf\xc3\xa9'.decode()    # 'café'
```

---
#### ⚠️ **Cuidados Importantes**

>[!quote] **Imutabilidade**: Strings não podem ser alteradas após criação

```python
   s = "hello"
   s[0] = "H"  # ❌ TypeError
   s = "H" + s[1:]  # ✅ Solução
```

>[!quote] **Concatenação eficiente** para muitas strings:

```python
   # Ruim: cria múltiplos objetos temporários
   resultado = ""
   for s in lista:
       resultado += s
   
   # Bom: mais eficiente
   resultado = "".join(lista)
```

---
