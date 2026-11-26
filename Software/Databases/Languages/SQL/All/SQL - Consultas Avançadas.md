---
banner: "![[Pasted image 20251020220325.png]]"
---

---

````ad-quote
title:

##### **Intro )** - SQL

```ad-quote
title:
<p align="justify">O objetivo desta seção é aprofundar nas técnicas de consulta SQL, focando em dois pilares centrais: primeiro, como aninhar consultas <code>SELECT</code> (conhecidas como SUBQUERIES) para criar filtros dinâmicos e complexos; segundo, como combinar os conjuntos de resultados de diferentes consultas usando OPERADORES DE CONJUNTO.</p>
```
```ad-quote
title:
<p align="justify">Uma SUBQUERY (ou subconsulta) é uma instrução <code>SELECT</code> completa que é colocada dentro de outra instrução SQL (como <code>SELECT</code>, <code>WHERE</code>, <code>FROM</code> ou <code>HAVING</code>). O banco de dados geralmente executa a subconsulta primeiro, e o resultado dela é usado pela consulta externa.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **00 )** - Tabelas de Exemplo

```ad-quote
title:
<p align="justify">Para todos os exemplos a seguir, usaremos o conjunto de tabelas genéricas abaixo.</p>
```

```ad-quote
title: 
###### Tabela - Categorias
```

```ad-quote
title:

| ID_Categoria | Nome |
| :--- | :--- |
| 10 | Eletrônicos |
| 20 | Informática |
| 30 | Livros |
```

```ad-quote
title:
**Tabela - Produtos**
```

```ad-quote
title:

| ID_Produto | Nome | Preco | ID_Categoria |
| :--- | :--- | :--- | :--- |
| 1 | Notebook | 3000 | 20 |
| 2 | Mouse | 100 | 20 |
| 3 | Smartphone | 1500 | 10 |
| 4 | SQL Básico | 50 | 30 |
| 5 | Fone de Ouvido | 350 | 10 |
```

```ad-quote
title: 
**Tabela - Clientes**
```

```ad-quote
title: 
| ID_Cliente | Nome_Cliente |
| :--- | :--- |
| 100 | Ana |
| 101 | Bruno |
| 102 | Carla |
| 103 | Davi |
```

```ad-quote
title: 
**Tabela - Pedidos**
```

```ad-quote
title: 

| ID_Pedido | ID_Cliente |
| :--- | :--- |
| 5000 | 100 |
| 5001 | 102 |
| 5002 | 100 |
```

```ad-quote
title: 
**Tabela - Clientes_Atuais**
```

```ad-quote
title: 
| Email |
| :--- |
| ana@email.com |
| bruno@email.com |
| carla@email.com |
```

```ad-quote
title: 
**Tabela - Clientes_Potenciais**
```

```ad-quote
title: 

| Email |
| :--- |
| bruno@email.com |
| davi@email.com |
| elisa@email.com |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Subconsulta Escalar

```ad-quote
title:
<p align="justify">Retorna exatamente UMA COLUNA e UMA LINHA. É tratada como um valor único e pode ser usada com operadores de comparação padrão.</p>
```
```ad-quote
title:

| Operadores Comuns |
| :--- |
| <code>=</code> |
| <code>&lt;&gt;</code> ou <code>!=</code> |
| <code>&gt;</code> |
| <code>&lt;</code> |

```

```SQL
-- Encontra produtos mais caros que a média de TODOS os produtos
SELECT 
    Nome,
    Preco
FROM 
    Produtos
WHERE 
    Preco > (SELECT AVG(Preco) FROM Produtos);
```

```ad-quote
title:
<p align="justify">A subconsulta <code>(SELECT AVG(Preco) FROM Produtos)</code> retorna <b>1000</b>. A consulta externa filtra produtos com preço maior que 1000.</p>
```
```ad-quote
title:
| Nome | Preco |
| :--- | :--- |
| Notebook | 3000 |
| Smartphone | 1500 |
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Subconsulta de Múltiplos Valores / Lista

```ad-quote
title:
<p align="justify">Retorna UMA COLUNA com MÚLTIPLAS LINHAS. É usada para comparar um valor contra uma lista de possíveis resultados.</p>
```
```ad-quote
title:

| Operadores Comuns |
| :--- |
| <code>IN</code> |
| <code>NOT IN</code> |
| <code>ANY</code> |
| <code>ALL</code> |

```

```SQL
-- Encontra produtos de categorias específicas (Eletrônicos ou Informática)
SELECT 
    Nome
FROM 
    Produtos
WHERE 
    ID_Categoria IN (
        SELECT ID_Categoria FROM Categorias 
        WHERE Nome = 'Eletrônicos' OR Nome = 'Informática'
    );
```

```ad-quote
title:
<p align="justify">A subconsulta retorna a lista de IDs <code>(10, 20)</code>. A consulta externa busca produtos nessas categorias.</p>
```
```ad-quote
title:
| Nome |
| :--- |
| Notebook |
| Mouse |
| Smartphone |
| Fone de Ouvido |
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Subconsulta Correlacionada / EXISTS

