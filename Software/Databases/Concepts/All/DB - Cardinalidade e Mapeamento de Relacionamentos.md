
---

````ad-quote
title:

##### **Intro )** - Cardinalidade e Mapeamento de Relacionamentos
```ad-quote
title:
<p align="justify">No universo dos bancos de dados relacionais, A Cardinalidade e O Mapeamento de Relacionamentos são conceitos fundamentais que ditam a estrutura e a integridade dos dados. Eles definem como as diferentes entidades de um sistema se conectam e interagem, garantindo que as informações sejam armazenadas de forma lógica, consistente e eficiente.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - O Que é Cardinalidade?

```ad-quote
title:
<p align="justify">A Cardinalidade, em modelagem de dados, refere-se ao número de instâncias de uma entidade que podem ou devem estar associadas a uma instância de outra entidade. Em termos mais simples, ela estabelece as regras de negócio sobre a quantidade de elementos que podem se relacionar. A Cardinalidade é geralmente expressa através de uma notação específica nos diagramas de entidade-relacionamento (DER).</p>
```

```ad-quote
title:
###### **Tipos Essenciais de Cardinalidade:**
```

```ad-quote
title:

|Tipo&nbsp; | Definição&nbsp; | Exemplo |
| :--- | :--- | :--- |
|**Um-para-Um (1:1)**|Uma instância de uma entidade A pode se relacionar com, no máximo, uma instância de uma entidade B, e vice-versa.|Um CIDADÃO possui um único CPF, e um CPF pertence a um único CIDADÃO.|
|**Um-para-Muitos (1:N)**|Uma instância de uma entidade A pode se relacionar com várias instâncias de uma entidade B, mas cada instância de B se relaciona com apenas uma instância de A.|Um CLIENTE pode realizar vários PEDIDOS, mas cada PEDIDO pertence a um único CLIENTE.|
|**Muitos-para-Muitos (N:M)**|Várias instâncias de uma entidade A podem se relacionar com várias instâncias de uma entidade B, e vice-versa.|Um ALUNO pode se matricular em várias DISCIPLINAS, e uma DISCIPLINA pode ter vários ALUNOS matriculados.|

```

```ad-quote
title:
<p align="justify">Além da cardinalidade máxima (1 ou N), também é crucial definir A Cardinalidade Mínima, que indica se o relacionamento é obrigatório (1) ou opcional (0). Por exemplo, um PEDIDO deve ter no mínimo um ITEM (cardinalidade mínima 1), mas um CLIENTE pode não ter feito nenhum PEDIDO ainda (cardinalidade mínima 0).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - O Mapeamento de Relacionamentos: Da Teoria à Prática

```ad-quote
title:
<p align="justify">O Mapeamento de Relacionamentos é o processo de traduzir o modelo conceitual de dados, representado pelo diagrama de entidade-relacionamento (DER), em um modelo lógico, que é a estrutura de tabelas, chaves primárias e chaves estrangeiras de um banco de dados relacional. Cada tipo de cardinalidade possui uma abordagem específica para o mapeamento.</p>
```

```ad-quote
title:
###### **Regras de Mapeamento:**
```

```ad-quote
title:

|Relacionamento&nbsp; | Abordagem de Mapeamento&nbsp; | Exemplo Prático |
| :--- | :--- | :--- |
|**Um-para-Um (1:1)**|A chave primária de uma tabela é adicionada como chave estrangeira na outra. Geralmente, a chave é alocada na entidade de participação opcional para evitar campos nulos.|Pode-se fundir as tabelas CIDADÃO e CPF ou adicionar o ID_CPF na tabela CIDADÃO.|
|**Um-para-Muitos (1:N)**|A chave primária da tabela do lado "um" do relacionamento migra como chave estrangeira para a tabela do lado "muitos".|A chave primária da tabela CLIENTE (ID_Cliente) é adicionada como chave estrangeira na tabela PEDIDOS.|
|**Muitos-para-Muitos (N:M)**|Cria-se uma nova tabela, chamada Tabela Associativa, contendo as chaves primárias de ambas as tabelas originais como chaves estrangeiras.|Para ALUNOS e DISCIPLINAS, cria-se a tabela MATRICULA com as chaves estrangeiras ID_Aluno e ID_Disciplina.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Definindo a Cardinalidade 1:N com Autoquestionamento

```ad-quote
title:
<p align="justify">Vamos utilizar o exemplo clássico das entidades CLIENTES e PEDIDOS para demonstrar o método.</p>
```

```ad-quote
title:
###### **Perguntas-Chave para Cardinalidade 1:N:**
```

```ad-quote
title:

|Direção do Relacionamento&nbsp; | Pergunta&nbsp; | Resposta&nbsp; | Conclusão Lógica |
| :--- | :--- | :--- | :--- |
|**De Cliente para Pedido**|"Um único CLIENTE pode ter quantos PEDIDOS?"|Vários (N)|O relacionamento inicia como 1:N.|
|**De Pedido para Cliente**|"Um único PEDIDO pode pertencer a quantos CLIENTES?"|Apenas um (1)|Confirma-se o relacionamento UM para MUITOS (1:N).|

