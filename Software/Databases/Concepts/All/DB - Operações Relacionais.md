---
banner: "![[Pasted image 20250915211800.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Exemplos de Operadores de Álgebra Relacional
```ad-quote
title:
<p align="justify">A Álgebra Relacional é uma linguagem de consulta formal, procedural, que utiliza um conjunto de operadores para realizar consultas em um banco de dados relacional. Cada operador recebe uma ou mais relações (tabelas) como entrada e produz uma nova relação como resultado. A seguir, são apresentados exemplos práticos para os operadores fundamentais.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Seleção (σ - Sigma)
```ad-quote
title:
<p align="justify">Este operador filtra as tuplas (linhas) de uma relação que satisfazem uma determinada condição.</p>
```
```ad-quote
title:
###### **Exemplo 1: Selecionar produtos com preço acima de 50.00**
```
```ad-quote
title:
Tabela de Entrada: Produtos

| ID_Produto | Nome | Categoria | Preço |
| :--- | :--- | :--- | :--- |
| 101 | Teclado | Periférico | 150.00 |
| 102 | Mouse | Periférico | 45.00 |
| 103 | Monitor | Periférico | 750.00 |
| 104 | Cadeira | Mobiliário | 49.50 |

```
```ad-quote
title:
Operação: σ_{Preço > 50.00}(Produtos)
```

```ad-quote
title:

Tabela Resultante:

| ID_Produto | Nome | Categoria | Preço |
| :--- | :--- | :--- | :--- |
| 101 | Teclado | Periférico | 150.00 |
| 103 | Monitor | Periférico | 750.00 |
```
```ad-quote
title:
###### **Exemplo 2: Selecionar alunos do curso de 'Engenharia'**
```
```ad-quote
title:

Tabela de Entrada: Alunos

| ID_Aluno | Nome | Curso | Ano |
| :--- | :--- | :--- | :--- |
| 1 | Ana | Engenharia | 3 |
| 2 | Bruno | Direito | 2 |
| 3 | Carla | Engenharia | 5 |
| 4 | Daniel | Medicina | 3 |

```

```ad-quote
title:
Operação: σ_{Curso = 'Engenharia'}(Alunos)
```

```ad-quote
title:
Tabela Resultante:

| ID_Aluno | Nome | Curso | Ano |
| :--- | :--- | :--- | :--- |
| 1 | Ana | Engenharia | 3 |
| 3 | Carla | Engenharia | 5 |
```
```ad-quote
title:
###### **Exemplo 3: Selecionar funcionários do departamento de 'Vendas' com salário superior a 4000**
```
```ad-quote
title:
Tabela de Entrada: Funcionarios

| ID_Func | Nome | Departamento | Salario |
| :--- | :--- | :--- | :--- |
| 55 | Eliana | Vendas | 4200 |
| 56 | Felipe | T.I. | 6000 |
| 57 | Gisele | Vendas | 3800 |
| 58 | Heitor | Vendas | 5500 |

```
```ad-quote
title:
Operação: σ_{Departamento = 'Vendas' ∧ Salario > 4000}(Funcionarios)
```
```ad-quote
title:
Tabela Resultante:

| ID_Func | Nome | Departamento | Salario |
| :--- | :--- | :--- | :--- |
| 55 | Eliana | Vendas | 4200 |
| 58 | Heitor | Vendas | 5500 |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Projeção (π - Pi)
```ad-quote
title:
<p align="justify">Este operador seleciona um subconjunto de atributos (colunas) de uma relação, eliminando tuplas duplicadas no resultado.</p>
```
```ad-quote
title:
###### **Exemplo 1: Listar apenas o nome e o preço dos produtos**
```
```ad-quote
title:
Tabela de Entrada: Produtos

| ID_Produto | Nome | Categoria | Preço |
| :--- | :--- | :--- | :--- |
| 101 | Teclado | Periférico | 150.00 |
| 102 | Mouse | Periférico | 45.00 |
| 103 | Monitor | Periférico | 750.00 |
```
```ad-quote
title:
Operação: π_{Nome, Preço}(Produtos)
```
```ad-quote
title:
Tabela Resultante:

| Nome | Preço |
| :--- | :--- |
| Teclado | 150.00 |
| Mouse | 45.00 |
| Monitor | 750.00 |
```
```ad-quote
title:
###### **Exemplo 2: Listar todos os cursos únicos oferecidos**
```
```ad-quote
title:
Tabela de Entrada: Alunos

| ID_Aluno | Nome | Curso | Ano |
| :--- | :--- | :--- | :--- |
| 1 | Ana | Engenharia | 3 |
| 2 | Bruno | Direito | 2 |
| 3 | Carla | Engenharia | 5 |
| 4 | Daniel | Direito | 1 |
```
```ad-quote
title:
Operação: π_{Curso}(Alunos)
```
```ad-quote
title:
Tabela Resultante (note a remoção de duplicatas):

| Curso |
| :--- |
| Engenharia |
| Direito |
```
```ad-quote
title:
###### **Exemplo 3: Obter uma lista de departamentos existentes**
```
```ad-quote
title:
Tabela de Entrada: Funcionarios

| ID_Func | Nome | Departamento | Salario |
| :--- | :--- | :--- | :--- |
| 55 | Eliana | Vendas | 4200 |
| 56 | Felipe | T.I. | 6000 |
| 57 | Gisele | Vendas | 3800 |
| 58 | Heitor | Marketing | 5500 |
```
```ad-quote
title:
Operação: π_{Departamento}(Funcionarios)
```
```ad-quote
title:
Tabela Resultante:

| Departamento |
| :--- |
| Vendas |
| T.I. |
| Marketing |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - União (∪)
```ad-quote
title:
<p align="justify">Combina as tuplas de duas relações com esquemas compatíveis (mesmo número e tipo de atributos).</p>
```
```ad-quote
title:
###### **Exemplo 1: Unir listas de funcionários de duas filiais**
```
```ad-quote
title:
Tabela 1: Funcionarios_SP

