
---

````ad-quote
title:

##### **Intro )** - A Estrutura da Consistência

```ad-quote
title:
<p align="justify">A Normalização é um processo formal e passo a passo para projetar bancos de dados relacionais de forma a minimizar a redundância de dados e evitar anomalias (problemas de inserção, atualização e exclusão). Cada "Forma Normal" (FN) é um conjunto de regras que uma tabela deve seguir para ser considerada bem projetada até aquele nível. O objetivo é garantir que cada pedaço de informação seja armazenado em um único lugar.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Primeira Forma Normal (1FN)

```ad-quote
title:
<p align="justify"><b>Problema: Atributos Multivalorados</b><br>A violação da 1FN ocorre quando uma única célula da tabela contém múltiplos valores, como uma lista. Isso é chamado de "atributo multivalorado". O problema prático disso é a dificuldade extrema de manipulação e consulta dos dados, tornando quase impossível filtrar ou ordenar por um valor específico dentro dessas listas.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo do Problema:</b><br>Nesta tabela, múltiplos números de telefone são armazenados na mesma célula.</p>

| ID_Cliente | Nome | Telefones |
| :--- | :--- | :--- |
| 1 | Ana Paula | (11) 98765-4321, (11) 2345-6789 |
| 2 | Bruno Costa | (21) 99999-8888 |

```

```ad-quote
title:
<p align="justify"><b>Solução: Garantir a Atomicidade</b><br>A solução é garantir a atomicidade dos dados, ou seja, que cada célula contenha apenas um valor. Para isso, a tabela é decomposta e cada valor da lista é movido para uma nova linha, garantindo que cada registro represente uma única informação atômica.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo da Solução:</b></p>

| ID_Cliente | Nome | Telefone |
| :--- | :--- | :--- |
| 1 | Ana Paula | (11) 98765-4321 |
| 1 | Ana Paula | (11) 2345-6789 |
| 2 | Bruno Costa | (21) 99999-8888 |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Segunda Forma Normal (2FN)

```ad-quote
title:
<p align="justify"><b>Problema: Dependência Parcial</b><br>Ocorre quando uma tabela tem uma chave primária composta e um atributo não-chave depende de apenas uma parte dessa chave. Isso causa redundância e anomalias de atualização (alterar em vários lugares), inserção (não poder adicionar parte da informação) e exclusão (perder dados ao apagar um registro).</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo do Problema:</b><br>A chave primária é (ID_Aluno, ID_Disciplina). No entanto, Nome_Aluno depende apenas de ID_Aluno e Nome_Disciplina depende apenas de ID_Disciplina, gerando repetição de dados.</p>

| ID_Aluno | ID_Disciplina | Nome_Aluno | Nome_Disciplina | Nota |
| :--- | :--- | :--- | :--- | :--- |
| 10 | 101 | Carlos Silva | Matemática | 8.5 |
| 10 | 202 | Carlos Silva | Física | 7.0 |
| 20 | 101 | Maria Luiza | Matemática | 9.0 |

```

```ad-quote
title:
<p align="justify"><b>Solução: Decompor a Tabela</b><br>A solução é decompor a tabela, movendo os atributos que dependem parcialmente da chave para novas tabelas, onde sua determinante se torna a chave primária.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo da Solução:</b><br>Criamos tabelas separadas para Alunos e Disciplinas e mantemos uma Tabela de Relacionamento para as notas.</p>

| ID_Aluno (PK) | Nome_Aluno |
| :--- | :--- |
| 10 | Carlos Silva |
| 20 | Maria Luiza |

| ID_Disciplina (PK) | Nome_Disciplina |
| :--- | :--- |
| 101 | Matemática |
| 202 | Física |

| ID_Aluno (FK) | ID_Disciplina (FK) | Nota |
| :--- | :--- | :--- |
| 10 | 101 | 8.5 |
| 10 | 202 | 7.0 |
| 20 | 101 | 9.0 |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Terceira Forma Normal (3FN)

```ad-quote
title:
<p align="justify"><b>Problema: Dependência Transitiva</b><br>Ocorre quando um atributo não-chave depende de outro atributo não-chave, em vez de depender diretamente da chave primária (Ex: Chave Primária → Atributo A → Atributo B). Isso também gera anomalias.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo do Problema:</b><br>A chave primária é ID_Funcionario. As colunas Nome_Depto e Localizacao_Depto dependem de ID_Depto, que não é a chave. Se a localização do departamento de Vendas mudar, será preciso atualizar múltiplas linhas.</p>

| ID_Funcionario (PK) | Nome_Funcionario | ID_Depto | Nome_Depto | Localizacao_Depto |
| :--- | :--- | :--- | :--- | :--- |
| 1 | João | 10 | Vendas | Prédio A, Sala 101 |
| 2 | Maria | 20 | Marketing | Prédio B, Sala 205 |
| 3 | Pedro | 10 | Vendas | Prédio A, Sala 101 |

```

```ad-quote
title:
<p align="justify"><b>Solução: Eliminar a Dependência Transitiva</b><br>A solução é decompor a tabela, movendo os atributos que dependem de outro atributo não-chave para uma nova tabela.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo da Solução:</b><br>Criamos uma tabela separada para Departamentos e na tabela Funcionarios mantemos apenas a chave estrangeira.</p>

| ID_Depto (PK) | Nome_Depto | Localizacao_Depto |
| :--- | :--- | :--- |
| 10 | Vendas | Prédio A, Sala 101 |
| 20 | Marketing | Prédio B, Sala 205 |

