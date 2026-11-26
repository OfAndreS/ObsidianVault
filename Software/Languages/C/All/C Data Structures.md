
---
#### **String**

>[!quote] Strings em C: Uma Abordagem Detalhada
>Em C, **strings** são, essencialmente, **vetores de caracteres**, em outras palavras uma sequência de **chars** terminados por um caractere nulo (`'\0'`).  
>- Essa terminação é crucial para que as funções da biblioteca padrão que manipulam strings saibam onde a string termina.
>  

>[!quote] Observações:
>**Tamanho** 
>- É importante alocar memória suficiente para a string, incluindo o caractere nulo.
>  
>**Inicialização com string literal** 
>- O compilador automaticamente adiciona o caractere nulo no final da string.

>[!quote] Atenção
>**Caractere nulo:** 
>- Ao modificar uma string, certifique-se de não sobrescrever o caractere nulo.
>
>**Funções de manipulação:** 
>- A biblioteca padrão do C oferece diversas funções para manipular strings, como `strcpy`, `strcat`, `strlen`, etc. 
>  
>**Alocação de memória:** 
>- Ao trabalhar com strings de tamanho variável, utilize `malloc` e `free` para alocar e liberar memória dinamicamente.
>  
>**Segurança:** 
>- Evite estouros de buffer ao trabalhar com strings. Utilize funções como `fgets` e `snprintf` para garantir a segurança.
##### *Específicos*

>[!quote] Entrada e Saída de Strings
>**`scanf()`**
>- Para ler strings, é preciso ter cuidado com o tamanho do buffer para evitar estouros.
>  
>**`fgets()`** 
>- É uma função mais segura para ler strings, pois permite especificar o número máximo de caracteres a serem lidos.
>  
>**`printf`:** 
>- Para imprimir strings, use o especificador de formato `%s`.

##### *Funções para Manipulação de Strings*

>[!quote] **Def**
>**01)** **`strcpy(destino, origem)`:** 
>- Copia a string `origem` para `destino`.
>

>[!quote] **Def** 
>  
>**02)** **`strcat(destino, origem)`:** 
>- Concatena a string `origem` ao final de `destino`.

>[!quote] **Def**
>
>**03)** **`strlen(string)`:** 
>- Retorna o comprimento da string (sem contar o caractere nulo).

>[!quote] **Def**
>
>**04)** **`strcmp(string1, string2)`:** 
>- Compara duas strings lexicograficamente. Retorna um valor negativo se `string1` é menor que `string2`, zero se são iguais e um valor positivo se `string1` é maior que `string2`.

>[!quote] **Def**
>
>**05)** **`sprintf(destino, formato, arg1, arg2, ...)`:** 
>- Formata e armazena uma série de caracteres e valores em `destino` de acordo com o formato especificado. É similar ao `printf`, mas em vez de imprimir na tela, armazena o resultado em uma string.
##### *Declaração e Inicialização*

```
char minhaString[20]; // Declara um array de 20 caracteres
char outraString[] = "Olá, mundo!"; // Inicializa com uma string literal
```
##### *Acesso aos Caracteres*

```
char primeiraLetra = minhaString[0]; // Acessa o primeiro caractere

``` 
##### *Modificação de Strings*

```
minhaString[0] = 'M'; // Altera o primeiro caractere

```
##### *Exemplos*

>[!error] Sem entrada de Dados

```
#include <stdio.h>
#include <string.h>

int main() {
    char str1[20] = "Olá";
    char str2[] = ", mundo!";

    strcat(str1, str2); // Concatena str2 a str1
    printf("%s\n", str1);

    int tamanho = strlen(str1);
    printf("Tamanho da string: %d\n", tamanho);

    return 0;
}
```

>[!error] Com entrada de Dados

```
#include <stdio.h>

int main() {
    char nome[50];

    printf("Digite seu nome: ");
    fgets(nome, 50, stdin);

    printf("Olá, %s!\n", nome);

    return 0;
}
```

---
#### **Array**

>[!quote] **Def**
>Arrays são coleções de elementos do mesmo tipo, armazenados em posições contíguas de memória. Eles são acessados por índices e têm tamanho fixo.
>
>~~***Definição Detalhada:***~~
>
>**Armazenamento:** 
>- Elementos armazenados sequencialmente na memória.
>  
>---
>
>**Uso:** 
>- Armazenar dados homogêneos (números, caracteres, etc.).
>  
>---
>
>**Acesso:** 
>- Direto, via índices (`array[0]`, `array[1]`, etc.).
>
>---
>
>**Limitação:** 
>- Tamanho fixo, definido na declaração.
###### ***Exemplo:***

```
#include <stdio.h>

int main() {
    int numeros[5] = {10, 20, 30, 40, 50}; // Declaração e inicialização

    // Acessando elementos
    for (int i = 0; i < 5; i++) {
        printf("Elemento %d: %d\n", i, numeros[i]);
    }
    return 0;
}
```

