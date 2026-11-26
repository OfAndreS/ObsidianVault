---
banner: "![[Pasted image 20251027210210.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O que é uma View

```ad-quote
title:
<p align="justify">Pense em uma View (Visão) como uma lente pré-configurada ou um atalho salvo para o seu banco de dados.</p>
```
```ad-quote
title:
<p align="justify">Tecnicamente, uma View é um objeto de banco de dados que armazena uma consulta <code>SELECT</code> sob um nome específico. Ela não armazena os dados fisicamente (como uma tabela faz); ela armazena a receita (a query) para buscar esses dados.</p>
```
```ad-quote
title:
<p align="justify">Quando você executa um <code>SELECT * FROM MinhaView</code>, o sistema de banco de dados (SGBD) intercepta essa chamada, substitui "MinhaView" pela consulta complexa que ela representa, e então executa essa consulta resultante contra as tabelas-base. Por isso, ela é chamada de tabela virtual.</p>
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
<p align="justify">Novamente, vamos usar nosso banco de dados universitário como base para todos os exemplos:</p>
```
```ad-quote
title:
**Tabela Alunos**
```
```ad-quote
title:

| ID_Aluno | Nome | Email | CR | Status |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Ana Silva | ana.silva@email.com | 9.2 | Ativo |
| 2 | Bruno Costa | bruno.c@email.com | 7.5 | Ativo |
| 3 | Carla Dias | carla.d@email.com | 8.8 | Inativo |
| 4 | Davi Moreira | davi.m@email.com | 8.1 | Ativo |
```
```ad-quote
title:
**Tabela Cursos**
```
```ad-quote
title:

| ID_Curso | Nome_Curso |
| :--- | :--- |
| 10 | Engenharia de Software |
| 20 | Medicina |
| 30 | Direito |
```
```ad-quote
title:
**Tabela Matriculas**
```
```ad-quote
title:

| ID_Matricula | ID_Aluno | ID_Curso |
| :--- | :--- | :--- |
| 100 | 1 | 10 |
| 101 | 2 | 10 |
| 102 | 3 | 20 |
| 103 | 4 | 10 |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Benefício 1 - Simplicidade / Abstração de Complexidade

```ad-quote
title:
<p align="justify">Uma View atua como uma camada de abstração. Ela permite encapsular uma lógica de negócios complexa, que pode envolver múltiplos <code>JOINs</code>, cálculos e filtros, em um objeto com um nome simples e intuitivo.</p>
```
```ad-quote
title:
<p align="justify">Conceito: Isso é análogo a criar uma função ou um método em programação. Os consumidores da (View) (analistas, relatórios, aplicações) não precisam saber como os dados são reunidos; eles apenas consomem o resultado final. Eles chamam a "função" (<code>SELECT * FROM MinhaView</code>) sem precisar ver o código-fonte complexo dela.</p>
```
```ad-quote
title:
###### **Exemplo:**
```
```ad-quote
title:
<p align="justify">O Problema: A reitoria precisa, toda segunda-feira, da lista de alunos de "Engenharia de Software" com status "Ativo" e <code>CR</code> acima de 8.0. A consulta é verbosa e fácil de errar.</p>
```

```SQL
SELECT 
    a.Nome, a.Email, a.CR
FROM Alunos AS a
JOIN Matriculas AS m ON a.ID_Aluno = m.ID_Aluno
JOIN Cursos AS c ON c.ID_Curso = m.ID_Curso
WHERE 
    c.Nome_Curso = 'Engenharia de Software'
    AND a.Status = 'Ativo'
    AND a.CR > 8.0;
```

```ad-quote
title:
###### **A Solução - Criar a View:**
```
```ad-quote
title:
<p align="justify">Você, como DBA, cria a (View) uma única vez.</p>
```

```SQL
CREATE VIEW V_Alunos_Destaque_EngSoft AS
SELECT 
    a.Nome, a.Email, a.CR
FROM Alunos AS a
JOIN Matriculas AS m ON a.ID_Aluno = m.ID_Aluno
JOIN Cursos AS c ON c.ID_Curso = m.ID_Curso
WHERE 
    c.Nome_Curso = 'Engenharia de Software'
    AND a.Status = 'Ativo'
    AND a.CR > 8.0;
```

```ad-quote
title:
###### **O Resultado:**
```
```ad-quote
title:
<p align="justify">A partir de agora, a reitoria (ou qualquer aplicação) obtém essa informação com uma consulta limpa e legível.</p>
```

```SQL
SELECT * FROM V_Alunos_Destaque_EngSoft;
```

```ad-quote
title: 
###### **Saída - Tabela Virtual**
```
```ad-quote
title:

