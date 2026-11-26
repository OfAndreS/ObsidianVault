---
banner: "- FILES/Attachments/Pasted image 20260712203132.png"
banner-x: 50
banner-y: 35
banner-fade: 100
---

---

#### **Intro )** - Arquitetura, Segurança e Injeção de Dependências no FastAPI — 05 (Dependency Injection, APIRouter, OAuth2, JWT & Middleware)

```ad-quote
title: **Def**
**Summary:**
- Como estruturar projetos FastAPI de grande porte e com nível de produção. Esta nota aborda a divisão em múltiplos módulos usando APIRouter, o poderoso sistema nativo de Injeção de Dependências (Depends), controle de acesso e autenticação com OAuth2 e tokens JWT (JSON Web Tokens), middlewares globais de CORS e tarefas assíncronas em background.
```

---

### 📋 Checklist de Estudos - Tópicos a Cobrir

- [ ] **01 )** - Modularização com `APIRouter` para separar recursos em múltiplos arquivos (`prefix`, `tags`, `responses`)
- [ ] **02 )** - Acoplamento de sub-roteadores na aplicação principal com `app.include_router()`
- [ ] **03 )** - O padrão de Injeção de Dependências (*Dependency Injection*) com o helper `Depends()`
- [ ] **04 )** - Reutilização e composição de dependências aninhadas (dependências que dependem de outras dependências)
- [ ] **05 )** - Dependências globais aplicadas em nível de roteador ou na aplicação inteira (`dependencies=[Depends(...)]`)
- [ ] **06 )** - Criptografia unidirecional de senhas com `passlib[bcrypt]` ou `bcrypt`
- [ ] **07 )** - Fluxo de autenticação OAuth2 com formulário de requisição padrão (`OAuth2PasswordRequestForm`)
- [ ] **08 )** - Geração de tokens de acesso JWT (*JSON Web Tokens*) com tempo de expiração (`exp`, `sub`) via biblioteca `python-jose` ou `PyJWT`
- [ ] **09 )** - Esquema de segurança `OAuth2PasswordBearer(tokenUrl="token")` para extrair o token do cabeçalho `Authorization: Bearer <token>`
- [ ] **10 )** - Criação da dependência guardiã `get_current_user` para proteger rotas privadas
- [ ] **11 )** - Configuração de Middleware de CORS (`CORSMiddleware`) para permitir requisições de frontends (React/Vue)
- [ ] **12 )** - Execução de tarefas não bloqueantes em segundo plano com `BackgroundTasks` (envio de emails, logs assíncronos)

---

```ad-done
title:
#### **Fase 1 ) - Modularização com APIRouter**
```

---

````ad-quote
title:

##### **01 )** - Divisão em Sub-módulos

```ad-quote
title:
<p align="justify">Em vez de concentrar todos os endpoints no arquivo <code>main.py</code>, utiliza-se <code>APIRouter</code> para isolar cada domínio (ex: usuários, produtos, pedidos) em seu próprio módulo, organizando tags e prefixos na documentação Swagger.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Implementação de Roteador Dedicado_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Arquivo de Rotas (routers/users.py)*
```

```python
from fastapi import APIRouter

router = APIRouter(
    prefix="/usuarios",
    tags=["Usuários"]
)

@router.get("/")
def listar_usuarios():
    return [{"id": 1, "nome": "Alice"}, {"id": 2, "nome": "Bob"}]

@router.get("/{user_id}")
def obter_usuario(user_id: int):
    return {"id": user_id, "nome": "Alice"}
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Registro no Arquivo Principal (main.py)*
```

```python
from fastapi import FastAPI
from routers import users

app = FastAPI(title="API Modular")

# Conecta o sub-roteador à aplicação principal
app.include_router(users.router)
```
````

---

```ad-done
title:
#### **Fase 2 ) - Autenticação JWT com OAuth2**
```

---

````ad-quote
title:

##### **02 )** - Barreira de Segurança e Tokens Criptográficos

```ad-quote
title:
<p align="justify">O cliente envia credenciais de login e recebe um token JWT assinado criptograficamente. Todas as requisições subsequentes a rotas protegidas devem enviar o token no cabeçalho <code>Authorization: Bearer &lt;token&gt;</code>, validado automaticamente via injeção de dependência.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Guardião de Rota com Depends_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Dependência get_current_user*
```

```python
from fastapi import Depends, HTTPException, status
from fastapi.security import OAuth2PasswordBearer
import jwt

SECRET_KEY = "chave_secreta_super_segura"
ALGORITHM = "HS256"

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

def get_current_user(token: str = Depends(oauth2_scheme)):
    try:
        payload = jwt.decode(token, SECRET_KEY, algorithms=[ALGORITHM])
        username: str = payload.get("sub")
        if username is None:
            raise HTTPException(
                status_code=status.HTTP_401_UNAUTHORIZED,
                detail="Token inválido"
            )
        return {"username": username}
    except jwt.PyJWTError:
        raise HTTPException(
            status_code=status.HTTP_401_UNAUTHORIZED,
            detail="Credenciais inválidas ou expiradas",
            headers={"WWW-Authenticate": "Bearer"},
        )
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Protegendo um Endpoint Privado*
```

```python
from fastapi import FastAPI, Depends

app = FastAPI()

# O endpoint exige que o usuário esteja autenticado com token válido
@app.get("/painel/privado")
def acessar_painel(current_user: dict = Depends(get_current_user)):
    return {
        "mensagem": "Acesso autorizado ao painel corporativo",
        "usuario_logado": current_user["username"]
    }
```
````

---
