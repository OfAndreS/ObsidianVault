---
banner: "![[Pasted image 20251221174721.png]]"
---
---

>[!quote] **Vault:** [Mozilla HTML](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Forms)

---

```ad-done
title:

#### **Módulo HTML - Estrutura e Lógica de Formulários**

```

---

````ad-quote
title:

##### **01 )** - O Elemento de Controle: Tag Form

```ad-quote
title:
<p align="justify">A tag form não é apenas um contentor visual, mas um objeto de configuração que dita como o navegador deve empacotar e despachar as informações. Ele atua como um contrato de comunicação: definem-se as regras de envio e o navegador garante que os dados sigam esse protocolo.</p>
```

```shell
<form action="{% url 'processar_dados' %}" method="POST" target="_self">
    
    {% csrf_token %} <!-- Implementação para o Django --> 

</form>
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) Fundamentação Teórica
```

```ad-quote
title:
<p align="justify">O formulário existe para criar um estado transicional entre o cliente e o servidor. Sem ele, o navegador não saberia como organizar os dados dispersos na página em um pacote HTTP válido.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Atributos Essenciais
```

```ad-quote
title:

|**Atributo**|**Função e Contexto Django**|
|---|---|
|action|Define o endpoint de destino (URL). No Django, utiliza-se a template tag url para dinamizar este campo.|
|method|O protocolo de comunicação (GET para dados na URL, POST para dados no corpo da requisição).|
|enctype|A codificação dos dados. Essencial definir como multipart/form-data para envio de arquivos.|
|target|Define onde abrir a resposta do servidor (ex: nova aba).|
|autocomplete|Auxilia o usuário com dados salvos no navegador (on/off).|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Triângulo de Identificação

```ad-quote
title:
<p align="justify">Para que um formulário seja acessível e funcional, ele precisa de uma estrutura de identidade clara composta por Label, ID e Name.</p>
```

```shell 
	<label for="campo_nome_usuario">Nome Completo:</label> 
	<input type="text" id="campo_nome_usuario" name="full_name"> 
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Fundamentação Teórica
```

```ad-quote
title:
<p align="justify">Esta tríade resolve três problemas distintos: acessibilidade (Label), manipulação local (ID) e transmissão de dados (Name). O name é a variável que o servidor espera receber; sem ele, o dado existe na interface, mas é invisível para o backend.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Componentes da Identidade
```

```ad-quote
title:

|**Componente**|**Descrição Técnica**|
|---|---|
|Label|A face visível. Expande a área de clique e permite identificação por leitores de tela.|
|ID|Endereço único no DOM. Usado para estilização CSS e manipulação JavaScript.|
|Name|Identidade para o Backend. É a chave que o Django lerá no dicionário request.POST.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Tipologia de Entradas 

```ad-quote
title:
<p align="justify">O atributo type define o comportamento e a validação nativa do campo, aplicando a Tipagem Semântica de Dados.</p>
```

```shell
<input type="email" name="user_email">

<input type="password" name="user_password">

<input type="number" name="learning_rate" min="0" max="1" step="0.01">

<input type="hidden" name="session_id" value="xyz_123">

<input type="date" name="data_nascimento">
<input type="time" name="horario_agendamento">
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) Fundamentação Teórica
```

```ad-quote
title:
<p align="justify">Ao especificar um tipo, delega-se ao navegador a responsabilidade de fornecer a interface adequada (teclados numéricos, calendários) e uma primeira camada de validação, reduzindo a necessidade de scripts complexos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Tipos Comuns
```

```ad-quote
title:

|**Tipo (Type)**|**Característica**|
|---|---|
|text|Entrada de texto simples.|
|email|Valida a presença de arroba e domínio.|
|password|Mascara os caracteres (segurança visual).|
|number|Restringe a números (aceita min, max e step).|
|tel / url|Otimiza o teclado em dispositivos móveis.|
|hidden|Transporta dados invisíveis ao usuário (ex: tokens CSRF).|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Seleção e Restrição de Dados

```ad-quote
title:
<p align="justify">Elementos focados na integridade dos dados através da restrição de opções.</p>
```

```shell
<label>
    <input type="checkbox" name="aceite_termos" checked> Aceito os termos
</label>

<label>
    <input type="radio" name="genero" value="M"> Masculino