| Nome | Email | CR |
| :--- | :--- | :--- |
| Ana Silva | ana.silva@email.com | 9.2 |
| Davi Moreira | davi.m@email.com | 8.1 |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Benefício 2 - Segurança / Controle de Acesso Granular

```ad-quote
title:
<p align="justify">(Views) são a principal ferramenta de um DBA para implementar segurança em nível de dados. Elas funcionam como um "proxy" que filtra o que um usuário pode ver e fazer.</p>
```
```ad-quote
title:
<p align="justify">Conceito: Em vez de dar permissão a um usuário para acessar a (tabela Alunos) inteira, você dá permissão apenas para acessar uma (View). Essa (View), por sua vez, age como um filtro em duas dimensões:</p>
```
```ad-quote
title:
<p align="justify">Segurança Vertical (Nível de Coluna): A (cláusula SELECT) da View age como um "tapa-olho", expondo seletivamente apenas as colunas que um usuário deve ver e escondendo colunas sensíveis (como <code>CR</code>).</p>
```
```ad-quote
title:
<p align="justify">Segurança Horizontal (Nível de Linha): A (cláusula WHERE) da View filtra quais linhas o usuário pode acessar (ex: mostrar apenas alunos do status "Ativo").</p>
```
```ad-quote
title:
###### **Exemplo:**
```
```ad-quote
title:
<p align="justify">O Problema: A equipe de marketing precisa de uma lista de contatos de alunos, mas não deve ver o <code>CR</code> (sensível) e não deve ver alunos "Inativos".</p>
```
```ad-quote
title:
###### **A Solução - Criar a View:**
```

```SQL
CREATE VIEW V_Marketing_Contatos_Ativos AS
SELECT 
    Nome, 
    Email
FROM 
    Alunos
WHERE 
    Status = 'Ativo';
```

```ad-quote
title:
###### **A Implementação da Segurança:**
```

```SQL
-- 1. Garante que o usuário 'mkt_user' NÃO pode ver a tabela original
REVOKE ALL ON Alunos FROM 'mkt_user';

-- 2. Concede permissão de leitura APENAS na View
GRANT SELECT ON V_Marketing_Contatos_Ativos TO 'mkt_user';

-- 3. (Opcional) Proíbe updates, mesmo que a View seja atualizável
REVOKE UPDATE, DELETE ON V_Marketing_Contatos_Ativos FROM 'mkt_user';
```

```ad-quote
title: 

###### **Saída - O que mkt_user vê**
```
```ad-quote
title:

| Nome | Email |
| :--- | :--- |
| Ana Silva | ana.silva@email.com |
| Bruno Costa | bruno.c@email.com |
| Davi Moreira | davi.m@email.com |
```
```ad-quote
title:
<p align="justify">A aluna 'Carla Dias' (Inativa) e a coluna <code>CR</code> estão 100% invisíveis</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Benefício 3 - Modularização

```ad-quote
title:
<p align="justify">Este é um dos benefícios arquiteturais mais importantes. A (View) (desacopla) a aplicação (ou o relatório) da estrutura física das tabelas-base.</p>
```
```ad-quote
title:
<p align="justify">Conceito: A (View) se torna um ("contrato" estável), uma (interface) de dados. As aplicações e relatórios são programados para "conversar" com essa interface (a (View)), e não com a implementação concreta (as tabelas). Se a estrutura das tabelas mudar (uma (refatoração)), você só precisa atualizar a (View); as aplicações continuam funcionando sem alteração.</p>
```
```ad-quote
title:
###### **Exemplo:**
```
```ad-quote
title:
<p align="justify">O Problema: Você tem 10 relatórios que buscam o <code>Email</code> do aluno. A diretoria decide que a coluna <code>Email</code> na tabela <code>Alunos</code> deve ser renomeada para <code>Email_Academico</code>.</p>
```
```ad-quote
title:
<p align="justify">Cenário Sem View: Todos os 10 relatórios quebrariam (Error: Column 'Email' not found). Você teria que editar o código-fonte de todos os 10 relatórios.</p>
```
```ad-quote
title:
<p align="justify">Cenário Com View:</p>
```
```ad-quote
title:
<p align="justify">Originalmente: Seus relatórios não acessavam <code>Alunos</code>. Eles acessavam uma (View):</p>
```

```SQL
-- Definição Original da View
CREATE VIEW V_Alunos_Publica AS
SELECT ID_Aluno, Nome, Email FROM Alunos;

