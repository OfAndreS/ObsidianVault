
---

>[!quote] **Definição** 
>Um **byte** é composto por 8 bits e representa uma unidade básica de armazenamento.
>Processadores e sistemas operam em diferentes arquiteturas de bits ***8, 16, 32, 64 bits***
>- influenciando a quantidade de dados que podem ser processados ou endereçados de uma só vez.
##### *O que é um **Bit**?*

>[!quote] **Definição**
> Um **bit** (abreviação de **"binary digit"** ou dígito binário) é a menor unidade de dados em um computador. Ele pode assumir um de dois valores: **0** ou **1**. 
>- Os bits são os blocos de construção fundamentais da computação, e todas as operações e dados no computador são representados por combinações de bits.

>[!quote] **Definição**
> No sistema binário, esses dois valores representam dois estados, que podem ser interpretados de várias formas, como:
>- **0** = Desligado, Falso, Não
>- **1** = Ligado, Verdadeiro, Sim 
##### *O que é um **Byte**?*

>[!quote] **Definição**
>Um **byte** é um conjunto de **8 bits**. 
>
>

>[!quote] **Definição**
>Ele é usado para representar um único caractere (como uma letra, número ou símbolo) em muitos sistemas de codificação, como o **ASCII**. 
>- A razão de usar 8 bits para formar um byte está relacionada à capacidade de armazenar **256 combinações diferentes** (2^8 = 256), o que é suficiente para representar um grande número de caracteres e outros tipos de dados.
##### *Significado de*  ***8, 16, 32 e 64 Bits***

>[!quote] **Definição**
>Esses números referem-se à quantidade de bits que um processador, sistema operacional ou outra tecnologia pode processar simultaneamente ou que uma unidade de dados 

>[!quote] **8 bits**
>**8 bits**: É o tamanho de um byte. Com 8 bits, você pode representar **256 valores diferentes** 
>- (0 a 255 no sistema decimal).

>[!quote] **16 bits**
>**16 bits**: Pode representar **65.536 valores diferentes** (2^16). 
>- Muitas máquinas antigas de 16 bits trabalhavam com unidades de 2 bytes.

>[!quote] **32 bits**
>**32 bits**: Pode representar **4.294.967.296 valores** (2^32). 
>- A arquitetura de computadores de 32 bits foi muito usada nos anos 1990 e 2000. Ela permite que os computadores enderecem até 4 GB de memória.

>[!quote] **64 bits**
>**64 bits**: Pode representar um valor extremamente grande, **18,4 quintilhões de valores** (2^64). 
>  - A arquitetura de 64 bits permite acesso a uma quantidade massiva de memória e é o padrão atual em computadores modernos.

---

>[!tip] ### **Armazenamento no Registro Binário**

---

> [!quote] **Def**  
> Um **registro binário** é uma estrutura de dados que armazena informações em formato binário, ou seja, utilizando sequências de bits (0s e 1s). Cada tipo de dado (como números inteiros, números de ponto flutuante, caracteres, etc.) é codificado em binário de acordo com regras específicas, e o registro binário organiza esses dados em uma sequência contígua de bits.

> [!quote] **Def**
> 
> ###### **Como um Registro Binário Armazena Dados**
> 
> Aqui está um resumo de como um registro binário consegue armazenar diferentes tipos de dados:

---
#### **1. Números Inteiros**

> [!quote] **Def**  
> Os números inteiros são armazenados diretamente em binário, utilizando uma representação fixa de bits.
> 
> _**Exemplo**_:
> 
> - Um inteiro de 32 bits usa 32 bits para representar o valor, seja em formato **com sinal** (usando complemento de dois) ou **sem sinal**.
>     
> - O número `5` em binário (8 bits) é `00000101`.
>     

---
#### **2. Números de Ponto Flutuante**

> [!quote] **Def**  
> Números decimais são armazenados usando um padrão como o **IEEE 754**, que divide os bits em três partes:
> 
> _**Sinal**_:
> 
> - 1 bit para indicar positivo ou negativo.
>     
> 
> _**Expoente**_:
> 
> - Representa a magnitude do número.
>     
> 
> _**Mantissa**_:
> 
> - Representa a precisão do número.
>     
> 
> _**Exemplo**_:
> 
> - O número `3.14` seria codificado em binário seguindo essas regras.
>     

---
#### **3. Caracteres**

> [!quote] **Def**  
> Caracteres são armazenados usando codificações como **ASCII** ou **Unicode**.
> 
> _**Exemplo**_:
> 
> - Cada caractere é mapeado para um valor numérico, que é então armazenado em binário.
>     
> - O caractere `'A'` em ASCII é representado pelo valor `65`, que em binário (8 bits) é `01000001`.
>     

---

#### **4. Booleanos**

> [!quote] **Def**  
> Valores booleanos (`true` ou `false`) são armazenados usando 1 bit, onde `0` pode representar `false` e `1` pode representar `true`.

---

#### **5. Estruturas de Dados Compostas**

> [!quote] **Def**  
> Estruturas como arrays, structs ou objetos são armazenadas como uma sequência de bits que representa cada campo ou elemento individualmente.
> 
> _**Exemplo**_:
> 
> - Uma struct com um inteiro (32 bits) e um caractere (8 bits) ocuparia 40 bits no total.
>     

---
#### **6. Endereços e Ponteiros**

> [!quote] **Def**  
> Endereços de memória ou ponteiros são armazenados como números inteiros que representam a localização de outro dado na memória.

---

>[!example] ### **Específicos**

---
#### **Organização do Registro Binário**

> [!quote] **Def**  
> Um registro binário é como uma "caixa" que contém uma sequência de bits. A organização desses bits depende do tipo de dado e do esquema de codificação utilizado.
> 
> _**Exemplo**_:
> 
>**Um registro de 64 bits pode armazenar:**
>     
> - Um inteiro de 64 bits.
>     
> - Dois inteiros de 32 bits.
>     
> - Um número de ponto flutuante de 64 bits.
>     
> - Uma sequência de 8 caracteres ASCII.
>     

---
#### **Exemplo Prático**

> [!quote] **Def**  
> Suponha que um registro binário de 16 bits precise armazenar:
> 
> _**01 )**_:
> 
> - Um inteiro de 8 bits (`5`).
>     
> 
> _**02 )**_:
> 
> - Um caractere ASCII (`'A'`).
>     
> 
> _**Representação Binária**_:
> 
> - Inteiro `5`: `00000101`.
>     
> - Caractere `'A'`: `01000001`.
>     
> 
> _**Registro Binário Final**_:
> 
> - `00000101 01000001`.

---