---
banner: "![[Pasted image 20251027210033.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O que é um Trigger (Gatilho)?

```ad-quote
title:
<p align="justify">Claro. Vamos mergulhar fundo no conceito de Triggers (Gatilhos).</p>
```
```ad-quote
title:
<p align="justify">Se as Views são a "leitura" e as Visões Materializadas são o "cache", os Triggers são a "AUTOMAÇÃO" ou a "REAÇÃO" do banco de dados.</p>
```
```ad-quote
title:
<p align="justify">Pense em um Trigger (Gatilho) como um alarme de segurança ou um sensor de movimento para o seu banco de dados. É um procedimento especial que você "arma" e que o SGBD executa AUTOMATICAMENTE quando um evento específico ocorre em uma tabela.</p>
```
```ad-quote
title:
<p align="justify">Diferente de uma View ou uma Stored Procedure, você NUNCA chama um Trigger pelo nome. Ele não é executado por um usuário; ele é DISPARADO pelo SGBD em resposta a uma ação de dados.</p>
```
```ad-quote
title:
<p align="justify">A sua finalidade é impor regras de negócio complexas, auditar mudanças ou automatizar ações que não podem ser feitas por restrições simples (<code>CONSTRAINTS</code>).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Os 3 Componentes de um Trigger

```ad-quote
title:
<p align="justify">Para definir um Trigger, você precisa responder a três perguntas:</p>
````

````ad-quote
title:
###### **A ) -** O EVENTO - O que dispara?

```ad-quote
title:
<p align="justify">A ação que o SGBD está "escutando". Quase sempre é um comando DML (Data Manipulation Language):</p>
```
```ad-quote
title:
###### **INSERT:**
```
```ad-quote
title:
<p align="justify">Quando uma nova linha é inserida.</p>
```
```ad-quote
title:
###### **UPDATE:**
```
```ad-quote
title:
<p align="justify">Quando uma linha existente é modificada.</p>
```
```ad-quote
title:
###### **DELETE:**
```
```ad-quote
title:
<p align="justify">Quando uma linha é removida.</p>
```
````

````ad-quote
title:
###### **B ) -** O MOMENTO - Quando dispara?

```ad-quote
title:
<p align="justify">O ponto exato em que a ação do Trigger deve ocorrer em relação ao evento.</p>
```
```ad-quote
title:
###### **BEFORE:**
```
```ad-quote
title:
<p align="justify">A ação do Trigger roda ANTES do SGBD tentar executar o comando (<code>INSERT</code>, <code>UPDATE</code>, <code>DELETE</code>). Isso é útil para VALIDAR ou MODIFICAR os dados antes que eles sejam salvos.</p>
```
```ad-quote
title:
###### **AFTER:**
```
```ad-quote
title:
<p align="justify">A ação do Trigger roda DEPOIS que o comando foi executado com sucesso. Isso é útil para AUDITAR ou disparar ações em outras tabelas (como criar um log).</p>
```
````

````ad-quote
title:
###### **C ) -** O NÍVEL - Com que frequência dispara?

```ad-quote
title:
###### **FOR EACH ROW - Nível de Linha:**
```
```ad-quote
title:
<p align="justify">A ação do Trigger executa UMA VEZ PARA CADA LINHA afetada pelo comando. Se você der um <code>UPDATE</code> que afeta 1.000 linhas, o Trigger roda 1.000 vezes. Este é o tipo MAIS COMUM.</p>
```
```ad-quote
title:
###### **FOR EACH STATEMENT - Nível de Comando:**
```
```ad-quote
title:
<p align="justify">A ação do Trigger executa APENAS UMA VEZ, não importa quantas linhas foram afetadas.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - As "Tabelas Mágicas": NEW e OLD

```ad-quote
title:
<p align="justify">Quando um Trigger <code>FOR EACH ROW</code> é disparado, o SGBD nos dá acesso a duas "pseudo-tabelas" especiais que contêm os dados da linha que está sendo afetada. Os nomes podem variar um pouco (ex: <code>inserted</code>/<code>deleted</code> no SQL Server), mas o conceito é universal:</p>
```
```ad-quote
title:
<p align="justify"><code>OLD</code>: Contém a versão da linha ANTES da mudança (os dados antigos).</p>
```
```ad-quote
title:
<p align="justify"><code>NEW</code>: Contém a versão da linha DEPOIS da mudança (os novos dados que estão tentando entrar).</p>
```
```ad-quote
title:
<p align="justify">Como elas se comportam em cada EVENTO:</p>
```
```ad-quote
title:

