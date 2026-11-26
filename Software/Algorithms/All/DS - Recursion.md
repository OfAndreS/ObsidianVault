
---

```ad-quote
title: **Def**

Recursão é uma técnica em programação onde **uma função chama a si mesma** para resolver um problema dividindo-o em subproblemas menores. Ela é amplamente usada em algoritmos, estruturas de dados e matemática computacional.
```

---

>[!example] #### **Conceitos Fundamentais**

---
### **1 )** *Componentes da Recursão*


```ad-quote
title: **Def**

Toda função recursiva deve ter:
1. **Caso Base** → Condição de parada para evitar chamadas infinitas.
2. **Passo Recursivo** → Chamada da função com um subproblema menor.
```

### **2 )** *Recursão vs. Iteração*


```ad-quote
title: **Def**

**Recursão**
- Usa chamadas de função repetidas.
- Pode ser mais intuitiva para certos problemas.
- Pode causar *stack overflow* se mal implementada.

**Iteração**
- Usa loops (`for`, `while`).
- Geralmente mais eficiente em memória.
- Não usa pilha de chamadas.
```


---

>[!example]  #### **Exemplos Clássicos

---
### **1 )** *Fatorial*

```cpp
#include <iostream>
using namespace std;

int fatorial(int n) {
    if (n == 0 || n == 1) // Caso base
        return 1;
    else
        return n * fatorial(n - 1); // Passo recursivo
}

int main() {
    cout << "Fatorial de 5: " << fatorial(5) << endl; // 120
    return 0;
}
```
##### *Representação Gráfica:*

```
fatorial(5)
│
└─ 5 * fatorial(4)
      │
      └─ 4 * fatorial(3)
            │
            └─ 3 * fatorial(2)
                  │
                  └─ 2 * fatorial(1)
                        │
                        └─ 1 (caso base)
```
##### *Chamada:* `fatorial(5)`

```ad-quote
title: **Def**

**Passo a Passo:**

**fatorial(5)**  
   → `5 * fatorial(4)`  
   (Empilha `fatorial(5)` e chama `fatorial(4)`)

---

**fatorial(4)**  
   → `4 * fatorial(3)`  
   (Empilha `fatorial(4)` e chama `fatorial(3)`)

---

**fatorial(3)**  
   → `3 * fatorial(2)`  
   (Empilha `fatorial(3)` e chama `fatorial(2)`)

---

**fatorial(2)**  
   → `2 * fatorial(1)`  
   (Empilha `fatorial(2)` e chama `fatorial(1)`)

---

**fatorial(1)**  
   → Retorna `1` (caso base)  
   (Desempilha e resolve as chamadas pendentes)

---

**Resolução:**

fatorial(1)` retorna `1` → `2 * 1 = 2`  
- `fatorial(2)` retorna `2` → `3 * 2 = 6`  
- `fatorial(3)` retorna `6` → `4 * 6 = 24`  
- `fatorial(4)` retorna `24` → `5 * 24 = 120`  
- **Resultado final:** `120`.
```

---
### **2 )** *Fibonacci*

```cpp
#include <iostream>
using namespace std;

int fibonacci(int n) {
    if (n <= 1) // Caso base
        return n;
    else
        return fibonacci(n - 1) + fibonacci(n - 2); // Passo recursivo
}

int main() {
    cout << "Fibonacci(6): " << fibonacci(6) << endl; // 8
    return 0;
}
```
##### *Representação Gráfica (Árvore de Chamadas):*

```
fibonacci(4)
│
├─ fibonacci(3)
│   │
│   ├─ fibonacci(2) → 1 (1 + 0)
│   │   │
│   │   ├─ fibonacci(1) → 1
│   │   └─ fibonacci(0) → 0
│   │
│   └─ fibonacci(1) → 1
│
└─ fibonacci(2) → 1 (1 + 0)
    │
    ├─ fibonacci(1) → 1
    └─ fibonacci(0) → 0
```
##### *Chamada:* `fibonacci(4)`

```ad-quote
title: **Def**

**Passo a Passo:**

**fibonacci(4)**  
   → `fibonacci(3) + fibonacci(2)`  
   (Divide em duas chamadas recursivas)

---

**fibonacci(3)**  
   → `fibonacci(2) + fibonacci(1)`  

---

**fibonacci(2)**  
   → `fibonacci(1) + fibonacci(0)`  

---

**fibonacci(1)** e **fibonacci(0)**  
   → Retornam `1` e `0` (casos base)  

---

**Resolução parcial:**  
   - `fibonacci(2)` = `1 + 0 = 1`  
   - `fibonacci(3)` = `1 + 1 = 2`  

---

**fibonacci(2)** (segunda chamada, do passo 1)  
   → `fibonacci(1) + fibonacci(0)` = `1 + 0 = 1`  

---

**Resultado final:**  
   `fibonacci(4)` = `2 + 1 = 3`.
```
##### *Observações:*

```ad-quote
title: **Def**

