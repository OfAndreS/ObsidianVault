---
banner: "![[Pasted image 20251215191705.png]]"
banner-x: 50
banner-y: 40
---

---

```ad-quote
title: **Def**

Em Python, **output variables** (variáveis de saída) referem-se ao uso de variáveis para exibir ou retornar dados em um programa. Isso inclui:  

**Exibição de valores no console**
-  (com `print()`).
  
**Retorno de valores em funções**
-  (com `return`).
  
**Formatação de strings para saída estruturada**
-  (f-strings, `.format()`).
  
**Redirecionamento de saída**
-  (para arquivos ou outros dispositivos).  
```

---
#### **1. Exibindo Variáveis com `print()`**  

>[!quote] A função `print()` é a principal maneira de gerar saída em Python.  
##### *Exemplo Básico*

```python
nome = "João"  
idade = 25  

print(nome)                # Saída: João  
print(idade)               # Saída: 25  
print("Nome:", nome)       # Saída: Nome: João  
```
##### *Múltiplas Variáveis em um Único `print()`*

```python
print(nome, idade)                  # Saída: João 25  
print(nome, idade, sep=" - ")       # Saída: João - 25  
print(nome, end=" ")                # Evita quebra de linha  
print(idade)                        # Saída: João 25  
```

---
#### **2. Retornando Variáveis em Funções (`return`)**  

>[!quote] Se uma função precisa "devolver" um valor, usamos `return`.  
##### *Exemplo com `return`*

```python
def calcular_idade(ano_nascimento):  
    return 2024 - ano_nascimento  

idade = calcular_idade(1990)  
print(idade)  # Saída: 34  
```
##### *Retornando Múltiplos Valores*

```python

#Python permite retornar tuplas, listas ou dicionários:  

def dados_pessoa():  
    return "Maria", 30, 1.65  # Tupla implícita  

nome, idade, altura = dados_pessoa()  
print(nome, idade, altura)  # Saída: Maria 30 1.65  
```

---
#### **3. Formatação de Saída (f-strings, `.format()`, `%`)**  

##### *f-strings (Python 3.6+)*

```python
nome = "Carlos"  
saldo = 1500.50  

print(f"{nome} tem R$ {saldo:.2f}")  # Saída: Carlos tem R$ 1500.50  
```
##### *Método `.format()`*

```python
print("{} tem {} anos".format(nome, idade))  # Saída: Carlos tem 30 anos  
```
##### *Formatação com `%` (Legado)*

```python
print("Nome: %s, Idade: %d" % (nome, idade))  # Saída: Nome: Carlos, Idade: 30  
```

---
#### **4. Redirecionando Saída para um Arquivo**  

```ad-quote
title: **Def**

Podemos salvar a saída em um arquivo em vez do console:  
- Isso criará um arquivo `saida.txt` com o texto.  
```

```python
with open("saida.txt", "w") as arquivo:  
    print("Dados salvos!", file=arquivo)  
```

---
#### **5. Capturando Saída em uma Variável (`StringIO`)**  

```ad-quote
title: **Def**

Se precisarmos armazenar a saída de `print()` em uma variável:  
```

```python
from io import StringIO  
import sys  

buffer = StringIO()  
sys.stdout = buffer  # Redireciona a saída padrão  

print("Isso vai para o buffer!")  
sys.stdout = sys.__stdout__  # Restaura a saída padrão  

conteudo = buffer.getvalue()  
print("Conteúdo capturado:", conteudo)  
```

---
#### **6. Supressão de Saída (`_` em Interpretadores Interativos)**  

```ad-quote
title: **Def**

Em ambientes como Jupyter ou Python REPL, `_` armazena o último valor impresso:  
```

```python
>>> 5 + 5  
10  
>>> resultado = _  
>>> print(resultado)  
10  
```

---
#### **7. Saída Personalizada com `__str__` e `__repr__`**  

```ad-quote
title: **Def**

Podemos definir como um objeto é exibido usando:  

- `__str__`: Saída legível para humanos.  
- `__repr__`: Saída técnica (usada em debugging).  
```

```python
class Pessoa:  
    def __init__(self, nome, idade):  
        self.nome = nome  
        self.idade = idade  

    def __str__(self):  
        return f"{self.nome} ({self.idade} anos)"  

    def __repr__(self):  
        return f"Pessoa('{self.nome}', {self.idade})"  

p = Pessoa("Ana", 28)  
print(p)          # Saída: Ana (28 anos)  
print(repr(p))    # Saída: Pessoa('Ana', 28)  
```

---
