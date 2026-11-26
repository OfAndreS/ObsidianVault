
---

>[!tip] ### **Modificadores de Tipos**

---
#### **Principais Modificadores**

> [!quote] **Def**
> 
> Os modificadores de tipos são usados para alterar o comportamento ou o tamanho dos tipos de dados básicos. Eles incluem `signed`, `unsigned`, `short` e `long`.
>
>**Modificadores Comuns:**
>
>`signed`: 
>- Permite valores positivos e negativos (padrão para `int` e `char`).
>  
>---
>  
>`unsigned`: 
>- Permite apenas valores positivos, dobrando o intervalo positivo.
>
>---
>
>`short`: 
>- Reduz o tamanho do tipo de dado.
>
>---
>
>`long`: 
>- Aumenta o tamanho do tipo de dado.
###### _**Exemplo:**_

```cpp
#include <iostream>
using namespace std;

int main() {
    unsigned int positivo = 100; // Apenas valores positivos
    short int pequeno = 32767;   // Número pequeno
    long int grande = 2147483647; // Número grande
    long long int muitoGrande = 9223372036854775807; // Número muito grande

    cout << "Positivo: " << positivo << endl;
    cout << "Pequeno: " << pequeno << endl;
    cout << "Grande: " << grande << endl;
    cout << "Muito Grande: " << muitoGrande << endl;
    return 0;
}

```

---

>[!tip] ### **DataType I**

---
##### _**Dados Inteiros:**_

>[!quote] **Def:**
>
>   `int`: 
>   - Números inteiros (geralmente 4 bytes).
> 
>---
>
>`short`: 
>- Números inteiros curtos (geralmente 2 bytes).
>  
>---
>
>`long`: 
>- Números inteiros longos (geralmente 4 ou 8 bytes).
>  
>---
>`long long`: 
>- Números inteiros muito longos (geralmente 8 bytes).

---
##### _**Dados Flutuantes:**_

>[!quote] **Def:**
>
>   `float`: 
>   - Números decimais de precisão simples (geralmente 4 bytes).
> 
>---
>
   `double`: 
>   - Números decimais de precisão dupla (geralmente 8 bytes).
>  
>---
>
>   `long double`: 
>   Números decimais de precisão estendida (geralmente 10 ou 16 bytes).
>

---
##### _**Dados Caracteres:**_

>[!quote] **Def:**
>
>    `char`: 
>    - Armazena um único caractere (1 byte).
> 
>---
>
   `wchar_t`: 
>   - Armazena caracteres largos (2 ou 4 bytes).

---
##### _**Dados Booleanos:**_

>[!quote] **Def:**
>
>    `bool`: 
>    - Armazena valores verdadeiros (`true`) ou falsos (`false`).
> 

---
###### _**Exemplo:**_

```cpp
#include <iostream>
using namespace std;

int main() {
    int idade = 25;
    float altura = 1.75f;
    double salario = 2500.50;
    char inicial = 'A';
    bool ehEstudante = true;

    cout << "Idade: " << idade << endl;
    cout << "Altura: " << altura << endl;
    cout << "Salário: " << salario << endl;
    cout << "Inicial: " << inicial << endl;
    cout << "É estudante? " << ehEstudante << endl; // 1 para true, 0 para false
    return 0;
}
```

---
