---
banner: "- FILES/Banners/General/Pasted image 20251020194602.png"
banner-x: 50
banner-y: 35
banner-fade: 100
---

---

#### **Intro )** - Ambiente e Instalação do PostgreSQL e pgAdmin 4 — 01 (PostgreSQL, pgAdmin 4, psql, Service & Setup)

```ad-quote
title: **Def**
**Summary:**
- Configuração do ecossistema de banco de dados relacional (RDBMS) com PostgreSQL e sua interface visual administrativa pgAdmin 4. Esta nota aborda a instalação completa do servidor PostgreSQL via gerenciador de pacotes, a inicialização e controle do serviço com systemd, a configuração de credenciais e privilégios no console interativo psql, a instalação do pgAdmin 4 (modos Desktop e Web) e a conexão do cliente visual com a instância local.
```

---

### 📋 Checklist de Estudos - Tópicos a Cobrir

- [ ] **01 )** - Atualização de pacotes do sistema e instalação do servidor PostgreSQL (`postgresql`, `postgresql-contrib`)
- [ ] **02 )** - Gerenciamento e verificação do status do serviço via systemd (`systemctl status`, `start`, `enable`)
- [ ] **03 )** - Acesso ao console interativo de administração `psql` com o usuário de sistema `postgres`
- [ ] **04 )** - Definição da senha de autenticação do superusuário (`ALTER USER postgres WITH PASSWORD ...`)
- [ ] **05 )** - Criação de banco de dados e usuário de aplicação com permissões dedicadas
- [ ] **06 )** - Comandos fundamentais de navegação e metadados no `psql` (`\l`, `\c`, `\dt`, `\du`, `\conninfo`, `\q`)
- [ ] **07 )** - Importação de chaves GPG e configuração do repositório oficial do pgAdmin 4
- [ ] **08 )** - Instalação dos pacotes do pgAdmin 4 nos modos Desktop e Web (`pgadmin4-desktop`, `pgadmin4-web`)
- [ ] **09 )** - Configuração e provisionamento do servidor web local do pgAdmin (`setup-web.sh`)
- [ ] **10 )** - Registro de servidor no pgAdmin 4 e conexão com a instância local (Host, Porta 5432, Autenticação)
- [ ] **11 )** - Diagnóstico de conectividade de rede, verificação da porta 5432 com `ss` e teste via CLI
- [ ] **12 )** - Orquestração alternativa conteinerizada via Docker Compose (PostgreSQL + pgAdmin 4)

---

```ad-done
title:
#### **Fase 1 ) - Instalação e Configuração do Servidor PostgreSQL**
```

---

````ad-quote
title:

##### **01 )** - Servidor Relacional PostgreSQL e Serviços do Sistema

```ad-quote
title:
<p align="justify">O PostgreSQL é um dos sistemas de gerenciamento de banco de dados objeto-relacionais mais avançados e robustos do mercado. Sua instalação em ambientes Linux configura automaticamente um daemon de sistema (systemd) em execução em segundo plano na porta padrão 5432, além de criar um usuário de sistema dedicado chamado postgres para isolamento de segurança.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Passo a Passo de Instalação e Serviços_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Instalação dos Pacotes Essenciais*
```

```bash
01 ) Atualização dos Índices de Pacotes
# Atualiza os índices locais do sistema operacional antes da instalação
sudo apt update && sudo apt upgrade -y


02 ) Instalação do PostgreSQL e Utilitários Contrib
# Instala o core do servidor PostgreSQL e o pacote contrib (extensões e recursos adicionais)
sudo apt install postgresql postgresql-contrib -y


03 ) Habilitação e Inicialização do Serviço
# Habilita o início automático com o boot do sistema e inicializa o daemon do PostgreSQL
sudo systemctl enable postgresql
sudo systemctl start postgresql


04 ) Verificação do Status do Serviço
# Confirma se o processo está em execução ativa (active/running)
sudo systemctl status postgresql
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Configuração de Credenciais e Superusuário via psql*
```

