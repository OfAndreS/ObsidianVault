---
banner: "![[Pasted image 20251027212455.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O que são Transações e Concorrência?

```ad-quote
title:
<p align="justify">A melhor analogia é um sistema bancário.</p>
```
```ad-quote
title:
<p align="justify">Uma TRANSAÇÃO é uma única operação "tudo ou nada". Pense em uma transferência: Debitar R$100 da Conta A E Creditar R$100 na Conta B. Não é aceitável que apenas METADE da operação aconteça. A transação garante que AMBAS aconteçam, ou NENHUMA aconteça.</p>
```
```ad-quote
title:
<p align="justify">CONCORRÊNCIA é o que acontece quando MILHARES de pessoas tentam fazer transferências (transações) ao MESMO TEMPO, usando as mesmas tabelas. É o trabalho do SGBD gerenciar esse caos, garantindo que uma transação não "atropele" ou corrompa os dados de outra.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - As Propriedades ACID - A Garantia da Transação

```ad-quote
title:
<p align="justify">Para que um SGBD seja considerado confiável (ou "transacional"), ele DEVE garantir quatro propriedades, conhecidas pelo acrônimo ACID.</p>
````

````ad-quote
title:
##### **A ) -** ATOMICITY - Atomicidade

```ad-quote
title:
<p align="justify">É a propriedade do "TUDO OU NADA".</p>
```
```ad-quote
title:
<p align="justify">A transação é uma unidade atômica, indivisível. Ela não pode ser quebrada. Ou todas as operações dentro dela (<code>INSERTs</code>, <code>UPDATEs</code>, <code>DELETEs</code>) são concluídas com sucesso (um <code>COMMIT</code>), ou NENHUMA delas é aplicada (um <code>ROLLBACK</code>).</p>
```
```ad-quote
title:
<p align="justify">Exemplo: Na transferência, se o débito da Conta A funcionar, mas o crédito na Conta B falhar (ex: a conta foi encerrada), o SGBD DESFAZ o débito da Conta A. O sistema volta ao estado original.</p>
```
````

````ad-quote
title:
##### **C ) -** CONSISTENCY - Consistência

```ad-quote
title:
<p align="justify">É a propriedade da "VALIDADE".</p>
```
```ad-quote
title:
<p align="justify">A transação deve levar o banco de dados de um estado válido para OUTRO estado válido. Ela não pode violar as regras de integridade do banco (<code>CONSTRAINTS</code>, <code>FOREIGN KEYS</code>, ou regras de <code>TRIGGERS</code>).</p>
```
```ad-quote
title:
<p align="justify">Exemplo: Nosso Trigger <code>TRG_Impede_Diminuir_CR</code> é uma regra de consistência. Se uma transação tentar diminuir o CR de um aluno, o Trigger falha, força um <code>ROLLBACK</code> (Atomicidade) e garante que o banco permaneça em um estado VÁLIDO (Consistência).</p>
```
````

````ad-quote
title:
##### **I ) -** ISOLATION - Isolamento

```ad-quote
title:
<p align="justify">É a propriedade da "BOLHA" (o coração da concorrência).</p>
```
```ad-quote
title:
<p align="justify">Garante que transações concorrentes (executando ao mesmo tempo) não interfiram umas nas outras. Para a Transação A, deve parecer que ela é a ÚNICA operação rodando no banco de dados naquele momento. O SGBD cria uma "bolha" de isolamento ao redor dela.</p>
```
````

````ad-quote
title:
##### **D ) -** DURABILITY - Durabilidade

```ad-quote
title:
<p align="justify">É a propriedade do "SALVO PARA SEMPRE".</p>
```
```ad-quote
title:
<p align="justify">Uma vez que uma transação é confirmada (<code>COMMIT</code>), suas mudanças são permanentes e devem sobreviver a qualquer falha subsequente, como uma queda de energia ou um crash do sistema. O SGBD garante isso escrevendo os resultados em logs de transação antes de confirmar.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - A Vida de uma Transação: <code>COMMIT</code> e <code>ROLLBACK</code>

```ad-quote
title:
<p align="justify">Na prática, você controla uma transação com estes comandos:</p>
```
```ad-quote
title:
###### **BEGIN TRANSACTION**
```
```ad-quote
title:
<p align="justify">Inicia a transação. Todas as operações seguintes estão "na bolha".</p>
```
```ad-quote
title:
###### **O Trabalho**
```
```ad-quote
title:
<p align="justify"><code>UPDATE Alunos SET Status = 'Inativo' WHERE ID_Aluno = 2;</code></p>
```
```ad-quote
title:
<p align="justify"><code>INSERT INTO Tabela_Log (Aviso) VALUES ('Aluno 2 inativado');</code></p>
```
```ad-quote
title:
###### **COMMIT**
```
```ad-quote
title:
<p align="justify">Confirma permanentemente (Durabilidade) todas as operações. O <code>UPDATE</code> E o <code>INSERT</code> são salvos. A transação termina.</p>
```
```ad-quote
title:
###### **ROLLBACK**
```
```ad-quote
title:
<p align="justify">Descarta TODAS as operações desde o <code>BEGIN</code>. O <code>UPDATE</code> E o <code>INSERT</code> são desfeitos (Atomicidade). O banco volta a ser como era antes. A transação termina.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - O Problema da Concorrência 

