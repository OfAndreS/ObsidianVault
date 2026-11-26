---
banner: "![[Pasted image 20251008190141.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Análise Detalhada da Estrutura da Consulta

```ad-quote
title:
<p align="justify">Vamos aprofundar em cada uma das cláusulas (SELECT, FROM, WHERE, ORDER BY), detalhando os operadores, as nuances de sintaxe e a lógica de processamento pelo sistema de banco de dados. Usaremos uma tabela fictícia Colaboradores como base para todos os exemplos.</p>
```

>[!quote] **Doc:** [W3Schools SQL Tutorial](https://www.w3schools.com/sql/)

```ad-quote
title:
<p align="justify"><b>Tabela de Exemplo: `Colaboradores`</b></p>
```

```ad-quote
title:

| ID_Colaborador | Nome_Completo | Departamento | Cargo | Salario | Data_Contratacao |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 101 | Ana Beatriz Lima | TI | Desenvolvedor Jr | 4800.00 | 2023-02-15 |
| 102 | Carlos Eduardo Rocha | Vendas | Gerente de Contas | 7500.00 | 2021-08-20 |
| 103 | Bruna Almeida | TI | Desenvolvedor Sr | 9200.00 | 2020-05-12 |
| 104 | Daniel Farias | Marketing | Analista de Mídias | 5100.00 | 2022-11-01 |
| 105 | Eduardo Costa | Vendas | Vendedor Interno | 4200.00 | 2023-07-30 |
| 106 | Fernanda Gonçalves | RH | Recrutador | 5500.00 | 2021-03-10 |
| 107 | Gabriel Pereira | TI | Arquiteto de Software | 14000.00 | 2018-01-25 |
| 108 | Helena Martins | Marketing | Coordenador | 8000.00 | 2019-10-09 |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Ordem de Execução Lógica

```ad-quote
title:
**Características Principais:**
```

```ad-quote
title:
<p align="justify">A ordem em que escrevemos uma consulta SQL não reflete a ordem em que o banco de dados a "pensa". Entender a ordem de execução lógica é o segredo para escrever consultas complexas e eficientes.</p>
```

```ad-quote
title:

| Passo Lógico | Cláusula | Explicação |
| :---: | --- | --- |
| 1 | `FROM` | Identifica e carrega as tabelas, definindo o universo de dados. |
| 2 | `WHERE` | Filtra as linhas com base em condições, descartando o que não é relevante. |
| 3 | `SELECT` | Projeta (seleciona) as colunas e executa expressões sobre os dados filtrados. |
| 4 | `ORDER BY` | Ordena o conjunto de resultados final para a exibição. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - A Cláusula `FROM`: O Ponto de Partida

```ad-quote
title:
<p align="justify"><b>Definindo o Universo de Dados</b></p>
```

```ad-quote
title:
<p align="justify">A cláusula FROM é a fundação da consulta. Sua missão é especificar a(s) fonte(s) de dados. O SGBD lê esta cláusula primeiro para saber com qual conjunto de dados brutos ele irá trabalhar.</p>
```

```sql
-- Sintaxe Básica
FROM Colaboradores
```

```ad-quote
title:
<p align="justify"><b>Aliases de Tabela - Apelidos</b></p>
```

```ad-quote
title:
<p align="justify">Em consultas complexas, é uma prática recomendada dar um "apelido" (alias) para a tabela. Isso torna a consulta mais curta e legível.</p>
```

```sql
-- 'AS' é opcional na maioria dos SGBDs
FROM Colaboradores AS c

-- ou simplesmente
FROM Colaboradores c
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - A Cláusula `WHERE`: Filtragem de Dados

```ad-quote
title:
A cláusula WHERE aplica um filtro rigoroso sobre os dados definidos pelo FROM. Ela avalia cada linha contra uma condição e apenas as linhas onde a condição é verdadeira são mantidas.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Operadores de Comparação**
```

```ad-quote
title:
Comparam valores em colunas com um valor específico.
```

```ad-quote
title:

| Operador | Descrição | Exemplo |
| :---: | --- | --- |
| `=` | Igual a | `WHERE Departamento = 'TI'` |
| `!=` ou `<>` | Diferente de | `WHERE Departamento != 'Vendas'` |
| `>` | Maior que | `WHERE Salario > 8000` |
| `<` | Menor que | `WHERE Salario < 5000` |
| `>=` , `<=` | Maior/Menor ou igual a | `WHERE Salario >= 7500` |

```
````

````ad-quote
title:
```ad-quote
title:
###### **Operadores Lógicos - `AND`, `OR`, `NOT`**
```

```ad-quote
title:
Usados para combinar múltiplas condições de filtragem.
```

```sql
-- AND: Ambas as condições devem ser verdadeiras.
WHERE Departamento = 'TI' AND Cargo = 'Desenvolvedor Sr'

-- OR: Pelo menos uma das condições deve ser verdadeira.
WHERE Departamento = 'RH' OR Salario > 10000

-- NOT: Inverte o resultado de uma condição.
WHERE NOT Departamento = 'TI'
```
````

````ad-quote
title:
```ad-quote
title:
###### **Operadores Especiais**
```

```ad-quote
title:
Oferecem formas mais expressivas de filtrar dados.
```

```sql
-- BETWEEN: Verifica se um valor está dentro de um intervalo (inclusivo).
WHERE Salario BETWEEN 5000 AND 7500

-- IN: Verifica se um valor corresponde a qualquer valor em uma lista.
WHERE Departamento IN ('Vendas', 'Marketing')

-- LIKE: Busca por padrões em texto (% para múltiplos caracteres, _ para um).
WHERE Nome_Completo LIKE 'Eduardo%'

-- IS NULL: Verifica se uma coluna possui valor nulo (vazio).
WHERE Data_Demissao IS NULL
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - A Cláusula `SELECT`: Projeção de Dados

```ad-quote
title:
Após a filtragem, a cláusula SELECT especifica quais colunas do resultado serão exibidas e permite a aplicação de transformações, como cálculos e apelidos.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Seleção de Colunas**
```

```ad-quote
title:
Você pode selecionar todas as colunas com `*` ou listar colunas específicas para melhor performance e clareza.
```

```sql
-- Selecionando todas as colunas
SELECT * FROM Colaboradores;

-- Selecionando colunas específicas
SELECT Nome_Completo, Salario FROM Colaboradores;
```
````

````ad-quote
title:
```ad-quote
title:
###### **Transformação de Dados - Aliases e Expressões**
```

```ad-quote
title:
Permite renomear colunas no resultado final com `AS` e realizar operações diretamente na consulta.
```

```sql
SELECT
    Nome_Completo AS "Nome do Colaborador",
    Salario,
    Salario * 12 AS Salario_Anual
FROM Colaboradores;
```
````

````ad-quote
title:
```ad-quote
title:
###### **Remoção de Duplicatas - `DISTINCT`**
```

```ad-quote
title:
Utilize `DISTINCT` para remover linhas completamente duplicadas do resultado final.
```

```sql
-- Retorna uma lista de departamentos únicos
SELECT DISTINCT Departamento FROM Colaboradores;
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - A Cláusula `ORDER BY`: Ordenação Final

```ad-quote
title:
Esta é a última etapa, responsável por organizar o conjunto de resultados final em uma ordem específica para exibição.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Direção da Ordenação - `ASC` e `DESC`**
```

```ad-quote
title:
`ASC` para ascendente (padrão) e `DESC` para descendente.
```

```sql
-- Ordenar pelo nome em ordem alfabética (ascendente)
ORDER BY Nome_Completo ASC;

-- Listar os maiores salários primeiro (descendente)
ORDER BY Salario DESC;
```
````

````ad-quote
title:
```ad-quote
title:
###### **Ordenação por Múltiplas Colunas**
```

```ad-quote
title:
O SGBD ordena pela primeira coluna e usa as colunas subsequentes como critério de desempate.
```

```sql
-- Agrupa por departamento (A-Z) e, dentro de cada um, ordena pelo maior salário
SELECT Nome_Completo, Departamento, Salario
FROM Colaboradores
ORDER BY Departamento ASC, Salario DESC;
```
````

````ad-quote
title:
```ad-quote
title:
###### **Ordenação por Alias**
```

```ad-quote
title:
É possível ordenar o resultado por uma coluna que foi criada ou renomeada com um alias no `SELECT`.
```

```sql
SELECT Nome_Completo, Salario * 12 AS Salario_Anual
FROM Colaboradores
ORDER BY Salario_Anual DESC;
```
````

---
