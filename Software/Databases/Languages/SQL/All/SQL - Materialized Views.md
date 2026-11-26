---
banner: "![[Pasted image 20251027210210.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Visões Materializadas

```ad-quote
title:
<p align="justify">Uma View Padrão é uma RECEITA (a consulta <code>SELECT</code>). Toda vez que você quer o bolo, você tem que preparar a receita do zero (executar a query).</p>
```
```ad-quote
title:
<p align="justify">Uma Visão Materializada é o BOLO JÁ PRONTO (o resultado da consulta, salvo fisicamente em disco). Quando você quer o bolo, você apenas o pega no prato (lê os dados pré-calculados).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - O que é uma Visão Materializada?

```ad-quote
title:
<p align="justify">Uma Visão Materializada (MV) é um objeto de banco de dados que armazena FISICAMENTE o resultado de uma consulta.</p>
```
```ad-quote
title:
<p align="justify">Diferente de uma View padrão, que é apenas uma "macro" lógica, a MV é uma tabela real, oculta, que guarda os dados exatos que a sua consulta <code>SELECT</code> retornaria. Por ser uma cópia física, ela funciona como um CACHE ou um SNAPSHOT (uma foto) dos dados em um ponto específico no tempo.</p>
```
```ad-quote
title:
<p align="justify">Quando você faz <code>SELECT * FROM Minha_MV</code>, o banco de dados não executa a consulta complexa original. Ele simplesmente lê os dados que JÁ ESTÃO GUARDADOS nessa "tabela-cache".</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - A Vantagem Óbvia: Performance de Leitura

```ad-quote
title:
<p align="justify">Este é o motivo de elas existirem.</p>
```
```ad-quote
title:
<p align="justify">View Padrão: <code>SELECT * FROM V_Relatorio_Complexo;</code></p>
```
```ad-quote
title:
<p align="justify">O SGBD executa 5 <code>JOINs</code>, 3 <code>GROUP BYs</code>, e agrega 10 milhões de linhas.</p>
```
```ad-quote
title:
<p align="justify">Tempo: 90 segundos.</p>
```
```ad-quote
title:
<p align="justify">Visão Materializada: <code>SELECT * FROM MV_Relatorio_Complexo;</code></p>
```
```ad-quote
title:
<p align="justify">O SGBD lê uma tabela pré-calculada que já tem os resultados prontos.</p>
```
```ad-quote
title:
<p align="justify">Tempo: 0.1 segundo.</p>
```
```ad-quote
title:
<p align="justify">Para dashboards, relatórios e aplicações de BI, onde dezenas de usuários consultam os mesmos dados complexos repetidamente, a diferença é gigantesca.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - O "Custo" e a Grande Desvantagem: Desatualização - Staleness

```ad-quote
title:
<p align="justify">Aqui está a troca. Como a MV é um BOLO PRONTO (um cache físico), ela não sabe magicamente quando os ingredientes (as tabelas-base) mudam.</p>
```
```ad-quote
title:
<p align="justify">Se um novo aluno se matricula na tabela <code>Alunos</code>, a Visão Materializada que conta o total de alunos NÃO será atualizada automaticamente. Ela conterá dados antigos, ou DADOS DESATUALIZADOS (STALE).</p>
```
```ad-quote
title:
<p align="justify">Isso introduz o conceito mais importante das MVs: o REFRESH (Atualização).</p>
```
```ad-quote
title:
<p align="justify">O custo da View Padrão é pago no TEMPO DE LEITURA (lenta para ler).</p>
```
```ad-quote
title:
<p align="justify">O custo da Visão Materializada é pago no TEMPO DE ATUALIZAÇÃO (precisa de um processo para ser atualizada) e em ESPAÇO DE ARMAZENAMENTO (ela ocupa espaço em disco).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Como a Atualização - Refresh - Funciona?

```ad-quote
title:
<p align="justify">Já que os dados ficam desatualizados, você precisa de uma estratégia para atualizá-los. Isso é chamado de REFRESH (Atualizar). O SGBD não faz isso sozinho; você precisa dizer a ele como e quando fazer.</p>
```
```ad-quote
title:
<p align="justify">As estratégias de atualização variam conforme o SGBD (<code>PostgreSQL</code>, <code>Oracle</code>, <code>SQL Server</code>, etc.), mas os conceitos são universais:</p>
````

````ad-quote
title:
##### **A ) -** Tipos de Gatilho - Quando atualizar?

```ad-quote
title:
###### **ON DEMAND - Sob Demanda:**
```
```ad-quote
title:
<p align="justify">É o modo padrão e mais comum. A MV só é atualizada quando você, o DBA, executa um comando manually.</p>
```
```ad-quote
title:
<p align="justify">Comando (Exemplo PostgreSQL): <code>REFRESH MATERIALIZED VIEW MV_Relatorio_Complexo;</code></p>
```
```ad-quote
title:
<p align="justify">Uso: Você agenda esse comando para rodar toda noite às 2h da manhã, usando um <code>cron job</code> ou um agendador do próprio banco.</p>
```
```ad-quote
title:
###### **ON COMMIT:**
```
```ad-quote
title:
<p align="justify">(Menos comum e perigoso). A MV é atualizada toda vez que uma transação (<code>INSERT</code>, <code>UPDATE</code>, <code>DELETE</code>) é confirmada (<code>commit</code>) em uma das tabelas-base.</p>
```
```ad-quote
title:
<p align="justify">Vantagem: Os dados estão sempre frescos.</p>
```
```ad-quote
title:
<p align="justify">Desvantagem: Isso pode tornar operações de escrita (como salvar um formulário) EXTREMAMENTE LENTAS, pois elas agora têm o custo extra de recalcular a MV.</p>
</a>
```
```ad-quote
title:
###### **ON SCHEDULE - Agendado:**
```
```ad-quote
title:
<p align="justify">Alguns bancos permitem que você defina o agendamento na própria criação da MV.</p>
```
```ad-quote
title:
<p align="justify">Exemplo: <code>... REFRESH ... STARTING AT (meia-noite) NEXT (cada 1 dia).</code></p>
````