```ad-quote
title:
<p align="justify">Quando o Isolamento (a bolha) falha, coisas ruins acontecem. O SGBD precisa gerenciar o acesso aos dados para evitar três anomalias clássicas:</p>
```
```ad-quote
title: 

| ID | Nome | Departamento | Salario |
| :--- | :--- | :--- | :--- |
| 10 | Ana | Vendas | 3000 |
| 20 | Bruno | TI | 5000 |
| 30 | Carla | Vendas | 3200 |

```
````

````ad-quote
title:
##### **A ) -** Dirty Read 

```ad-quote
title:
<p align="justify">A Transação A lê dados que a Transação B modificou, mas que a B AINDA NÃO DEU <code>COMMIT</code>.</p>
```
```ad-quote
title:
<p align="justify">O Perigo: A Transação B dá <code>ROLLBACK</code>. Agora, a Transação A tomou decisões baseadas em dados "fantasmas" que nunca existiram oficialmente.</p>
```
```ad-quote
title: 
| Transação 1 (T1) | Transação 2 (T2) | Estado do Banco (Visão da T1) |
| :--- | :--- | :--- |
| `START TRANSACTION;` | | |
| | `START TRANSACTION;` | |
| | `UPDATE Funcionarios SET Salario = 9999 WHERE ID = 10;` | *(T2 muda o salário, mas sem commit)* |
| `SELECT * FROM Funcionarios WHERE ID = 10;` | | `(10, 'Ana', 'Vendas', 9999)` |
| | `ROLLBACK;` | *(T2 desfaz a mudança. Salário volta a 3000)* |
| *... (T1 usa o salário de 9999 para um cálculo) ...* | | |
| `COMMIT;` | | |

```

```ad-quote
title: 
<p align="justify">Problema: A T1 baseou suas operações em um salário de 9999 que foi posteriormente desfeito (NUNCA FOI CONFIRMADO no banco).</p>
```

````

````ad-quote
title:
##### **B ) -** Non-Repeatable Read 

```ad-quote
title:
<p align="justify">A Transação A lê uma linha. A Transação B <code>UPDATE</code> (ou <code>DELETE</code>) ESSA MESMA LINHA e dá <code>COMMIT</code>. A Transação A lê a mesma linha novamente e o valor MUDOU (ou sumiu).</p>
```
```ad-quote
title:
<p align="justify">O Perigo: A Transação A tem dados inconsistentes dentro de sua própria execução (ex: um relatório onde o total muda no meio do cálculo).</p>
```
```ad-quote
title:
| Transação 1 (T1) | Transação 2 (T2) | Estado do Banco (Visão da T1) |
| :--- | :--- | :--- |
| `START TRANSACTION;` | | |
| `SELECT * FROM Funcionarios WHERE ID = 10;` | | `(10, 'Ana', 'Vendas', 3000)` |
| | `START TRANSACTION;` | |
| | `UPDATE Funcionarios SET Salario = 3500 WHERE ID = 10;` | |
| | `COMMIT;` | *(Mudança CONFIRMADA. Salário agora é 3500)* |
| *... (T1 continua processando) ...* | | |
| `SELECT * FROM Funcionarios WHERE ID = 10;` | | `(10, 'Ana', 'Vendas', 3500)` |
| `COMMIT;` | | |

```

```ad-quote
title:
<p align="justify">Problema: A T1 leu a MESMA linha (ID 10) duas vezes e viu valores diferentes (Salário 3000 e depois 3500).</p>
```

````

````ad-quote
title:
##### **C ) -** Phantom Read 

