
---



---

```ad-done
title:
#### **Fase 1 ) - ...**
```

---

````ad-quote
title:

##### **01 )** - Tipos de views

```ad-quote
title:
Existem cinco maneiras principais de construir essas rotas. A evolução delas vai do modo mais manual até o modo mais automático. A seguir, apresenta-se cada uma dessas abordagens para facilitar a compreensão das opções disponíveis no ecossistema do Django e do Django Rest Framework.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Views Baseadas em Funções_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Descrição*
```

```ad-quote
title:

<p align="justify">Esta é a forma mais antiga e manual de criar uma rota. Escreve-se uma função simples em Python que recebe o pedido de quem está usando o sistema e devolve uma resposta. No desenvolvimento de APIs, utiliza-se um comando especial chamado api_view logo acima da função. O código fica totalmente transparente e a leitura das instruções ocorre de cima para baixo. Isso permite entender perfeitamente o fluxo da informação. É a melhor escolha para lógicas muito complexas que não envolvem banco de dados.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Problema ideal*
```

```ad-quote
title:

<p align="justify">Um sistema que precisa receber um aviso de um serviço de pagamento externo. Esse processo não salva dados em uma tabela comum. Exige apenas o recebimento da requisição, a validação de uma assinatura de segurança e o disparo de um email de recibo para o cliente.</p>
```

```python

# views.py
from rest_framework.decorators import api_view
from rest_framework.response import Response

@api_view(['POST'])
def processar_pagamento(request):
    return Response({"status": "Pagamento confirmado e email enviado"})


#   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #


# urls.py
from django.urls import path
from .views import processar_pagamento

urlpatterns = [
    path("pagamento/", processar_pagamento),
]

```

````

````ad-quote
title:  

```ad-quote
title:  

###### C ) *Implementação* - *( 2/10 )*
```

```ad-quote
title:  
A simplicidade visual obriga o programador a construir cada etapa do processo manualmente. Isso dispensa o estudo de regras complexas do framework. O código fica bem mais longo e o aprendizado se torna muito rápido.
```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Views Baseadas em Classes Padrão_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Descrição*
```

```ad-quote
title:

<p align="justify">O sistema original introduziu o uso de classes para organizar melhor o código das páginas da internet. Cria-se uma classe que herda a estrutura da classe View original. Essa abordagem ajuda a organizar as rotas por blocos lógicos. A separação entre o código que busca informações e o código que salva informações ocorre de uma forma muito limpa.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Problema ideal*
```

```ad-quote
title:

<p align="justify">Um projeto que precisa exibir uma página inicial simples em HTML sem usar as ferramentas de API. Essa solução é perfeita para renderizar telas tradicionais e separar a lógica do que acontece quando o usuário entra na página do que acontece quando um formulário é enviado.</p>
```

```python

# views.py
from django.views import View
from django.http import HttpResponse

class PaginaInicial(View):
    def get(self, request):
        return HttpResponse("Bem-vindo ao sistema de tarefas")


#   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #


# urls.py
from django.urls import path
from .views import PaginaInicial

urlpatterns = [
    path("inicio/", PaginaInicial.as_view()),
]

```

````

````ad-quote
title:  

```ad-quote
title:  

###### C ) *Implementação* - *( 4/10 )*
```

```ad-quote
title:  
A estrutura de classes organiza o código e automatiza uma pequena parte do trabalho. Em troca dessa ajuda, exige um estudo inicial mais aprofundado sobre como o sistema divide as responsabilidades.
```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.3 ) - _APIView_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Descrição*
```

```ad-quote
title:

<p align="justify">Essa classe funciona como uma versão melhorada das classes padrão. Ela foi criada especificamente para a construção de APIs. Ela entrega ferramentas prontas para ler dados na internet e gerencia toda a parte de segurança da rota. A principal força dessa estrutura é manter um controle muito alto sobre as regras do projeto.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Problema ideal*
```

```ad-quote
title:

<p align="justify">Um aplicativo que precisa consultar a cotação de uma moeda em um serviço externo. A rota precisa receber o pedido do usuário, fazer uma chamada para outro servidor na internet, processar a resposta e entregar um formato final customizado que não existe no próprio banco de dados.</p>
```

