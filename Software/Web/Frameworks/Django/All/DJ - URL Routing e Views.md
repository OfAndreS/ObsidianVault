---
banner: "![[Pasted image 20251221174537.png]]"
---

---

```ad-done
title:

#### **Fase 1 ) - Estrutura de Roteamento - Urls**

```

---

````ad-quote
title:

##### **01 )** - Urls

```ad-quote
title:
<p align="justify">O sistema de roteamento do Django é fundamentado na separação de responsabilidades entre as configurações globais do projeto e a lógica específica de cada aplicativo. Esta estrutura permite que o diretório Projeto funcione como o núcleo de roteamento, enquanto o aplicativo core gerencia a lógica de exibição e interação com o usuário.</p>
```

```ad-quote
title:
<p align="justify">A grande vantagem desta metodologia é a desacoplagem. Você ganha a liberdade de alterar nomes de diretórios ou estruturas de URLs sem causar falhas nos links internos, pois o motor do Django resolve as rotas através dos nomes atribuídos.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Ciclo de Vida da Requisição

```ad-quote
title:
<p align="justify">Quando um usuário acessa uma URL, o sistema percorre um fluxo definido para entregar a resposta correta.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Identificação do Caminho
```

```ad-quote
title:
O Django analisa o arquivo principal _Projeto/urls.py_ e identifica para qual aplicativo a requisição deve ser enviada.
```

```python
path('', include('App.urls'))
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Execução da Função
```

```ad-quote
title:
No arquivo _App/urls.py_, o sistema localiza a função correspondente dentro do arquivo _views.py_ e a executa.
```

```python
path('', views.index, name='url_da_home'),
```

````

````ad-quote
title:

```ad-quote
title:
###### C ) Renderização Final
```

```ad-quote
title:
O comando _render_ dentro da view.py processa o arquivo _HTML_ junto com os dados fornecidos, gerando a página final que o navegador exibe.
```

```python
def index(request):
	return render(request, 'index.html')
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Configuração Global - Projeto/urls.py

```ad-quote
title:
<p align="justify">O arquivo central de URLs atua como o ponto de entrada principal para todas as requisições enviadas ao servidor. A melhor prática consiste em delegar o mapeamento para os aplicativos individuais.</p>
```

```ad-quote
title:
|**Função**|**Descrição Técnica**|**Aplicação**|
|---|---|---|
|Admin|Caminho para o painel administrativo.|Gerenciamento de dados nativo.|
|Include|Importação de arquivos de rotas secundários.|Desacoplagem de módulos da aplicação.|
```

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.register),
    path('', include('App.urls')), 
]
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Roteador do Aplicativo - App/urls.py

```ad-quote
title:
<p align="justify">Cada aplicativo possui seu próprio arquivo de rotas para definir caminhos específicos para os templates. O uso de nomes para as rotas é essencial para garantir a flexibilidade do sistema.</p>
```

```ad-quote
title:
|**Elemento**|**Tipo de Rota**|**Referência Interna**|
|---|---|---|
|Página Inicial|Estática (Raiz)|url_da_home|
|Contato|Estática|url_de_contato|
|Perfil Cliente|Dinâmica (ID)|url_perfil|
```

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='url_da_home'),
    path('contato/', views.contato, name='url_de_contato'),
    path('cliente/<int:id>/', views.perfil_cliente, name='url_perfil'),
]
```
````

---

```ad-done
title:

#### **Fase 2 ) - Lógica de Processamento - Views**

```

---

````ad-quote
title:

##### **01 )** - Definição e Propósito

```ad-quote
title:
<p align="justify">As views constituem o núcleo da lógica no Django. Se as URLs funcionam como o mapa que indica o caminho, as views são as responsáveis por executar as ações ao chegar no destino. Em termos técnicos, uma view é uma função ou classe projetada para processar uma requisição web e retornar uma resposta adequada.</p>
```

```ad-quote
title:
<p align="justify">A função primordial é servir como ponte no padrão MTV (Model-Template-View), gerenciando o fluxo de dados entre o banco de dados e a interface apresentada ao usuário final.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Ciclo de Vida no Padrão MTV

```ad-quote
title:
<p align="justify">A view opera em três etapas distintas para garantir que a interação do usuário resulte em uma resposta válida.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Recebimento de Entrada
```

```ad-quote
title:
O sistema captura um objeto _HttpRequest_, contendo metadados como cookies, dados de formulários e informações do navegador.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Processamento e Lógica
```

```ad-quote
title:
A view interage com o _Model_ para persistir ou buscar informações, executando cálculos e validações de regras de negócio.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Geração de Saída
```