```bash
01 ) Acesso ao Usuário Postgres do Sistema
# O PostgreSQL utiliza por padrão o método de autenticação 'peer', mapeando o usuário do SO
sudo -i -u postgres


02 ) Abertura do Console Interativo psql
# Inicia a interface de linha de comando do PostgreSQL
psql


03 ) Definição da Senha do Superusuário postgres
# Define a senha que será exigida na conexão gráfica do pgAdmin 4
ALTER USER postgres WITH PASSWORD 'sua_senha_segura';


04 ) Criação de Banco de Dados e Usuário de Aplicação (Opcional/Recomendado)
# Cria um banco de dados de desenvolvimento e um usuário com privilégios restritos
CREATE DATABASE meu_banco;
CREATE USER desenvolvedor WITH ENCRYPTED PASSWORD 'senha_dev';
GRANT ALL PRIVILEGES ON DATABASE meu_banco TO desenvolvedor;


05 ) Encerramento da Sessão no psql e Retorno ao Usuário Padrão
# Encerra o interpretador psql e depois sai da sessão do usuário postgres
\q
exit
```
````

---

```ad-done
title:
#### **Fase 2 ) - Instalação e Configuração do pgAdmin 4**
```

---

````ad-quote
title:

##### **02 )** - Interface Gráfica Administrativa (pgAdmin 4)

```ad-quote
title:
<p align="justify">O pgAdmin 4 é a plataforma oficial e mais consagrada para administração visual do PostgreSQL. Ele permite inspecionar esquemas, tabelas, índices e triggers, executar comandos SQL em Query Tools interativas, visualizar planos de execução e monitorar conexões ativas e métricas de desempenho em tempo real.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Configuração de Repositório e Instalação_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Configuração do Repositório Oficial do pgAdmin*
```

```bash
01 ) Instalação de Utilitários de Transporte e Chave Pública GPG
# Instala o curl e adiciona a chave oficial de assinatura do repositório pgAdmin
sudo apt install curl ca-certificates gnupg -y
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg


02 ) Adição do Repositório Oficial às Fontes APT
# Cria o arquivo de configuração de repositório vinculado à chave assinada
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list'


03 ) Atualização das Listas de Pacotes do Sistema
# Atualiza os índices do APT para incluir os pacotes do novo repositório
sudo apt update
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Opções de Instalação e Assistente Web*
```

```bash
01 ) Opção 1: Instalação Completa (Recomendada: Desktop e Web)
# Instala tanto a interface autônoma de desktop quanto o servidor web local
sudo apt install pgadmin4 -y


02 ) Opção 2: Instalação Apenas do Modo Desktop
# Instala somente o aplicativo nativo de janela desktop
sudo apt install pgadmin4-desktop -y


03 ) Opção 3: Instalação Apenas do Modo Web
# Instala o serviço web do pgAdmin para acesso via navegador
sudo apt install pgadmin4-web -y


04 ) Configuração do Ambiente Web (Necessário ao utilizar pgadmin4 ou pgadmin4-web)
# Executa o assistente oficial para criar a conta de login (e-mail e senha) e configurar o servidor web
sudo /usr/pgadmin4/bin/setup-web.sh
```
````

---

```ad-done
title:
#### **Fase 3 ) - Conexão e Navegação no pgAdmin 4**
```

---

````ad-quote
title:

##### **03 )** - Registro de Servidor e Primeiros Passos

```ad-quote
title:
<p align="justify">Com o serviço do PostgreSQL ativo na porta local 5432 e o pgAdmin 4 instalado, o passo final consiste em cadastrar a instância do servidor local na árvore de objetos (Object Explorer) utilizando as credenciais previamente configuradas.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Parâmetros de Conexão e Validação_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Passo a Passo de Conexão no pgAdmin 4*
```