| Evento | <code>OLD</code> (Dados Antigos) | <code>NEW</code> (Dados Novos) |
| :--- | :--- | :--- |
| <code>INSERT</code> | <code>NULL</code> (não havia nada antes) | Contém a nova linha a ser inserida |
| <code>UPDATE</code> | Contém a linha como ela era antes | Contém a linha com as modificações |
| <code>DELETE</code> | Contém a linha que está sendo apagada | <code>NULL</code> (não haverá nada depois) |
```
```ad-quote
title:
<p align="justify">O acesso a <code>OLD</code> e <code>NEW</code> é o que torna os Triggers tão poderosos para validação e auditoria.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Tabelas de Exemplo

```ad-quote
title:
<p align="justify">Vamos usar a tabela <code>Alunos</code> e criar uma nova tabela <code>Auditoria_Alunos</code> para nossos exemplos.</p>
```
```ad-quote
title:
**Tabela Alunos**
```
```ad-quote
title:

| ID_Aluno | Nome | CR | Status |
| :--- | :--- | :--- | :--- |
| 1 | Ana Silva | 9.2 | Ativo |
| 2 | Bruno Costa | 7.5 | Ativo |
| 3 | Carla Dias | 8.8 | Inativo |
```
```ad-quote
title:
**Tabela Auditoria_Alunos** (Nova)
```
```ad-quote
title:

| ID_Log | ID_Aluno_Afetado | Campo_Alterado | Valor_Antigo | Valor_Novo | Data_Alteracao | Usuario_BD |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| (auto) | ... | ... | ... | ... | ... | ... |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Exemplo 1: Auditoria - Trigger <code>AFTER UPDATE</code>

```ad-quote
title:
<p align="justify">O Problema: Precisamos manter um histórico de TODAS as mudanças de status dos alunos. Se um aluno for de "Ativo" para "Inativo" (ou vice-versa), queremos registrar QUEM, QUANDO e O QUE mudou.</p>
```
```ad-quote
title:
<p align="justify">A Solução: Um Trigger <code>AFTER UPDATE</code> no Nível de Linha (<code>FOR EACH ROW</code>) que verifica se o campo <code>Status</code> mudou. Se mudou, ele insere um registro na tabela <code>Auditoria_Alunos</code>.</p>
```
```ad-quote
title:
###### **A Criação do Trigger:**
```

```SQL
CREATE TRIGGER TRG_Audita_Status_Aluno
-- 2. MOMENTO: Depois que o UPDATE for confirmado
AFTER UPDATE ON Alunos
-- 3. NÍVEL: Para cada linha afetada
FOR EACH ROW
BEGIN
    -- Usamos OLD e NEW para comparar os valores
    IF OLD.Status <> NEW.Status THEN
        -- Ação do Trigger: Inserir na tabela de Log
        INSERT INTO Auditoria_Alunos
            (ID_Aluno_Afetado, Campo_Alterado, Valor_Antigo, Valor_Novo, Data_Alteracao, Usuario_BD)
        VALUES
            (OLD.ID_Aluno, 'Status', OLD.Status, NEW.Status, NOW(), CURRENT_USER());
    END IF;
END;
```

```ad-quote
title:
###### **O Evento - O que o usuário faz:**
```
```ad-quote
title:
<p align="justify">O usuário 'admin' executa um comando SQL simples, sem saber do Trigger.</p>
```

```SQL
UPDATE Alunos SET Status = 'Inativo' WHERE ID_Aluno = 2;
```

```ad-quote
title:
###### **O Resultado - O que o Trigger faz:**
```
```ad-quote
title:
<p align="justify">O SGBD dispara o Trigger AUTOMATICAMENTE. A tabela <code>Auditoria_Alunos</code> agora contém:</p>
```
```ad-quote
title:

| ID_Log | ID_Aluno_Afetado | Campo_Alterado | Valor_Antigo | Valor_Novo | Data_Alteracao | Usuario_BD |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 2 | 'Status' | 'Ativo' | 'Inativo' | 2025-10-27... | 'admin' |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Exemplo 2: Integridade de Dados Trigger - <code>BEFORE UPDATE</code>

```ad-quote
title:
<p align="justify">O Problema: A reitoria define uma regra de negócio complexa: "O Coeficiente de Rendimento (<code>CR</code>) de um aluno NUNCA pode ser diminuído manualmente. Ele só pode aumentar."</p>
```
```ad-quote
title:
<p align="justify">Uma restrição <code>CHECK</code> não pode fazer isso, pois ela não sabe o valor ANTIGO da linha. Precisamos de um Trigger.</p>
```
```ad-quote
title:
<p align="justify">A Solução: Um Trigger <code>BEFORE UPDATE</code> (ANTES da ação) que compara o <code>CR</code> antigo com o novo. Se o novo for menor, o Trigger CANCELA a operação.</p>
```
```ad-quote
title:
###### **A Criação do Trigger:**
```

