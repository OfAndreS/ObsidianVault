---
banner: "- FILES/Attachments/Pasted image 20261012205745.png"
banner-x: 50
banner-y: 35
banner-fade: 100
---
---

````ad-quote
title:

##### **Intro )** - Validação de Dados e Schemas no FastAPI

```ad-quote
title:
<p align="justify">A base do FastAPI é a biblioteca Pydantic, responsável pela validação rigorosa de dados de entrada, garantia de tipos e serialização de saída em JSON. Esta nota aborda a definição de esquemas com BaseModel, restrições com Field, validações personalizadas com decoradores e a separação arquitetural de contratos de entrada e saída.</p>
```
````

---

```ad-done
title:
#### **Fase 1 ) - Fundamentos do Pydantic V2**
```

---

````ad-quote
title:

##### **01 )** - O Pydantic

```ad-quote
title:
<p align="justify">O Pydantic serve para validar todos os dados externos que chegam até a sua aplicação. Para realizar tal tarefa ele converte os tipos quando necessário, garante que formatos específicos como datas, e-mails ou URLs estão sendo seguidos e faz uma documentação preliminar de forma rápida.</p>
```

```bash
# INSTALAÇÃO
pip install "pydantic[email]"
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Modelo Base_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O Pydantic valida os dados por meio de esquemas baseados em classes que herdam de BaseModel. Para que a validação funcione, o nome de cada atributo da classe deve ser igual ao nome da chave correspondente no dado recebido. Você também deve declarar o tipo de dado de cada atributo.</p>
```

```python
from pydantic import BaseModel

class Usuario(BaseModel):
    id: int
    nome: str
    email: str
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Exemplo*
```

```ad-quote
title:
<p align="justify">No exemplo abaixo, o modelo Usuario valida um dicionário Python com dados pessoais. Cada chave do dicionário tem o mesmo nome de um atributo do modelo. O campo id recebe o texto "10", mas o Pydantic converte esse valor para o número inteiro 10 automaticamente.</p>
```

```python
dados = {"id": "10", "nome": "Ana", "email": "ana@exemplo.com"}

u = Usuario.model_validate(dados)
print(u)

# Saída:
# id=10 nome='Ana' email='ana@exemplo.com'
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _Range de Valores_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Além de definir o tipo de cada atributo, o Pydantic também permite criar outras restrições, como a quantidade de itens em uma lista, o tamanho de uma string ou o intervalo permitido para um número. Para aplicar esses critérios, basta atribuir a função Field ao campo desejado.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Parâmetros*
```

```bash
01 ) default - Qualquer
# Define um valor fixo caso o dado não seja enviado
# Field(default="Ativo")

02 ) gt / ge - Números
# Exige valor maior (gt) ou maior/igual (ge) ao limite
# Field(gt=0)

03 ) lt / le - Números
# Exige valor menor (lt) ou menor/igual (le) ao limite
# Field(le=100)

04 ) min_length / max_length - Texto / Coleções
# Define a quantidade mínima ou máxima de caracteres ou itens
# Field(min_length=3, max_length=50)

05 ) pattern - Texto
# Valida o formato da string com uma expressão regular (Regex)
# Field(pattern=r"^\d{3}$")

06 ) alias - Texto
# Mapeia o atributo para uma chave com nome diferente no dado original
# Field(alias="codigo_usuario")

07 ) default_factory - Função (Callable)
# Gera um valor padrão dinâmico no momento da criação do objeto
# Field(default_factory=list)

08 ) description - Texto
# Adiciona uma explicação sobre o campo na documentação do esquema
# Field(description="Preço final do produto em reais")

09 ) frozen - Booleano
# Impede a alteração do valor do atributo após a criação do objeto
# Field(frozen=True)
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Exemplo*
```

```ad-quote
title:
<p align="justify">No exemplo abaixo, o modelo Produto valida um dicionário Python utilizando as restrições da função Field. O parâmetro alias mapeia a chave "codigo_produto" do dicionário diretamente para o atributo id da classe. Além disso, o dicionário omite os campos estoque e tags, mas o Pydantic preenche esses atributos automaticamente com seus valores padrão.</p>
```

```python
from pydantic import BaseModel, Field

class Produto(BaseModel):
    id: int = Field(alias="codigo_produto", gt=0)
    nome: str = Field(min_length=3, max_length=50)
    preco: float = Field(gt=0, description="Preço em reais")
    estoque: int = Field(default=0, ge=0)
    tags: list[str] = Field(default_factory=list)

dados_entrada = {
    "codigo_produto": 105,
    "nome": "Teclado Mecânico",
    "preco": 250.00
}

item = Produto.model_validate(dados_entrada)
print(item)
# Saída: id=105 nome='Teclado Mecânico' preco=250.0 estoque=0 tags=[]
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.3 ) - _Campos Opcionais_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">No Pydantic V2, um campo opcional exige um valor padrão (= None), enquanto um campo anulável exige a união de tipos (| None). Pense em um formulário de cadastro: deixar um campo em branco equivale a ser anulável (nullable, representado com | None), enquanto nem sequer enviar o campo na requisição equivale a ser opcional (not required, representado definindo um valor padrão com =).</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Exemplo*
```

