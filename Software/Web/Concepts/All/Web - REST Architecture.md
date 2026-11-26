
---

https://www.youtube.com/watch?v=CblNa4yBY5U

---

````ad-quote
title:

##### **Intro )** - Arquitetura REST

```ad-quote
title:
<p align="justify">REST (Representational State Transfer) é um Estilo Arquitetural para sistemas distribuídos definido por Roy Fielding em sua tese de doutorado no ano 2000. Ele não é um protocolo e nem uma tecnologia mas sim um conjunto de restrições e boas práticas sobre como utilizar o protocolo HTTP corretamente.</p>
```

![[Pasted image 20251127185442.png]]

```ad-quote
title:
###### **A Analogia do Trânsito**
```

```ad-quote
title:
<p align="justify">Se o HTTP é o Carro o REST são as Regras De Trânsito.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Os 6 Princípios - Constraints

```ad-quote
title:
<p align="justify">Para uma API ser considerada verdadeiramente RESTful ela deve obedecer a seis restrições arquiteturais fundamentais.</p>
```



```ad-quote
title:

|Princípio&nbsp; | Definição e Benefício&nbsp; |
| :--- | :--- |
|**Client-Server**|Separação total de responsabilidades. O Front-end cuida da interface e não sabe sobre o banco de dados. O Back-end cuida das regras de negócio. Permite Evolução Independente.|
|**Stateless**|O servidor não armazena contexto do cliente entre as requisições. Cada pedido deve conter toda a informação necessária como tokens e filtros. Garante Escalabilidade.|
|**Cacheable**|As respostas devem indicar se podem ser armazenadas em cache pelo cliente reduzindo o tráfego na rede e aumentando a velocidade.|
|**Uniform Interface**|O contrato de comunicação deve ser padronizado permitindo que o entendimento de um recurso facilite o entendimento de outros.|
|**Layered System**|O cliente não precisa saber se está conectado ao servidor final ou a um intermediário como Load Balancers. Traz Segurança e Balanceamento.|
|**Code on Demand**|Única regra opcional onde o servidor pode enviar código executável para o cliente como scripts JavaScript.|

```
````

---
### 1. O Recurso e a Rota

Você define qual informação vai manipular e escolhe o nome do caminho. Aqui você decide se o formato visual será uma rota de coleção, de documento ou de controlador.

### 2. O Método e os Filtros

Você escolhe o verbo adequado para a intenção de uso. Logo em seguida, você avalia a necessidade de usar parâmetros de caminho para identificar um arquivo ou parâmetros de consulta para filtrar uma lista.

### 3. A Carga de Dados

Você desenha a estrutura do pacote principal. Se a ação for de criação ou de atualização, você define os campos exatos que o cliente deve enviar no corpo da requisição.

### 4. As Regras de Segurança

Você avalia se o endereço é público ou privado. Caso a porta seja trancada, você configura o sistema para exigir os parâmetros de cabeçalho contendo as chaves de acesso.

### 5. O Padrão de Resposta

Você planeja o formato do pacote de devolução. Aqui você escolhe os códigos de status numéricos corretos para sinalizar o sucesso da operação ou para explicar o motivo de uma falha.

---

```ad-done
title:

#### **Fase 2 ) - Tipos de rota**

```

---

````ad-quote
title:

##### **02 )** - O que são os tipos de rotas

```ad-quote
title:
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Rotas de Coleção_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que é*
```

```ad-quote
title:
<p align="justify">Representam um grupo completo de elementos. Pense nelas como a gaveta inteira de um arquivo.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) *Padrão de escrita*
```

```ad-quote
title:
<p align="justify">A regra é usar sempre um substantivo no plural.</p>
```

```bash
# /usuarios
# /livros
# /produtos
# /pedidos
# /clientes
# /faturas
# /artigos
# /comentarios
```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Rotas de Documento_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que é*
```

```ad-quote
title:
<p align="justify">Representam um elemento único isolado. Pense nelas como uma pasta específica retirada de dentro da gaveta.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Padrão de escrita*
```

```ad-quote
title:
<p align="justify">A estrutura visual é a junção da rota de coleção com o parâmetro de caminho.</p>
```

```bash
# /usuarios/42
# /livros/105
# /produtos/99
# /pedidos/2023
# /clientes/50
# /faturas/77
# /artigos/12
# /comentarios/5
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.3 ) - _Rotas de Controlador_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que é*
```