```ad-quote
title:
O ciclo termina com a entrega de um _HttpResponse_, que pode ser a renderização de um template HTML ou o envio de dados em formato JSON.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Implementação: FBV vs CBV

```ad-quote
title:
<p align="justify">Existem duas metodologias principais para construir a lógica dentro do arquivo views.py, cada uma com suas vantagens específicas para o desenvolvimento.</p>
```

```ad-quote
title:
|**Metodologia**|**Descrição Técnica**|**Indicação**|
|---|---|---|
|FBV|Function-Based Views (Baseadas em funções).|Lógicas diretas e iniciantes.|
|CBV|Class-Based Views (Baseadas em classes).|Reutilização de código e projetos complexos.|
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Vantagens e Desvantagens
```

```ad-quote
title:
|**Característica**|**Function-Based Views (FBV)**|**Class-Based Views (CBV)**|
|---|---|---|
|Curva de Aprendizado|Baixa: Python puro e intuitivo.|Alta: Exige domínio de POO e Mixins.|
|Reutilização|Dificultada: Gera repetição de código.|Excelente: Uso intensivo de herança.|
|Legibilidade|Alta: O fluxo é explícito e linear.|Média: A lógica pode estar escondida na classe pai.|
|Flexibilidade|Total: Controle sobre cada linha.|Estruturada: Segue padrões pré-definidos.|
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Quando utilizar Function-Based Views - FBV
```

```ad-quote
title:
<p align="justify">As funções são ideais para situações onde a lógica é única ou muito específica, não seguindo os padrões convencionais do Django (como um dashboard customizado ou integração com APIs externas complexas).</p>
```

```ad-quote
title:

|**Cenário ou Vantagem**|**Descrição e Aplicação**|
|---|---|
|Lógicas customizadas|Indicado para situações onde o processamento de dados é específico e não se encaixa nos padrões de um _CRUD_ simples.|
|Prototipagem rápida|Utilizado para validar ideias de forma ágil, evitando a complexidade inicial de estruturas de herança.|
|Facilidade de Depuração|Proporciona um fluxo de execução linear, tornando o erro facilmente rastreável dentro do escopo da própria função.|

```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Quando utilizar Class-Based Views - CBV
```

```ad-quote
title:
<p align="justify">As classes brilham em operações padrão de banco de dados, conhecidas como CRUD (Create, Read, Update, Delete). Elas permitem que o desenvolvedor escreva pouquíssimas linhas de código para funcionalidades robustas.</p>
```

```ad-quote
title:

|**Contexto ou Recurso**|**Descrição e Aplicação**|
|---|---|
|Operações CRUD|Realização de listagem, criação, edição e deleção de objetos originados do _Model_.|
|Projetos extensos|Ambientes onde a padronização do código e o princípio _DRY_ (_Don't Repeat Yourself_) são vitais para a manutenção.|
|Mixins|Técnica utilizada quando existe a necessidade de injetar comportamentos específicos, como regras de permissões, em múltiplas _views_.|

```

````

````ad-quote
title:

```ad-quote
title:
###### Py ) Código Python
```

```python
# Exemplo de FBV (Function-Based View)
from django.shortcuts import render
from django.http import HttpResponse

def minha_view_simples(request):
    if request.method == 'GET':
        return render(request, 'index.html')
    elif request.method == 'POST':
        return HttpResponse("Dados recebidos!")
```

<br>

```python
# Exemplo de CBV (Class-Based View)
from django.views.generic import TemplateView

class HomeView(TemplateView):
    template_name = "index.html"
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Manipulação de Dados e Contexto

```ad-quote
title:
<p align="justify">Para que os dados do banco de dados apareçam no HTML, a view utiliza um dicionário chamado contexto. Este elemento permite que o comando render realize a mesclagem entre a lógica Python e a estrutura do Template.</p>
```

```python
from .models import Cliente

def lista_clientes(request):
    todos_clientes = Cliente.objects.all()
    
    # O contexto envia as variáveis para o HTML
    contexto = {
        'lista': todos_clientes,
        'quantidade': todos_clientes.count(),
        'status_sistema': 'Ativo'
    }
    
    return render(request, 'clientes.html', contexto)
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Ferramentas e Atalhos - Shortcuts

```ad-quote
title:
<p align="justify">O módulo _django.shortcuts_ oferece funções que agilizam tarefas repetitivas no desenvolvimento de views, aumentando a produtividade e legibilidade do código.</p>
```

```ad-quote
title:
|**Atalho**|**Finalidade**|
|---|---|
|render()|Une o template ao contexto para retornar um HttpResponse.|
|redirect()|Encaminha o usuário para uma nova rota ou view específica.|
|get_object_or_404()|Busca um item ou gera erro 404 caso ele não exista.|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Boas Práticas e Segurança

```ad-quote
title:
<p align="justify">Manter um código limpo e seguro é essencial para a manutenção do projeto a longo prazo.</p>
```

```ad-quote
title:
* Views Magras: Evite lógicas complexas no arquivo de views; mova cálculos para os _models_ ou _services_.
* Tratamento de Exceções: Utilize blocos _try/except_ para prever falhas na busca de dados.
* Proteção de Acesso: Aplique decoradores como _@login_required_ para restringir o acesso a usuários não autenticados.
```
````

---