---
#### **Multidimensional Arrays & Matrix Arrays**

>[!quote] **Def**
>Arrays multidimensionais são arrays com mais de uma dimensão. Matrizes são arrays 2D, úteis para representar tabelas ou grids.
>
>~~***Definição Detalhada:***~~
>
>**Armazenamento:** 
>- Elementos organizados em linhas e colunas (para 2D).
>
>---
>  
>**Uso:** 
>- Representação de tabelas, matrizes, grids.
>
>---
>  
>**Acesso:** 
>- Usando múltiplos índices (`matriz[0][0]`, `matriz[1][2]`, etc.).
###### ***Exemplo:***

```
#include <stdio.h>

int main() {
    int matriz[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };

    // Acessando elementos
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("Matriz[%d][%d] = %d\n", i, j, matriz[i][j]);
        }
    }
    return 0;
}
```

---
#### **Linked Lists**

>[!quote] **Def**
>Linked Lists (listas encadeadas) são estruturas dinâmicas onde cada elemento (nó) contém dados e um ponteiro para o próximo nó. Elas permitem inserção e remoção eficientes, mas o acesso sequencial é mais lento comparado a arrays.
>
>~~***Definição Detalhada:***~~
>
>**Armazenamento:** 
>- Nós dinâmicos, cada um contendo dados e um ponteiro para o próximo nó.
>
>---
>
>**Uso:** 
>- Quando o número de elementos é desconhecido ou varia frequentemente.
>
>---
>
>**Variações:** 
>- Listas simplesmente encadeadas, duplamente encadeadas, circulares.
###### ***Exemplo:***

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

int main() {
    struct Node* head = NULL;
    struct Node* second = NULL;
    struct Node* third = NULL;

    // Alocando memória para os nós
    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    // Atribuindo dados e ligando os nós
    head->data = 1;
    head->next = second;

    second->data = 2;
    second->next = third;

    third->data = 3;
    third->next = NULL;

    // Percorrendo a lista
    struct Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");

    // Liberando memória
    free(head);
    free(second);
    free(third);

    return 0;
}
```

---
#### **Stacks**

>[!quote] **Def**
>Stacks (pilhas) são estruturas que seguem o princípio **LIFO** (Last In, First Out), onde o último elemento inserido é o primeiro a ser removido.
>
>~~***Definição Detalhada:***~~
>
>**Armazenamento:** 
>- Elementos organizados em uma sequência linear.
>
>---
>  
>**Uso:** 
>- Gerenciamento de chamadas de funções, avaliação de expressões, undo/redo.
>
>---
>  
>**Operações:** 
>- `push` (inserir), `pop` (remover), `peek` (verificar o topo).
###### ***Exemplo:***

```
#include <stdio.h>
#include <stdlib.h>

#define MAX 100

struct Stack {
    int items[MAX];
    int top;
};

void push(struct Stack* s, int value) {
    if (s->top == MAX - 1) {
        printf("Stack overflow!\n");
        return;
    }
    s->items[++(s->top)] = value;
}

int pop(struct Stack* s) {
    if (s->top == -1) {
        printf("Stack underflow!\n");
        return -1;
    }
    return s->items[(s->top)--];
}

int main() {
    struct Stack s;
    s.top = -1;

    push(&s, 10);
    push(&s, 20);
    push(&s, 30);

    printf("Elemento removido: %d\n", pop(&s)); // Saída: 30
    printf("Elemento removido: %d\n", pop(&s)); // Saída: 20

    return 0;
}
```

---
#### **Queues**

>[!quote] **Def**
>Queues (filas) seguem o princípio **FIFO** (First In, First Out), onde o primeiro elemento inserido é o primeiro a ser removido.
>
>~~***Definição Detalhada:***~~
>
>**Armazenamento:** 
>- Elementos organizados em uma sequência linear.
>
>---
>  
>**Uso:** 
>- Gerenciamento de tarefas em ordem de chegada (impressão, processamento).
>
>---
>  
>**Operações:** 
>- `enqueue` (inserir), `dequeue` (remover), `peek` (verificar o início).
###### ***Exemplo:***

```
#include <stdio.h>
#include <stdlib.h>

#define MAX 100

struct Queue {
    int items[MAX];
    int front, rear;
};

void enqueue(struct Queue* q, int value) {
    if (q->rear == MAX - 1) {
        printf("Queue overflow!\n");
        return;
    }
    q->items[++(q->rear)] = value;
}

int dequeue(struct Queue* q) {
    if (q->front > q->rear) {
        printf("Queue underflow!\n");
        return -1;
    }
    return q->items[(q->front)++];
}

int main() {
    struct Queue q;
    q.front = 0;
    q.rear = -1;

    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    printf("Elemento removido: %d\n", dequeue(&q)); // Saída: 10
    printf("Elemento removido: %d\n", dequeue(&q)); // Saída: 20

    return 0;
}
```

---
