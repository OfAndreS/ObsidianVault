
---

> [!tip] #### **Funções**

---
#### **Estrutura Básica de uma Função**

>[!quote] **Uma função em C possui:**
>
>**Tipo de Retorno:** 
>- Especifica o tipo de dado que a função retorna (ou `void` se não retornar nada).
>  
>--- 
>  
>**Nome da Função:** 
>- Identificador usado para chamar a função.
>  
>---  
>  
>**Parâmetros:** 
>- Valores passados para a função (podem ser opcionais).
>  
>---  
>  
>**Bloco de Código:** 
>- Conjunto de instruções que a função executa.
###### _**Sintaxe Geral**_

```C

tipo_de_retorno nome_da_função(tipo_parametro1 nome_parametro1, tipo_parametro2 nome_parametro2, ...) {
    // Código da função
    return valor; // Opcional para funções void
}

```

---

> [!tip] #### **Declaração / Definição / Chamadas**

---
#### **Declaração (Prototipação)**

>[!quote] **Def**
>- Informa ao compilador a existência da função antes do uso.
```C

int soma(int a, int b); // Declaração`

```
#### **Definição**

>[!quote] **Def**
>- Contém a implementação da função.
```C

int soma(int a, int b) {     return a + b; }

```
#### **Chamadas**

>[!quote] **Def**
>- Usa o nome da função seguido de parênteses, com ou sem argumentos.
```C

int resultado = soma(3, 5); // Chamada printf("Resultado: %d\n", resultado);

```

---

> [!tip] #### **Categorias de Funções**

---
#### **a) Funções Sem Retorno (`void`)**

>[!quote] **Def**
>- Não retornam valores.
```C

void exibirMensagem() {
    printf("Olá, Mundo!\n");
}

```
###### _Chamada:_

```C

exibirMensagem();

```

---
#### **b ) Funções com Retorno**

>[!quote] **Def**
>- Retornam valores de um tipo específico.
```C

float calcularMedia(float nota1, float nota2) {
    return (nota1 + nota2) / 2;
}

```
###### _Chamada:_

```C

float media = calcularMedia(8.5, 7.3); printf("Média: %.2f\n", media);,

```

---
#### **c ) Funções com Parâmetros**

>[!quote] **Def**
>- Aceitam argumentos para processar dados.
```C

int quadrado(int x) {     
	return x * x; 
}

```
###### _Chamada:_

```C

printf("Quadrado de 4: %d\n", quadrado(4));

```

---

#### **d ) Funções Sem Parâmetros**

>[!quote] **Def**
>- Não requerem argumentos na chamada.
```C

int obterNumero() { int num; printf("Digite um número: ");     
	scanf("%d", &num);     
	return num; 
}

```
###### _Chamada:_

```C

int num = obterNumero();
printf("Número lido: %d\n", num);

```

---

> [!tip] #### **Passagem de Parâmetros**

---
#### **a ) Por Valor**

>[!quote] **Def**
>- Uma cópia do argumento é passada; mudanças não afetam o original.
```C

void incrementar(int x) {
    x++;
    printf("Valor dentro da função: %d\n", x);
}

```
###### _Chamada:_

```C

int num = 5;
incrementar(num);
printf("Valor fora da função: %d\n", num); // Não muda

```

---
#### **b ) Por Referência**

>[!quote] **Def**
>- Um ponteiro é usado para passar o endereço do argumento, permitindo modificações.
```C

void dobrar(int *x) {
    *x = *x * 2;
}

```
###### _Chamada:_

```C

int num = 10;
dobrar(&num);
printf("Valor dobrado: %d\n", num); // Modificado

```

---

> [!tip] #### **Funções Recursivas**

---

>[!quote] **Def**
>- Chamam a si mesmas para resolver problemas de forma iterativa.
```C

int fatorial(int n) {
    if (n == 0) return 1;
    return n * fatorial(n - 1);
}

```
###### _Chamada:_

```C

printf("Fatorial de 5: %d\n", fatorial(5));

```

---

> [!tip] #### **Functions Prototypes**

---

>[!quote] **Def**
>Em **C**, um _function prototype_ (protótipo de função) é uma declaração da função que informa ao compilador sobre o nome da função, seu tipo de retorno e os parâmetros que ela aceita, mas sem incluir a implementação (o corpo da função). É como uma "promessa" de que a função será definida em algum lugar do código.
>
>**Estrutura de um Protótipo de Função**
>- **retorno**: O tipo de dado retornado pela função (ex.: `int`, `float`, `void`).
>  
>---
>
>- **nome_da_função**: O nome da função.
>  
>---
>
>- **tipo_parâmetro**: Os tipos dos parâmetros que a função recebe. Os nomes dos parâmetros são opcionais no protótipo, mas ajudam na legibilidade.
>
#### **Por que usar protótipos de função?**

>[!quote] **Def**
>**Organização**: 
>- Permite que as funções sejam definidas depois do `main()` ou em outro arquivo.
>  
>---
>
>**Segurança**: 
>- Garante que o compilador possa verificar se a função está sendo chamada corretamente, com os tipos e número de argumentos adequados.
>  
>---
>
>**Modularidade**: 
>- É essencial em projetos maiores, especialmente ao usar arquivos separados para declaração (cabeçalhos `.h`) e implementação.
###### ***sintaxe geral***

```C

retorno nome_da_função(tipo_parâmetro1, tipo_parâmetro2, ...);

```
###### ***Exemplo***

```C

#include <stdio.h>

// Protótipo da função
int soma(int a, int b);

int main() {
    int resultado = soma(3, 4); // Chamando a função
    printf("Resultado: %d\n", resultado);
    return 0;
}

// Definição da função
int soma(int a, int b) {
    return a + b;
}

```

---
