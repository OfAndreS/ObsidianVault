
---

>[!tip] ### **Vector C++**

---

>[!quote] **Def**
>O `vector` é um container de sequência dinâmica que armazena elementos em um array redimensionável. Ele permite acesso aleatório aos elementos e é ideal para situações em que você precisa de um array que pode crescer ou diminuir em tempo de execução.
>
> **Principais características:**
>
>1 )
>- Armazena elementos em um array contíguo na memória.
>  
>---
>
>2 )
>- Permite acesso aleatório aos elementos em tempo constante (`O(1)`).
>
>---
>
>3 )
>- Inserções e remoções no final são eficientes (`O(1)`), mas no meio ou no início são mais lentas (`O(n)`).

---
#### **Declaração Padrão:**

```cpp
#include <vector>

int main() {
    // Declaração de um vetor de inteiros
    std::vector<int> vec;

    // Inicialização com valores
    std::vector<int> vecInicializado = {1, 2, 3, 4, 5};

    // Adicionando elementos
    vec.push_back(10);
    vec.push_back(20);

    // Acessando elementos
    int primeiroElemento = vec[0]; // Acesso sem verificação de limites
    int segundoElemento = vec.at(1); // Acesso com verificação de limites

    // Iterando sobre o vetor
    for (int i = 0; i < vec.size(); ++i) {
        std::cout << vec[i] << " ";
    }

    return 0;
}
```

---
#### **Principais funções:**

>[!quote] **`push_back(valor)`**: Adiciona um elemento ao final do vetor.

```
std::vector<int> vec;
vec.push_back(10); // Adiciona 10 ao final
```

---

>[!quote] **`pop_back()`**: Remove o último elemento do vetor.

```
vec.pop_back(); // Remove o último elemento

```

---

>[!quote] **`size()`**: Retorna o número de elementos no vetor.

```
std::cout << "Tamanho: " << vec.size() << std::endl;

```

---

>[!quote] **`at(index)`**: Acessa o elemento em uma posição específica com verificação de limites.

```
int elemento = vec.at(0); // Acessa o primeiro elemento

```

---

>[!quote] **`operator[]`**: Acessa o elemento em uma posição específica sem verificação de limites.

```
int elemento = vec[0]; // Acessa o primeiro elemento

```

---

>[!quote] **`begin()` e `end()`**: Retornam iteradores para o início e o fim do vetor.

```
for (auto it = vec.begin(); it != vec.end(); ++it) {
    std::cout << *it << " "; }
```

---

>[!quote] **`insert(posição, valor)`**: Insere um elemento em uma posição específica.

```
vec.insert(vec.begin() + 2, 42); // Insere 42 na posição 2

```

---

>[!quote] **`erase(posição)`**: Remove um elemento de uma posição específica.

```
vec.erase(vec.begin() + 1); // Remove o segundo elemento

```

---

>[!quote] **`clear()`**: Remove todos os elementos do vetor.

```
vec.clear();

```

---

>[!quote] **`find()`**: Remove todos os elementos do vetor.

```
vec.clear();

```
---

>[!tip] ### **List C++**

---

>[!quote] **Def**
>A `list` é uma lista duplamente encadeada que permite inserções e remoções eficientes em qualquer posição. Diferente do `vector`, ela não permite acesso aleatório, mas é mais eficiente para operações que envolvem inserções e remoções frequentes no meio da lista.
>
> **Principais características:**
>
>1 )
>- Armazena elementos em nós encadeados, onde cada nó contém um ponteiro para o próximo e o anterior.
>  
>---
>
>2 )
>- Inserções e remoções em qualquer posição são eficientes (`O(1)`).
>
>---
>
>3 )
>- Não permite acesso aleatório aos elementos (acesso é `O(n)`).

---
#### **Declaração Padrão:**

```cpp
#include <list>

int main() {
    // Declaração de uma lista de inteiros
    std::list<int> lista;

    // Inicialização com valores
    std::list<int> listaInicializada = {1, 2, 3, 4, 5};

    // Adicionando elementos
    lista.push_back(10); // Adiciona ao final
    lista.push_front(5); // Adiciona no início

    // Iterando sobre a lista
    for (auto it = lista.begin(); it != lista.end(); ++it) {
        std::cout << *it << " ";
    }

    // Removendo elementos
    lista.pop_back(); // Remove o último elemento
    lista.pop_front(); // Remove o primeiro elemento

    return 0;
}
```

---
#### **Principais funções:**

>[!quote] **`push_back(valor)`**: Adiciona um elemento ao final da lista.

```
std::list<int> lista;
lista.push_back(10); // Adiciona 10 ao final
```

---

>[!quote] **`push_front(valor)`**: Adiciona um elemento ao início da lista.

```
lista.push_front(5); // Adiciona 5 no início

```

---

>[!quote] **`pop_back()`**: Remove o último elemento da lista.

