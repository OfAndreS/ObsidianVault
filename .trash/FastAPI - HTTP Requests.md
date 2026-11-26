
---
## Extração de Dados em Requisições

### Parâmetros de Rota (Path Parameters)

**O que é:**
 
São informações embutidas diretamente na estrutura do endereço da URL, formando uma rota única e específica.

**Como funciona:**

Você define um espaço reservado na rota usando chaves, como `/usuarios/{id}`. O FastAPI captura o valor exato que o usuário digitou nessa posição do link e envia para a sua função.

**Melhor caso de uso:**

Identificar recursos específicos e únicos dentro de um sistema, como o perfil de um usuário ou uma página específica de um produto.

**Quando não usar:**

Quando o dado for opcional, muito longo, ou quando houver muitas variáveis para preencher ao mesmo tempo.

### Parâmetros de Consulta (Query Parameters)

**O que é:**

São filtros e opções adicionados ao final da URL. Eles sempre aparecem após um ponto de interrogação `?` e seguem o formato de chave-valor unidos pelo sinal de igual =.

**Como funciona:**

Se você cria uma variável na sua função do FastAPI e não especifica o local na rota, o sistema automaticamente a trata como um parâmetro de consulta. Os filtros extras são separados pelo símbolo `&`, como em `?cidade=natal&idade=20`.

**Melhor caso de uso:**

Filtrar resultados de uma busca, ordenar listas, definir o número da página atual (paginação) e enviar configurações opcionais.

**Quando não usar:**

Para transmitir informações sensíveis, como senhas ou dados financeiros. Tudo o que está na URL fica gravado no histórico de navegação.

### Corpo da Requisição (Request Body)

**O que é:**

É a carga principal de informações de uma requisição. É um pacote de dados oculto que o cliente envia para o servidor.

**Como funciona:**

O cliente formata os dados em estruturas organizadas, sendo o formato JSON o mais comum. No código Python, você avisa ao FastAPI que a informação chegará no corpo da requisição usando ferramentas específicas como o `Body` ou modelos baseados no Pydantic. Esse método exige que o verbo HTTP seja de envio, como `POST`, `PUT` ou `PATCH`.

**Melhor caso de uso:**

Receber formulários de cadastro completos, arquivos, grandes blocos de texto ou criar novos registros complexos no banco de dados.

**Quando não usar:**

Em operações de leitura simples que usam o verbo `GET`, pois por padrão essas requisições não devem alterar o estado do servidor e frequentemente ignoram o conteúdo anexado no corpo da mensagem.

### Cabeçalhos (HTTP Headers)

**O que é:**

São metadados da requisição. Eles funcionam como etiquetas de envio que acompanham o pacote principal da mensagem.

**Como funciona:**

Eles transportam pares de chaves e valores com detalhes técnicos da comunicação. No FastAPI, você extrai essas informações usando o recurso `Header`. O sistema automatiza a leitura formatando os nomes originais e convertendo hifens em linhas inferiores para combinar com as regras de nomes de variáveis em Python.

**Melhor caso de uso:**

Verificar permissões de acesso, confirmar a identidade do usuário através de tokens, checar o tipo de navegador que fez a requisição ou definir o idioma preferido do cliente.

**Quando não usar:**

Para o envio de dados que fazem parte da lógica central da sua aplicação ou preenchimento de recursos comuns. Seu uso deve ficar restrito aos controles gerais de operação e segurança.

---
---
### **1. Parâmetro de Rota**

Ação: Buscar um livro único. Método: GET. Caminho: /livros/{id} O sistema lê o número de identificação no link e devolve os dados exatos daquela obra.

### **2. Parâmetro de Consulta**

Ação: Filtrar o catálogo. Método: GET. Caminho: /livros?genero=ficcao O sistema aplica filtros na sua busca com base nos critérios declarados no final do link.

### **3. Corpo da Requisição**

Ação: Cadastrar um novo livro. Método: POST. Caminho: /livros O sistema recebe as informações completas da obra dentro de um pacote de dados oculto e salva o registro.

### **4. Cabeçalhos HTTP**

Ação: Apagar um livro do sistema. Método: DELETE. Caminho: /livros/{id} O sistema exige uma senha secreta enviada na área de controle da mensagem para autorizar a exclusão.

---

Quero entrar na página e receber o HTML
Quero adicionar um novo livro
Quero ver a lista de livros após a adição
Quero remover um livro
Quero ver a lista de livros após a remoção

---

O FastAPI lê as rotas de cima para baixo. Como a rota `@app.get("/book/{id_book}")` foi declarada **antes**, o FastAPI acha que a palavra `"gender"` (da URL `/book/gender`) é, na verdade, o `id_book` de um livro.