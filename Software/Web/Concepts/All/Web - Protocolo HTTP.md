---
banner: Pasted image 20260712203132.png
banner-x: 50
banner-y: 35
banner-fade: 100
---
---

>[!quote] **Link:** [Article One](https://www.alura.com.br/artigos/http?utm_term=&utm_campaign=&utm_source=google&utm_medium=cpc&campaign_id=23805973578__&utm_id=23805973578__&hsa_acc=7964138385&hsa_cam=&hsa_grp=&hsa_ad=&hsa_src=x&hsa_tgt=&hsa_kw=&hsa_mt=&hsa_net=google&hsa_ver=3&gad_source=1&gad_campaignid=23815806613&gbraid=0AAAAADpqZIAQkAYhHPOX1CeS3NPEhdaly&gclid=CjwKCAjw9szSBhBNEiwAC57Sq9FYsFk0bXFgR78cJ7K0mqxjD1QAdE5CSvm0rzrhnAKxPXH4jAXrWRoCDHQQAvD_BwE)

---

```ad-done
title:
#### **Fase 1 ) - Definição**
```

---

````ad-quote
title:

##### **01 )** - O Protocolo HTTP

```ad-quote
title:
O HTTP é a base para que o cliente e um servidor web [[Web - Arquitetura Cliente-Servidor| { X } ]] troquem informações. Ele permite a requisição e a resposta de recursos, como imagens, arquivos e as próprias páginas webs que acessamos, por meio de mensagens padronizadas. Com ele, é possível que um estudante num café em São Paulo leia um artigo que está armazenado em um servidor no Japão.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Funcionamento_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Arquitetura*
```

```ad-quote
title:
<p align="justify">O HTTP opera em um modelo cliente-servidor, em que um cliente, geralmente um navegador web, faz solicitações a um servidor para obter recursos, como páginas da web, imagens ou arquivos.</p>
```

![[Pasted image 20251127134356.png]]

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Elementos Base*
```

```Bash

# Métodos HTTP

# Headers

# URI - Uniform Resource Identifier

# Cache

# Hipermídia

```

````

````ad-quote
title:

```ad-quote
title:
###### C ) *Fluxo HTTP*
```

```bash
01 )
# Você digita o URL  do site. O navegador consulta o DNS para descobrir o número de IP do servidor.


02 )
# O navegador usa o IP para iniciar uma conexão com o servidor através do protocolo TCP.


03 )
# O navegador pede a página ao servidor usando o protocolo HTTP. Esse pedido viaja por dentro da conexão TCP que acabou de ser criada.


04 )
# O servidor processa a solicitação. Ele devolve os arquivos da página ou envia um código de erro 404 se não achar o documento.


05 )
# O navegador recebe as informações e faz a renderização. Esse processo converte o código de texto puro na interface visual da sua tela.


06 )
# O navegador identifica que precisa de imagens e recursos complementares. A conexão TCP continua aberta para baixar esses itens extras de forma rápida e contínua.


07 )
# O navegador encerra a conexão TCP apenas após carregar todas as peças solicitadas. A página fica totalmente pronta para a sua navegação.
```

````

---

```ad-done
title:
#### **Fase 2 ) - Comunicação**
```

---

````ad-quote
title:

##### **02 )** - Requisição

```ad-quote
title:
Quando o cliente faz uma solicitação ao servidor, ele envia um bloco de texto formatado contendo três partes.
```

```bash
# START LINE
POST /api/login HTTP/1.1

# HEADERS
Host: www.meusite.com.br
Content-Type: application/json
Content-Length: 48

# BODY
{
  "email": "aluno@email.com",
  "senha": "123"
}
```

```bash
import requests

resposta = requests.get('https://jsonplaceholder.typicode.com/posts/1')
dados = resposta.json()

print(dados)
```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Start Line_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
A Start Line é o comando de ação. Ela possui três elementos principais separados por espaço. O primeiro elemento é o método que define o tipo da operação. O segundo elemento é o caminho exato do recurso que você quer acessar no servidor. O terceiro elemento é a versão do protocolo de comunicação.
```
```bash
# START LINE
POST /api/login HTTP/1.1
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Métodos*
```

```bash
01 ) GET
# O método GET solicita dados de um recurso específico. É utilizado para recuperar informações, como páginas web, através de um servidor. Parâmetros são normalmente enviados na URL. Headers podem fornecer autenticação ou preferências de conteúdo.

02 ) HEAD
# Semelhante ao GET, o HEAD obtém apenas os cabeçalhos da resposta, sem o corpo. É útil para consultar metadados sem carregar o conteúdo completo.

03 ) POST
# O método POST envia dados ao servidor para processamento. É comumente empregado no envio de formulários ou na criação de recursos.

04 ) PUT
# O PUT envia dados para criar ou atualizar um recurso no URI especificado, substituindo-o completamente.

05 ) DELETE
# O método DELETE solicita a remoção de um recurso. Após o sucesso, o recurso é removido ou se torna inacessível. Recomenda-se incluir um parâmetro na URL para evitar exclusões acidentais em massa.

06 ) TRACE
# O TRACE é uma ferramenta de diagnóstico. O servidor reflete a solicitação de volta, permitindo que o cliente veja as alterações sofridas no caminho até o servidor.

07 ) OPTIONS
# O método OPTIONS consulta as opções de comunicação permitidas para um recurso ou servidor, como métodos suportados e cabeçalhos aceitáveis.

08 ) CONNECT
# O CONNECT estabelece um túnel com o servidor, geralmente para comunicações seguras via proxy HTTP, sendo usado principalmente para criar conexões SSL/TLS.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Headers - Metadados_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
Os cabeçalhos são as configurações da mensagem. Cada linha contém um nome e um valor. O navegador usa essa área para informar o formato dos dados que estão no corpo da mensagem e o tamanho total do pacote. O servidor lê essas linhas para saber como desembrulhar a informação principal.
```
```bash
# HEADERS
Host: www.meusite.com.br
Content-Type: application/json
Content-Length: 48
```
````

