---
banner: "![[Pasted image 20250915211800.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify">A Teoria da Álgebra Relacional é uma estrutura matemática formal que define um conjunto de operações sobre relações, constituindo a base teórica para a manipulação de dados em bancos de dados relacionais. Diferente de linguagens de consulta como SQL, que são linguagens comerciais e declarativas, a Álgebra Relacional é uma linguagem procedural que especifica como obter os dados através de uma sequência de operações. Seu valor reside na sua precisão matemática, que permite a análise e otimização formal de consultas.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Fundamentos: O Modelo Relacional Formal

```ad-quote
title:
<p align="justify">Para compreender a teoria da Álgebra Relacional, é imprescindível definir seus componentes sob uma ótica formal:</p>
```

```ad-quote
title:
###### **Componentes Formais:**
```

```ad-quote
title:

|Componente&nbsp; | Definição&nbsp; | Exemplo |
| :--- | :--- | :--- |
|**Domínio (D)**|Um conjunto de valores atômicos e indivisíveis.|O conjunto dos números inteiros, o conjunto de todas as strings de caracteres.|
|**Esquema de Relação (R(A1, A2, ..., An))**|Define a estrutura de uma relação. É composto por um nome (R) e uma lista de atributos.|R(ClienteID, Nome, Email)|
|**Atributo (Ai)**|O nome de uma "coluna". A cada atributo Ai está associado um domínio, dom(Ai).|Nome, Email|
|**Tupla (t)**|Uma lista ordenada de valores <v1, v2, ..., vn>, onde cada valor vi é um elemento do domínio de seu atributo correspondente, vi ∈ dom(Ai).|<123, "Maria", "maria@email.com">|
|**Relação (r)**|Uma instância de um esquema de relação R. Formalmente, uma relação r é um conjunto finito de tuplas distintas.|A tabela CLIENTES com todas as suas linhas.|

```

```ad-quote
title:
<p align="justify">A relação possui duas propriedades cruciais: não há tuplas duplicadas (pois é um conjunto matemático) e a ordem das tuplas é irrelevante.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - A Propriedade de Fechamento

```ad-quote
title:
<p align="justify">Uma característica central da Álgebra Relacional é sua propriedade de fechamento. Isso significa que cada operador da álgebra recebe uma ou mais relações como entrada e produz, invariavelmente, uma nova relação como saída. Essa propriedade é fundamental, pois permite que as operações sejam aninhadas e compostas, formando expressões complexas a partir de operadores simples, da mesma forma que operações aritméticas (+, -, *, /) podem ser combinadas.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Operadores Fundamentais: O Núcleo da Álgebra

```ad-quote
title:
<p align="justify">Os seis operadores a seguir são considerados o núcleo irredutível da Álgebra Relacional, a partir dos quais outros operadores podem ser derivados.</p>
```

```ad-quote
title:
**1. Seleção (σ - Sigma)**
```

```ad-quote
title:

**Tipo**: 
- Operador unário

**Função**: 
- Filtra tuplas de uma relação basedo em um predicado

**Definição Formal**: 
1. $$σ_P(r) = \{ t \in r \mid P(t) \}$$

**Propriedades**: 
  - Mantém o mesmo esquema da relação original
  - Comutativa: $σ_{P1}(σ_{P2}(r)) ≡ σ_{P2}(σ_{P1}(r)) ≡ σ_{P1 \land P2}(r)$
```

```ad-quote
title:
**2. Projeção (π - Pi)**
```


```ad-quote
title:

**Tipo**:
- Operador unário

**Função**:
- Seleciona um subconjunto de atributos (colunas)

**Definição Formal**:
1. $$π_{A_1, A_2, ..., A_k}(r) = \{ t[A_1, A_2, ..., A_k] \mid t \in r \}$$

**Propriedades**:
  - Elimina tuplas duplicadas resultantes
  - Produz nova relação com esquema reduzido
```


```ad-quote
title:
**3. União (∪)**
```


```ad-quote
title:

**Tipo**:
- Operador binário

**Função**:
- Combina tuplas de duas relações compatíveis

**Definição Formal**:
1. $$r ∪ s = \{ t \mid t \in r \text{ ou } t \in s \}$$

**Propriedades**:
  - Requer compatibilidade de esquema (união-compatível)
  - Comutativa: $r ∪ s = s ∪ r$
  - Associativa: $(r ∪ s) ∪ t = r ∪ (s ∪ t)$
```


```ad-quote
title:
**4. Diferença de Conjuntos (-)**
```


```ad-quote
title:

**Tipo**:
- Operador binário

**Função**:
- Encontra tuplas presentes em r mas não em s

**Definição Formal**:
1. $$r - s = \{ t \mid t \in r \text{ e } t \notin s \}$$

**Propriedades**:
  - Requer compatibilidade de esquema
  - Não comutativa: $r - s ≠ s - r$
```


```ad-quote
title:
**5. Produto Cartesiano (×)**
```


