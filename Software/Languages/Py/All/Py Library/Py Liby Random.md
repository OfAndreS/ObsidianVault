
---
#### **Quando Usar Cada Módulo**

```ad-quote
title: **Def**

**`random`**: 
- Para necessidades gerais onde a segurança não é crítica (jogos, simulações simples)

---

**`secrets`**: 
- Para segurança, autenticação e criptografia

---

**`numpy.random`**: 
- Para computação científica e trabalhar com grandes volumes de dados
  
```

---
#### **Boas Práticas e Advertências**

```ad-quote
title: **Def**

**Não use `random` para segurança**: 
- Para senhas, tokens ou qualquer coisa relacionada a segurança, sempre prefira `secrets`

---

**Performance**: 
- Para gerar grandes quantidades de números, `numpy.random` é muito mais eficiente que `random`

---

**Reprodutibilidade**: 
- Sempre defina uma seed quando precisar de resultados reproduzíveis

---

**Aleatoriedade verdadeira**: 
- Os módulos padrão geram números pseudoaleatórios. Para aleatoriedade verdadeira, você precisaria de hardware especializado ou serviços online
```

---

```ad-example

#### **Módulos para Geração de Números Aleatórios**
```

---
#### 1 ) **Módulo `random` / Pseudoaleatório**

>[!quote] O módulo padrão `random` é adequado para a maioria das necessidades básicas de aleatoriedade:

```python
import random

# Gera um float entre 0.0 e 1.0
numero = random.random()

# Inteiro aleatório entre dois valores (inclusive)
dado = random.randint(1, 6)

# Float aleatório em um intervalo
preco = random.uniform(10.5, 99.9)

# Seleção aleatória de elementos
frutas = ['maçã', 'banana', 'laranja']
sorteio = random.choice(frutas)

# Embaralhamento de listas
baralho = ['Ás', 'Rei', 'Dama', 'Valete']
random.shuffle(baralho)

# Amostra sem repetição
amostra = random.sample(range(100), 5)
```

---
#### 2 ) **Módulo `secrets` / Para segurança**

>[!quote] Recomendado para operações criptográficas e segurança:

```python
import secrets

# Gera um inteiro seguro
token_seguro = secrets.randbelow(1000)

# Cria tokens hexadecimais
token = secrets.token_hex(16)

# Escolha segura
senha = secrets.choice(['python', 'java', 'c++'])
```

---
#### 3 ) **`numpy.random` / Para ciência de dados**

>[!quote] Ideal para trabalhar com arrays numéricos:

```python
import numpy as np

# Array de números aleatórios
numeros = np.random.rand(5)

# Inteiros em um intervalo
dados = np.random.randint(1, 7, size=10)

# Distribuição normal
normal = np.random.normal(0, 1, 100)
```

---
#### **Controlando a Aleatoriedade com Seeds**

>[!quote] Para resultados reproduzíveis:

```python
random.seed(42)       # Configura a seed para random
np.random.seed(42)    # Configura a seed para numpy
```

---
#### **Distribuições Estatísticas Avançadas**

>[!quote] Além da distribuição uniforme, podemos gerar números com outras distribuições:

```python
# Distribuição normal (Gaussiana)
normal = random.gauss(0, 1)

# Distribuição exponencial
exp = random.expovariate(1.0)

# Distribuição triangular
tri = random.triangular(1, 5, 10)
```

---

```ad-example

#### **Aplicações Práticas**
```

---
#### **Gerando Dados Aleatórios Complexos**

```python
# String aleatória
import string
senha = ''.join(random.choices(string.ascii_letters + string.digits, k=12))

# Data aleatória
from datetime import datetime, timedelta
inicio = datetime(2020, 1, 1)
fim = datetime(2023, 1, 1)
dias = (fim - inicio).days
data_aleatoria = inicio + timedelta(days=random.randint(0, dias))
```

---
#### **Exemplo Completo: Simulação de Dados**

```python
import random
from datetime import datetime, timedelta

def gerar_dados_aleatorios(n):
    dados = []
    for _ in range(n):
        # Gera data aleatória no último ano
        inicio = datetime.now() - timedelta(days=365)
        dias = (datetime.now() - inicio).days
        data = inicio + timedelta(days=random.randint(0, dias))
        
        # Gera valores com distribuição normal
        valor = max(0, random.gauss(100, 30))
        
        # Escolhe categoria aleatória
        categorias = ['eletrônicos', 'vestuário', 'alimentos', 'livros']
        categoria = random.choice(categorias)
        
        dados.append({
            'data': data.strftime('%Y-%m-%d'),
            'valor': round(valor, 2),
            'categoria': categoria
        })
    return dados

# Gera 10 registros de exemplo
print(gerar_dados_aleatorios(10))
```

---