---
banner: "![[Pasted image 20251020214009.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify">Ótima pergunta. Ter essa visão "macro" é fundamental para saber qual ferramenta usar em cada situação. Os operadores em SQL podem ser agrupados em várias categorias lógicas. Aqui está uma lista detalhada, dividida por suas funções.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Operadores Aritméticos

```ad-quote
title:
<p align="justify">Usados para realizar cálculos matemáticos, geralmente nas cláusulas <code>SELECT</code> ou <code>WHERE</code>.</p>
```

```ad-quote
title:

| Operador | Descrição |
| :--- | :--- |
| <code>+</code> | (Adição): Soma dois valores. |
| <code>-</code> | (Subtração): Subtrai um valor de outro. |
| <code>*</code> | (Multiplicação): Multiplica dois valores. |
| <code>/</code> | (Divisão): Divide um valor por outro. |
| <code>%</code> | (Módulo): Retorna o resto de uma divisão (útil para encontrar pares/ímpares). |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Operadores de Comparação

```ad-quote
title:
<p align="justify">Usados principalmente em cláusulas <code>WHERE</code> e <code>HAVING</code> para filtrar dados. Eles comparam dois valores e retornam <code>TRUE</code>, <code>FALSE</code> ou <code>UNKNOWN</code> (no caso de <code>NULL</code>s).</p>
```
```ad-quote
title:

| Operador | Descrição |
| :--- | :--- |
| <code>=</code> | (Igual a) |
| <code>!=</code> ou <code>&lt;&gt;</code> | (Diferente de) |
| <code>&gt;</code> | (Maior que) |
| <code>&lt;</code> | (Menor que) |
| <code>&gt;=</code> | (Maior ou igual a) |
| <code>&lt;=</code> | (Menor ou igual a) |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Operadores Lógicos

```ad-quote
title:
<p align="justify">Usados para combinar múltiplas condições booleanas (verdadeiro/falso) na cláusula <code>WHERE</code>.</p>
```
```ad-quote
title:

| Operador | Descrição |
| :--- | :--- |
| <code>AND</code> | Retorna <code>TRUE</code> se ambas as condições forem verdadeiras. |
| <code>OR</code> | Retorna <code>TRUE</code> se pelo menos uma das condições for verdadeira. |
| <code>NOT</code> | Inverte o valor de uma condição (de <code>TRUE</code> para <code>FALSE</code> ou vice-versa). |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Operadores de Conjunto / Set Operators

```ad-quote
title:
<p align="justify">Estes foram os que acabamos de discutir. Eles combinam os conjuntos de resultados de duas ou mais consultas <code>SELECT</code>.</p>
```
```ad-quote
title:

| Operador | Descrição |
| :--- | :--- |
| <code>UNION</code> | Combina os resultados e remove linhas duplicadas. |
| <code>UNION ALL</code> | Combina os resultados e mantém todas as linhas, incluindo duplicatas. |
| <code>INTERSECT</code> | Retorna apenas as linhas que existem em ambos os resultados. |
| <code>EXCEPT</code> | (ou <code>MINUS</code> em Oracle): Este é o operador de "subtração". Ele pega o resultado da Consulta 1 e remove as linhas que também estão na Consulta 2. |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Operadores de Filtragem Avançada / Predicados

```ad-quote
title:
<p align="justify">Estes também são usados no <code>WHERE</code>, mas lidam com condições mais complexas do que uma simples comparação.</p>
```
```ad-quote
title:

| Operador | Descrição |
| :--- | :--- |
| <code>IN</code> | Verifica se um valor está dentro de uma lista de valores (ex: <code>WHERE Cor IN ('Vermelho', 'Azul')</code>). |
| <code>BETWEEN</code> | Verifica se um valor está dentro de um intervalo (ex: <code>WHERE Preco BETWEEN 10 AND 20</code>). |
| <code>LIKE</code> | Usado para comparação de padrões em texto, usando curingas (<code>%</code>, <code>_</code>). |
| <code>IS NULL</code> / <code>IS NOT NULL</code> | Verifica se um valor é (ou não é) nulo. |
| <code>EXISTS</code> | Verifica se uma subconsulta retorna pelo menos uma linha. |
| <code>ANY</code> / <code>SOME</code> | Compara um valor com qualquer valor em uma lista ou subconsulta (ex: <code>WHERE Preco &gt; ANY (SELECT ...)</code>). |
| <code>ALL</code> | Compara um valor com todos os valores em uma lista ou subconsulta (ex: <code>WHERE Preco &gt; ALL (SELECT ...)</code>). |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Operadores de Alias e Atribuição

```ad-quote
title:

