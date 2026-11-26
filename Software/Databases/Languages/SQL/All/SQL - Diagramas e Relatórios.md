
---

````ad-quote
title:

##### **Intro )** - O que são Diagramas e Relatórios?

```ad-quote
title:
<p align="justify">Se as Tabelas são os "tijolos" e as Views/Triggers são as "ferramentas", então os Diagramas são a "PLANTA BAIXA" (o design) e os Relatórios são a "CASA PRONTA" (o produto final entregue ao usuário).</p>
```
```ad-quote
title:
<p align="justify">Um DIAGRAMA (especificamente um DER - Diagrama Entidade-Relacionamento) mostra a ARQUITETURA dos dados: quais tabelas existem e como elas se conectam.</p>
```
```ad-quote
title:
<p align="justify">Um RELATÓRIO é o PRODUTO FINAL de uma consulta. É a informação formatada, agregada e pronta para consumo, que permite a tomada de decisões (ex: um gráfico de pizza, uma planilha de resultados, um dashboard de BI).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Diagramas Entidade-Relacionamento (DER)

```ad-quote
title:
<p align="justify">Um Diagrama Entidade-Relacionamento (também chamado de ERD ou DER) é a principal ferramenta de modelagem de dados. Ele é o mapa que guia a construção do banco de dados.</p>
```
```ad-quote
title:
<p align="justify">Seus componentes principais são:</p>
````

````ad-quote
title:
##### **A ) -** ENTIDADES

```ad-quote
title:
<p align="justify">São os "substantivos" do seu sistema, que se tornam as TABELAS.</p>
```
```ad-quote
title:
<p align="justify">Em nosso exemplo: <code>Alunos</code>, <code>Cursos</code>, <code>Matriculas</code>.</p>
```
````

````ad-quote
title:
##### **B ) -** ATRIBUTOS

```ad-quote
title:
<p align="justify">São as "qualidades" ou "características" de uma entidade, que se tornam as COLUNAS.</p>
```
```ad-quote
title:
<p align="justify">Exemplos: O <code>Nome</code> e o <code>CR</code> da entidade <code>Alunos</code>.</p>
```
````

````ad-quote
title:
##### **C ) -** RELACIONAMENTOS (e Cardinalidade)

```ad-quote
title:
<p align="justify">São os "verbos" que conectam as entidades, implementados através de CHAVES ESTRANGEIRAS (Foreign Keys).</p>
```
```ad-quote
title:
<p align="justify">A CARDINALIDADE define a regra desse relacionamento (quantos de A se conectam a quantos de B).</p>
```
```ad-quote
title:
###### **Um-para-Muitos (1:N):**
```
```ad-quote
title:
<p align="justify">O tipo mais comum. Exemplo: "UM <code>Aluno</code> pode ter MUITAS <code>Matriculas</code>". A chave primária de <code>Alunos</code> (<code>ID_Aluno</code>) vai como chave estrangeira para a tabela <code>Matriculas</code>.</p>
```
```ad-quote
title:
###### **Muitos-para-Muitos (N:M):**
```
```ad-quote
title:
<p align="justify">Ocorre quando "MUITOS <code>Alunos</code> podem se matricular em MUITOS <code>Cursos</code>". Este relacionamento NÃO PODE ser implementado diretamente. Ele é "quebrado" em dois relacionamentos (1:N) usando uma TABELA ASSOCIATIVA.</p>
```
```ad-quote
title:
<p align="justify">A tabela <code>Matriculas</code> é a nossa tabela associativa. Ela resolve o N:M entre <code>Alunos</code> e <code>Cursos</code>.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O que são Relatórios?

```ad-quote
title:
<p align="justify">Relatórios são o objetivo final de quase todo banco de dados. Um banco existe para armazenar dados brutos e respondê-los de forma agregada e significativa.</p>
```
```ad-quote
title:
<p align="justify">Um relatório pode ser qualquer coisa, desde uma simples exportação CSV até um complexo dashboard interativo em ferramentas como Power BI, Tableau ou Google Looker Studio.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Como os Objetos de BD se Encaixam nos Relatórios