```SQL
CREATE TRIGGER TRG_Impede_Diminuir_CR
-- 2. MOMENTO: Antes do UPDATE ser aplicado
BEFORE UPDATE ON Alunos
-- 3. NÍVEL: Para cada linha
FOR EACH ROW
BEGIN
    -- Comparamos o NOVO valor com o ANTIGO
    IF NEW.CR < OLD.CR THEN
        -- Ação do Trigger: Lançar um ERRO e cancelar o UPDATE
        -- (A sintaxe exata para "lançar erro" varia:
        -- SIGNAL SQLSTATE, RAISE_APPLICATION_ERROR, RAISE EXCEPTION)
        SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'ERRO: Não é permitido diminuir o CR de um aluno.';
    END IF;
END;
```

```ad-quote
title:
###### **O Evento - O que o usuário tenta fazer:**
```

```SQL
-- Esta operação é válida
UPDATE Alunos SET CR = 7.8 WHERE ID_Aluno = 2; -- (OK, 7.8 > 7.5)

-- Esta operação é INVÁLIDA
UPDATE Alunos SET CR = 9.0 WHERE ID_Aluno = 1; -- (ERRO, 9.0 < 9.2)
```

```ad-quote
title:
###### **O Resultado:**
```
```ad-quote
title:
<p align="justify">O primeiro <code>UPDATE</code> funciona. O segundo <code>UPDATE</code> falha e retorna uma mensagem de erro para o usuário. O Trigger protegeu a integridade dos dados.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - As Desvantagens e Perigos dos Triggers

```ad-quote
title:
<p align="justify">Triggers são EXTREMAMENTE poderosos, mas também são uma das funcionalidades mais perigosas de um SGBD. Muitos DBAs experientes evitam usá-los, exceto como último recurso.</p>
```
```ad-quote
title:
###### **A ) -** LÓGICA OCULTA O EFEITO "FANTASMA":
```
```ad-quote
title:
<p align="justify">Esta é a PIOR ARMADILHA. Um desenvolvedor júnior executa um simples <code>INSERT</code> e, sem que ele saiba, o Trigger dispara e atualiza outras 5 tabelas, envia um e-mail e apaga registros antigos. Como a lógica não está na aplicação, e sim "escondida" no banco, a depuração (debug) se torna um PESADELO.</p>
```
```ad-quote
title:
###### **B ) -** PERFORMANCE:
```
```ad-quote
title:
<p align="justify">Um Trigger <code>FOR EACH ROW</code> é um custo computacional. Se você faz uma inserção em lote (batch) de 1 MILHÃO de linhas, o seu Trigger de auditoria irá rodar 1 MILHÃO de vezes. Isso pode tornar uma operação que levaria 5 segundos levar 50 minutos.</p>
```
```ad-quote
title:
###### **C ) -** TRIGGERS EM CASCATA E LOOPS INFINITOS:
```
```ad-quote
title:
<p align="justify">Cenário: Você tem um Trigger na Tabela A que, ao ser atualizada, atualiza a Tabela B. Mas a Tabela B também tem um Trigger que, ao ser atualizado, atualiza a Tabela A. O usuário atualiza a Tabela A... e o SGBD entra em um loop infinito até estourar a memória ou o limite de recursão.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Resumo: Quando Usar (e Não Usar)

```ad-quote
title:
###### **A ) -** Use Triggers para:
```
```ad-quote
title:
<ul>
 <li>AUDITORIA ROBUSTA: O melhor caso de uso. Registrar quem mudou o quê e quando (Exemplo 1).</li>
 <li>REGRAS DE INTEGRIDADE COMPLEXAS: Regras que dependem de estados (<code>OLD</code> vs <code>NEW</code>) e que <code>CONSTRAINTS</code> não suportam (Exemplo 2).</li>
</ul>
```
```ad-quote
title:
###### **B ) -** Evite Triggers para:
```
```ad-quote
title:
<ul>
 <li>REGRAS DE NEGÓCIO DA APLICAÇÃO: Se a lógica é "quando um pedido é aprovado, enviar um e-mail", isso deve estar no CÓDIGO DA APLICAÇÃO (Python, Java, C#), não escondido no banco.</li>
 <li>REPLICAÇÃO DE DADOS SIMPLES: (Ex: "manter um contador atualizado"). Muitas vezes, uma Visão Materializada (MV) ou um procedimento agendado é uma solução mais limpa e com melhor performance.</li>
</ul>
```
```ad-quote
title:
<p align="justify">Triggers são a "magia" do banco de dados, mas, como toda magia, ela tem um custo e pode ser perigosa se usada sem cuidado.</p>
```
```ad-quote
title:
<p align="justify">Gostaria de ver como funcionam os Stored Procedures (Procedimentos Armazenados), que são os "blocos de construção" que os Triggers frequentemente utilizam para organizar lógicas complexas?</p>
```
````

---