| Operador | Descrição |
| :--- | :--- |
| <code>AS</code> | Usado para dar um alias (apelido) temporário a uma coluna ou tabela (ex: <code>SELECT Nome AS Nome_Cliente ...</code>). |
| <code>=</code> | (Atribuição): No contexto de um <code>UPDATE ... SET</code>, atua como atribuição (ex: <code>UPDATE Produtos SET Preco = 50 ...</code>). |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Operadores Bitwise / Bit a Bit

```ad-quote
title:
<p align="justify">Estes são mais avançados e menos comuns, mas fundamentais em certas operações de baixo nível. Eles operam nos bits individuais dos números.</p>
```
```ad-quote
title:

| Operador | Descrição |
| :--- | :--- |
| <code>&</code> | (Bitwise AND) |
| <code>\|</code> | (Bitwise OR) |
| <code>^</code> | (Bitwise XOR - "ou exclusivo") |
| <code>~</code> | (Bitwise NOT - inversão) |

```
````

---

```ad-done
title:
#### **Fase 2 )** - Tipos de Instruções SQL
```

---

````ad-quote
title:

##### **01 )** - DML / Data Manipulation Language

```ad-quote
title:
<p align="justify"><b>Linguagem de Manipulação de Dados:</b> Este é o grupo que a maioria das pessoas associa à palavra "consulta". São os comandos usados para ler, inserir, modificar e apagar os dados dentro das tabelas.</p>
```
```ad-quote
title:

| Comando | Descrição |
| :--- | :--- |
| <code>SELECT</code> | Usado para ler e recuperar dados. É a consulta mais complexa e poderosa. |
| <code>INSERT</code> | Usado para adicionar novas linhas (registros) a uma tabela. |
| <code>UPDATE</code> | Usado para modificar dados em linhas que já existem. |
| <code>DELETE</code> | Usado para remover linhas de uma tabela. |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - DDL / Data Definition Language

```ad-quote
title:
<p align="justify"><b>Linguagem de Definição de Dados:</b> Este grupo não mexe com os dados em si, mas sim com a estrutura do banco de dados. São os comandos que criam, alteram ou destroem as "plantas" dos seus dados.</p>
```
```ad-quote
title:

| Comando | Descrição |
| :--- | :--- |
| <code>CREATE</code> | Cria um novo objeto no banco (ex: <code>CREATE TABLE</code>, <code>CREATE VIEW</code>). |
| <code>ALTER</code> | Modifica a estrutura de um objeto existente (ex: <code>ALTER TABLE ... ADD COLUMN ...</code>). |
| <code>DROP</code> | Remove um objeto inteiro do banco de dados (ex: <code>DROP TABLE nome_da_tabela</code>). |
| <code>TRUNCATE</code> | Remove todos os dados de uma tabela de forma muito rápida (diferente de <code>DELETE</code>). |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - DCL / Data Control Language

```ad-quote
title:
<p align="justify"><b>Linguagem de Controle de Dados:</b> Este grupo lida com a segurança e as permissões do banco de dados. São os comandos que o administrador usa para dizer quem pode fazer o quê.</p>
```
```ad-quote
title:

| Comando | Descrição |
| :--- | :--- |
| <code>GRANT</code> | Concede permissões a um usuário (ex: <code>GRANT SELECT ON Produtos TO ...</code>). |
| <code>REVOKE</code> | Remove permissões de um usuário. |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - TCL / Transaction Control Language

```ad-quote
title:
<p align="justify"><b>Linguagem de Controle de Transação:</b> Estes comandos gerenciam as "transações" — blocos de trabalho que devem ser executados como um todo ou não ser executados de forma alguma.</p>
```
```ad-quote
title:

| Comando | Descrição |
| :--- | :--- |
| <code>COMMIT</code> | Salva permanentemente todas as alterações feitas na transação atual. |
| <code>ROLLBACK</code> | Desfaz todas as alterações feitas desde o último <code>COMMIT</code>. |
| <code>SAVEPOINT</code> | Cria um ponto de "salvamento" intermediário dentro de uma transação. |

