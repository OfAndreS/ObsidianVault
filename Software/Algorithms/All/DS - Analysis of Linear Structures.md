
---

```ad-example

#### **Array - Vetor**
```

---
#### **01 )** - Acesso

```ad-quote
title: **Def**

**Acessar no início - índice 0**
- **Custo - O( 1 )**
- Observação: O acesso a qualquer elemento por seu índice é uma operação de tempo constante.

---

**Acessar no meio - índice `i`** 
- **Custo - O( 1 )**
- Observação: Acesso direto via aritmética de ponteiros, independentemente da posição.

---

**Acessar no final**
- **Custo - O( 1 )**
- Observação: O acesso ao último elemento também é direto através de seu índice.
```

---
#### **02 )** - Inserção

```ad-quote
title: **Def**

**Inserir no início**
 
- **Custo - O( n )**
 
- Observação: Requer o deslocamento de todos os `n` elementos existentes para a direita para abrir espaço na posição 0.

---

**Inserir no meio (índice `i`)**

- **Custo - O( n )**

- Observação: Em média, requer o deslocamento de `n - i` elementos para a direita.

---

**Inserir no final**

- **Custo - O( 1 ) amortizado**

- Observação: Geralmente é uma operação O(1), mas pode incorrer em um custo O(n) para redimensionar o array quando sua capacidade é excedida.

```

---
#### **03 )** - Remoção

```ad-quote
title: **Def**

**Remover no início**
- **Custo - $O(n)$**
- Observação: Requer o deslocamento de todos os `n - 1` elementos restantes para a esquerda para preencher o espaço.

---

**Remover no meio (índice `i`)**
- **Custo - $O(n)$**
- Observação: Requer o deslocamento dos `n - i - 1` elementos à direita da posição removida.

---

**Remover no final**
- **Custo - $O(1)$**
- Observação: Apenas diminui o marcador de tamanho do array, não exige deslocamento de elementos.
```

---

```ad-example

#### **Lista Ligada Simples - Singly Linked List**
```

---

#### **01 )** - Acesso

```ad-quote
title: **Def**

**Acessar no início (cabeça/head)**
- **Custo - $O(1)$**
- Observação: O ponteiro da cabeça (`head`) aponta diretamente para o primeiro nó.

---

**Acessar no meio**
- **Custo - $O(n)$**
- Observação: É necessário percorrer a lista a partir da cabeça até a posição desejada.

---

**Acessar no final (cauda/tail)**
- **Custo - $O(n)$**
- Observação: É necessário percorrer toda a lista desde a cabeça. Se um ponteiro para a cauda for mantido, o acesso direto ao nó é $O(1)$, mas o acesso ao seu *predecessor* ainda é $O(n)$.
```

---

#### **02 )** - Inserção

```ad-quote
title: **Def**

**Inserir no início**
- **Custo - $O(1)$**
- Observação: Apenas envolve a atualização de ponteiros na cabeça da lista.

---

**Inserir no meio**
- **Custo - $O(n)$**
- Observação: O custo é dominado pelo tempo necessário para encontrar o ponto de inserção. A inserção em si é $O(1)$ uma vez que o nó anterior é encontrado.

---

**Inserir no final**
- **Custo - $O(1)$ se um ponteiro para a cauda (`tail`) for mantido. $O(n)$ se não for.**
- Observação: Com um ponteiro para a cauda, a inserção é direta. Sem ele, é preciso percorrer toda a lista para encontrar o último nó.
```

---

#### **03 )** - Remoção

```ad-quote
title: **Def**

**Remover no início**
- **Custo - $O(1)$**
- Observação: Simplesmente move o ponteiro da cabeça para o segundo nó.

---

**Remover no meio**
- **Custo - $O(n)$**
- Observação: Requer percorrer a lista para encontrar o nó *anterior* ao que será removido, para então poder atualizar seu ponteiro.

---

**Remover no final**
- **Custo - $O(n)$**
- Observação: Mesmo com um ponteiro para a cauda, é preciso percorrer a lista inteira para encontrar o nó *penúltimo* e atualizar seu ponteiro para `null`.
```

