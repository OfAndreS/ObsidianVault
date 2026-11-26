
---

````ad-quote
title:

##### **Intro )** - A Gramática do Raciocínio Lógico

```ad-quote
title:
<p align="justify">Assim como uma língua natural possui regras gramaticais para formar sentenças coerentes, a lógica proposicional possui uma sintaxe rigorosa para construir expressões válidas. As Fórmulas Bem-Formuladas, ou Ex: fbf, são o resultado da aplicação dessa sintaxe. Elas definem o universo de todas as expressões que podem ser logicamente avaliadas, garantindo que cada fórmula tenha uma estrutura clara, sem ambiguidades, e passível de ter seu valor verdade determinado através de ferramentas como a tabela-verdade.</p>
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Definição Recursiva de uma FBF

```ad-quote
title:
<p align="justify">Uma expressão é classificada como uma fbf se, e somente se, sua construção puder ser justificada por um conjunto finito de aplicações das seguintes regras formais:</p>
```

```ad-quote
title:

|Passo&nbsp;    | Descrição Formal&nbsp;    |
| --- | --- |
|**Passo 1 (Base):**|Qualquer variável proposicional (Ex: p, q, r, ...) é uma fbf.|
|**Passo 2 (Indução):**|Se Ex: α e Ex: β são fbfs, então as seguintes expressões também são fbfs:<br> 1. (~α)<br> 2. (α ∧ β)<br> 3. (α ∨ β)<br> 4. (α → β)<br> 5. (α ↔ β)|
|**Passo 3 (Fechamento):**|Uma expressão só é uma fbf se puder ser formada pela aplicação dos Passos 1 e 2.|

```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Notação dos Conectivos Lógicos

```ad-quote
title:
<p align="justify">A clareza na notação dos conectivos é fundamental. Embora existam símbolos primários amplamente aceitos, algumas notações alternativas são encontradas em diferentes contextos, como na programação ou em textos filosóficos.</p>
```

```ad-quote
title:

|Operação Lógica&nbsp;    | Notação Primária&nbsp;   | Notações Alternativas&nbsp;   |
| --- | --- | --- |
|**Negação**|~|¬, !|
|**Conjunção**|∧|&, &&, .|
|**Disjunção**|∨|\|, \|\|, +|
|**Condicional**|→|⇒, ⊃|
|**Bicondicional**|↔|⇔, ≡|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Análise de Fórmulas

```ad-quote
title:
<p align="justify">A melhor maneira de entender as regras é analisar a construção (ou a falha na construção) de algumas fórmulas.</p>
```

```ad-quote
title:

|Fórmula&nbsp;    | Análise da Construção&nbsp;    | Veredito&nbsp;   |
| --- | --- | --- |
|**(~(p → q))**|1. Ex: p e Ex: q são fbfs (Passo 1).<br>2. Portanto, (p → q) é uma fbf (Passo 2.4).<br>3. Consequentemente, (~(p → q)) é uma fbf (Passo 2.1).|É uma FBF|
|**(p ∧ (q ∨ r))**|1. Ex: p, Ex: q, e Ex: r são fbfs (Passo 1).<br>2. Portanto, (q ∨ r) é uma fbf (Passo 2.3).<br>3. Como Ex: p e (q ∨ r) são fbfs, (p ∧ (q ∨ r)) é uma fbf (Passo 2.2).|É uma FBF|
|**p ∧ q → r**|Esta expressão é ambígua. Não está claro se ela representa ((p ∧ q) → r) ou (p ∧ (q → r)). A falta de parênteses viola a aplicação estrita da Regra 2.|Não é uma FBF|
|**(p ∨ q ~)**|O conectivo '~' é unário (aplica-se a uma fbf), mas foi posicionado como um operador binário sem uma segunda fbf à direita. Viola as regras de formação.|Não é uma FBF|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Convenções de Notação e Precedência

```ad-quote
title:
<p align="justify">Para melhorar a legibilidade e reduzir o número de parênteses, os lógicos adotam convenções de notação. A mais importante é a ordem de precedência dos operadores, que define qual conectivo "amarra" mais fortemente as proposições ao seu redor.</p>
```

```ad-quote
title:

|Precedência&nbsp;    | Operador&nbsp;   | Exemplo de Leitura&nbsp;    |
| --- | --- | --- |
|**1**|~ (Negação)|A fórmula ~p ∧ q é lida como ((~p) ∧ q).|
|**2**|∧ (Conjunção), ∨ (Disjunção)|A fórmula p ∧ q → r é lida como ((p ∧ q) → r).|
|**3 **|→ (Condicional), ↔ (Bicondicional)|A fórmula p → q ↔ r é lida como ((p → q) ↔ r).|
|**Convenção Adicional:**|Os parênteses mais externos de uma fórmula completa podem ser omitidos. Assim, (p → q) pode ser escrito simplesmente como p → q.|

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
<p align="justify">O estudo das Fórmulas Bem-Formuladas e de suas notações é o estudo da anatomia da lógica. Ao dominar as regras de sintaxe, as convenções e a precedência dos operadores, garantimos que nossas expressões lógicas sejam bem definidas e universalmente compreensíveis. Esta estrutura sintática é o alicerce indispensável sobre o qual a análise semântica — a atribuição de significado e de valores de verdade — pode ser construída com segurança e precisão.</p>
```
````

---