```
````

---

```ad-done
title:
#### **Fase 3 )** - Tipos Práticos de Consultas de Leitura / SELECT
```

---

````ad-quote
title:

##### **01 )** - Seleção/Projeção Simples

```ad-quote
title:
<p align="justify">O <code>SELECT</code> básico de uma única tabela.</p>
```
```ad-quote
title:

| Palavras-Chave Comuns |
| :--- |
| <code>SELECT</code> |
| <code>FROM</code> |
| <code>WHERE</code> |

```

```SQL
SELECT 
    Nome, 
    Preco 
FROM 
    Produtos 
WHERE 
    Preco > 50;
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Junções / Joins

```ad-quote
title:
<p align="justify">Combinam colunas de duas ou mais tabelas.</p>
```
```ad-quote
title:

| Palavras-Chave Comuns |
| :--- |
| <code>INNER JOIN</code> |
| <code>LEFT JOIN</code> |
| <code>ON</code> |

```

```SQL
SELECT 
    p.Nome, 
    c.NomeCategoria 
FROM 
    Produtos AS p
INNER JOIN 
    Categorias AS c ON p.ID_Categoria = c.ID_Categoria;
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Agregação / Aggregation

```ad-quote
title:
<p align="justify">Agrupa linhas para realizar cálculos sobre esses grupos.</p>
```
```ad-quote
title:

| Palavras-Chave/Funções Comuns |
| :--- |
| <code>GROUP BY</code> |
| <code>COUNT()</code> |
| <code>SUM()</code> |
| <code>AVG()</code> |
| <code>HAVING</code> |

```

```SQL
SELECT 
    ID_Categoria, 
    COUNT(*) AS Total_Produtos
FROM 
    Produtos
GROUP BY 
    ID_Categoria
HAVING 
    COUNT(*) > 10;
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Subconsultas / Subqueries

```ad-quote
title:
<p align="justify">Uma consulta <code>SELECT</code> dentro de outra.</p>
```
```ad-quote
title:

| Palavras-Chave Comuns |
| :--- |
| <code>IN</code> |
| <code>EXISTS</code> |
| <code>(SELECT ...)</code> |

```

```SQL
SELECT 
    Nome
FROM 
    Produtos
WHERE 
    Preco > (SELECT AVG(Preco) FROM Produtos);
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Conjunto / Set Queries

```ad-quote
title:
<p align="justify">Combinam os resultados de duas consultas.</p>
```
```ad-quote
title:

| Palavras-Chave Comuns |
| :--- |
| <code>UNION</code> |
| <code>INTERSECT</code> |
| <code>EXCEPT</code> |

```

```SQL
SELECT Email FROM Clientes_Atuais
UNION
SELECT Email FROM Clientes_Potenciais;
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - CTEs / Common Table Expressions

```ad-quote
title:
<p align="justify">Criam um bloco de consulta temporário e nomeado.</p>
```
```ad-quote
title:

| Palavras-Chave Comuns |
| :--- |
| <code>WITH ... AS (SELECT ...)</code> |

```

```SQL
WITH Vendas_Categoria AS (
    SELECT 
        ID_Categoria, 
        SUM(Valor) AS Total_Vendido
    FROM 
        Vendas
    GROUP BY 
        ID_Categoria
)
SELECT 
    c.NomeCategoria, 
    vc.Total_Vendido
FROM 
    Vendas_Categoria AS vc
JOIN 
    Categorias AS c ON vc.ID_Categoria = c.ID_Categoria;
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Funções de Janela / Window Functions

```ad-quote
title:
<p align="justify">Realiza cálculos em um "conjunto" de linhas sem usar <code>GROUP BY</code>.</p>
```
```ad-quote
title:

| Palavras-Chave Comuns |
| :--- |
| <code>OVER (PARTITION BY ...)</code> |
| <code>ROW_NUMBER()</code> |
| <code>RANK()</code> |
| <code>LEAD()</code> / <code>LAG()</code> |

```

```SQL
SELECT 
    Nome,
    Preco,
    ID_Categoria,
    RANK() OVER (PARTITION BY ID_Categoria ORDER BY Preco DESC) AS Ranking_Na_Categoria
FROM 
    Produtos;
```

````

---