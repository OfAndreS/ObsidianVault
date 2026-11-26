
---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify">Dicionários são estruturas de dados fundamentais em Python que armazenam informações como pares de chave-valor, oferecendo um mecanismo extremamente eficiente para busca e manipulação de dados.</p>
```

```ad-quote
title:
<p align="justify"><b>Link:</b> <a href="[https://www.w3schools.com/python/python_dictionaries.asp](https://www.w3schools.com/python/python_dictionaries.asp)">Python Dictionaries</a></p>
```
````

---

> [!example] **_New_**

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

|índice     |  Boa prática   |
| --- | --- |
|   1 ) |   Use chaves descritivas e consistentes.  |
|   2 ) |  Prefira .get() para acesso seguro a valores.   |
|   3 ) |  Use dicionários aninhados com moderação   |
|   4 ) |  Para dados imutáveis, considere types.MappingProxyType para criar dicionários somente leitura.   |


```

```ad-quote
title:
**Limitações e Alternativas**

```

```ad-quote
title:

|Condição     | Alternativa    |
| --- | --- |
| Ordenação    |  Antes do Python 3.7, use collections.OrderedDict   |
| Chaves imutáveis    | Se precisar de chaves mutáveis, considere transformar em tuplas    |
| Para dados estruturados   | Considere dataclasses ou namedtuple    |


```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Fundamentos dos Dicionários

```ad-quote
title:
**Definição e Características:**
```

```ad-quote
title:

| Definição    | Explicação     |
| --- | --- |
| É uma coleção Não ordenada    | Mantém ordem de inserção após py 3.7 |
| Mutável    | Pode ser alterado após criação    |
| Indexada por chaves    | Não por índices numéricos    |
| Chaves únicas e imutáveis | nNo podem sofrer alteração após a definição|


```


```ad-quote
title:
<p align="justify"><b>Estrutura Básica:</b></p>
```

```python
dicionario = {
    chave1: valor1,
    chave2: valor2,
    ...
}
```

```ad-quote
title:
<p align="justify"><b>Exemplo:</b></p>
```

```python
cliente = {
    "id": 1425,
    "nome": "Ana Silva",
    "email": "ana@exemplo.com",
    "ativo": True,
    "pedidos": [1254, 1258, 1262]
}
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Criação de Dicionários

```ad-quote
title:
**Tipos de Chaves e Valores:**
```


```ad-quote
title:

| Definição    | Explicação    |
| --- | --- |
| Chaves    | Strings (mais comum), Números (int, float), Tuplas (desde que contenham apenas tipos imutáveis), Booleanos (cuidado com colisões True/1 e False/0)    |
| Valores    | Qualquer tipo de objeto Python, incluindo listas, outros dicionários, funções, etc    |

  
```

```ad-quote
title:
<p align="justify"><b>Métodos de Criação:</b></p>
```

```python
# Método literal (mais comum)
d1 = {"a": 1, "b": 2, "c": 3}

# Usando o construtor dict()
d2 = dict(a=1, b=2, c=3)  # Chaves viram strings automaticamente

# A partir de sequências
d3 = dict([("a", 1), ("b", 2), ("c", 3)])  # Lista de tuplas
d4 = dict(zip(["a", "b", "c"], [1, 2, 3])) # Usando zip()

# Compreensão de dicionário
d5 = {x: x**2 for x in range(1, 6)}  # {1:1, 2:4, 3:9, 4:16, 5:25}
```

```ad-quote
title:
<p align="justify"><b>Exemplo Avançado - Dicionário Aninhado:</b></p>
```

```python
estoque = {
    1001: {"produto": "Notebook", "preco": 3500.00, "qtd": 42},
    1002: {"produto": "Mouse", "preco": 85.90, "qtd": 127},
    1003: {"produto": "Teclado", "preco": 120.00, "qtd": 58}
}
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Operações Básicas

```ad-quote
title:
Dicionários em Python permitem armazenar dados como pares chave-valor, com operações básicas incluindo acesso (via colchetes ou `get()`), modificação (atribuição direta ou `update()`) e remoção (`del`, `pop()`, `clear()`). O acesso seguro com `get()` evita erros para chaves inexistentes, enquanto métodos como `popitem()` e `update()` oferecem funcionalidades avançadas. Essas operações são eficientes (O(1) em média) e flexíveis, tornando dicionários ideais para estruturas de dados não ordenadas (antes do Python 3.7) ou ordenadas por inserção (versões recentes).
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Acesso a Elementos: Acesso Direto
```

