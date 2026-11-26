
---

```ad-quote
title: **Def**

Em Python, variáveis são referências a valores armazenados na memória. Diferente de linguagens de baixo nível

Python utiliza:
- **Tipagem dinâmica** 
- **Inferência de tipos**
  
Tornando a sintaxe mais simples e expressiva.  
```

>[!quote] **Link:** [Python Variables](https://www.w3schools.com/python/python_variables.asp)
>

---
#### **Declaração e Atribuição**  

>[!quote] Uma variável simplesmente atribuindo um valor a um identificador:  

```python
# Tipos básicos
nome = "Ana"            # str (string)  
idade = 30              # int (inteiro)  
altura = 1.68           # float (ponto flutuante)  
tem_cartao = True       # bool (booleano)  

# Coleções  
numeros = [1, 2, 3]     # list (lista mutável)  
coordenadas = (4, 5)     # tuple (tupla imutável)  
dados = {"nome": "Ana", "idade": 30}  # dict (dicionário)  
```

---
#### **Inferência de Tipos e `type()`**  

>[!quote] O tipo da variável automaticamente. Podemos verificar com `type()`:  

```python
print(type(nome))        # <class 'str'>  
print(type(idade))       # <class 'int'>  
print(type(altura))      # <class 'float'>  
```

---
#### **Regras de Nomenclatura**  

```ad-quote
title: **Def**

###### ***Permitido***:  

Letras 
- (`a-z`, `A-Z`)
  
---

Números 
- (`0-9`) & (`_`)

---

Case-sensitive 
- (`idade ≠ Idade ≠ IDADE`) 
```

```python
#Permitido:

nome_completo = "João Silva"  
_valor_total = 100.50  
cliente_ativo = True  
```

```ad-quote
title: **Def**

###### ***Proibido***:
  
Iniciar com número 
- (`1cliente` ❌)

---

Usar espaços 
- (`nome completo` ❌)

---

Palavras reservadas 
- (`if`, `for`, `def` ❌)
  
```

```python
#Proibido:

2myvar = "John"  
my-var = "John"  
my var = "John"
```

---
#### **Convenções de Nomes / PEP 8**  

>[!quote] **`snake_case`** para variáveis e funções:  

```python
  saldo_atual = 1000  
  def calcular_total():  
      ...  
  ```

>[!quote] **`PascalCase`** para classes:  

```python
  class ClientePremium:  
      ...  
  ```

>[!quote] **`UPPER_CASE`** para constantes (por convenção):  

```python
  TAXA_JUROS = 0.05  
  ```

---
#### **Atribuição Múltipla**  

>[!quote] Python permite atribuições compactas:  

```python
# Atribuição em linha  
x, y, z = 1, 2, 3  

# Troca de valores sem variável auxiliar  
a, b = b, a  

# Atribuição em lote  
c = d = e = 0  
```

---
#### **Escopo de Variáveis**  

```ad-quote
title: **Def**

**Variável Global**: 
- Acessível em todo o programa.
  
**Variável Local**: 
- Existe apenas dentro de uma função.
  
```

```python
total = 100  # Variável global  

def atualizar_saldo():  
    global total  # Indica que estamos modificando a variável global  
    total += 50  

atualizar_saldo()  
print(total)  # Saída: 150  
```

---
#### 🛠 **Boas Práticas**  

```ad-quote
title: **Def**

**1 ) - Nomes descritivos**:  

**2 ) - Evitar variáveis globais desnecessárias**.

**3 ) - Constantes em `UPPER_CASE`**

**4 ) - Documentar variáveis complexas**:   
```

>[!quote] **1 )**

```python
- ❌ x = 10
- ✅ quantidade_produtos = 10
```

>[!quote] **3 )**

   ```python
   PI = 3.14159  
   ```

>[!quote] **4 )**

   ```python
   # Armazena coordenadas (latitude, longitude)  
   posicao = (-23.55, -46.63)  
   ```

---
