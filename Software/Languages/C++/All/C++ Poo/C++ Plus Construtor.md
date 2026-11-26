
---
#### **Construtor Padrão**

>[!quote] **Def**
>O construtor padrão é o construtor que não recebe parâmetros. Ele é usado para inicializar um objeto com valores padrão ou deixar os atributos em um estado inicial válido.
>
>**Características:**
>
>**01 )** 
>
>- Não possui parâmetros.
>
>---
>**02 )**    
>- Se nenhum construtor for definido, o compilador gera um construtor padrão implicitamente.
>
>---
>**03 )**    
>- Pode ser explicitamente definido pelo programador.
###### ***Exemplo:***

```cpp
#include <iostream>
using namespace std;

class Exemplo {
private:
    int valor;

public:
    // Construtor padrão
    Exemplo() {
        valor = 0; // Inicialização padrão
        cout << "Construtor padrão chamado!" << endl;
    }

    void exibir() {
        cout << "Valor: " << valor << endl;
    }
};

int main() {
    Exemplo obj; // Construtor padrão é chamado
    obj.exibir();
    return 0;
}
```

---
#### **Uso de `this` em Construtores**

>[!quote] **Def**
>A palavra-chave `this` é um ponteiro que aponta para o objeto atual. Em construtores, ela é usada para resolver ambiguidades quando os nomes dos parâmetros são iguais aos nomes dos atributos da classe.
>
>**Características:**
>
>**01 )** 
>
>- `this` é um ponteiro para o objeto atual.
>  
>---
>**02 )**    
>- Útil para diferenciar entre atributos da classe e parâmetros com o mesmo nome.
###### ***Exemplo:***

```cpp
#include <iostream>
using namespace std;

class Exemplo {
private:
    int valor;

public:
    // Construtor usando 'this'
    Exemplo(int valor) {
        this->valor = valor; // 'this->valor' refere-se ao atributo da classe
        cout << "Construtor com 'this' chamado!" << endl;
    }

    void exibir() {
        cout << "Valor: " << valor << endl;
    }
};

int main() {
    Exemplo obj(42); // Construtor com 'this' é chamado
    obj.exibir();
    return 0;
}
```

---
#### **Lista de Inicialização**

>[!quote] **Def**
>A lista de inicialização é uma forma eficiente de inicializar os atributos de uma classe diretamente no construtor, antes do corpo do construtor ser executado. Ela é especialmente útil para inicializar atributos constantes (`const`) ou referências, que não podem ser inicializados no corpo do construtor.
>
>**Características:**
>
>**01 )**
>
>- A lista de inicialização é colocada após os parâmetros do construtor, separada por dois-pontos (`:`).
>  
>---
>**02 )**  
>- A ordem de inicialização segue a ordem de declaração dos atributos na classe, não a ordem na lista de inicialização.
>  
>---
> **03 )**
> - Mais eficiente do que atribuir valores no corpo do construtor, pois evita a inicialização padrão seguida de atribuição.
###### ***Exemplo:***

```cpp
#include <iostream>
using namespace std;

class Exemplo {
private:
    int valor;

public:
    // Construtor usando 'this'
    Exemplo(int valor) {
        this->valor = valor; // 'this->valor' refere-se ao atributo da classe
        cout << "Construtor com 'this' chamado!" << endl;
    }

    void exibir() {
        cout << "Valor: " << valor << endl;
    }
};

int main() {
    Exemplo obj(42); // Construtor com 'this' é chamado
    obj.exibir();
    return 0;
}
```


---

>[!tip] ### **Comparação entre Inicialização no Corpo e Lista de Inicialização**

---

>[!quote] **Def**
>A lista de inicialização é uma forma eficiente de inicializar os atributos de uma classe diretamente no construtor, antes do corpo do construtor ser executado. Ela é especialmente útil para inicializar atributos constantes (`const`) ou referências, que não podem ser inicializados no corpo do construtor.
>
>**Características:**
>
>**01 )** Evita a inicialização padrão seguida de atribuição.
>
>- Evita a inicialização padrão seguida de atribuição.
>  
>---
>**02 )** **Obrigatório para `const` e referências**:
>- Atributos `const` e referências só podem ser inicializados na lista de inicialização.
>  
>---
> **03 )** **Ordem de inicialização clara**:
> - A ordem de inicialização é explícita e segue a declaração dos atributos.

---
##### **Inicialização no Corpo do Construtor:**

```cpp
class Exemplo {
private:
    int valor;

public:
    Exemplo(int v) {
        valor = v; // Atribuição no corpo do construtor
    }
};
```

---
##### **Lista de Inicialização:**

```cpp
class Exemplo {
private:
    int valor;

public:
    Exemplo(int v) {
        valor = v; // Atribuição no corpo do construtor
    }
};
```

---
#### **Exemplo Completo com Todos os Tipos de Construtores**

```cpp
#include <iostream>
using namespace std;

class Exemplo {
private:
    int valor;
    const int constante;
    int& referencia;

public:
    // Construtor padrão
    Exemplo() : valor(0), constante(100), referencia(valor) {
        cout << "Construtor padrão chamado!" << endl;
    }

    // Construtor parametrizado com lista de inicialização
    Exemplo(int valor, int& ref) : valor(valor), constante(200), referencia(ref) {
        cout << "Construtor parametrizado chamado!" << endl;
    }

    // Construtor usando 'this'
    Exemplo(int valor) {
        this->valor = valor;
        this->referencia = valor; // Referência deve ser inicializada na lista
        cout << "Construtor com 'this' chamado!" << endl;
    }

    void exibir() {
        cout << "Valor: " << valor << ", Constante: " << constante
             << ", Referência: " << referencia << endl;
    }
};

int main() {
    int ref = 50;
    Exemplo obj1; // Construtor padrão
    Exemplo obj2(42, ref); // Construtor parametrizado
    Exemplo obj3(10); // Construtor com 'this'

    obj1.exibir();
    obj2.exibir();
    obj3.exibir();

    return 0;
}
```

---