---

```ad-example

#### **Lista Duplamente Ligada - Doubly Linked List**
```

---
#### **01 )** - Acesso

```ad-quote
title: **Def**

**Acessar no início (cabeça/head)**
- **Custo - $O(1)$**
- Observação: Acesso direto através do ponteiro da cabeça.

---

**Acessar no meio**
- **Custo - $O(n)$**
- Observação: Requer percorrer a lista a partir de uma das extremidades. Pode ser otimizado para $O(n/2)$ se a busca começar da extremidade mais próxima, mas isso ainda é $O(n)$.

---

**Acessar no final (cauda/tail)**
- **Custo - $O(1)$**
- Observação: Acesso direto através do ponteiro da cauda.
```

---
#### **02 )** - Inserção

```ad-quote
title: **Def**

**Inserir no início**
- **Custo - $O(1)$**
- Observação: Envolve a atualização de ponteiros na cabeça (`head`) e no novo nó.

---

**Inserir no meio**
- **Custo - $O(n)$**
- Observação: O custo dominante é o de encontrar a posição. A inserção em si, após encontrar o nó, é $O(1)$ pois temos acesso aos vizinhos em ambas as direções.

---

**Inserir no final**
- **Custo - $O(1)$**
- Observação: Envolve a atualização de ponteiros na cauda (`tail`) e no novo nó.
```

---
#### **03 )** - Remoção

```ad-quote
title: **Def**

**Remover no início**
- **Custo - $O(1)$**
- Observação: Atualização simples de ponteiros na cabeça.

---

**Remover no meio**
- **Custo - $O(n)$ se o nó precisa ser encontrado. $O(1)$ se a referência do nó já for conhecida.**
- Observação: Se o nó a ser removido já é conhecido, a remoção é $O(1)$ porque seus vizinhos (anterior e próximo) são diretamente acessíveis através de seus ponteiros, facilitando a religação.

---

**Remover no final**
- **Custo - $O(1)$**
- Observação: O ponteiro `previous` do último nó permite encontrar o penúltimo nó instantaneamente para que ele se torne a nova cauda.
```

---

```ad-error

### **Implementação do TAD Pilha - LIFO**
```

---
#### **01) - Array / Vetor Dinâmico**

```ad-quote
**Estado:** 
- Mantém-se o **array** e um contador **tamanho** que indica a próxima posição livre e o número de elementos. O topo da pilha é a posição **tamanho** - 1.
```

```ad-quote
title: **push(valor)**
1.  Verifica-se se **tamanho** é igual à capacidade do **array**. Se for, o **array** é redimensionado (operação custosa).
2.  O **valor** é inserido em **array[tamanho]**.
3.  O contador **tamanho** é incrementado.

---

**Custo:** $O(1)$.
```

```ad-quote
title: **pop()**
1.  Verifica-se se a pilha está vazia (**tamanho** == 0).
2.  O valor de **array[tamanho - 1]** é lido e salvo.
3.  O contador **tamanho** é decrementado.
4.  O valor salvo é retornado.

---

**Custo:** $O(1)$.
```

```ad-quote
title: **peek()**
1.  Verifica-se se a pilha está vazia.
2.  O valor de **array[tamanho - 1]** é retornado sem alterar o **tamanho**.

---

**Custo:** $O(1)$.
```

---

>[!error] _New_

---
#### **02) - Lista Ligada Simples**

```ad-quote
**Estado:** Mantém-se apenas um ponteiro, **topo**, que aponta para a cabeça (**head**) da lista. Uma lista vazia tem **topo** == **null**.
```

```ad-quote
title: **push(valor)**
1.  Cria-se um novo nó com o **valor**.
2.  O ponteiro **proximo** do novo nó é definido para apontar para o **topo** atual.
3.  O ponteiro **topo** da pilha é atualizado, passando a apontar para o novo nó.

---

**Custo:** $O(1)$.
```

