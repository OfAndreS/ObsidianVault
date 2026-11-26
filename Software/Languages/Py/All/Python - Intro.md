
---

```ad-example

#### **Definição**
```

---

```ad-quote
title: **Def**

Python é uma linguagem de programação de alto nível, interpretada e multiparadigma, conhecida por sua sintaxe clara e legível. É amplamente utilizada em desenvolvimento web, ciência de dados, inteligência artificial, automação e scripting. Python prioriza a produtividade do desenvolvedor, oferecendo estruturas de dados eficientes e uma abordagem simples mas poderosa para programação orientada a objetos e funcional.
```

---
#### **Importação de Módulos**

```ad-quote
title: **Def**

Módulos / Bibliotecas em Python são arquivos contendo código Python que podem ser reutilizados em outros programas. Eles fornecem funções, classes e variáveis pré-definidas para tarefas comuns. Para usar um módulo, você o importa usando a diretiva `import`.
```

```python
import math           # Para funções matemáticas
from sys import exit  # Para importar uma função específica
```

---
#### **Função Principal (Main)**

```ad-quote
title: **Def**

Em Python, a execução do programa começa no topo do arquivo. Por convenção, usa-se `if __name__ == "__main__":` para definir o bloco principal, garantindo que o código só será executado quando o arquivo for rodado diretamente (não quando importado como módulo).
```

```python
def printHeader():
    print("\n\n| *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *\n\n")

def main():
    printHeader()
    print("Hello, World!")

if __name__ == "__main__":
    main()
```

---
#### **Entrada/Saída (Input/Output)**

```ad-quote
title: **Def**

Python utiliza funções nativas para operações básicas de entrada e saída. A função `input()` captura dados do usuário (como string), enquanto `print()` exibe saídas no console. Diferente de C++, não é necessário incluir bibliotecas para essas operações básicas.
```
###### _**Entrada:**_

```python
nome = input("Digite seu nome: ")  # Entrada (sempre retorna string)
```
###### _**Saída:**_

```python
print("Olá,", nome)  # Saída formatada automaticamente
```

```python
print(f"My name is: {name}. And Yours? ")
```

###### _**Ex:**_

```python

if __name__ == "__main__":
    idade = int(input("Digite sua idade: "))  # Conversão para inteiro
    print(f"Você tem {idade} anos e seu nome é {nome}.")  # f-string (Python 3.6+)
    
```

---

>[!tip] #### **Executar o Python**

---
#### **1 ) Navegue até a pasta do arquivo Python**

>[!quote] Use o comando `cd` para acessar o diretório onde está o seu arquivo `.py`:

```bash
cd caminho/para/a/pasta
```
###### ***Exemplo:***

```bash
cd ~/Documentos/meu_projeto
```

---
#### **2) Execute o arquivo Python**
##### **No Windows:**

>[!quote] Execução padrão

```bash
python nome_do_arquivo.py
```

>[!quote] ou (se você instalou o Python 3):

```bash
py nome_do_arquivo.py
```

---
##### **No Linux/Mac:**

>[!quote] Execução padrão

```bash
python3 nome_do_arquivo.py
```

---
