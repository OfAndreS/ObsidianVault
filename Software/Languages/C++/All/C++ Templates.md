
---
#### **Funções Templates**

>[!quote] **Def**  
Funções templates permitem criar funções genéricas que funcionam com qualquer tipo de dado, sem precisar reescrever o código para cada tipo. Elas são úteis para implementar operações que podem ser aplicadas a diferentes tipos, como operações matemáticas ou funções de utilidade.
>
>**Operações matemáticas genéricas:** 
>- Criar uma função que soma dois valores, independentemente de serem `int`, `double`, ou outros tipos numéricos.
>  
>---
>
>**Funções de utilidade:** 
>- Implementar funções como `swap`, `max`, ou `min` que funcionam com qualquer tipo de dado.  
###### ***Notação:***

> [!quote] **Def**  
> Funções templates permitem que você escreva uma única função que pode ser usada com diferentes tipos de dados. A sintaxe básica para definir uma função template é a seguinte:
>

> [!quote] `template <typename T>`: 
>  - Define um template com um parâmetro de tipo `T`. 
>    `T` é um placeholder para o tipo de dado que será especificado quando a função for chamada.

> [!quote] `T soma<int>(T a, T b)`: 
>  - A função `soma` agora pode ser usada com qualquer tipo `T` que suporte o operador `+`. 

```cpp
template <typename T>
T soma(T a, T b) {
    return a + b;
}
```
###### ***Exemplo:***

```cpp
int main() {
    int resultadoInt = soma<int>(3, 4);          // T é int
    double resultadoDouble = soma<int>(3.5, 4.2); // T é double
    return 0;
}
```

---
#### **Classes Templates**

>[!quote] **Def**  
Classes templates permitem criar classes genéricas que podem ser usadas com diferentes tipos de dados. Elas são amplamente utilizadas na STL para implementar contêineres como `std::vector`, `std::list`, e `std::map`.
>
>**Contêineres genéricos:**
>- Implementar estruturas de dados como `Array`, `List`, ou `Stack` que funcionam com qualquer tipo de dado.
>  
>---
>
>**Classes utilitárias:** 
>- Criar classes como `Caixa` ou `Par` que armazenam valores de tipos genéricos.
###### ***Notação:***

> [!quote] **Def**  
Classes templates permitem que você defina classes que podem operar com tipos de dados genéricos. A sintaxe é semelhante à das funções templates:

> [!quote] `template <typename T>`:
>  - Define um template de classe com um parâmetro de tipo `T`.

> [!quote] **`Caixa(T v)`**:
>  - O construtor da classe `Caixa` aceita um valor do tipo `T`.

> [!quote] **`T getValor() const`**:
>  - Retorna o valor armazenado na caixa.

```cpp
template <typename T>
class Caixa {
private:
    T valor;
public:
    Caixa(T v) : valor(v) {}
    T getValor() const { return valor; }
};
```
###### ***Exemplo:***

```cpp
int main() {
    Caixa<int> caixaInt(42);          // T é int
    Caixa<std::string> caixaStr("Hello"); // T é std::string

    std::cout << caixaInt.getValor() << std::endl;  // Saída: 42
    std::cout << caixaStr.getValor() << std::endl;  // Saída: Hello
    return 0;
}
```

---
#### **Parâmetros de Template Não-Tipo**

>[!quote] **Def**  
Templates podem aceitar parâmetros não-tipo, como valores constantes (inteiros, ponteiros, etc.), além de tipos. Isso é útil para criar classes ou funções que dependem de valores constantes.
>
>**Arrays de tamanho fixo:**
>- Criar uma classe `Array` com tamanho definido em tempo de compilação.
>  
>---
>
>**Matrizes ou grids:** 
>- Implementar estruturas de dados com dimensões fixas, como uma matriz 3x3.
###### ***Notação:***

> [!quote] **Def**  
Além de tipos, templates também podem aceitar parâmetros não-tipo, como valores inteiros, ponteiros, ou referências. Isso é útil para criar classes ou funções que dependem de valores constantes.

> [!quote] `template <typename T, int tamanho>`:
>  - Define um template com um tipo `T` e um valor inteiro `tamanho`.

> [!quote] `T elementos[tamanho];`:
>  - Um array de elementos do tipo `T` com tamanho fixo.

```cpp
template <typename T, int tamanho>
class Array {
private:
    T elementos[tamanho];
public:
    T& operator[](int index) {
        return elementos[index];
    }
};
```
###### ***Exemplo:***

```cpp
int main() {
    Array<int, 5> arr;
    arr[0] = 10;
    arr[1] = 20;
    std::cout << arr[0] << std::endl;  // Saída: 10
    return 0;
}
```

---
#### **Especialização de Templates**

>[!quote] **Def**  
Especialização permite fornecer uma implementação específica de um template para um tipo ou valor particular. Isso é útil para otimizar ou personalizar o comportamento de um template para tipos específicos.
>
>**Otimização para tipos específicos:**
>- Fornecer uma implementação mais eficiente para tipos como `char` ou `bool`.
>  
>---
>
>**Comportamento personalizado:**
>- Implementar lógica específica para tipos específicos, como strings ou ponteiros.
###### ***Notação:***

> [!quote] **Def**  
> Às vezes, você pode querer fornecer uma implementação específica de um template para um tipo particular. Isso é chamado de especialização de template.

