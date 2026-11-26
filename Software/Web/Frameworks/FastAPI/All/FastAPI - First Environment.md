---
banner: "- FILES/Attachments/Pasted image 20261012205745.png"
banner-x: 50
banner-y: 35
banner-fade: 100
---

---

#### **Intro )** - Ambiente e Execução no FastAPI — 01 (Conda, Uvicorn, ASGI, Setup, Anatomy & Reload)

```ad-quote
title: **Def**
**Summary:**
- Configuração do ecossistema de desenvolvimento para APIs com FastAPI. Esta nota aborda desde o isolamento de dependências com Conda/venv até a execução do servidor assíncrono Uvicorn com live-reload, além da exploração da documentação automática OpenAPI (Swagger UI e ReDoc).
```

---

### 📋 Checklist de Estudos - Tópicos a Cobrir

- [ ] **01 )** - O que é o padrão ASGI (Asynchronous Server Gateway Interface) e por que ele supera o WSGI
- [ ] **02 )** - Isolamento do ambiente com Conda (`conda create --name FastAPI python=3.11`)
- [ ] **03 )** - Ativação do ambiente e gerenciamento de dependências (`fastapi` e `uvicorn`)
- [ ] **04 )** - Instalação de utilitários de produção (`uvicorn[standard]`)
- [ ] **05 )** - Instanciação da aplicação principal com `app = FastAPI()`
- [ ] **06 )** - Criação do primeiro endpoint raiz (`@app.get("/")`) retornando JSON nativo
- [ ] **07 )** - Execução do servidor via linha de comando (`uvicorn main:app --reload`)
- [ ] **08 )** - Parâmetros do Uvicorn (`--host`, `--port`, `--reload`, `--workers`)
- [ ] **09 )** - Acesso e navegação na documentação interativa Swagger UI (`/docs`)
- [ ] **10 )** - Acesso à documentação alternativa ReDoc (`/redoc`)
- [ ] **11 )** - Anatomia recomendada de pastas para projetos em FastAPI
- [ ] **12 )** - Boas práticas de congelamento de dependências com `requirements.txt` ou `environment.yml`

---

```ad-done
title:
#### **Fase 1 ) - Instalação e Isolamento do Ambiente**
```

---

````ad-quote
title:

##### **01 )** - Criação do Ambiente Virtual com Conda

```ad-quote
title:
<p align="justify">O isolamento do interpretador Python e de suas bibliotecas garante que as versões dos pacotes não conflitem com outros projetos na mesma máquina.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Passo a Passo de Instalação_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Criação e Ativação do Ambiente*
```

```bash
01 ) Criação do Ambiente Isolado
# Cria um ambiente Python 3.11 dedicado via Conda
conda create --name FastAPI python=3.11 -y


02 ) Ativação do Ambiente
# Ativa o interpretador dedicado do projeto
conda activate FastAPI


03 ) Instalação do FastAPI e Servidor ASGI Uvicorn
# Instala os pacotes essenciais via canal conda-forge ou pip
conda install -c conda-forge fastapi uvicorn -y
```
````

---

```ad-done
title:
#### **Fase 2 ) - Aplicação Base e Servidor Uvicorn**
```

---

````ad-quote
title:

##### **02 )** - Inicialização e Ciclo de Execução

```ad-quote
title:
<p align="justify">O FastAPI conecta o código Python a um servidor ASGI assíncrono de altíssima performance chamado Uvicorn. O Uvicorn monitora alterações no código e reinicia o processo automaticamente durante o desenvolvimento.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Código e Inicialização_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Código da Aplicação (main.py)*
```

```python
from fastapi import FastAPI

app = FastAPI(
    title="Minha Primeira API",
    description="API inicial configurada com FastAPI e Uvicorn",
    version="1.0.0"
)

@app.get("/")
def read_root():
    return {"mensagem": "Servidor FastAPI ativo com sucesso!", "status": "online"}
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comando de Execução do Servidor*
```

```bash
01 ) Comando de Execução em Desenvolvimento
# Primeira palavra (main): nome do arquivo Python sem a extensão .py
# Segunda palavra (app): nome da variável instanciada do FastAPI dentro do arquivo
# Flag (--reload): reinicia o servidor automaticamente a cada salvamento de código
uvicorn main:app --reload


02 ) Customização de Porta e Host
# Permite acesso externo ou define portas customizadas
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```
````

---

```ad-done
title:
#### **Fase 3 ) - Documentação Interativa Automática**
```

---

````ad-quote
title:

##### **03 )** - Swagger UI e ReDoc Nativos

```ad-quote
title:
<p align="justify">O FastAPI lê os tipos do Python e gera automaticamente a especificação OpenAPI da sua API, oferecendo duas interfaces gráficas de teste prontas sem nenhuma linha extra de código.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Rotas de Documentação_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Endpoints de Visualização no Navegador*
```

```bash
01 ) Swagger UI (Interativo)
# http://127.0.0.1:8000/docs
# Permite testar endpoints diretamente pela interface com o botão "Try it out"


02 ) ReDoc (Documentação Técnica Limpa)
# http://127.0.0.1:8000/redoc
# Layout organizado focado em consulta para desenvolvedores e integração de terceiros


03 ) JSON OpenAPI Bruto
# http://127.0.0.1:8000/openapi.json
# Contrato formal OpenAPI 3.0 utilizado para gerar SDKs e clientes automaticamente
```
````

---