```ad-quote
title:
<p align="justify">A Transação A faz uma consulta com <code>WHERE</code> (ex: <code>SELECT COUNT(*) FROM Funcionarios WHERE Departamento='Vendas'</code>). A Transação B <code>INSERT</code> uma NOVA linha que satisfaz essa condição (um novo funcionário em 'Vendas') e dá <code>COMMIT</code>.</p>
```
```ad-quote
title:
<p align="justify">O Perigo: A Transação A executa a MESMA consulta de <code>COUNT</code> novamente e o número MUDOU. Uma linha "fantasma" apareceu.</p>
```
```ad-quote
title: 
| Transação 1 (T1) | Transação 2 (T2) | Estado do Banco (Visão da T1) |
| :--- | :--- | :--- |
| `START TRANSACTION;` | | |
| `SELECT * FROM Funcionarios WHERE Departamento = 'Vendas';` | | `(10, 'Ana', ...)`<br/>`(30, 'Carla', ...)`<br/>*(Total: 2 linhas)* |
| | `START TRANSACTION;` | |
| | `INSERT INTO Funcionarios (ID, 40, 'David', 'Vendas', 2900);` | |
| | `COMMIT;` | *(Mudança CONFIRMADA. Há um novo vendedor)* |
| *... (T1 continua processando) ...* | | |
| `SELECT * FROM Funcionarios WHERE Departamento = 'Vendas';` | | `(10, 'Ana', ...)`<br/>`(30, 'Carla', ...)`<br/>`(40, 'David', ...)`<br/>*(Total: 3 linhas)* |
| `COMMIT;` | | |
```
```ad-quote
title:
<p align="justify">Problema: A T1 executou a MESMA consulta (<code>WHERE Departamento = 'Vendas'</code>) duas vezes e o NÚMERO de linhas retornadas mudou. A linha 40 ('David') é a "linha fantasma".</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - A Solução: Bloqueios - Locks - e Níveis de Isolamento

```ad-quote
title:
<p align="justify">Para prevenir essas anomalias, o SGBD usa BLOQUEIOS - LOCKS.</p>
```
```ad-quote
title:
<p align="justify">Pense em um "lock" como um semáforo. Quando uma transação precisa modificar uma linha, ela coloca um Lock Exclusivo (X) nela. NENHUMA outra transação pode ler ou escrever nessa linha até que a primeira transação termine (<code>COMMIT</code> ou <code>ROLLBACK</code>) e libere o "lock".</p>
```
```ad-quote
title:
<p align="justify">O DBA pode "afinar" o quão agressivo o SGBD é com os "locks" usando NÍVEIS DE ISOLAMENTO. É um "dial" que troca performance por consistência.</p>
````

````ad-quote
title:
##### **A ) -** READ UNCOMMITTED

```ad-quote
title:
<p align="justify">O nível MAIS RÁPIDO e MAIS PERIGOSO. Não usa "locks" de leitura. Permite todas as anomalias (incluindo Leitura Suja).</p>
```
````

````ad-quote
title:
##### **B ) -** READ COMMITTED

```ad-quote
title:
<p align="justify">O padrão na maioria dos SGBDs (PostgreSQL, SQL Server). Evita Leitura Suja. A transação só lê dados que já foram "commitados". (Ainda permite leituras não repetíveis e fantasmas).</p>
```
````

````ad-quote
title:
##### **C ) -** REPEATABLE READ

```ad-quote
title:
<p align="justify">Mais rigoroso. Garante que, se você ler a mesma linha duas vezes, ela será a mesma. Evita Leituras Não Repetíveis. (Ainda pode permitir Leitura Fantasma).</p>
```
````

````ad-quote
title:
##### **D ) -** SERIALIZABLE

```ad-quote
title:
<p align="justify">O nível MÁXIMO e MAIS LENTO. Evita TODAS as anomalias. Ele garante (com "locks" pesados) que o resultado das transações concorrentes é o mesmo como se elas tivessem sido executadas uma após a outra (serialmente).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Conclusão

```ad-quote
title:
<p align="justify">Gerenciamento de Concorrência é a arte de balancear duas necessidades opostas:</p>
```

```ad-quote
title:
###### **PERFORMANCE:**
```

```ad-quote
title:
Deixar muitas transações rodarem ao mesmo tempo (Nível de Isolamento Baixo).</p>
```

```ad-quote
title:
###### **CONSISTÊNCIA:**
```

```ad-quote
title:
Garantir que os dados estejam 100% corretos e isolados (Nível de Isolamento Alto).</p>
```
```ad-quote
title:
<p align="justify">As propriedades ACID são a promessa fundamental que um SGBD faz para proteger seus dados, e os Níveis de Isolamento são como você configura os detalhes dessa promessa.</p>
```
````

---