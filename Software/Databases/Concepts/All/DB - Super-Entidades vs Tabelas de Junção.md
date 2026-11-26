
---

````ad-quote
title:

##### **Intro )** - Tabelas de Junção vs. Superentidades: Uma Análise na Modelagem

```ad-quote
title:
<p align="justify">No universo da modelagem de bancos de dados relacionais, a busca por uma estrutura que seja flexível, eficiente e que preserve a integridade dos dados é constante. Duas abordagens que frequentemente surgem em discussões sobre design de esquemas são o uso de Tabelas de Junção e a implementação de Superentidades, também conhecidas como supertipos e subtipos. Embora ambas sejam ferramentas poderosas, elas resolvem problemas fundamentalmente diferentes. Este guia explora as duas abordagens, suas implicações na Terceira Forma Normal e apresenta alternativas que seguem os princípios da normalização.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Tabelas de Junção: A Ponte para Relacionamentos Muitos-para-Muitos

```ad-quote
title:
<p align="justify">As Tabelas de Junção, também chamadas de tabelas associativas ou de ligação, são a solução padrão e normalizada para representar relacionamentos de cardinalidade muitos-para-muitos (N:M) em um banco de dados relacional. Em sua essência, um relacionamento N:M ocorre quando uma instância de uma entidade pode estar associada a múltiplas instâncias de outra entidade, e vice-versa.</p>
```

```ad-quote
title:
###### **Cenário de Uso e Estrutura:**
```

```ad-quote
title:
<p align="justify">Considere um sistema de uma instituição de ensino onde um Aluno pode se matricular em vários Cursos, e um Curso pode ter vários Alunos. Para modelar essa relação, cria-se uma terceira tabela, a Tabela de Junção.</p>
```

```ad-quote
title:

|Tabela Alunos&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Aluno|INT|PRIMARY KEY|
|Nome|VARCHAR(100)||

|Tabela Cursos&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Curso|INT|PRIMARY KEY|
|Nome_Curso|VARCHAR(100)||

|Tabela Matriculas (Junção)&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Aluno|INT|PRIMARY KEY, FOREIGN KEY (ref. Alunos)|
|ID_Curso|INT|PRIMARY KEY, FOREIGN KEY (ref. Cursos)|
|Data_Matricula|DATE||
|Nota_Final|DECIMAL(4, 2)||

```

```ad-quote
title:

###### **Especificando 1:N**

```

```ad-quote
title:

Caso seja necessário utilizar as tabelas de junção com uma regra de negócio 1:N, é necessário especificar o tipo de dado como **UNIQUE constraint**

```

```ad-quote
title:
###### **Análise da Abordagem:**
```

```ad-quote
title:

|Aspecto&nbsp; | Vantagem&nbsp; | Desvantagem&nbsp; |
| :--- | :--- | :--- |
|**Normalização**|Aderência natural à 3FN|Aumento do número de tabelas|
|**Design**|Clareza e facilidade de manutenção|Consultas requerem múltiplos JOINs|
|**Flexibilidade**|Permite adicionar atributos à relação||

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Superentidades: Modelando a Herança e a Especialização

```ad-quote
title:
<p align="justify">A abordagem de Superentidades, ou modelo de supertipo/subtipo, é utilizada para representar relacionamentos de generalização/especialização, também conhecidos como herança, no nível do banco de dados. Nesse modelo, uma entidade genérica (a superentidade) possui atributos comuns a várias outras entidades mais específicas (as subentidades).</p>
```

```ad-quote
title:
###### **Implementações e Implicações na 3FN:**
```

```ad-quote
title:

|Estratégia&nbsp; | Descrição&nbsp; | Aderência à 3FN&nbsp; |
| :--- | :--- | :--- |
|**Tabela Única**|Uma tabela com todos os atributos e um discriminador|Pode violar a 3FN com muitos campos nulos|
|**Tabela por Classe**|Tabela para supertipo e tabelas separadas para subtipos|Melhor aderência à 3FN|
|**Tabela por Hierarquia**|Tabelas separadas para cada subtipo com atributos comuns|Pode levar à redundância de dados|

```

