
---
### O banco de dados no arquivo Model

O arquivo models.py define o formato da informação e cria a estrutura no banco de dados. O código abaixo cria uma tabela simples de tarefas.

  

Python

```
from django.db import models

class Tarefa(models.Model):
    titulo = models.CharField(max_length=100)
    concluida = models.BooleanField(default=False)

    def __str__(self):
        return self.titulo
```

### O mapa de endereços na Rota

O arquivo urls.py funciona como o painel de navegação do site. Ele liga um endereço de internet digitado pelo visitante a uma função específica do sistema.

  

Python

```
from django.urls import path
from . import views

urlpatterns = [
    path('minhas-tarefas/', views.lista_tarefas, name='lista_tarefas'),
]
```

### O processamento de dados na View

O arquivo views.py concentra a inteligência do processo. Ele recebe o pedido do navegador, faz a consulta no banco de dados e repassa o resultado para a página visual.

  

Python

```
from django.shortcuts import render
from .models import Tarefa

def lista_tarefas(request):
    tarefas_do_banco = Tarefa.objects.all()
    pacote_de_dados = {'tarefas': tarefas_do_banco}
    
    return render(request, 'tarefas.html', pacote_de_dados)
```

O termo request representa o pedido inicial do visitante. O termo render é a ferramenta de entrega. Ele costura as variáveis com o código visual da página.

  

### A exibição no Template

O arquivo tarefas.html organiza o que aparece na tela do navegador. Ele mistura códigos da linguagem visual tradicional com comandos do próprio Django.

  

HTML

```
<!DOCTYPE html>
<html>
<body>
    <h1>Lista de Tarefas</h1>
    
    <ul>
        {% for tarefa in tarefas %}
            <li>{{ tarefa.titulo }} - Concluída: {{ tarefa.concluida }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

As chaves duplas e os sinais de porcentagem são códigos dinâmicos. Eles indicam os espaços exatos onde as informações reais da base de dados devem aparecer quando a página carregar.

---
Code

├── django_project
│   ├── __init__.py
|   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
└── .venv/

The `.venv` directory was created with our virtual environment but Django has added a `django_project` directory and a `manage.py` file. Within `django_project` are five new files:

- `__init__.py` indicates that the files in the folder are part of a Python package. Without this file, we cannot import files from another directory which we will be doing a lot of in Django!
- `asgi.py` allows for an optional [Asynchronous Server Gateway Interface](https://asgi.readthedocs.io/en/latest/specs/main.html) to be run
- `settings.py` controls our Django project’s overall settings
- `urls.py` tells Django which pages to build in response to a browser or URL request
- `wsgi.py` stands for [Web Server Gateway Interface](https://en.wikipedia.org/wiki/Web_Server_Gateway_Interface) which helps Django serve our eventual web pages.

Shell

├── books
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py

Each app has a `__init__.py` file identifying it as a Python package and there are 6 new files created:

- `admin.py` is a configuration file for the built-in Django Admin app
- `apps.py` is a configuration file for the app itself
- `migrations/` is a directory that stores migrations files for database changes
- `models.py` is where we define our database models
- `tests.py` is for our app-specific tests
- `views.py` is where we handle the request/response logic for our web app