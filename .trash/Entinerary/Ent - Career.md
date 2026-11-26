
---

````ad-quote
title:
##### **1 ) -** Fundamentos e Pythonismo - 25%

```ad-quote
title:
O objetivo aqui é escrever código que seja _performático_ e _legível_ para outros engenheiros. O Python é uma linguagem fácil de começar, mas difícil de dominar em nível profissional.
```
````

````ad-quote
title:

```ad-quote
title:

###### A ) - **Python Internals:**

```

```ad-quote
title:

- [ ] Importância - 7/10

```

```ad-quote
title:

Compreender o funcionamento do _CPython_, o gerenciamento de memória via _Reference Counting_ e o _Global Interpreter Lock (GIL)_. Dominar o modelo de dados significa entender como os métodos _dunder_ permitem que suas classes se comportem como tipos nativos (ex: tornar um objeto iterável ou "chamável"). Os protocolos (via _Abstract Base Classes_ ou _Structural Typing_) garantem que seu código seja flexível e siga o princípio de _Duck Typing_.

```

````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Funcionalidades Avançadas:**
```

```ad-quote
title:
- [ ] Importância - 9/10
```

```ad-quote
title:
Dominar _decoradores_ para estender comportamentos de funções sem modificar seu código fonte (essencial para _logging_ e _auth_). Usar _gerenciadores de contexto_ para garantir o fechamento de recursos como arquivos ou conexões de rede. Utilizar _iteradores_ e _geradores_ para processar grandes volumes de dados (como arquivos de áudio) sem estourar a memória RAM.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) - **Concorrência e Assincronia:**
```

```ad-quote
title:
- [ ] Importância - 10/10
```

```ad-quote
title:
Diferenciar quando usar _threads_ (I/O intensivo), _multiprocessing_ (processamento paralelo de CPU para redes neurais) e _asyncio_. O domínio de _async/await_ é fundamental para criar aplicações web modernas que lidam com milhares de conexões simultâneas sem criar gargalos de espera.
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) - **Tipagem Estática:**
```

```ad-quote
title:
- [ ] Importância - 9/10
```

```ad-quote
title:
Implementar _type hints_ em todo o projeto para transformar o Python em uma linguagem mais segura. Ferramentas como _Mypy_ ou _Pyright_ ajudam a detectar erros de lógica antes mesmo da execução, o que é vital em sistemas complexos de engenharia.
```
````

````ad-quote
title:
```ad-quote
title:
###### E ) - **Algoritmos e Estruturas:**
```

```ad-quote
title:
- [ ] Importância - 7/10
```

```ad-quote
title:
Não apenas conhecer, mas saber aplicar a _Notação Big O_ para prever o custo de execução. Dominar a manipulação de estruturas como _Heaps_, _Tries_ e _Grafos_, além de saber quando uma busca em largura (_BFS_) é superior a uma busca em profundidade (_DFS_) em problemas de otimização.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **2 ) -** Backend com Django - 25%

```ad-quote
title:
Aqui você constrói a estrutura que sustenta a inteligência do sistema. O Django é o "alicerce" que garante a segurança e a organização dos dados.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Django ORM Profundo:**
```

```ad-quote
title:
- [ ] Importância - 10/10
```

```ad-quote
title:
Ir além do básico e entender como evitar o problema de _N+1 queries_ usando _select_related_ e _prefetch_related_. Aprender a realizar agregações complexas diretamente no banco de dados e garantir a integridade com _transações atômicas_, evitando que falhas no meio de um processo corrompam as informações.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Django REST Framework (DRF):**
```

```ad-quote
title:
- [ ] Importância - 9/10
```

```ad-quote
title:
Construir APIs robustas com _serializers_ customizados que validam dados complexos. Implementar sistemas de autenticação seguros (como _JWT_ ou _OAuth2_) e utilizar _throttling_ para proteger sua infraestrutura de ataques de negação de serviço ou uso excessivo de recursos.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) - **Arquitetura de Software:**
```

```ad-quote
title:
- [ ] Importância - 8/10
```

```ad-quote
title:
Evitar o antipadrão de "models gordos" ou "views complexas". Implementar uma camada de _Services_ para isolar a lógica de negócio do _framework_. Isso torna o sistema muito mais fácil de testar, manter e migrar para outras tecnologias no futuro se necessário.
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) - **Tarefas Assíncronas:**
```

```ad-quote
title:
- [ ] Importância - 9/10
```

```ad-quote
title:
Dominar a integração do Django com o _Celery_. Isso permite que tarefas pesadas, como a _extração de características de áudio_ ou o envio de e-mails em massa, aconteçam em segundo plano, mantendo a experiência do usuário fluida e sem travamentos na interface.
```
````

````ad-quote
title:
```ad-quote
title:
###### E ) - **Segurança:**
```

```ad-quote
title:
- [ ] Importância - 10/10
```

