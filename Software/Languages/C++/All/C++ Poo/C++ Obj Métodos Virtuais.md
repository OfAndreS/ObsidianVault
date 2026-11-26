
---

```ad-example

#### **Polimorfismo, Métodos Virtuais e Classes Abstratas em C++**
```

---

```ad-quote
title: **Def**

Em C++, o polimorfismo em tempo de execução (ou polimorfismo dinâmico) é um dos pilares da Programação Orientada a Objetos. Ele é alcançado principalmente através do uso de **ponteiros (ou referências) para a classe base** e **métodos virtuais**. Isso permite que uma chamada de método em um objeto seja resolvida em tempo de execução, em vez de em tempo de compilação, garantindo que a versão correta do método (da classe derivada) seja executada.
```

---

```ad-example

#### **Métodos Virtuais**
```

---

```ad-quote
title: **Def**

Um **método virtual** é uma função membro em uma classe base que você espera que seja **sobrescrita** em classes derivadas. Ao declarar um método como `virtual` na classe base, você informa ao compilador que a decisão sobre qual implementação do método chamar deve ser adiada até o tempo de execução. Isso é conhecido como **ligação tardia** (late binding) ou **despacho dinâmico** (dynamic dispatch).
```

---

#### **01 )** - Sobrescrita de Métodos com `override`

```ad-quote
title: **Def**

Quando uma classe derivada fornece sua própria implementação para um método virtual da classe base, ela está **sobrescrevendo** (overriding) esse método. Para garantir a clareza e evitar erros, o C++ moderno (a partir do C++11) introduziu o especificador `override`. Usar `override` informa explicitamente ao compilador que a função deve sobrescrever um método virtual da classe base. Se não houver um método correspondente para sobrescrever, o compilador gerará um erro.
```

---

> [!example] **_Exemplo C++:_**

---

```cpp
#include <iostream>
#include <string>
#include <vector>

// Classe Base
class Animal {
public:
    std::string nome;

    Animal(const std::string& n) : nome(n) {}

    // Método virtual que pode ser sobrescrito pelas classes derivadas
    virtual void fazer_som() const {
        std::cout << nome << " faz um som genérico..." << std::endl;
    }
    
    // Um destrutor virtual é crucial ao usar polimorfismo com ponteiros.
    virtual ~Animal() {} 
};

// Classe Derivada
class Cachorro : public Animal {
public:
    Cachorro(const std::string& n) : Animal(n) {}

    // Sobrescrevendo o método da classe base. 'override' é uma boa prática.
    void fazer_som() const override {
        std::cout << nome << " faz: Au au!" << std::endl;
    }
};

// Outra Classe Derivada
class Gato : public Animal {
public:
    Gato(const std::string& n) : Animal(n) {}

    // Sobrescrevendo o método da classe base.
    void fazer_som() const override {
        std::cout << nome << " faz: Miau!" << std::endl;
    }
};

// Função polimórfica que funciona com qualquer objeto derivado de Animal
void emitir_som(const Animal* animal) {
    animal->fazer_som(); // A chamada correta (Cachorro::fazer_som ou Gato::fazer_som) é decidida em tempo de execução
}

int main() {
    Animal* a = new Animal("Bicho");
    Cachorro* c = new Cachorro("Rex");
    Gato* g = new Gato("Mia");

    std::cout << "Chamada direta:" << std::endl;
    c->fazer_som();
    g->fazer_som();

    std::cout << "\nChamada polimórfica:" << std::endl;
    emitir_som(a);
    emitir_som(c); // Ponteiro de Cachorro é tratado como Ponteiro de Animal
    emitir_som(g); // Ponteiro de Gato é tratado como Ponteiro de Animal

    // Limpando a memória
    delete a;
    delete c;
    delete g;

    return 0;
}
```

---

```ad-example

#### **Classes Abstratas e Métodos Virtuais Puros**
```

---

```ad-quote
title: **Def: Método Virtual Puro**

Um **método virtual puro** (pure virtual function) é um método virtual que a classe base não implementa. Ele é declarado atribuindo `= 0;` à sua declaração. Qualquer classe que contenha um ou mais métodos virtuais puros se torna uma **classe abstrata**.
```

