
---
#### **Herança Simples (Single Inheritance)**

>[!quote] **Def**
**Conceito:**
>
>- Na herança simples, uma classe derivada herda de **apenas uma classe base**. É o tipo mais comum e direto de herança.

![[Pasted image 20250310124636.png]]

>[!quote] **Def**
>**Melhor Caso de Uso:**
>
>**01**)
>- Quando você tem uma relação clara de "É um" (por exemplo, um `Dog` **é um** `Animal`).
>  
>**02**)  
>- Ideal para hierarquias simples e diretas, onde uma classe precisa estender o comportamento de uma única classe base.

```cpp
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating" << std::endl;
    }
};

class Dog : public Animal {
public:
    void bark() {
        std::cout << "Dog is barking" << std::endl;
    }
};

int main() {
    Dog dog;
    dog.eat();  // Método herdado da classe Animal
    dog.bark(); // Método da classe Dog
    return 0;
}
```

---
#### **Herança Multinível (Multilevel Inheritance)**

>[!quote] **Def**
**Conceito:**
>
>- Na herança multinível, uma classe derivada herda de outra classe derivada, criando uma **cadeia de herança**.

![[Pasted image 20250310130449.png]]

>[!quote] **Def**
>**Melhor Caso de Uso:**
>
>**01**)
>- Quando você precisa criar uma hierarquia de classes com níveis de especialização crescente.
>  
>**02**)  
>- Útil para modelar relações onde cada nível adiciona mais funcionalidades específicas (por exemplo, `Animal` → `Mammal` → `Dog`).

```cpp
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating" << std::endl;
    }
};

class Mammal : public Animal {
public:
    void breathe() {
        std::cout << "Mammal is breathing" << std::endl;
    }
};

class Dog : public Mammal {
public:
    void bark() {
        std::cout << "Dog is barking" << std::endl;
    }
};

int main() {
    Dog dog;
    dog.eat();     // Método da classe Animal
    dog.breathe(); // Método da classe Mammal
    dog.bark();    // Método da classe Dog
    return 0;
}
```

---
#### **Herança Hierárquica (Hierarchical Inheritance)**

>[!quote] **Def**
**Conceito:**
>
>- Na herança hierárquica, **várias classes derivadas herdam de uma única classe base**. Isso cria uma estrutura em forma de árvore.

![[Pasted image 20250310130143.png]]

>[!quote] **Def**
>**Melhor Caso de Uso:**
>
>**01**)
>- Quando você tem uma classe base comum e várias classes derivadas que compartilham características dessa base, mas têm comportamentos específicos.
>  
>**02**)  
>- Ideal para modelar categorias de objetos que compartilham funcionalidades comuns (por exemplo, `Car` e `Bike` são tipos de `Vehicle`).

```cpp
class Vehicle {
public:
    void start() {
        std::cout << "Vehicle started" << std::endl;
    }
};

class Car : public Vehicle {
public:
    void drive() {
        std::cout << "Car is driving" << std::endl;
    }
};

class Bike : public Vehicle {
public:
    void ride() {
        std::cout << "Bike is riding" << std::endl;
    }
};

int main() {
    Car car;
    Bike bike;
    car.start();  // Método da classe Vehicle
    car.drive();  // Método da classe Car
    bike.start(); // Método da classe Vehicle
    bike.ride(); // Método da classe Bike
    return 0;
}
```

---
#### **Herança Múltipla (Multiple Inheritance)**

>[!quote] **Def**
**Conceito:**
>
>- Na herança múltipla, uma classe derivada herda de **duas ou mais classes base**. Isso permite combinar características de várias classes em uma única classe derivada.

![[Pasted image 20250310125422.png]]

>[!quote] **Def**
>**Melhor Caso de Uso:**
>
>**01**)
> - Quando uma classe precisa combinar funcionalidades de múltiplas classes base.
>
>  
>**02**)  
>- Útil em cenários onde uma entidade possui características de diferentes categorias (por exemplo, um `Bat` é um mamífero que voa).

