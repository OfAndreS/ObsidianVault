
---

>[!quote] Referências são uma evolução simplificada dos ponteiros.

![[Pasted image 20250302204204.png]]

>[!quote] **Def**
>Uma referência em C++ é um **alias** para uma variável já existente. Isso significa que, ao criar uma referência, você está criando um novo nome para acessar o mesmo espaço de memória da variável original. Uma vez que uma referência é inicializada, ela **não pode ser alterada** para referenciar outra variável.
>
>**Sendo:**
>
>**01 )**
>- `& ref` é uma referência para `x`.
>  
>---
>
>**02 )**  
>- Qualquer modificação em `ref` afetará `x`, e vice-versa.
>  
>--- 
>
>**03 )**  
>- `ref` e `x` compartilham o mesmo espaço de memória.

```
int x = 10;
int& ref = x;  // ref é uma referência para x
```

---
#### **Inicialização de Referências**

>[!quote] **Def**
>
>
>**Referências devem ser inicializadas no momento da declaração.**
>- Não é possível declarar uma referência sem inicializá-la.
>  
>---
>
>**Referências não podem ser nulas.**
>- Elas devem sempre referenciar um objeto válido. Isso as torna mais seguras do que ponteiros, que podem ser nulos.
>  
>--- 
>
>**Referências não podem ser reatribuídas.**
>- Uma vez que uma referência é inicializada, ela não pode ser alterada para referenciar outro objeto.
###### ***Exemplo:***

```cpp
int y = 20;
int& ref2;  // Erro: referência não inicializada
int& ref2 = y;  // Correto


```
###### ***Exemplo:***

```cpp
int a = 5;
int b = 10;
int& ref = a;
ref = b;  // Isso não faz ref referenciar b; apenas atribui o valor de b a a.
```

---
#### **Referências Constantes**

>[!quote] **Def**
>
>
>Referências constantes são usadas para garantir que o valor referenciado não seja modificado através da referência. Elas são úteis para:
>  
>
>**01 )**
>- Passar argumentos para funções sem permitir modificações.
>  
>--- 
>
>**02 )**
>- Estender a vida de objetos temporários.
###### ***Referência para uma variável constante:***

```cpp
const int z = 40;
const int& ref3 = z;

// ref3 é uma referência constante para z
ref3 = 50;  
// Erro: não é possível modificar uma referência constante
```
###### ***Referência a um valor temporário:***

```cpp


const int& ref4 = 100;  
// Referência constante para um valor temporário


```
---
#### **Passagem de Argumentos por Referência**

>[!quote] **Def**
>
>
Passar argumentos por referência é uma técnica comum em C++ para:
>  
>
>**01 )**
>- Evitar a cópia de objetos grandes.
>  
>--- 
>
>**02 )**
>- Permitir que funções modifiquem os valores originais.
###### ***Evitar cópia de objetos grandes:***

```cpp
void printValue(const int& ref) {
    std::cout << ref << std::endl;
}

//Implementação

int a = 10;
printValue(a);  // Passa 'a' por referência (sem cópia)
```
###### ***Modificar argumentos:***

```cpp
void increment(int& ref) {
    ref++;
}

//Implementação

int b = 5;
increment(b);  // b agora é 6
```

---
#### **Referências e Polimorfismo

>[!quote] **Def**
>
>
Referências podem ser usadas para implementar polimorfismo, permitindo que uma referência a uma classe base aponte para um objeto de uma classe derivada.

```cpp

class Base {
public:
    virtual void print() {
        std::cout << "Base" << std::endl;
    }
};

class Derived : public Base {
public:
    void print() override {
        std::cout << "Derived" << std::endl;
    }
};

Derived d;
Base& refBase = d;
refBase.print();  // Output: Derived

```

---
#### **Referências e STL** 

>[!quote] **Def**
>
>
A STL faz uso extensivo de referências para acessar elementos em contêineres como `std::vector`, `std::map`, etc.

```cpp

class Base {
public:
    virtual void print() {
        std::cout << "Base" << std::endl;
    }
};

class Derived : public Base {
public:
    void print() override {
        std::cout << "Derived" << std::endl;
    }
};

Derived d;
Base& refBase = d;
refBase.print();  // Output: Derived

```

---