```
lista.pop_back(); // Remove o último elemento

```

---

>[!quote] **`pop_front()`**: Remove o primeiro elemento da lista.

```
lista.pop_front(); // Remove o primeiro elemento

```

---

>[!quote] **`size()`**: Retorna o número de elementos na lista.

```
std::cout << "Tamanho: " << lista.size() << std::endl;

```

---

>[!quote] **`insert(posição, valor)`**: Insere um elemento em uma posição específica.

```
auto it = lista.begin();
std::advance(it, 2); // Avança o iterador para a posição 2
lista.insert(it, 42); // Insere 42 na posição 2
```

---

>[!quote] **`erase(posição)`**: Remove um elemento de uma posição específica.

```
auto it = lista.begin();
std::advance(it, 1); // Avança o iterador para a posição 1
lista.erase(it); // Remove o segundo elemento
```

---

>[!quote] **`clear()`**: Remove todos os elementos da lista.

```
lista.clear();

```

---

>[!quote] **`sort()`**: Ordena os elementos da lista.

```
lista.sort(); // Ordena a lista em ordem crescente

```

---

>[!quote] **`unique()`**: Remove elementos duplicados consecutivos.

```
lista.unique(); // Remove duplicatas consecutivas

```

---

>[!tip] ### **Map C++**

---

>[!quote] **Def**
>O `map` é um container associativo que armazena pares de chave-valor, onde cada chave é única. Ele é implementado como uma árvore balanceada (geralmente uma árvore rubro-negra), o que garante que os elementos sejam sempre ordenados pelas chaves.
>
> **Principais características:**
>
>1 )
>- Armazena elementos em pares `chave-valor`.
>  
>---
>
>2 )
>- As chaves são únicas e ordenadas.
>
>---
>
>3 )
>- Inserções, remoções e buscas têm complexidade `O(log n)`.

---
#### **Declaração Padrão:**

```cpp
#include <map>
#include <string>

int main() {
    // Declaração de um mapa com chave do tipo string e valor do tipo int
    std::map<std::string, int> mapa;

    // Inicialização com valores
    std::map<std::string, int> mapaInicializado = {
        {"chave1", 10},
        {"chave2", 20},
        {"chave3", 30}
    };

    // Adicionando elementos
    mapa["chave4"] = 40; // Usando operator[]
    mapa.insert({"chave5", 50}); // Usando insert

    // Acessando elementos
    int valor = mapa["chave1"]; // Acessa o valor associado a "chave1"

    // Verificando se uma chave existe
    if (mapa.count("chave2")) {
        std::cout << "Chave encontrada!" << std::endl;
    }

    // Iterando sobre o mapa
    for (auto it = mapa.begin(); it != mapa.end(); ++it) {
        std::cout << it->first << ": " << it->second << std::endl;
    }

    // Removendo elementos
    mapa.erase("chave1"); // Remove o elemento com chave "chave1"

    return 0;
}
```

---
#### **Principais funções:**

>[!quote] **`insert({chave, valor})`**: Insere um par chave-valor no mapa.

```
std::map<std::string, int> mapa;
mapa.insert({"chave1", 10}); // Insere o par {"chave1", 10}
```

---

>[!quote] **`operator[]`**: Acessa ou insere um valor associado a uma chave.

```
mapa["chave2"] = 20; // Insere ou atualiza o valor associado a "chave2"
```

---

>[!quote] **`find(chave)`**: Retorna um iterador para o elemento com a chave especificada.

```
auto it = mapa.find("chave1");
if (it != mapa.end()) {
    std::cout << "Valor: " << it->second << std::endl;
}
```

---

>[!quote] **`erase(chave)`**: Remove o elemento com a chave especificada.

```
mapa.erase("chave1"); // Remove o elemento com chave "chave1"

```

---

>[!quote] **`size()`**: Retorna o número de elementos no mapa.

```
std::cout << "Tamanho: " << mapa.size() << std::endl;

```

---

>[!quote] **`clear()`**: Remove todos os elementos do mapa.

```
mapa.clear();

```

---

>[!quote] **`begin()` e `end()`**: Retornam iteradores para o início e o fim do mapa.

```
for (auto it = mapa.begin(); it != mapa.end(); ++it) {
    std::cout << it->first << ": " << it->second << std::endl;
}
```

---

>[!quote] **`count(chave)`**: Retorna 1 se a chave existir no mapa, caso contrário, retorna 0.

```
if (mapa.count("chave1")) {
    std::cout << "Chave encontrada!" << std::endl;
}
```

---

>[!quote] **`i.first`** e **`i.second`** Acessa o valor do Map dentro do forrange

```
map<string, int> number = {{"Chave 1", 10}, {"Chave 2", 20}, {"Chave 3", 30}};

for (auto i : number) {

cout << "| Key: " << i.first << " | Value: " << i.second << endl;    

}
```

---
