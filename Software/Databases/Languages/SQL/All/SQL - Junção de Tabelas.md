---
banner: "![[Pasted image 20251008190141.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Combinando Dados de Múltiplas Tabelas

```ad-quote
title:
<p align="justify">Bancos de dados relacionais são projetados para evitar a repetição de dados, dividindo as informações em tabelas lógicas e interligadas (um processo chamado de normalização). A operação JOIN é a ferramenta fundamental do SQL para recombinar essas tabelas no momento da consulta. Ela permite cruzar informações de duas ou more tabelas com base em uma coluna de relacionamento em comum, possibilitando a extração de insights completos e complexos que não seriam possíveis analisando as tabelas isoladamente.</p>
```

>[!quote] **Doc:** [W3Schools SQL Joins](https://www.w3schools.com/sql/sql_join.asp)

```ad-quote
title:
<p align="justify"><b>Tabelas de Exemplo</b></p>
```

```ad-quote
title:
<p align="justify"><b>Tabela 1: `Clientes`</b></p>

| ID_Cliente | Nome | Cidade |
| :---: | :--- | :--- |
| 1 | João Silva | São Paulo |
| 2 | Maria Garcia | Rio de Janeiro |
| 3 | Carlos Souza | Belo Horizonte |
| 4 | Ana Pereira | Salvador |

<br>
<p align="justify"><b>Tabela 2: `Pedidos`</b></p>

| ID_Pedido | ID_Cliente | Produto | Valor |
| :---: | :---: | :--- | :--- |
| 101 | 1 | Notebook | 3500.00 |
| 102 | 2 | Mouse | 80.00 |
| 103 | 1 | Teclado | 120.00 |
| 104 | 3 | Monitor | 950.00 |

<p align="justify">Note que o cliente 'Ana Pereira' (ID 4) não possui nenhum pedido associado.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Condição de Junção: A Cláusula `ON`

```ad-quote
title:
**Características Principais:**
```

```ad-quote
title:
<p align="justify">A cláusula ON é a regra que define como as tabelas se conectam. Ela especifica a condição de correspondência entre as colunas, que geralmente é a chave primária de uma tabela e a chave estrangeira da outra. A junção ocorre para cada linha onde a condição especificada em ON é verdadeira.</p>
```

```ad-quote
title:
<p align="justify"><b>Sintaxe Fundamental</b></p>
```

```sql
SELECT
    TabelaA.Coluna1, TabelaB.Coluna2
FROM
    TabelaA
JOIN
    TabelaB ON TabelaA.ChaveComum = TabelaB.ChaveComum;
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - `INNER JOIN`: A Interseção dos Dados

```ad-quote
title:
O INNER JOIN (ou simplesmente JOIN) é o tipo de junção mais comum. Ele retorna apenas os registros que possuem valores correspondentes em AMBAS as tabelas. Se um cliente não tiver pedidos, ele não aparecerá no resultado.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Exemplo Prático**
```

```ad-quote
title:
<p align="justify">Pergunta: Listar apenas os clientes que fizeram pedidos, mostrando o nome do cliente e o produto comprado.</p>
```

```sql
SELECT
    Clientes.Nome,
    Pedidos.Produto
FROM
    Clientes
INNER JOIN
    Pedidos ON Clientes.ID_Cliente = Pedidos.ID_Cliente;
```

```ad-quote
title:
**Resultado Esperado:**
```

```ad-quote
title:

| Nome | Produto |
| :--- | :--- |
| João Silva | Notebook |
| Maria Garcia | Mouse |
| João Silva | Teclado |
| Carlos Souza | Monitor |

<p align="justify">Observe que 'Ana Pereira' não está presente, pois ela não possui correspondência na tabela de Pedidos.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - `LEFT JOIN`: Priorizando a Tabela da Esquerda

```ad-quote
title:
O LEFT JOIN (ou LEFT OUTER JOIN) retorna TODOS os registros da tabela da esquerda (a primeira a ser mencionada) e os registros correspondentes da tabela da direita. Se não houver correspondência para um registro da esquerda, as colunas da direita conterão valores NULL.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Exemplo Prático**
```

```ad-quote
title:
<p align="justify"><b>Pergunta:</b> Listar TODOS os clientes e os pedidos que eles fizeram. Se um cliente não fez um pedido, ele ainda deve aparecer.</p>
```

```sql
SELECT
    Clientes.Nome,
    Pedidos.Produto
FROM
    Clientes
LEFT JOIN
    Pedidos ON Clientes.ID_Cliente = Pedidos.ID_Cliente;
```

```ad-quote
title:
**Resultado Esperado:**
```

```ad-quote
title:

| Nome | Produto |
| :--- | :--- |
| João Silva | Notebook |
| João Silva | Teclado |
| Maria Garcia | Mouse |
| Carlos Souza | Monitor |
| Ana Pereira | NULL |

<p align="justify">'Ana Pereira' agora aparece, com o valor NULL na coluna 'Produto', indicando que não há pedido correspondente.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Caso de Uso: Encontrando Registros "Órfãos"**
```

```ad-quote
title:
<p align="justify">Uma aplicação poderosa do LEFT JOIN é encontrar registros em uma tabela que não têm correspondência em outra, usando um filtro WHERE para buscar os valores NULL.</p>
<p align="justify"><b>Pergunta:</b> Quais clientes nunca fizeram um pedido?</p>
```

```sql
SELECT
    Clientes.Nome
FROM
    Clientes
LEFT JOIN
    Pedidos ON Clientes.ID_Cliente = Pedidos.ID_Cliente
WHERE
    Pedidos.ID_Pedido IS NULL;
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - `RIGHT JOIN`: Priorizando a Tabela da Direita

```ad-quote
title:
O RIGHT JOIN (ou RIGHT OUTER JOIN) é o oposto do LEFT JOIN. Ele retorna TODOS os registros da tabela da direita e os registros correspondentes da tabela da esquerda. Se não houver correspondência, as colunas da esquerda conterão NULL.
<br>
<p align="justify"><b>Nota:</b> É menos comum, pois qualquer RIGHT JOIN pode ser reescrito como um LEFT JOIN trocando a ordem das tabelas, o que geralmente é mais intuitivo de ler.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Exemplo Prático**
```

```ad-quote
title:
<p align="justify"><b>Pergunta:</b> Listar todos os pedidos e, se houver, as informações do cliente que o fez.</p>
```

```sql
SELECT
    Clientes.Nome,
    Pedidos.Produto
FROM
    Clientes
RIGHT JOIN
    Pedidos ON Clientes.ID_Cliente = Pedidos.ID_Cliente;
```

```ad-quote
title:
**Resultado Esperado:**
```

```ad-quote
title:

| Nome | Produto |
| :--- | :--- |
| João Silva | Notebook |
| Maria Garcia | Mouse |
| João Silva | Teclado |
| Carlos Souza | Monitor |

<p align="justify">Neste caso, o resultado é idêntico ao INNER JOIN porque todos os pedidos em nossa tabela de exemplo têm um cliente correspondente.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - `FULL OUTER JOIN`: A União Completa

```ad-quote
title:
O FULL OUTER JOIN retorna todos os registros quando há uma correspondência em uma das tabelas (esquerda ou direita). Essencialmente, ele combina os resultados de um LEFT JOIN e um RIGHT JOIN. Se não houver correspondência, as colunas da tabela oposta terão NULL.
<br>
<p align="justify"><b>Nota:</b> Alguns SGBDs (como o MySQL) não suportam `FULL OUTER JOIN` diretamente. Nesses casos, o resultado pode ser simulado com uma `UNION` de um `LEFT JOIN` e um `RIGHT JOIN`.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Exemplo Prático**
```

```ad-quote
title:
<p align="justify"><b>Pergunta:</b> Listar todas as associações possíveis entre clientes e pedidos, incluindo clientes sem pedidos.</p>
```

```sql
SELECT
    Clientes.Nome,
    Pedidos.Produto
FROM
    Clientes
FULL OUTER JOIN
    Pedidos ON Clientes.ID_Cliente = Pedidos.ID_Cliente;
```

```ad-quote
title:
**Resultado Esperado:**
```

```ad-quote
title:

| Nome | Produto |
| :--- | :--- |
| João Silva | Notebook |
| João Silva | Teclado |
| Maria Garcia | Mouse |
| Carlos Souza | Monitor |
| Ana Pereira | NULL |

<p align="justify">O resultado inclui tanto os registros correspondentes quanto os registros não correspondentes de ambas as tabelas (neste caso, apenas da tabela Clientes).</p>
```
````

---
