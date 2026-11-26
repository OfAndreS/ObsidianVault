
---

> [!tip] #### **1 Operadores Aritméticos**

---

>[!quote] **Def**
>`+` (Adição): 
>- Soma dois operandos. 
>  Ex: `a + b`
>  
>---
>  
>`-` (Subtração): 
>- Subtrai o segundo operando do primeiro. 
>  Ex: `a - b`
>  
>---
>  
>`*` (Multiplicação): 
>- Multiplica dois operandos. 
>  Ex: `a * b`
>  
>---
>
>`/` (Divisão): 
>- Se ambos forem inteiros, o resultado é a divisão inteira (truncada). 
>  Ex: `a / b`
>  
>---
>
>`%` (Módulo): 
>- Retorna o resto da divisão inteira. 
>  Ex: `a % b`
```
int x = 10;
int y = 3;
int soma = x + y; // soma = 13
int divisao = x / y; // divisao = 3 (divisão inteira)
int resto = x % y; // resto = 1
```

---

> [!tip] #### **2 Operadores de Atribuição**

---

>[!quote] **Def**
>`=` (Atribuição simples):
>- Atribui o valor do operando à direita ao operando à esquerda. 
>  Ex: `a = 10` 
>  
>---
>  
>`+=` (Atribuição com adição): 
>- `a += b` é equivalente a `a = a + b`
>  
>---
>  
>`-=` (Atribuição com subtração): 
>- `a -= b` é equivalente a `a = a - b`
>  
>---
>
>`*=` (Atribuição com multiplicação): 
>- `a *= b` é equivalente a `a = a * b`
>  
>---
>
>`/=` (Atribuição com divisão):
>- `a /= b` é equivalente a `a = a / b`
>  
>---
>
>`%=` (Atribuição com módulo):
>- `a %= b` é equivalente a `a = a % b`
```
int a = 5;
a += 3; // a agora é 8
a *= 2; // a agora é 16
```

---

> [!tip] #### **3 Operadores de Incremento e Decremento**

---

>[!quote] **Def**
>
>**`++` Incremento**
>- `a++` (Pós-incremento): Retorna o valor de `a` _antes_ de incrementá-lo.
>- `++a` (Pré-incremento): Incrementa `a` _e então_ retorna o novo valor.
>  
>---
>
>**`--` Decremento:**
>
>- `a--` (Pós-decremento): Retorna o valor de `a` _antes_ de decrementá-lo.
>- `--a` (Pré-decremento): Decrementa `a` _e então_ retorna o novo valor.
```
int i = 5;
int x = i++; // x = 5, i = 6
int y = ++i; // y = 7, i = 7
```

---

> [!tip] #### **4 Operadores Relacionais**

---

>[!quote] **Def**
>`==` **Igual a**
>- Verifica se dois operandos são iguais.
>  
>---
>  
>`!=` **Diferente de**
>- Verifica se dois operandos são diferentes.
>  
>---
>  
>`>` **Maior que**
>- Verifica se o primeiro operando é maior que o segundo.
>  
>---
>
>`<` **Menor que**
>- Verifica se o primeiro operando é menor que o segundo.
>  
>---
>
>`>=` **Maior ou igual a**
>- Verifica se o primeiro operando é maior ou igual ao segundo.
>  
>---
>
>`<=` **Menor ou igual a**
>- Verifica se o primeiro operando é menor ou igual ao segundo.
>  
>  
```
int a = 10;
int b = 5;
if (a > b) { // Verdadeiro
    printf("a é maior que b\n");
}
```

---

> [!tip] #### **5 Operadores Lógicos**

---

>[!quote] **Def**
>
>**`&&` AND lógico**
>- Retorna verdadeiro se ambas as expressões forem verdadeiras.
>  
>---
>
>**`||` OR lógico**
>
>- Retorna verdadeiro se pelo menos uma das expressões for verdadeira.
>  
>---
>`!` **NOT lógico**
>- Nega uma expressão. Se a expressão for verdadeira, retorna falso, e vice-versa.
```
int idade = 20;
char temCarteira = 1; // 1 representa verdadeiro

if (idade >= 18 && temCarteira) {
    printf("Pode dirigir\n");
}
```

---

> [!tip] #### **6 Operadores Bitwise**

---

>[!quote] **Def**
>`&` **AND bitwise**
>- Realiza um AND bit a bit entre dois operandos.
>  
>---
>  
>`|` **OR bitwise**
>- Realiza um OR bit a bit entre dois operandos.
>  
>---
>  
>`^` **XOR bitwise**
>- Realiza um XOR bit a bit entre dois operandos.
>  
>---
>
>`~` **NOT bitwise**
>- Inverte os bits de um operando.
>  
>---
>
>`<<` **Deslocamento à esquerda**
>- Desloca os bits de um operando para a esquerda.
>  
>---
>
>`>>` **Deslocamento à direita**
>- Desloca os bits de um operando para a direita.

---

> [!tip] #### **7 Operadores Especiais**

---
##### **Operador Condicional - Ternário**

>[!quote] **Def**
Uma forma concisa de escrever uma instrução `if-else`.
>- `condição ? expressão1 : expressão2`
>  
>---
>  
> Se a `condição` for verdadeira, a `expressão1` é avaliada; caso contrário, a `expressão2` é avaliada.

```
int maior = (a > b) ? a : b; // maior recebe o maior valor entre a e b
```

##### **Operadores de Endereço e Indireção**

>[!quote] **Def**
>**`&` Operador de endereço** 
>- Retorna o endereço de memória de uma variável.
>  
>---
>
>`*` **Operador de indireção ou dereferência** 
>- Acessa o valor armazenado em um endereço de memória (usado com ponteiros).

#### **Manipulação Modular %**

>[!quote] **Def**
>Separa o número contido na variável n.
```C
#include <stdio.h>
int main()
{
  int sum = 0;
  int n = 139;
  
    while (n > 0) {
        sum = n % 10; 
        n /= 10;      
        printf("%d", sum);
    }
}
```

---
