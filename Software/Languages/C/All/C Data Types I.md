
---

>[!quote] **Sumário**
>**Inteiros**
>- `%d` ou `%i` para `int`
>
>---
>  
>- `%u` para `unsigned int`
>
>---
>  
>- `%hd` para `short int`
> 
>---  
>  
>- `%hu` para `unsigned short int`
>
>---
>  
>- `%ld` para `long int`
>
>---
>  
>- `%lu` para `unsigned long int`
>

>[!quote] **Sumário**
>
>**Ponto flutuante**:
>
>- `%f` para `float`
>
>---
>
>- `%lf` para `double`
>
>---  
>  
>- `%Lf` para `long double`
>

>[!quote] **Sumário**
>
>**Caracteres**:
>- `%c` para `char`

---

> [!Tip] #### **Tipos Char**

---
#### _**Char**_

>[!quote] **Def**
>- **Tamanho**: 8 bits
>- **Intervalo**: -128 a 127
>  
>**Formato de impressão**: `%c` (para caracteres) ou `%d` (para inteiros)
```
char c = 'A'; // Armazenando um caractere 
char c2 = 65; // Usando o código ASCII de 'A'
```
#### ***unsigned char***

>[!quote] **Def**
>- **Tamanho**: 8 bits
>- **Intervalo**: 0 a 255
>  
>**Formato de impressão**: `%c` ou `%u` (para inteiros)
```
unsigned char c = 200;

```
#### ***unsigned char***

>[!quote] **Def**
>- **Tamanho**: 8 bits
>- **Intervalo**: -128 a 127
>  
>**Formato de impressão**: `%c` ou `%d`
```
signed char c = -100;

```

---

> [!Tip] #### **Dados Inteiros**

---
#### **_int_**

>[!quote]
>- **Tamanho**: 16 bits
>- **Intervalo**: -32.768 a 32.767
>  
>**Formato de impressão**: `%d`
```
int num = 1000;

```
#### **_unsigned int_**

>[!quote] **Def**
>- **Tamanho**: 16 bits
>- **Intervalo**: 0 a 65.535
>  
>**Formato de impressão**: `%u`
```
unsigned int num = 50000;

```
#### **_signed int_**

>[!quote] **Def**
>- **Tamanho**: 16 bits
>- **Intervalo**: -32.768 a 32.767
>  
>**Formato de impressão**: `%d`
```
signed int num = -200;

```

---

> [!Tip] #### **Dados Ponto Flutuante**

---
#### **_float_**

>[!quote] **Def**
>- **Tamanho**: 32 bits
>- **Intervalo**: 3,4E-38 a 3,4E+38
>
>**Formato de impressão**: `%f`
```
float num = 3.14f;

```
#### **_double_**

>[!quote] **Def*8
>- **Tamanho**: 64 bits
>- **Intervalo**: 1,7E-308 a 1,7E+308
>
>**Formato de impressão**: `%lf`
```
double num = 3.141592653589;

```
#### **_long double_**

>[!quote] **Def**
>- **Tamanho**: 80 bits ou mais
>- **Intervalo**: 3,4E-4932 a 3,4E+4932
>
>**Formato de impressão**: `%Lf`
```
long double num = 3.14159265358979323846L;

```

---

> [!Tip] #### **Booleano**

---
#### ***bool***

>[!quote] **Def**
>Em C, o tipo `bool` foi introduzido no padrão **C99** para representar valores booleanos: verdadeiro (`true`) ou falso (`false`).
>
>- **Definição:** Para usar `bool`, é necessário incluir o cabeçalho `<stdbool.h>`.
>  
>**Valores:**
>
>- `true` é uma constante com valor 1.
>- `false` é uma constante com valor 0.
```c

#include <stdio.h>
#include <stdbool.h>

int main() {
    bool is_valid = true;

    if (is_valid) {
        printf("A condição é verdadeira.\n");
    }

    return 0;
}

```

---

> [!Tip] #### **Typecasting**

---
#### ***Conversão implícita***

>[!quote] **Def**
>O compilador automaticamente converte um tipo em outro quando necessário, sem necessidade de instruções explícitas do programador. Normalmente ocorre em expressões matemáticas ou ao atribuir valores de tipos menores para maiores.
```

int num = 10;
float result = num;  // Conversão implícita de int para float

```

---
#### ***Conversão explícita***

>[!quote] **Def**
>O programador especifica a conversão de um tipo para outro utilizando a sintaxe 
>`var = var(tipo_desejado)`.
```

float num = 3.14;
int result = (int)num;  // Conversão explícita de float para int

```

---
#### ***TypeOfCasting***

>[!quote] **Def**
>**De tipos numéricos:**
  >  
>- Inteiro para float (`int` → `float`)
>- Float para inteiro (`float` → `int`)
>- Double para float (`double` → `float`)
>- Entre diferentes tamanhos de inteiros (`short` ↔ `int`, `int` ↔ `long`, etc.)
>
>---
>
>**De ponteiros:**
>
>- Conversão entre tipos de ponteiros (`int*` ↔ `float*`, por exemplo).
>- Conversão de ponteiro para inteiro e vice-versa.
>
>---
>  
>**Outros:**
>
>- Casting de caracteres (`char` ↔ `int`).
>
> **Nota:** Apesar de poderoso, o casting deve ser usado com cuidado para evitar comportamentos inesperados, como perda de dados ao converter de `float` para `int`.

---
