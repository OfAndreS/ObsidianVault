
---

>[!quote] **Def**
>A escolha entre alocamento estático e dinâmico depende das necessidades específicas do seu programa. Em muitas situações, uma combinação de ambos os tipos é utilizada para criar programas eficientes e adaptáveis. É crucial entender a diferença e as implicações de cada tipo para evitar erros e garantir a boa gestão da memória no seu código C.
>
>Existem duas formas principais de alocamento de memória em C:

>[!quote] **Def**
>**Alocamento estático:** 
>- Simples, rápido, tamanho fixo, adequado para variáveis com tempo de vida e tamanho conhecidos em tempo de compilação.
>
>---
>  
>**Alocamento dinâmico:** 
>- Flexível, tamanho variável, adequado para situações onde o tamanho dos dados é dinâmico ou desconhecido, requer gestão manual da memória pelo programador (alocar e libertar).

---

>[!tip] ### **Static Memory Allocation**

---

>[!quote] **Def**
>**Onde acontece:** 
>- A alocação estática ocorre **durante a compilação** do programa. O compilador decide antecipadamente a quantidade de memória necessária e reserva esse espaço.
>
>**Onde é armazenada:** 
>- A memória alocada estaticamente é normalmente armazenada na **pilha (stack) ou na seção de dados (data segment)**, dependendo do tipo de variável.
#### **Tipos de variáveis estáticas:**

>[!quote] **Def**
>**Variáveis globais:** 
>- Declaradas fora de qualquer função, têm tempo de vida durante toda a execução do programa e são alocadas na seção de dados.
>  
>---
>
>**Variáveis estáticas locais:** 
>- Declaradas dentro de uma função com a palavra-chave `static`, mantêm o seu valor entre chamadas à função e são alocadas na seção de dados.
>  
>---
>
>**Variáveis locais automáticas (padrão):** 
>- Declaradas dentro de uma função (sem `static`), são alocadas na pilha quando a função é chamada e desalocadas quando a função termina.
>  
>---
>
>**Constantes e literais:** 
>- Valores fixos no código fonte também são alocados estaticamente.
##### *~~**Características do alocamento estático:**~~*

>[!quote] **Def**
>**Tamanho fixo:** 
>- O tamanho da memória alocada é determinado em tempo de compilação e **não pode ser alterado durante a execução**.
>  
>---
>
>**Rápido e eficiente:** 
>- O alocamento e desalocamento são geralmente rápidos, pois são gerenciados pelo compilador.
>  
>---
>
>**Limitações:** 
>- Não é adequado para situações onde o tamanho da memória necessária é desconhecido em tempo de compilação ou varia durante a execução do programa (por exemplo, lidar com entrada de dados do utilizador, estruturas de dados dinâmicas).
###### ***Exemplo:***

```cpp
#include <stdio.h>

int global_var; // Variável global (alocamento estático na seção de dados)

void funcao_exemplo() {
    int local_var; // Variável local automática (alocamento estático na pilha)
    static int static_local_var; // Variável local estática (alocamento estático na seção de dados)

    printf("Endereço de local_var: %p\n", &local_var);
    printf("Endereço de static_local_var: %p\n", &static_local_var);
}

int main() {
    funcao_exemplo();
    printf("Endereço de global_var: %p\n", &global_var);
    return 0;
}
```

---

>[!tip] ### **Dynamic Memory Allocation**

---

>[!quote] **Def**
>**Onde acontece:** 
>- A alocação dinâmica ocorre **durante a execução** do programa (runtime), quando o programa requisita memória ao sistema operativo.
>
>**Onde é armazenada:** 
>- A memória alocada dinamicamente é retirada de uma área de memória livre chamada **heap (monte)**.
#### **Funções para alocamento dinâmico em C**

