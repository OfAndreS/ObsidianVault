
----

>[!tip] ### **Modificadores de Tamanho e Sinal**

---
#### **Modificador `singed`**

>[!quote] **`signed`**: Indica que um tipo pode armazenar valores positivos e negativos (padrão para `int`, `char`, etc.).

```cpp
signed int x = -10; // equivalente a int x = -10;
```

---
#### **Modificador `unsigned`**

> [!quote] **`unsigned`**: Indica que um tipo só armazena valores não negativos (apenas positivos).

```cpp
unsigned int y = 42; // só pode armazenar valores >= 0
```

---
#### **Modificador `short`**

> [!quote] **`short`**: Reduz o tamanho de um tipo (geralmente pela metade).

```cpp
short int z = 100; // usa menos memória que um int normal
```

---
#### **Modificador `long`**

> [!quote] **`long`**: Aumenta o tamanho de um tipo.

```cpp
long int w = 1000000; // pode armazenar valores maiores
```

---

>[!tip] ### **Modificadores de Precisão**

---
#### **Modificador `double`**

> [!quote] **`double`**: Aumenta a precisão de um número de ponto flutuante.

```cpp
long int w = 1000000; // pode armazenar valores maiores
```

---
#### **Modificador `long double`**

> [!quote] **`long double`**: Aumenta ainda mais a precisão.

```cpp

```

---

>[!tip] ### **Modificadores de Acesso**

---
#### **Modificador `public`**

> [!quote] **`public`**: Membros são acessíveis de qualquer lugar.

```cpp
class Exemplo {
public:
    int x; // Acessível de fora da classe
};
```

---
#### **Modificador `private`**

> [!quote] **`private`**: Membros só são acessíveis dentro da própria classe.

```cpp
class Exemplo {
private:
    int y; // Só acessível dentro da classe
};
```

---
#### **Modificador `protected`**

> [!quote] **`protected`**: Membros são acessíveis dentro da classe e por classes derivadas.

```cpp
class Exemplo {
protected:
    int z; // Acessível na classe e em classes filhas
};
```


---
#### **Modificador `friend`**

> [!quote] **`friend`**: Permite que uma função ou classe acesse membros privados de outra classe.

```cpp
class Amiga {
    friend void funcaoAmiga(Amiga& a);
private:
    int segredo;
};

void funcaoAmiga(Amiga& a) {
    a.segredo = 42; // Acesso permitido
}
```

---

>[!tip] ### **Modificadores de Funções**

---
#### **Modificador `inline`**

> [!quote] **`inline`**: Sugere ao compilador substituir a chamada da função pelo seu corpo (para otimização).

```cpp
inline int soma(int a, int b) {
    return a + b;
}
```

---
#### **Modificador `const`**

> [!quote] **`const`**: Indica que a função não modifica o estado do objeto (em métodos de classe).

```cpp
class Exemplo {
public:
    int getValor() const {
        return valor; // Não modifica o objeto
    }
private:
    int valor;
};
```

>[!quote] **Vault:** [[C++ Mdf Const]]

---
#### **Modificador `static`**

> [!quote] **`static`**: Define uma função como pertencente à classe, e não a instâncias específicas.

```cpp
class Exemplo {
public:
    static void metodoEstatico() {
        // Pode ser chamado sem instanciar a classe
    }
};
```

---
#### **Modificador `virtual`**

> [!quote] **`virtual`**: Permite que uma função seja sobrescrita em classes derivadas (polimorfismo).

```cpp
class Base {
public:
    virtual void metodo() {
        cout << "Base" << endl;
    }
};
```

---
#### **Modificador `override`**

> [!quote] **`override`**: Indica que uma função está sobrescrevendo uma função virtual da classe base.

```cpp
class Derivada : public Base {
public:
    void metodo() override {
        cout << "Derivada" << endl;
    }
};
```

---
#### **Modificador `final`**

> [!quote] **`final`**: Impede que uma função seja sobrescrita em classes derivadas.

```cpp
class Derivada : public Base {
public:
    void metodo() final {
        cout << "Não pode ser sobrescrito" << endl;
    }
};
```

---

>[!tip] ### **Modificadores de Variáveis**

---
#### **Modificador `const`**

> [!quote] **`const`**: Indica que o valor da variável não pode ser alterado após a inicialização.

```cpp
const int x = 10;
// x = 20; // Erro: x é constante
```

>[!quote] **Vault:** [[C++ Mdf Const]]

---
#### **Modificador `static`**

> [!quote] **`static`**: Define uma variável como global para a classe ou função, mantendo seu valor entre chamadas.

```cpp
void funcao() {
    static int contador = 0;
    contador++;
    cout << contador << endl;
}
```

---
#### **Modificador `volatile`**

> [!quote] **`volatile`**: Indica que o valor da variável pode ser alterado fora do controle do programa (usado em hardware ou multithreading).

```cpp
volatile int sensorValue;
```

---
#### **Modificador `mutable`**

> [!quote] **`mutable`**: Permite que um membro de uma classe seja modificado mesmo em um objeto `const`.

```cpp
class Exemplo {
public:
    mutable int contador;
    void metodo() const {
        contador++; // Permitido, mesmo em método const
    }
};
```

---

>[!tip] ### **Modificadores de Armazenamento**

---
#### **Modificador `auto`**

> [!quote] **`auto`**: Define uma variável com tipo automático (inferido pelo compilador).

```cpp
auto x = 10; // x é do tipo int
```

---
#### **Modificador `register`**

> [!quote] **`register`**: Sugere ao compilador armazenar a variável em um registrador (obsoleto em C++ moderno).

```cpp
register int y = 20;
```

---
#### **Modificador `extern`**

> [!quote] **`extern`**: Indica que a variável é declarada em outro arquivo.

```cpp
extern int globalVar; // Definida em outro arquivo
```

---
