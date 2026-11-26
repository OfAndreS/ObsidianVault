A estruturação do ambiente de desenvolvimento abrange pacotes básicos e configurações de segurança, controle de acesso, paginação e permissões de rede. O processo exige a execução de etapas em uma ordem específica para garantir a comunicação correta entre as ferramentas.

https://pythonacademy.com.br/blog/construcao-de-apis-com-django-rest-framework

https://pythonacademy.com.br/assets/posts/drf/drf-classes.png

---

```ad-done
title:
#### **Fase 1 ) - ...**
```

---

````ad-quote
title:

##### **01 )** - Descrição

```ad-quote
title:
<p align="justify"></p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Instalação_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Elementos Base*
```

```ad-quote
title:
<p align="justify">Além dos pacotes base, instalamos o pacote corsheaders que permite a comunicação entre a API e o navegador. Ademais, o pacote simplejwt gerencia as chaves de acesso dos usuários.</p>
```

```Bash

conda create --name DjangoAPI python=3.10
conda activate DjangoAPI
pip install django djangorestframework django-cors-headers djangorestframework-simplejwt

```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Criação do projeto*
```

```Shell

django-admin startproject nome_do_projeto .

```

````

````ad-quote
title:

```ad-quote
title:
###### C ) *Criando e configurando um app*
```

```bash

python manage.py startapp nome_do_app
python manage.py migrate

```

```ad-quote
title:
<p align="justify">No Django sempre precisamos adicionar novos aplicativos a configuração INSTALLED_APPS, presente no arquivo Settings.py.</p>
```

```python

# django_project/settings.py
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    # Local
    "nome_do_app.apps.nome_do_appConfig",  # new
]

```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _.gitignore_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Código do arquivo*
```

```.gitignore

.venv/
venv/
env/
ENV/
env.bak/
venv.bak/
__pycache__/
*.py[cod]
*$py.class
.pytest_cache/
.coverage
htmlcov/
*.sqlite3
media/
media_root/
staticfiles/
static_root/
.env
.secrets
local_settings.py
.vscode/
.idea/
*.suo
*.ntvs*
*.njsproj
*.sln
*.swp
.DS_Store
Thumbs.db


```

````

---

```ad-done
title:
#### **Fase 2 ) - ...**
```

---

````ad-quote
title:

##### **02 )** - Descrição 

```ad-quote
title:
<p align="justify"></p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Models.py_ - [[DJ - Models.py | { X }]]
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Criando um modelo*
```

```ad-quote
title:
<p align="justify">Um método __str__ também é adicionado para fornecer um nome legível para cada instância de modelo futuro.</p>
```

```python

# nome_do_app/models.py
from django.db import models

class Todo(models.Model):
    title = models.CharField(max_length=200)
    body = models.TextField()

    def __str__(self):
        return self.title

```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Realizando o Migrate*
```

```ad-quote
title:
<p align="justify">  
Já que atualizamos nosso modelo, é hora da dança de duas etapas do Django de criar um novo arquivo de migração e então sincronizar o banco de dados com as alterações.</p>
```

```Bash

python manage.py makemigrations nome_do_app
python manage.py migrate

```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Admin.py_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Elaborando o código*
```

```python

# nome_do_app/admin.py
from django.contrib import admin

from .models import Todo

class TodoAdmin(admin.ModelAdmin):
    list_display = (
        "title",
        "body",
    )


admin.site.register(Todo, TodoAdmin)

```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Executando o comando*
```

```ad-quote
title:
<p align="justify">Agora podemos criar uma conta de superusuário para fazer login no administrador.</p>
```

```Bash

python manage.py createsuperuser

```

````

Start up the local server again with `python manage.py runserver` and navigate to the admin section at `http://127.0.0.1:8000/admin/`. Log in and click on “+ Add” next to `Todos`. Create 3 new todo items, making sure to add a title and body for both. Here’s what mine looks like:

> [!done] **_New_**

```ad-quote
title:

##### 2.3 ) - _Tests.py_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Elaborando o código*
```

