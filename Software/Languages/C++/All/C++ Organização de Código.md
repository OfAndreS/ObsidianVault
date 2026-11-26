
---
#### **Boas Práticas**

>[!quote] **Def**
>**DRY (Don't Repeat Yourself)**: 
>- Evite duplicação de código.
>  
>---
>  
>**KISS (Keep It Simple, Stupid)**: 
>- Mantenha o código simples e direto.
>  
>---
>
>**Comentários e Documentação**: 
>- Use comentários para explicar o código e gere documentação com ferramentas como Doxygen.
>  
>---
>  
>**Testes**: 
>- Escreva testes unitários para garantir a qualidade do código.
#### **Ferramentas de Apoio**

>[!quote] **Def**
>**Linters**:
>- Ferramentas como `clang-tidy` ajudam a manter o código limpo.
>  
>---
>  
>**Formatters**:
>- Use ferramentas como `clang-format` para padronizar o estilo do código.
>  
>---
>
>**IDEs**: 
>- Utilize IDEs como Visual Studio, CLion ou Code::Blocks para facilitar a organização e desenvolvimento.
>  

---

>[!tip] ### **Organização de Código**

---
#### **Estrutura Básica de um Projeto em C++**

>[!quote] **Def:**
>Um projeto em C++ geralmente é organizado em dois tipos de arquivos:
> 
>**Arquivos de Cabeçalho (`.h` ou `.hpp`)**:
>- Contêm declarações de classes, funções, variáveis globais, macros e diretivas de pré-processador.
>
>---
>  
>**Arquivos de Implementação (`.cpp`)**:
>- Contêm a implementação das funções e métodos declarados nos arquivos de cabeçalho.
>

```
/projeto
    /include
        minhaClasse.hpp
    /src
        minhaClasse.cpp
    main.cpp
```

---
#### **Separação de Interface e Implementação**

>[!quote] **Def:**
> 
>**Interface**:
>- Declarações de classes, funções e variáveis são colocadas em arquivos de cabeçalho (`.hpp`).
>
>---
>  
>**Implementação**:
>- A definição das funções e métodos é colocada em arquivos de implementação (`.cpp`).

```cpp
// minhaClasse.hpp
class MinhaClasse {
public:
    void metodo();
};

// minhaClasse.cpp
#include "minhaClasse.hpp"
void MinhaClasse::metodo() {
    // Implementação
}
```

---
#### **Uso de `#include` e Inclusão de Headers**

>[!quote] **Def:**
> 
>**`#include`**:
>- Usado para incluir arquivos de cabeçalho em outros arquivos.
>
>---
>  
>**Evitar Inclusões Redundantes**:
>- Use `#pragma once` ou include guards para evitar múltiplas inclusões do mesmo arquivo.
###### ***Exemplo com `#pragma once`:***

```cpp
// minhaClasse.hpp
#pragma once
class MinhaClasse {
    // ...
};
```
###### ***Exemplo com include guards:***

```cpp
// minhaClasse.hpp
#ifndef MINHA_CLASSE_HPP
#define MINHA_CLASSE_HPP
class MinhaClasse {
    // ...
};
#endif
```

---
#### **Namespaces**

>[!quote] **Def:**
> 
>Namespaces ajudam a organizar o código e evitar conflitos de nomes.

```cpp
//Exemplo
namespace MeuNamespace {
    class MinhaClasse {
        // ...
    };
}

//Implementação
MeuNamespace::MinhaClasse obj;
```

---
#### **Modularização**

>[!quote] **Def:**
> 
>**Função:**
>- Divida o código em módulos lógicos, cada um com seus próprios arquivos de cabeçalho e implementação.
>
>---
>  
>**Exemplo de módulos**:
>- `math.hpp` e `math.cpp` para funções matemáticas.
>- `utils.hpp` e `utils.cpp` para utilitários gerais.

---
#### **Variáveis Globais e `extern`**

>[!quote] **Def:**
> 
>Variáveis globais devem ser evitadas, mas, quando necessárias, declare-as com `extern` no arquivo de cabeçalho e defina-as em um arquivo `.cpp`.

```cpp
// globais.hpp
extern int contador;

// globais.cpp
int contador = 0;
```

---
#### **Funções `inline`**

>[!quote] **Def:**
> 
>- Funções pequenas e frequentemente usadas podem ser declaradas como `inline` para otimização.
>
>---
>  
>- A implementação de funções `inline` geralmente fica no arquivo de cabeçalho.

```cpp
// math.hpp
inline int soma(int a, int b) {
    return a + b;
}

// Implementação
soma(a, b);
```

---
#### **Organização de Classes**

>[!quote] **Def:**
> 
>- Declare classes em arquivos de cabeçalho e implemente métodos em arquivos `.cpp`.
>
>---
>  
>- Use métodos `public`, `private` e `protected` para encapsulamento.

```cpp
// minhaClasse.hpp
class MinhaClasse {
private:
    int valor;
public:
    void setValor(int v);
    int getValor() const;
};

// minhaClasse.cpp
#include "minhaClasse.hpp"
void MinhaClasse::setValor(int v) {
    valor = v;
}
int MinhaClasse::getValor() const {
    return valor;
}
```

---
#### **Uso de Bibliotecas Externas**

>[!quote] **Def:**
> 
>- Inclua bibliotecas externas usando `#include` e, se necessário, configure caminhos de bibliotecas no sistema de build.
>

```cpp
#include <iostream>  // Biblioteca padrão
#include "minhaBiblioteca.hpp"  // Biblioteca local
```

---
#### **Makefiles e Sistemas de Build**

>[!quote] **Def:**
> 
>- Use ferramentas como **Make**, **CMake**, ou sistemas de build integrados em IDEs para compilar e linkar o projeto.

```cpp
CXX = g++
CXXFLAGS = -std=c++17 -Wall
TARGET = meuPrograma

$(TARGET): main.o minhaClasse.o
    $(CXX) $(CXXFLAGS) -o $(TARGET) main.o minhaClasse.o

main.o: main.cpp minhaClasse.hpp
    $(CXX) $(CXXFLAGS) -c main.cpp

minhaClasse.o: minhaClasse.cpp minhaClasse.hpp
    $(CXX) $(CXXFLAGS) -c minhaClasse.cpp

clean:
    rm -f *.o $(TARGET)
```

---