-- Relatório (exemplo):
SELECT Nome, Email FROM V_Alunos_Publica WHERE ID_Aluno = 1;
```

```ad-quote
title:
###### **A Refatoração:**
```
```ad-quote
title:
<p align="justify">O DBA executa a mudança no banco de dados.</p>
```

```SQL
-- Passo 1: Renomeia a coluna na tabela física
ALTER TABLE Alunos RENAME COLUMN Email TO Email_Academico;

-- Passo 2: Atualiza a View para mapear o novo nome de volta ao antigo
-- A View "absorve" a mudança, mantendo o "contrato" externo.
CREATE OR REPLACE VIEW V_Alunos_Publica AS
SELECT ID_Aluno, Nome, Email_Academico AS Email
FROM Alunos;
```

```ad-quote
title:
###### **O Resultado:**
```
```ad-quote
title:
<p align="justify">Nenhum dos 10 relatórios quebrou. Eles continuam pedindo a coluna <code>Email</code> para a <code>V_Alunos_Publica</code>. A (View), que agora foi atualizada, traduz esse pedido e busca os dados da coluna <code>Email_Academico</code> na tabela <code>Alunos</code>. A manutenção foi centralizada em um único objeto.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Tópico Adicional - Vistas Atualizáveis

```ad-quote
title:
<p align="justify">Conceito: Embora a função principal de uma (View) seja a leitura, algumas (Views) permitem que (comandos DML) (<code>INSERT</code>, <code>UPDATE</code>, <code>DELETE</code>) sejam executados nela. O SGBD, então, repassa essa operação para a (tabela-base).</p>
```
```ad-quote
title:
<p align="justify">A regra principal para uma (View) ser atualizável é a (ausência de ambiguidade): o SGBD precisa saber exatamente qual linha e qual coluna da (tabela-base) devem ser modificadas. Isso geralmente significa:</p>
```
```ad-quote
title:
<p align="justify">Baseada em uma única tabela.</p>
```
```ad-quote
title:
<p align="justify">Não pode conter (agregações) (<code>GROUP BY</code>, <code>COUNT()</code>, <code>SUM()</code>).</p>
```
```ad-quote
title:
<p align="justify">Não pode conter <code>DISTINCT</code>, <code>UNION</code>, etc.</p>
```

```ad-quote
title:
###### **A View:**
```

```SQL
CREATE VIEW V_Emails_Alunos AS
SELECT ID_Aluno, Nome, Email FROM Alunos;
```

```ad-quote
title: 
###### **Tabela Alunos - Antes**
```
```ad-quote
title:

| ID_Aluno | Nome | Email | ... |
| :--- | :--- | :--- | :--- |
| 2 | Bruno Costa | bruno.c@email.com | ... |
```
```ad-quote
title:
###### **A Operação - feita na View:**
```

```SQL
UPDATE V_Emails_Alunos 
SET Email = 'bruno.costa@novo.email.com' 
WHERE ID_Aluno = 2;
```

```ad-quote
title: 
###### **Tabela Alunos - Depois**
```
```ad-quote
title:

| ID_Aluno | Nome | Email | ... |
| :--- | :--- | :--- | :--- |
| 2 | Bruno Costa | bruno.costa@novo.email.com | ... |
```
```ad-quote
title:
<p align="justify">A tabela-base foi modificada com sucesso através da View.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - A Principal Desvantagem: Performance

```ad-quote
title:
<p align="justify">Conceito: Uma (View) padrão é uma (abstração lógica), não (física). Ela é, essencialmente, uma ("macro" de texto). Quando você consulta a (View), o SGBD "cola" a definição da (View) na sua consulta e depois otimiza e executa a consulta inteira.</p>
```
```ad-quote
title:
<p align="justify">O custo da complexidade (os <code>JOINs</code>, os filtros) é pago em (tempo de execução) (runtime).</p>
```
```ad-quote
title:
###### **Exemplo:**
```
```ad-quote
title:
<p align="justify">Se 100 usuários abrirem um dashboard que usa a <code>V_Alunos_Destaque_EngSoft</code> (nossa primeira (View)), a consulta complexa com 3 <code>JOINs</code> e múltiplos <code>WHEREs</code> será executada 100 vezes.</p>
```
```ad-quote
title:
<p align="justify">Isso não é um problema para (Views) simples, mas para (Views) que unem tabelas de milhões de linhas, a latência pode ser um grande gargalo.</p>
```
```ad-quote
title:
<p align="justify">(Nota avançada: Esse problema de performance é exatamente o que as (Visões Materializadas) (Materialized Views) resolvem. Diferente das (Views) padrão, uma (Visão Materializada) (armazena fisicamente) os dados (como um (cache)), oferecendo leitura instantânea. O "custo" dela é outro: os dados podem ficar (desatualizados) (stale) e precisam ser atualizados periodicamente).</p>
```
````

---