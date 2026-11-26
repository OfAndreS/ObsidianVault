---
banner: Pasted image 20260712203132.png
banner-x: 50
banner-y: 35
banner-fade: 100
---
---

>[!quote] **Link:** [FastAPI Official Documentation](https://fastapi.tiangolo.com/)

---

```ad-done
title:
#### **Fase 1 ) - Task API ⭐**
```

---

````ad-quote
title:

##### **01 )** - Quick Task API em Memória (Nível 1 - Básico)

```ad-quote
title:
<p align="justify">Construção de uma API RESTful minimalista de gerenciamento de tarefas armazenadas em memória. O objetivo principal é fixar a mentalidade de rotas, verbos HTTP (GET, POST, PUT, DELETE), tipagem primitiva e exploração interativa pelo Swagger UI.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">A API permite listar todas as tarefas, buscar uma tarefa específica por ID (parâmetro de rota), criar uma nova tarefa via payload simples, alternar o status de conclusão e excluir um item. Não requer banco de dados, utilizando uma lista ou dicionário Python como repositório temporário.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Instanciação e Verbos HTTP
# Uso de app = FastAPI() e decoradores semânticos: @app.get, @app.post, @app.put e @app.delete.


02 ) Parâmetros de Rota (Path Parameters)
# Captura de identificador numérico da tarefa na URL: /tasks/{task_id} com tipagem task_id: int.


03 ) Parâmetros de Consulta (Query Parameters)
# Filtragem de tarefas por status na listagem: /tasks?completed=true com completed: bool | None = None.


04 ) Códigos de Status HTTP Semânticos
# Retorno de status_code=status.HTTP_201_CREATED no cadastro e status.HTTP_204_NO_CONTENT na exclusão.


05 ) Interrupção Controlada com HTTPException
# Disparo de HTTPException(status_code=404, detail="Tarefa não encontrada") quando o ID requisitado não existir.


06 ) Teste Interativo via Swagger UI
# Validação funcional de todos os métodos diretamente através da interface /docs.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Rotas Recomendada*
```

```bash
Rotas da API:
 ├── GET    /tasks           # Lista tarefas com filtro opcional (?completed=bool)
 ├── GET    /tasks/{task_id} # Retorna os detalhes de uma tarefa específica
 ├── POST   /tasks           # Cadastra uma nova tarefa (201 Created)
 ├── PUT    /tasks/{task_id} # Atualiza título ou status da tarefa
 └── DELETE /tasks/{task_id} # Remove a tarefa do repositório (204 No Content)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Tentar buscar ou excluir uma tarefa inexistente deve retornar HTTP 404 padronizado.
# [x] Enviar um ID alfanumérico para /tasks/abc deve retornar HTTP 422 automaticamente pelo FastAPI.
# [x] Todos os endpoints devem estar documentados com descrições claras no Swagger UI (/docs).


# Desafio Bônus:
# Implementar um contador sequencial automático e thread-safe para gerar IDs únicos incrementais.
```
````

---

```ad-done
title:
#### **Fase 2 ) - Catalog API ⭐⭐**
```

---

````ad-quote
title:

##### **02 )** - Catálogo de Produtos com Validação Estrita (Nível 2 - Básico-Intermediário)

```ad-quote
title:
<p align="justify">API de gerenciamento de catálogo de produtos com validação profunda de dados de entrada via Pydantic V2. O foco é garantir a integridade dos dados antes da persistência, uso de Field, regex e paginação avançada.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O sistema gerencia produtos contendo nome, descrição, preço, código SKU padronizado, categoria e disponibilidade. Validações estritas impedem cadastros com preços negativos ou códigos fora do padrão corporativo, e a listagem oferece paginação controlada por parâmetros de consulta.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Modelagem Declarativa com Pydantic V2
# Criação do contrato ProdutoCreate herdando de pydantic.BaseModel.


02 ) Restrições de Campos com Field()
# Preço obrigatoriamente positivo (gt=0).
# Nome com tamanho mínimo e máximo (min_length=3, max_length=120).
# Código SKU validado por expressão regular (pattern=r"^[A-Z]{3}-\d{4}$").


03 ) Validador Customizado com @field_validator
# Método validador para normalizar o nome do produto (remover espaços excessivos e formatar título).


04 ) Paginação Segura com Query()
# Parâmetros page: int = Query(default=1, ge=1) e limit: int = Query(default=10, ge=1, le=50).


05 ) Segregação de Contrato com response_model
# Utilização de ProdutoResponse para expor apenas os campos permitidos com formatação garantida.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Contratos Pydantic*
```

```bash
Modelos Pydantic:
 ├── ProdutoBase (campos compartilhados: nome, preco, categoria)
 ├── ProdutoCreate (herda de Base + sku com validação regex)
 ├── ProdutoUpdate (todos os campos opcionais para atualização parcial)
 └── ProdutoResponse (herda de Base + id gerado e data de cadastro)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Requisições com SKU inválido (ex: "123-abc") devem ser rejeitadas com HTTP 422 descritivo.
# [x] A listagem não pode permitir limit superior a 50 itens por página.
# [x] Resposta de criação deve devolver exatamente o modelo ProdutoResponse.


# Desafio Bônus:
# Implementar um validador de nível de modelo (@model_validator) que impeça produtos da categoria "Premium" de terem preço inferior a R$ 100,00.
```
````

---

```ad-done
title:
#### **Fase 3 ) - Library ORM ⭐⭐⭐**
```

---

````ad-quote
title:

##### **03 )** - Gestor de Biblioteca com SQLAlchemy 2.0 (Nível 3 - Intermediário)

```ad-quote
title:
<p align="justify">API de acervo literário com persistência em banco relacional (SQLite) utilizando o ORM SQLAlchemy 2.0. O desafio foca na modelagem relacional 1-para-N (Autor e Livros), controle transacional e injeção do ciclo de vida da sessão de banco via Depends(get_db).</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O sistema cadastra autores e livros associados a eles. Permite consultar autores com a lista completa de suas publicações, registrar novos livros vinculados a um autor existente via chave estrangeira, atualizar dados cadastrais e realizar buscas por título ou gênero literário.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Arquitetura de Conexão com SQLAlchemy 2.0
# Configuração de create_engine, sessionmaker e DeclarativeBase no arquivo database.py.


02 ) Injeção de Dependência da Sessão (get_db)
# Criação do gerador com yield e bloco finally: db.close() injetado nos endpoints via Depends(get_db).


03 ) Modelagem Relacional 1:N
# Tabela de Autores e Livros vinculados por ForeignKey("autores.id") e relationship() bidirecional.


04 ) Tipagem Mapped do SQLAlchemy 2.0
# Mapeamento estrito com Mapped[int], Mapped[str] e mapped_column().


05 ) Consultas Modernas com select()
# Execução de consultas via db.execute(select(LivroModel).where(...)).scalars().all().


06 ) Interoperabilidade Pydantic-ORM
# Uso de ConfigDict(from_attributes=True) para que os schemas Pydantic leiam diretamente os modelos ORM.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Arquitetura e Relacionamento de Banco*
```

```bash
Diagrama Relacional:
 [AutorModel] (1) ───────────◄ (N) [LivroModel]
  ├── id (PK)                       ├── id (PK)
  ├── nome                          ├── titulo
  ├── nacionalidade                 ├── ano_publicacao
  └── livros (relationship)        ├── autor_id (FK -> autores.id)
                                    └── autor (relationship)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Não permitir cadastrar um livro vinculado a um autor_id que não exista no banco (lançar HTTP 404).
# [x] A sessão do banco deve ser rigorosamente fechada após cada requisição.
# [x] A exclusão de um autor deve tratar a política de integridade referencial dos seus livros.


# Desafio Bônus:
# Implementar exclusão em cascata (cascade="all, delete-orphan") para que ao deletar um autor, todos os seus livros sejam apagados automaticamente.
```
````

---

```ad-done
title:
#### **Fase 4 ) - Modular Blog ⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **04 )** - Sistema de Blog Modular com APIRouter (Nível 4 - Intermediário Avançado)

```ad-quote
title:
<p align="justify">Plataforma de publicação de artigos com arquitetura modular desacoplada através de sub-roteadores APIRouter, middlewares globais e tratamento centralizado de exceções customizadas.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">A API organiza as funcionalidades em múltiplos módulos independentes: módulo de Usuários, módulo de Artigos/Posts e módulo de Comentários. Cada módulo possui suas próprias rotas, tags de documentação e esquemas, integrados ao núcleo da aplicação com suporte a CORS para consumo por navegadores.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Modularização com APIRouter
# Sub-roteadores em arquivos independentes (routers/posts.py, routers/comments.py, routers/users.py).
# Inclusão centralizada no main.py com app.include_router(posts.router, prefix="/api/v1").


02 ) Tags e Metadados OpenAPI
# Separação visual limpa dos endpoints por contexto na documentação Swagger UI.


