
---

```ad-quote
title: **Def**

O Quick Sort é um algoritmo de ordenação eficiente que utiliza a estratégia "dividir para conquistar" com seleção de um pivô. Ele particiona recursivamente a lista em torno de um elemento pivô, colocando elementos menores antes e maiores depois do pivô, garantindo ordenação local.
```

---

>[!example] #### **Quick Sort em C / Algoritmo de Ordenação por Partição**

---
##### *Estrutura Quick Sort*

```ad-quote
title: **Def**
**01 )**
- Separar

**02 )**
- Ordenar (Primeira Parte)

**03 )**
- Ordenar (Segunda Parte)

**04 )**
- Juncao
```

---
#### 🔧 **Implementação em C**

```c
#include <stdio.h>

// Função para trocar dois elementos
void swap(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

// Função de partição modificada para usar o primeiro elemento como pivô
int partition(int arr[], int low, int high) {
    int pivot = arr[low];  // Pivô é agora o primeiro elemento
    int i = low;           // Índice começa no low
    
    for (int j = low + 1; j <= high; j++) {
        if (arr[j] < pivot) {
            i++;
            swap(&arr[i], &arr[j]);
        }
    }
    // Coloca o pivô na posição correta
    swap(&arr[i], &arr[low]);
    return i;  // Retorna a posição do pivô
}

// Função principal do Quick Sort (inalterada)
void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        
        quickSort(arr, low, pi - 1);   // Ordena elementos antes do pivô
        quickSort(arr, pi + 1, high);  // Ordena elementos após o pivô
    }
}

int main() {
    int arr[] = {3, 2, 4, 5, 8, 0, 1, 9, 7};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    printf("Array original: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    quickSort(arr, 0, n - 1);
    
    printf("\nArray ordenado: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    return 0;
}
```
##### **VP )** *Visualizacao da Recursão*

```cpp
Nível 0: quickSort([3,2,4,5,8,0,1,9,7], 0, 8)
           pivô=3 (índice 0), partição → [2,0,1,3,8,4,5,9,7], pi=3
           ├─ Nível 1: quickSort([2,0,1], 0, 2)   // Lado esquerdo do pivô 3
           │    pivô=2 (índice 0), partição → [0,1,2], pi=2
           │    ├─ Nível 2: quickSort([0,1], 0, 1)   // Lado esquerdo do pivô 2
           │    │    pivô=0 (índice 0), partição → [0,1], pi=0
           │    │    ├─ Nível 3: quickSort([], 0, -1) → caso base
           │    │    └─ Nível 3: quickSort([1], 1, 1) → caso base
           │    │
           │    └─ Nível 2: quickSort([], 3, 2) → caso base   // Lado direito do pivô 2
           │
           └─ Nível 1: quickSort([8,4,5,9,7], 4, 8)   // Lado direito do pivô 3
                pivô=8 (índice 4), partição → [4,5,7,8,9], pi=7
                ├─ Nível 2: quickSort([4,5,7], 4, 6)   // Lado esquerdo do pivô 8
                │    pivô=4 (índice 4), partição → [4,5,7], pi=4
                │    ├─ Nível 3: quickSort([], 4, 3) → caso base
                │    └─ Nível 3: quickSort([5,7], 5, 6)
                │         pivô=5 (índice 5), partição → [5,7], pi=5
                │         ├─ Nível 4: quickSort([], 5, 4) → caso base
                │         └─ Nível 4: quickSort([7], 6, 6) → caso base
                │
                └─ Nível 2: quickSort([9], 8, 8) → caso base   // Lado direito do pivô 8
```

---
#### 🌐 **Visualização do Processo**

```ad-quote
title: 🔄 Quick Sort - Visualização Detalhada (10 números)
**Array Original:** [7, 2, 9, 4, 6, 1, 3, 8, 5, 10]
```

