---
banner: "![[Pasted image 20251221173031.png]]"
banner-x: 51
banner-y: 40
---

---
#### **Intro )** - Java

```ad-quote
title: **Def**
**Summary:**
- Este roteiro foca nos desafios técnicos específicos de usar ARQUIVOS CSV e JAVA 17 em um ambiente concorrente. Este projeto não é um CRUD comum, exigindo conhecimentos de MANIPULAÇÃO DE ARQUIVOS e CONCORRÊNCIA, frequentemente ignorados em tutoriais básicos.
```

>[!quote] **Vault:** [[Java - O Ecossistema de Desenvolvimento]]

---

> [!done] _New_

---
#### **00 )** - Iniciando um Projeto

```ad-quote
title: **Def**
**Summary:**
- Todo projeto em JAVA segue uma estrutura modular rigorosa, com as responsabilidades das classes estrategicamente divididas. Portanto, é crucial que o desenvolvedor compreenda essas nuances. Estar preparado para configurar a arquitetura de diretórios e pacotes é um pré-requisito obrigatório antes mesmo de colocar a mão na massa e iniciar a codificação.
```

>[!quote] **Vault:** [[Java - Setup Inicial - Vanilla Development]]

---

> [!done] _New_

---
#### **01 )** - Fundamentos do Java 17+ - A Base

```ad-quote
title: **Def**
**Summary:**
- Antes de mexer no Spring, é necessário dominar as ferramentas da linguagem usadas nos pacotes MODEL e REPOSITORY. O foco inclui RECORDS para DTOs imutáveis, JAVA NIO.2 para I/O eficiente, STREAM API para manipulação de listas e novos STRING METHODS.
```

> [!quote] **Vault:** [[Java - Records]]

> [!quote] **Vault:** [[Java - NIO.2 Files]]

> [!quote] **Vault:** [[Java - Stream API]]

---

> [!done] _New_

---
#### **02 )** - O Desafio da Concorrência

```ad-quote
title: **Def**
**Summary:**
- O ponto mais crítico do projeto. Garante que se dois usuários votarem ao mesmo tempo, o sistema não perca dados. Envolve o estudo de ATOMICLONG para somas seguras, diferenças entre COLLECTIONS.SYNCHRONIZEDLIST e COPYONWRITEARRAYLIST, e o uso da keyword SYNCHRONIZED.
```

> [!quote] **Vault:** [[Java - Concurrency]]

> [!quote] **Vault:** [[Java - Thread Safety]]

> [!quote] **Vault:** [[Java - Atomic Variables]]

---

````ad-quote
title:
##### **00 ) -** Desenvolvimento de APIs

>[!quote] **Vault:** [[Java - Desenvolvimento de APIs]]

````
