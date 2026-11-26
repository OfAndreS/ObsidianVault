
---
#### **Operadores Aritméticos**

>[!quote] **Def**
>
>Os operadores aritméticos em Python são usados para realizar cálculos matemáticos básicos, como adição, subtração, multiplicação, divisão, exponenciação e módulo (resto da divisão).
>
>**Operadores Aritméticos:**
>
>**- `+` Adição**
>  
>---
>**- `-` Subtração**
>
>---
>**- `*` Multiplicação**
>  
>---
>**- `//` Divisão Inteira**
>
>---
>**- `/` Divisão**
>  
>---
>**- `%` Módulo - resto da divisão**
>
>---
>**-** `**` **Exponenciação**
###### _**Exemplo:**_

```python
a = 10
b = 3
print(a + b)   # 13
print(a - b)   # 7
print(a * b)   # 30
print(a / b)   # 3.333...
print(a // b)  # 3
print(a % b)   # 1
print(a ** b)  # 1000
```

---
#### **Operadores Relacionais**

> [!quote] **Def**
> 
> Os operadores relacionais são usados para comparar dois valores ou expressões. Eles retornam um valor booleano (`true` ou `false`) com base na comparação realizada. Esses operadores são frequentemente usados em estruturas condicionais, como `if` e `while`.
>
>**Operadores Relacionais:**
>
>- `==` **Igual a**
>
>---
>  
>- `!=` **Diferente de**
>
>---
>
>- `>` **Maior que**
>
>---
>  
>- `<` **Menor que**
>
>---
>  
>- `>=` **Maior ou igual a**
>
>---
>  
>- `<=` **Menor ou igual a**
###### _**Exemplo:**_

```python
x = 5
y = 10
print(x == y)  # False
print(x != y)  # True
print(x > y)   # False
print(x < y)   # True
print(x >= y)  # False
print(x <= y)  # True
```

---
#### **Operadores Lógicos**

> [!quote] **Def**
> 
> Os operadores lógicos combinam ou invertem expressões booleanas. São usados para criar condições complexas.
>
>**Operadores Lógicos:**
>
>- `and` **E lógico** - Retorna `true` se ambas as expressões forem verdadeiras.
>  
>---
>
>- `or` **OU lógico** - Retorna `true` se pelo menos uma das expressões for verdadeira.
>  
>---
>
>- `not` **NÃO lógico**- Inverte o valor booleano (de `true` para `false` e vice-versa).
###### _**Exemplo:**_

```python
a = True
b = False
print(a and b)  # False
print(a or b)   # True
print(not a)    # False
print(not b)    # True
```

---
#### **Operador Ternário**

> [!quote] **Def**
> 
> O operador ternário permite escrever uma condição em uma única linha. Sintaxe:  
> `valor_se_verdadeiro if condicao else valor_se_falso`
###### _**Exemplo:**_

```python
idade = 18
status = "Adulto" if idade >= 18 else "Menor de idade"
print(status)  # Saída: Adulto
```

---
#### **Operadores de Identidade**

> [!quote] **Def**
> 
> Verificam se dois objetos ocupam a mesma posição na memória.
> **Operadores de Identidade:**
> 
> - `is` **True se for o mesmo objeto**
>
>---
> - `is not` **True se não for o mesmo objeto**
###### _**Exemplo:**_

```python
a = [1, 2]
b = a
c = [1, 2]
print(a is b)      # True
print(a is c)      # False (objetos diferentes)
print(a == c)      # True (valores iguais)
```

---
#### **Operadores de Associação**

> [!quote] **Def**
> 
> Verificam se um valor está presente em uma sequência (lista, tupla, string, etc.).
> **Operadores de Associação:**
> 
> - `in` **True se o valor existe na sequência**
>   
>---
> - `not in` **True se o valor não existe na sequência**
###### _**Exemplo:**_

```python
lista = [1, 2, 3]
print(2 in lista)     # True
print(4 not in lista) # True
```

---

