---
banner: "![[Pasted image 20251221172857.png]]"
banner-x: 48
banner-y: 42
---

---

![[🔍 Search.base#Leng - C++]]

---
#### **Instalação de um Compilador C++**

>[!quote] **Def**
>
>Para programar em C, é necessário um compilador que transforme o código-fonte em linguagem de máquina, tornando-o executável. As instruções a seguir guiarão você na instalação de um compilador para os sistemas operacionais Windows, Linux e macOS.
>
>**Windows:**
>
>- **MinGW:** 
>  1. Baixe e instale o MinGW, que inclui o GCC (GNU Compiler Collection), o compilador padrão para C.
>- **Outras opções:** 
>  1. Utilize ambientes como MSYS2 ou IDEs como Code::Blocks, que já vêm com um compilador integrado.

>[!quote] **How to install:** [Como configurar](https://www.youtube.com/watch?v=3pfRvy_gfqY)

>[!quote] **Online Compiler:** [C Online Compiler](https://onecompiler.com/c)

>[!quote] **The RoadMap C: ** [C++ Developer Roadmap](https://roadmap.sh/cpp)

---
#### **Introdução ao C++**

>[!quote] **Def:**
>C++ é uma linguagem de programação poderosa e de alto desempenho que estende a linguagem C com recursos de programação orientada a objetos. É amplamente utilizada para desenvolvimento de sistemas/software, desenvolvimento de jogos e simulações em tempo real. O C++ permite tanto a manipulação de memória de baixo nível quanto abstrações de alto nível, tornando-a versátil para diversas aplicações.

>[!quote] **Vault:** [[C++ Introdução]]

>[!quote] **Vault:** [[C++ Compilação]]

>[!quote] **Vault:** [[C++ Commun Functions]]

---
#### **C++ Organização de Código**

>[!quote] **Def**
>A organização de código em C++ envolve a separação clara entre interface (arquivos `.hpp`) e implementação (arquivos `.cpp`), uso de namespaces para evitar conflitos, modularização em componentes lógicos e boas práticas como `#pragma once` ou include guards para evitar inclusões redundantes. Ferramentas como Makefiles ou CMake ajudam a gerenciar a compilação, enquanto técnicas como encapsulamento, funções `inline` e `extern` para variáveis globais contribuem para a eficiência e manutenibilidade do código.

>[!quote] **Vault:** [[C++ Organização de Código]]

---

>[!example] ### **C++ Library**

---
#### **C++ Standard Library STL**

>[!quote] **Def:**
>A **C++ STL** é uma biblioteca poderosa que faz parte da biblioteca padrão do C++, oferecendo um conjunto rico de modelos (templates) para estruturas de dados e algoritmos genéricos.
>
>É composta principalmente por
> 
>**Containers:**
>- Modelos para organizar dados (como vetores, listas, mapas)
>
>---
>  
>**Algorithms:** 
>- que são funções para realizar operações nesses dados (como ordenar, buscar, transformar)
>
>---
>  
>**Iterators:**
>- Fornece uma maneira de acessar os elementos dos containers de forma uniforme.

>[!quote] **Vault:** [[C++ Standard Library STD]]

---
#### **Build My Library**

>[!quote] **Def**

>[!quote] **Vault:** [[C++ Build My Library]]

---

>[!tip] ### **Basic Operations C++**

---
#### **Operadores**

>[!quote] **Def:**
>**Aritméticos:** 
>- Incluem `+`, `-`, `*`, `/`, `%` para operações matemáticas básicas como soma, subtração, multiplicação, divisão e resto. Permitem realizar cálculos numéricos em programas.
>  
>---
>**Relacionais:** 
>- Operadores como `>`, `<`, `==`, `!=`, `>=`, `<=` comparam valores. O resultado destas comparações é sempre um valor booleano: `verdadeiro` (true) ou `falso` (false).
>  
>---
>
>**Lógicos:** 
>  - `&&` (E lógico), `||` (OU lógico), `!` (NÃO lógico) combinam expressões booleanas. Usados para construir condições mais complexas e tomar decisões lógicas no código.

>[!quote] **Vault:** [[C++ Basic Operations]]

---
#### **Control Flow**

>[!quote] **Def**
>O controle de fluxo em C++ define a ordem de execução das instruções do programa. Por padrão, o código executa de forma sequencial, linha por linha. Para alterar essa ordem, usamos estruturas como `if`, `else`, `switch` para decisões, e `for`, `while`, `do-while` para repetições (loops). Essas ferramentas permitem criar programas dinâmicos e que reagem a diferentes condições.

>[!quote] **Vault:** [[C++ Control Flow]]

---
#### **Modificadores**

>[!quote] **Def**
>Em C++, os **modificadores** são palavras-chave que alteram o comportamento de tipos de dados, variáveis, funções ou classes. Eles permitem controlar aspectos como visibilidade, duração de armazenamento, mutabilidade e outras propriedades. Abaixo está uma visão geral dos principais modificadores em C++:

>[!quote] **Vault:** [[C++ Modificadores]]

---

>[!tip] ### **DataType C++**

---
#### **DataType I**

>[!quote] **Def**
>Em C, os tipos de dados definem o tipo de informação que uma variável pode armazenar e as operações que podem ser realizadas sobre ela. Os tipos básicos incluem:
>
>- **int:** números inteiros 
>- **float:** números de ponto flutuante 
>- **char:** caracteres individuais 
>- **bool: ** verdadeiro ou falso

>[!quote] **Vault:** [[C++ DataType I]]

---
#### **DataType II**

>[!quote] **Def**
>DataType II em C++ refere-se a tipos de dados mais complexos e definidos pelo utilizador, para além dos tipos de dados básicos (como `int`, `float`, `char`).
>
>Inclui `struct` e `class`, que permitem agrupar variáveis de diferentes tipos sob um único nome, criando estruturas de dados personalizadas.
>
>Ponteiros e arrays também se enquadram nesta categoria, oferecendo mecanismos para gerir memória e coleções de dados de forma mais flexível.

>[!quote] **Vault:** [[C++ DataType II]]

---
#### **Templates**

>[!quote] **Def**
>código que pode ser reutilizado com diferentes tipos de dados. Eles são uma forma de programação genérica que permite que você defina funções ou classes que operam com tipos de dados genéricos, sem precisar especificar o tipo exato até o momento do uso.

>[!quote] **Vault:** [[C++ Templates]]

---

>[!tip] ### **C++ I/O Stream**

---
#### **I/O Stream**

>[!quote] **Def**
>Em C++, **I/O Streams** são um sistema de classes e objetos que fornecem uma maneira flexível e consistente de realizar operações de entrada e saída, permitindo que programas interajam com fontes de dados como o teclado, a tela, arquivos e redes.
>
>Através de bibliotecas como `<iostream>` (para entrada e saída padrão), `<fstream>` (para arquivos) e `<sstream>` (para strings), I/O Streams oferecem funcionalidades para ler dados de diversas fontes e escrever dados para diferentes destinos, formatando a informação de maneira controlada.

>[!quote] **Vault:** [[C++ IO Stream]]

---

>[!tip] ### **C++ P / Orientada a Objeto**

---
#### **P / Orientada a Objeto**

>[!quote] **Def**
>Em C++, **I/O Streams** são um sistema de classes e objetos que fornecem uma maneira flexível e consistente de realizar operações de entrada e saída, permitindo que programas interajam com fontes de dados como o teclado, a tela, arquivos e redes.
>
>Através de bibliotecas como `<iostream>` (para entrada e saída padrão), `<fstream>` (para arquivos) e `<sstream>` (para strings), I/O Streams oferecem funcionalidades para ler dados de diversas fontes e escrever dados para diferentes destinos, formatando a informação de maneira controlada.

>[!quote] **Vault:** [[C++ Poo]]

---

