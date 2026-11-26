
---

> [!example] ***New***

---

````ad-quote
title:

##### **Exemplo Prático )** - Sistema de Vendas com Cardinalidades

```ad-quote
title:
<p align="justify">Vamos analisar um sistema de vendas completo com cinco tabelas inter-relacionadas para demonstrar na prática os conceitos de cardinalidade e mapeamento de relacionamentos.</p>
```

```ad-quote
title:
###### **Estrutura do Banco de Dados:**
```

```ad-quote
title:

|Tabela CLIENTE&nbsp; | 
| :--- | 
|Armazena os dados dos clientes|

| id_cliente (PK) | nome | email | telefone | endereco |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Ana Silva | ana.silva@email.com | (84) 98888-1111 | Rua das Flores, 123, Natal |
| 2 | Bruno Costa | bruno.c@email.com | (84) 99999-2222 | Av. Principal, 456, Parnamirim |

```

```ad-quote
title:

|Tabela FUNCIONARIO&nbsp; |
| :--- |
|Armazena os dados dos funcionários|

| id_funcionario (PK) | nome | cargo |
| :--- | :--- | :--- |
| 10 | Carlos Pereira | Vendedor |
| 20 | Sofia Mendes | Gerente de Vendas |

```

```ad-quote
title:

|Tabela PRODUTO&nbsp; | 
| :--- |
|Nosso catálogo de produtos|

| id_produto (PK) | nome_produto | descricao | preco_unitario |
| :--- | :--- | :--- | :--- |
| 100 | Teclado Mecânico RGB | Gamer, ABNT2 | R$ 350,00 |
| 101 | Mouse Sem Fio | Ergonômico, 6 botões | R$ 120,50 |
| 102 | Headset Gamer 7.1 | Com microfone | R$ 410,00 |

```

```ad-quote
title:
###### **Tabelas de Relacionamento:**
```

```ad-quote
title:

|Tabela PEDIDO&nbsp; | 
| :--- |
|O registro de cada compra, ligando cliente e funcionário|

| id_pedido (PK) | data_pedido | valor_total | id_cliente (FK) | id_funcionario (FK) |
| :--- | :--- | :--- | :--- | :--- |
| 1001 | 2025-09-08 | R$ 470,50 | 1 | 10 |
| 1002 | 2025-09-08 | R$ 920,50 | 2 | 20 |

```

```ad-quote
title:

|Tabela contém (item_pedido)&nbsp; | Descrição&nbsp; |
| :--- |
|Detalha os itens presentes em cada pedido||

| id_pedido (FK) | id_produto (FK) | quantidade | preco_momento |
| :------------- | :-------------- | :--------- | :------------ |
| 1001           | 100             | 1          | R$ 350,00     |
| 1001           | 101             | 1          | R$ 120,50     |
| 1002           | 102             | 2          | R$ 400,00     |
| 1002           | 101             | 1          | R$ 120,50     |

```

```ad-quote
title:
###### **Análise de Cardinalidades:**
```

```ad-quote
title:

|Relacionamento&nbsp; | Tipo&nbsp; | Mapeamento&nbsp; |
| :--- | :--- | :--- |
|**CLIENTE - PEDIDO**|1:N|Chave primária de CLIENTE migra para PEDIDO|
|**FUNCIONARIO - PEDIDO**|1:N|Chave primária de FUNCIONARIO migra para PEDIDO|
|**PEDIDO - PRODUTO**|N:M|Tabela associativa CONTÉM com chaves de ambas|

```

```ad-quote
title:
###### **Como Ler as Relações - Exemplo do Pedido 1001:**
```