```ad-quote
title:
<p align="justify">Representam uma ação complexa no sistema. Você cria essa rota quando a operação foge da regra básica de salvar ou apagar um arquivo. Pense nelas como um botão de emergência ou de execução.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Padrão de escrita*
```

```ad-quote
title:
<p align="justify">Elas são a única exceção do padrão REST onde o uso de verbos é permitido no endereço.</p>
```

```bash
# /usuarios/42/bloquear
# /livros/105/reservar
# /produtos/99/desativar
# /pedidos/2023/cancelar
# /clientes/50/promover
# /faturas/77/pagar
# /artigos/12/publicar
# /comentarios/5/ocultar
```
````

---

```ad-done
title:

#### **Fase 3 ) - Tipos de Parâmetros**

```

---

````ad-quote
title:

##### **03 )** - O que são parâmetros na URL

```ad-quote
title:

Os parâmetros são as informações dinâmicas enviadas do cliente para o servidor durante uma requisição HTTP. Eles funcionam como as instruções detalhadas de um pedido e servem para personalizar a comunicação. Essas variáveis permitem filtrar os resultados de uma busca, apontar para um arquivo específico no banco de dados, entregar blocos extensos de texto ou transportar credenciais de segurança. Em resumo, os parâmetros atuam como os canais de entrada de uma API, garantindo que o sistema receba todos os dados necessários para executar a operação desejada.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Path Parameters_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o é*
```

```ad-quote
title:
<p align="justify">São valores numéricos ou de texto embutidos de forma obrigatória no próprio link de destino. O melhor uso para eles é identificar e apontar para um arquivo único dentro do banco de dados da aplicação.</p>
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
O número inserido no final do endereço funciona como a variável principal. O servidor entende que o usuário não quer a lista inteira de pessoas, mas precisa ler exclusivamente a ficha de cadastro do cliente com a identificação cento e vinte e três.
```

```HTTP
GET /api/clientes/123
```

````

> [!done] **_New_**

```ad-quote
title:

##### 3.2 ) - _Query Parameters_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o é*
```

```ad-quote
title:
<p align="justify">São variáveis soltas adicionadas no final do endereço da web logo após um sinal de ponto de interrogação. O melhor uso para elas é filtrar informações, organizar a ordem de exibição na tela ou dividir listas gigantescas em páginas menores.</p>
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
A primeira parte do texto tenta acessar o catálogo geral de produtos. As variáveis soltas avisam ao servidor para devolver apenas os itens de tecnologia, organizar a devolução baseada no preço e enviar apenas a segunda página de resultados dessa busca.
```

```HTTP
GET /api/produtos?categoria=eletrônicos&ordenar=preco&pagina=2
```

````

> [!done] **_New_**

```ad-quote
title:

##### 3.3 ) - _Header Parameters_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o é*
```

```ad-quote
title:
<p align="justify">São peças de informação de controle enviadas na área invisível da mensagem HTTP. O melhor uso para eles é transportar dados técnicos e regras de formato sem misturar essa burocracia com a carga de dados real do usuário.</p>
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
<p align="justify">O programa do usuário envia uma chave secreta de acesso na linha de autorização do pacote técnico. O servidor lê essa chave antes de processar qualquer coisa para ter certeza de que a pessoa possui permissão para ver os arquivos solicitados.</p>
```

```HTTP
GET /api/documentos/456 HTTP/1.1
Host: api.exemplo.com
Authorization: Bearer token123
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.4 ) - _Body Parameters_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o é*
```

```ad-quote
title:
<p align="justify">É um pacote pesado de dados inserido no bloco inferior da mensagem de ida. O melhor uso para ele é transportar informações complexas e extensas durante a criação ou atualização de cadastros no sistema.</p>
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
<p align="justify">O usuário está preenchendo um formulário para enviar os dados de um cliente novo no formato padronizado de chaves e valores. O servidor retira essas informações do pacote de texto para gravar o cadastro do João de forma permanente.</p>
```

```HTTP
POST /api/clientes HTTP/1.1
Host: api.exemplo.com
Content-Type: application/json

{
  "nome": "João",
  "email": "joao@example.com"
}
```
````

---

```ad-done
title:

#### **Fase 4 ) - Métodos HTTP**

```

---

````ad-quote
title:

##### **04 )** - O que são os métodos HTTP's - [[Web - Protocolo HTTP |{ X }]]
```ad-quote
title:
```
````

