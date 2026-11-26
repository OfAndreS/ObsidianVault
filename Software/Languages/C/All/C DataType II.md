
---

> [!tip] #### **Ponteiros**

---
#### **Ponteiros** 

>[!quote] **Def**
>Um ponteiro é uma variável especial que armazena o endereço de memória de outra variável. É usado para acessar e manipular dados na memória diretamente, tornando o código mais flexível e poderoso.

>[!quote] **YouTube:** [Ponteiros I](https://www.youtube.com/watch?v=k3xWL8i7-Mc) && [Ponteiros II](https://www.youtube.com/watch?v=ZhYiNrI2OLU)
###### ***Definição:***

```C

int x = 10;
int *ptr = &x; // Declaração de um ponteiro para um inteiro

```

>[!quote] **Def:**
>
>**Para &:**
>
>- Número em hexadecimal representa a variável que armazena um valor.
>`000fff = x = 10;`
>
>**Para *ptr:**
>
>- É o artifício da linguagem que faz revelar o valor apontado
###### ***Exemplo:***
```C
#include <stdio.h>

int main() {
    int x = 10;
    int *p = &x;  // Ponteiro p aponta para o endereço de x

    printf("Valor de x: %d\n", x);      // Imprime o valor de x
    printf("Valor de x via ponteiro: %d\n", *p); // Acessa o valor de x via ponteiro
    printf("Endereço de x: %p\n", p);  // Imprime o endereço armazenado no ponteiro

    return 0;
}

```
###### ***Exemplo Uso em Funções:***
```C
#include <stdio.h>
#include <stdlib.h>
void manipulaPonteiros(int *ptr){
    *ptr = (*ptr + 2);
}

int main() {

    int x = 10;
    int *ptr = &x; // ptr aponta para x

    manipulaPonteiros(ptr);
    printf("Valor de x antes da manipular: %d\n", *ptr); // Imprime 12
    return 0;

}
```

---
#### **Double Pointer** 

>[!quote] **Def**
>Um double pointer é um ponteiro que aponta para outro ponteiro. É útil em casos como manipulação de matrizes, alocação dinâmica complexa e passagem de ponteiros para funções.
###### ***Definição:***

```C

int **pptr; // Declaração de um ponteiro para ponteiro

```
###### ***Exemplo:***

```C

#include <stdio.h>

int main() {
    int x = 42;
    int *p = &x;    // Ponteiro p aponta para x
    int **pp = &p;  // Ponteiro pp aponta para p

    printf("Valor de x via pp: %d\n", **pp); // Acessa o valor de x
    return 0;
}

```

---
#### **Function Pointer** 

>[!quote] **Def**
>Armazena o endereço de uma função, permitindo chamá-la de forma indireta. Útil em callbacks e tabelas de funções.
###### ***Definição:***

```C

void (*funcPtr)(); // Ponteiro para função sem parâmetros e sem retorno

```
###### ***Exemplo:***

```C

#include <stdio.h>

void greet() {
    printf("Hello, World!\n");
}

int main() {
    void (*funcPtr)() = greet; // Ponteiro para a função greet
    funcPtr();                 // Chama a função através do ponteiro

    return 0;
}

```

---
#### **Restrict** 

>[!quote] **Def**
>A keyword `restrict` informa ao compilador que o ponteiro será o único meio de acessar o dado que ele aponta. Isso permite otimizações no código.
###### ***Definição:***

```C

void add(int *restrict a, int *restrict b, int *restrict result) { }

```
###### ***Exemplo:***

```C

#include <stdio.h>

void add(int *restrict a, int *restrict b, int *restrict result) {
    *result = *a + *b; // Supõe que a, b e result não compartilham memória
}

int main() {
    int x = 5, y = 10, z;
    add(&x, &y, &z);
    printf("Soma: %d\n", z);

    return 0;
}

```

---

> [!tip] #### **Struct**

---
#### **Struct** 

>[!quote] **Def**
>Agrupa variáveis de diferentes tipos em uma única unidade lógica.
###### ***Definição:***

```C

struct Point {
    int x;
    int y;
};

```
###### ***Exemplo:***

```C

#include <stdio.h>

struct Point {
    int x;
    int y;
};

int main() {
    struct Point p = {10, 20};
    printf("Ponto: (%d, %d)\n", p.x, p.y); // Operador '.'

    struct Point *ptr = &p;
    printf("Ponto via ponteiro: (%d, %d)\n", ptr->x, ptr->y); // Operador '->'

    return 0;
}

```

---

> [!tip] #### **Union**

---
#### **Union** 

>[!quote] **Def**
>Permite armazenar diferentes tipos de dados no mesmo espaço de memória. Os membros compartilham o mesmo espaço, economizando memória.
###### ***Definição:***

```C

union Data {
    int i;
    float f;
};

```
###### ***Exemplo:***

```C

#include <stdio.h>

union Data {
    int i;
    float f;
};

int main() {
    union Data d;
    d.i = 42;
    printf("Inteiro: %d\n", d.i);

    d.f = 3.14;
    printf("Float: %f\n", d.f); // Sobrescreve o valor de inteiro

    return 0;
}

```

---

> [!tip] #### **Enum**

---
#### **Enum** 

>[!quote] **Def**
>Define um conjunto de constantes inteiras com nomes, melhorando a legibilidade do código.
###### ***Definição:***

```C

enum Days { MON, TUE, WED, THU, FRI };

```
###### ***Exemplo:***

```C

#include <stdio.h>

enum Days { MON, TUE, WED, THU, FRI };

int main() {
    enum Days today = WED;
    printf("Hoje é o dia: %d\n", today); // Imprime 2

    return 0;
}

```

---

> [!tip] #### **size_t**

---
#### **size_t** 

>[!quote] **Def**
>`size_t` é um tipo de dado não assinado usado para representar tamanhos de objetos e índices em funções da biblioteca padrão. Ele é garantido para ser grande o suficiente para qualquer tamanho de objeto no sistema.
###### ***Definição:***

```C

sizeof(var);

```
###### ***Exemplo:***

```C

#include <stdio.h>

int main() {
    size_t size = sizeof(int);
    printf("Tamanho de int: %zu bytes\n", size);

    return 0;
}

```

---