```ad-quote
title:
<p align="justify">Uma subconsulta que faz referência a colunas da consulta externa. Ela é executada uma vez para CADA LINHA processada pela consulta externa. É comumente usada para verificar a existência de dados relacionados.</p>
```
```ad-quote
title:

| Operadores Comuns |
| :--- |
| <code>EXISTS</code> |
| <code>NOT EXISTS</code> |

```

```SQL
-- Encontra clientes que fizeram pelo menos um pedido
SELECT 
    Nome_Cliente
FROM 
    Clientes AS c
WHERE 
    EXISTS (
        SELECT 1 FROM Pedidos AS p 
        WHERE p.ID_Cliente = c.ID_Cliente
    );
```

```ad-quote
title:
<p align="justify">A consulta retorna apenas 'Ana' (ID 100) e 'Carla' (ID 102), pois são as únicas que possuem correspondência na tabela <code>Pedidos</code>. 'Bruno' e 'Davi' são filtrados.</p>
```
```ad-quote
title:
| Nome_Cliente |
| :--- |
| Ana |
| Carla |
```

````

---

```ad-done
title:
#### **Fase 2 )** - Operadores de Conjunto / Set Operators
```

---

````ad-quote
title:

##### **04 )** - Definição

```ad-quote
title:
<p align="justify">Operadores de conjunto combinam os CONJUNTOS DE RESULTADOS de duas ou more instruções <code>SELECT</code>. Para que funcionem, as consultas devem ter o mesmo número de colunas e tipos de dados compatíveis em cada coluna.</p>
<p align="justify">Diferente de um <code>JOIN</code> (que combina colunas horizontalmente), os operadores de conjunto "empilham" as linhas verticalmente.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - UNION

```ad-quote
title:
<p align="justify">Combina os resultados de duas consultas e REMOVE AUTOMATICAMENTE quaisquer linhas duplicadas. (Conjunto A ∪ B)</p>
```

```SQL
-- Lista de emails de clientes atuais E potenciais, sem duplicatas
SELECT Email FROM Clientes_Atuais
UNION
SELECT Email FROM Clientes_Potenciais;
```

```ad-quote
title:
<p align="justify">O email <code>bruno@email.com</code>, que aparece em ambas as tabelas, é listado apenas uma vez.</p>
```
```ad-quote
title:
| Email |
| :--- |
| ana@email.com |
| bruno@email.com |
| carla@email.com |
| davi@email.com |
| elisa@email.com |
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - UNION ALL

```ad-quote
title:
<p align="justify">Combina os resultados de duas consultas e MANTÉM TODAS AS LINHAS, incluindo duplicatas. É mais rápido que o <code>UNION</code> por não precisar verificar duplicatas.</p>
```

```SQL
-- Contagem total de emails, incluindo duplicatas
SELECT Email FROM Clientes_Atuais
UNION ALL
SELECT Email FROM Clientes_Potenciais;
```

```ad-quote
title:
<p align="justify">O email <code>bruno@email.com</code> aparece duas vezes, pois está presente em ambas as tabelas originais.</p>
```
```ad-quote
title:
| Email |
| :--- |
| ana@email.com |
| bruno@email.com |
| carla@email.com |
| bruno@email.com |
| davi@email.com |
| elisa@email.com |
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - INTERSECT

```ad-quote
title:
<p align="justify">Retorna apenas as linhas que estão presentes EM AMBOS os conjuntos de resultados. (Conjunto A ∩ B)</p>
```

```SQL
-- Lista de emails que são TANTO clientes atuais QUANTO potenciais
SELECT Email FROM Clientes_Atuais
INTERSECT
SELECT Email FROM Clientes_Potenciais;
```

```ad-quote
title:
<p align="justify">Apenas <code>bruno@email.com</code> é retornado, pois é o único email presente nos dois conjuntos.</p>
```
```ad-quote
title:
| Email |
| :--- |
| bruno@email.com |
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **08 )** - EXCEPT / MINUS

```ad-quote
title:
<p align="justify">Retorna as linhas do PRIMEIRO conjunto de resultados que NÃO ESTÃO PRESENTES no SEGUNDO. (Conjunto A - B)</p>
```

```SQL
-- Lista de clientes atuais que NÃO estão na lista de potenciais
SELECT Email FROM Clientes_Atuais
EXCEPT
SELECT Email FROM Clientes_Potenciais;
```

```ad-quote
title:
<p align="justify">Retorna os emails da tabela <code>Clientes_Atuais</code> que não existem na <code>Clientes_Potenciais</code>. <code>bruno@email.com</code> é removido por estar no segundo conjunto.</p>
```
```ad-quote
title:
| Email |
| :--- |
| ana@email.com |
| carla@email.com |
```

````

---