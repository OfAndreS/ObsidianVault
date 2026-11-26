
---

````ad-quote
title:

##### **Intro )** - O Alicerce do Raciocínio Estruturado

```ad-quote
title:
<p align="justify">A lógica proposicional, também conhecida como cálculo proposicional, é o ramo da lógica que estuda a validade de argumentos por meio da análise de proposições e das relações de verdade que se estabelecem entre elas. Trata-se de uma linguagem formal que busca eliminar as ambiguidades da linguagem natural, permitindo a construção e a avaliação de raciocínios de forma precisa e rigorosa. Seus elementos fundamentais são as proposições e a atribuição de um valor verdade a cada uma delas.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - O Que é uma Proposição?

```ad-quote
title:
<p align="justify">Uma proposição é uma sentença declarativa que pode ser classificada, sem ambiguidade, como Ex: verdadeira (V) ou Ex: falsa (F). É a expressão de um pensamento completo, que afirma ou nega um fato ou uma ideia.</p>
```

```ad-quote
title:

|Característica Essencial&nbsp;    | Detalhes    |
| --- | --- |
|**Ser uma oração declarativa:**|Excluem-se frases interrogativas ("Qual o seu nome?"), exclamativas ("Que belo dia!"), imperativas ("Feche a porta.") e sentenças abertas (que possuem variáveis, como "x + 2 = 5", cujo valor verdade depende do valor de x).|
|**Possuir um valor verdade:**|Pode ser inequivocamente definida como verdadeira ou falsa.|

```

```ad-quote
title:

|Exemplos de Proposições&nbsp;    | Valor Verdade&nbsp;    |
| --- | --- |
|**"O Brasil é um país da América do Sul."**|Proposição verdadeira|
|**"A Lua é feita de queijo."**|Proposição falsa|
|**"2 + 2 = 4"**|Proposição verdadeira|

```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - O Valor Verdade: O Pilar da Lógica Proposicional

```ad-quote
title:
<p align="justify">O conceito central da lógica proposicional é o valor verdade (ou valor lógico) de uma proposição. Como mencionado, uma proposição só pode assumir um de dois valores:</p>
```

```ad-quote
title:

|Valor&nbsp;    | Descrição    |
| --- | --- |
|**Verdadeiro (V):**|Quando a proposição corresponde à realidade dos fatos.|
|**Falso (F):**|Quando a proposição não corresponde à realidade dos fatos.|

```

```ad-quote
title:
<p align="justify">Esse sistema binário é a base sobre a qual toda a estrutura da lógica proposicional é construída.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Os Princípios Fundamentais da Lógica Proposicional

```ad-quote
title:
<p align="justify">A lógica clássica se sustenta em três princípios fundamentais, que garantem a consistência e a coerência do sistema:</p>
```

```ad-quote
title:

|Princípio&nbsp;    | Definição    |
| --- | --- |
|**Princípio da Identidade:**|O que é verdadeiro é verdadeiro, e o que é falso é falso. Uma proposição é igual a si mesma.|
|**Princípio da Não Contradição:**|Uma proposição não pode ser verdadeira e falsa ao mesmo tempo.|
|**Princípio do Terceiro Excluído:**|Uma proposição ou é verdadeira ou é falsa, não existindo uma terceira possibilidade.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Tipos de Proposições

```ad-quote
title:
<p align="justify">As proposições podem ser classificadas em duas categorias principais:</p>
```

```ad-quote
title:

|Tipo&nbsp;    | Descrição    |
| --- | --- |
|**Proposições Simples (ou Atômicas):**|São aquelas que expressam uma única ideia e não podem ser divididas em proposições menores. São geralmente representadas por letras minúsculas (p, q, r, etc.). Exemplo: Ex: p: O sol é uma estrela.|
|**Proposições Compostas (ou Moleculares):**|São formadas pela combinação de duas ou mais proposições simples, por meio de conectivos lógicos. Exemplo: O sol é uma estrela e a Terra é um planeta.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Conectivos Lógicos e a Tabela-Verdade

