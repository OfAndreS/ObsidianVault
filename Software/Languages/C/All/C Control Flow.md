
---

> [!Tip] #### **Condicional**

---
#### _**if**_

>[!quote] **Def**
>- **Descrição:** Avalia uma condição e executa o bloco de código se a condição for verdadeira.
```cpp

if (condição1) {
    // Executado se condição1 for verdadeira
} else if (condição2) {
    // Executado se condição2 for verdadeira
} else {
    // Executado se nenhuma condição for verdadeira
}

```

---

> [!Tip] #### **Switch-Case**

---
#### _**Switch**_

>[!quote] **Def**
>
>- **Descrição:** Escolhe uma entre várias opções com base em um valor específico.
>
```cpp

switch (variável) {
    case valor1:
        // Código executado se variável == valor1
        break;
    case valor2:
        // Código executado se variável == valor2
        break;
    default:
        // Código executado se nenhum caso for satisfeito
}

```

---

> [!Tip] #### **Controle de Fluxo em Laços**

---
#### ***break***

>[!quote] **Def**
>- **Descrição:** Encerra imediatamente o laço ou o `switch`.
```cpp

for (int i = 0; i < 5; i++) {
    if (i == 3) {
        break;
    }
    printf("Iteração %d\n", i);
}

```
#### ***continue***

>[!quote] **Def**
>- **Descrição:** Interrompe a iteração atual e pula para a próxima.
```cpp

for (int i = 0; i < 5; i++) {
    if (i == 2) {
        continue;
    }
    printf("Iteração %d\n", i);
}

```
#### ***goto***

>[!quote] **Def**
>- **Descrição:** Permite pular para um rótulo específico. Deve ser usado com cautela, pois pode dificultar a leitura do código.
```cpp

int i = 0;
if (i == 0) {
    goto fim;
}
printf("Isso não será exibido.\n");
fim:
    printf("Fim do programa.\n");

```

---

> [!Tip] #### **Loops**

---

> [!quote] Definição
> Loops são estruturas fundamentais em programação que permitem executar um bloco de código repetidamente enquanto uma determinada condição for verdadeira. 
> Em C, temos três tipos principais de loops: 
>- `for` 
>- `while` 
>- `do-while` 
>  
>Além disso, embora não seja um loop nativo da linguagem C, o conceito de `foreach` pode ser implementado utilizando outras estruturas.
#### ***For***

> [!quote] **Sintaxe:**
> - Ideal para quando sabemos o número exato de iterações.
```c
for (inicialização; condição; incremento) {
    // Código a ser repetido
}
```

>[!quote] **Exemplo:** 
>- Imprimir os números de 1 a 10.
```cpp
for (int i = 1; i <= 10; i++) {
    printf("%d ", i);
}
```
#### ***While***

> [!quote] **Sintaxe:**
>- Executa um bloco de código enquanto uma condição for verdadeira.
```C
while (condição) {
    // Código a ser repetido
}
```

> [!quote] **Exemplo:**
>- Ler números até que o usuário digite 0.
```cpp
int numero;
do {
    printf("Digite um número (0 para sair): ");
    scanf("%d", &numero);
} while (numero != 0);
```
#### ***Do-While***

> [!quote] **Sintaxe:**
>- Executa um bloco de código enquanto uma condição for verdadeira.
```C
do {
    // Código a ser repetido
} while (condição);
```

> [!quote] **Exemplo:**
> - Imprimir uma mensagem de boas-vindas pelo menos uma vez.
```cpp
char continuar;
do {
    printf("Bem-vindo!\n");
    printf("Deseja continuar? (s/n): ");
    scanf(" %c", &continuar);
} while (continuar == 's');
```
##### *Foreach (Simulação em C)*

>[!quote] C não tem Foreach
>Embora o C não tenha um loop `foreach` nativo como em linguagens como C# ou Java, podemos simular seu comportamento utilizando ponteiros e aritmética de ponteiros para percorrer arrays.
```cpp
#include <stdio.h>

int main() {
    int numeros[] = {1, 2, 3, 4, 5};
    int tamanho = sizeof(numeros) / sizeof(numeros[0]);

    // Simulação de foreach
    for (int *ptr = numeros; ptr < numeros + tamanho; ptr++) {
        printf("%d ", *ptr);
    }

    return 0;
}
```


---

> [!Tip] #### **Switch Case Vs If**

---

>[!quote] Quando usar o Switch / Case
>**Quando usar switch case:**
>- Quando você tem uma variável que pode assumir um conjunto limitado de valores.
>- Quando você precisa comparar essa variável com vários valores constantes.
>- Quando a estrutura de decisão é baseada em igualdade.
>  
>**Quando usar if:**
>- Quando as condições são mais complexas e envolvem operadores lógicos (&&, ||, !).
>- Quando você precisa comparar valores que não são constantes.
>- Quando a ordem das comparações é importante.

![[Pasted image 20240912094330 1.png]]

>[!error] Como funciona
>**Execução** 
>- A expressão dentro do `switch` é avaliada.
>- O valor resultante é comparado com cada `case`.
>- Se houver uma correspondência, o código dentro daquele `case` é executado.
>- O `break` é usado para sair do `switch` após a execução de um caso.
>- Se nenhum caso corresponder, o código dentro do `default` é executado (se houver).
>  
>**Observações:**
>- O `break` é fundamental para evitar que o código continue executando os casos seguintes após encontrar uma correspondência.
>- O `default` é opcional e é utilizado para tratar casos não especificados nos outros `cases`.
>- É possível aninhar `switch` dentro de outros `switch`.

```cpp
#include <stdio.h>

int main() {
    char grade;
    printf("Digite sua nota (A, B, C, D ou F): ");
    scanf(" %c", &grade);

    switch (grade) {
        case 'A':
            printf("Excelente!\n");
            break;
        case 'B':
            printf("Muito bom!\n");
            break;
        case 'C':
            printf("Bom!\n");
            break;
        case 'D':
        case 'F':
            printf("Precisa melhorar!\n");
            break;
        default:
            printf("Nota inválida.\n");
    }

    return 0;
}
```

---