```ad-quote
title:
Aplicar na prática as melhores defesas contra _SQL Injection_, _Cross-Site Scripting (XSS)_ e _Cross-Site Request Forgery (CSRF)_. Saber gerenciar segredos e chaves de API de forma segura usando variáveis de ambiente e ferramentas de _vault_, nunca expondo dados sensíveis no sistema de versão.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **3 ) -** IA e Dados Aplicados - 20%

```ad-quote
title:
O seu foco é transformar modelos de pesquisa em funcionalidades de produto. É a ponte entre o seu trabalho acadêmico e a aplicação comercial.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Engenharia de Features e ETL:**
```

```ad-quote
title:
- [ ] Importância - 8/10
```

```ad-quote
title:
Dominar o ciclo de _Extract, Transform, Load_. Usar _Pandas_ para análise exploratória e migrar para o _Polars_ quando precisar de performance extrema em grandes datasets.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Serviço de Modelos:**
```

```ad-quote
title:
- [ ] Importância - 9/10
```

```ad-quote
title:
Aprender a exportar modelos treinados para formatos de produção como _ONNX_ ou _TorchScript_. Otimizar a inferência para que o modelo responda em milissegundos, utilizando técnicas como _quantização_ para reduzir o peso dos arquivos sem perder precisão significativa.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) - **Bancos de Dados Vetoriais:**
```

```ad-quote
title:
- [ ] Importância - 8/10
```

```ad-quote
title:
Implementar ferramentas como _ChromaDB_ ou _Qdrant_ para armazenar "assinaturas" de dados (embeddings). Isso permite criar funcionalidades de busca por similaridade (ex: "encontrar músicas parecidas com esta") que são impossíveis de fazer com bancos de dados relacionais comuns.
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) - **RAG - Retrieval-Augmented Generation:**
```

```ad-quote
title:
- [ ] Importância - 8/10
```

```ad-quote
title:
Conectar modelos de linguagem (_LLMs_) a fontes de dados externas. Isso permite que a IA responda perguntas baseada em documentos específicos da sua pesquisa ou empresa, reduzindo drasticamente as alucinações dos modelos generativos.
```
````

````ad-quote
title:
```ad-quote
title:
###### E ) - **MLOps Básico:**
```

```ad-quote
title:
- [ ] Importância - 7/10
```

```ad-quote
title:
Utilizar o _DVC_ para versionar seus datasets e modelos da mesma forma que versiona o código. Implementar o monitoramento de _drift_, que alerta quando o comportamento dos dados no mundo real muda e o seu modelo começa a perder a eficácia original.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **4 ) -** DevOps e Infraestrutura - 15%

```ad-quote
title:
A garantia de que o seu sistema é estável, escalável e fácil de atualizar. Um código que só roda na sua máquina ainda não é um produto.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Docker e Containers:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Isolar todo o ambiente de execução em _containers_. Criar _Dockerfiles_ otimizados (multi-stage builds) para reduzir o tamanho das imagens e facilitar o deploy. Usar o _Docker Compose_ para orquestrar múltiplos serviços (Django, Postgres, Redis) localmente com um único comando.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Servidores Web:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Configurar o _Nginx_ para gerenciar o tráfego de entrada, servir arquivos estáticos de forma eficiente e atuar como _load balancer_. Dominar a configuração de servidores de aplicação como _Gunicorn_ (síncrono) ou _Uvicorn_ (assíncrono) para servir seu app Python.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) - **CI/CD:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Automatizar a esteira de produção com _GitHub Actions_. Toda vez que você enviar um código, o sistema deve rodar testes automaticamente, verificar o estilo do código e fazer o deploy para o servidor se tudo estiver correto.
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) - **Bancos de Dados:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Além de escrever consultas, saber administrar o _PostgreSQL_. Isso inclui criar índices para acelerar buscas, realizar migrações de esquema sem derrubar o sistema e configurar rotinas de _backup_ automáticas.
```
````

````ad-quote
title:
```ad-quote
title:
###### E ) - **Observabilidade:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Não esperar o usuário reclamar para saber que algo deu errado. Implementar _Sentry_ para capturar exceções em tempo real e utilizar _Prometheus_ com _Grafana_ para visualizar o uso de CPU, memória e tempo de resposta da sua API.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **5 ) -** Produto e Soft Skills - 15%

```ad-quote
title:
O que transforma um técnico em um resolvedor de problemas de negócio. É a camada que dá sentido a todo o esforço tecnológico anterior.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Comunicação Técnica:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Traduzir a complexidade de um _classificador de áudio_ para termos que um gerente de produto ou investidor entenda. Focar no _benefício_ (precisão, velocidade, custo) em vez de apenas na arquitetura da rede neural.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Documentação Profissional:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Escrever _READMEs_ que permitam que outro desenvolvedor suba o projeto em 5 minutos. Utilizar o _Swagger/OpenAPI_ para que qualquer pessoa saiba como consumir sua API sem precisar ler o seu código fonte. Criar diagramas de arquitetura claros para explicar o fluxo de dados.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) - **Mentalidade de MVP:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Entender que o "feito é melhor que o perfeito" para validar uma ideia. Saber identificar qual é a funcionalidade mínima que gera valor para o usuário e focar nela, evitando o _over-engineering_ (excesso de engenharia) em problemas que ainda não existem.
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) - **Metodologias Ágeis:**
```

```ad-quote
title:
<input type="checkbox"> <input type="checkbox"> <input type="checkbox"> 
```

```ad-quote
title:
Adaptar-se a fluxos de trabalho como _Scrum_ ou _Kanban_. Saber estimar prazos de forma realista, quebrar tarefas grandes em pequenas entregas e participar de forma construtiva em revisões de código e reuniões de equipe.
```
````

---