```ad-quote
title:

Acesso direto usando chave entre colchetes. Se a chave não existir, levanta KeyError. Ideal quando tem certeza da existência da chave.
```

```python
print(cliente["nome"])  # Imprime: Ana Silva
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Acesso a Elementos: Método get() - Forma Segura
```

```ad-quote
title:
Método mais seguro para acesso que permite especificar um valor padrão para chaves inexistentes, não interrompendo a execução do programa.
```

```python
print(cliente.get("email"))            
# ana@exemplo.com (retorna valor se existir)

print(cliente.get("telefone"))         
# None (não causa erro, retorna None padrão)

print(cliente.get("telefone", "Não cadastrado"))  
# Retorna "Não cadastrado" se chave não existir
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Acesso a Elementos: Dicionários Aninhados
```

```ad-quote
title:
Acesso a valores em estruturas aninhadas, podendo combinar acesso direto e get().
```

```python
print(estoque[1001]["preco"])  # 3500.00
print(estoque.get(1001, {}).get("preco", 0.0))
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) Modificação e Adição
```

```ad-quote
title:
Para modificar, basta atribuir um novo valor a uma chave existente. Se a chave não existir, um novo par chave-valor será criado.
```

```python
# Modificação Simples
cliente["email"] = "ana.silva@novoemail.com"

# Adição de Novos Elementos
cliente["telefone"] = "(11) 98765-4321"
```
````

````ad-quote
title:
```ad-quote
title:
###### E ) Atualização em Massa com update()
```

```ad-quote
title:
Atualiza múltiplos valores de uma vez, recebendo outro dicionário ou pares chave-valor. Chaves existentes são atualizadas e novas chaves são adicionadas.
```

```python
cliente.update({
    "endereco": "Rua das Flores, 123",
    "cidade": "São Paulo"
})
```
````

````ad-quote
title:
```ad-quote
title:
###### F ) Remoção com del e pop()
```

```ad-quote
title:
del: Remove a chave e seu valor. Levanta KeyError se a chave não existir.
pop(): Remove a chave e retorna seu valor, permitindo especificar um valor padrão para chaves inexistentes.
```

```python
# Comando del
del cliente["cidade"]  # Remove permanentemente a chave "cidade"

# Método pop()
telefone = cliente.pop("telefone")  # Remove e retorna o valor
telefone = cliente.pop("telefone", "N/A")  # Com valor padrão
```
````

````ad-quote
title:
```ad-quote
title:
###### G ) Remoção com popitem() e clear()
```

```ad-quote
title:
popitem(): Remove e retorna o último par (chave, valor) inserido (Python 3.7+), útil para processar itens em ordem inversa (LIFO).
clear(): Esvazia completamente o dicionário, removendo todos os seus elementos.
```

```python
# Método popitem()
chave, valor = cliente.popitem()

# Limpeza Total com clear()
cliente.clear()
print(cliente)   # {}
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Métodos Principais

```ad-quote
title:
<p align="justify"><b>Exploração do Dicionário:</b></p>
```

```python
# Chaves
print(cliente.keys())  # dict_keys(['id', 'nome', 'email', ...])

# Valores
print(cliente.values())  # dict_values([1425, 'Ana Silva', ...])

# Itens (pares chave-valor)
print(cliente.items())  # dict_items([('id', 1425), ('nome', 'Ana Silva'), ...])

# Comprimento
print(len(cliente))  # Número de pares chave-valor
```

```ad-quote
title:
<p align="justify"><b>Cópia de Dicionários:</b></p>
```

```python
# Cópia superficial
copia = cliente.copy()

# Cópia profunda (para dicionários aninhados)
import copy
copia_profunda = copy.deepcopy(estoque)
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Iteração em Dicionários

```ad-quote
title:
<p align="justify"><b>Loops Básicos:</b></p>
```

