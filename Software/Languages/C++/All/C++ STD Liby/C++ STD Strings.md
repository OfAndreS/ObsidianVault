
---

>[!tip] ### **Concatenação de Strings C++**

---
#### **Operador `+`**

>[!quote] O operador `+` é usado para concatenar duas strings.

```cpp
std::string str1 = "Olá, ";
std::string str2 = "mundo!";
std::string str3 = str1 + str2; // Concatena str1 e str2

std::cout << str3 << std::endl; // Saída: Olá, mundo!
```

---
#### **Função `append()`**

>[!quote] A função `append()` adiciona uma string ao final de outra.

```cpp
std::string str1 = "Olá, ";
std::string str2 = "mundo!";
str1.append(str2); // Adiciona str2 ao final de str1

std::cout << str1 << std::endl; // Saída: Olá, mundo!
```

---

>[!tip] ### **Acesso a Caracteres C++**

---
#### **Operador `[]`**

>[!quote] O operador `[]` permite acessar um caractere específico da string por índice.

```cpp
std::string str = "C++";
char c = str[0]; // Acessa o primeiro caractere ('C')

std::cout << c << std::endl; // Saída: C
```

---
#### **Função `at()`**

>[!quote] A função `at()` faz o mesmo que o operador `[]`, mas com verificação de limites. Se o índice estiver fora dos limites, lança uma exceção (`std::out_of_range`).

```cpp
std::string str = "C++";
char c = str.at(1); // Acessa o segundo caractere ('+')

std::cout << c << std::endl; // Saída: +
```

---

>[!tip] ### **Tamanho da String C++**

---
#### **Função `size()`**

>[!quote] Retorna o número de caracteres na string.

```cpp
std::string str = "C++";
std::cout << "Tamanho: " << str.size() << std::endl; // Saída: 3
```

---
#### **Função `length()`**

>[!quote] Faz o mesmo que `size()`, retornando o número de caracteres.

```cpp
std::string str = "C++";
std::cout << "Comprimento: " << str.length() << std::endl; // Saída: 3
```

---

>[!tip] ### **Substring C++**

---
#### **Função `substr()`**

>[!quote] Extrai uma parte da string, começando em uma posição específica e com um comprimento opcional.

```cpp
std::string str = "Programação C++";
std::string sub = str.substr(0, 11); // Extrai "Programação"

std::cout << sub << std::endl; // Saída: Programação
```

---

>[!tip] ### **Busca em Strings C++**

---
#### **Função `find()`**

>[!quote] Busca uma substring ou caractere na string e retorna a posição da primeira ocorrência. Se não encontrar, retorna `std::string::npos`.

```cpp
std::string str = "C++ é poderoso!";
size_t pos = str.find("poderoso"); // Busca "poderoso"

if (pos != std::string::npos) {
    std::cout << "Encontrado na posição: " << pos << std::endl; // Saída: Encontrado na posição: 7
} else {
    std::cout << "Não encontrado" << std::endl;
}
```

---
#### **Função `rfind()`**

>[!quote] Faz a mesma coisa que `find()`, mas começa a busca a partir do final da string.

```cpp
std::string str = "C++ é poderoso!";
size_t pos = str.find("poderoso"); // Busca "poderoso"

if (pos != std::string::npos) {
    std::cout << "Encontrado na posição: " << pos << std::endl; // Saída: Encontrado na posição: 7
} else {
    std::cout << "Não encontrado" << std::endl;
}
```

---

>[!tip] ### **Modificação de Strings C++**

---
#### **Função `replace()`**

>[!quote] Substitui uma parte da string por outra string.

```cpp
std::string str = "C++ é legal!";
str.replace(4, 2, "muito"); // Substitui "é" por "muito"

std::cout << str << std::endl; // Saída: C++ muito legal!
```

---
#### **Função `insert()`**

>[!quote] Insere uma string em uma posição específica.

```cpp
std::string str = "C++ legal!";
str.insert(4, "é "); // Insere "é " na posição 4

std::cout << str << std::endl; // Saída: C++ é legal!
```

---
#### **Função `erase()`**

>[!quote] Remove uma parte da string.

```cpp
std::string str = "C++ é legal!";
str.erase(4, 3); // Remove "é "

std::cout << str << std::endl; // Saída: C++ legal!
```

---

>[!tip] ### **Manipulação de Caracteres C++**

---
#### **`isalpha()`**

>[!quote] Verifica se um caractere é uma letra.

```cpp
char c = 'A';
if (std::isalpha(c)) {
    std::cout << "É uma letra!" << std::endl;
}
```

---
#### **`toupper()` e `tolower()`**

>[!quote] Converte um caractere para maiúscula ou minúscula.

```cpp
char c = 'a';
c = std::toupper(c); // Converte para 'A'
std::cout << c << std::endl; // Saída: A
```

---

>[!tip] ### **Conversões C++**

---
#### **Conversão para C-string**

>[!quote] A função `c_str()` converte uma `std::string` em uma C-string (`const char*`).

```cpp
std::string str = "C++";
const char* cstr = str.c_str();

std::cout << cstr << std::endl; // Saída: C++
```

---
#### **Conversão de Números para Strings / Casting String**

>[!quote] A função `std::to_string()` converte números em strings.

```cpp
int num = 42;
std::string str = std::to_string(num);

std::cout << str << std::endl; // Saída: 42
```

---
#### **Conversão de Strings para Números**

>[!quote] Funções como `std::stoi()`, `std::stol()`, `std::stod()` convertem strings em números.

```cpp
std::string str = "123";
int num = std::stoi(str); // Converte para int

std::cout << num + 1 << std::endl; // Saída: 124
```

---

>[!tip] ### **Iteração sobre Strings C++**

---
#### **Usando Índices**

```cpp
std::string str = "C++";
for (size_t i = 0; i < str.size(); ++i) {
    std::cout << str[i] << " ";
}
// Saída: C + +
```

#### **Usando Iteradores**

```cpp
for (auto it = str.begin(); it != str.end(); ++it) {
    std::cout << *it << " ";
}
// Saída: C + +
```

#### **Usando Range-based for (C++11)**

```cpp
for (char c : str) {
    std::cout << c << " ";
}
// Saída: C + +
```

---

>[!tip] ### **Exemplo Completo C++**

---

```cpp
#include <iostream>
#include <string>
#include <cctype>

int main() {
    std::string str = "Programação C++";

    // Tamanho da string
    std::cout << "Tamanho: " << str.size() << std::endl;

    // Acesso a caracteres
    std::cout << "Primeiro caractere: " << str[0] << std::endl;

    // Substring
    std::string sub = str.substr(0, 11);
    std::cout << "Substring: " << sub << std::endl;

    // Conversão para maiúsculas
    for (char& c : str) {
        c = std::toupper(c);
    }
    std::cout << "String em maiúsculas: " << str << std::endl;

    // Busca
    size_t pos = str.find("C++");
    if (pos != std::string::npos) {
        std::cout << "Encontrado na posição: " << pos << std::endl;
    }

    return 0;
}
```

---
