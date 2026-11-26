
---

```ad-quote
title: **Def**

O qualificador `const` em C++ é uma ferramenta poderosa que permite especificar que um objeto ou variável não pode ser modificado após sua inicialização. Ele é fundamental para escrever código mais seguro, expressivo e otimizado.
```

---

```ad-example
#### **Conceitos Básicos**
```

---
#### **2 )** _Variáveis constantes_

```cpp
const int max_size = 100;
max_size = 200; // Erro de compilação - não pode modificar uma constante
```

---
#### **2 )** _Ponteiros constantes_

```ad-quote
title: **Def**

Há duas formas principais:
```

```cpp
const int* ptr = &max_size;
*ptr = 50; // Erro - dados são constantes
```

>[!quote] Ponteiro para constante (dados não podem ser modificados)

```cpp
int* const ptr = &var;
ptr = &outra_var; // Erro - ponteiro é constante
```

>[!quote] Ponteiro constante (ponteiro não pode apontar para outro lugar)

---
#### **3 )** _Referências constantes_

```cpp
const int& ref = max_size;
ref = 30; // Erro - referência para constante
```

---
## Uso em Funções

### 1. Parâmetros constantes
```cpp
void printValue(const int value) {
    // value não pode ser modificado dentro da função
    cout << value;
}
```

### 2. Retorno constante
```cpp
const int getMaxValue() {
    return 100;
}
```

## Uso com Membros de Classe

### 1. Membros de dados constantes
```cpp
class MyClass {
    const int id;
public:
    MyClass(int i) : id(i) {} // Deve ser inicializado na lista de inicialização
};
```

### 2. Métodos constantes
```cpp
class MyClass {
    int value;
public:
    int getValue() const { // Promete não modificar o objeto
        return value;
    }
};
```

### 3. Objetos constantes
```cpp
const MyClass obj(10);
obj.getValue(); // OK - método é const
// obj.setValue(20); // Erro - objeto é const
```

## `constexpr` (C++11 em diante)

`constexpr` indica que o valor pode ser calculado em tempo de compilação:
```cpp
constexpr int square(int x) {
    return x * x;
}

constexpr int val = square(10); // Calculado em tempo de compilação
```

## Vantagens do uso de `const`

1. **Segurança**: Previne modificações acidentais
2. **Clareza**: Documenta a intenção no código
3. **Otimização**: Compilador pode fazer otimizações melhores
4. **Thread-safety**: Dados constantes são implicitamente thread-safe

## Casting de constantes

Às vezes é necessário remover a constância (use com cautela!):
```cpp
const int x = 10;
int* y = const_cast<int*>(&x); // Removendo o const
```

## Palavra-chave `mutable`

Permite que membros de classe sejam modificados mesmo em métodos const:
```cpp
class Counter {
    mutable int cache;
public:
    int getCount() const {
        cache++; // Permitido apesar de ser método const
        return cache;
    }
};
```

O uso apropriado de `const` é uma das práticas mais importantes para escrever código C++ robusto e mantenível.