```

```ad-quote
title:
<p align="justify">Conclusão e Mapeamento: O relacionamento é de UM Cliente para MUITOS Pedidos (1:N). A regra de mapeamento para este tipo é simples: a chave primária do lado "1" (CLIENTES) migra para a tabela do lado "N" (PEDIDOS) como uma chave estrangeira.</p>
```

```ad-quote
title:
###### **Estrutura das Tabelas Mapeadas:**
```

```ad-quote
title:

|Tabela CLIENTES (Lado "1")&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Cliente|INT|PRIMARY KEY|
|Nome|VARCHAR(100)||
|Email|VARCHAR(100)||

|Tabela PEDIDOS (Lado "N")&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Pedido|INT|PRIMARY KEY|
|Data_Pedido|DATE||
|Valor_Total|DECIMAL(10, 2)||
|ID_Cliente|INT|FOREIGN KEY (ref. CLIENTES)|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Definindo a Cardinalidade Mínima (Opcionalidade)

```ad-quote
title:
<p align="justify">Após definir a cardinalidade máxima (1:N), é crucial investigar a cardinalidade mínima, também conhecida como opcionalidade, para refinar a estrutura das tabelas com restrições de integridade.</p>
```

```ad-quote
title:
###### **Perguntas-Chave para Opcionalidade:**
```

```ad-quote
title:

|Foco da Pergunta&nbsp; | Pergunta&nbsp; | Resposta&nbsp; | Conclusão e Impacto |
| :--- | :--- | :--- | :--- |
|**Opcionalidade do Pedido**|"Um CLIENTE pode existir sem PEDIDOS?"|Sim|Participação opcional do PEDIDO (min 0).|
|**Opcionalidade do Cliente**|"Um PEDIDO pode existir sem um CLIENTE?"|Nao|Participação obrigatória do CLIENTE (min 1).|

```

```ad-quote
title:
<p align="justify">Conclusão e Mapeamento: A obrigatoriedade se traduz na restrição NOT NULL na coluna da chave estrangeira. Isso garante que o banco de dados nunca permitirá um pedido sem um cliente válido.</p>
```

```ad-quote
title:
###### **Tabela Refinada com Restrição de Integridade:**
```

```ad-quote
title:

|Tabela PEDIDOS (Refinada)&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Pedido|INT|PRIMARY KEY|
|Data_Pedido|DATE||
|Valor_Total|DECIMAL(10, 2)||
|ID_Cliente|INT|FOREIGN KEY (ref. CLIENTES), NOT NULL|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Identificando e Mapeando Relacionamentos N:M

```ad-quote
title:
<p align="justify">Para relacionamentos mais complexos, o autoquestionamento também é eficaz. Vamos usar o exemplo de ALUNOS e DISCIPLINAS.</p>
```

```ad-quote
title:
###### **Perguntas-Chave para Cardinalidade N:M:**
```

```ad-quote
title:

|Direção do Relacionamento&nbsp; | Pergunta&nbsp; | Resposta&nbsp; | Conclusão Lógica |
| :--- | :--- | :--- | :--- |
|**De Aluno para Disciplina**|"Um ALUNO pode se inscrever em quantas DISCIPLINAS?"|Várias (N)|O relacionamento é identificado como N:M.|
|**De Disciplina para Aluno**|"Uma DISCIPLINA pode ter quantos ALUNOS?"|Várias (M)|Confirma-se o relacionamento MUITOS para MUITOS (N:M).|

```

```ad-quote
title:
<p align="justify">Pergunta sobre Atributos: "Existe informação específica da junção de um ALUNO e uma DISCIPLINA?" Sim, a Nota Final. Isso indica a necessidade de uma tabela associativa para abrigar esse atributo.</p>
```

```ad-quote
title:
###### **Estrutura das Tabelas para N:M:**
```

```ad-quote
title:

|Tabela ALUNOS&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Aluno|INT|PRIMARY KEY|
|Nome_Aluno|VARCHAR(100)||

|Tabela DISCIPLINAS&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Disciplina|INT|PRIMARY KEY|
|Nome_Disciplina|VARCHAR(100)||

|Tabela MATRICULAS (Associativa)&nbsp; | Tipo&nbsp; | Restrição&nbsp; |
| :--- | :--- | :--- |
|ID_Aluno|INT|PRIMARY KEY, FOREIGN KEY (ref. ALUNOS)|
|ID_Disciplina|INT|PRIMARY KEY, FOREIGN KEY (ref. DISCIPLINAS)|
|Nota_Final|DECIMAL(4, 2)||

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
<p align="justify">Em suma, a técnica de autoquestionamento guiado por perguntas específicas sobre quantidade e obrigatoriedade fornece um método claro e infalível para descobrir a cardinalidade e realizar o mapeamento correto das tabelas em um banco de dados relacional, assegurando a integridade e a fidelidade às regras de negócio.</p>
```
````

---