03 ) Middleware Global de CORS (CORSMiddleware)
# Configuração de allow_origins, allow_methods e allow_headers para desbloquear requisições frontend.


04 ) Handler Centralizado de Exceções
# Criação de exceção customizada (ex: RecursoNaoEncontradoException) e registro com @app.exception_handler().


05 ) Injeção de Dependências Compostas
# Dependência comum de paginação compartilhada entre os roteadores de posts e comentários.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Pastas Recomendada*
```

```bash
app/
 ├── main.py              # Instanciação do app, middlewares e registro de rotas
 ├── core/
 │    └── exceptions.py   # Handlers de erro customizados
 ├── database.py          # Conexão e sessão de banco
 ├── models/              # Modelos do SQLAlchemy
 ├── schemas/             # Schemas do Pydantic por domínio
 └── routers/
      ├── users.py        # Endpoints de autores e usuários
      ├── posts.py        # Endpoints de criação e listagem de artigos
      └── comments.py     # Endpoints de comentários
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Nenhum endpoint de regra de negócio deve ser declarado diretamente dentro do main.py.
# [x] As rotas devem possuir o prefixo global padronizado /api/v1.
# [x] Erros customizados devem devolver um JSON padronizado com campos "erro", "codigo" e "timestamp".


# Desafio Bônus:
# Implementar um middleware customizado que meça o tempo de processamento de cada requisição e anexe o header X-Process-Time na resposta.
```
````

---

```ad-done
title:
#### **Fase 5 ) - Auth Service ⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **05 )** - API de Autenticação Segura com OAuth2 e JWT (Nível 5 - Avançado)

