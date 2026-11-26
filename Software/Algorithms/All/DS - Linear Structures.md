
---

>[!example] ### **Array**

---

```ad-quote
title: **Def**

Um **array**, também conhecido como: 
- vetor (em português) 
- lista 
  
Embora o termo "lista" possa ter outras conotações. 

É uma estrutura de dados fundamental na ciência da computação. Sua principal característica é armazenar uma coleção de: 

- **Elementos do mesmo tipo** de dados em **locais de memória contíguos**. 

Isso significa que os elementos são armazenados um após o outro, sem espaços vazios entre eles.
```
#### **Definição Completa:**

```ad-quote
title: **Def**

Um array pode ser definido como uma sequência finita e ordenada de elementos homogêneos (do mesmo tipo), armazenados em posições de memória adjacentes. Cada elemento no array é identificado por um índice (ou chave), que geralmente começa em 0 (zero) e vai até o tamanho do array menos 1.
```

---

>[!tip] **Características Principais:**

---
#### **Armazenamento Contíguo** 

```ad-quote
title: **Def**

Esta é a característica definidora de um array. Todos os elementos são alocados em blocos de memória que estão fisicamente próximos uns dos outros. Imagine uma fileira de caixas em um armazém, onde cada caixa contém um item do mesmo tipo.

**Benefício:** 

- Essa contiguidade permite um cálculo eficiente do endereço de memória de qualquer elemento. Sabendo o endereço do primeiro elemento (o endereço base) e o tamanho de cada elemento, o endereço de qualquer outro elemento pode ser calculado rapidamente usando o índice.
```

---
#### **Acesso em Tempo Constante O(1)**

```ad-quote
title: **Def**

Uma das maiores vantagens dos arrays é a capacidade de acessar qualquer elemento diretamente em tempo constante, denotado como O(1) na notação Big O. Isso significa que o tempo necessário para acessar um elemento específico não depende do tamanho do array.

**Como funciona:** 

- Para acessar um elemento em um índice específico, o computador realiza um simples cálculo de endereço: 
- `Endereço do elemento = Endereço base do array + (índice * tamanho do elemento)` 
  
Como essa operação envolve apenas uma multiplicação e uma adição, ela leva um tempo constante, independentemente do tamanho do array.
```

---
#### **Elementos Homogêneos**

```ad-quote
title: **Def**

Em muitos arrays (especialmente em linguagens de programação de mais baixo nível), todos os elementos precisam ser do mesmo tipo de dados (por exemplo, todos inteiros, todos caracteres, etc.). Isso simplifica o gerenciamento da memória e o cálculo dos endereços. Algumas linguagens de programação de mais alto nível (como Python) permitem arrays (listas) com elementos de tipos diferentes, mas internamente podem usar mecanismos diferentes ou impor certas restrições.
```

---
#### **Tamanho Fixo**

```ad-quote
title: **Def**

Em muitas linguagens, o tamanho de um array é definido quando ele é criado e não pode ser facilmente alterado durante a execução do programa. Se você precisar armazenar mais elementos do que o tamanho inicial, geralmente é necessário criar um novo array maior e copiar os elementos do array antigo para o novo. Algumas linguagens oferecem estruturas de dados dinâmicas (como listas dinâmicas ou vetores redimensionáveis) que internamente podem usar arrays, mas lidam com o redimensionamento automaticamente.
```

---

>[!danger] **Exemplo**

---
#### **Matrizes em Álgebra Linear**

```ad-quote
title: **Def**

Um exemplo clássico de como arrays são usados é na representação de **matrizes** em álgebra linear. Uma matriz é uma tabela retangular de números, dispostos em linhas e colunas.

- **Representação com Arrays:** Uma matriz pode ser representada usando um array bidimensional (um array de arrays). Cada elemento do array principal representa uma linha da matriz, e cada elemento dentro desses arrays representa uma coluna.
```
###### **Exemplo em Notação Matemática:**

```cpp
A = [ a₁₁ a₁₂ a₁₃ ] 
	[ a₂₁ a₂₂ a₂₃ ] 
	[ a₃₁ a₃₂ a₃₃ ]
```
###### **Representação em um Array Bidimensional (conceitual):**

```cpp
matriz_A = [ [a₁₁, a₁₂, a₁₃], 
			 [a₂₁, a₂₂, a₂₃], 
			 [a₃₁, a₃₂, a₃₃] ]
```
###### **Acesso aos Elementos:**

```ad-quote
title: **Def**

Para acessar um elemento específico na matriz, como o elemento na segunda linha e terceira coluna (a₂₃), usamos dois índices: um para a linha e outro para a coluna. No exemplo acima, isso seria `matriz_A[1][2]` (lembrando que a indexação geralmente começa em 0).
```