```ad-quote
title:
**1 ) - O Pedido:** 
- Localizamos o id_pedido = 1001 na tabela PEDIDO.
  
**2 ) - Cliente:** 
- O id_cliente 1 referencia Ana Silva na tabela CLIENTE.
  
**3 ) - Funcionário:** 
- O id_funcionario 10 referencia Carlos Pereira na tabela FUNCIONARIO.
  
**4 ) - Itens:** 
- Buscamos na tabela CONTÉM todos os itens com id_pedido 1001.
  
**5 ) - Produtos:** 
- Os ids 100 e 101 correspondem a Teclado Mecânico e Mouse Sem Fio na tabela PRODUTO.
  
**6 ) - Valor Total:** 
- O campo valor_total de R$ 470,50 resulta da soma (1 * R$ 350,00) + (1 * R$ 120,50).
```

```ad-quote
title:
<p align="justify">Esta estrutura relacional demonstra na prática a aplicação dos conceitos de cardinalidade, permitindo que qualquer consulta sobre os pedidos seja respondida através da conexão lógica entre as tabelas mediante chaves primárias e estrangeiras.</p>
```
````

---

> [!example] ***New***

---

````ad-quote
title:
##### **Exemplo Prático )** - Sistema de Consultório Médico

```ad-quote
title:
<p align="justify">Vamos analisar um sistema completo para consultório médico com cinco tabelas inter-relacionadas para demonstrar na prática os conceitos de cardinalidade e mapeamento de relacionamentos no contexto médico.</p>
```

```ad-quote
title:
###### **Estrutura do Banco de Dados:**
```

```ad-quote
title:

|Tabela PACIENTE&nbsp; | 
| :--- | 
|Armazena os dados dos pacientes|

| id_paciente (PK) | nome | data_nascimento | telefone | endereco | historico_medico |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Maria Santos | 1985-03-15 | (84) 98888-7777 | Av. Saúde, 123, Natal | Hipertensão leve |
| 2 | João Oliveira | 1990-07-22 | (84) 99999-8888 | Rua Médica, 456, Parnamirim | Alergia a penicilina |

```

```ad-quote
title:

|Tabela MEDICO&nbsp; |
| :--- |
|Armazena os dados dos médicos|

| id_medico (PK) | nome | especialidade | crm | telefone |
| :--- | :--- | :--- | :--- | :--- |
| 10 | Dra. Carla Silva | Cardiologia | CRM/RN 12345 | (84) 3222-1111 |
| 20 | Dr. Pedro Costa | Ortopedia | CRM/RN 67890 | (84) 3333-2222 |

```

```ad-quote
title:

|Tabela ESPECIALIDADE&nbsp; | 
| :--- |
|Catálogo de especialidades médicas|

| id_especialidade (PK) | nome_especialidade | descricao |
| :--- | :--- | :--- |
| 100 | Cardiologia | Trata doenças do coração e sistema circulatório |
| 101 | Ortopedia | Trata doenças dos ossos, músculos e articulações |
| 102 | Dermatologia | Trata doenças da pele, cabelos e unhas |

```

```ad-quote
title:
###### **Tabelas de Relacionamento:**
```

```ad-quote
title:

|Tabela CONSULTA&nbsp; | 
| :--- |
|O registro de cada consulta, ligando paciente e médico|

| id_consulta (PK) | data_consulta | horario | diagnostico | prescricao | id_paciente (FK) | id_medico (FK) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1001 | 2025-09-10 | 14:30 | Hipertensão controlada | Manter medicamento | 1 | 10 |
| 1002 | 2025-09-10 | 16:00 | Fratura no punho | Gesso por 4 semanas | 2 | 20 |

```

```ad-quote
title:

|Tabela possui (medico_especialidade)&nbsp; | Descrição&nbsp; |
| :--- |
|Relaciona médicos com suas especialidades||

| id_medico (FK) | id_especialidade (FK) |
| :------------- | :--------------------- |
| 10             | 100                    |
| 20             | 101                    |
| 20             | 102                    |

```

```ad-quote
title:
###### **Análise de Cardinalidades:**
```

```ad-quote
title:

|Relacionamento&nbsp; | Tipo&nbsp; | Mapeamento&nbsp; |
| :--- | :--- | :--- |
|**PACIENTE - CONSULTA**|1:N|Chave primária de PACIENTE migra para CONSULTA|
|**MEDICO - CONSULTA**|1:N|Chave primária de MEDICO migra para CONSULTA|
|**MEDICO - ESPECIALIDADE**|N:M|Tabela associativa POSSUI com chaves de ambas|

```