```ad-quote
title:
<p align="justify">Microsserviço de autenticação e controle de identidade corporativa. Implementa o fluxo padrão OAuth2 Password Bearer, armazenamento seguro de senhas com algoritmo Bcrypt e emissão de tokens de acesso JWT criptografados.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 5.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O serviço disponibiliza rota de cadastro com hash irreversível de senha, endpoint padrão <code>/auth/token</code> consumindo credenciais via form-data, emissão de Access Token com tempo de vida limitado (TTL) e a dependência de segurança <code>get_current_user</code> para proteger rotas privadas contra acessos não autorizados.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Hashing de Senhas com Bcrypt
# Criptografia segura com passlib[bcrypt] ou biblioteca bcrypt pura (hashpw e checkpw).
# NUNCA persistir senhas em texto puro no banco de dados.


02 ) OAuth2PasswordRequestForm
# Uso do formulário padrão de autenticação do FastAPI para captura de username e password.


03 ) Geração e Assinatura de JWT (JSON Web Tokens)
# Construção do payload com sub (identificador), exp (timestamp de expiração) e algoritmo HS256.


04 ) Esquema de Segurança OAuth2PasswordBearer
# Configuração do tokenUrl="/auth/token" que adiciona o botão de autorização (cadeado) no Swagger UI.


05 ) Dependência Guardiã get_current_user
# Decodificação do token recebido no header Authorization: Bearer <token>.
# Emissão imediata de HTTP 401 Unauthorized com header WWW-Authenticate: Bearer caso o token seja inválido ou expire.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Fluxo de Autenticação OAuth2 / JWT*
```

```bash
Fluxo de Comunicação:
 1. Cliente ────── POST /auth/token (username, password) ─────► Servidor
 2. Servidor ──── Valida hash e gera JWT assinado ───────────► Cliente
 3. Cliente ────── GET /perfil (Header: Bearer <JWT>) ────────► Servidor (get_current_user)
 4. Servidor ──── Decodifica token e retorna usuário ────────► Cliente (200 OK)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] O botão "Authorize" do Swagger UI deve funcionar perfeitamente com o endpoint de login.
# [x] Senhas devem ser validadas antes de gerar o hash (mínimo de 8 caracteres, números e letras).
# [x] Tokens expirados devem ser rejeitados imediatamente com mensagem de erro descritiva.


# Desafio Bônus:
# Implementar um mecanismo de Refresh Token para renovar a sessão sem exigir nova digitação de senha.
```
````