---

>[!example] ### **Lista Ligada**

---

```ad-quote
title: **Def**

Uma **lista ligada** (em inglês: _linked list_):

É uma estrutura de dados linear, semelhante a um array, mas com uma organização fundamentalmente diferente. 
- Ao contrário dos arrays, onde os elementos são armazenados em locais de memória contíguos, 
  
Em uma lista ligada, os elementos são armazenados em **nós** separados, que estão **ligados uns aos outros através de ponteiros (ou referências)**.
```
#### **Definição Completa:**

```ad-quote
title: **Def**

Uma lista ligada é uma sequência de elementos, chamados **nós**, onde cada nó contém duas partes principais:

1. **Dados:** A informação que o nó armazena. Pode ser de qualquer tipo de dado (inteiro, caractere, objeto, etc.).
2. **Ponteiro (ou Referência):** Um endereço de memória que aponta para o próximo nó na sequência.

O primeiro nó da lista é chamado de **cabeça (head)**, e o último nó geralmente tem seu ponteiro apontando para `null` (ou `None`), indicando o fim da lista.
```

---

>[!tip] **Estrutura de um Nó**

---
#### **Estrutura de um Nó:**

```ad-quote
title: **Def**

Imagine cada nó como uma pequena caixa com dois compartimentos: um para guardar a informação e outro para guardar um "endereço" que te diz onde encontrar a próxima caixa.
```

```cpp
struct ListNode {

     int val;

     ListNode *next;

     ListNode() : val(0), next(nullptr) {}

     ListNode(int x) : val(x), next(nullptr) {}

     ListNode(int x, ListNode *next) : val(x), next(next) {}

 };
```

---
#### **Lista Ligada Simples / Singly Linked List**

```ad-quote
title: **Def**
**01 )**
- Cada nó contém um ponteiro que aponta para o próximo nó na sequência.

**02 )**
- A travessia da lista só pode ser feita em uma direção: do primeiro nó para o último.
```

![[Pasted image 20250330212025.png]] 
###### ***Exemplo:*** 

```ad-quote
title: **Def**

**Histórico de um navegador web (simplificado):** 
Imagine que você está navegando na internet e visita algumas páginas. 
- Podemos representar esse histórico usando uma lista ligada simples. 
- Cada página visitada seria um nó, contendo a URL da página e um ponteiro para a próxima página que você visitou. 
  
Você só pode voltar para a página anterior clicando no botão "Voltar", que essencialmente te move para o nó anterior na sequência.
```

```
[Página Inicial] -> [Página A] -> [Página B] -> [Página C] -> null
```

```ad-quote
title: **Def**


Neste exemplo, a "Página Inicial" seria a cabeça da lista, e a "Página C" seria o último nó, com seu ponteiro apontando para `null`. Para acessar a "Página B", você teria que começar da "Página Inicial" e seguir os ponteiros até chegar lá.
```

---
#### **Lista Ligada Duplamente / Doubly Linked List**

```ad-quote
title: **Def**
**01 )**
- Cada nó contém dois ponteiros: um que aponta para o próximo nó e outro que aponta para o nó anterior.

**02 )**
- Permite a travessia da lista em ambas as direções (para frente e para trás).

**03 )**
- Facilita operações como inserção e remoção em certas situações.
```

![[Pasted image 20250330212937.png]]
###### ***Exemplo:*** 

```ad-quote
title: **Def**

**Funcionalidade "Avançar" e "Voltar" em um navegador web:** 

Expandindo o exemplo anterior, um navegador web real usa uma estrutura mais parecida com uma lista ligada duplamente para o histórico. 
- Isso permite que você não apenas volte para a página anterior, mas também avance para a próxima página no seu histórico (se você voltou). 
  
Cada nó (página visitada) teria um ponteiro para a próxima página e um ponteiro para a página anterior.
```

```
null <-- [Página Inicial] <--> [Página A] <--> [Página B] <--> [Página C] --> null
```

```ad-quote
title: **Def**

Agora, a partir da "Página B", você pode facilmente ir para "Página A" (voltando) ou para "Página C" (avançando).
```

---
#### **Lista Ligada Circular / Circular Linked List**

```ad-quote
title: **Def**
**01 )**
- O ponteiro do último nó aponta de volta para o primeiro nó (a cabeça), formando um ciclo.

**02 )**
- Pode ser simplesmente ou duplamente ligada.

**03 )**
- Útil para representar estruturas onde um ciclo é natural, como uma fila de tarefas que se repetem.
```

