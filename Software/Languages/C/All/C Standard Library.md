
---

>[!quote] **Def**
> A Biblioteca Padrão C é um conjunto fundamental de funções, tipos de dados e macros pré-definidos que estão disponíveis para todos os programas C.
>
> Estas funcionalidades são organizadas em ficheiros de cabeçalho (header files), que terminam tipicamente com a extensão `.h`.
>
> Para utilizar as funcionalidades de um ficheiro de cabeçalho, usa-se a diretiva `#include` no início do teu código C. Por exemplo, `#include <stdio.h>`.
>
> Aqui estão alguns dos ficheiros de cabeçalho mais importantes que um iniciante em C deve conhecer:

---

>[!tip] ### **Funções**

---

>[!quote] **Def**
> **`<stdio.h>`:**  
> 
> Este é o primeiro e talvez o mais importante ficheiro de cabeçalho.
> Contém funções para operações de **Standard Input/Output** (Entrada/Saída Padrão).
> 
> Funções como `printf()` para imprimir texto no ecrã, `scanf()` para ler dados do teclado, `fopen()`, `fclose()`, `fread()`, `fwrite()` para trabalhar com ficheiros estão definidas aqui.
>

---

>[!quote] **Def**
>
> **`<stdlib.h>`:** 
> 
> Este ficheiro de cabeçalho providencia funções para **utilidades gerais**.
> Inclui funções para:
> 
>**Alocação e gestão de memória:** 
>   - `malloc()`, `calloc()`, `realloc()`, `free()` 
>   para alocar e libertar memória dinamicamente.
>   
> **Conversão de tipos numéricos:** 
> - `atoi()`, `atol()`, `atof()` 
> para converter strings para inteiros, longs, e floats, respetivamente.
> 
> ---
> 
> **Geração de números aleatórios:** `rand()`, `srand()`.
>   
>  **Funções de sistema:** `exit()`, `abort()`.
>    
> **Procura e ordenação:** `qsort()`, `bsearch()`.
>   
> **Aritmética de inteiros:** `abs()`, `div()`.

---

>[!quote] **Def**
> **`<string.h>`:** 
> 
> Este ficheiro de cabeçalho contém funções para **manipulação de strings** (cadeias de caracteres).
> 
> **Funções como:** 
> - `strcpy()` para copiar strings
> - `strcat()` para concatenar strings
> - `strcmp()` para comparar strings
> - `strlen()` para obter o comprimento de uma string
> - `strstr()` para procurar uma substring
> - `memcpy()`, `memmove()`, `memset()` para manipulação de blocos de memória.

---

>[!quote] **Def**
> **`<stdbool.h>`:**  Este ficheiro de cabeçalho define o tipo de dados **booleano** `bool` e os valores `true` e `false`.
> 
>Antes deste ficheiro de cabeçalho, em C, representava-se verdadeiro e falso com inteiros (tipicamente 1 para verdadeiro e 0 para falso).  
>
>- `stdbool.h` torna o código mais legível ao usar `bool`, `true`, e `false` explicitamente.

---

>[!quote] **Def**
> **`<ctype.h>`:** Este ficheiro de cabeçalho contém funções para **classificação de caracteres** e conversão de caracteres.
> Funções para verificar se um caractere é: 
> - alfabético (`isalpha()`)
> - numérico (`isdigit()`)
> - alfanumérico (`isalnum()`)
> - maiúsculas (`isupper()`) 
> - minúsculas (`islower()`)
> - espaço em branco (`isspace()`)
>   
>---
>
> Funções para converter caracteres para maiúsculas (`toupper()`) ou minúsculas (`tolower()`).

---

>[!quote] **Def**
> **`<time.h>`:** Este ficheiro de cabeçalho providencia funções para **manipulação de tempo e data**.
> 
>  Inclui funções para:
>  
> - obter a hora atual (`time()`)
> - converter entre diferentes formatos de tempo
> - formatar tempo para strings (`strftime()`), 
>   
>E funções para operações com relógios de processador.

---

>[!quote] **Def**
> **`<stddef.h>`:**  Este ficheiro de cabeçalho define vários **tipos de dados padrão e macros** que são úteis em várias partes da linguagem C.
> 
> **Define tipos como:**
> - `size_t` (um tipo inteiro sem sinal usado para representar o tamanho de objetos)
> - `ptrdiff_t` (um tipo inteiro com sinal usado para representar a diferença entre dois ponteiros)
> - `NULL` (uma macro que representa um ponteiro nulo) 
> - `offsetof` (uma macro para obter o offset de um membro numa struct).

---

>[!quote] **Def**
> **`<stdint.h>`:** Este ficheiro de cabeçalho define **tipos de inteiros de tamanho fixo**.
> Permite aos programadores usar tipos de inteiros com um número específico de bits, independentemente da arquitetura da máquina. 
> **Por exemplo:** 
> 
> - `int32_t` é um inteiro com sinal de 32 bits.
> - `uint64_t` é um inteiro sem sinal de 64 bits.  
> 
> Isto é útil para garantir portabilidade e trabalhar com formatos de dados binários específicos.

---

>[!quote] **Def**
> **`<stdarg.h>`:** Este ficheiro de cabeçalho providencia funcionalidades para trabalhar com **funções de número variável de argumentos** (variadic functions).
> 
> Permite criar funções que podem aceitar um número variável de argumentos, como a função `printf()`.  
> 
> Define macros como `va_list`, `va_start`, `va_arg`, `va_end` para aceder aos argumentos variáveis.

---

>[!quote] **Def**
> **`<errno.h>`:**  Este ficheiro de cabeçalho define macros para **reportar erros**.
> 
> Define a macro `errno`, que é uma variável global que é configurada por funções da biblioteca padrão para indicar que ocorreu um erro.  Os valores que `errno` pode assumir são definidos como macros como `EPERM`, `ENOENT`, `EIO`, etc., representando diferentes tipos de erros.

---
#### **Obs:**

>[!quote] **Def**
> Estes são apenas alguns dos ficheiros de cabeçalho mais importantes da Biblioteca Padrão C.  À medida que fores aprendendo C e construindo programas mais complexos, irás descobrir e usar outros ficheiros de cabeçalho da biblioteca padrão.  Explorar a documentação da biblioteca padrão C é uma ótima maneira de aprofundar o teu conhecimento e descobrir funcionalidades úteis.

---