```ad-quote
title:

##### 2.3 ) - _Body_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
O corpo é o cofre da requisição. Ele fica separado dos cabeçalhos por uma linha em branco obrigatória. O navegador coloca aqui as informações que você digitou em um formulário. Esse bloco é muito comum quando você faz um cadastro ou realiza uma compra.
```
```bash
# BODY
{
  "email": "aluno@email.com",
  "senha": "123"
}
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Resposta

```ad-quote
title:
O servidor processa o pedido e devolve um bloco de texto formatado contendo três partes. A linha de status informa o resultado da operação, os cabeçalhos descrevem os metadados e o corpo entrega o conteúdo solicitado.
```

```bash
# STATUS LINE
HTTP/1.1 200 OK

# HEADERS
Content-Type: text/html; charset=UTF-8
Content-Length: 1256
Set-Cookie: sessionid=abc123; Path=/

# BODY
<!DOCTYPE html>
<html>
<head><title>Exemplo</title></head>
<body><p>Página carregada com sucesso.</p></body>
</html>
```

```bash
import requests

resposta = requests.get('https://jsonplaceholder.typicode.com/posts/1')
print(resposta.status_code)
print(resposta.headers['Content-Type'])
print(resposta.text[:200])
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Status Line_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
A linha de status é a primeira linha da resposta HTTP. Ela é composta pela versão do protocolo, um código numérico de três dígitos e uma frase descritiva. O cliente interpreta essa linha para saber se a requisição foi bem-sucedida ou se houve algum tipo de erro.
```
```bash
# STATUS LINE
HTTP/1.1 404 Not Found
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Códigos de Status*
```

```ad-quote
title:
Os códigos de status são agrupados em cinco categorias, indicadas pelo primeiro dígito. Cada categoria representa uma classe de resposta, desde informações provisórias até erros do servidor.
```

```ad-quote
title:
| Faixa | Categoria | Exemplos Comuns |
| :--- | :--- | :--- |
| 1xx | Informativo | 100 Continue (O servidor recebeu e está processando). |
| 2xx | Sucesso | 200 OK, 201 Created, 204 No Content. |
| 3xx | Redirecionamento | 301 Moved Permanently, 304 Not Modified. |
| 4xx | Erro do Cliente | 400 Bad Request, 401 Unauthorized, 404 Not Found. |
| 5xx | Erro do Servidor | 500 Internal Server Error, 502 Bad Gateway. |
```
````

```ad-quote
title:

##### 3.2 ) - _Headers - Metadados_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
Os cabeçalhos de resposta fornecem metadados sobre o servidor e o recurso enviado. Cada linha contém um nome e um valor. O navegador utiliza essas informações para interpretar o tipo de conteúdo, gerenciar cookies, controlar o cache e entender outras instruções.
```
```bash
# HEADERS
Content-Type: application/json
Content-Length: 234
Cache-Control: max-age=3600
```
````

```ad-quote
title:

##### 3.3 ) - _Body_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
O corpo da resposta carrega o conteúdo solicitado. Ele é separado dos cabeçalhos por uma linha em branco obrigatória. Pode conter uma página HTML, dados estruturados em JSON, imagens ou qualquer outro tipo de recurso requisitado pelo cliente.
```
```bash
# BODY
{
  "userId": 1,
  "id": 1,
  "title": "exemplo de post",
  "body": "conteudo do post aqui"
}
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - HTTPS e Segurança - SSL/TLS

```ad-quote
title:
<p align="justify">O HTTPS (HTTP Secure) não é um protocolo diferente, mas sim o HTTP trafegando dentro de um túnel CRIPTOGRAFADO. Adiciona-se a camada SSL/TLS entre o TCP e o HTTP.</p>
```



```ad-quote
title:
###### **Pilares da Segurança HTTPS**
```

```ad-quote
title:

|Componente&nbsp; | Função&nbsp; |
| :--- | :--- |
|**Criptografia Assimétrica**|Usa um par de chaves (Pública e Privada) para iniciar a conversa segura.|
|**Certificado Digital**|O servidor apresenta um documento emitido por uma AUTORIDADE CERTIFICADORA (CA) para provar identidade e evitar ataques MAN-IN-THE-MIDDLE.|

```
````

---