![[Pasted image 20250330213312.png]]
###### ***Exemplo:*** 

```ad-quote
title: **Def**

Uma fila de reprodução de música em loop:** Imagine um aplicativo de música onde você tem uma playlist configurada para repetir. Quando a última música termina, ela volta para a primeira música da lista. Isso pode ser implementado usando uma lista ligada circular, onde o ponteiro do último nó (a última música) aponta de volta para o primeiro nó (a primeira música).
```

```
[Música 1] --> [Música 2] --> [Música 3]
^                                |
|________________________________|
```

---

>[!tip] **Operações Comuns em Listas Ligadas**

---
#### **Inserção:** 

```ad-quote
title: **Def**

Adicionar um novo nó à lista. Isso pode ser feito:
    
**No início:** 
- O novo nó se torna a nova cabeça.

**No final:** 
- O ponteiro do último nó é atualizado para apontar para o novo nó.

**No meio:** 
- O novo nó é inserido entre dois nós existentes, ajustando os ponteiros adequadamente.
```

---
#### **Remoção:** 

```ad-quote
title: **Def**

Remover um nó existente da lista. Isso pode ser feito:

**No início:** 
- A cabeça é movida para o próximo nó.

**No final:** 
- O ponteiro do penúltimo nó é atualizado para `null`.

**No meio:** 
- Os ponteiros dos nós adjacentes ao nó a ser removido são ajustados para "pular" o nó removido.

**Travessia:** 
- Visitar cada nó da lista em sequência, geralmente começando pela cabeça e seguindo os ponteiros até o final.
```

---
#### **Busca:** 

```ad-quote
title: **Def**


Encontrar um nó específico na lista que contenha um determinado valor. Isso geralmente envolve percorrer a lista sequencialmente e comparar os dados de cada nó com o valor procurado.
```

---

>[!tip] **Especificações**

---
#### **Vantagens das Listas Ligadas:**

```ad-quote
title: **Def**

**Tamanho Dinâmico:** 
- As listas ligadas podem crescer ou diminuir dinamicamente em tempo de execução, pois a memória é alocada para cada nó individualmente conforme necessário. Isso é diferente dos arrays, que geralmente têm um tamanho fixo.

**Inserção e Remoção Eficientes:** 
- Inserir ou remover nós no meio de uma lista ligada é geralmente mais eficiente do que em um array. Em um array, inserir ou remover um elemento no meio requer o deslocamento de todos os elementos subsequentes. Em uma lista ligada, basta ajustar os ponteiros dos nós vizinhos.
```

---
#### **Desvantagens das Listas Ligadas:**

```ad-quote
title: **Def**

**Acesso Sequencial:** 
- Para acessar um elemento específico em uma lista ligada, é necessário começar pela cabeça e percorrer a lista sequencialmente até encontrar o nó desejado. Isso significa que o tempo de acesso a um elemento em uma posição arbitrária é O(n), onde n é o número de elementos na lista (ao contrário do acesso O(1) dos arrays).

**Sobrecarga de Memória:** 
- Cada nó em uma lista ligada requer memória extra para armazenar o ponteiro (ou ponteiros), além dos dados em si. Isso pode resultar em um uso de memória ligeiramente maior em comparação com arrays para a mesma quantidade de dados.

**Implementação Mais Complexa:** 
- A implementação de operações em listas ligadas pode ser um pouco mais complexa do que em arrays, devido à necessidade de manipular os ponteiros corretamente.
```

---

>[!error] **Ex )** *Exemplo Completo* 

---
#### **Algoritmo para Lista Ligada em C++**

```ad-quote
title: **Def**

Aqui está uma implementação básica de uma lista ligada (lista encadeada) em C++ com as operações principais:
```

