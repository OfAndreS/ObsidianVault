
---

````ad-quote
title:

##### **Intro )** - Contexto Histórico e o Problema

```ad-quote
title:
<p align="justify">Para entender o Spring precisamos analisar a evolução do desenvolvimento Java em três atos: o Problema J2EE EJB, a Solução Spring Framework e a Otimização Spring Boot.</p>
```



```ad-quote
title:
###### **O Cenário Pré-2003 - J2EE**
```

```ad-quote
title:

|Problema&nbsp; | Impacto no Desenvolvimento&nbsp; |
| :--- | :--- |
|**Burocracia Extrema**|Obrigava a criação de múltiplas interfaces e arquivos XML gigantescos para tarefas simples.|
|**Acoplamento Intenso**|O código era Intrinsecamente Dependente de servidores de aplicação pesados como WebSphere. Não rodava em um método main simples.|
|**Invasão no Código**|A regra de negócio precisava estender classes do framework sujando a lógica com infraestrutura.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - A Filosofia Spring e POJOs

```ad-quote
title:
<p align="justify">Em 2002 Rod Johnson lançou a tese revolucionária de que a complexidade da infraestrutura não deve se misturar com a regra de negócio. O Spring nasceu para permitir o uso de POJOs Plain Old Java Objects.</p>
```

```ad-quote
title:
###### **Definição de POJO**
```

```ad-quote
title:
<p align="justify">É uma classe Java comum que não herda de ninguém e não implementa interfaces complexas. O Spring atua de forma Invisível para dar a essa classe poderes de transação e segurança.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Mecanismo Técnico - IoC e DI

```ad-quote
title:
<p align="justify">O framework resolve a complexidade através de dois pilares fundamentais que invertem a responsabilidade de gerenciamento de objetos.</p>
```



```ad-quote
title:
###### **A. Inversão de Controle - IoC**
```

```ad-quote
title:
<p align="justify">No modelo tradicional o seu código controla o fluxo. No Spring existe um Container ApplicationContext que gerencia o ciclo de vida dos objetos. Você diz ao Spring para criar e guardar o objeto na memória.</p>
```

```ad-quote
title:
###### **B. Injeção de Dependência - DI**
```

```ad-quote
title:

|Cenário&nbsp; | Comportamento&nbsp; |
| :--- | :--- |
|**Sem Spring**|A classe Venda cria uma instância de Estoque dentro dela (new Estoque). Alto acoplamento.|
|**Com Spring**|A classe Venda apenas declara que precisa de um Estoque. O Spring Injeta a instância pronta no momento da execução.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - A Evolução Moderna: Spring Boot

```ad-quote
title:
<p align="justify">O Spring Framework resolveu o problema do código Java mas criou a Complexidade De Configuração com muitos XMLs. O Spring Boot resolve isso através da Convenção Sobre Configuração.</p>
```



```ad-quote
title:
###### **Diferenciais do Spring Boot**
```

```ad-quote
title:

|Recurso&nbsp; | Benefício&nbsp; |
| :--- | :--- |
|**Autoconfiguração**|Se detectar um driver de banco de dados ele configura automaticamente o DataSource padrão.|
|**Stand-alone**|Traz um servidor Tomcat Embutido dentro do arquivo jar. Elimina a necessidade de instalação separada de servidores.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **Conclusão )** - Resumo Definitivo

```ad-quote
title:
<p align="justify">O ecossistema Spring retira a complexidade técnica boilerplate da frente do desenvolvedor permitindo focar na regra de negócio.</p>
```

```ad-quote
title:

|Componente&nbsp; | Função Principal&nbsp; |
| :--- | :--- |
|**Spring Framework**|Gerencia a criação e conexão dos objetos via IoC e Injeção de Dependência.|
|**Spring Boot**|Elimina configurações manuais entregando um ambiente produtivo pronto para rodar.|
|**Objetivo Final**|Criar sistemas robustos usando objetos simples POJOs.|

```
````

---