>[!quote] **Def**
>C fornece funções da biblioteca padrão `<stdlib.h>` para gerenciar o alocamento dinâmico:
>
>**`malloc(size)`:** 
>- Aloca um bloco de memória de tamanho `size` bytes. Retorna um ponteiro `void*` para o início do bloco alocado. **A memória alocada com `malloc` não é inicializada** e pode conter lixo de memória.
>  
>---
>
>**`calloc(num, size)`:** 
>- Aloca um bloco de memória para um array de `num` elementos, onde cada elemento tem tamanho `size` bytes. Retorna um ponteiro `void*` para o início do bloco alocado. **A memória alocada com `calloc` é inicializada a zero**.
>  
>---
>
>**`realloc(ptr, new_size)`:** 
>- Redimensiona um bloco de memória previamente alocado dinamicamente, apontado por `ptr`, para um novo tamanho `new_size`. Pode expandir ou reduzir o bloco. Retorna um ponteiro `void*` para o bloco redimensionado (que pode ser um endereço de memória diferente do original `ptr` se a realocação exigir mover o bloco para um novo local).
>  
>---
>
>**`free(ptr)`:** 
>- Liberta (desaloca) um bloco de memória previamente alocado dinamicamente, apontado por `ptr`. É **essencial usar `free`** para devolver a memória ao sistema operativo quando ela não é mais necessária, prevenindo **memory leaks (fugas de memória)**.
##### *~~**Características do alocamento dinâmico:**~~*

>[!quote] **Def**
>**Tamanho dinâmico:** 
>- O tamanho da memória é decidido durante a execução e pode ser ajustado conforme a necessidade.
>  
>---
>
>**Flexibilidade:**
>- Ideal para situações onde o tamanho dos dados é desconhecido em tempo de compilação ou pode variar. Permite criar estruturas de dados dinâmicas como listas ligadas, árvores, etc.
>  
>---
>
>**Responsabilidade do programador:** 
>- O programador é responsável por **alocar e desalocar** a memória dinamicamente usando as funções apropriadas. **Esquecer de libertar a memória alocada dinamicamente leva a memory leaks.**
>  
>---
>**Potencialmente mais lento:** 
>- O alocamento e desalocamento dinâmicos podem ser ligeiramente mais lentos que o alocamento estático, pois envolvem a interação com o sistema operativo para gerenciar o heap. 
###### ***Exemplo de alocamento dinâmico com `malloc` e `free`:***

```C
#include <stdio.h>
#include <stdlib.h> // Necessário para malloc, calloc, realloc, free

int main() {
    int *ptr;
    int n = 5;

    // Alocar memória dinamicamente para 5 inteiros usando malloc
    ptr = (int*) malloc(n * sizeof(int)); // É boa prática fazer cast do void* para o tipo desejado

    if (ptr == NULL) { // SEMPRE verificar se malloc retornou NULL (falha na alocação)
        printf("Falha na alocação de memória!\n");
        return 1; // Indica erro ao sistema operativo
    }

    printf("Memória alocada com sucesso usando malloc.\n");

    // Inicializar a memória (poderia ser feito com calloc, que inicializa a zero automaticamente)
    for (int i = 0; i < n; i++) {
        ptr[i] = i + 1;
    }

    // Imprimir os valores
    printf("Valores armazenados:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", ptr[i]);
    }
    printf("\n");

    // Libertar a memória alocada dinamicamente com free
    free(ptr);
    ptr = NULL; // Boa prática: definir o ponteiro a NULL após libertar a memória para evitar double free ou dangling pointers

    printf("Memória libertada com sucesso.\n");

    return 0;
}
```
###### ***Exemplo com `calloc` e `realloc`:***

```C
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr;
    int n = 5;

    // Alocar memória com calloc (inicializada a zero)
    ptr = (int*) calloc(n, sizeof(int));

    if (ptr == NULL) {
        printf("Falha na alocação com calloc!\n");
        return 1;
    }

    printf("Memória alocada com calloc (inicializada a zero).\n");

    // Imprimir os valores (devem ser todos zero inicialmente)
    printf("Valores iniciais (calloc):\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", ptr[i]);
    }
    printf("\n");


    // Redimensionar a memória com realloc para 10 inteiros
    n = 10;
    ptr = (int*) realloc(ptr, n * sizeof(int));

    if (ptr == NULL) {
        printf("Falha na realocação com realloc!\n");
        return 1;
    }

    printf("Memória redimensionada com realloc para %d elementos.\n", n);

    // Inicializar os novos elementos (os primeiros 5 elementos podem ter sido preservados)
    for (int i = 5; i < n; i++) {
        ptr[i] = i + 1;
    }

    // Imprimir os valores após realocação
    printf("Valores após realloc:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", ptr[i]);
    }
    printf("\n");


    free(ptr);
    ptr = NULL;

    return 0;
}
```

---


