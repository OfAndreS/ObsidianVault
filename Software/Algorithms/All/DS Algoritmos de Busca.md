
---
#### **Quando Escolher Cada Uma:**

```ad-quote
title: **Def**

**Use busca linear** quando:
- Seus dados não estão (e não podem ser) ordenados        
- A lista é pequena (<100 elementos)
- Você faz poucas buscas e muitas inserções

**Use busca binária** quando:
- Seus dados estão ou podem ser mantidos ordenados
- A lista é grande (>1000 elementos)
- Você faz muitas buscas comparado a inserções/remoções
```

---

>[!tip] #### **Busca Linear**

---
#### **Funcionamento Detalhado**

```ad-quote
title: **Def**

A busca linear, também conhecida como busca sequencial, percorre cada elemento de uma estrutura de dados (array, lista, etc.) **um por um**, da primeira posição até a última, comparando cada elemento com o valor alvo até encontrar uma correspondência.
```

```c
int busca_linear(int arr[], int tamanho, int alvo) {

    for (int i = 0; i < tamanho; i++) {

        if (arr[i] == alvo) {

            return i;  // Retorna o índice se encontrado

        }

    }

    return -1;  // Retorna -1 se não encontrado

}
```

---
#### **Características Técnicas:**

```ad-quote
title: **Def**

**Pior caso**: O(n) 
- Quando o elemento está na última posição ou não existe

---

**Melhor caso**: O(1) 
- Quando o elemento está na primeira posição

---

**Caso médio**: O(n/2) ≈ O(n) 
- Em distribuições uniformes
```

---
##### ***Vantagens:***

```ad-quote
title: **Def**

**Simplicidade**: 
- Fácil de entender e implementar
   
**Versatilidade**: 
- Funciona em qualquer estrutura de dados sequencial (listas ligadas, arrays não ordenados)    

**Sem pré-processamento**: 
- Não requer preparação dos dados    
```
##### ***Desvantagens:***

```ad-quote
title: **Def**

**Ineficiente para grandes conjuntos**: 
- Tempo de busca cresce linearmente com o tamanho dos dados

**Não aproveita ordenação**: 
- Se os dados estiverem ordenados, não tira vantagem disso   
```

---
#### **Casos de Uso Ideais:**

```ad-quote
title: **Def**

- Listas com menos de 100 elementos
    
- Quando os dados mudam frequentemente (evitando custo de reordenar)
    
- Implementações simples onde a otimização não é crítica
```

---

>[!tip] #### **Busca Binária**

---
#### **Funcionamento Detalhado**

```ad-quote
title: **Def**

A busca binária opera sobre **dados ordenados**, dividindo repetidamente o espaço de busca pela metade. Compara o elemento central com o alvo e descarta a metade irrelevante.
```
##### *Implementação Iterativa:*

```c
#include <stdio.h>

int busca_binaria_iterativa(int arr[], int tamanho, int alvo) {
    int esq = 0;
    int dir = tamanho - 1;
    
    while (esq <= dir) {
        int meio = esq + (dir - esq) / 2;  // Evita overflow
        
        if (arr[meio] == alvo) {
            return meio;
        } else if (arr[meio] < alvo) {
            esq = meio + 1;
        } else {
            dir = meio - 1;
        }
    }
    
    return -1;  // Elemento não encontrado
}
```
##### *Implementação Recursiva:*

```c
int busca_binaria_recursiva(int arr[], int alvo, int esq, int dir) {
    if (esq > dir) {
        return -1;
    }
    
    int meio = esq + (dir - esq) / 2;
    
    if (arr[meio] == alvo) {
        return meio;
    } else if (arr[meio] < alvo) {
        return busca_binaria_recursiva(arr, alvo, meio + 1, dir);
    } else {
        return busca_binaria_recursiva(arr, alvo, esq, meio - 1);
    }
}
```

---
#### **Características Técnicas:**

```ad-quote
title: **Def**

**Pior caso**: 
- O(log n)

**Melhor caso**: 
- O(1) - Quando o alvo está exatamente no meio

**Requisito absoluto**: 
- Dados devem estar pré-ordenados
```

---
##### ***Vantagens:***

```ad-quote
title: **Def**

**Eficiência**: 
- Extremamente rápida para grandes conjuntos de dados

**Escalabilidade**: 
- O tempo de busca cresce logaritmicamente com o tamanho dos dados
```
##### ***Desvantagens:***

```ad-quote
title: **Def**

**Pré-requisito de ordenação**: 
- Custo de manter dados ordenados

**Complexidade de implementação**: 
- Maior chance de erros de "off-by-one"

**Acesso aleatório necessário**: 
- Não funciona bem em listas ligadas  
```
  
---
### Casos de Uso Ideais:

```ad-quote
title: **Def**

- Bancos de dados indexados
    
- Sistemas onde os dados são estáticos ou pouco alterados
    
- Aplicações que requerem muitas buscas em relação a inserções/remoções
```

---
