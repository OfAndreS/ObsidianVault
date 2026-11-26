A estruturação do ambiente de desenvolvimento abrange pacotes básicos e configurações de segurança, controle de acesso, paginação e permissões de rede. O processo exige a execução de etapas em uma ordem específica para garantir a comunicação correta entre as ferramentas.

  

**1.Preparação do ambiente e instalação de pacotes:**

A etapa inicial consiste na criação de um ambiente isolado no Conda e na instalação das ferramentas necessárias. Além do pacote principal, adicionam-se recursos para conexão externa e gerenciamento de autenticação. Os comandos a serem executados no terminal são:

  

Bash

```
conda create --name api_avancada python=3.10
conda activate api_avancada
pip install django djangorestframework django-cors-headers djangorestframework-simplejwt
```

O pacote corsheaders permite a comunicação entre a API e o navegador. O pacote simplejwt gerencia as chaves de acesso dos usuários.

  

**2.Criação do projeto base:**

Com as ferramentas instaladas, a estrutura de arquivos do sistema é gerada por meio do comando a seguir:

  

Bash

```
django-admin startproject sistema_central .
```

**3.Registro dos aplicativos:**

No arquivo settings.py, é preciso registrar as novas ferramentas na lista INSTALLED_APPS para que o Django as reconheça:

  

Python

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',
    'corsheaders',
]
```

**4.Configuração dos filtros de conexão:**

No mesmo arquivo settings.py, a lista MIDDLEWARE atua como uma camada intermediária que inspeciona as conexões. A regra do corsheaders deve ser inserida no topo desta lista:

  

Python

```
MIDDLEWARE = [
    'corsheaders.middleware.CorsMiddleware',
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]
```

Logo abaixo desta lista, define-se quais endereços de internet têm permissão para acessar os dados:

  

Python

```
CORS_ALLOWED_ORIGINS = [
    "http://localhost:3000",
    "http://127.0.0.1:3000",
]
```

**5.Definições globais da API:**

O framework concentra as regras gerais em um dicionário de configurações. Este bloco deve ser adicionado ao final do arquivo settings.py:

  

Python

```
REST_FRAMEWORK = {
    'DEFAULT_PAGINATION_CLASS': 'rest_framework.pagination.PageNumberPagination',
    'PAGE_SIZE': 10,
    'DEFAULT_AUTHENTICATION_CLASSES': (
        'rest_framework_simplejwt.authentication.JWTAuthentication',
        'rest_framework.authentication.SessionAuthentication',
    ),
    'DEFAULT_PERMISSION_CLASSES': (
        'rest_framework.permissions.IsAuthenticated',
    ),
    'DEFAULT_THROTTLE_CLASSES': [
        'rest_framework.throttling.AnonRateThrottle',
        'rest_framework.throttling.UserRateThrottle'
    ],
    'DEFAULT_THROTTLE_RATES': {
        'anon': '100/day',
        'user': '1000/day'
    }
}
```

A paginação divide as respostas em blocos de 10 itens. A regra de permissão restringe o acesso apenas a usuários autenticados. A função de limite controla a quantidade de requisições por segundo para evitar sobrecarga no servidor.

  

**6.Configuração das rotas de autenticação:**

A etapa final estabelece os caminhos para a obtenção das chaves de acesso. O arquivo urls.py deve ser ajustado com o seguinte conteúdo:

Python

```
from django.contrib import admin
from django.urls import path
from rest_framework_simplejwt.views import TokenObtainPairView, TokenRefreshView

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/login/', TokenObtainPairView.as_view()),
    path('api/renovar-login/', TokenRefreshView.as_view()),
]
```