---
banner: "![[Pasted image 20251221174537.png]]"
---

---

```ad-done
title: 

#### **Fase 1 ) - Camada de Persistência - Models**

```

---

````ad-quote
title:

##### **01 )** - A Essência dos Models

```ad-quote
title:
<p align="justify">Um Model no Django não é apenas uma representação de uma tabela; ele é a camada de abstração que encapsula tanto os dados quanto a lógica de negócio associada a eles. Seguindo o princípio DRY (Don't Repeat Yourself), o model centraliza a inteligência da sua aplicação.</p>
```

```ad-quote
title:
<p align="justify">Esta camada funciona como o Coração do sistema, onde a estrutura do banco de dados é definida através de classes Python, permitindo que o desenvolvedor manipule registros sem a necessidade de escrever SQL manualmente.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Estrutura de um Model Robusto

```ad-quote
title:
<p align="justify">Abaixo, apresento um exemplo seguindo as melhores práticas, como o uso de nomes amigáveis para tradução (gettext), métodos de representação e organização de metadados.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Definição da Entidade Categoria
```

```python
from django.db import models
from django.utils.translation import gettext_lazy as _

class Categoria(models.Model):
    nome = models.CharField(_("nome da categoria"), max_length=100, unique=True)
    descricao = models.TextField(_("descrição"), blank=True)

    class Meta:
        verbose_name = _("categoria")
        verbose_name_plural = _("categorias")
        ordering = ['nome']

    def __str__(self):
        return self.nome
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Definição da Entidade Livro e Relacionamentos
```

```python
class Livro(models.Model):
    titulo = models.CharField(_("título"), max_length=255)
    isbn = models.CharField("ISBN", max_length=13, unique=True)
    data_publicacao = models.DateField(_("data de publicação"))
    
    categoria = models.ForeignKey(
        Categoria, 
        on_delete=models.PROTECT, 
        related_name="livros",
        verbose_name=_("categoria")
    )

    class Meta:
        verbose_name = _("livro")
        verbose_name_plural = _("livros")
        ordering = ['-data_publicacao']

    def __str__(self):
        return f"{self.titulo} ({self.data_publicacao.year})"
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Atributos de Campo e Classe Meta

```ad-quote
title:
<p align="justify">Para garantir que seu banco de dados seja escalável e seu código legível, os campos e a classe Meta configuram o comportamento técnico e visual do dado.</p>
```

```ad-quote
title:
|**Atributo**|**Descrição Técnica**|**Impacto**|
|---|---|---|
|null=True|Permite valores nulos no banco.|Estrutura de Dados.|
|blank=True|Permite campo vazio em formulários.|Validação de Interface.|
|unique=True|Impede duplicidade de valores.|Integridade referencial.|
|ordering|Define a ordem padrão de busca.|Performance e Exibição.|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Relacionamentos e Integridade

```ad-quote
title:
<p align="justify">O Django oferece três tipos principais de relacionamentos, cada um exigindo atenção à integridade referencial através do parâmetro on_delete.</p>
```

```ad-quote
title:
|**Tipo de Relacionamento**|**Caso de Uso**|**Comportamento**|
|---|---|---|
|ForeignKey|Um para Muitos|Associa registros dependentes.|
|ManyToManyField|Muitos para Muitos|Gera tabela intermediária.|
|OneToOneField|Um para Um|Extensão única de perfil.|
```

```ad-quote
title:
<p align="justify">O uso de Fat Models (Modelos Gordos) é incentivado para manter a lógica de negócio, como cálculos e validações, dentro da própria classe, deixando as Views mais limpas e focadas no fluxo de requisição.</p>
```
````

---

```ad-done
title:

#### **Fase 2 ) - Evolução do Banco de Dados - Migrations**

```

---

````ad-quote
title:

##### **01 )** - A Filosofia das Migrations

```ad-quote
title:
<p align="justify">No desenvolvimento moderno, o banco de dados não é uma entidade estática. Ele evolui conforme as necessidades do negócio mudam. As migrations resolvem o problema de como propagar essas mudanças entre diferentes ambientes sem a necessidade de intervenção manual via SQL.</p>
```

```ad-quote
title:
<p align="justify">Este mecanismo garante que o esquema do banco de dados esteja sempre sincronizado com o código-fonte, servindo como um sistema de controle de versão para a estrutura das tabelas.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Processo de Propagação

```ad-quote
title:
<p align="justify">O fluxo de trabalho do Django segue um ciclo rigoroso de três etapas para transformar definições de classe em estruturas de dados reais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Alteração no Model
```

```ad-quote
title:
O desenvolvedor modifica a classe em _models.py_, adicionando, removendo ou alterando campos e metadados.
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Detecção - makemigrations
```

```ad-quote
title:
O Django inspeciona as mudanças e gera um arquivo de migração em Python que descreve de forma declarativa o que mudou.
```

```python
python manage.py makemigrations
```

````

````ad-quote
title:

```ad-quote
title:
###### C ) Sincronização - migrate
```

```ad-quote
title:
O framework traduz o arquivo Python para comandos SQL específicos do banco (PostgreSQL, MySQL, etc) e os executa.
```

```python
python manage.py migrate
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Anatomia de uma Migração

```ad-quote
title:
<p align="justify">Um arquivo de migração é uma classe que herda de _Migration_. Ele organiza as dependências para formar um grafo de execução seguro.</p>
```

```ad-quote
title:
|**Componente**|**Função Técnica**|**Impacto**|
|---|---|---|
|Dependencies|Lista de migrações anteriores necessárias.|Garante a ordem cronológica.|
|Operations|Lista de ações sequenciais (AddField, etc).|Define o que será alterado.|
```

```python
from django.db import migrations, models

class Migration(migrations.Migration):
    dependencies = [
        ('biblioteca', '0001_initial'),
    ]
    operations = [
        migrations.AddField(
            model_name='livro',
            name='isbn',
            field=models.CharField(max_length=13, unique=True),
        ),
    ]
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Categorias de Mudança

```ad-quote
title:
<p align="justify">É fundamental distinguir entre alterações na estrutura e alterações no conteúdo para manter a integridade dos dados existentes.</p>
```

```ad-quote
title:
|**Tipo**|**Foco da Operação**|**Automação**|
|---|---|---|
|Schema Migration|Alteração de tabelas e colunas.|Totalmente automática.|
|Data Migration|Manipulação de registros existentes.|Manual via RunPython.|
```

```ad-quote
title:
<p align="justify">Para controlar o histórico, o Django utiliza a tabela interna _django_migrations_ no banco de dados, registrando cada arquivo aplicado para evitar execuções duplicadas.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Melhores Práticas e Conflitos

```ad-quote
title:
<p align="justify">Em ambientes de equipe, a imutabilidade é a regra de ouro: nunca edite uma migração que já foi enviada ao repositório ou produção.</p>
```

```ad-quote
title:
###### Resolução de Conflitos
<p align="justify">Quando dois desenvolvedores criam migrações com o mesmo número, o Django detecta a divergência. A solução é fundir os caminhos através do comando de merge.</p>
```

```python
python manage.py makemigrations --merge
```
````

---