>[!quote] **Def**
>**Cuidado:**
>
>**01**)
> - Pode levar ao **problema do diamante** (diamond problem), onde a classe derivada herda múltiplas cópias de uma mesma classe base indiretamente. 
>   
>**02**)   
>- Isso pode ser resolvido com **herança virtual**.

```cpp
class Bird {
public:
    void fly() {
        std::cout << "Bird is flying" << std::endl;
    }
};

class Mammal {
public:
    void run() {
        std::cout << "Mammal is running" << std::endl;
    }
};

class Bat : public Bird, public Mammal {
public:
    void display() {
        std::cout << "Bat is a flying mammal" << std::endl;
    }
};

int main() {
    Bat bat;
    bat.fly();   // Método da classe Bird
    bat.run();   // Método da classe Mammal
    bat.display(); // Método da classe Bat
    return 0;
}
```

---
#### **Herança Híbrida (Hybrid Inheritance)**

>[!quote] **Def**
**Conceito:**
>
>- A herança híbrida é uma combinação de dois ou mais tipos de herança. Por exemplo, pode combinar herança múltipla e herança hierárquica.

![[Pasted image 20250310131016.png]]

>[!quote] **Def**
>**Melhor Caso de Uso:**
>
>**01**)
>- Quando você precisa combinar múltiplos tipos de herança para modelar relações complexas.
>  
>**02**)  
>- Útil em cenários onde uma classe precisa herdar características de várias hierarquias (por exemplo, um veículo anfíbio que é tanto um carro quanto um barco).

```cpp
class Vehicle {
public:
    void start() {
        std::cout << "Vehicle started" << std::endl;
    }
};

class Car : public Vehicle {
public:
    void drive() {
        std::cout << "Car is driving" << std::endl;
    }
};

class Boat : public Vehicle {
public:
    void sail() {
        std::cout << "Boat is sailing" << std::endl;
    }
};

class AmphibiousVehicle : public Car, public Boat {
public:
    void display() {
        std::cout << "AmphibiousVehicle can drive and sail" << std::endl;
    }
};

int main() {
    AmphibiousVehicle av;
    av.drive();   // Método da classe Car
    av.sail();   // Método da classe Boat
    av.display(); // Método da classe AmphibiousVehicle
    return 0;
}
```

---
#### **Herança Virtual (Virtual Inheritance)**

>[!quote] **Def**
**Conceito:**
>
>- A herança virtual é usada para resolver o **problema do diamante** (diamond problem) na herança múltipla. Ela garante que apenas uma instância da classe base seja compartilhada entre as classes derivadas.

![[Pasted image 20250310131556.png]]

>[!quote] **Def**
>**Melhor Caso de Uso:**
>
>**01**)
>- Quando você precisa evitar a duplicação de membros da classe base em cenários de herança múltipla.
>  
>**02**)  
>- Ideal para resolver o problema do diamante, onde uma classe derivada herda indiretamente de uma mesma classe base por múltiplos caminhos.

```cpp
class Animal {
public:
    void eat() {
        std::cout << "Animal is eating" << std::endl;
    }
};

class Mammal : virtual public Animal {
public:
    void breathe() {
        std::cout << "Mammal is breathing" << std::endl;
    }
};

class Bird : virtual public Animal {
public:
    void fly() {
        std::cout << "Bird is flying" << std::endl;
    }
};

class Bat : public Mammal, public Bird {
public:
    void display() {
        std::cout << "Bat is a flying mammal" << std::endl;
    }
};

int main() {
    Bat bat;
    bat.eat();   // Método da classe Animal (apenas uma instância)
    bat.breathe(); // Método da classe Mammal
    bat.fly();   // Método da classe Bird
    bat.display(); // Método da classe Bat
    return 0;
}
```

---
