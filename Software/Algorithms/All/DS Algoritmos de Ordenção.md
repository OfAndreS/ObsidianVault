
---

```ad-quote
title: **Def**

Os algoritmos de ordenação são fundamentais na ciência da computação, permitindo organizar dados em uma sequência específica (crescente ou decrescente). Vamos explorar os principais algoritmos:
```

---
## Considerações na Escolha

```ad-quote
title: **Def**

**Tamanho dos dados**: 
- Para pequenos conjuntos, algoritmos O(n²) podem ser melhores

**Estrutura dos dados**: 
- Alguns algoritmos são mais eficientes para dados parcialmente ordenados

**Estabilidade**: 
- Importante quando a ordem relativa de elementos iguais deve ser mantida

**Memória disponível**: 
- Alguns algoritmos como Merge Sort requerem espaço adicional

A escolha do algoritmo ideal depende do contexto específico e dos requisitos da aplicação.
```

---
#### **Carcteristicas**

```ad-quote
title: **Def**

Aqui está uma análise concisa dos três conceitos fundamentais em algoritmos de ordenação:
```

---
#### **In-place**

```ad-quote
title: Definição
**Algoritmos que operam diretamente no array original**, usando apenas uma quantidade constante de espaço adicional (O(1)). Exemplos clássicos: 
- Quick Sort (particionamento in-place) 
- Heap Sort
- Insertion Sort

**Vantagem**: Eficiência de memória (crucial para sistemas embarcados ou grandes datasets).  
**Trade-off**: Algumas otimizações podem ser sacrificadas (ex: Merge Sort padrão não é in-place).
```

---
#### **Estabilidade**

```ad-quote
title: Definição
**Preserva a ordem relativa de elementos com chaves idênticas**. Crucial quando a ordem inicial carrega informação (ex: ordenar por nome após ordenar por departamento).

**Estáveis**:  
- Merge Sort  
- Insertion Sort  
- Timsort  

**Não-estáveis**:  
- Quick Sort (a menos que use partição estável)  
- Heap Sort  
- Selection Sort  

**Técnica para estabilizar**: Usar índices originais como critério secundário de ordenação.
```

---
#### **Paralelizável**

```ad-quote
title: Definição
**Capacidade de dividir o trabalho entre múltiplos núcleos/threads**. Fator crítico para big data e GPUs.

**Altamente paralelizáveis**:  
- Merge Sort (divisão natural independente)  
- Quick Sort (partições independentes)  
- Bucket Sort  

**Desafios**:  
- Overhead de sincronização  
- Balanceamento de carga desigual (ex: Quick Sort com pivô mal escolhido)  

**Exemplo prático**: `parallel_sort` na biblioteca C++17 usa divisão recursiva multi-thread.
```

---

>[!example] #### **Algoritmos Simples / O(n²)**

---

```ad-quote
title: **Def**
| **Propriedade**        | **Insertion Sort**  /  /  /  | **Selection Sort**  /  /  /  | **Bubble Sort**  /  /  /  |
| ---------------------- | -------------------------- | -------------------------- | ------------------------- |
| **In-place**           | ✅ Sim                      | ✅ Sim                      | ✅ Sim                     |
| **Estável**            | ✅ Sim                      | ❌ Não                      | ✅ Sim                     |
| **Paralelizável**      | ❌ Não <br>                 | ❌ Não                      | ❌ Não                     |
| **Caso Médio (Big-O)** | **O(n²)**                  | **O(n²)**                  | **O(n²)**                 |
| **Melhor Caso**        | **O(n)** )                 | **O(n²)**                  | **O(n)**                  |
| **Pior Caso**          | **O(n²)**                  | **O(n²)**                  | **O(n²)**                 |

```

```ad-quote
title: **Def**

**Bubble Sort**
   - Compara pares adjacentes e os troca se estiverem na ordem errada
   - Repete até não haver mais trocas
   - Complexidade: O(n²) no pior caso

---

**Selection Sort**
   - Divide a lista em duas partes: ordenada e não ordenada
   - Seleciona o menor elemento da parte não ordenada e coloca no final da parte ordenada
   - Complexidade: O(n²)

---

**Insertion Sort**
   - Constrói a lista ordenada um item de cada vez
   - Pega cada elemento e insere na posição correta na parte já ordenada
   - Complexidade: O(n²) no pior caso, mas eficiente para pequenos conjuntos
```

>[!quote] ***Vault:*** [[DS Algoritmos Simples Bubble Sort]]

>[!quote] ***Vault:*** [[DS Algoritmos Simples Selection Sort]]

>[!quote] ***Vault:*** [[DS Algoritmos Simples Insertion Sort]]

---

>[!example] #### **Algoritmos Eficientes (O(n log n))**

---
```ad-cite


| **Propriedade**           | **Quick Sort** = = = = = | **Merge Sort** = = = = = | **Heap Sort** = = = = = |
| ------------------------- | ------------------------ | ------------------------ | ----------------------- |
| **In-place**              | ✅ Sim                    | ❌ Não                    | ✅ Sim                   |
| **Estável**               | ❌ Não                    | ✅ Sim                    | ❌ Não                   |
| **Paralelizável**         | ✅ Sim                    | ✅ Sim                    | ❌ Difícil               |
| **Caso Médio (Big-O)**    | **O(n log n)**           | **O(n log n)**           | **O(n log n)**          |
| **Melhor Caso**           | **O(n log n)**           | **O(n log n)**           | **O(n log n)**          |
| **Pior Caso**             | **O(n²)**                | **O(n log n)**           | **O(n log n)**          |
| **Complexidade Espacial** | **O(log n)**             | **O(n)**                 | **O(1)**                |

```

```ad-quote
title: **Def**

**Merge Sort**
   - Divide e conquista: divide a lista em metades, ordena cada metade e depois combina
   - Estável (mantém ordem de elementos iguais)
   - Complexidade: O(n log n) em todos os casos

---

**Quick Sort**
   - Escolhe um elemento pivô e particiona a lista em elementos menores e maiores que o pivô
   - Ordena recursivamente as sublistas
   - Complexidade média: O(n log n), pior caso O(n²)

---

**Heap Sort**
   - Constrói uma heap a partir dos dados
   - Remove repetidamente o maior elemento da heap e reconstroi a heap
   - Complexidade: O(n log n)
```

>[!quote] ***Vault:*** [[DS Algoritmos Eficientes Heap Sort]]

>[!quote] ***Vault:*** [[DS Algoritmos Eficientes Quick Sort]]

>[!quote] ***Vault:*** [[DS Algoritmos Eficientes Merge Sort]]

---

>[!example] #### **Algoritmos Especiais**

---

```ad-quote
title: **Def**

**Counting Sort**
   - Não baseado em comparação
   - Funciona contando o número de objetos com valores distintos
   - Complexidade: O(n + k) onde k é o range dos dados

---

**Radix Sort**
   - Ordena números processando dígitos individuais
   - Pode usar counting sort como sub-rotina
   - Complexidade: O(nk) para n números com k dígitos

---

**Bucket Sort**
   - Divide os elementos em baldes (buckets) e ordena cada balde individualmente
   - Eficiente quando a entrada é uniformemente distribuída
```

>[!quote] ***Vault:*** [[DS Algoritmos Especiais]]

---
