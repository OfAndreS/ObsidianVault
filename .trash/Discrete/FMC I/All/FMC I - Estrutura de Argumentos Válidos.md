
---

````ad-quote
title:

##### **Intro )** - A Arquitetura do Raciocínio

```ad-quote
title:
<p align="justify">A lógica, em sua essência, é o estudo dos métodos e princípios usados para distinguir o raciocínio correto do incorreto. O objeto central dessa análise é o Ex: argumento. Em lógica, um argumento não é uma disputa verbal, mas sim um conjunto de proposições estruturadas de tal forma que uma delas, a Ex: Conclusão, pretende ser sustentada pelas outras, as Ex: Premissas. O objetivo fundamental é determinar se a ponte que liga as premissas à conclusão é estruturalmente sólida. Essa solidez estrutural é o que definimos como validade.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Definição Formal de Validade

```ad-quote
title:
<p align="justify">A validade de um argumento não depende da verdade ou falsidade real de suas premissas no mundo empírico, mas sim de sua forma lógica. Um argumento é considerado Ex: válido se, e somente se, for impossível que todas as suas premissas sejam verdadeiras e sua conclusão seja, ao mesmo tempo, falsa. A validade é uma garantia condicional: ela garante que, Ex: se as premissas forem verdadeiras, a conclusão necessariamente também o será. Portanto, a validade preserva a verdade.</p>
```

```ad-quote
title:

|Conceito&nbsp;    | Foco&nbsp;   | Pergunta Chave&nbsp;    |
| --- | --- | --- |
|**Verdade**|Conteúdo das Proposições|A afirmação corresponde à realidade? É um fato?|
|**Validade**|Estrutura do Argumento|A conclusão se segue logicamente das premissas? A forma é correta?|

```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Validade vs. Solidez (Tabela Corrigida)

```ad-quote
title:
<p align="justify">Esta é uma das distinções mais cruciais na lógica. Enquanto a validade trata apenas da estrutura, a solidez (ou correção) de um argumento exige mais. Um argumento é Ex: sólido (ou correto) se ele atende a duas condições simultaneamente: (1) ele é válido em sua forma e (2) todas as suas premissas são, de fato, verdadeiras.</p>
```

```ad-quote
title:

| Estrutura    | Premissas                | Resultado                                                                                       | Exemplo                                                                                                 |
| ------------ | ------------------------ | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Válido**   | **Todas Verdadeiras**    | **Argumento Sólido.** A conclusão é garantidamente verdadeira.                                  | Todo homem é mortal. Sócrates é homem. Logo, Sócrates é mortal.                                         |
| **Válido**   | **Pelo menos uma Falsa** | **Argumento Não-Sólido.** A conclusão pode ser V ou F por acaso.                                | Todos os mamíferos são pássaros (F). Baleias são mamíferos (V). Logo, baleias são pássaros (F).         |
| **Inválido** | **Todas Verdadeiras**    | **Argumento Não-Sólido.** A conclusão pode ser V ou F; a estrutura falha em garantir a verdade. | Todos os cães são mamíferos (V). Felix é um mamífero (V). Logo, Felix é um cão (F). (Pode ser um gato). |
| **Inválido** | **Pelo menos uma Falsa** | **Argumento Não-Sólido.** Nenhum tipo de garantia. A conclusão pode ser V ou F.                 | Todos os peixes são plantas (F). As rosas são peixes (F). Logo, as rosas são plantas (V).               |


```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Teste de Validade: O Método da Tautologia Condicional

```ad-quote
title:
<p align="justify">A maneira formal de testar a validade de um argumento é convertê-lo em uma única proposição condicional. A fórmula é criada unindo todas as premissas com o conectivo de conjunção (∧) para formar o antecedente, e usando a conclusão como o consequente. Se esta fórmula condicional resultante for uma Ex: tautologia, o argumento original é válido.</p>
```

```ad-quote
title:
**Análise do Argumento: *Modus Ponens***
<p align="justify">Premissa 1: Se o alarme toca (p), então eu acordo (q). (p → q)<br>Premissa 2: O alarme tocou (p). (p)<br>Conclusão: Logo, eu acordei (q). (q)<br><b>Fórmula a ser testada: ((p → q) ∧ p) → q</b></p>

| **p** | **q** | **p → q** | **(p → q) ∧ p** | **((p → q) ∧ p) → q** |
| :---: | :---: | :---------: | :---------------: | :--------------------------: |
|   V   |   V   |      V      |         V         |              **V** |
|   V   |   F   |      F      |         F         |              **V** |
|   F   |   V   |      V      |         F         |              **V** |
|   F   |   F   |      V      |         F         |              **V** |
<p align="justify">Como a coluna final é uma tautologia, o argumento *Modus Ponens* é formalmente válido.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Formas Argumentativas Válidas Comuns (Regras de Inferência)

```ad-quote
title:
<p align="justify">Certos padrões de argumentos válidos são tão comuns que recebem nomes específicos e são usados como "regras de inferência" para construir provas mais complexas.</p>
```

```ad-quote
title:

|Nome da Regra&nbsp;    | Estrutura Lógica&nbsp;   | Exemplo Cotidiano&nbsp;    |
| --- | --- | --- |
|***Modus Ponens***|(p → q), p ∴ q|Se chove, fico em casa. Choveu. Logo, fiquei em casa.|
|***Modus Tollens***|(p → q), ~q ∴ ~p|Se o portão está aberto, o cão foge. O cão não fugiu. Logo, o portão não estava aberto.|
|**Silogismo Hipotético**|(p → q), (q → r) ∴ (p → r)|Se eu estudar, passo na prova. Se eu passar na prova, ganho um presente. Logo, se eu estudar, ganho um presente.|
|**Silogismo Disjuntivo**|(p ∨ q), ~p ∴ q|O pedido chegará hoje ou amanhã. Ele não chegou hoje. Logo, chegará amanhã.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Estruturas Inválidas Comuns (Falácias Formais)

```ad-quote
title:
<p align="justify">É igualmente importante reconhecer estruturas de argumento que parecem convincentes, mas são logicamente inválidas. Estas são conhecidas como falácias formais.</p>
```

```ad-quote
title:

|Nome da Falácia&nbsp;    | Estrutura Lógica&nbsp;   | Exemplo de Erro&nbsp;    |
| --- | --- | --- |
|**Falácia da Afirmação do Consequente**|(p → q), q ∴ p|Se uma pessoa tem gripe, ela tem febre. Maria tem febre. Logo, Maria tem gripe. (Inválido, pois outras doenças causam febre).|
|**Falácia da Negação do Antecedente**|(p → q), ~p ∴ ~q|Se o animal é um cão, ele é um mamífero. O animal não é um cão. Logo, ele não é um mamífero. (Inválido, pois pode ser um gato).|

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
<p align="justify">A compreensão da estrutura de um argumento válido é o pilar do pensamento crítico e do raciocínio rigoroso. A validade lógica nos oferece uma ferramenta objetiva para avaliar se uma conclusão é uma consequência necessária de um conjunto de suposições, independentemente de nossas crenças ou opiniões sobre o conteúdo dessas suposições. Ao dominar a distinção entre validade, verdade e solidez, e ao reconhecer as formas de argumento válidas e falaciosas, nos equipamos para construir conhecimento de forma segura e para desconstruir raciocínios falhos em qualquer campo do saber humano.</p>
```
````

---