| ID_Funcionario (PK) | Nome_Funcionario | ID_Depto (FK) |
| :--- | :--- | :--- |
| 1 | João | 10 |
| 2 | Maria | 20 |
| 3 | Pedro | 10 |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Forma Normal de Boyce-Codd (FNBC)

```ad-quote
title:
<p align="justify"><b>Problema: Determinantes que não são Superchaves</b><br>A FNBC é uma 3FN mais rigorosa. O problema ocorre em cenários raros onde um atributo ou conjunto de atributos que não é uma superchave determina outro atributo. A regra é: para qualquer dependência A → B, A deve ser uma superchave.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo do Problema:</b><br>A chave primária é (`ID_Aluno`, `Disciplina`). Se cada professor leciona uma única disciplina, temos a dependência `ID_Professor` → `Disciplina`. No entanto, `ID_Professor` sozinho não é uma superchave da tabela, violando a FNBC e causando redundância.</p>

| ID_Aluno | Disciplina | ID_Professor |
| :--- | :--- | :--- |
| 100 | Cálculo | 5 |
| 100 | Física | 7 |
| 200 | Cálculo | 5 |

```

```ad-quote
title:
<p align="justify"><b>Solução: Garantir que todo Determinante seja Superchave</b><br>A solução é decompor a tabela para que em cada dependência funcional, o determinante seja uma superchave em sua respectiva tabela.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo da Solução:</b><br>Separamos a relação entre professor e disciplina da relação entre aluno e professor.</p>

| ID_Professor (PK) | Disciplina |
| :--- | :--- |
| 5 | Cálculo |
| 7 | Física |

| ID_Aluno (FK) | ID_Professor (FK) |
| :--- | :--- |
| 100 | 5 |
| 100 | 7 |
| 200 | 5 |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Quarta Forma Normal (4FN)

```ad-quote
title:
<p align="justify"><b>Problema: Dependência Multivalorada</b><br>Ocorre quando uma tabela armazena dois ou mais fatos independentes com relação "muitos-para-muitos" sobre a mesma entidade. Manter esses fatos na mesma tabela força a criação de um produto cartesiano de registros, gerando enorme redundância e dados inconsistentes.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo do Problema:</b><br>Gerenciar um projeto e dominar uma linguagem são fatos independentes. Para registrar que o funcionário 1 trabalha nos projetos X e Y e domina Python e Java, somos forçados a criar 4 linhas, sugerindo falsas relações (Ex: que ele usa Python especificamente no Projeto X).</p>

| ID_Funcionario | Projeto | Linguagem |
| :--- | :--- | :--- |
| 1 | Projeto X | Python |
| 1 | Projeto X | Java |
| 1 | Projeto Y | Python |
| 1 | Projeto Y | Java |

```

```ad-quote
title:
<p align="justify"><b>Solução: Isolar Dependências Multivaloradas</b><br>A solução é decompor a tabela, isolando cada fato multivalorado independente em sua própria tabela.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo da Solução:</b></p>

| ID_Funcionario (FK) | Projeto |
| :--- | :--- |
| 1 | Projeto X |
| 1 | Projeto Y |

| ID_Funcionario (FK) | Linguagem |
| :--- | :--- |
| 1 | Python |
| 1 | Java |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Quinta Forma Normal (5FN)

```ad-quote
title:
<p align="justify"><b>Problema: Dependência de Junção</b><br>Este é um tipo raro de anomalia. Uma tabela tem uma dependência de junção se ela pode ser decomposta em três ou mais tabelas menores e depois reunida sem perda de dados. Não fazer essa decomposição pode forçar redundância para representar relações cíclicas.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo do Problema:</b><br>Uma regra de negócio diz: se um vendedor está autorizado a vender uma marca E também a vender uma linha de produtos, ele DEVE vender aquela linha para aquela marca. A tabela abaixo representa fatos que poderiam ser decompostos e reconstruídos de forma mais eficiente.</p>

| Vendedor | Marca | Linha_Produto |
| :--- | :--- | :--- |
| Bia | Marca A | Skincare |
| Bia | Marca B | Maquiagem |
| Carlos | Marca A | Skincare |
| Carlos | Marca A | Maquiagem |

```

```ad-quote
title:
<p align="justify"><b>Solução: Decompor em Projeções Mínimas</b><br>A solução é decompor a tabela em suas projeções constituintes mínimas que, quando unidas, recriam a tabela original sem perda.</p>
```

```ad-quote
title:
<p align="justify"><b>Exemplo da Solução:</b><br>A decomposição reflete as regras de negócio subjacentes, armazenando cada fato de forma independente.</p>

| Vendedor | Marca |
| :--- | :--- |
| Bia | Marca A |
| Bia | Marca B |
| Carlos | Marca A |

| Vendedor | Linha_Produto |
| :--- | :--- |
| Bia | Skincare |
| Bia | Maquiagem |
| Carlos | Skincare |
| Carlos | Maquiagem |

| Marca | Linha_Produto |
| :--- | :--- |
| Marca A | Skincare |
| Marca B | Maquiagem |
| Marca A | Maquiagem |

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
<p align="justify">Dominar as Formas Normais é uma habilidade essencial para projetistas de banco de dados. Embora a 3FN ou FNBC seja o padrão para a maioria das aplicações, entender as formas mais altas permite resolver problemas complexos de redundância e integridade. A normalização resulta em bancos de dados mais enxutos, consistentes e fáceis de manter, formando a espinha dorsal de sistemas de informação robustos e escaláveis.</p>
```
````

---