```python

# views.py
from rest_framework.views import APIView
from rest_framework.response import Response

class CotacaoMoeda(APIView):
    def get(self, request):
        dados = {"moeda": "Dólar", "valor": 5.20}
        return Response(dados)


#   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #


# urls.py
from django.urls import path
from .views import CotacaoMoeda

urlpatterns = [
    path("cotacao/", CotacaoMoeda.as_view()),
]

```

````

````ad-quote
title:  

```ad-quote
title:  

###### C ) *Implementação* - *( 5/10 )*
```

```ad-quote
title:  
Este é o ponto de equilíbrio exato do ecossistema. O tempo que você gasta digitando a lógica do banco de dados é praticamente igual ao tempo que você gasta estudando as regras de segurança prontas do sistema.
```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.4 ) - _Views Genéricas_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Descrição*
```

```ad-quote
title:

<p align="justify">Essas são as classes que combinam ações. Elas pegam as operações mais repetitivas dos bancos de dados e as transformam em pacotes prontos. Com isso, economiza-se dezenas de linhas de código. É necessário apenas informar qual é a tabela do banco de dados e qual é o validador dos dados para a rota funcionar.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Problema ideal*
```

```ad-quote
title:

<p align="justify">A construção de um portal de notícias. Os visitantes comuns podem apenas acessar a lista completa de artigos ou ler um artigo específico. Ninguém pode criar ou apagar os textos pela API pública. As views genéricas resolvem isso fornecendo classes limitadas exclusivamente para a ação de leitura.</p>
```

```python

# views.py
from rest_framework import generics
from .models import Artigo
from .serializers import ArtigoSerializer

class ListarArtigos(generics.ListAPIView):
    queryset = Artigo.objects.all()
    serializer_class = ArtigoSerializer


#   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #


# urls.py
from django.urls import path
from .views import ListarArtigos

urlpatterns = [
    path("artigos/", ListarArtigos.as_view()),
]

```

````

````ad-quote
title:  

```ad-quote
title:  

###### C ) *Implementação* - *( 8/10 )*
```

```ad-quote
title:  
O sistema entrega a rota quase pronta e poupa muita digitação. Para conseguir essa velocidade de desenvolvimento, o programador paga o preço de precisar compreender o funcionamento de várias funções invisíveis.
```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.5 ) - _ViewSets e ModelViewSets_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Descrição*
```

```ad-quote
title:

<p align="justify">Esse é o nível máximo de automação. Agrupa-se todas as ações possíveis de uma tabela em um bloco único de código. Gera todas as rotas de criação, leitura, atualização e exclusão de uma vez. O arquivo de endereços da aplicação fica minúsculo com a ajuda do roteador automático.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Problema ideal*
```

```ad-quote
title:

<p align="justify">A construção do painel administrativo de uma loja virtual. O estoquista precisa ter liberdade total para criar produtos novos, atualizar preços, listar o estoque inteiro e remover itens descontinuados. Todas as operações clássicas de banco de dados são necessárias sobre a mesma tabela.</p>
```

```python

# views.py
from rest_framework import viewsets
from .models import Produto
from .serializers import ProdutoSerializer

class ProdutoViewSet(viewsets.ModelViewSet):
    queryset = Produto.objects.all()
    serializer_class = ProdutoSerializer


#   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #


# urls.py
from django.urls import path, include
from rest_framework.routers import DefaultRouter
from .views import ProdutoViewSet

roteador = DefaultRouter()
roteador.register(r'produtos', ProdutoViewSet, basename='produto')

urlpatterns = [
    path("", include(roteador.urls)),
]

```

````

````ad-quote
title:  

```ad-quote
title:  

###### C ) *Implementação* - *( 10/10 )*
```

```ad-quote
title:  
A automação total esconde todas as engrenagens do projeto. O desenvolvedor não escreve quase nada para a rota funcionar. O custo disso é a necessidade de leitura profunda da documentação oficial sempre que for preciso modificar alguma regra básica de comportamento.
```

````

---