```ad-quote
title:
<p align="justify">Queremos confirmar se o título e o corpo aparecem conforme o esperado, assim como o método __str__ no modelo.</p>
```

```python

# nome_do_app/tests.py
from django.test import TestCase

from .models import Todo

class TodoModelTest(TestCase):
    @classmethod
    def setUpTestData(cls):
        cls.todo = Todo.objects.create(
            title="First Todo",
            body="A body of text here"
        )

    def test_model_content(self):
        self.assertEqual(self.todo.title, "First Todo")
        self.assertEqual(self.todo.body, "A body of text here")
        self.assertEqual(str(self.todo), "First Todo")

```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Executando o comando*
```

```Bash

python manage.py test

```

````

---

```ad-done
title:
#### **Fase 3 ) - **
```

---

````ad-quote
title:

##### **03 )** - Descrição

```ad-quote
title:
<p align="justify"></p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Settings.py_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Configurando o framework*
```

```ad-quote
title:
<p align="justify">O aprendizado das configurações padrão exige tempo, uma vez que o Django REST Framework possui uma vasta gama de diretrizes implícitas, cuja <a href="https://www.django-rest-framework.org/api-guide/settings/">documentação oficial</a> traz a relação completa. A permissão AllowAny é uma delas.</p>
```

```python

# django_project/settings.py
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    # 3rd party
    "rest_framework",  # new
    # Local
    "todos.apps.TodosConfig",  
]

REST_FRAMEWORK = {
    "DEFAULT_PERMISSION_CLASSES": [
        "rest_framework.permissions.AllowAny",
    ],
}

```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.2 ) - _Urls.py_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Adicionando as rotas*
```

```ad-quote
title:
<p align="justify">É uma boa ideia ter todos os endpoints da API em um caminho consistente, como api/ caso seja necessário adicionar páginas web tradicionais do Django posteriormente.</p>
```

```python

# django_project/urls.py
from django.contrib import admin
from django.urls import path, include   # new

urlpatterns = [
    path("admin/", admin.site.urls),
    path("api/", include("todos.urls")),  # new
]

```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Configurando as rotas*
```

```python

# nome_do_app/urls.py
from django.urls import path

from .views import ListTodo, DetailTodo

urlpatterns = [
    path("<int:pk>/", DetailTodo.as_view(), name="todo_detail"),
    path("", ListTodo.as_view(), name="todo_list"),
]

```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.3 ) - _Serializers.py_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Expondo os dados*
```

```ad-quote
title:
<p align="justify">Estamos especificando qual modelo usar e os campos específicos que queremos expor. Além disso, o id que é similar a pk é criado automaticamente pelo Django. Portanto, não precisamos defini-lo dentro do model.</p>
```

```python

# nome_do_app/serializers.py
from rest_framework import serializers

from .models import Todo

class TodoSerializer(serializers.ModelSerializer):
    class Meta:
        model = Todo
        fields = (
            "id",
            "title",
            "body",
        )

```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.3 ) - _Views.py_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Estroturando o código*
```

```ad-quote
title:
<p align="justify">No topo do arquivo, são importadas as generic views do Django REST Framework, o modelo Todo e o TodoSerializer recém-criado. Conforme definido no arquivo todos/urls.py, existem duas rotas e, consequentemente, duas views distintas. A view ListTodo herda de ListAPIView para gerenciar a listagem dos dados, enquanto a DetailTodo herda de RetrieveAPIView para lidar com a exibição de detalhes.</p>
```

```python

# nome_do_app/views.py
from rest_framework import generics

from .models import Todo
from .serializers import TodoSerializer


class ListTodo(generics.ListAPIView):
    queryset = Todo.objects.all()
    serializer_class = TodoSerializer

class DetailTodo(generics.RetrieveAPIView):
    queryset = Todo.objects.all()
    serializer_class = TodoSerializer

```
````

Let’s use Django REST Framework’s browsable API now to interact with our data. Make sure the local server is running and navigate to `http://127.0.0.1:8000/api/` to see our working API list views endpoint.

---