```ad-quote
title:

##### 4.1 ) - _GET_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O sistema identifica o método de busca. Ele entende que o usuário deseja ler as informações do livro com identificação número 123. O servidor percebe que não existe corpo na mensagem de ida.</p>
```

```HTTP
GET /livros/123 HTTP/1.1
Host: api.biblioteca.com
Accept: application/json
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O sistema envia uma mensagem de sucesso acompanhada dos dados do livro solicitado.</p>
```

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 45

{
  "titulo": "O Hobbit",
  "autor": "Tolkien"
}
```

````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Este é um método exclusivo de leitura. Ele serve apenas para pedir dados. O seu comportamento padrão é viajar com o pacote de ida totalmente vazio.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.2 ) - _HEAD_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O sistema entende que o usuário quer saber se o livro 123 existe. O servidor percebe que o cliente deseja os detalhes técnicos do arquivo, mas não quer o conteúdo do livro em si.</p>
```

```HTTP
HEAD /livros/123 HTTP/1.1
Host: api.biblioteca.com
Accept: application/json
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O sistema envia a linha de sucesso e os cabeçalhos de controle. A mensagem acaba na linha em branco. O pacote não possui corpo.</p>
```

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 45
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Ele é idêntico ao método de busca tradicional, mas o servidor corta o corpo da resposta. Ele é muito usado para testar se um link funciona antes de baixar um arquivo pesado.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.3 ) - _POST_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O sistema encontra um pedido de criação. Ele lê o endereço geral da biblioteca e sabe que precisa adicionar um item novo ao acervo. Em seguida ele acessa o corpo da mensagem e coleta os dados do novo livro.</p>
```

```HTTP
POST /livros HTTP/1.1
Host: api.biblioteca.com
Content-Type: application/json
Content-Length: 53

{
  "titulo": "Duna",
  "autor": "Frank Herbert"
}
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O sistema salva os dados e devolve o código de status 201. Esse número confirma que o cadastro foi criado. A resposta inclui a identificação da nova obra.</p>
```

```HTTP
HTTP/1.1 201 Created
Content-Type: application/json
Content-Length: 26

{
  "id": 124,
  "status": "ok"
}
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Ele é o principal método de envio de dados novos. Diferente da leitura, ele carrega informações no pacote de ida. Se você repetir o mesmo pedido idêntico várias vezes, o sistema criará vários livros repetidos no sistema.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.4 ) - _PUT_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O sistema identifica um pedido de substituição completa. Ele vai até a prateleira procurar o livro 123. Ao encontrar a obra, o servidor apaga o cadastro antigo e escreve exatamente o que chegou no novo corpo da mensagem.</p>
```

```HTTP
PUT /livros/123 HTTP/1.1
Host: api.biblioteca.com
Content-Type: application/json
Content-Length: 58

{
  "titulo": "O Hobbit",
  "autor": "J. R. R. Tolkien"
}
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O sistema avisa que a alteração foi feita com sucesso. Ele pode devolver o registro atualizado no pacote final para confirmação.</p>
```

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 58

{
  "titulo": "O Hobbit",
  "autor": "J. R. R. Tolkien"
}
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Ele serve para atualização completa de um recurso específico. A principal diferença para o método de criação é a previsibilidade. Se você enviar o mesmo pacote mil vezes, o resultado no servidor será sempre um único livro atualizado.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.5 ) - _PATCH_

```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O sistema identifica um pedido de atualização parcial. Ele vai até a prateleira procurar o livro 123. Ao encontrar a obra o servidor altera apenas a informação que chegou no corpo da mensagem e mantém o restante dos dados como estavam antes.</p>
```

```HTTP
PATCH /livros/123 HTTP/1.1
Host: api.biblioteca.com
Content-Type: application/json
Content-Length: 29

{
  "ano_publicacao": 1937
}
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O sistema avisa que a modificação pontual foi feita com sucesso. Ele pode devolver o registro completo com o novo detalhe alterado para que o aplicativo confirme a operação.</p>
```

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 76

{
  "titulo": "O Hobbit",
  "autor": "J. R. R. Tolkien",
  "ano_publicacao": 1937
}
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Ele serve para a modificação de campos específicos de um recurso. A principal diferença em relação ao método de substituição completa é a economia no envio de informações. Você manda apenas o pedaço de dado que precisa de ajuste sem precisar enviar todos os outros detalhes novamente.</p>
```

````

> [!done] **_New_**

