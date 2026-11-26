
---
#### **Instalação de um Compilador C**

>[!quote] **Def**
>
>Para programar em C, é necessário um compilador que transforme o código-fonte em linguagem de máquina, tornando-o executável. As instruções a seguir guiarão você na instalação de um compilador para os sistemas operacionais Windows, Linux e macOS.
>
>**Windows:**
>
>- **MinGW:** 
>  1. Baixe e instale o MinGW, que inclui o GCC (GNU Compiler Collection), o compilador padrão para C.
>- **Outras opções:** 
>  2. Utilize ambientes como MSYS2 ou IDEs como Code::Blocks, que já vêm com um compilador integrado.

>[!note] **Info C:** [[Info C]]

>[!quote] **RoadMap C: ** [Programming](https://github.com/Koubae/Programming-CookBook/blob/master/Programming%20Languages/C/roadmap.md)

>[!quote] **Compiler:** [C Online Compiler](https://onecompiler.com/c)

>[!quote] **How to install:** [Como configurar](https://www.youtube.com/watch?v=3pfRvy_gfqY)

>[!quote] **Commun Functions:** [[C Commun Functions]]

---
#### **Notação Base**

>[!quote] **Def**
>- Funções e explicações básicas sobre a linguágem
>  

>[!quote] ***Vault:*** [[C Notação Base]]

---
#### **Comum Error**

>[!quote] **Def**
>- Problema no console do VsCode não imprimindo caracteres especiais. 
>  

>[!quote] **Link:** [Corrigindo problemas de caracteres especiais](https://www.youtube.com/watch?v=Zw1KA4u0Fzg)

---

>[!tip] ### **Basic**

---
#### **Data Types I**

>[!quote]
>Em C, os tipos de dados definem o tipo de informação que uma variável pode armazenar e as operações que podem ser realizadas sobre ela. Os tipos básicos incluem:
>
>- **int:** números inteiros 
>- **float:** números de ponto flutuante 
>- **char:** caracteres individuais 

>[!quote] ***Vault:*** [[C Data Types I]]

---
#### **Operators**

>[!quote] **Def**
>**Operadores em C são símbolos especiais que indicam ao compilador para realizar uma determinada operação com um ou mais operandos.** Eles são essenciais para a manipulação de dados e o controle do fluxo de execução de um programa.
>
>- **Aritméticos:** Realizam operações matemáticas como soma, subtração, multiplicação, divisão e módulo.
>- **Relacionais:** Comparam valores e retornam um valor booleano (verdadeiro ou falso).
>- **Lógicos:** Combinam expressões lógicas usando operadores
>- **Bitwise:** Realizam operações bit a bit em números inteiros.

>[!quote] ***Vault:*** [[C Operators]]

---
#### **Control Flow**

>[!quote] **Def**
>**Controle de fluxo em C** refere-se aos mecanismos que permitem alterar a ordem de execução das instruções em um programa. Em vez de seguir uma sequência linear, o programa pode tomar decisões, repetir blocos de código ou saltar para outras partes do código com base em condições específicas.
>
>- **Estruturas condicionais:**  `if`, `else if`, `else` 
>  
>- **Laços de repetição:**  `for`, `while`, `do-while` 
>  
>- **Comandos de salto:** `break`, `continue`, `goto` 

>[!quote] ***Vault:*** [[C Control Flow]]

---
#### **Functions**

>[!quote] **Def**
>**Funções em C** são como pequenos programas dentro de um programa maior. Elas agrupam um conjunto de instruções que realizam uma tarefa específica e podem ser chamadas por outras partes do código quantas vezes forem necessárias. Isso torna o código mais organizado, modular e fácil de manter.
>
>- **Reutilização de código:** Evite repetir o mesmo código 
>- **Modularização:** Divida o programa em partes menores e mais gerenciáveis.
>- **Abstração:** Esconda a complexidade interna de uma tarefa
>- **Organização:** Melhore a legibilidade e a manutenção do código.

>[!quote] ***Vault:*** [[C Functions]]

---

>[!tip] ### **Intermediate**

---
#### **I/O Stream**

>[!quote] **Def**
>I/O Streams em C representam fluxos de dados para entrada (leitura) e saída (escrita).
>
>---
>
> `<stdio.h>` oferece funções para manipular esses fluxos
> - `printf` (saída formatada)
>- `scanf`    (Oferece uma entrada formatada) 
>  
>---
>
>  Além de funções para arquivos como `fopen` e `fclose`. Existem streams padrão como `stdin` (entrada padrão), `stdout` (saída padrão) e `stderr` (erro padrão), além da possibilidade de trabalhar com arquivos. O tratamento adequado de erros e o uso correto dos especificadores de formato são cruciais para um I/O eficiente.

>[!quote] ***Vault:*** [[C IO Stream]]

---
#### **Data Types II**

>[!quote] **Def**
>**Ponteiros:** 
>- Permitem manipular diretamente endereços de memória, incluindo ponteiros para ponteiros (ponteiro duplo) e ponteiros para funções. O qualificador `restrict` otimiza o acesso a ponteiros, evitando aliasing.
>  
>---
>
>**volatile:** 
>- Indica que uma variável pode ser modificada por fatores externos ao programa (ex: hardware), prevenindo otimizações incorretas do compilador.
>  
>---
>
>**Tipos Compostos:** 
>- `struct` agrupa variáveis de tipos diferentes sob um único nome, acessadas por `.` (direto) ou `->` (ponteiro). `union` armazena diferentes tipos no mesmo espaço de memória. `enum` define conjuntos de constantes nomeadas.
>  
>---
>
>**Utilitários:** 
>- `size_t` representa tamanhos de objetos em bytes, enquanto `typedef` cria sinônimos para tipos existentes, melhorando a legibilidade do código.

>[!quote] ***Vault:*** [[C DataType II]]

---
#### **C Standard Library**

>[!quote] **Def**
>A biblioteca padrão do C é um conjunto de funções e macros essenciais fornecidas pela linguagem para realizar tarefas comuns, como manipulação de strings, entrada e saída de dados, alocação de memória e operações matemáticas. Ela é composta por vários cabeçalhos, como `<stdio.h>`, `<stdlib.h>`, `<string.h>`, e `<math.h>`, cada um contendo funcionalidades específicas. Essas bibliotecas são portáveis e garantem que os programas em C possam ser executados em diferentes sistemas com comportamento consistente. Dominar o uso da biblioteca padrão é fundamental para desenvolver programas eficientes e robustos em C.

>[!quote] ***Vault:*** [[C Standard Library]]

---
#### **C Dynamic Memory Allocation**

>[!quote] **Def**
>Em C, o alocamento de memória é fundamental para gerenciar dados durante a execução do programa. Existem dois tipos principais: o alocamento estático, onde a memória é definida em tempo de compilação, e o alocamento dinâmico, que ocorre em tempo de execução, permitindo flexibilidade. Funções como `malloc`, `calloc`, `realloc` são usadas para alocar dinamicamente, e é crucial liberar a memória com `free` quando não for mais necessária para evitar vazamentos. Um gerenciamento cuidadoso da memória é essencial para a eficiência e estabilidade de programas em C.

>[!quote] ***Vault:*** [[C Memory Allocation]]

---

>[!tip] ### **Advanced**

---
#### **Data Structures**

>[!quote] **Def**
>**Data Structures** são formas organizadas de armazenar e gerenciar dados para eficiência em operações. 
>- **Strings:** 
>  São sequências de caracteres
>- **Arrays:** 
>  São coleções de elementos acessados por índices. 
>  
>---
>
>- **Multidimensional Arrays** & **Matrix Arrays:** 
>  São arrays com múltiplas dimensões, usando o **Array Subscript Operator** para acesso. 
>  
> ---
> 
>- **Linked Lists**, **Stacks** e **Queues:** 
>  São estruturas dinâmicas para gerenciar dados com regras específicas de inserção e remoção.

>[!quote] ***Vault:*** [[C Data Structures]]

---