```ad-quote
title:
###### **Como Ler as Relações - Exemplo da Consulta 1001:**
```

```ad-quote
title:
**1 ) - A Consulta:** 
- Localizamos o id_consulta = 1001 na tabela CONSULTA.
  
**2 ) - Paciente:** 
- O id_paciente 1 referencia Maria Santos na tabela PACIENTE.
  
**3 ) - Médico:** 
- O id_medico 10 referencia Dra. Carla Silva na tabela MEDICO.
  
**4 ) - Especialidades do Médico:** 
- Buscamos na tabela POSSUI todas as especialidades com id_medico 10.
  
**5 ) - Especialidade:** 
- O id_especialidade 100 corresponde a Cardiologia na tabela ESPECIALIDADE.
  
**6 ) - Diagnóstico e Prescrição:** 
- Os campos diagnóstico e prescrição contêm as informações médicas da consulta.
```

```ad-quote
title:
<p align="justify">Esta estrutura relacional demonstra na prática a aplicação dos conceitos de cardinalidade em um contexto médico, permitindo que qualquer consulta sobre pacientes, médicos, especialidades e consultas seja respondida através da conexão lógica entre as tabelas mediante chaves primárias e estrangeiras.</p>
```
````

---

> [!example] ***New***

---

````ad-quote
title:
##### **Exemplo Prático )** - Sistema de Gestão de Projetos

```ad-quote
title:
<p align="justify">Vamos analisar um sistema completo para gestão de projetos com cinco tabelas inter-relacionadas para demonstrar na prática os conceitos de cardinalidade e mapeamento de relacionamentos no contexto de gestão empresarial.</p>
```

```ad-quote
title:
###### **Estrutura do Banco de Dados:**
```

```ad-quote
title:

|Tabela CLIENTE&nbsp; | 
| :--- | 
|Armazena os dados dos clientes|

| id_cliente (PK) | nome | telefone | email | endereco |
| :--- | :--- | :--- | :--- | :--- |
| 1 | TechSolutions Ltda | (11) 3333-4444 | contato@techsolutions.com | Av. Paulista, 1000, São Paulo |
| 2 | InovaCorp S.A. | (21) 2222-5555 | projetos@inovacorp.com | Rua do Ouvidor, 50, Rio de Janeiro |

```

```ad-quote
title:

|Tabela DEPARTAMENTO&nbsp; |
| :--- |
|Armazena os departamentos da empresa|

| id_departamento (PK) | nome | descricao | orcamento_anual |
| :--- | :--- | :--- | :--- |
| 10 | TI | Tecnologia da Informação | R$ 500.000,00 |
| 20 | Marketing | Divulgação e Publicidade | R$ 300.000,00 |
| 30 | RH | Recursos Humanos | R$ 250.000,00 |

```

```ad-quote
title:

|Tabela FUNCIONARIO&nbsp; | 
| :--- |
|Armazena os dados dos funcionários|

| id_funcionario (PK) | nome | cargo | salario | id_departamento (FK) |
| :--- | :--- | :--- | :--- | :--- |
| 100 | Ana Silva | Desenvolvedora Sênior | R$ 8.500,00 | 10 |
| 101 | Carlos Oliveira | Analista de Sistemas | R$ 6.200,00 | 10 |
| 102 | Mariana Costa | Gerente de Marketing | R$ 9.800,00 | 20 |
| 103 | Pedro Santos | Recrutador | R$ 5.500,00 | 30 |

```

```ad-quote
title:
###### **Tabelas de Relacionamento:**
```

