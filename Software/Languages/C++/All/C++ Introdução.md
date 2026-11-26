
---
#### **Introdução ao C++**

>[!quote] **Def**
>
>C++ é uma linguagem de programação poderosa e de alto desempenho que estende a linguagem C com recursos de programação orientada a objetos. É amplamente utilizada para desenvolvimento de sistemas/software, desenvolvimento de jogos e simulações em tempo real. O C++ permite tanto a manipulação de memória de baixo nível quanto abstrações de alto nível, tornando-a versátil para diversas aplicações.

---
#### **Inclusão de Bibliotecas**

>[!quote] **Def**
>
>Bibliotecas em C++ fornecem código pré-escrito que pode ser reutilizado para realizar tarefas comuns, como operações de entrada/saída, cálculos matemáticos e manipulação de strings. Para usar uma biblioteca, você inclui seu arquivo de cabeçalho no seu programa usando a diretiva `#include`.
>
```cpp

#include <iostream>  // Para operações de entrada/saída
#include <cmath>    // Para funções matemáticas

```

---
#### **Função Principal (Main)**

>[!quote] **Def**
>
>A função `main` é o ponto de entrada de qualquer programa em C++. É onde a execução do programa começa e termina. A função `main` deve retornar um valor inteiro, normalmente `0` para indicar execução bem-sucedida.
```cpp

int main() {  
// Seu código aqui  
return 0;  
}

```

---
#### **Entrada/Saída (Input/Output)**

>[!quote] **Def**
>
>As operações de entrada e saída (E/S) em C++ são realizadas usando a biblioteca `iostream`, que fornece os objetos `cin` e `cout` para ler a entrada do usuário e escrever a saída no console, respectivamente.

###### ***Entrada:***
```
cout << "Você digitou: " << numero << endl; // Saída
```
###### ***Saída:***
```
cin >> var; //Entra dados para a variável
```
###### ***Ex:***

```cpp

#include <iostream>  
using namespace std;

int main() {  
int numero;  
cout << "Digite um número: "; // Saída  
cin >> numero; // Entrada  
cout << "Você digitou: " << numero << endl; // Saída  
return 0;  
}

```

---
