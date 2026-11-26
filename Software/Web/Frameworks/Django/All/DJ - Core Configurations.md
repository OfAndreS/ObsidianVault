---
banner: "![[Pasted image 20251221174537.png]]"
---
---

````ad-quote
title:

#### **01 ) -** Configuração inicial

```ad-quote
title:
<p align="justify">Todo projeto Django começa com uma série de configurações e comandos rodados no terminal visando iniciar a aplicação de forma correta.</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Terminal - Iniciando o Projeto
```

```shell
django-admin startproject NomeDoProjeto .
```

<br>

```shell
python manage.py startapp NomeDaAplicação
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Projeto - Settings.py
```

```ad-quote
title:

|**Configuração**|**Variável/Local**|**Valor Sugerido**|
|---|---|---|
|Modo de Depuração|`DEBUG`|`True`|
|Registro da Aplicação|`INSTALLED_APPS`|_'nome_da_sua_app'_|
|Busca Automática de Templates|`TEMPLATES -> APP_DIRS`|`True`|
|Diretório de Templates Global|`TEMPLATES -> DIRS`|`['templates']`|

|**Configuração**|**Variável/Local**|**Descrição / Valor Sugerido**|
|---|---|---|
|Banco de Dados|`DATABASES`|Define o motor (ex: _sqlite3_ ou _postgresql_) e o nome do arquivo/base.|
|Idioma do Sistema|`LANGUAGE_CODE`|Define o idioma da interface (ex: _'pt-br'_).|
|Fuso Horário|`TIME_ZONE`|Ajusta o horário para a sua região (ex: _'America/Sao_Paulo'_).|
|Arquivos Estáticos|`STATIC_URL`|Define o prefixo da _URL_ para arquivos _CSS_ e _JS_ (ex: _'static/'_).|
|Hosts Permitidos|`ALLOWED_HOSTS`|Lista de domínios que podem acessar o site (vazio em desenvolvimento).|
|Gerenciamento de Mídia|`MEDIA_URL`|Define a _URL_ para arquivos enviados pelos usuários.|

```

````

````ad-quote
title:

```ad-quote
title:
###### C ) Terminal - Criando arquivos
```

```shell
cd NomeDaAplicação
```

<br>

```shell
touch urls.py
```

<br>

```shell
mkdir templates
```

<br>

```shell
cd templates
```

<br>

```shell
touch index.html
```

````

````ad-quote
title:

```ad-quote
title:
###### D ) Aplicação - Views.py
```

```ad-quote
title:
<p align="justify">Criar todas as Views. As mesmas são necessárias para referenciar os arquivos '.html' que serão carregados ao iniciar o servidor.</p>
```

```python
def index(request):

return render(request, 'index.html')
```

````

````ad-quote
title:

```ad-quote
title:
###### E ) Projeto / Aplicação - Urls.py
```

```ad-quote
title:
<p align="justify">Dentro do arquivo Projeto/Urls.py apenas faça a referência dos arquivos Aplicação/Urls.py</p>
```

```python
urlpatterns = [
	path('admin/', admin.site.urls),
	path('', include('App.urls')),
]
```

```ad-quote
title:
<p align="justify">Dentro do Aplicação/Urls.py referencie as páginas .html que estão presentes no Aplicação/Templates</p>
```

```python
from django.urls import path
from .views import index, contato

urlpatterns = [
	path('', index),
	path('contato', contato),
]
```

````

