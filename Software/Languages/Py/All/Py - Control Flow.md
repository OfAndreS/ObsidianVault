
---

>[!tip] ### **Condicionais em Python**

---
#### _**if**_

> [!quote] **Def**  
> **`if`:** Executa um bloco de código **apenas se** uma condição especificada for verdadeira.
###### _**Exemplo:**_

```python
if condição:
    # Código a ser executado se a condição for verdadeira
```

---
#### _**elif (else if)**_

> [!quote] **Def**  
> **`elif`:** Usado em conjunto com `if` para verificar **múltiplas condições** em sequência. Equivalente ao `else if` do C++.
###### _**Exemplo:**_

```python
if condição1:
    # Código se condição1 for verdadeira
elif condição2:
    # Código se condição1 for falsa E condição2 for verdadeira
else:
    # Caso contrário, executa este bloco
```

---
#### _**match-case (Python 3.10+)**_

> [!quote] **Def**  
> **`match-case`:** Similar ao `switch-case` do C++, mas mais poderoso. Compara um valor com padrões (patterns) e executa o bloco correspondente.
###### _**Exemplo:**_

```python
match variável:
    case valor1:
        # Código se variável == valor1
    case valor2:
        # Código se variável == valor2
    case _:  # Default (opcional)
        # Código se nenhum caso anterior for válido
```

```python
status = 404
match status:
    case 200:
        print("Sucesso!")
    case 404:
        print("Não encontrado")
    case _:
        print("Erro desconhecido")
```

---

>[!tip] ### **Loops em Python**

---
#### _**while**_

> [!quote] **Def**  
> **`while`:** Executa um bloco de código **enquanto** uma condição for verdadeira.
###### _**Exemplo:**_

```python
while condição:
    # Código a ser repetido enquanto a condição for verdadeira
```

---
#### _**for (iteração tradicional)**_

> [!quote] **Def**  
> **`for`:** Itera sobre uma sequência (lista, tupla, string, etc.) ou objeto iterável. Não usa inicialização/condição/incremento como em C++.
###### _**Exemplo:**_

```python
for item in sequência:
    # Código a ser executado para cada item da sequência
```

---
#### _**for com range()**_

> [!quote] **Def**  
> **`range()`:** Usado para gerar uma sequência numérica, frequentemente em loops `for` para repetições controladas.
###### _**Exemplo:**_

```python
for i in range(início, fim, passo):
    # Código a ser repetido (i assume valores do intervalo)
```

```python
for i in range(5):  # 0 a 4
    print(i)
```

---
#### _**for-else**_

> [!quote] **Def**  
> **`for-else`:** O bloco `else` é executado **após o loop** `for`, mas **apenas se o loop não for interrompido por `break`**.
###### _**Exemplo:**_

```python
for item in sequência:
    if condição:
        break
else:
    # Executado se o loop terminar normalmente (sem break)
```

---
#### _**Compreensões de Lista (for inline)**_

> [!quote] **Def**  
> **`List Comprehension`:** Sintaxe concisa para criar listas baseadas em loops `for` e condicionais.
###### _**Exemplo:**_

```python
nova_lista = [expressão for item in sequência if condição]
```

```python
pares = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
```

---
