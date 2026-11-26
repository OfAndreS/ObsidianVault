
---

````ad-quote
title:

##### **Intro )** - O Elo Crítico

```ad-quote
title:
<p align="justify">No processo de projetar um banco de dados relacional eficiente e confiável, dois conceitos são de vital importância: Dependências Funcionais e Anomalias. Entender a relação intrínseca entre eles é o que nos permite estruturar os dados de forma a garantir sua consistência e integridade. Essencialmente, as dependências funcionais, quando mal gerenciadas, são a causa raiz das anomalias que podem corromper um banco de dados.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - O Que São Dependências Funcionais?

```ad-quote
title:
<p align="justify">Uma dependência funcional é uma restrição entre dois ou mais atributos em uma tabela. Ela descreve uma relação onde o valor de um atributo (ou um conjunto de atributos), chamado de determinante, determina unicamente o valor de outro atributo, o dependente. A notação para uma dependência funcional é A → B, que se lê "A determina funcionalmente B" ou "B é funcionalmente dependente de A". Isso significa que para cada valor único de A, existe apenas um valor correspondente de B.</p>
```

```ad-quote
title:

|CPF&nbsp;    | Nome&nbsp;    | Salário&nbsp;    |
| --- | --- | --- |
|111.111.111-11|João Silva|5000|
|222.222.222-22|Maria Souza|6000|
|333.333.333-33|Pedro Costa|5000|

```

```ad-quote
title:
<p align="justify">Nesta tabela, podemos identificar as seguintes dependências funcionais: CPF → Nome e CPF → Salário. O CPF de um funcionário determina unicamente seu nome e seu salário. É importante notar que o contrário não é verdadeiro. O nome não determina o CPF (podemos ter homônimos) e o salário não determina o CPF (diferentes funcionários podem ter o mesmo salário).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - O Que São Anomalias?

```ad-quote
title:
<p align="justify">Anomalias são problemas ou inconsistências que ocorrem em um banco de dados mal projetado. Elas surgem, em geral, devido à redundância de dados e a dependências funcionais inadequadas dentro de uma mesma tabela. Essas inconsistências podem comprometer a integridade e a confiabilidade dos dados armazenados. Existem três tipos principais de anomalias.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Anomalia de Inserção

```ad-quote
title:
<p align="justify">Ocorre quando não é possível adicionar um novo registro à tabela porque falta o valor de um dos atributos que compõem a chave primária, ou quando para inserir uma informação sobre um objeto, é necessário inserir informações sobre outro objeto que não está relacionado diretamente.</p>
```

```ad-quote
title:

|ID_Projeto&nbsp;    | Nome_Projeto&nbsp;    | Descricao_Projeto;    | CPF_Func&nbsp; | Nome_Func&nbsp;  |
| --- | --- | --- | --- | --- |
|101|Sistema X| ... |111.111.111-11|João Silva|
|101|Sistema X| ... |222.222.222-22|Maria Souza|
|102|App Y| ... |333.333.333-33|Pedro Costa|

```

```ad-quote
title:
<p align="justify">Problema: Como inserir um novo projeto que ainda não tem funcionários alocados? Seria necessário inserir valores nulos para CPF_Func e Nome_Func, o que pode não ser permitido se fizerem parte da chave, ou criaria um registro incompleto e sem sentido.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Anomalia de Exclusão

```ad-quote
title:
<p align="justify">Acontece quando a remoção de um registro leva à perda de informações que não gostaríamos de perder. A exclusão de um conjunto de dados sobre um objeto acaba por eliminar, de forma indesejada, informações sobre outro. Por exemplo, usando a tabela anterior, se o funcionário "Pedro Costa" for o único alocado no "App Y" e ele for removido da tabela, todas as informações sobre o "App Y" (ID_Projeto = 102, Nome_Projeto = App Y e a Descricao_Projeto = ...) serão perdidas junto com o registro do funcionário.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Anomalia de Atualização (ou Modificação)

```ad-quote
title:
<p align="justify">Surge da redundância de dados. Se uma informação que aparece em múltiplos registros precisa ser atualizada, é necessário modificar todas as ocorrências. Se a atualização não for feita em todos os lugares, o banco de dados se tornará inconsistente. Por exemplo, na mesma tabela, se o nome do "Sistema X" mudar para "Sistema Z", seria necessário atualizar essa informação em duas linhas. Se o DBA (Administrador de Banco de Dados) esquecer de atualizar uma delas, a tabela ficará inconsistente, com o mesmo ID_Projeto apontando para dois nomes diferentes.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - A Relação Causal: Como Dependências Geram Anomalias

```ad-quote
title:
<p align="justify">A causa fundamental das anomalias é a existência de dependências funcionais indesejadas dentro de uma mesma tabela, especialmente as descritas abaixo.</p>
```

```ad-quote
title:

|Tipo de Dependência&nbsp;    | Descrição&nbsp;    |
| --- | --- |
|**Dependências Parciais:**|Ocorrem quando um atributo não-chave depende de apenas uma parte da chave primária composta. Isso leva à redundância e, consequentemente, a anomalias de atualização e inserção.|
|**Dependências Transitivas:**|Acontecem quando um atributo não-chave depende de outro atributo não-chave, que por sua vez depende da chave primária. Por exemplo, A → B e B → C. Isso também gera redundância e os três tipos de anomalias.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - A Solução: Normalização

```ad-quote
title:
<p align="justify">A solução para eliminar as anomalias é o processo de Normalização. A normalização é uma técnica de projeto de banco de dados que visa organizar os atributos em tabelas para reduzir a redundância e melhorar a integridade dos dados. Isso é feito decompondo tabelas grandes e problemáticas em tabelas menores e bem estruturadas, com base nas dependências funcionais.</p>
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
<p align="justify">Ao identificar e separar as dependências funcionais em tabelas distintas, a normalização garante que cada pedaço de informação seja armazenado em apenas um lugar, eliminando assim as anomalias e criando um banco de dados mais robusto, flexível e confiável.</p>
```
````

---