```python
# Pelas chaves (padrão)
for chave in cliente:
    print(f"{chave}: {cliente[chave]}")

# Pelos itens (mais eficiente)
for chave, valor in cliente.items():
    print(f"{chave}: {valor}")

# Pelos valores (quando não precisamos das chaves)
for valor in cliente.values():
    print(valor)
```

```ad-quote
title:
<p align="justify"><b>Ordenação:</b></p>
```

```python
# Ordenar pelas chaves
for chave in sorted(cliente.keys()):
    print(chave, cliente[chave])

# Ordenar pelos valores
for chave in sorted(cliente, key=cliente.get):
    print(chave, cliente[chave])
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Técnicas Avançadas

```ad-quote
title:
**Dicionários Aninhados**
```

```ad-quote
title:
Permitem criar estruturas de dados complexas, como JSON. O acesso a valores aninhados pode ser encadeado.
```

```python
empresa = {
    "departamentos": {
        "vendas": {
            "gerente": "Carlos",
            "funcionarios": 12,
            "meta": 150000.00
        },
        "ti": {
            "gerente": "Mariana",
            "funcionarios": 8,
            "projetos": ["ERP", "Site", "App"]
        }
    }
}

# Acesso seguro a valores aninhados
print(empresa.get("departamentos", {}).get("vendas", {}).get("meta"))
```

```ad-quote
title:
**DefaultDict**
```

```ad-quote
title:
Útil para valores padrão automáticos. Ao tentar acessar uma chave inexistente, ele cria a chave com um valor padrão definido, evitando KeyErrors.
```

```python
from collections import defaultdict

# Contagem de palavras
texto = "o rato roeu a roupa do rei de roma"
contador = defaultdict(int)  # Valor padrão 0 para int

for palavra in texto.split():
    contador[palavra] += 1

print(dict(contador))
```

```ad-quote
title:
**Counter**
```

```ad-quote
title:
Uma subclasse de dicionário especializada para contagens eficientes de objetos "hasheáveis".
```

```python
from collections import Counter

palavras = texto.split()
contador = Counter(palavras)
print(contador.most_common(3))  # 3 palavras mais frequentes
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **08 )** - Performance e Casos de Uso

```ad-quote
title:

| Caso    | Avaliação    |
| --- | --- |
|  Busca por chave   | O(1) - extremamente eficiente   |
|  Inserção/Remoção   | O(1) em média    |
|  Memória   | Mais consumo que listas devido à estrutura de hash table.    |


```

```ad-quote
title:
**Configurações de Aplicação**
```

```python
config = {
    "database": {
        "host": "localhost",
        "port": 5432,
        "user": "admin",
        "password": "secret"
    },
    "logging": {
        "level": "DEBUG",
        "file": "app.log"
    }
}
```

```ad-quote
title:
**Cache Simples**
```

```python
cache = {}

def get_data(key):
    if key not in cache:
        # Simula busca demorada
        print(f"Buscando {key}...")
        cache[key] = f"Dados para {key}"
    return cache[key]
```

```ad-quote
title:
**Transformação de Dados**
```

```python
# Transformação de lista para dicionário
pessoas = [
    {"id": 1, "nome": "João"},
    {"id": 2, "nome": "Maria"},
    {"id": 3, "nome": "Carlos"}
]

pessoas_por_id = {pessoa["id"]: pessoa for pessoa in pessoas}
```
````

---

````ad-example
title:
#### **Py Dicts** - Funções e Métodos de Dicionários
````

---

````ad-quote
title:
```ad-quote
title:
Em Python, a manipulação de dicionários é realizada através de dois mecanismos principais: os Métodos de Dicionário, que são funções pertencentes ao próprio objeto do dicionário e são chamados com a sintaxe `meu_dict.metodo()`, e as Funções Nativas (built-in), que são funções gerais da linguagem que recebem o dicionário como um argumento, utilizando a sintaxe `funcao(meu_dict)`. A principal diferença é que as operações são baseadas em pares de chave-valor em vez de uma sequência ordenada de itens.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 01 ) - Métodos de Dicionário: Acesso e Visualização

```ad-quote
title:
Métodos para recuperar e visualizar dados do dicionário de forma segura.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `get()` | Retorna o valor associado a uma chave. Se não existir, retorna valor padrão. | `valor = dicionario.get("chave", "padrao")` |
| `keys()` | Retorna uma visão de todas as chaves do dicionário. | `chaves = dicionario.keys()` |
| `values()` | Retorna uma visão de todos os valores do dicionário. | `valores = dicionario.values()` |
| `items()` | Retorna uma visão de todos os pares (chave, valor) como tuplas. | `itens = dicionario.items()` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 02 ) - Métodos de Dicionário: Adição e Atualização

