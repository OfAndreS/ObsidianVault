
---

````ad-quote
title:

##### **Intro )** - A Natureza do Valor-Verdade das Proposições

```ad-quote
title:
<p align="justify">Além de analisar a estrutura sintática das Fórmulas Bem-Formuladas (fbf), a lógica proposicional se aprofunda em sua natureza semântica, ou seja, no seu comportamento em relação aos valores-verdade. Ao construir uma tabela-verdade para uma proposição composta, revelamos um padrão em sua coluna de resultados. Esse padrão permite classificar qualquer fbf em três categorias exaustivas e mutuamente exclusivas: aquelas que são sempre verdadeiras (Ex: Tautologias), aquelas que são sempre falsas (Ex: Contradições), e aquelas cujo valor-verdade depende das proposições que as compõem (Ex: Contingências).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Tautologias: As Verdades Lógicas

```ad-quote
title:
<p align="justify">Uma Tautologia é uma proposição composta que é sempre verdadeira, independentemente dos valores-verdade de suas proposições atômicas constituintes. Em sua tabela-verdade, a coluna correspondente à proposição principal conterá apenas o valor 'V' (Verdadeiro). Tautologias representam verdades lógicas fundamentais e princípios de raciocínio que são válidos em todas as circunstâncias possíveis.</p>
```

```ad-quote
title:
**Exemplo Analisado: O Princípio do Terceiro Excluído (p ∨ ~p)**
<p align="justify">Esta fórmula afirma que para qualquer proposição Ex: p, ou ela é verdadeira, ou sua negação é verdadeira. Não há uma terceira opção.</p>

| **p** | **~p** | **p ∨ ~p** |
| :---: | :----: | :----------: |
|   V   |   F    |      **V** |
|   F   |   V    |      **V** |
<p align="justify">Como a coluna final (p ∨ ~p) contém apenas 'V', a fórmula é uma Tautologia.</p>
```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Contradições: As Falsidades Lógicas

```ad-quote
title:
<p align="justify">Uma Contradição é o oposto direto de uma tautologia. É uma proposição composta que é sempre falsa, independentemente dos valores-verdade de suas proposições atômicas. Em sua tabela-verdade, a coluna correspondente à proposição principal conterá apenas o valor 'F' (Falso). Contradições representam impossibilidades lógicas ou declarações que são inerentemente autocontraditórias.</p>
```

```ad-quote
title:
**Exemplo Analisado: O Princípio da Não Contradição ~(p ∧ ~p)**
<p align="justify">Esta fórmula, na sua forma mais básica (p ∧ ~p), afirma que uma proposição e sua negação não podem ser verdadeiras ao mesmo tempo. A expressão (p ∧ ~p) é a contradição fundamental.</p>

| **p** | **~p** | **p ∧ ~p** |
| :---: | :----: | :----------: |
|   V   |   F    |      **F** |
|   F   |   V    |      **F** |
<p align="justify">Como a coluna final (p ∧ ~p) contém apenas 'F', a fórmula é uma Contradição.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Contingências: As Proposições do Mundo Real

```ad-quote
title:
<p align="justify">Uma Contingência é uma proposição composta que pode ser tanto verdadeira quanto falsa, dependendo dos valores-verdade de suas proposições atômicas. Sua coluna de resultados na tabela-verdade conterá pelo menos um 'V' e pelo menos um 'F'. A grande maioria das proposições que usamos no dia a dia para descrever o mundo são contingências, pois sua veracidade depende dos fatos e do estado das coisas.</p>
```

```ad-quote
title:
**Exemplo Analisado: A Condicional Simples (p → q)**
<p align="justify">A afirmação "Se chover (p), então a rua ficará molhada (q)" não é uma verdade ou falsidade lógica absoluta; ela depende do que de fato acontece.</p>

| **p** | **q** | **p → q** |
| :---: | :---: | :----------: |
|   V   |   V   |      **V** |
|   V   |   F   |      **F** |
|   F   |   V   |      **V** |
|   F   |   F   |      **V** |
<p align="justify">Como a coluna final (p → q) contém tanto 'V' quanto 'F', a fórmula é uma Contingência.</p>
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
<p align="justify">A capacidade de classificar fórmulas em Tautologias, Contradições e Contingências é uma habilidade central na lógica. Essa classificação nos permite identificar a validade universal de argumentos, detectar inconsistências internas em um conjunto de crenças e compreender a natureza das declarações. As tautologias formam a espinha dorsal dos sistemas de prova e dedução, enquanto a identificação de contradições é crucial para garantir a coerência e a racionalidade do discurso. As contingências, por sua vez, representam o vasto campo das verdades empíricas que buscamos verificar sobre a realidade.</p>
```
````

---