```ad-quote
title:
<p align="justify">Os conectivos lógicos são operadores que permitem a formação de proposições compostas a partir de proposições simples. O valor verdade de uma proposição composta depende dos valores verdade das proposições simples que a compõem e do conectivo utilizado. Para determinar esse valor, utiliza-se uma ferramenta chamada Ex: tabela-verdade.</p>
<p align="justify">A Ex: tabela-verdade é uma representação esquemática que exibe todas as combinações possíveis de valores verdade das proposições simples e o valor verdade resultante da proposição composta.</p>
```

```ad-quote
title:
**1. Negação (~)**
<p align="justify">A negação inverte o valor verdade de uma proposição. É lida como "não". Se Ex: p: "Está chovendo", então Ex: ~p: "Não está chovendo".</p>

| **p** | **~p** |
| :---: | :----: |
|   V   |   F    |
|   F   |   V    |

```

```ad-quote
title:
**2. Conjunção (∧)**
<p align="justify">A conjunção é verdadeira somente se ambas as proposições forem verdadeiras. É lida como "e". Se Ex: p: "João estudou" e Ex: q: "João foi aprovado", então Ex: p ∧ q: "João estudou e foi aprovado".</p>

| **p** | **q** | **p ∧ q** |
| :---: | :---: | :-------: |
|   V   |   V   |     V     |
|   V   |   F   |     F     |
|   F   |   V   |     F     |
|   F   |   F   |     F     |

```

```ad-quote
title:
**3. Disjunção Inclusiva (∨)**
<p align="justify">A disjunção inclusiva é falsa somente se ambas as proposições forem falsas. É lida como "ou". Se Ex: p: "Maria gosta de sorvete" e Ex: q: "Maria gosta de açaí", então Ex: p ∨ q: "Maria gosta de sorvete ou de açaí".</p>

| **p** | **q** | **p ∨ q** |
| :---: | :---: | :-------: |
|   V   |   V   |     V     |
|   V   |   F   |     V     |
|   F   |   V   |     V     |
|   F   |   F   |     F     |

```

```ad-quote
title:
**4. Condicional (→)**
<p align="justify">A condicional é falsa somente quando a primeira proposição (antecedente) é verdadeira e a segunda (consequente) é falsa. É lida como "se... então...". Se Ex: p: "Se chover" e Ex: q: "levarei o guarda-chuva", então Ex: p → q: "Se chover, então levarei o guarda-chuva".</p>

| **p** | **q** | **p → q** |
| :---: | :---: | :-------: |
|   V   |   V   |     V     |
|   V   |   F   |     F     |
|   F   |   V   |     V     |
|   F   |   F   |     V     |

```

```ad-quote
title:
**5. Bicondicional (↔)**
<p align="justify">A bicondicional é verdadeira somente quando ambas as proposições têm o mesmo valor verdade (ambas verdadeiras ou ambas falsas). É lida como "se e somente se". Se Ex: p: "Um triângulo é equilátero" e Ex: q: "ele possui três lados iguais", então Ex: p ↔ q: "Um triângulo é equilátero se e somente se possui três lados iguais".</p>

| **p** | **q** | **p ↔ q** |
| :---: | :---: | :-------: |
|   V   |   V   |     V     |
|   V   |   F   |     F     |
|   F   |   V   |     F     |
|   F   |   F   |     V     |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">Em suma, a lógica proposicional fornece as ferramentas essenciais para a análise e a construção de argumentos válidos. Ao compreender os conceitos de proposição, valor verdade e os operadores lógicos, é possível decifrar a estrutura lógica do pensamento e do discurso, habilidade fundamental em diversas áreas do conhecimento, da matemática e ciência da computação à filosofia e ao direito.</p>
```
````

---