> [!quote] **`template <>`**:
>  - Indica que esta é uma especialização do template `Caixa` para o tipo `char`.

> [!quote] **`Caixa<char>`**:
>  - A classe `Caixa` agora tem uma implementação específica para o tipo `char`.

```cpp
template <>
class Caixa<char> {
private:
    char valor;
public:
    Caixa(char v) : valor(v) {}
    char getValor() const { return valor; }
    void print() const {
        std::cout << "Valor especial: " << valor << std::endl;
    }
};
```
###### ***Exemplo:***

```cpp
int main() {
    Caixa<char> caixaChar('A');
    caixaChar.print();  // Saída: Valor especial: A
    return 0;
}
```

---
#### **Template de Múltiplos Parâmetros**

>[!quote] **Def**  
Templates podem ter vários parâmetros, permitindo maior flexibilidade na definição de funções ou classes. Isso é útil para criar estruturas que dependem de mais de um tipo ou valor.
>
>**Pares ou tuplas:**
>- Criar uma classe `Par` que armazena dois valores de tipos diferentes.
>  
>---
>
>**Funções com múltiplos tipos:**
>- Implementar funções que operam com dois ou mais tipos de dados.
###### ***Notação:***

> [!quote] **Def**  
> Templates podem ter múltiplos parâmetros, tanto de tipo quanto não-tipo.

> [!quote] **`template <typename T1, typename T2>`**:
>  - Define um template com dois parâmetros de tipo, `T1` e `T2`.

> [!quote] **`Par(T1 p, T2 s)`**:
>  - Construtor que aceita dois valores de tipos diferentes.

```cpp
template <typename T1, typename T2>
class Par {
private:
    T1 primeiro;
    T2 segundo;
public:
    Par(T1 p, T2 s) : primeiro(p), segundo(s) {}
    T1 getPrimeiro() const { return primeiro; }
    T2 getSegundo() const { return segundo; }
};
```
###### ***Exemplo:***

```cpp
int main() {
    Par<int, std::string> par(1, "Hello");
    std::cout << par.getPrimeiro() << ", " << par.getSegundo() << std::endl;  // Saída: 1, Hello
    return 0;
}
```

---
#### **Template de Métodos em Classes Não-Template**

>[!quote] **Def**  
Métodos templates permitem que métodos de uma classe não-template sejam genéricos. Isso é útil para adicionar funcionalidades genéricas a classes existentes.
>
>**Classes utilitárias:**
>- Adicionar métodos genéricos a classes existentes, como uma função `soma` em uma classe `Calculadora`.
>  
>---
>
>**Conversão de tipos:**
>- Implementar métodos que convertem ou manipulam dados de tipos variados.
###### ***Notação:***

> [!quote] **Def**  
> Você pode definir métodos templates dentro de classes que não são templates.

> [!quote] **`template <typename T>`**:
>  - Define um método template dentro de uma classe não-template.

> [!quote] **`T soma(T a, T b)`**:
>  - Método que pode ser usado com qualquer tipo `T`.

```cpp
class Calculadora {
public:
    template <typename T>
    T soma(T a, T b) {
        return a + b;
    }
};
```
###### ***Exemplo:***

```cpp
int main() {
    Calculadora calc;
    std::cout << calc.soma(3, 4) << std::endl;          // Saída: 7
    std::cout << calc.soma(3.5, 4.2) << std::endl;      // Saída: 7.7
    return 0;
}
```

---
#### **Template de Variadic (Variadic Templates)**

>[!quote] **Def**  
Templates variádicos permitem criar funções ou classes que aceitam um número variável de argumentos de tipos diferentes. Isso é útil para implementar funções ou estruturas que precisam ser flexíveis em relação ao número de argumentos.
>
>**Funções de log:**
>- Criar uma função `print` que aceita qualquer número de argumentos de tipos variados.
>  
>---
>
>**Tuplas genéricas:**
>- Implementar uma classe `Tupla` que armazena um número variável de elementos.

>[!quote] ***Link:*** [Template Others](https://www.udemy.com/course/complete-game-development-series-04-making-a-game-with-c/learn/lecture/40905874#content)
###### ***Notação:***

> [!quote] **Def**  
> Templates variádicos permitem criar funções ou classes que aceitam um número variável de argumentos de tipos diferentes.

> [!quote] **`template <typename... Args>`**:
>  - Defini um número desconhecido de Templates

> [!quote] **`void print(Args... args)`**:
>  - Recebe um número ainda desconhecido de argumentos definidos na chamada da função

```cpp
template <typename... Args>
void print(Args... args) {
    (std::cout << ... << args) << std::endl;
}
```
###### ***Exemplo:***

```cpp
//.hpp
template<typename ArgOne, typename... Others>
ArgOne infiniteSum(const ArgOne& argOne, const Others& ... others);

template<typename S>
S infiniteSum(S s);

//.inl
template<typename S>
S infiniteSum(S s)
{
	return s;
}

template<typename ArgOne, typename... Others>
ArgOne infiniteSum(const ArgOne& argOne, const Others& ... others)
{
	return argOne + infiniteSum(others...);
}

//main

std::cout << "| Sum: " << infiniteSum(5, 2, 5, 8, 9) << std::endl;
```

---