---

```ad-done
title:
#### **Fase 6 ) - Store API ⭐⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **06 )** - E-Commerce RESTful com Relacionamentos N:N e Alembic (Nível 6 - Avançado)

```ad-quote
title:
<p align="justify">API completa de retaguarda para e-commerce com modelagem relacional complexa Muitos-para-Muitos (Pedidos e Produtos), transações atômicas com rollback em caso de falha de estoque e versionamento de banco com Alembic.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 6.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O sistema processa pedidos contendo múltiplos produtos e quantidades. Exige controle rigoroso de estoque, cálculo automático de subtotal e frete, congelamento do preço unitário do item no momento da compra (tabela associativa ItemPedido) e controle de migrações estruturadas do banco de dados.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Modelagem N:N com Atributos Extras
# Tabela de associação ItemPedido contendo pedido_id, produto_id, quantidade e preco_unitario_momento.


02 ) Controle Transacional com Rollback
# Uso de blocos try / except db.commit() com db.rollback() para garantir atomicidade.
# Se algum produto do pedido não tiver estoque suficiente, cancelar a transação inteira.


03 ) Versionamento de Banco com Alembic
# Inicialização com alembic init migrations, geração automática de migrações com alembic revision --autogenerate e aplicação com alembic upgrade head.


04 ) Variáveis de Ambiente com pydantic-settings
# Leitura tipada de configurações (DATABASE_URL, SECRET_KEY, DEBUG) através de classe BaseSettings lendo arquivo .env.


05 ) Consultas com Eager Loading (joinedload)
# Uso de options(joinedload(PedidoModel.itens)) para evitar o problema de performance N+1 queries.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura Relacional de Pedidos*
```

```bash
Esquema de Tabelas:
 [UsuarioModel] (1) ──────────◄ (N) [PedidoModel]
                                          │ (1)
                                          ▼
                                     [ItemPedido] (N) ◄──────── (1) [ProdutoModel]
                                      ├── preco_momento
                                      └── quantidade
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Toda alteração de schema deve ser aplicada via migrações Alembic, sem drop_all()/create_all().
# [x] Tentativa de compra acima da quantidade disponível de estoque deve abortar a criação do pedido.
# [x] O valor unitário salvo no ItemPedido deve refletir o valor da compra, imune a alterações futuras no produto.


# Desafio Bônus:
# Implementar soft-delete em produtos (marcando active=False em vez de remover fisicamente do banco).
```
````

---

```ad-done
title:
#### **Fase 7 ) - Event Stream API ⭐⭐⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **07 )** - API Assíncrona com Cache Redis e BackgroundTasks (Nível 7 - Expert)

```ad-quote
title:
<p align="justify">Serviço de alta taxa de transferência (high throughput) totalmente assíncrono. Emprega BackgroundTasks nativas do FastAPI para operações que não devem bloquear a resposta HTTP e integração com Redis para cache em memória e invalidação inteligente.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 7.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">A API recebe notificações e eventos pesados. Processa o registro de clientes devolvendo resposta instantânea com HTTP 202 Accepted, enquanto dispara rotinas demoradas em background (geração de relatórios e emails simulados). Endpoints de consulta utilizam cache em Redis com tempo de vida (TTL) para desonerar o banco principal.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Tarefas Assíncronas com BackgroundTasks
# Injeção de background_tasks: BackgroundTasks e enfileiramento com background_tasks.add_task(func, *args).
# A resposta HTTP é devolvida ao cliente em milissegundos sem esperar a conclusão da rotina pesada.


02 ) Integração com Cache Redis (redis-py assíncrono)
# Conexão assíncrona com servidor Redis (aioredis / redis.asyncio).
# Verificação de chave no cache antes de consultar o banco relacional (Cache-Aside Pattern).


03 ) TTL e Invalidação Proativa de Cache
# Definição de tempo de expiração automático nos registros em cache (ex: 60 segundos).
# Limpeza cirúrgica da chave do Redis sempre que ocorrer uma alteração ou exclusão do recurso.


04 ) Código 100% Async / Await
# Definição de endpoints com async def e execução não bloqueante de I/O.


05 ) Rate Limiting por IP ou Token
# Implementação de limitação de taxa de requisições para mitigar ataques de negação de serviço (DoS).
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Fluxo de Cache e Background Tasks*
```