</label>
<label>
    <input type="radio" name="genero" value="F"> Feminino
</label>

<select name="cidade_uf">
    <optgroup label="Sudeste">
        <option value="SP">São Paulo</option>
        <option value="RJ">Rio de Janeiro</option>
    </optgroup>
</select>

<input list="browsers" name="navegador">
<datalist id="browsers">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Safari">
</datalist>
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) Fundamentação Teórica
```

```ad-quote
title:
<p align="justify">Limitar as opções a um conjunto pré-definido garante que a entrada seja sempre previsível e compatível com a lógica do sistema, evitando erros de processamento em datasets sensíveis.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Elementos de Escolha
```

```ad-quote
title:

|**Elemento**|**Aplicação**|
|---|---|
|checkbox|Seleções binárias ou múltiplas escolhas independentes.|
|radio|Escolha única dentro de um grupo (mesmo name).|
|select / option|Listas suspensas (dropdowns).|
|datalist|Lista de sugestões com autocompletar para campos de texto.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Validação e UX

```ad-quote
title:
<p align="justify">O HTML5 permite realizar uma pré-validação no lado do cliente (Client-side validation).</p>
```

```shell
<input type="text" name="cpf" placeholder="000.000.000-00" required>

<input type="text" name="id_usuario" value="USER_88" readonly>

<input type="text" name="status_sistema" value="OFFLINE" disabled>

<input type="text" name="cep" pattern="\d{5}-\d{3}" title="Digite no formato 12345-678">
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) Fundamentação Teórica: Fail-Fast
```

```ad-quote
title:
<p align="justify">Ao validar no navegador, oferece-se feedback instantâneo, economizando recursos do servidor e evitando o processamento de requisições destinadas ao erro.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Atributos de Controle
```

```ad-quote
title:

|**Atributo**|**Efeito**|
|---|---|
|required|Torna o preenchimento obrigatório.|
|placeholder|Dica visual do formato esperado.|
|readonly|Dado visível e enviado, mas imutável.|
|disabled|Dado visível, imutável e não enviado.|
|pattern|Validação via Expressões Regulares (Regex).|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Ciclo de Envio e Semântica

```ad-quote
title:
<p align="justify">Organização lógica e gatilhos de ação para o formulário.</p>
```

```shell
<button type="submit">Salvar Dados</button>

<button type="reset">Limpar</button>

<button type="button" onclick="calcularMedia()">Calcular Prévia</button>
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) Botões e Intencionalidade
```

```ad-quote
title:

|**Tipo de Botão**|**Ação**|
|---|---|
|submit|Padrão. Dispara o envio dos dados.|
|reset|Limpa o formulário (restaura estado inicial).|
|button|Sem ação nativa. Gatilho para JavaScript.|

```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Agrupamento Semântico
```

```ad-quote
title:
<p align="justify">Para formulários extensos, o uso de fieldset e legend reduz a carga cognitiva, permitindo que o usuário processe as informações em blocos lógicos.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Transmissão de Mídia e Protocolos

```ad-quote
title:
<p align="justify">Configurações críticas para o envio de arquivos binários (áudio, imagem) e segurança.</p>
```

```shell
<form action="/upload/" method="POST" enctype="multipart/form-data">
    
    {% csrf_token %}
    
    <label for="input_audio">Selecione o arquivo .wav:</label>
    
    <input type="file" id="input_audio" name="audio_sample" accept="audio/*">
    
    <button type="submit">Enviar Arquivo</button>
</form>
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) Upload de Arquivos
```

```ad-quote
title:
<p align="justify">Para enviar binários sem corrompê-los, é obrigatório o uso do método POST e do enctype multipart/form-data. No Django, estes dados são acessados via request.FILES e não request.POST.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Comparativo: GET vs POST
```

```ad-quote
title:

|**Característica**|**GET**|**POST**|
|---|---|---|
|Visibilidade|Exposto na URL.|Invisível na URL (Body).|
|Capacidade|Limitada (aprox. 2000 carac).|Virtualmente ilimitada.|
|Arquivos|Não suportado.|Suporte total (Multipart).|
|Segurança|Nula para dados sensíveis.|Mais seguro (Exige CSRF).|
|Idempotência|Sim (leitura).|Não (alteração de estado).|

```
````

---