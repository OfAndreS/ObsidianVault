---
banner: "- FILES/Attachments/Pasted image 20261012205745.png"
banner-x: 50
banner-y: 35
banner-fade: 100
---
---
#### **Intro )** - 02 (Endpoints, Path, Query, Body, Headers & HTTP Verbs)

```ad-quote
title: **Def**
**Summary:**
- Como o FastAPI extrai dados de requisições HTTP e os mapeia diretamente para variáveis tipadas de funções Python. Esta nota detalha o funcionamento dos parâmetros de rota, parâmetros de consulta, corpos de requisição (JSON payloads), leitura de metadados em cabeçalhos HTTP e emissão de status codes semânticos.
```

---
#### 📋 Checklist de Estudos - Tópicos a Cobrir

- [ ] **01 )** - Verbos HTTP principais e decoradores de rota (`@app.get`, `@app.post`, `@app.put`, `@app.delete`, `@app.patch`)

---

- [ ] **02 )** - Parâmetros de Rota (*Path Parameters*) com tipagem estrita (`/itens/{item_id: int}`)

---

- [ ] **03 )** - Conversão e coerção automática de tipos com emissão de erro 422 caso a tipagem falhe

---

- [ ] **04 )** - Ordem de declaração de rotas (rotas estáticas devem vir antes de rotas com parâmetros dinâmicos)

---

- [ ] **05 )** - Parâmetros de Consulta (*Query Parameters*) com valores padrão e campos opcionais (`Optional[str] = None`)

---

- [ ] **06 )** - Validação de Query Params com a classe `Query()` (`min_length`, `max_length`, `regex`, `gt`, `le`)

---

- [ ] **07 )** - Corpo da Requisição (*Request Body*) básico com a classe `Body()`

---

- [ ] **08 )** - Extração de Metadados de Requisição com `Header()` e `Cookie()`

---

- [ ] **09 )** - Conversão automática de nomes de headers (hífen para underline em Python)

---

- [ ] **10 )** - Definição de Códigos de Status HTTP semânticos via `status_code=status.HTTP_201_CREATED`

---

- [ ] **11 )** - Lançamento de erros e interrupção controlada de fluxo com `HTTPException(status_code=404, detail="...")`

---

- [ ] **12 )** - Retorno de respostas tipadas com `Response` e tipos especializados (`JSONResponse`, `RedirectResponse`)

---

#### Princípios básicos

##### Matching dos endpoints

Para descobrir qual endpoint corresponde à requisição do usuário, o FastAPI adota uma abordagem Top-Down. Durante a inicialização do servidor, as rotas são lidas e registradas em memória em uma lista ordenada. Quando uma requisição chega, o sistema avalia essas rotas na ordem em que foram declaradas até encontrar uma que corresponda ao padrão digitado. Caso nenhuma rota seja compatível após esgotar a lista, o sistema retorna um erro HTTP 404 (Recurso Não Encontrado).

##### Casso de fracasso

```python
from fastapi import FastAPI

app = FastAPI()

# O servidor lê esta rota primeiro na inicialização
@app.get("/usuarios/{usuario_id}")
def obter_usuario(usuario_id: str):
    return {"mensagem": f"Buscando o usuário com ID: {usuario_id}"}

# Esta rota NUNCA será alcançada!
@app.get("/usuarios/me")
def obter_usuario_atual():
    return {"mensagem": "Este é o seu próprio perfil de usuário"}
```

O que acontece se o usuário acessar `/usuarios/me`?  Como o FastAPI avalia de cima para baixo a lista gravada na inicialização, ele para na primeira rota que "casa" com o padrão. Ele vai achar que você está tentando buscar um usuário cujo ID é a string `"me"`.  O retorno será: `{"mensagem": "Buscando o usuário com ID: me"}` (em vez de mostrar o perfil atual).

##### Caso de sucesso - respeitando o Top-Down