| ID_Func | Nome |
| :--- | :--- |
| 10 | João |
| 12 | Maria |

Tabela 2: Funcionarios_RJ

| ID_Func | Nome |
| :--- | :--- |
| 21 | Pedro |
| 10 | João |
```
```ad-quote
title:
Operação: Funcionarios_SP ∪ Funcionarios_RJ
```
```ad-quote
title:
Tabela Resultante (a tupla duplicada de João é removida):

| ID_Func | Nome |
| :--- | :--- |
| 10 | João |
| 12 | Maria |
| 21 | Pedro |
```
```ad-quote
title:
###### **Exemplo 2: Consolidar produtos ativos e inativos**
```
```ad-quote
title:
Tabela 1: Produtos_Ativos

| ID_Prod | Nome |
| :--- | :--- |
| A1 | Notebook |
| A2 | Celular |

Tabela 2: Produtos_Inativos

| ID_Prod | Nome |
| :--- | :--- |
| D5 | Tablet |
| D8 | Câmera |
```
```ad-quote
title:
Operação: Produtos_Ativos ∪ Produtos_Inativos
```
```ad-quote
title:
Tabela Resultante:

| ID_Prod | Nome |
| :--- | :--- |
| A1 | Notebook |
| A2 | Celular |
| D5 | Tablet |
| D8 | Câmera |
```
```ad-quote
title:
###### **Exemplo 3: Unir clientes de diferentes categorias**
```
```ad-quote
title:
Tabela 1: Clientes_Premium

| ID_Cli | Nome | Cidade |
| :--- | :--- | :--- |
| 1 | Ana | São Paulo |

Tabela 2: Clientes_Standard

| ID_Cli | Nome | Cidade |
| :--- | :--- | :--- |
| 2 | Bruno | Recife |
| 3 | Carla | Curitiba |
```
```ad-quote
title:
Operação: Clientes_Premium ∪ Clientes_Standard
```
```ad-quote
title:
Tabela Resultante:

| ID_Cli | Nome | Cidade |
| :--- | :--- | :--- |
| 1 | Ana | São Paulo |
| 2 | Bruno | Recife |
| 3 | Carla | Curitiba |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Diferença de Conjuntos (-)
```ad-quote
title:
<p align="justify">Retorna as tuplas que estão na primeira relação mas não estão na segunda. Os esquemas devem ser compatíveis.</p>
```
```ad-quote
title:
###### **Exemplo 1: Encontrar alunos matriculados que não pegaram livros**
```
```ad-quote
title:
Tabela 1: Alunos_Matriculados

| ID_Aluno | Nome |
| :--- | :--- |
| 101 | Bia |
| 102 | Caio |
| 103 | Duda |

Tabela 2: Alunos_Com_Livros

| ID_Aluno | Nome |
| :--- | :--- |
| 102 | Caio |
```
```ad-quote
title:
Operação: Alunos_Matriculados - Alunos_Com_Livros
```
```ad-quote
title:
Tabela Resultante:

| ID_Aluno | Nome |
| :--- | :--- |
| 101 | Bia |
| 103 | Duda |
```
```ad-quote
title:
###### **Exemplo 2: Identificar produtos que estão no catálogo mas não no estoque**
```
```ad-quote
title:
Tabela 1: Catalogo_Produtos

| ID_Prod |
| :--- |
| P01 |
| P02 |
| P03 |

Tabela 2: Estoque

| ID_Prod |
| :--- |
| P01 |
| P03 |
```
```ad-quote
title:
Operação: Catalogo_Produtos - Estoque
```
```ad-quote
title:
Tabela Resultante:

| ID_Prod |
| :--- |
| P02 |
```
```ad-quote
title:
###### **Exemplo 3: Clientes do ano passado que não compraram este ano**
```
```ad-quote
title:
Tabela 1: Clientes_2024

| ID_Cliente |
| :--- |
| 5 |
| 8 |
| 12 |
| 15 |

Tabela 2: Clientes_2025

| ID_Cliente |
| :--- |
| 8 |
| 15 |
| 21 |
```
```ad-quote
title:
Operação: Clientes_2024 - Clientes_2025
```
```ad-quote
title:
Tabela Resultante:

| ID_Cliente |
| :--- |
| 5 |
| 12 |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Produto Cartesiano (×)
```ad-quote
title:
<p align="justify">Combina cada tupla da primeira relação com cada tupla da segunda.</p>
```
```ad-quote
title:
###### **Exemplo 1: Combinar todos os alunos com todas as disciplinas disponíveis**
```
```ad-quote
title:
Tabela 1: Alunos

