
---

```ad-example

#### **Insertion Sort em C / Algoritmo de Ordenação por Inserção**
```

---
#### 📌 **Introdução**

```ad-quote
title: **Def**

O Insertion Sort é um algoritmo de ordenação simples que constrói a lista ordenada um elemento de cada vez, movendo elementos não ordenados para a posição correta na parte ordenada. É eficiente para pequenos conjuntos de dados ou arrays quase ordenados.
```

---
#### 🔧 **Implementação em C**

```c
#include <stdio.h>

void insertionSort(int arr[], int n) { // (1)
    for (int i = 1; i < n; i++) { // (2)
        int key = arr[i]; // (3)
        int j = i - 1;
        
        // Move os elementos maiores que key para uma posição à frente
        while (j >= 0 && arr[j] > key) { // (4)
            arr[j + 1] = arr[j]; // (5)
            j--;
        }
        arr[j + 1] = key; // (6)
    }
}

int main() {
    int arr[] = {5, 3, 8, 4, 2};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    printf("Array original: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    insertionSort(arr, n);
    
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

**Função insertionSort**:
   - (1) - Recebe um array e seu tamanho como parâmetros  
   - (2) - Loop externo itera a partir do segundo elemento  
   - (3) - Seleciona o elemento atual como chave para inserção  
   - (4) - Loop interno move elementos maiores que a chave para a direita  
   - (5) - Deslocamento de elementos dentro do array  
   - (6) - Insere a chave na posição correta  

**Função main**:
   - Demonstração com array de exemplo  
   - Exibe o array antes e depois da ordenação  
```

```
Início da ordenação:
arr = [5, 3, 8, 4, 2] 

--- Passagem 1 (i = arr[1]) ---
Chave: 3
Comparando com 5 → move 5 para direita
Inserindo 3 na posição 0
Resultado: 3 5 | 8 4 2 

--- Passagem 2 (i = arr[2]) ---
Chave: 8
Comparando com 5 → mantém posição
Resultado: 3 5 8 | 4 2 

--- Passagem 3 (i = arr[3]) ---
Chave: 4
Comparando com 8 → move 8 para direita
Comparando com 5 → move 5 para direita
Encontra posição para 4
Resultado: 3 4 5 8 | 2 

--- Passagem 4 (i = arr[4]) ---
Chave: 2
Comparando com 8 → move 8 para direita
Comparando com 5 → move 5 para direita
Comparando com 4 → move 4 para direita
Comparando com 3 → move 3 para direita
Inserindo 2 na posição 0
Resultado final: 2 3 4 5 8 |
```

![[Pasted image 20250521005210.png]]

---
#### ⚙️ **Complexidade e Desempenho**

```ad-quote
title: **Def**

**Melhor caso**: 
- O(n) - quando o array já está ordenado (apenas comparações)

**Pior caso**: 
- O(n²) - quando o array está em ordem inversa

**Caso médio**: 
- O(n²) - para dados aleatórios
```

---
#### 🔍 **Características Principais**

```ad-quote
title: **Def**

**Adaptabilidade**: 
- Excelente performance em arrays parcialmente ordenados

**Estabilidade**: 
- Mantém a ordem relativa de elementos iguais

**In-place**: 
- Requer apenas O(1) de memória adicional

**Online**: 
- Pode ordenar dados à medida que são recebidos
```

---
#### 🚀 **Vantagens sobre Bubble e Selection Sort**

```ad-quote
title: **Def**

**Eficiência prática**: 
- Geralmente mais rápido que Bubble e Selection Sort em casos reais

**Menos operações**: 
- Move elementos apenas uma vez (Selection Sort faz O(n) trocas explícitas)

**Melhor caso linear**: 
- Único entre os algoritmos O(n²) com esta característica
```

---
#### 💡 **Quando Utilizar**

```ad-quote
title: **Def**
**01)**
- Para pequenos conjuntos de dados (até 100-1000 elementos)

**02)**
- Quando os dados estão quase ordenados (poucas inversões)

**03)**
- Como parte de algoritmos mais complexos (ex: Timsort)

**04)**
- Em sistemas onde a estabilidade é requerida
```

---
#### ❗ **Limitações**

```ad-quote
title: **Def**
**01)**
- Ineficiente para grandes conjuntos de dados

**02)**
- Desempenho ruim com dados em ordem inversa

**03)**
- Não aproveita elementos já em posição como o Shell Sort
```

---
