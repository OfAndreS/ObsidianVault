
---

````ad-quote
title:

##### **Intro )** - A Planta Baixa do Banco de Dados

```ad-quote
title:
<p align="justify">O Modelo Entidade-Relacionamento (MER) é uma abordagem de modelagem de dados de alto nível, utilizada para criar um projeto conceitual para um banco de dados. Funciona como a planta baixa de um arquiteto: antes de construir as paredes (tabelas) e instalar a fiação (dados), o MER permite que desenvolvedores, administradores de banco de dados (DBAs) e stakeholders visualizem a estrutura da informação, os objetos de negócio e como eles se conectam. Criado por Peter Chen em 1976, seu principal objetivo é traduzir os requisitos de um sistema em um modelo abstrato e visual, que servirá de base para o projeto lógico e físico do banco de dados.</p>
```
````

![[Pasted image 20250816190236.png]]

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Os Componentes Fundamentais

```ad-quote
title:
<p align="justify">O modelo é construído a partir de três conceitos básicos que representam os dados e suas interações. Compreender cada um deles é o primeiro passo para a criação de um diagrama coeso.</p>
```

```ad-quote
title:

|Componente&nbsp;    | Descrição    |
| --- | --- |
|**Entidade:**|Representa um objeto do mundo real sobre o qual desejamos armazenar informações. Pode ser algo concreto (um `CLIENTE`, um `PRODUTO`) ou abstrato (uma `VENDA`, uma `CONTA`).|
|**Atributo:**|É uma propriedade ou característica que descreve uma entidade. Por exemplo, a entidade `CLIENTE` pode ter os atributos `Nome`, `CPF` e `Data de Nascimento`.|
|**Relacionamento:**|Define uma associação ou interação entre duas ou mais entidades. Por exemplo, um `CLIENTE` **realiza** uma `VENDA`, e uma `VENDA` **contém** `PRODUTOS`.|

```

```ad-quote
title:
###### **Tipos de Atributos:**
- Os atributos podem ser classificados para detalhar ainda mais o modelo.</p>

|Tipo de Atributo&nbsp;    | Descrição    |
| --- | --- |
|**Identificador (ou Chave):**|Um ou mais atributos que identificam unicamente cada ocorrência de uma entidade. Ex: `CPF` para um `CLIENTE`.|
|**Simples vs. Composto:**|Um atributo **simples** é indivisível (ex: `Preço`). Um **composto** pode ser dividido em partes menores (ex: `Endereço`, composto por `Rua`, `Cidade`, `CEP`).|
|**Monovalorado vs. Multivalorado:**|Um atributo **monovalorado** possui apenas um valor (ex: `Data de Nascimento`). Um **multivalorado** pode ter vários valores (ex: `Telefone`).|
|**Derivado:**|Um atributo cujo valor pode ser calculado ou deduzido a partir de outro atributo. Ex: A `Idade` pode ser derivada da `Data de Nascimento`.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Cardinalidade dos Relacionamentos

```ad-quote
title:
<p align="justify">A cardinalidade define o número de ocorrências de uma entidade que podem se relacionar com as ocorrências de outra entidade. É um conceito crucial para definir as regras de negócio do sistema.</p>
```

```ad-quote
title:

|Cardinalidade&nbsp;    | Descrição    | Exemplo |
|---|---|---|
|**Um-para-Um (1:1):**|Cada ocorrência da Entidade A se relaciona com no máximo uma ocorrência da Entidade B, e vice-versa.|Um `MOTORISTA` dirige um único `CAMINHÃO`, e um `CAMINHÃO` é dirigido por um único `MOTORISTA`.|
|**Um-para-Muitos (1:N):**|Cada ocorrência da Entidade A pode se relacionar com várias ocorrências da Entidade B, mas cada ocorrência de B só se relaciona com uma de A.|Uma `MÃE` pode ter muitos `FILHOS`, mas cada `FILHO` tem apenas uma `MÃE`.|
|**Muitos-para-Muitos (N:M):**|Cada ocorrência da Entidade A pode se relacionar com várias ocorrências da Entidade B, e vice-versa.|Um `ALUNO` pode se matricular em muitas `DISCIPLINAS`, e uma `DISCIPLINA` pode ter muitos `ALUNOS` matriculados.|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - O Diagrama Entidade-Relacionamento (DER)

```ad-quote
title:
<p align="justify">O Diagrama Entidade-Relacionamento (DER) é a representação gráfica do Modelo Entidade-Relacionamento. Ele utiliza um conjunto de símbolos padronizados para visualizar as entidades, atributos e relacionamentos, tornando o modelo compreensível para toda a equipe de desenvolvimento.</p>
```

```ad-quote
title:
<p align="justify"><b>Notação de Peter Chen (Clássica):</b></p>

|Elemento&nbsp;    | Símbolo Gráfico    |
| --- | --- |
|**Entidade:**|Retângulo|
|**Relacionamento:**|Losango|
|**Atributo:**|Elipse|
|**Atributo Identificador (Chave):**|Elipse com o nome sublinhado|
|**Atributo Multivalorado:**|Elipse dupla|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Mapeamento para o Modelo Lógico (Relacional)

```ad-quote
title:
<p align="justify">Após a criação do MER/DER, o próximo passo é convertê-lo para um modelo lógico, que no mundo dos SGBDs mais tradicionais é o Modelo Relacional (baseado em tabelas). Este processo, chamado de mapeamento, segue um conjunto de regras bem definidas.</p>
```

```ad-quote
title:

|Regra de Mapeamento&nbsp;    | Descrição    |
| --- | --- |
|**Entidades:**|Cada entidade forte no DER se torna uma tabela no modelo relacional.|
|**Atributos Simples:**|Cada atributo simples se torna uma coluna na tabela correspondente.|
|**Atributo Identificador:**|O atributo identificador da entidade se torna a **Chave Primária (Primary Key)** da tabela.|
|**Relacionamento 1:N:**|A chave primária do lado "1" da relação é adicionada como uma **Chave Estrangeira (Foreign Key)** na tabela do lado "N".|
|**Relacionamento N:M:**|Cria-se uma nova tabela, chamada de tabela associativa ou de junção. Suas colunas de chave primária são as chaves estrangeiras das duas tabelas que participam do relacionamento.|

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
<p align="justify">O Modelo Entidade-Relacionamento é mais do que um simples diagrama; é uma ferramenta estratégica de comunicação e planejamento. Ele força a análise detalhada das regras de negócio, garante que a estrutura do banco de dados atenda aos requisitos do sistema e serve como uma documentação viva do projeto. Dominar o MER é uma habilidade indispensável para qualquer profissional que deseje construir sistemas de informação robustos, consistentes e escaláveis.</p>
```
````

---