```ad-quote
title: **Def: Classe Abstrata**

Uma **classe abstrata** atua como um **contrato** ou uma **interface**. Ela não pode ser instanciada diretamente. Seu propósito é servir como uma classe base para que outras classes derivem dela e forneçam implementações concretas para seus métodos virtuais puros. Isso força as classes derivadas a aderirem à interface definida pela classe abstrata.
```

---

> [!example] **_Exemplo C++:_**

---

```cpp
#include <iostream>
#include <string>

// 'Forma' é uma classe abstrata porque contém um método virtual puro.
class Forma {
public:
    // Método virtual puro. Toda classe derivada DEVE implementar calcular_area().
    virtual double calcular_area() const = 0; 
    
    // Classes abstratas ainda podem ter métodos normais e construtores/destrutores.
    virtual ~Forma() { std::cout << "Destrutor da Forma chamado." << std::endl; }
};

class Circulo : public Forma {
private:
    double raio;
public:
    Circulo(double r) : raio(r) {}

    // Implementação obrigatória do método virtual puro.
    double calcular_area() const override {
        return 3.14159 * raio * raio;
    }
};

class Retangulo : public Forma {
private:
    double largura, altura;
public:
    Retangulo(double l, double a) : largura(l), altura(a) {}

    // Implementação obrigatória.
    double calcular_area() const override {
        return largura * altura;
    }
};


int main() {
    // Forma f; // ERRO DE COMPILAÇÃO! Não se pode instanciar uma classe abstrata.

    Forma* c = new Circulo(10.0);
    Forma* r = new Retangulo(5.0, 4.0);
    
    std::cout << "Área do Círculo: " << c->calcular_area() << std::endl;
    std::cout << "Área do Retângulo: " << r->calcular_area() << std::endl;

    delete c;
    delete r;

    return 0;
}
```

---

```ad-example

#### **Destrutores Virtuais**
```

---

```ad-quote
title: **Def**

Ao trabalhar com herança e polimorfismo, é **essencial declarar o destrutor da classe base como `virtual`**. Se você deletar um objeto de uma classe derivada através de um ponteiro para a classe base e o destrutor da base **não for virtual**, apenas o destrutor da classe base será chamado. Isso causa um **vazamento de memória** (memory leak), pois os recursos alocados pela classe derivada nunca são liberados.
```

```ad-quote
title: **Regra de Ouro**

Se uma classe tem **pelo menos um método virtual**, ela deve ter um **destrutor virtual**, mesmo que ele não faça nada. Isso garante que a cadeia de destruição correta seja chamada ao deletar objetos polimorficamente.
```

---

> [!example] **_Exemplo C++:_**

---

```cpp
#include <iostream>

class Base {
public:
    Base() { std::cout << "Construtor da Base\n"; }
    
    // Sem 'virtual' aqui, o destrutor da Derivada não seria chamado no 'delete b'.
    virtual ~Base() { std::cout << "Destrutor da Base\n"; } 
};

class Derivada : public Base {
private:
    int* _dados;
public:
    Derivada() { 
        _dados = new int[10]; // Alocando recursos
        std::cout << "Construtor da Derivada (recursos alocados)\n"; 
    }
    
    ~Derivada() { 
        delete[] _dados; // Liberando recursos
        std::cout << "Destrutor da Derivada (recursos liberados)\n"; 
    }
};

int main() {
    std::cout << "Criando objeto Derivada através de um ponteiro da Base...\n";
    
    // Ponteiro da classe base apontando para um objeto da classe derivada
    Base* b = new Derivada(); 

    std::cout << "\nDeletando o objeto através do ponteiro da Base...\n";
    delete b; // Graças ao destrutor virtual, o destrutor de Derivada é chamado primeiro, depois o de Base.
    
    std::cout << "\nSe ~Base() não fosse virtual, a mensagem 'Destrutor da Derivada' não apareceria e teríamos um vazamento de memória.\n";

    return 0;
}
```

---