```ad-quote
title:
<p align="justify">O modelo PerfilUsuario combina um campo obrigatório com diferentes variações de campos opcionais: simples, com restrições de tamanho/valor via Field e listas dinâmicas com default_factory.</p>
```

```python
from pydantic import BaseModel, Field

class PerfilUsuario(BaseModel):
    username: str
    apelido: str | None = None
    biografia: str | None = Field(default=None, max_length=160)
    idade: int | None = Field(default=None, ge=18)
    interesses: list[str] = Field(default_factory=list)

usuario_basico = PerfilUsuario.model_validate({"username": "andre_dev"})
print(usuario_basico)
# Saída: username='andre_dev' apelido=None biografia=None idade=None interesses=[]
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.4 ) - _Modelos Aninhados e Tipos Especiais_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Para representar estruturas JSON hierárquicas, um BaseModel pode ser utilizado como tipo de atributo dentro de outro modelo (Nested Models). Além disso, o Pydantic fornece tipos especializados como EmailStr, HttpUrl e UUID que validam formatos complexos automaticamente.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Exemplo*
```

```ad-quote
title:
<p align="justify">O modelo Empresa utiliza o modelo Endereco como atributo aninhado e valida simultaneamente o identificador único (UUID), o endereço de e-mail e a URL do site.</p>
```

```python
from uuid import UUID
from pydantic import BaseModel, EmailStr, HttpUrl

class Endereco(BaseModel):
    cidade: str
    cep: str

class Empresa(BaseModel):
    id: UUID
    email_contato: EmailStr
    site: HttpUrl
    endereco: Endereco

dados_empresa = {
    "id": "123e4567-e89b-12d3-a456-426614174000",
    "email_contato": "contato@empresa.com.br",
    "site": "https://empresa.com.br",
    "endereco": {"cidade": "São Paulo", "cep": "01001-000"}
}

emp = Empresa.model_validate(dados_empresa)
print(emp.endereco.cidade)  # Saída: São Paulo
```
````

---

```ad-done
title:
#### **Fase 2 ) - Validações Customizadas**
```

---

````ad-quote
title:

##### **02 )** - Validadores de Regras de Negócio

```ad-quote
title:
<p align="justify">Quando as restrições declarativas do Field não são suficientes para expressar uma regra de negócio específica da aplicação, o Pydantic V2 permite criar funções validadoras personalizadas por meio de decoradores.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Validador de Campo_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O decorador @field_validator intercepta e valida um atributo específico de forma isolada. Se a regra falhar, a função deve lançar um ValueError; se passar, deve retornar o valor validado ou transformado.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Exemplo*
```

```ad-quote
title:
<p align="justify">O validador abaixo impede que o campo username contenha espaços em branco e padroniza o texto recebido convertendo todos os caracteres para letras minúsculas.</p>
```

```python
from pydantic import BaseModel, field_validator

class ContaUsuario(BaseModel):
    username: str

    @field_validator("username")
    @classmethod
    def validar_username(cls, valor: str) -> str:
        if " " in valor:
            raise ValueError("O username não pode conter espaços em branco")
        return valor.lower()
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Validador de Modelo_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O decorador @model_validator(mode="after") é executado após todos os campos individuais terem sido validados. Ele recebe a instância completa do objeto (self), permitindo cruzar informações entre dois ou mais atributos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Exemplo*
```

```ad-quote
title:
<p align="justify">O modelo CadastroSenha compara os campos senha e confirmar_senha após a leitura inicial dos dados, garantindo que ambos possuam exatamente o mesmo conteúdo.</p>
```

```python
from pydantic import BaseModel, model_validator

class CadastroSenha(BaseModel):
    senha: str
    confirmar_senha: str

    @model_validator(mode="after")
    def conferir_senhas_iguais(self) -> "CadastroSenha":
        if self.senha != self.confirmar_senha:
            raise ValueError("As senhas informadas não coincidem")
        return self
```
````

---

```ad-done
title:
#### **Fase 3 ) - Pydantic no FastAPI**
```

---

````ad-quote
title:

##### **03 )** - Segregação de Contratos

```ad-quote
title:
<p align="justify">No desenvolvimento de APIs, os dados que o usuário envia são diferentes dos dados que a API retorna. Usar um único modelo para tudo expõe dados sensíveis (como senhas) ou exige que o usuário envie dados gerados pelo sistema (como o id). Por isso, dividimos os modelos de acordo com o papel de cada operação HTTP.</p>
```