- Cada chamada gera **duas novas chamadas** (exceto nos casos base).
- Ineficiente para `n` grande (complexidade exponencial: `O(2^n)`).
```

---
### **3 )** *Soma de Números*

```cpp
#include <iostream>
using namespace std;

int soma(int n) {
    if (n == 0) // Caso base
        return 0;
    else
        return n + soma(n - 1); // Passo recursivo
}

int main() {
    cout << "Soma de 1 a 5: " << soma(5) << endl; // 15
    return 0;
}
```
##### *Representação Gráfica:*

```
soma(3)
│
└─ 3 + soma(2)
      │
      └─ 2 + soma(1)
            │
            └─ 1 + soma(0)
                  │
                  └─ 0 (caso base)
```
##### *Chamada:* `soma(3)`

```ad-quote
title: **Def**

**Passo a Passo:**

**soma(3)**  
   → `3 + soma(2)`  

---

**soma(2)**  
   → `2 + soma(1)`  

---

**soma(1)**  
   → `1 + soma(0)`  

---

**soma(0)**  
   → Retorna `0` (caso base)  

---

**Resolução:**  
   - `soma(1)` = `1 + 0 = 1`  
   - `soma(2)` = `2 + 1 = 3`  
   - `soma(3)` = `3 + 3 = 6`  
```

---

>[!example] #### **Recursão em Estruturas de Dados**

---
### **1 )** *Busca em Árvore Binária*

```cpp
struct Node {
    int data;
    Node* left;
    Node* right;
};

bool busca(Node* root, int valor) {
    if (root == nullptr) // Caso base: não encontrado
        return false;
    if (root->data == valor) // Caso base: encontrado
        return true;
    if (valor < root->data)
        return busca(root->left, valor); // Busca na subárvore esquerda
    else
        return busca(root->right, valor); // Busca na subárvore direita
}
```

---
### **2 )** *Travessia em Ordem (In-Order Traversal)*

```cpp
void inOrder(Node* root) {
    if (root == nullptr) // Caso base
        return;
    inOrder(root->left);  // Visita subárvore esquerda
    cout << root->data << " "; // Visita nó atual
    inOrder(root->right); // Visita subárvore direita
}
```

---

>[!example] #### **Tipos de Recursão**

---
### **1 )** *Recursão Direta*

>[!quote] A função chama a si mesma diretamente.

```cpp
void funcao(int n) {
    if (n == 0) return;
    funcao(n - 1); // Chamada direta
}
```

---
### **2 )** *Recursão Indireta*

>[!quote] A função `A` chama a função `B`, que chama `A` novamente.

```cpp
void funcaoB(int n);

void funcaoA(int n) {
    if (n == 0) return;
    funcaoB(n - 1); // Chamada indireta
}

void funcaoB(int n) {
    funcaoA(n); // Volta para A
}
```

---
### **3 )** *Recursão de Cauda (Tail Recursion)*

>[!quote] A chamada recursiva é a última operação da função.

```cpp
int fatorialTail(int n, int acumulador = 1) {
    if (n == 0) return acumulador;
    return fatorialTail(n - 1, n * acumulador); // Chamada na cauda
}

//(Compiladores podem converter isso em um loop, evitando *stack overflow*.)

```

---

>[!example] #### **Especificações**

---
#### **Vantagens e Desvantagens**

```ad-quote
title: **Def**

**✔️ Vantagens**
- Código mais limpo e legível para certos problemas (ex.: árvores, backtracking).
- Natural para problemas com **subestrutura ótima** (ex.: divisão e conquista).

**❌ Desvantagens**
- Pode consumir muita memória devido à **pilha de chamadas** (*stack overflow*).
- Pode ser menos eficiente que iteração (ex.: Fibonacci recursivo vs. iterativo).
```

---
#### **Quando Usar Recursão?**

```ad-quote
title: **Def**

- Problemas com **natureza recursiva** (ex.: árvores, grafos, backtracking).
- Quando a **legibilidade** é mais importante que a eficiência.
- Em linguagens funcionais (Haskell, Lisp), onde recursão é incentivada.
```

---
#### **Melhores Práticas**

```ad-quote
title: **Def**

**Sempre definir um caso base**: 
- para evitar loops infinitos.
  
**Evitar recursão desnecessária**: 
- em problemas simples (prefira iteração).
  
**Usar memoização**: 
- para evitar recálculos (ex.: Fibonacci com cache).
  
**Considerar recursão de cauda**: 
- quando possível para otimização.
```

---
#### **Exemplo com Memoização (Fibonacci Eficiente)**

```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

unordered_map<int, int> cache;

int fibMemo(int n) {
    if (n <= 1) return n;
    if (cache.find(n) != cache.end())
        return cache[n];
    cache[n] = fibMemo(n - 1) + fibMemo(n - 2);
    return cache[n];
}

int main() {
    cout << "Fib(50): " << fibMemo(50) << endl; // Rápido devido à memoização
    return 0;
}
```

---