```cpp
#include <iostream>

/*
 * Estrutura do nó da lista ligada
 * Cada nó contém:
 * - data: valor armazenado no nó
 * - next: ponteiro para o próximo nó na lista
 */
struct Node {
    int data;       // Dado armazenado no nó
    Node* next;     // Ponteiro para o próximo nó
    
    // Construtor do nó
    Node(int val) : data(val), next(nullptr) {}
};

/*
 * Classe que representa a lista ligada
 * Contém operações básicas para manipulação da lista
 */
class LinkedList {
private:
    Node* head;     // Ponteiro para o primeiro nó da lista
    
public:
    // Construtor: inicializa a lista vazia
    LinkedList() : head(nullptr) {}
    
    /*
     * Insere um novo nó no início da lista
     * Parâmetro: val - valor a ser inserido
     */
    void insertAtBeginning(int val) {
        // 1. Cria um novo nó
        Node* newNode = new Node(val);
        
        // 2. Faz o novo nó apontar para o atual primeiro elemento
        newNode->next = head;
        
        // 3. Atualiza o head para apontar para o novo nó
        head = newNode;
    }
    
    /*
     * Insere um novo nó no final da lista
     * Parâmetro: val - valor a ser inserido
     */
    void insertAtEnd(int val) {
        // 1. Cria um novo nó
        Node* newNode = new Node(val);
        
        // 2. Caso especial: lista vazia
        if (head == nullptr) {
            head = newNode;
            return;
        }
        
        // 3. Percorre a lista até o último nó
        Node* current = head;
        while (current->next != nullptr) {
            current = current->next;
        }
        
        // 4. Insere o novo nó no final
        current->next = newNode;
    }
    
    /*
     * Remove o nó contendo o valor especificado
     * Parâmetro: val - valor a ser removido
     * Retorno: true se encontrou e removeu, false caso contrário
     */
    bool remove(int val) {
        // Caso especial: lista vazia
        if (head == nullptr) return false;
        
        // Caso especial: remoção do primeiro nó
        if (head->data == val) {
            Node* temp = head;      // Guarda referência ao nó a ser removido
            head = head->next;      // Atualiza o head
            delete temp;           // Libera a memória
            return true;
        }
        
        // Procura o nó anterior ao que contém o valor
        Node* current = head;
        while (current->next != nullptr && current->next->data != val) {
            current = current->next;
        }
        
        // Se não encontrou o valor
        if (current->next == nullptr) return false;
        
        // Remove o nó encontrado
        Node* temp = current->next;         // Guarda referência ao nó a ser removido
        current->next = current->next->next; // Ponteiro "pula" o nó a ser removido
        delete temp;                       // Libera a memória
        return true;
    }
    
    /*
     * Busca um valor na lista
     * Parâmetro: val - valor a ser buscado
     * Retorno: true se encontrou, false caso contrário
     */
    bool search(int val) {
        Node* current = head;
        
        // Percorre a lista até encontrar o valor ou chegar ao final
        while (current != nullptr) {
            if (current->data == val) {
                return true;
            }
            current = current->next;
        }
        return false;
    }
    
    /*
     * Imprime todos os elementos da lista
     * Formato: valor1 -> valor2 -> ... -> nullptr
     */
    void print() {
        Node* current = head;
        while (current != nullptr) {
            std::cout << current->data << " -> ";
            current = current->next;
        }
        std::cout << "nullptr" << std::endl;
    }
    
    /*
     * Destrutor: libera toda a memória alocada para os nós
     * Garante que não haja vazamento de memória quando a lista é destruída
     */
    ~LinkedList() {
        Node* current = head;
        while (current != nullptr) {
            Node* next = current->next; // Guarda referência ao próximo nó
            delete current;            // Libera o nó atual
            current = next;           // Avança para o próximo nó
        }
    }
};

/*
 * Função principal - demonstração do uso da lista ligada
 */
int main() {
    // Cria uma lista vazia
    LinkedList list;
    
    // Insere alguns valores
    list.insertAtEnd(10);     // Lista: 10 -> nullptr
    list.insertAtEnd(20);     // Lista: 10 -> 20 -> nullptr
    list.insertAtBeginning(5); // Lista: 5 -> 10 -> 20 -> nullptr
    list.insertAtEnd(30);     // Lista: 5 -> 10 -> 20 -> 30 -> nullptr
    
    // Imprime a lista
    std::cout << "Lista: ";
    list.print();
    
    // Remove um elemento
    list.remove(20);         // Lista: 5 -> 10 -> 30 -> nullptr
    std::cout << "Após remover 20: ";
    list.print();
    
    // Testa a busca
    std::cout << "Buscar 10: " << (list.search(10) ? "Encontrado" : "Não encontrado") << std::endl;
    std::cout << "Buscar 20: " << (list.search(20) ? "Encontrado" : "Não encontrado") << std::endl;
    
    return 0;
}
```

## Principais Operações Implementadas:

1. **Inserção**:
   - `insertAtBeginning()` - Insere no início da lista
   - `insertAtEnd()` - Insere no final da lista

2. **Remoção**:
   - `remove()` - Remove um nó com valor específico

3. **Busca**:
   - `search()` - Verifica se um valor existe na lista

4. **Exibição**:
   - `print()` - Mostra todos os elementos da lista

5. **Gerenciamento de Memória**:
   - Destrutor para liberar toda a memória alocada

Esta implementação pode ser estendida com outras funcionalidades como:
- Inserção em posição específica
- Inversão da lista
- Ordenação
- Contagem de elementos
- Entre outras operações comuns em listas ligadas