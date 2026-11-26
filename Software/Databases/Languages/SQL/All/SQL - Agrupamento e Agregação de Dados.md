---
banner: "![[Pasted image 20251008190141.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Sumarizando Dados com Agregação

```ad-quote
title:
<p align="justify">Em análise de dados, raramente estamos interessados apenas em linhas individuais. Na maioria das vezes, queremos respostas sumarizadas sobre conjuntos de dados, como a contagem total de itens, a soma de valores ou a média de salários. As funções de agregação (COUNT, SUM, AVG) realizam esses cálculos. A cláusula GROUP BY é o mecanismo que nos permite aplicar essas funções a subconjuntos específicos de dados, como "a média salarial por departamento". Por fim, a cláusula HAVING atua como um filtro sobre os resultados desses grupos já agregados.</p>
```

>[!quote] **Doc:** [W3Schools SQL GROUP BY](https://www.w3schools.com/sql/sql_groupby.asp)

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

##### **01 )** - Funções de Agregação Essenciais

```ad-quote
title:
**Características Principais:**
```

```ad-quote
title:
<p align="justify">Funções de agregação operam sobre um conjunto de linhas e retornam um único valor de resumo. Elas são o coração das consultas de sumarização de dados.</p>
```

```ad-quote
title:

| Função | Explicação | Exemplo de Uso (na tabela inteira) |
| :---: | --- | --- |
| `COUNT()` | Conta o número de linhas. `COUNT(*)` conta todas as linhas; `COUNT(coluna)` conta valores não nulos. | `SELECT COUNT(*) FROM Colaboradores;` (Resultado: 8) |
| `SUM()` | Soma todos os valores de uma coluna numérica. | `SELECT SUM(Salario) FROM Colaboradores;` |
| `AVG()` | Calcula a média de todos os valores de uma coluna numérica. | `SELECT AVG(Salario) FROM Colaboradores;` |
| `MAX()` | Retorna o maior valor de uma coluna. | `SELECT MAX(Salario) FROM Colaboradores;` (Resultado: 14000.00) |
| `MIN()` | Retorna o menor valor de uma coluna. | `SELECT MIN(Salario) FROM Colaboradores;` (Resultado: 4200.00) |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - A Cláusula `GROUP BY`: Agrupando Linhas

```ad-quote
title:
<p align="justify">A cláusula GROUP BY agrupa linhas que têm os mesmos valores em colunas especificadas em um único registro de resumo. As funções de agregação, quando usadas com GROUP BY, calculam um resultado para cada um desses grupos, em vez de para a tabela inteira.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### **Uso Básico e Lógica**
```

```ad-quote
title:
Agrupa as linhas com base nos valores de uma ou mais colunas para que funções de agregação possam ser aplicadas a cada grupo.
```

```sql
-- Pergunta: Quantos funcionários existem em cada departamento?

SELECT
    Departamento,
    COUNT(ID_Colaborador) AS Quantidade_Funcionarios
FROM
    Colaboradores
GROUP BY
    Departamento;
```

```ad-quote
title:
**Resultado Esperado:**
```

```ad-quote
title:

| Departamento | Quantidade_Funcionarios |
| :--- | :--- |
| TI | 3 |
| Vendas | 2 |
| Marketing | 2 |
| RH | 1 |

```
````

````ad-quote
title:
```ad-quote
title:
###### **Regra Fundamental do `GROUP BY`**
```

```ad-quote
title:
<p align="justify">Toda coluna presente na cláusula `SELECT` deve ou ser parte de uma função de agregação (como COUNT, SUM, AVG) ou estar listada na cláusula `GROUP BY`. Isso é necessário porque, para um grupo como 'TI', o banco de dados não saberia qual `Nome_Completo` individual exibir, pois existem três nomes diferentes nesse grupo.</p>
```

```sql
-- ESTA CONSULTA GERARÁ UM ERRO!
-- O 'Nome_Completo' não está agregado nem no GROUP BY.
SELECT Departamento, Nome_Completo, COUNT(*)
FROM Colaboradores
GROUP BY Departamento;
```
````

````ad-quote
title:
```ad-quote
title:
###### **Agrupamento por Múltiplas Colunas**
```

```ad-quote
title:
<p align="justify">Você pode agrupar por mais de uma coluna para criar subgrupos mais granulares.</p>
```

```sql
-- Pergunta: Qual a média salarial para cada cargo dentro de cada departamento?

SELECT
    Departamento,
    Cargo,
    AVG(Salario) AS Media_Salarial
FROM
    Colaboradores
GROUP BY
    Departamento, Cargo
ORDER BY
    Departamento, Media_Salarial DESC;
```
````

````ad-quote
title:
```ad-quote
title:
###### **Agrupamento Entre Múltiplas Entidades**
```

```ad-quote
title:
<p align="justify">Você pode agrupar por mais de uma entidade.</p>
```

```sql
SELECT
    c.cidadeComprador,
    c.nomeComprador,
    SUM(v.valorVenda) AS TotalGasto
FROM
    Comprador AS c
    INNER JOIN Venda AS v ON c.idComprador = v.idComprador
GROUP BY
    c.cidadeComprador, c.nomeComprador
ORDER BY
    c.cidadeComprador, TotalGasto DESC;
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - A Cláusula `HAVING`: Filtrando Grupos

```ad-quote
title:
A cláusula HAVING foi introduzida porque a cláusula WHERE não pode ser usada com funções de agregação. Enquanto WHERE filtra linhas antes da agregação, HAVING filtra grupos após a agregação ter sido concluída.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Diferença Crucial: `WHERE` vs `HAVING`**
```

```ad-quote
title:

| Cláusula | Quando é Processada | O que Filtra | Pode usar Funções de Agregação? |
| :---: | --- | --- | :---: |
| `WHERE` | **Antes** do `GROUP BY` | Linhas Individuais | Não |
| `HAVING` | **Depois** do `GROUP BY` | Grupos Inteiros | Sim |

```
````

````ad-quote
title:
```ad-quote
title:
###### **Uso do `HAVING`**
```

```ad-quote
title:
É usado para impor condições sobre os resultados das funções de agregação.
```

```sql
-- Pergunta: Quais departamentos possuem mais de 1 funcionário?

SELECT
    Departamento,
    COUNT(ID_Colaborador) AS Quantidade_Funcionarios
FROM
    Colaboradores
GROUP BY
    Departamento
HAVING
    COUNT(ID_Colaborador) > 1; -- Filtra os grupos após a contagem
```
````

````ad-quote
title:
```ad-quote
title:
###### **Combinando `WHERE` e `HAVING`**
```

```ad-quote
title:
É comum usar as duas cláusulas em uma mesma consulta para filtrar tanto as linhas antes da agregação quanto os grupos após a agregação.
```

```sql
-- Pergunta: Dentre os funcionários contratados antes de 2022,
-- quais departamentos têm uma média salarial superior a 6000?

SELECT
    Departamento,
    AVG(Salario) AS Media_Salarial
FROM
    Colaboradores
WHERE
    Data_Contratacao < '2022-01-01' -- 1. Filtra as linhas primeiro
GROUP BY
    Departamento -- 2. Agrupa as linhas restantes
HAVING
    AVG(Salario) > 6000; -- 3. Filtra os grupos resultantes
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Ordem de Execução Lógica Completa

```ad-quote
title:
<p align="justify">Com a inclusão de GROUP BY e HAVING, a ordem lógica de processamento de uma consulta SQL se torna mais completa, e entendê-la é crucial para construir consultas complexas corretamente.</p>
```

```ad-quote
title:

| Ordem | Cláusula | Propósito |
| :---: | --- | --- |
| 1 | `FROM` | Define a(s) tabela(s) de origem. |
| 2 | `WHERE` | Filtra as linhas individuais. |
| 3 | `GROUP BY` | Agrupa as linhas filtradas em conjuntos. |
| 4 | `HAVING` | Filtra os grupos com base em condições de agregação. |
| 5 | `SELECT` | Seleciona as colunas e aplica expressões. |
| 6 | `ORDER BY` | Ordena o resultado final. |

```
````

---