
---

```ad-example

#### **Selection Sort em C / Algoritmo de Ordenação por Seleção**
```

---
#### 📌 **Introdução**

```ad-quote
title: **Def**

O Selection Sort é um algoritmo de ordenação simples que divide o array em duas partes: uma ordenada e outra não ordenada. A cada iteração, o menor elemento da parte não ordenada é selecionado e movido para o final da parte ordenada.
```

---
#### 🔧 **Implementação em C**

```c
#include <stdio.h>

void selectionSort(int arr[], int n) { // ( 1 )
    for (int i = 0; i < n-1; i++) { // ( 2 )
        int min_idx = i; // ( 3 )
        for (int j = i+1; j < n; j++) { // ( 4 )
            if (arr[j] < arr[min_idx]) { // ( 5 )
                min_idx = j;
            }
        }
// Troca o menor elemento encontrado com o primeiro elemento não ordenado
        int temp = arr[min_idx];
        arr[min_idx] = arr[i];
        arr[i] = temp; // ( 6 )
    }
}

int main() {
    int arr[] = {5, 3, 8, 4, 2};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    printf("Array original: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    selectionSort(arr, n);
    
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

**Função selectionSort**:
   - ( 1 ) - Recebe um array e seu tamanho como parâmetros  
   - ( 2 ) - Loop externo controla a posição atual do início da parte não ordenada  
   - ( 3 ) - Assume que o menor elemento é o primeiro da parte não ordenada  
   - ( 4 ) - Loop interno procura o menor elemento na parte não ordenada  
   - ( 5 ) - Atualiza o índice do menor elemento quando encontra um valor menor  
   - ( 6 ) - Troca o menor elemento encontrado com o primeiro da parte não ordenada  

**Função main**:
   - Declara e inicializa um array de exemplo  
   - Chama a função selectionSort para ordenar o array  
   - Imprime o array antes e depois da ordenação  
```

```
Início da ordenação:
5 3 8 4 2 
Barra de ordenacao: |
--- Passagem 1 ---
Procurando mínimo a partir da posição 0:
  Comparando 5 com 3 → novo mínimo: 3 (índice 1)
  Comparando 3 com 8 → mantém mínimo
  Comparando 3 com 4 → mantém mínimo
  Comparando 3 com 2 → novo mínimo: 2 (índice 4)
Troca 5 (posição 0) com 2 (posição 4)
Resultado: 2 | 3 8 4 5 

--- Passagem 2 ---
Procurando mínimo a partir da posição 1:
  Comparando 3 com 8 → mantém mínimo
  Comparando 3 com 4 → mantém mínimo
  Comparando 3 com 5 → mantém mínimo
Nenhuma troca necessária
Resultado: 2 3 | 8 4 5 

--- Passagem 3 ---
Procurando mínimo a partir da posição 2:
  Comparando 8 com 4 → novo mínimo: 4 (índice 3)
  Comparando 4 com 5 → mantém mínimo
Troca 8 (posição 2) com 4 (posição 3)
Resultado: 2 3 4 | 8 5 

--- Passagem 4 ---
Procurando mínimo a partir da posição 3:
  Comparando 8 com 5 → novo mínimo: 5 (índice 4)
Troca 8 (posição 3) com 5 (posição 4)
Resultado final: 2 3 4 5 8 | 
```

![[Pasted image 20250520220143.png]]

---
#### ⚙️ **Complexidade e Desempenho**

```ad-quote
title: **Def**

**Melhor caso**: 
- O(n²) - mesmo quando o array já está ordenado

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

**In-place**: 
- Não requer memória adicional significativa

**Poucas trocas**: 
- Realiza no máximo n-1 trocas (útil quando operações de troca são custosas)

**Não adaptável**: 
- O tempo de execução não melhora com arrays parcialmente ordenados
```

---
#### 🚀 **Vantagens sobre Bubble Sort**

```ad-quote
title: **Def**

**Eficiência em trocas**: 
- Realiza O(n) trocas contra O(n²) do Bubble Sort

**Performance consistente**: 
- Tempo de execução não varia significativamente entre melhor/pior caso

**Melhor para memórias flash**: 
- Ideal para dispositivos onde operações de escrita são limitadas
```

---
#### 💡 **Quando Utilizar**

```ad-quote
title: **Def**
** 01)**
- Para conjuntos de dados pequenos (até 1000 elementos)

** 02)**
- Quando a quantidade de trocas deve ser minimizada

** 03)**
- Em sistemas com restrições de memória (implementação in-place)
```

--- 
#### ❗ **Limitações**

```ad-quote
title: **Def**
** 01)**
- Ineficiente para grandes conjuntos de dados

** 02)**
- Não aproveita a ordenação parcial do array

** 03)**
- Pior performance que Insertion Sort na maioria dos casos práticos
```

---

