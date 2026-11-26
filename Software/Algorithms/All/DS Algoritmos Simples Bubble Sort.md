
---

```ad-example

#### **Bubble Sort em C / Algoritmo de Ordenação por Troca**
```

---
#### 📌 **Introdução**

```ad-quote
title: **Def**

O Bubble Sort é um dos algoritmos de ordenação mais simples, baseado na comparação e troca de elementos adjacentes. Embora fácil de implementar, sua eficiência é limitada para conjuntos grandes de dados.
```

---
#### 🔧 **Implementação em C**

```c
#include <stdio.h>
#include <stdbool.h>

void bubbleSort(int arr[], int n) { // ( 1 )
    for (int i = 0; i < n-1; i++) { // ( 2 )
        bool swapped = false;
        for (int j = 0; j < n-i-1; j++) { // ( 2 )
            if (arr[j] > arr[j+1]) { // ( 3 )
                // Troca os elementos
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
                swapped = true;
            }
        }
        // Se nenhuma troca ocorreu, o array está ordenado
        if (!swapped) break; // ( 4 )
    }
}

int main() {
    int arr[] = {5, 3, 8, 4, 2};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    printf("Array original: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    bubbleSort(arr, n);
    
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

**Função bubbleSort**:
   - ( 1 ) - Recebe um array e seu tamanho como parâmetros
   - ( 2 ) - Utiliza dois loops aninhados para percorrer o array
   - ( 3 ) - Compara elementos adjacentes e os troca se estiverem na ordem errada
   - ( 4 ) - Inclui uma otimização que interrompe o processo se nenhuma troca ocorrer em uma passagem completa

**Função main**:
   - Declara e inicializa um array de exemplo
   - Chama a função bubbleSort para ordenar o array
   - Imprime o array antes e depois da ordenação
```

```
Início da ordenação:
5 3 8 4 2 

--- Passagem 1 ---
Comparando [5] e [3]: 5 3 8 4 2 
  -> Troca realizada: 3 5 8 4 2 
Comparando [5] e [8]: 3 5 8 4 2 
  -> Mantém a ordem
Comparando [8] e [4]: 3 5 8 4 2 
  -> Troca realizada: 3 5 4 8 2 
Comparando [8] e [2]: 3 5 4 8 2 
  -> Troca realizada: 3 5 4 2 8 
Resultado após passagem 1: 3 5 4 2 8 

--- Passagem 2 ---
Comparando [3] e [5]: 3 5 4 2 8 
  -> Mantém a ordem
Comparando [5] e [4]: 3 5 4 2 8 
  -> Troca realizada: 3 4 5 2 8 
Comparando [5] e [2]: 3 4 5 2 8 
  -> Troca realizada: 3 4 2 5 8 
Resultado após passagem 2: 3 4 2 5 8 

--- Passagem 3 ---
Comparando [3] e [4]: 3 4 2 5 8 
  -> Mantém a ordem
Comparando [4] e [2]: 3 4 2 5 8 
  -> Troca realizada: 3 2 4 5 8 
Resultado após passagem 3: 3 2 4 5 8 

--- Passagem 4 ---
Comparando [3] e [2]: 3 2 4 5 8 
  -> Troca realizada: 2 3 4 5 8 
Resultado após passagem 4: 2 3 4 5 8 

Nenhuma troca realizada - array ordenado!

Array final ordenado: 2 3 4 5 8 
```

![[Pasted image 20250520215513.png]]

---
#### ⚙️ **Complexidade e Desempenho**

```ad-quote
title: **Def**

**Melhor caso**: 
- O(n) - quando o array já está ordenado

**Pior caso**: 
- O(n²) - quando o array está em ordem inversa

**Caso médio**: 
- O(n²) - para dados aleatórios
```

---
#### 🔍 **Características Principais**

```ad-quote
title: **Def**

**Simplicidade**: 
- Fácil de entender e implementar

**Estabilidade**: 
- Mantém a ordem relativa de elementos iguais

**In-place**: 
- Não requer memória adicional significativa

**Adaptabilidade**: 
- Pode detectar se o array já está ordenado
```

---
#### 🚀 **Otimizações Implementadas**

```ad-quote
title: **Def**

**Early Termination**: 
- O algoritmo para se nenhuma troca for feita em uma passagem completa

**Redução do Espaço de Busca**: 
- A cada passagem, o maior elemento é posicionado corretamente, reduzindo o número de comparações necessárias

```

---
#### 💡 **Quando Utilizar**

```ad-quote
title: **Def**
** 01)**
- Para pequenos conjuntos de dados (até 1000 elementos)

** 02)**
- Quando a simplicidade de implementação é mais importante que a eficiência
```

---