```ad-quote
title:
<p align="justify">É aqui que tudo se conecta. As ferramentas de relatório (como o Power BI) raramente (ou nunca deveriam) consultar as tabelas-base diretamente.</p>
````

````ad-quote
title:
##### **A ) -** VIEWS / Relatórios

```ad-quote
title:
<p align="justify">A View Padrão atua como a CAMADA DE ABSTRAÇÃO (ou "Contrato") para o relatório.</p>
```
```ad-quote
title:
<p align="justify">O Problema: O time de Marketing precisa de um relatório dos alunos de Engenharia de Software. Eles não sabem fazer <code>JOINs</code>.</p>
```
```ad-quote
title:
<p align="justify">A Solução: O DBA cria a <code>V_Alunos_Destaque_EngSoft</code>. A equipe de Marketing conecta sua ferramenta de BI (ex: Excel) a essa View. A lógica complexa fica no banco de dados, e o relatório consome apenas o resultado simples. Se o DBA refatorar as tabelas-base, ele só precisa atualizar a View; o relatório CONTINUA FUNCIONANDO.</p>
```
````

````ad-quote
title:
##### **B ) -** VISÕES MATERIALIZADAS / Relatórios

```ad-quote
title:
<p align="justify">A Visão Materializada atua como a CAMADA DE PERFORMANCE (ou "Cache") para o relatório.</p>
```
```ad-quote
title:
<p align="justify">O Problema: O "Relatório de Alunos de Destaque" (nossa View) demora 90 segundos para carregar, pois envolve <code>JOINs</code> em tabelas de milhões de linhas. O dashboard fica inutilizável.</p>
```
```ad-quote
title:
<p align="justify">A Solução: O DBA converte a View em uma Visão Materializada (<code>MV_Alunos_Destaque_EngSoft</code>) e agenda um <code>REFRESH</code> para toda madrugada. Agora, quando os 100 usuários abrem o dashboard de manhã, ele carrega em 0.1 SEGUNDO, pois está lendo dados pré-calculados. O "custo" é que o relatório mostra os dados de D-1 (do dia anterior).</p>
```
````

````ad-quote
title:
##### **C ) -** TRIGGERS e Relatórios

```ad-quote
title:
<p align="justify">Triggers são a CAMADA DE COLETA DE DADOS para relatórios específicos (como auditoria).</p>
```
```ad-quote
title:
<p align="justify">O Problema: A reitoria precisa de um "Relatório de Alterações de Status" para saber quais alunos ficaram inativos no último mês.</p>
```
```ad-quote
title:
<p align="justify">A Solução: O <code>TRG_Audita_Status_Aluno</code> (que criamos anteriormente) já está populando a tabela <code>Auditoria_Alunos</code> em tempo real. O relatório da reitoria é simplesmente um <code>SELECT</code> nessa tabela <code>Auditoria_Alunos</code>. O Trigger foi o mecanismo que AUTOMATIZOU a coleta dos dados que o relatório consome.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Conclusão: O Fluxo Completo

```ad-quote
title:
<p align="justify">1. O DBA desenha o **DIAGRAMA** (a planta baixa).</p>
```
```ad-quote
title:
<p align="justify">2. As **TABELAS** são criadas (a fundação).</p>
```
```ad-quote
title:
<p align="justify">3. **TRIGGERS** são armados (os sensores que registram eventos, como logs de auditoria).</p>
```
```ad-quote
title:
<p align="justify">4. **VIEWS** e **VISÕES MATERIALIZADAS** são construídas sobre as tabelas (a "API" de dados, focada em segurança, simplicidade ou performance).</p>
```
```ad-quote
title:
<p align="justify">5. Os **RELATÓRIOS** (ferramentas de BI) são conectados a essas Views/MVs para entregar o produto final ao usuário.</p>
```
````

---