```ad-quote
title:
###### **Exemplo de Tabela por Classe (3FN):**
```

```ad-quote
title:

|Tabela Funcionarios (Supertipo)&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Funcionario|INT|PRIMARY KEY|
|Nome|VARCHAR(100)||
|Data_Admissao|DATE||

|Tabela Gerentes (Subtipo)&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Funcionario|INT|PRIMARY KEY, FOREIGN KEY|
|Bonus_Gerencial|DECIMAL(10, 2)||

|Tabela Engenheiros (Subtipo)&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Funcionario|INT|PRIMARY KEY, FOREIGN KEY|
|Especialidade_Engenharia|VARCHAR(50)||

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Alternativas que Seguem a 3FN: Uma Análise Comparativa

```ad-quote
title:
<p align="justify">A questão sobre alternativas que seguem a 3FN depende fundamentalmente do problema que se está tentando resolver, seja para relacionamentos muitos-para-muitos ou para generalização/especialização.</p>
```

```ad-quote
title:
###### **Comparativo de Abordagens 3FN:**
```

```ad-quote
title:

|Problema&nbsp; | Solução 3FN&nbsp; | Exemplo&nbsp; |
| :--- | :--- | :--- |
|**Relacionamento N:M**|Tabela de Junção|Tabela MATRICULAS para ALUNOS e CURSOS|
|**Generalização**|Tabela por Classe|Tabelas FUNCIONARIOS, GERENTES, ENGENHEIROS|

```

```ad-quote
title:
###### **Modelo Entidade-Atributo-Valor (EAV):**
```

```ad-quote
title:
<p align="justify">Embora tecnicamente possa estar em 3FN, o modelo EAV é frequentemente criticado por sua complexidade de consultas, desafios na integridade dos dados e dificuldade de manutenção, não sendo recomendado para a maioria dos casos de uso.</p>
```

```ad-quote
title:

|Tabela Entidades&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Entidade|INT|PRIMARY KEY|
|Nome_Entidade|VARCHAR(100)||

|Tabela Atributos&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Atributo|INT|PRIMARY KEY|
|Nome_Atributo|VARCHAR(100)||

|Tabela Valores&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Entidade|INT|PRIMARY KEY, FOREIGN KEY|
|ID_Atributo|INT|PRIMARY KEY, FOREIGN KEY|
|Valor|VARCHAR(255)||

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )** - Ferramentas Diferentes para Problemas Diferentes

```ad-quote
title:
<p align="justify">Em resumo, Tabelas de Junção e Superentidades não são abordagens concorrentes, mas sim soluções para desafios distintos na modelagem de dados. Ambas possuem seu lugar no design de bancos de dados relacionais quando aplicadas aos problemas apropriados.</p>
```

```ad-quote
title:
###### **Resumo Comparativo:**
```

```ad-quote
title:

|Característica&nbsp; | Tabelas de Junção&nbsp; | Superentidades&nbsp; |
| :--- | :--- | :--- |
|**Propósito Principal**|Relacionamentos muitos-para-muitos (N:M)|Generalização/especialização (herança)|
|**Aderência à 3FN**|Naturalmente em 3FN|Depende da implementação|
|**Melhor Abordagem 3FN**|A própria Tabela de Junção|Implementação Tabela por Classe|

```

```ad-quote
title:
<p align="justify">Ao projetar um banco de dados, a escolha entre essas abordagens deve ser guiada pela natureza dos dados e dos relacionamentos. Priorizar a normalização, especialmente a Terceira Forma Normal, resulta em um esquema mais robusto, com menos redundância e maior integridade dos dados, facilitando a manutenção e a evolução do sistema.</p>
```
````

---
