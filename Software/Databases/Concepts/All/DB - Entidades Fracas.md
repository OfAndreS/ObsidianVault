
---

````ad-quote
title:

##### **Intro )** - Entidades Fracas no Modelo Entidade-Relacionamento
```ad-quote
title:
<p align="justify">No universo da modelagem de dados através do Modelo Entidade-Relacionamento (MER), as Entidades Fracas representam um conceito fundamental para a correta estruturação de bancos de dados. Diferentemente das entidades fortes, que possuem existência independente, uma entidade fraca é aquela que depende da existência de outra entidade, denominada entidade forte ou proprietária, para ser identificada unicamente.</p>
```
```ad-quote
title:
<p align="justify">Em outras palavras, uma entidade fraca não possui atributos suficientes para formar uma chave primária por si só. Sua identificação é estabelecida através de um relacionamento especial com sua entidade forte.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Características Fundamentais de uma Entidade Fraca

```ad-quote
title:
<p align="justify">Para compreender plenamente o papel das entidades fracas, é crucial conhecer suas características distintivas.</p>
```

```ad-quote
title:

|Característica&nbsp; | Definição&nbsp; |
| :--- | :--- |
|**Dependência de Existência**|A principal característica é que uma instância de uma entidade fraca não pode existir no banco de dados sem a correspondente instância da entidade forte à qual está associada. Se a entidade forte for removida, todas as entidades fracas dependentes dela também devem ser eliminadas.|
|**Ausência de Chave Primária Completa**|A entidade fraca não possui um conjunto de atributos que, isoladamente, possa identificar unicamente cada uma de suas ocorrências. Ela possui um Discriminador (ou chave parcial), que é um conjunto de atributos que permite distinguir as entidades fracas relacionadas a uma mesma entidade forte.|
|**Relacionamento Identificador**|A conexão entre uma entidade fraca e sua entidade forte é chamada de Relacionamento Identificador. Este relacionamento é crucial, pois é através dele que a entidade fraca "empresta" a chave primária da entidade forte para compor a sua própria chave primária.|
|**Participação Total**|A entidade fraca sempre possui Participação Total no relacionamento identificador. Isso significa que toda e qualquer instância da entidade fraca deve, obrigatoriamente, estar associada a uma instância da entidade forte.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - A Chave Primária da Entidade Fraca

```ad-quote
title:
<p align="justify">A chave primária de uma entidade fraca é uma chave composta, formada pela chave primária da entidade forte (que atua como chave estrangeira na entidade fraca) e pelo discriminador da própria entidade fraca.</p>
```

```ad-quote
title:
###### **Fórmula da Chave Primária da Entidade Fraca:**
```

```ad-quote
title:
<p align="center">Chave Primária (Entidade Fraca) = Chave Primária (Entidade Forte) + Discriminador (Entidade Fraca)</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Notação em Diagramas Entidade-Relacionamento (DER)

```ad-quote
title:
<p align="justify">Nos Diagramas Entidade-Relacionamento, as entidades fracas e seus relacionamentos identificadores possuem uma notação específica para diferenciá-los dos componentes fortes.</p>
```

```ad-quote
title:

|Componente&nbsp; | Representação&nbsp; |
| :--- | :--- |
|**Entidade Fraca**|É representada por um retângulo com linha dupla.|
|**Relacionamento Identificador**|É representado por um losango com linha dupla.|
|**Discriminador (Chave Parcial)**|O atributo ou conjunto de atributos que atua como discriminador é geralmente sublinhado com uma linha pontilhada ou tracejada.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Exemplo Prático: Funcionários e Dependentes

```ad-quote
title:
<p align="justify">Um dos exemplos mais clássicos para ilustrar o conceito de entidade fraca é o relacionamento entre Funcionário e Dependente.</p>
```

```ad-quote
title:

|Componente&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|**Entidade Forte**|`FUNCIONÁRIO`, com a chave primária `id_funcionario`.|
|**Entidade Fraca**|`DEPENDENTE`. Um dependente não pode existir sem um funcionário.|
|**Atributos de DEPENDENTE**|`nome_dependente`, `data_nascimento`, `parentesco`.|

```

```ad-quote
title:
<p align="justify">Neste cenário, o `nome_dependente` pode não ser único em toda a tabela de dependentes (vários funcionários podem ter filhos chamados "João", por exemplo). No entanto, o `nome_dependente` é suficiente para distinguir os dependentes de um mesmo funcionário. Portanto, `nome_dependente` funciona como o discriminador.</p>
```
```ad-quote
title:
<p align="justify">A chave primária da entidade `DEPENDENTE` seria a combinação de `id_funcionario` (a chave da entidade forte) e `nome_dependente` (o discriminador). Assim, o par (`id_funcionario`, `nome_dependente`) garante a unicidade de cada registro de dependente.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Representação do Exemplo no Diagrama

```bash
      +-----------------+          +------------------+
      |   FUNCIONÁRIO   |          |    DEPENDENTE    |  << Retângulo Duplo
      +-----------------+          +------------------+
      | *id_funcionario |          | _nome_dependente_ |  << Discriminador Sublinhado
      |  nome           |          |  data_nascimento |
      |  ...            |          |  parentesco      |
      +-----------------+          +------------------+
            |                              |
            | 1                          N |
            |                              |
      +------------------+
      |  possui          |  << Losango Duplo
      +------------------+
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Outros Exemplos Comuns

```ad-quote
title:

|Cenário&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|**Prédios e Apartamentos**|Um APARTAMENTO (entidade fraca) não existe sem um PRÉDIO (entidade forte). O número do apartamento serve como discriminador.|
|**Pedidos e Itens de Pedido**|Um ITEM_DE_PEDIDO (entidade fraca) só existe dentro de um PEDIDO (entidade forte). O número do item ou o ID do produto dentro do pedido pode ser o discriminador.|
|**Contas Bancárias e Transações**|Uma TRANSAÇÃO (entidade fraca) está sempre vinculada a uma CONTA_BANCARIA (entidade forte).|

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
<p align="justify">Em resumo, a utilização de entidades fracas é uma técnica essencial na modelagem de dados para representar de forma precisa e íntegra os relacionamentos de dependência de existência que são comuns em sistemas do mundo real. Identificar corretamente essas entidades e seus relacionamentos é um passo crucial para a construção de um banco de dados robusto e confiável.</p>
```
````

---