```ad-quote
title:

|Tabela PROJETO&nbsp; | 
| :--- |
|Registro dos projetos da empresa|

| id_projeto (PK) | nome | descricao | data_inicio | data_prevista | orcamento | id_cliente (FK) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1001 | Sistema de Gestão | Desenvolvimento de ERP | 2025-01-15 | 2025-08-30 | R$ 150.000,00 | 1 |
| 1002 | Campanha Digital | Marketing para novo produto | 2025-02-10 | 2025-05-20 | R$ 80.000,00 | 2 |

```

```ad-quote
title:

|Tabela TAREFA&nbsp; | 
| :--- |
|Detalhamento das tarefas dos projetos|

| id_tarefa (PK) | descricao | status | data_inicio | data_conclusao | prioridade | id_projeto (FK) | id_funcionario_resp (FK) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 5001 | Desenvolvimento do módulo de vendas | Em andamento | 2025-01-20 | 2025-03-15 | Alta | 1001 | 100 |
| 5002 | Design da interface do usuário | Concluída | 2025-01-18 | 2025-02-10 | Média | 1001 | 101 |
| 5003 | Criação de material publicitário | Pendente | 2025-02-15 | 2025-03-30 | Alta | 1002 | 102 |

```

```ad-quote
title:

|Tabela ALOCACAO&nbsp; | Descrição&nbsp; |
| :--- |
|Relaciona funcionários com os projetos em que trabalham||

| id_funcionario (FK) | id_projeto (FK) | horas_semanais | funcao_no_projeto | data_inicio | data_fim |
| :------------- | :-------------- | :--------- | :------------ | :--- | :--- |
| 100 | 1001 | 30 | Desenvolvedor Líder | 2025-01-15 | 2025-08-30 |
| 101 | 1001 | 25 | Desenvolvedor Front-end | 2025-01-15 | 2025-06-15 |
| 102 | 1002 | 20 | Gerente de Campanha | 2025-02-10 | 2025-05-20 |
| 103 | 1001 | 10 | Recrutador do Projeto | 2025-02-01 | 2025-03-01 |

```

```ad-quote
title:
###### **Análise de Cardinalidades:**
```

```ad-quote
title:

|Relacionamento&nbsp; | Tipo&nbsp; | Mapeamento&nbsp; |
| :--- | :--- | :--- |
|**CLIENTE - PROJETO**|1:N|Chave primária de CLIENTE migra para PROJETO|
|**DEPARTAMENTO - FUNCIONARIO**|1:N|Chave primária de DEPARTAMENTO migra para FUNCIONARIO|
|**PROJETO - TAREFA**|1:N|Chave primária de PROJETO migra para TAREFA|
|**FUNCIONARIO - TAREFA**|1:N|Chave primária de FUNCIONARIO migra para TAREFA (como responsável)|
|**FUNCIONARIO - PROJETO**|N:M|Tabela associativa ALOCACAO com chaves de ambas|

```

```ad-quote
title:
###### **Como Ler as Relações - Exemplo do Projeto 1001:**
```

```ad-quote
title:
**1 ) - O Projeto:** 
- Localizamos o id_projeto = 1001 na tabela PROJETO.
  
**2 ) - Cliente:** 
- O id_cliente 1 referencia TechSolutions Ltda na tabela CLIENTE.
  
**3 ) - Tarefas:** 
- Buscamos na tabela TAREFA todas as tarefas com id_projeto 1001.
  
**4 ) - Funcionários Responsáveis:** 
- Os ids 100 e 101 correspondem a Ana Silva e Carlos Oliveira na tabela FUNCIONARIO.
  
**5 ) - Alocações:** 
- Buscamos na tabela ALOCACAO todos os funcionários alocados no projeto 1001.
  
**6 ) - Departamentos:** 
- Os funcionários pertencem aos departamentos com base no id_departamento.
```

```ad-quote
title:
<p align="justify">Esta estrutura relacional demonstra na prática a aplicação dos conceitos de cardinalidade em um sistema de gestão de projetos, permitindo consultas complexas sobre projetos, tarefas, alocações de funcionários e estrutura departamental através da conexão lógica entre as tabelas mediante chaves primárias e estrangeiras.</p>
```
````

---