```ad-quote
title:
Métodos para modificar o dicionário adicionando ou atualizando elementos.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `update()` | Atualiza o dicionário com pares chave-valor de outro dicionário ou iterável. | `dicionario.update({"chave": "valor"})` |
| `setdefault()` | Retorna o valor se a chave existir. Caso contrário, insere a chave com valor padrão. | `valor = dicionario.setdefault("chave", "padrao")` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 03 ) - Métodos de Dicionário: Remoção

```ad-quote
title:
Métodos para remover elementos do dicionário, alguns retornando os valores removidos.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `pop()` | Remove uma chave específica e retorna seu valor. Pode especificar valor padrão. | `valor = dicionario.pop("chave", "padrao")` |
| `popitem()` | Remove e retorna o último par (chave, valor) inserido (Python 3.7+). | `chave, valor = dicionario.popitem()` |
| `clear()` | Remove todos os itens do dicionário, deixando-o vazio. | `dicionario.clear()` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 04 ) - Métodos de Dicionário: Outros Métodos

```ad-quote
title:
Métodos adicionais para cópia e criação de dicionários.
```

```ad-quote
title:
| Método | Descrição | Exemplo de Uso |
|---|---|---|
| `copy()` | Retorna uma cópia rasa (shallow copy) do dicionário. | `copia = dicionario.copy()` |
| `fromkeys()` | Cria novo dicionário com chaves de um iterável e mesmo valor para todas. | `novo = dict.fromkeys(["a", "b"], 0)` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 05 ) - Funções Nativas: Análise e Criação

```ad-quote
title:
Funções gerais do Python que podem ser usadas com dicionários, operando principalmente sobre as chaves.
```

```ad-quote
title:
| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `len()` | Retorna o número de pares chave-valor no dicionário. | `tamanho = len(dicionario)` |
| `dict()` | Cria um novo dicionário a partir de um iterável de pares chave-valor. | `novo = dict([("a", 1), ("b", 2)])` |
| `sorted()` | Retorna uma nova lista com as chaves do dicionário ordenadas. | `ordenadas = sorted(dicionario)` |
| `max()` | Retorna a maior chave do dicionário. | `maior = max(dicionario)` |
| `min()` | Retorna a menor chave do dicionário. | `menor = min(dicionario)` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 06 ) - Funções Nativas: Verificação Lógica e Matemática

```ad-quote
title:
Funções que avaliam elementos ou realizam operações matemáticas com os valores do dicionário.
```

```ad-quote
title:
| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `any()` | Retorna True se pelo menos uma chave for verdadeira. | `resultado = any(dicionario)` |
| `all()` | Retorna True se todas as chaves forem verdadeiras. | `resultado = all(dicionario)` |
| `sum()` | Soma todos os valores do dicionário (se forem numéricos). | `total = sum(dicionario.values())` |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:
##### 07 ) - Classes do Módulo collections

```ad-quote
title:
Subclasses especializadas de dicionários para funcionalidades avançadas.
```

```ad-quote
title:
| Classe | Descrição | Exemplo de Uso |
|---|---|---|
| `defaultdict` | Fornece valor padrão para chaves inexistentes. | `d = defaultdict(int); d["nova"] += 1` |
| `Counter` | Especializada para contar objetos hasheáveis. | `c = Counter(['a', 'b', 'a'])` |
| `OrderedDict` | Mantém a ordem de inserção dos itens (com métodos adicionais). | `d = OrderedDict(); d["a"] = 1` |
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
<p align="justify">Dicionários são uma das estruturas mais versáteis e poderosas do Python, essenciais para programação eficiente e legível. Seu domínio é fundamental para qualquer desenvolvedor Python.</p>
```
````

---