```bash
Arquitetura de Fluxo:
 Requisição GET ────────► Checa Redis Cache? ───[SIM]───► Retorno Imediato (Cache Hit)
                               │ [NÃO]
                               ▼
                         Consulta Banco ──────► Grava no Redis (TTL) ──► Retorna Dados

 Requisição POST ───────► Salva no Banco ─────► Invalida Cache no Redis
                               │
                               └──────────────► add_task() em Background ──► Retorna 202 Accepted
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Tarefas pesadas não podem adicionar mais de 10ms ao tempo de resposta do endpoint.
# [x] Consultas com cache ativo devem responder em menos de 5ms.
# [x] Atualizar um registro deve invalidar imediatamente a respectiva chave de cache no Redis.


# Desafio Bônus:
# Implementar um endpoint de Server-Sent Events (SSE) com StreamingResponse para enviar logs de progresso da tarefa em tempo real ao cliente.
```
````

---

```ad-done
title:
#### **Fase 8 ) - Enterprise SaaS ⭐⭐⭐⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **08 )** - SaaS Multitenant Enterprise com Docker e Pytest (Nível 8 - Master / Enterprise)

```ad-quote
title:
<p align="justify">Plataforma SaaS corporativa completa com arquitetura limpa em camadas, suporte a múltiplos clientes isolados (multitenancy), cobertura integral de testes automatizados com Pytest e empacotamento em containers Docker.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 8.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">Sistema corporativo que atende diferentes organizações clientes na mesma infraestrutura garantindo segregação total de dados. A aplicação conta com arquitetura desacoplada em camadas (Controller, Service, Repository), suíte completa de testes automatizados unitários e de integração com banco de testes descartável e orquestração via Docker Compose.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Arquitetura Limpa em Camadas
# Camada de Apresentação (Routers) desacoplada da Camada de Domínio (Services) e Acesso a Dados (Repositories).


02 ) Isolamento Multitenant Seguro
# Extração do tenant_id a partir do token JWT ou header corporativo X-Tenant-ID.
# Injeção automática de filtros em todas as consultas SQL para impedir vazamento de dados entre empresas.


03 ) Testes Automatizados com Pytest e HTTPX
# Configuração de conftest.py com fixtures para banco de dados isolado em memória (SQLite in-memory).
# Uso de httpx.AsyncClient para disparar requisições assíncronas aos endpoints nos testes.


04 ) Tratamento de Migrações em Testes
# Aplicação automática das migrações do banco no setup da suíte de testes.


05 ) Containerização Profissional com Docker
# Criação de Dockerfile multi-stage com imagem base python:3.11-slim, usuário não-root e sem cache de pacotes.
# docker-compose.yml orquestrando a API FastAPI, banco PostgreSQL e Redis com healthchecks ativos.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Pastas Enterprise*
```

```bash
src/
 ├── api/                 # Camada de Entrada (Routers e Dependências)
 │    ├── v1/
 │    └── dependencies/   # get_current_user, get_tenant
 ├── core/                # Configurações globais, segurança e logs
 ├── domain/              # Regras de negócio puras (Entities e Interfaces)
 ├── repositories/        # Implementações de persistência com SQLAlchemy
 ├── services/            # Casos de uso e orquestração de negócios
 └── tests/               # Suíte automatizada com Pytest
      ├── conftest.py     # Fixtures de banco e cliente HTTPX
      ├── unit/           # Testes unitários de serviços
      └── integration/    # Testes de integração de endpoints
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Nenhum usuário de uma organização pode visualizar ou alterar dados de outro tenant (teste específico obrigatório).
# [x] O comando pytest deve rodar com sucesso e cobrir mais de 80% do código da aplicação.
# [x] O comando docker compose up deve subir o ecossistema completo funcional em uma única execução.


# Desafio Bônus:
# Configurar pipeline de CI no GitHub Actions que execute linting (ruff/flake8) e rode a suíte do Pytest a cada push.
```
````

---