| Nome_Aluno |
| :--- |
| Lucas |
| Laura |

Tabela 2: Disciplinas

| Nome_Disciplina |
| :--- |
| Matemática |
| História |
```
```ad-quote
title:
Operação: Alunos × Disciplinas
```
```ad-quote
title:
Tabela Resultante:

| Nome_Aluno | Nome_Disciplina |
| :--- | :--- |
| Lucas | Matemática |
| Lucas | História |
| Laura | Matemática |
| Laura | História |
```
```ad-quote
title:
###### **Exemplo 2: Gerar todas as variações de um produto (tamanho e cor)**
```
```ad-quote
title:
Tabela 1: Tamanhos

| Tamanho |
| :--- |
| P |
| M |

Tabela 2: Cores

| Cor |
| :--- |
| Azul |
| Vermelho |
| Preto |
```
```ad-quote
title:
Operação: Tamanhos × Cores
```
```ad-quote
title:
Tabela Resultante:

| Tamanho | Cor |
| :--- | :--- |
| P | Azul |
| P | Vermelho |
| P | Preto |
| M | Azul |
| M | Vermelho |
| M | Preto |
```
```ad-quote
title:
###### **Exemplo 3: Combinar fornecedores com possíveis centros de distribuição**
```
```ad-quote
title:
Tabela 1: Fornecedores

| ID_Forn | Nome_Forn |
| :--- | :--- |
| F1 | Acme |
| F2 | Logi |

Tabela 2: Centros

| ID_Centro | Cidade |
| :--- | :--- |
| CD1 | Campinas |
| CD2 | Santos |
```
```ad-quote
title:
Operação: Fornecedores × Centros
```
```ad-quote
title:
Tabela Resultante:

| ID_Forn | Nome_Forn | ID_Centro | Cidade |
| :--- | :--- | :--- | :--- |
| F1 | Acme | CD1 | Campinas |
| F1 | Acme | CD2 | Santos |
| F2 | Logi | CD1 | Campinas |
| F2 | Logi | CD2 | Santos |
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Renomeação (ρ - Rho)
```ad-quote
title:
<p align="justify">Muda o nome de uma relação e/ou de seus atributos.</p>
```
```ad-quote
title:
###### **Exemplo 1: Renomear uma tabela para maior clareza**
```
```ad-quote
title:
Tabela de Entrada: Func

| id | nome |
| :--- | :--- |
| 1 | Ana |
```
```ad-quote
title:
Operação: ρ_{Funcionarios}(Func)
```
```ad-quote
title:
<p align="justify">Descrição: A tabela Func passa a ser referenciada como Funcionarios. O conteúdo e o nome das colunas permanecem os mesmos.</p>
```
```ad-quote
title:
###### **Exemplo 2: Renomear os atributos de uma tabela**
```
```ad-quote
title:
Tabela de Entrada: PROD

| cod | descr | val |
| :--- | :--- | :--- |
| 101 | Caneta | 1.50 |
```
```ad-quote
title:
Operação: ρ_{Produtos(Codigo, Descricao, Valor)}(PROD)
```
```ad-quote
title:
Tabela Resultante (Produtos):

| Codigo | Descricao | Valor |
| :--- | :--- | :--- |
| 101 | Caneta | 1.50 |
```
```ad-quote
title:
###### **Exemplo 3: Renomear para realizar uma auto-junção (junção da tabela com ela mesma)**
```
```ad-quote
title:
Tabela de Entrada: Empregados

| ID_Emp | Nome | ID_Super |
| :--- | :--- | :--- |
| 1 | Beatriz | 2 |
| 2 | Carlos | NULL |
| 3 | Davi | 2 |
```
```ad-quote
title:
Operação: ρ_{Funcionario}(Empregados) e ρ_{Supervisor}(Empregados)
```
```ad-quote
title:
<p align="justify">Descrição: Para descobrir o nome do supervisor de cada empregado, precisaríamos comparar a coluna ID_Super de uma cópia da tabela com a coluna ID_Emp de outra. A renomeação é essencial para evitar ambiguidade. Uma operação de junção posterior usaria esses novos nomes, por exemplo: π_{Funcionario.Nome, Supervisor.Nome} (Funcionario ⨝_{Funcionario.ID_Super = Supervisor.ID_Emp} Supervisor).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">Em suma, os operadores da Álgebra Relacional - Seleção, Projeção, União, Diferença, Produto Cartesiano e Renomeação - formam a base para a manipulação e consulta de dados em sistemas de banco de dados relacionais. Compreender o funcionamento de cada um através de exemplos práticos é fundamental para construir consultas complexas e eficientes, garantindo a extração precisa da informação desejada a partir das relações existentes.</p>
```
````

---