```
=== "Passo 1: Partição Inicial (pivô=3)"
    
    [3, 2, 4, 5, 8, 0, 1, 9, 7]
    Partição:
    2, 0, 1 → menores que 3
    4, 5, 8, 9, 7 → maiores que 3
    Troca final: [2, 0, 1, 3, 4, 5, 8, 9, 7] → pi=3
    Subarrays: [2,0,1] e [4,5,8,9,7]

=== "Passo 2: Subarray [2,0,1] (pivô=2)"
    
    [2, 0, 1]
    Partição:
    0, 1 → menores que 2
    [] → maiores que 2
    Troca final: [0, 1, 2] → pi=2
    Subarrays: [0,1] e []

=== "Passo 3: Subarray [0,1] (pivô=0)"
    
    [0, 1]
    Partição:
    [] → menores que 0
    1 → maior que 0
    Troca final: [0, 1] → pi=0
    Subarrays: [] e [1]

=== "Passo 4: Subarray [4,5,8,9,7] (pivô=4)"
    
    [4, 5, 8, 9, 7]
    Partição:
    [] → menores que 4
    5,8,9,7 → maiores que 4
    Troca final: [4,5,8,9,7] → pi=0
    Subarrays: [] e [5,8,9,7]

=== "Passo 5: Subarray [5,8,9,7] (pivô=5)"
    
    [5, 8, 9, 7]
    Partição:
    [] → menores que 5
    8,9,7 → maiores que 5
    Troca final: [5,8,9,7] → pi=0
    Subarrays: [] e [8,9,7]

=== "Passo 6: Subarray [8,9,7] (pivô=8)"
    
    [8, 9, 7]
    Partição:
    7 → menor que 8
    9 → maior que 8
    Troca final: [7, 8, 9] → pi=1
    Subarrays: [7] e [9]

=== "Passo 7: Subarray [9] (caso base)"
    
    [9] → tamanho 1, já ordenado

=== "Passo 8: Subarray [7] (caso base)"
    
    [7] → tamanho 1, já ordenado

=== "Passo 9: Subarray [1] (caso base)"
    
    [1] → tamanho 1, já ordenado

Resultado Final: [0, 1, 2, 3, 4, 5, 7, 8, 9]
```

![[Pasted image 20250521211038.png]]

---
#### 🔍 **Características Principais**

```ad-quote
title: **Def**

**Eficiência prática**: 
- Geralmente mais rápido que Merge/Heap Sort devido a constantes menores

**In-place**: 
- Ordenação sem armazenamento auxiliar significativo

**Sensível a pivô**: 
- Desempenho depende da estratégia de seleção do pivô

**Cache-friendly**: 
- Acesso sequencial à memória melhora performance

```

---
#### 🚀 **Vantagens sobre Outros Algoritmos**

```ad-quote
title: **Def**

**Velocidade prática**: 
- 2-3x mais rápido que Merge Sort na maioria dos casos

**Eficiência espaço**: 
- Melhor que Merge Sort (O(n)) e comparável a Heap Sort

**Adaptabilidade**: 
- Desempenho melhora com dados parcialmente ordenados
```

---
#### 💡 **Quando Utilizar**

```ad-quote
title: **Def**
**01)**
- Para conjuntos de dados gerais onde velocidade é crítica

**02)**
- Quando espaço de memória é limitado

**03)**
- Em linguagens que otimizam recursão (C/C++)

**04)**
- Como base para algoritmos híbridos (Introsort, Timsort)
```

---
#### ❗ **Limitações**

```ad-quote
title: **Def**
**01)**
- Pior caso O(n²) em dados já ordenados/quase ordenados

**02)**
- Não estável sem modificações

**03)**
- Desempenho degrada com muitos elementos repetidos

**04)**
- Vulnerável a ataques de negação de serviço (pivô mal escolhido)
```

---
#### 🛠️ **Otimizações Comuns**

```ad-quote
title: **Def**

**Seleção de pivô inteligente**:  
- Mediana de três/randômica/ninther para evitar O(n²)  

**Insertion Sort para pequenas partições**:  
- Troca para Insertion Sort quando partições são pequenas (~10 elementos)  

**Versão iterativa**:  
- Implementação com pilha explícita para evitar overflow  

**Particionamento de 3 vias**:  
- Eficiente para muitos elementos repetidos (Dutch National Flag)  

**Tail recursion elimination**:  
- Otimiza uso da pilha de chamadas
```

--- 
#### **Nota sobre Implementações Práticas**

```c
// Estratégia comum de pivô (mediana de três)
int median_of_three(int arr[], int low, int high) {
    int mid = low + (high - low)/2;
   if (arr[mid] < arr[low]) swap(&arr[low], &arr[mid]);
   if (arr[high] < arr[low]) swap(&arr[low], &arr[high]);
    if (arr[mid] < arr[high]) swap(&arr[mid], &arr[high]);
    return partition(arr, low, high);
}
```

---