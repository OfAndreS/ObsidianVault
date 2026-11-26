
---

````ad-quote
title:

##### **Intro )** - A Mecânica do Raciocínio Dedutivo

```ad-quote
title:
<p align="justify">Se a análise de argumentos válidos nos ensina a identificar um raciocínio correto, as Regras de Dedução e Inferência nos ensinam a construí-lo. Elas são o motor do pensamento lógico, um conjunto de ferramentas que nos permite avançar de um conjunto de verdades conhecidas (as premissas) para uma nova verdade (a conclusão) através de uma série de passos irrefutáveis. Uma Ex: dedução formal é um processo passo a passo, uma prova, onde cada novo elo na corrente do raciocínio é forjado por uma regra que garante a preservação da verdade, assegurando que, se partimos de premissas verdadeiras, a conclusão alcançada será, inquestionavelmente, verdadeira.</p>
```
````

>[!quote] **Questões:** [Validade dos argumentos](https://gemini.google.com/app/147fc45f1b28e4a3?hl=pt-BR)

>[!quote] **Questões:** [Regras de Inferência](https://gemini.google.com/app/d430d698d9e56dba?hl=pt-BR)

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Estrutura de uma Dedução Formal

```ad-quote
title:
<p align="justify">Uma dedução (ou prova) formal é uma sequência numerada de Fórmulas Bem-Formuladas (fbfs) em que cada linha deve ser justificada. Uma linha pode ser justificada de duas maneiras: ou é uma Ex: premissa (uma das suposições iniciais do argumento), ou é o resultado da aplicação de uma Ex: regra de dedução a linhas anteriores na prova. Distinguimos dois tipos de regras que compõem nossa "caixa de ferramentas" lógica.</p>
```

```ad-quote
title:

|Tipo de Regra&nbsp;    | Descrição&nbsp;   | Analogia&nbsp;    |
| --- | --- | --- |
|**Regras de Inferência**|São "ruas de mão única". A partir de certas premissas, elas nos permitem inferir uma conclusão, mas não o contrário. Elas sempre geram uma nova linha na dedução.|Um carpinteiro usando madeira (premissas) para construir uma cadeira (conclusão). A cadeira é um novo objeto.|
|**Regras de Equivalência**|São "ruas de mão dupla". Baseadas em equivalências tautológicas, elas nos permitem substituir uma fórmula (ou parte dela) por sua equivalente, em qualquer linha. A troca é válida nos dois sentidos.|Um tradutor trocando uma frase em português por sua equivalente em inglês. A ideia fundamental é a mesma.|

```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - As Principais Regras de Inferência

```ad-quote
title:
<p align="justify">Estas são as regras fundamentais para derivar novas informações a partir das existentes.</p>
```

```ad-quote
title:

|Nome (Abreviação)&nbsp;    | Formato Lógico&nbsp;   | Descrição&nbsp;    |
|---|---|---|
|**Modus Ponens (MP)**|De `p → q` e `p`, infere-se `q`|Se você tem uma condicional e afirma o seu antecedente, pode afirmar o consequente.|
|**Modus Tollens (MT)**|De `p → q` e `~q`, infere-se `~p`|Se você tem uma condicional e nega o seu consequente, pode negar o antecedente.|
|**Silogismo Hipotético (SH)**|De `p → q` e `q → r`, infere-se `p → r`|Permite encadear condicionais para criar uma nova condicional transitiva.|
|**Silogismo Disjuntivo (SD)**|De `p ∨ q` e `~p`, infere-se `q`|Se você tem uma disjunção e nega uma de suas partes, pode afirmar a outra.|
|**Simplificação (Simp)**|De `p ∧ q`, infere-se `p` (ou `q`)|Se você tem uma conjunção verdadeira, cada uma de suas partes é verdadeira.|
|**Conjunção (Conj)**|De `p` e `q`, infere-se `p ∧ q` ou |Se você tem duas linhas verdadeiras, pode uni-las em uma conjunção.|
|**Conjunção (Conj) Negado**|De `p'` e `q'`, infere-se `p' ∧ q'` ou |Se você tem duas linhas falsas, pode uni-las em uma conjunção.|
|**Adição (Add)**|De `p`, infere-se `p ∨ q`|Se uma proposição é verdadeira, a disjunção dela com qualquer outra proposição também será.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Regras de Equivalência (ou Substituição) Comuns

```ad-quote
title:
<p align="justify">Estas regras permitem reescrever fórmulas em formas logicamente idênticas, o que é crucial para revelar estruturas que permitem a aplicação das regras de inferência.</p>
```

```ad-quote
title:

|Nome (Abreviação)&nbsp;    | Equivalência Lógica&nbsp;   |
|---|---|
|**Leis de De Morgan (DeM)**|~(p ∧ q) ⇔ (~p ∨ ~q)<br>~(p ∨ q) ⇔ (~p ∧ ~q)|
|**Dupla Negação (DN)**|p ⇔ ~~p|
|**Contraposição (Contra)**|(p → q) ⇔ (~q → ~p)|
|**Implicação Material (Impl)**|(p → q) ⇔ (~p ∨ q)<br>(p → q) ⇔ ~(p ∧ ~q)|
|**Bicondicional Material (Bicond)**|(p ↔ q) ⇔ ((p → q) ∧ (q → p))<br>(p ↔ q) ⇔ ((p ∧ q) ∨ (~p ∧ ~q))|
|**Comutatividade (Com)**|(p ∧ q) ⇔ (q ∧ p)<br>(p ∨ q) ⇔ (q ∨ p)<br>(p ↔ q) ⇔ (q ↔ p)|
|**Associatividade (Assoc)**|(p ∧ (q ∧ r)) ⇔ ((p ∧ q) ∧ r)<br>(p ∨ (q ∨ r)) ⇔ ((p ∨ q) ∨ r)<br>(p ↔ (q ↔ r)) ⇔ ((p ↔ q) ↔ r)|
|**Distributividade (Dist)**|p ∧ (q ∨ r) ⇔ (p ∧ q) ∨ (p ∧ r)<br>p ∨ (q ∧ r) ⇔ (p ∨ q) ∧ (p ∨ r)<br>p ∧ (q → r) ⇔ (p ∧ q) → (p ∧ r)|
|**Leis de Identidade (Id)**|p ∧ T ⇔ p<br>p ∨ F ⇔ p|
|**Leis de Dominação (Dom)**|p ∨ T ⇔ T<br>p ∧ F ⇔ F|
|**Leis da Idempotência (Idem)**|p ∧ p ⇔ p<br>p ∨ p ⇔ p|
|**Leis da Absorção (Abs)**|p ∧ (p ∨ q) ⇔ p<br>p ∨ (p ∧ q) ⇔ p|
|**Lei do Terceiro Excluído (TercEx)**|p ∨ ~p ⇔ T|
|**Lei da Não-Contradição (NCont)**|p ∧ ~p ⇔ F|
|**Exportação (Exp)**|(p ∧ q) → r ⇔ p → (q → r)|
|**Tautologia (Taut)**|p ⇔ p ∧ p<br>p ⇔ p ∨ p|
|**Equivalência por Definição**|p → q ⇔ ~p ∨ q<br>p ↔ q ⇔ (p → q) ∧ (q → p)|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Exemplo de uma Dedução Formal Passo a Passo

```ad-quote
title:
<p align="justify">Vamos usar as regras para provar a validade do seguinte argumento:<br><b>Premissas:</b> (1) Se o projeto for aprovado (A), então o orçamento será liberado (B). (2) Se o orçamento for liberado (B), então a construção começará (C). (3) A construção não começará (~C).<br><b>Conclusão:</b> Logo, o projeto não foi aprovado (~A).</p>
```

```ad-quote
title:
**Prova Formal: A → B, B → C, ~C ∴ ~A**

|Passo&nbsp;    | Fórmula&nbsp;   | Justificativa (Regra e Linhas)&nbsp;    |
|---|---|---|
|**1**|A → B|Premissa|
|**2**|B → C|Premissa|
|**3**|~C|Premissa|
|**4**|A → C|Silogismo Hipotético (SH) nas linhas 1, 2|
|**5**|~A|Modus Tollens (MT) nas linhas 4, 3|

<p align="justify">A linha 5 deriva a conclusão desejada a partir das premissas, usando apenas regras de inferência válidas. Portanto, o argumento está provado como válido.</p>
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
<p align="justify">As Regras de Dedução e Inferência são o coração da lógica formal, transformando-a de um estudo estático de validade em um sistema dinâmico para a construção de conhecimento. Elas nos fornecem um método rigoroso para certificar que nossas conclusões são consequências lógicas de nossas premissas, formando a base para as provas matemáticas, o desenvolvimento de algoritmos em ciência da computação, a verificação de software e o raciocínio filosófico. Dominar essas regras é aprender a linguagem da própria razão, permitindo a construção de argumentos complexos com a confiança de que cada passo em direção à conclusão repousa sobre uma fundação logicamente sólida.</p>
```
````

---