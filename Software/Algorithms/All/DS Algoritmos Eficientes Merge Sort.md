
---

```ad-quote
title: **Def**

O Merge Sort é um algoritmo de ordenação eficiente que utiliza a estratégia "dividir para conquistar". Ele divide recursivamente a lista em sublistas menores, ordena-as e depois as combina (merge) para produzir a lista final ordenada.
```

---

>[!example] #### **Merge Sort em C / Algoritmo de Ordenação por Divisão e Conquista**

---
##### *Estrutura Merge Sort*

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
#include <stdlib.h>

// Função para combinar duas sublistas ordenadas
// Parâmetros:
// arr[] - array a ser ordenado
// l - índice inicial da sublista esquerda
// m - índice do meio (fim da sublista esquerda)
// r - índice final da sublista direita
void merge(int arr[], int l, int m, int r) {
    // Calcula o tamanho das duas sublistas
    int n1 = m - l + 1;  // Tamanho da sublista esquerda
    int n2 = r - m;      // Tamanho da sublista direita
    
    // Cria arrays temporários para armazenar as sublistas
    int L[n1], R[n2];  // L = sublista esquerda, R = sublista direita
    
    // Copia os dados para os arrays temporários
    for (int i = 0; i < n1; i++)
        L[i] = arr[l + i];          // Copia a sublista esquerda
    for (int j = 0; j < n2; j++)
        R[j] = arr[m + 1 + j];      // Copia a sublista direita
    
    // Combina as duas sublistas ordenadas
    int i = 0;      // Índice inicial da sublista esquerda
    int j = 0;      // Índice inicial da sublista direita
    int k = l;      // Índice inicial do array original
    
    // Compara os elementos das duas sublistas e insere o menor no array original
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {  // Se elemento da esquerda for menor ou igual
            arr[k] = L[i];   // Copia para o array original
            i++;             // Avança no array esquerdo
        } else {
            arr[k] = R[j];   // Caso contrário, copia o elemento da direita
            j++;             // Avança no array direito
        }
        k++;                 // Avança no array original
    }
    
    // Copia os elementos restantes da sublista esquerda (se houver)
    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }
    
    // Copia os elementos restantes da sublista direita (se houver)
    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}

// Função principal do Merge Sort que implementa a abordagem dividir e conquistar
// Parâmetros:
// arr[] - array a ser ordenado
// l - índice inicial do subarray
// r - índice final do subarray
void mergeSort(int arr[], int l, int r) {
    if (l < r) {  // Condição de parada: subarray com tamanho > 1
        // Encontra o ponto médio para dividir o array
        int m = l + (r - l) / 2;  // Equivalente a (l+r)/2, mas evita overflow
        
        // Ordena recursivamente as duas metades
        mergeSort(arr, l, m);      // Ordena a primeira metade (l até m)
        mergeSort(arr, m + 1, r);  // Ordena a segunda metade (m+1 até r)
        
        // Combina as duas metades ordenadas
        merge(arr, l, m, r);
    }
}

// Função principal
int main() {
    // Array de exemplo
    int arr[] = {5, 3, 8, 4, 2};
    int n = sizeof(arr)/sizeof(arr[0]);  // Calcula o tamanho do array
    
    // Imprime o array original
    printf("Array original: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    // Chama o Merge Sort para ordenar o array
    mergeSort(arr, 0, n - 1);  // Ordena do índice 0 até n-1
    
    // Imprime o array ordenado
    printf("\nArray ordenado: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    return 0;
}
```

---
#### 🌐 **Visualização do Processo**

```
Array original: [5, 3, 8, 4, 2]

1. Divisão:

   [5, 3, 8]       | [4, 2]
   [5] | [3, 8]    | [2] | [4]
         [3] | [8] |

2. Combinação:

	Esquerda:
		[3, 8] | [5]
	    [3, 5, 8]
	Direita:
		[2, 4]
	Merge:
		[3, 5, 8] | [2, 4]
		[2, 3, 4, 5, 8]

Final: [2, 3, 4, 5, 8]
```

##### **VP )** *Visualizacao da Recursão*

```cpp
Nível 0: mergeSort([5,3,8,4,2], 0, 4)
           divide em m = 2
           ├─ Nível 1: mergeSort([5,3,8], 0, 2)
           │    divide em m = 1
           │    ├─ Nível 2: mergeSort([5,3], 0, 1)
           │    │    divide em m = 0
           │    │    ├─ Nível 3: mergeSort([5], 0, 0) → caso base (retorna)
           │    │    └─ Nível 3: mergeSort([3], 1, 1) → caso base (retorna)
           │    │    merge([5,3], 0, 0, 1) → [3,5]
           │    │
           │    └─ Nível 2: mergeSort([8], 2, 2) → caso base (retorna)
           │    merge([3,5,8], 0, 1, 2) → [3,5,8]
           │
           └─ Nível 1: mergeSort([4,2], 3, 4)
                divide em m = 3
                ├─ Nível 2: mergeSort([4], 3, 3) → caso base (retorna)
                └─ Nível 2: mergeSort([2], 4, 4) → caso base (retorna)
                merge([4,2], 3, 3, 4) → [2,4]
           merge([3,5,8,2,4], 0, 2, 4) → [2,3,4,5,8]
```

---
#### ⚙️ **Complexidade e Desempenho**

```ad-quote
title: **Def**

**Todos os casos**: 
- O(n log n) - tempo garantido em qualquer cenário

**Espaço auxiliar**: 
- O(n) - requer arrays temporários para o merge

**Estabilidade**: 
- Estável - mantém a ordem de elementos iguais
```

---
#### 🔍 **Características Principais**

```ad-quote
title: **Def**

**Consistência**: 
- Desempenho previsível independente da distribuição dos dados

**Paralelizável**: 
- Divisão natural permite implementação paralela eficiente

**Versatilidade**: 
- Funciona bem com estruturas de dados encadeadas

**Não-adaptável**: 
- Tempo de execução não melhora com dados parcialmente ordenados
```

---
#### 🚀 **Vantagens sobre Algoritmos Simples**

```ad-quote
title: **Def**

**Eficiência garantida**: 
- Supera algoritmos O(n²) para n > ~100 elementos

**Escalabilidade**: 
- Mantém bom desempenho com grandes conjuntos de dados

**Ordenação externa**: 
- Pode ser adaptado para ordenar dados em disco/memória secundária
```

---
#### 💡 **Quando Utilizar**

```ad-quote
title: **Def**
**01)**
- Para conjuntos médios/grandes de dados (acima de 1000 elementos)

**02)**
- Quando se necessita de estabilidade na ordenação

**03)**
- Em sistemas onde o pior caso deve ser evitado

**04)**
- Como base para algoritmos mais complexos (ex: Timsort)
```

---
#### ❗ **Limitações**

```ad-quote
title: **Def**
**01)**
- Requer espaço adicional O(n)

**02)**
- Overhead de recursão para listas muito pequenas

**03)**
- Implementação iterativa é mais complexa que algoritmos simples
```

---
#### 🛠️ **Otimizações Comuns**

```ad-quote
title: **Def**

**Insertion Sort para pequenas partições**:  
- Usar Insertion Sort quando subarrays têm tamanho ≤ 15-20 elementos  

**Eliminar cópias**:  
- Alternar entre arrays auxiliares para reduzir operações de cópia  

**Versão iterativa**:  
- Implementação não-recursiva para evitar overhead de chamadas  

**Merge in-place**:  
- Técnicas avançadas para reduzir espaço adicional (mais complexas)
```

---