```bash
01 ) Inicialização do pgAdmin 4
# Modo Desktop: abra pelo lançador do sistema procurando por "pgAdmin 4"
# Modo Web: acesse pelo navegador web no endereço http://127.0.0.1/pgadmin4


02 ) Definição da Senha Mestra (Master Password)
# Na primeira inicialização, o pgAdmin solicitará uma Master Password para proteger as senhas salvas


03 ) Registro do Novo Servidor
# No painel lateral esquerdo (Object Explorer), clique com o botão direito em:
# Servers -> Register -> Server...


04 ) Preenchimento da Aba "General"
# Name: PostgreSQL Local (ou qualquer identificador descritivo)


05 ) Preenchimento da Aba "Connection"
# Host name/address: localhost (ou 127.0.0.1)
# Port: 5432
# Maintenance database: postgres
# Username: postgres
# Password: <senha definida anteriormente no comando ALTER USER postgres>
# Marque a caixa "Save password" para não solicitar a cada reconexão


06 ) Salvamento e Exploração
# Clique em "Save". A árvore do servidor exibirá os Databases, Schemas, Tables e Ferramentas de Query
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Diagnóstico de Conexão e Comandos Úteis do psql*
```

```bash
01 ) Teste de Conexão por Rede Local via Terminal
# Valida se a porta TCP 5432 está aceitando conexões autenticadas
psql -h localhost -p 5432 -U postgres -d postgres


02 ) Verificação da Porta 5432 em Escuta
# Inspeciona os sockets do sistema para confirmar que o PostgreSQL está escutando conexões
sudo ss -tulpn | grep 5432


03 ) Comandos Essenciais no Console psql
# \l          -> Lista todos os bancos de dados do cluster
# \c <banco>  -> Alterna a conexão para o banco de dados especificado
# \dt         -> Lista todas as tabelas do esquema ativo (public)
# \du         -> Lista os usuários/roles e seus respectivos privilégios
# \conninfo   -> Exibe detalhes da conexão ativa (usuário, host, porta e protocolo)
# \q          -> Encerra o terminal psql
```
````

---

```ad-done
title:
#### **Fase 4 ) - Alternativa Conteinerizada com Docker Compose**
```

---

````ad-quote
title:

##### **04 )** - Ambiente Isolado com Docker (Opcional)

```ad-quote
title:
<p align="justify">Para fluxos de desenvolvimento modernos que dispensam a instalação direta de pacotes no sistema operacional hospedeiro, o Docker Compose oferece uma solução rápida e reprodutível que sobe simultaneamente o servidor PostgreSQL e a interface pgAdmin 4 em containers isolados.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.1 ) - _Estruturação do docker-compose.yml_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Arquivo de Orquestração (docker-compose.yml)*
```

```yaml
version: '3.8'

services:
  postgres:
    image: postgres:16-alpine
    container_name: postgres_db
    restart: always
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: sua_senha_segura
      POSTGRES_DB: meu_banco
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data

  pgadmin:
    image: dpage/pgadmin4:latest
    container_name: pgadmin_ui
    restart: always
    environment:
      PGADMIN_DEFAULT_EMAIL: admin@admin.com
      PGADMIN_DEFAULT_PASSWORD: admin
    ports:
      - "5050:80"
    depends_on:
      - postgres

volumes:
  postgres_data:
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos de Ciclo de Vida dos Containers*
```

```bash
01 ) Inicialização dos Containers em Segundo Plano
# Baixa as imagens oficiais e inicializa os serviços em background
docker compose up -d


02 ) Monitoramento dos Logs de Execução
# Acompanha a saída do banco e do pgAdmin em tempo real
docker compose logs -f


03 ) Acesso ao pgAdmin no Navegador
# Acesse http://localhost:5050 utilizando:
# E-mail: admin@admin.com | Senha: admin
# Ao registrar o servidor, no campo Host name utilize o nome do serviço: postgres


04 ) Parada e Destruição dos Containers (Preservando os Dados no Volume)
# Interrompe os containers sem perder os dados armazenados
docker compose down
```
````

---