```python
@app.patch("/usuarios/{usuario_id}", response_model=UsuarioResponse)
def atualizar_usuario(usuario_id: int, dados: UsuarioUpdate):
    usuario_db = {
        "id": usuario_id,
        "nome": "Ana",
        "email": "ana@exemplo.com",
        "senha": "hash_super_secreto_123"
    }

    # Extrai apenas os campos que o cliente enviou na requisição JSON
    dados_enviados = dados.model_dump(exclude_unset=True)

    # Atualiza apenas as chaves presentes em dados_enviados
    usuario_db.update(dados_enviados)

    # O FastAPI filtra "senha" automaticamente graças ao response_model
    return usuario_db
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Modelo Base_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O Modelo Base reúne os atributos comuns compartilhados por todas as operações daquele recurso, servindo como superclasse para evitar repetição de código.</p>
```

```python
from pydantic import BaseModel, Field

class UsuarioBase(BaseModel):
    nome: str = Field(min_length=3, max_length=50)
    email: str
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.2 ) - _Modelo Create_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O Modelo Create valida os dados de entrada exigidos apenas no momento do cadastro (POST). Ele herda os atributos básicos e adiciona campos sensíveis, como a senha, que jamais devem sair da API.</p>
```

```python
class UsuarioCreate(UsuarioBase):
    senha: str = Field(min_length=8)
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.3 ) - _Modelo Response_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O Modelo Response filtra e formata os dados de saída (GET e retorno de POST/PATCH). Ele omite a senha, inclui o id gerado pelo banco e configura from_attributes=True para permitir a leitura direta de objetos ORM como o SQLAlchemy.</p>
```

```python
from pydantic import ConfigDict

class UsuarioResponse(UsuarioBase):
    id: int
    model_config = ConfigDict(from_attributes=True)
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.4 ) - _Modelo Update_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O Modelo Update valida atualizações parciais (PATCH), onde todos os campos são declarados como opcionais para que o cliente envie apenas o que deseja alterar.</p>
```

```python
class UsuarioUpdate(BaseModel):
    nome: str | None = Field(default=None, min_length=3, max_length=50)
    email: str | None = None
    senha: str | None = Field(default=None, min_length=8)
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.5 ) - _Erro 422 - Unprocessable Entity_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Quando o cliente envia um dado que viola qualquer regra do Pydantic, o FastAPI interrompe a execução da rota e devolve automaticamente uma resposta HTTP 422 Unprocessable Entity contendo a lista detalhada de falhas no corpo JSON.</p>
```

```json
{
  "detail": [
    {
      "type": "string_too_short",
      "loc": ["body", "nome"],
      "msg": "String should have at least 3 characters",
      "input": "An",
      "ctx": {
        "min_length": 3
      }
    }
  ]
}
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Campos de Erro*
```

```ad-quote
title:
<p align="justify">Cada item dentro da lista detail descreve exatamente o local e a razão da falha de validação encontrada pelo Pydantic.</p>
```

```ad-quote
title:
| Chave | Significado |
| :--- | :--- |
| **type** | Identificador interno do tipo de erro gerado pelo Pydantic (ex: string_too_short, int_parsing). |
| **loc** | Caminho exato do campo inválido na requisição (ex: ["body", "nome"] ou ["query", "pagina"]). |
| **msg** | Mensagem descritiva informando qual regra foi violada. |
| **input** | O valor exato enviado pelo cliente que causou a falha na validação. |
```
````

---

#### 📋 Checklist

- [x] **01 )** - Fundamentos do Pydantic V2 e herança de `pydantic.BaseModel`

---

- [x] **02 )** - Tipagem moderna do Python (`str`, `int`, `float`, `bool`, `list[T]`, `dict[K, V]`, `Optional[T]`)

---

- [x] **03 )** - Uso de `Field()` para definir valores padrão, documentação e restrições numéricas (`gt`, `ge`, `lt`, `le`)

---

- [x] **04 )** - Restrições em strings com `Field(min_length=..., max_length=..., pattern=r"...")`

---

- [x] **05 )** - Modelos aninhados (*Nested Models*) para representar estruturas hierárquicas complexas

---

- [ ] **06 )** - Validação de formatos específicos com Pydantic Types (`EmailStr`, `HttpUrl`, `UUID`)

---

- [ ] **07 )** - Criação de validadores customizados com o decorador `@field_validator`

---

- [ ] **08 )** - Validação em nível de modelo com `@model_validator(mode="after")`

---

- [ ] **09 )** - Segregação de contratos: Schemas de Entrada (`UserCreate`, `UserUpdate`) vs Saída (`UserResponse`)

---

- [ ] **10 )** - Proteção contra vazamento de dados sensíveis usando `response_model` no decorador da rota

---

- [ ] **11 )** - Configurações do modelo via `ConfigDict(from_attributes=True)` para interoperabilidade com ORMs

---

- [ ] **12 )** - Compreensão da anatomia do erro 422 Unprocessable Entity retornado automaticamente pelo FastAPI

---
