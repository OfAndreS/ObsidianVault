
---
#### **Operações Aritméticas**

>[!quote] **Def**
>
>As operações aritméticas em C++ são usadas para realizar cálculos matemáticos básicos, como adição, subtração, multiplicação, divisão e módulo (resto da divisão). Essas operações são realizadas usando os operadores aritméticos padrão.
>
>**Operadores Aritméticos:**
>
>**- `+` Adição**
>  
>---
>**- `-` Subtração**
>
>---
>**- `*` Multiplicação**
>  
>---
>**- `/` Divisão**
>  
>---
>**- `%` Módulo - resto da divisão**
>  
###### _**Exemplo:**_

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 3;
    cout << "Soma: " << (a + b) << endl;          // 13
    cout << "Subtração: " << (a - b) << endl;     // 7
    cout << "Multiplicação: " << (a * b) << endl; // 30
    cout << "Divisão: " << (a / b) << endl;       // 3 (divisão inteira)
    cout << "Módulo: " << (a % b) << endl;        // 1
    return 0;
}
```

---
#### **Operadores Relacionais**

> [!quote] **Def**
> 
> Os operadores relacionais são usados para comparar dois valores ou expressões. Eles retornam um valor booleano (`true` ou `false`) com base na comparação realizada. Esses operadores são frequentemente usados em estruturas condicionais, como `if` e `while`.
>
>**Operadores Relacionais:**
>
>- `==` **Igual a**
>
>---
>  
>- `!=` **Diferente de**
>
>---
>
>- `>` **Maior que**
>
>---
>  
>- `<` **Menor que**
>
>---
>  
>- `>=` **Maior ou igual a**
>
>---
>  
>- `<=` **Menor ou igual a**
###### _**Exemplo:**_

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5, y = 10;
    cout << (x == y) << endl;  // 0 (false)
    cout << (x != y) << endl;  // 1 (true)
    cout << (x > y) << endl;   // 0 (false)
    cout << (x < y) << endl;   // 1 (true)
    cout << (x >= y) << endl;  // 0 (false)
    cout << (x <= y) << endl;  // 1 (true)
    return 0;
}
```

---
#### **Operadores Lógicos**

> [!quote] **Def**
> 
> Os operadores lógicos são usados para combinar ou inverter expressões booleanas. Eles são frequentemente utilizados em condições complexas para tomar decisões no código. Os operadores lógicos básicos são `&&` (E lógico), `||` (OU lógico) e `!` (NÃO lógico).
>
>**Operadores Lógicos:**
>
>- `&&` **E lógico** - Retorna `true` se ambas as expressões forem verdadeiras.
>  
>---
>
>- `||` **OU lógico** - Retorna `true` se pelo menos uma das expressões for verdadeira.
>  
>---
>
>- `!` **NÃO lógico**- Inverte o valor booleano (de `true` para `false` e vice-versa).
###### _**Exemplo:**_

```cpp
#include <iostream>
using namespace std;

int main() {
    bool a = true, b = false;
    cout << (a && b) << endl;  // 0 (false)
    cout << (a || b) << endl;  // 1 (true)
    cout << (!a) << endl;      // 0 (false)
    cout << (!b) << endl;      // 1 (true)
    return 0;
}
```

---
#### **Operador Ternário**

> [!quote] **Def**
> 
> O operador ternário é uma forma compacta de realizar uma operação condicional em C++. Ele é chamado de "ternário" porque envolve três operandos: uma condição, uma expressão para o caso verdadeiro e uma expressão para o caso falso. A sintaxe básica é:
> 
> cpp
> 
> Copy
> 
> condição ? expressão1 : expressão2;
> 
> **Funcionamento:**
> 
> - Se a **condição** for verdadeira (`true`), o operador retorna o valor de **expressão1**.
>     
> - Se a **condição** for falsa (`false`), o operador retorna o valor de **expressão2**.
>     
> 
> O operador ternário é frequentemente utilizado para substituir estruturas condicionais simples, como `if-else`, de forma mais concisa.
###### _**Exemplo:**_

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 20;

    // Usando o operador ternário para encontrar o maior valor
    int maior = (a > b) ? a : b;
    cout << "O maior valor é: " << maior << endl; // Saída: 20

    // Usando o operador ternário para decidir se é maior de idade
    int idade = 18;
    string status = (idade >= 18) ? "Adulto" : "Menor de idade";
    cout << "Status: " << status << endl; // Saída: Adulto

    return 0;
}
```

---
