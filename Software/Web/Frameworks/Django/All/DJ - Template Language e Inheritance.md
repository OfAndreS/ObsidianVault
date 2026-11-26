---
banner: "![[Pasted image 20251221174537.png]]"
---

---

```ad-done
title: 

#### **Fase 1 ) -** Django Template Language DTL

```

---

````ad-quote
title:

##### **01 )** - O Conceito MTV

```ad-quote
title:
<p align="justify">O Django utiliza o padrão MTV (Model-Template-View). O Template é a camada responsável por definir como os dados serão exibidos, separando a lógica de apresentação da lógica de negócios para permitir um fluxo de trabalho harmonioso entre designers e desenvolvedores.</p>
```



```ad-quote
title:
<p align="justify">Diferente do MVC tradicional, o Django delega ao Template o papel da View clássica, focando na geração dinâmica de HTML através de um motor de renderização robusto e seguro.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Sintaxe Básica e Componentes

```ad-quote
title:
<p align="justify">A linguagem de templates foca em quatro construções principais que permitem a manipulação de dados e controle de fluxo diretamente no HTML.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Variáveis e Acesso a Dados
```

```ad-quote
title:
As variáveis são envolvidas por chaves duplas e substituídas pelos valores enviados pela View através do contexto. O ponto é usado para acessar atributos, chaves ou índices.
```

```html
Olá, {{ usuario }}!
Título do Blog: {{ blog.titulo }}
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Tags de Lógica e Controle
```

```ad-quote
title:
As tags, delimitadas por chaves e porcentagem, controlam o comportamento do template, como laços de repetição e verificações condicionais.
```

```python
{% if usuario.esta_logado %}
    <p>Bem-vindo!</p>
{% endif %}

{% for item in lista %}
    <li>{{ item }}</li>
{% endfor %}
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Filtros e Formatação

```ad-quote
title:
<p align="justify">Filtros permitem modificar a exibição de uma variável no momento da renderização. Eles são aplicados através do caractere pipe e podem aceitar argumentos específicos.</p>
```

```ad-quote
title:
|**Filtro**|**Ação Técnica**|**Resultado Exemplo**|
|---|---|---|
|lower|Converte texto para minúsculas.|{{ nome|lower }}|
|date|Formata objetos de data/hora.|{{ data|date:"d/m/Y" }}|
|default|Valor reserva se variável for vazia.|{{ var|default:"N/A" }}|
|length|Retorna o tamanho da lista/string.|{{ lista|length }}|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Herança de Templates

```ad-quote
title:
<p align="justify">A herança é o pilar do princípio DRY no DTL. Ela permite criar layouts base com blocos editáveis que são preenchidos por templates filhos específicos.</p>
```

```ad-quote
title:
###### Estrutura Base (base.html)
```

```html
<html>
<body>
    <nav>Menu</nav>
    {% block conteudo %}{% endblock %}
</body>
</html>
```

```ad-quote
title:
###### Especialização (home.html)
```

```html
{% extends "base.html" %}

{% block conteudo %}
    <h1>Esta é a Home</h1>
{% endblock %}
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Segurança e Limitações

```ad-quote
title:
<p align="justify">O DTL foi projetado para ser propositalmente limitado, impedindo a execução de código Python arbitrário para garantir a segurança e a organização do projeto.</p>
```

```ad-quote
title:
###### Proteção Nativa
<p align="justify">O motor do Django escapa automaticamente caracteres HTML especiais para prevenir ataques de Cross-Site Scripting (XSS). Lógicas complexas devem sempre ser movidas para a View ou para Custom Tags.</p>
```
````

---