
---

>[!tip] #### **HeapSort em C: Algoritmo de Ordenação por Heap**

---
#### 📌 **Introdução**

```ad-quote
title: **Def**

O HeapSort é um algoritmo de ordenação baseado em comparações que utiliza uma estrutura de dados chamada **heap** (binário) para organizar os elementos. É uma combinação eficiente dos princípios de Selection Sort e da estrutura Heap, oferecendo desempenho ótimo para ordenação in-place.
```

---
#### 🔧 **Implementação em C**

```c
#include <stdio.h>

// Função para transformar uma subárvore em heap
void heapify(int arr[], int n, int i) {  // (1)
    int largest = i;       // Inicializa o maior como raiz
    int left = 2 * i + 1;  // Filho esquerdo
    int right = 2 * i + 2; // Filho direito

    // Se o filho esquerdo é maior que a raiz
    if (left < n && arr[left] > arr[largest])  // (2)
        largest = left;

    // Se o filho direito é maior que o maior até agora
    if (right < n && arr[right] > arr[largest])  // (3)
        largest = right;

    // Se o maior não é a raiz
    if (largest != i) {  // (4)
        // Troca os elementos
        int temp = arr[i];
        arr[i] = arr[largest];
        arr[largest] = temp;

        // Heapify recursivamente a subárvore afetada
        heapify(arr, n, largest);  // (5)
    }
}

// Função principal do HeapSort
void heapSort(int arr[], int n) {  // (6)
    // Constrói o heap (reorganiza o array)
    for (int i = n / 2 - 1; i >= 0; i--)  // (7)
        heapify(arr, n, i);

    // Extrai elementos do heap um por um
    for (int i = n - 1; i > 0; i--) {  // (8)
        // Move a raiz atual para o final
        int temp = arr[0];
        arr[0] = arr[i];
        arr[i] = temp;

        // Chama heapify no heap reduzido
        heapify(arr, i, 0);  // (9)
    }
}

int main() {
    int arr[] = {5, 3, 8, 4, 2};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    printf("Array original: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    heapSort(arr, n);
    
    printf("\nArray ordenado: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    return 0;
}
```

---
#### 📝 **Explicação do Código**

```ad-quote
title: **Def**

**Função heapify**:
   - (1) - Transforma uma subárvore com raiz no índice `i` em um heap
   - (2) - Compara com o filho esquerdo
   - (3) - Compara com o filho direito
   - (4) - Se necessário, troca e continua o processo
   - (5) - Chamada recursiva para manter a propriedade de heap

**Função heapSort**:
   - (6) - Implementa o algoritmo completo
   - (7) - Constrói o heap máximo (para ordenação crescente)
   - (8) - Extrai os elementos do heap na ordem correta
   - (9) - Reconstroi o heap após cada extração

**Função main**:
   - Demonstração com array de exemplo
   - Chamada para heapSort e exibição dos resultados
```

---
#### 🌐 **Visualização do Processo**

```
Array original: [5, 3, 8, 4, 2]

1. Construção do Heap:
   Heap inicial: [5, 3, 8, 4, 2]
   Após heapify: [8, 4, 5, 3, 2]

2. Ordenação:
   Passo 1: Troca 8 e 2 → [2, 4, 5, 3, 8]
            Heapify → [5, 4, 2, 3, 8]
   Passo 2: Troca 5 e 3 → [3, 4, 2, 5, 8]
            Heapify → [4, 3, 2, 5, 8]
   Passo 3: Troca 4 e 2 → [2, 3, 4, 5, 8]
            Heapify → [3, 2, 4, 5, 8]
   Passo 4: Troca 3 e 2 → [2, 3, 4, 5, 8]
```

---
#### ⚙️ **Complexidade e Desempenho**

```ad-quote
title: **Def**

**Todos os casos**: 
- O(n log n) - tempo garantido em qualquer cenário

**Espaço auxiliar**: 
- O(1) - ordenação in-place (sem armazenamento adicional significativo)

**Estabilidade**: 
- Não estável - pode alterar ordem de elementos iguais
```

---
#### 🔍 **Características Principais**

```ad-quote
title: **Def**

**Eficiência garantida**: 
- Desempenho ótimo para ordenação baseada em comparações

**In-place**: 
- Não requer memória adicional significativa

**Não-adaptável**: 
- Tempo de execução não melhora com dados parcialmente ordenados

**Útil para prioridades**: 
- Estrutura heap permite eficiente extração do máximo/mínimo
```

---
#### 🚀 **Vantagens sobre Outros Algoritmos**

```ad-quote
title: **Def**

**Melhor que Merge Sort**: 
- Não requer espaço adicional O(n)

**Previsível que Quick Sort**: 
- Pior caso O(n log n) vs O(n²) do Quick Sort

**Eficiência prática**: 
- Excelente para sistemas em tempo real onde o pior caso importa
```

---
#### 💡 **Quando Utilizar**

```ad-quote
title: **Def**
**01)**
- Quando se necessita de ordenação in-place com complexidade O(n log n)

**02)**
- Em sistemas críticos onde o pior caso do Quick Sort é inaceitável

**03)**
- Para implementação de filas de prioridade eficientes

**04)**
- Em ambientes com restrição de memória
```

---
#### ❗ **Limitações**

```ad-quote
title: **Def**
**01)**
- Não estável (ordem relativa não é preservada)

**02)**
- Maior constante oculta que Quick Sort na prática

**03)**
- Acesso à memória menos cache-friendly que Merge Sort
```

---
#### 🛠️ **Otimizações Comuns**

```ad-quote
title: **Def**

**Heapify iterativo**:  
- Versão não-recursiva para evitar overflow de pilha  

**Build Heap otimizado**:  
- Construção do heap em tempo O(n)  

**Versão estável**:  
- Modificações para manter estabilidade (com trade-offs)  

**Heap binário vs d-ário**:  
- Experimentar com diferentes graus de heap para melhor cache locality
```

---