Agora sim: se o usuário digitar `/usuarios/me`, o FastAPI bate na primeira rota, encontra a correspondência exata e já retorna a resposta imediatamente. Se ele digitar `/usuarios/123`, a primeira não serve, ele passa para a de baixo, valida o parâmetro e responde corretamente.

```python
from fastapi import FastAPI

app = FastAPI()

# 1º: Rota específica (avaliada primeiro)
@app.get("/usuarios/me")
def obter_usuario_atual():
    return {"mensagem": "Este é o seu próprio perfil de usuário"}

# 2º: Rota genérica com parâmetro (avaliada se a de cima não bater)
@app.get("/usuarios/{usuario_id}")
def obter_usuario(usuario_id: str):
    return {"mensagem": f"Buscando o usuário com ID: {usuario_id}"}
```

##### Conversão automática para JSON

O FastAPI **converte automaticamente a maioria dos retornos de função** (como dicionários, listas e modelos Pydantic) para o formato JSON. Dessa forma, o programador **quase nunca** precisa se preocupar com a formatação final dos dados, focando principalmente na lógica a ser aplicada no endpoint.

##### Caso de fracasso

Se você tentar retornar um objeto de uma classe personalizada que não herda do Pydantic, ou objetos complexos do sistema (como arquivos abertos, conexões de banco de dados ou datas sem formatação), o FastAPI não saberá como converter aquilo para JSON e o código vai quebrar.

```python
from fastapi import FastAPI

app = FastAPI()

# Uma classe Python comum (não é um modelo Pydantic)
class Pessoa:
    def __init__(self, nome: str, idade: int):
        self.nome = nome
        self.idade = int(idade)

@app.get("/pessoa-erro")
def obter_pessoa():
    usuario = Pessoa(nome="Carlos", idade=30)
    
    # FALHA AQUI: O FastAPI não sabe como converter o objeto 'Pessoa' diretamente para JSON
    return usuario 
```

Ao acessar esse endpoint, o FastAPI vai gerar um erro interno (Internal Server Error - HTTP 500) e você verá um erro parecido com este no terminal:

```shell
ValueError: [TypeError('Object of type Pessoa is not JSON serializable'), ...]
```

##### Caso de sucesso

Se você retornar estruturas de dados nativas (como dicionários) ou modelos do Pydantic, o FastAPI faz toda a mágica de conversão para JSON nos bastidores. O programador só se preocupa com a lógica.

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class Produto(BaseModel):
    id: int
    nome: str
    preco: float

@app.get("/produto-sucesso")
def obter_produto():
    # O FastAPI converte automaticamente este modelo Pydantic para JSON
    return Produto(id=1, nome="Notebook", preco=4500.00)
```

Resultado: O cliente recebe um JSON perfeito: 

```shell
{"id": 1, "nome": "Notebook", "preco": 4500.0}
```

---
---

#### Implementação dos métodos HTTP

![[Pasted image 20261012105808.png]]

---

- Todo método precisa de ter status code correspondente a ação que ele está tentando realizar.

```embed
title: "HTTP response status codes - HTTP | MDN"
image: ""
description: "HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:"
url: "https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status"
favicon: ""
```

---
##### Método Post

https://fastapi.tiangolo.com/tutorial/body/

Um método POST básico precisa receber os dados do cliente e armazená-los em uma estrutura de dados utilizando um ID. No FastAPI, utilizamos alguns recursos para implementar esse fluxo. A biblioteca Pydantic fica responsável pela validação e padronização da entrada, enquanto o módulo UUID gera os IDs únicos.

```python
from uuid import UUID, uuid4

from fastapi import FastAPI, status
from pydantic import BaseModel, Field

app = FastAPI()

class PostSchema(BaseModel):
	title: str
	content: str


class PostResponse(PostSchema):
    id: UUID


my_posts: list[PostResponse] = []


@app.post("/posts", response_model=PostResponse)	
def create_post(payload: PostSchema):
	new_post = PostResponse(id=uuid4(), **payload.model_dump())
    my_posts.append(new_post)
    return new_post
``` 