```ad-quote
title:

##### 4.6 ) - _DELETE_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O servidor reconhece a ordem de exclusão. Ele busca o registro do livro 123 no banco de dados e simplesmente destrói essa informação. A mensagem original viaja sem corpo.</p>
```

```HTTP
DELETE /livros/123 HTTP/1.1
Host: api.biblioteca.com
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O sistema devolve um código de status 204. Esse número significa que a operação deu certo e que o servidor não tem nenhum conteúdo adicional para mostrar na tela de volta.</p>
```

```HTTP
HTTP/1.1 204 No Content
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">É o único método dedicado exclusivamente para apagar informações. Ele trabalha com caminhos exatos e quase nunca envia ou recebe corpo de texto.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.7 ) - _TRACE_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O servidor funciona como um espelho. Ele entende que é um teste técnico. O computador precisa pegar tudo o que chegou na porta de entrada e preparar a devolução sem processar nenhuma regra da biblioteca.</p>
```

```HTTP
TRACE /livros HTTP/1.1
Host: api.biblioteca.com
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O sistema empacota a mensagem de ida inteira e coloca tudo dentro do corpo da viagem de volta. O tipo de documento enviado é classificado como mensagem HTTP pura.</p>
```

```HTTP
HTTP/1.1 200 OK
Content-Type: message/http
Content-Length: 51

TRACE /livros HTTP/1.1
Host: api.biblioteca.com
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Ele não interage com os dados do seu sistema. Serve apenas para rastreamento. As pessoas desenvolvedoras usam essa opção para ver se algum computador de passagem alterou a mensagem original pelo caminho.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.8 ) - _OPTIONS_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O sistema interpreta um pedido de regras. O usuário está perguntando quais ações a biblioteca permite fazer com o livro 123. O servidor não altera nem consulta a obra real.</p>
```

```HTTP
OPTIONS /livros/123 HTTP/1.1
Host: api.biblioteca.com
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">A resposta inclui um cabeçalho especial chamado Allow. Ele lista as palavras permitidas para aquele endereço exato. A mensagem não possui corpo.</p>
```

```HTTP
HTTP/1.1 200 OK
Allow: GET, HEAD, PUT, DELETE
Content-Length: 0
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Ele é um método de descoberta. Os navegadores de internet disparam esse pedido automaticamente nos bastidores antes de fazer chamadas complexas. Ele descobre as regras de segurança do servidor de forma antecipada.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.9 ) - _CONNECT_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que o servidor recebe*
```

```ad-quote
title:
<p align="justify">O sistema entende que precisa atuar como uma ponte. O usuário quer passar pelo servidor atual e abrir um túnel direto com o computador do arquivo restrito da biblioteca.</p>
```

```HTTP
CONNECT interno.biblioteca.com:443 HTTP/1.1
Host: interno.biblioteca.com:443
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *O que o servidor devolve*
```

```ad-quote
title:
<p align="justify">O servidor confirma que o túnel de rede foi aberto. A partir desse momento, a estrutura padrão de mensagem HTTP é abandonada e o canal passa a transmitir dados criptografados sem interrupção.</p>
```

```HTTP
HTTP/1.1 200 Connection Established
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Diferença desse método*
```

```ad-quote
title:
<p align="justify">Ele é o único que foge da dinâmica de pedir ou enviar informações para uma API. Ele converte a conexão normal em um tubo de rede transparente. É a tecnologia responsável por fazer a internet funcionar de forma segura.</p>
```
````

---

> [!done] **_New_**

---
### O Corpo da Mensagem

Nós falamos bastante sobre ele, mas é vital lembrar que a estrutura visual importa muito. O pacote de texto que viaja nos métodos de criação e atualização precisa seguir uma lógica constante. Pense nisso como um formulário fixo. O cliente que consome a sua API precisa saber de antemão os nomes exatos dos campos que o servidor espera receber.

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Segurança e Idempotência

```ad-quote
title:
<p align="justify">Em sistemas distribuídos a rede pode falhar e requisições podem se perder. Conceitos de segurança e idempotência são vitais para lidar com repetições de chamadas.</p>
```

```ad-quote
title:
###### **Classificação dos Métodos:**
```

