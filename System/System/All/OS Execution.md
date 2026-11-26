
---
#### **🧩 Multitarefa e Multiprocessos**

```ad-quote
title: **Def**

O sistema operacional pode executar vários processos ao mesmo tempo (multitarefa), mesmo que sejam:

- Do mesmo programa (várias instâncias).
    
- De programas diferentes (Word, Chrome, Spotify).
    

Cada processo é isolado por segurança, estabilidade e controle de recursos.
```

---
#### **🧰 Extras Técnicos**

```ad-quote
title: **Def**


**Thread ≠ Processo**: 
- Um processo pode conter várias **threads** (linhas de execução) compartilhando memória entre si.

---
   
**Fork**: 
- Em sistemas Unix, é comum criar novos processos com o comando `fork()`, que clona um processo pai.

---
   
**Exec**: 
- Também no Unix, `exec()` substitui o código de um processo por outro programa.

---
   
**Zombie Process**: 
- Processo que terminou, mas cujo status ainda não foi coletado pelo sistema.
```

---

```ad-example

#### **O que é um Programa**?
```

---
#### **Definição**

```ad-quote
title: **Def**

Um **programa** é um **conjunto de instruções codificadas** (em uma linguagem como C, Python, Java etc.) que pode ser interpretado ou compilado para ser entendido por um computador.

- Está **armazenado de forma passiva** em algum meio (HD, SSD, pen drive).
    
- É apenas **um arquivo** (por exemplo: `.exe`, `.sh`, `.py`, `.jar`, etc.).
    
- **Não faz nada por conta própria** — é só um plano de ação, aguardando ser colocado em prática.
```
###### ***Exemplo:***

```ad-quote
title: **Def**

- O arquivo `notepad.exe` que está na sua pasta `C:\Windows\System32\`.
    
- Ele é um **programa**, mas enquanto você não der dois cliques nele, nada acontece.
    
```

---
#### **🛠 Estrutura de um programa:**

```ad-quote
title: **Def**
**01 )**
- Código binário (máquina) ou interpretado.
  
**02 )**
- Dados iniciais (constantes, variáveis globais).
  
**03 )**
- Áreas de instruções (como deve ser executado).
  
**04 )**
- Pode conter bibliotecas ou ser dependente de outras.
```

---
#### **💡 Analogia:**

```ad-quote
title: **Def**

Um programa é como um **livro de receitas guardado na estante**. Ele contém todas as instruções para fazer vários pratos, mas nada acontece até alguém pegar e usar.
```

---

```ad-example

#### **O que é um Processo**?
```

---
#### **Definição**

```ad-quote
title: **Def**

Um **processo** é uma: 
- **Instância em execução de um programa**. 
  
É criado quando o sistema operacional carrega um programa da memória secundária (HD, SSD) para a memória principal (RAM) e começa a executá-lo.

- É uma **entidade ativa**.
    
- Tem seu **próprio contexto de execução**.
    
- Pode **interagir com o sistema**, abrir arquivos, acessar dispositivos, se comunicar com outros processos etc.
```

---
#### **🧠 Como o sistema operacional enxerga isso?**

```ad-quote
title: **Def**

Para o sistema operacional, programas são apenas arquivos. Mas processos são entidades complexas. Ao criar um processo, o SO precisa:

**01 )**
- Atribuir um identificador único (PID).

---

**02 )**
- Carregar o código do programa na memória.

---

**03 )**
- Reservar áreas de memória para variáveis, pilha de execução e dados dinâmicos.

---

**04 )**
- Configurar os registradores da CPU para começar a execução.

---

**05 )**
- Monitorar o estado do processo enquanto ele vive.

---

Tudo isso é feito **automaticamente e invisivelmente** toda vez que você executa um programa.
```

>[!quote] ***Vault:*** [[OS Detail of the process]]

---
## 👨‍💻 Código exemplo para ilustrar

```ad-quote
title: **Def**

Vamos pensar em um código Python simples:
```

```python

# programa.py
print("Olá, mundo!")

```

```ad-quote
title: **Def**

Esse arquivo salvo é o **programa**. Ele está no seu disco rígido.

Agora, ao executar:
```

```python

python programa.py

```

```ad-quote
title: **Def**


Você cria um **processo** que:

- Carrega o interpretador Python.
    
- Lê o código do arquivo.
    
- Executa a instrução `print("Olá, mundo!")`.
    
- Usa memória, CPU, termina.
    

Assim que o processo termina, ele libera os recursos que estava usando. Mas o programa (`programa.py`) continua intacto no disco.
```

---