````ad-quote
title:
##### **B ) -** Tipos de Método - Como atualizar?

```ad-quote
title:
###### **COMPLETE:**
```
```ad-quote
title:
<p align="justify">O SGBD joga fora TODOS os dados antigos da MV (um <code>TRUNCATE</code>) e re-executa a consulta complexa original do zero, inserindo os novos resultados.</p>
```
```ad-quote
title:
<p align="justify">Vantagem: Simples de implementar.</p>
```
```ad-quote
title:
<p align="justify">Desvantagem: Pode ser MUITO LENTO se a consulta original demorar 90 segundos. Durante esse tempo, a MV pode ficar indisponível.</p>
```
```ad-quote
title:
###### **FAST / INCREMENTAL:**
```
```ad-quote
title:
<p align="justify">O método mais avançado. O SGBD é inteligente o suficiente para olhar apenas o que mudou nas tabelas-base (os "deltas") e aplicar apenas essas mudanças na MV.</p>
```
```ad-quote
title:
<p align="justify">Exemplo: Se 10 novos alunos foram inseridos, em vez de recalcular TUDO, ele apenas adiciona 10 na contagem da MV.</p>
```
```ad-quote
title:
<p align="justify">Vantagem: Atualização quase instantânea.</p>
```
```ad-quote
title:
<p align="justify">Desvantagem: MUITO mais complexo de configurar. Requer logs especiais nas tabelas-base (chamados <code>Materialized View Logs</code>) e tem muitas limitações (pode não funcionar com <code>JOINs</code> complexos, <code>GROUP BYs</code> etc.).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Casos de Uso Típicos

```ad-quote
title:
<p align="justify">Você usa MVs quando os três critérios a seguir são verdadeiros:</p>
```
```ad-quote
title:
<p align="justify">A CONSULTA É LENTA: A consulta original envolve <code>JOINs</code> pesados, agregações em milhões/bilhões de linhas, etc.</p>
```
```ad-quote
title:
<p align="justify">A LEITURA É FREQUENTE: Os mesmos dados serão lidos muitas vezes (ex: um dashboard de BI, a página inicial de um site).</p>
```
```ad-quote
title:
<p align="justify">HÁ TOLERÂNCIA À DESATUALIZAÇÃO: O usuário (ex: um diretor vendo um relatório) não se importa se os dados tiverem 1 hora ou até 24 horas de atraso.</p>
```
```ad-quote
title:
###### **Exemplos perfeitos:**
```
```ad-quote
title:
<p align="justify">Dashboards de BI (contagem de vendas do dia anterior).</p>
```
```ad-quote
title:
<p align="justify">Relatórios analíticos (total de matrículas por curso no semestre).</p>
```
```ad-quote
title:
<p align="justify">Cálculos de sumarização para IA/Machine Learning.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Comparação Direta: View Padrão vs. Visão Materializada

```ad-quote
title:

| Característica | View Padrão (Lógica) | Visão Materializada (Física) |
| :--- | :--- | :--- |
| O QUE ARMAZENA? | Apenas a Consulta <code>SELECT</code> (o "texto") | O RESULTADO da Consulta (os dados) |
| USO DE ESPAÇO | Mínimo (alguns bytes) | Alto (armazena todos os dados) |
| PERFORMANCE DE LEITURA | Lenta (executa a query toda vez) | Rápida (lê dados pré-calculados) |
| ATUALIZAÇÃO DOS DADOS | TEMPO REAL (sempre atualizados) | DESATUALIZADOS (um snapshot no tempo) |
| CUSTO PRINCIPAL | Pago no <code>SELECT</code> (Runtime) | Pago no <code>REFRESH</code> (Atualização) |
| CASO DE USO | Simplificar consultas do dia-a-dia, segurança | Acelerar dashboards e relatórios pesados (BI) |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Conclusão

```ad-quote
title:
<p align="justify">Em resumo, uma Visão Materializada é uma ferramenta de OTIMIZAÇÃO poderosa que troca "frescor" dos dados por performance de leitura.</p>
```
```ad-quote
title:
<p align="justify">Gostaria de ver um exemplo de sintaxe de como criar e atualizar uma Visão Materializada (usando a sintaxe do PostgreSQL como exemplo, já que é uma das mais claras)?</p>
```
````

---