```ad-quote
title:

|Método&nbsp; | É Idempotente?&nbsp; | Comportamento em Múltiplas Chamadas&nbsp; |
| :--- | :--- | :--- |
|**GET**|✅ SIM|Ler dez vezes não altera o dado. É um Método Seguro.|
|**PUT**|✅ SIM|Atualizar o nome para André dez vezes resulta no nome sendo André.|
|**DELETE**|✅ SIM|Deletar o item X repetidamente resulta no mesmo estado final (item apagado).|
|**POST**|❌ NÃO|Enviar Criar Pedido três vezes criará três pedidos diferentes. Requer cuidado extra como tokens de idempotência.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - O Modelo de Maturidade Richardson

```ad-quote
title:
<p align="justify">Leonard Richardson criou uma escala de zero a três para medir o quão RESTful uma API é.</p>
```



```ad-quote
title:

|Nível&nbsp; | Característica&nbsp; |
| :--- | :--- |
|**Nível 0**|The Swamp of POX. Usa HTTP apenas como túnel estilo RPC. Tudo costuma ser POST em uma única URL.|
|**Nível 1**|Resources. Começa a usar URLs diferentes para recursos diferentes mas ainda usa verbos incorretamente.|
|**Nível 2**|HTTP Verbs. O padrão de mercado atual. Usa URLs corretas Verbos corretos e Status Codes corretos.|
|**Nível 3**|HATEOAS. O nível máximo onde a API devolve links de navegação guiando o cliente sobre os próximos passos possíveis.|

```

```ad-quote
title:
###### **Exemplo de Resposta Nível 3 (HATEOAS):**
```

```json
{
  "id": 1,
  "nome": "André",
  "saldo": 100,
  "_links": {
    "self": { "href": "/clientes/1" },
    "depositar": { "href": "/clientes/1/deposito" },
    "pedidos": { "href": "/clientes/1/pedidos" }
  }
}
```
````

---

> [!done] **_New_**

---

### O Padrão de Respostas

Uma ferramenta de qualidade nunca deixa o usuário confuso. Você precisa aplicar com cuidado aquelas famílias numéricas de status. Se a pessoa enviar um dado incompleto, o seu sistema deve devolver um código da família 400. O corpo dessa mensagem de retorno deve conter um texto amigável explicando exatamente qual etapa falhou.

### O Controle de Versões

As regras de um projeto de tecnologia mudam com o passar do tempo. Para não quebrar os aplicativos que já funcionam conectados com o seu sistema, você adiciona um pequeno marcador de versão no início do endereço principal. Exemplo de link: /v1/livros Se no futuro você alterar toda a estrutura do seu banco de dados, você apenas cria o caminho v2. Dessa forma você atende as novas demandas e mantém a versão antiga funcionando para os usuários atuais.

---
---

### Client

O computador ou sistema que faz o pedido original. Pense nele como uma pessoa sentada na mesa de um restaurante fazendo o pedido.

### Server

O computador central que guarda os arquivos e processa as regras. Ele funciona como a cozinha do restaurante preparando o prato solicitado.

### Request

A mensagem de ida pela rede. É o pacote de texto oficial que o Client envia para a porta do Server.

### Response

A mensagem de volta pela rede. É o pacote final que o Server devolve para o Client após terminar todo o processamento.

### Method

A ação desejada pelo Client. É a palavra inicial da mensagem que avisa se a intenção é buscar, criar, atualizar ou apagar um dado.

### Resource

A informação real armazenada no sistema. Pode ser o cadastro de uma pessoa ou um catálogo de produtos. Pense nele como o objeto físico guardado no banco de dados.

### Endpoint

O endereço público de destino. É o link exato exposto na internet que permite alcançar um Resource específico.

### Route

A regra interna desenhada no seu código. Ela gerencia o tráfego e conecta o endereço externo com a função de processamento correta nos bastidores.

### Header

A área invisível de controle do pacote. É o espaço técnico usado para enviar formatos de arquivo e credenciais de segurança.

### Body

A área de carga real do pacote. É o espaço reservado para transportar formulários longos e dados pesados.

### Status Code

O número de três dígitos que inicia a mensagem de volta. Ele funciona como um resumo rápido para avisar se a operação deu certo ou falhou.

### JSON

O modelo de texto padronizado para a troca de dados. Ele estrutura as informações em pares de nomes e valores para facilitar a leitura rápida pelos computadores.

### Path Parameter

O valor embutido de forma fixa no endereço de destino. Serve como um número de identificação para apontar para um arquivo único.

### Query Parameter

O valor adicionado solto no final do endereço de destino. Serve como um filtro de busca para limitar os resultados de uma lista grande.