```ad-quote
title: **pop()**
1.  Verifica-se se **topo** == **null**.
2.  O valor do nó **topo** é salvo.
3.  O ponteiro **topo** é atualizado para **topo.proximo**, efetivamente removendo o primeiro nó.
4.  O valor salvo é retornado.

---

**Custo:** $O(1)$.
```

```ad-quote
title: **peek()**
1.  Verifica-se se **topo** == **null**.
2.  O valor do nó **topo** é retornado sem modificar a estrutura.

---

**Custo:** $O(1)$.
```

---

>[!error] _New_

---
#### **03) - Lista Duplamente Ligada**

```ad-quote
A implementação é conceitualmente idêntica à da Lista Ligada Simples, usando a cabeça (**head**) da lista como o **topo**. A única diferença prática é a gestão adicional do ponteiro **anterior**, que não é utilizado pela lógica da pilha, mas precisa ser mantido. A complexidade de todas as operações permanece $O(1)$.
```

---

```ad-error

### **Implementação do TAD Fila - FIFO**
```

---
#### **04) - Array / Vetor**

```ad-quote
**Abordagem Ineficiente:** Usar um array padrão onde o início é sempre o índice 0 leva a uma remoção de custo $O(n)$, pois requer o deslocamento de todos os elementos.

**Abordagem Eficiente (Array Circular):**
**Estado:** Mantém-se o **array** e os índices **inicio**, **fim** e **tamanho** para controlar a porção de dados válidos.
```

```ad-quote
title: **enqueue(valor)**
1.  Verifica-se se a fila está cheia (**tamanho** == **capacidade**).
2.  O **valor** é inserido na posição **array[fim]**.
3.  O índice **fim** é atualizado de forma circular: **fim** = (**fim** + 1) % **capacidade**.
4.  O **tamanho** é incrementado.

---

**Custo:** $O(1)$.
```

```ad-quote
title: **dequeue()**
1.  Verifica-se se a fila está vazia (**tamanho** == 0).
2.  O valor de **array[inicio]** é lido e salvo.
3.  O índice **inicio** é atualizado de forma circular: **inicio** = (**inicio** + 1) % **capacidade**.
4.  O **tamanho** é decrementado.

---

**Custo:** $O(1)$.
```

---

>[!error] _New_

---
#### **05) - Lista Ligada Simples**

```ad-quote
**Estado:** Mantêm-se dois ponteiros, **inicio** (para a cabeça) e **fim** (para a cauda). Em uma fila vazia, ambos são **null**.
```

```ad-quote
title: **enqueue(valor)**
1.  Cria-se um novo nó com o **valor**.
2.  Se a fila está vazia, **inicio** e **fim** passam a apontar para o novo nó.
3.  Caso contrário, o **proximo** do nó **fim** atual passa a apontar para o novo nó.
4.  O ponteiro **fim** é atualizado para apontar para o novo nó.

---

**Custo:** $O(1)$.
```

```ad-quote
title: **dequeue()**
1.  Verifica-se se a fila está vazia (**inicio** == **null**).
2.  O valor do nó **inicio** é salvo.
3.  O ponteiro **inicio** é atualizado para **inicio.proximo**.
4.  Se a fila ficou vazia (**inicio** == **null**), o ponteiro **fim** também é atualizado para **null**.

---

**Custo:** $O(1)$.
```

---

>[!error] _New_

---
#### **06) - Lista Duplamente Ligada**

```ad-quote
A implementação é muito semelhante à da Lista Ligada Simples, usando ponteiros **inicio** e **fim**. O ponteiro **anterior** de cada nó facilita certas operações e torna o código ligeiramente diferente, mas o conceito e a eficiência são os mesmos. As operações **enqueue** e **dequeue** permanecem com custo $O(1)$.
```

---