```ad-quote
title:

**Tipo**:
- Operador binário

**Função**:
- Combina cada tupla de r com cada tupla de s

**Definição Formal**:
1. $$r × s = \{ \langle v_1, ..., v_n, u_1, ..., u_m \rangle \mid \langle v_1, ..., v_n \rangle \in r \text{ e } \langle u_1, ..., u_m \rangle \in s \}$$

**Propriedades**:
  - Esquema resultante é concatenação dos esquemas
  - Operação fundamental para combinar relações
```


```ad-quote
title:
**6. Renomeação (ρ - Rho)**
```


```ad-quote
title:

**Tipo**:
- Operador unário

**Função**:
- Renomeia relações e/ou atributos

**Definição Formal**:
1. $$ρ_{s(B_1, B_2, ..., B_n)}(r)$$

**Propriedades**:
  - Essencial para evitar ambiguidades
  - Permite referenciar resultados de expressões
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Operadores Derivados e a Junção

```ad-quote
title:
<p align="justify">Embora os operadores fundamentais sejam suficientes para expressar qualquer consulta relacionalmente completa, operadores derivados são definidos para conveniência e expressividade.</p>
```

```ad-quote
title:
###### **Principais Operadores Derivados:**
```

```ad-quote
title:

|Operador&nbsp; | Definição&nbsp; | Casos Especiais&nbsp; |
| :--- | :--- | :--- |
|**Interseção (∩)**|r ∩ s = r - (r - s)|Derivado da diferença de conjuntos.|
|**Junção (⋈)**|r ⋈_θ s = σ_θ(r × s)|Combinação de produto cartesiano e seleção.|
|**Equijunção**|Caso especial de Theta-Junção onde θ contém apenas igualdades.|-|
|**Junção Natural**|Caso especial da equijunção onde a igualdade é testada em atributos de mesmo nome, eliminando duplicatas.|r ⋈ s|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Poder de Expressividade e Completude Relacional

```ad-quote
title:
<p align="justify">Uma linguagem de consulta é considerada relacionalmente completa se ela pode expressar qualquer consulta que possa ser expressa no Cálculo Relacional. A Álgebra Relacional (com seus seis operadores fundamentais) é relacionalmente completa. Isso estabelece um marco teórico para medir o poder de expressividade de outras linguagens. SQL, por exemplo, é mais do que relacionalmente completa, pois inclui funcionalidades que vão além da Álgebra Relacional pura.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Leis de Equivalência e a Base para Otimização

```ad-quote
title:
<p align="justify">O aspecto mais poderoso da Álgebra Relacional, do ponto de vista da ciência da computação, é a existência de um conjunto de regras de equivalência algébrica. Essas regras permitem que uma expressão seja transformada em outra logicamente equivalente, mas potencialmente muito mais eficiente em termos de execução.</p>
```

```ad-quote
title:
###### **Exemplos de Regras de Equivalência:**
```

```ad-quote
title:

|Regra&nbsp; | Equivalência&nbsp; |
| :--- | :--- |
|**Cascata de Seleções**|σ_P1(σ_P2(r)) ≡ σ_{P1 ∧ P2}(r)|
|**Comutatividade da Seleção**|σ_P1(σ_P2(r)) ≡ σ_P2(σ_P1(r))|
|**"Empurrar" a Seleção**|Se P envolve apenas atributos de r, σ_P(r ⋈ s) ≡ (σ_P(r)) ⋈ s|
|**Comutatividade da Junção**|r ⋈ s ≡ s ⋈ r|
|**Associatividade da Junção**|(r ⋈ s) ⋈ t ≡ r ⋈ (s ⋈ t)|

```

```ad-quote
title:
<p align="justify">O otimizador de consultas de um SGBD utiliza essas regras para reescrever o plano de execução de uma consulta, buscando a forma mais eficiente.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Limitações Teóricas da Álgebra Relacional Pura

```ad-quote
title:
<p align="justify">A Álgebra Relacional clássica, apesar de seu poder, possui limitações teóricas inerentes que a distinguem das linguagens comerciais modernas.</p>
```

```ad-quote
title:
###### **Principais Limitações:**
```

```ad-quote
title:

|Limitação&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|**Falta de Agregação**|Não há operadores para realizar cálculos sobre conjuntos de tuplas, como SUM, AVG, COUNT, MIN ou MAX.|
|**Incapacidade para Computação Aritmética**|Não é possível criar novos atributos cujos valores são derivados de cálculos aritméticos sobre outros atributos.|
|**Não Recursiva**|É impossível expressar consultas recursivas, como "encontrar todos os gerentes (diretos e indiretos) de um funcionário".|

```

```ad-quote
title:
<p align="justify">Para superar essas limitações, foi definida a Álgebra Relacional Estendida, que adiciona operadores para agregação, funções de cálculo e ordenação, aproximando-a mais das capacidades do SQL moderno.</p>
```
````

---