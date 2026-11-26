---
banner: "![[Pasted image 20251221174537.png]]"
banner-x: 50
banner-y: 45
---
---
#### **Intro )** - Fundamentos do Framework Django

```ad-quote
title: **Def**
**Summary:**
- O Django é um framework de alto nível que promove o desenvolvimento rápido e um design limpo. Ele utiliza a arquitetura MVT para separar a lógica de negócios da interface, focando em segurança e escalabilidade desde a raiz do projeto.
```

>[!quote] **Draw:** [[DrawDjango.excalidraw]]

>[!quote] **Link:** [Django Project - Documentation](https://docs.djangoproject.com/en/stable/)

>[!quote] **Link:** [Django Girls Tutorial - Estrutura](https://tutorial.djangogirls.org/pt/django_installation/)

---

> [!done] **_New_**

---
##### **00 ) -** Django Operações Suportadas

>[!quote] **Vault:** [[Dj - Operações Suportadas]]

---

```ad-done
title:
#### **Fase 1 )** - Estrutura de Projeto e Aplicações
```

---

```ad-quote
title: 
Esta fase foca na compreensão da anatomia de um sistema Django, distinguindo as configurações globais das funcionalidades modulares.
```

---

> [!done] **_New_**

---
#### **01 ) -** Anatomia: Project vs App

```ad-quote
title: **Def**
**Summary:**
- Um Project contém as configurações globais de infraestrutura, como segredos e banco de dados. Um App é uma unidade funcional específica (ex: checkout ou blog), permitindo a reutilização de código e organização modular.
```

> [!quote] **Vault:** [[DJ - Project e App Architecture]]

---

> [!done] **_New_**

---
#### **02 ) -** Orquestração: Settings e Manage.py

```ad-quote
title: **Def**
**Summary:**
- O arquivo settings.py gerencia o registro de aplicações e templates. O manage.py atua como a interface de linha de comando para execução do servidor, migrações e tarefas administrativas.
```

> [!quote] **Vault:** [[DJ - Core Configurations]]

---

```ad-done
title:
#### **Fase 2 ) -** O Fluxo de Dados e o Padrão MVT
```

---

```ad-quote
title: 
Nesta etapa, exploramos como o Django processa uma requisição e a transforma em uma resposta visual através de rotas, lógicas e herança de interface.
```

---
#### **03 ) -** Roteamento e Lógica: URLs e Views

```ad-quote
title: **Def**
**Summary:**
- As URLs definem os caminhos e capturam dados dinâmicos via path converters. As Views (FBVs) processam o objeto request e retornam o HttpResponse, servindo como a ponte lógica do sistema.
```

> [!quote] **Vault:** [[DJ - URL Routing e Views]]

---

> [!done] **_New_**

---
#### **04 ) -** Interceptação: Middlewares

```ad-quote
title: **Def**
**Summary:**
- Componentes que processam a requisição e a resposta globalmente. Atuam como camadas de segurança e utilidade (ex: autenticação, proteção _CSRF_ e sessões) que executam de forma automática antes ou depois da lógica da View.
```

> [!quote] **Vault:** [[DJ - Middlewares Architecture]]

---

> [!done] **_New_**

---
#### **05 ) -** Interface: Templates e Herança DTL

```ad-quote
title: **Def**
**Summary:**
- Uso da Django Template Language para renderização dinâmica. A herança de templates permite a criação de layouts base reaproveitáveis, otimizando a manutenção do front-end através de blocos de conteúdo.
```

> [!quote] **Vault:** [[DJ - Template Language e Inheritance]]

---

```ad-done
title:
#### **Fase 3 ) -** Persistência e Modelagem (ORM)
```

---

```ad-quote
title: 
Fase crítica onde o foco é o mapeamento de dados e a comunicação com o banco de dados sem a necessidade de escrita manual de SQL.
```

---
#### **06 ) -** Modelagem: Models e Ciclo de Migrações

```ad-quote
title: **Def**
**Summary:**
- Definição de tabelas via classes Python utilizando campos como CharField e IntegerField. O ciclo de vida é gerido por makemigrations e migrate, traduzindo alterações de código em esquemas de banco de dados.
```

> [!quote] **Vault:** [[DJ - Models e Migrations]]

---

> [!done] **_New_**

---
#### **07 ) -** Controle: Django Admin

```ad-quote
title: **Def**
**Summary:**
- O Django Admin é uma das funcionalidades mais poderosas e amadas do framework. Ele é uma interface de gerenciamento automática, pronta para o uso, que permite criar, ler, atualizar e excluir (_CRUD_) registros no seu banco de dados sem que você precise escrever código HTML ou CSS para isso.
```

> [!quote] **Vault:** [[DJ - Django Admin]]

---

> [!done] **_New_**

---
#### **08 ) -** Interação: Django ORM e QuerySets

```ad-quote
title: **Def**
**Summary:**
- Manipulação de dados através de QuerySets utilizando métodos como all(), filter() e get(). A prática via Shell do Django permite validar a lógica de busca antes da implementação nas Views.
```

> [!quote] **Vault:** [[DJ - ORM e QuerySet API]]

---

> [!done] **_New_**

---
#### **09 ) -** Laboratório: Django Shell e Shell Plus

```ad-quote
title: **Def**
**Summary:**
- O Shell do Django permite interagir com o projeto via terminal. O uso do Shell Plus (via django-extensions) automatiza o import de modelos, sendo uma ferramenta essencial para testar consultas do _ORM_ e depurar o comportamento do banco de dados em tempo real.
```

> [!quote] **Vault:** [[DJ - Shell e Debugging]]

---

```ad-done
title:
#### **Fase 4 ) -** Interação de Usuário e Formulários
```

---

```ad-quote
title: 
Esta etapa final é dedicada à captura de dados e validação de segurança, integrando a interface do usuário diretamente com as regras do banco de dados.
```

---
#### **10 ) -** Formulários: ModelForms e Validação

```ad-quote
title: **Def**
**Summary:**
- Utilização de ModelForms para geração automática de campos HTML baseados em modelos. Implementação de validações automáticas e distinção entre métodos HTTP (GET/POST) para integridade dos dados.
```

> [!quote] **Vault:** [[DJ - Forms e Segurança de Dados]]

---

> [!done] **_New_**

---
#### **11 ) -** Feedback: Django Messages Framework

```ad-quote
title: **Def**
**Summary:**
- Sistema para exibir notificações temporárias ao usuário (sucesso, erro, aviso). Permite que a aplicação forneça um retorno visual após o processamento de formulários ou alterações de estado, melhorando a experiência do usuário.
```

> [!quote] **Vault:** [[DJ - Messages Framework]]

---
