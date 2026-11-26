---
banner: "![[Pasted image 20251221174537.png]]"
---

---

```ad-done
title:

#### **Fase 1 ) - Acesso Administrativo**

```

---

````ad-quote
title:

##### **01 )** - Criação do Superusuário

```ad-quote
title:
<p align="justify">O ponto de partida para gerenciar qualquer projeto Django é a criação de uma conta com privilégios administrativos totais. Este processo é realizado diretamente através da interface de linha de comando do framework.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Criando a Senha
```

```ad-quote
title:
|**Campo**|**Descrição do Input**|**Obrigatoriedade**|
|---|---|---|
|Username|OfAndreS|Obrigatório.|
|Email address|...|Opcional.|
|Password|3278|Obrigatório.|
|Password (again)|3278|Obrigatório.|
```

```python
python manage.py createsuperuser
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Inicialização do Ambiente Local
```

```ad-quote
title:
<p align="justify">Para que a interface administrativa seja renderizada e processe as tentativas de login, o servidor de desenvolvimento deve estar ativo e escutando as requisições na porta definida.</p>
```

```python
python manage.py runserver
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Acesso ao Painel de Controle
```

```ad-quote
title:
<p align="justify">Com o serviço em execução, o acesso é feito via navegador. A rota padrão do Django concentra todas as ferramentas de manipulação de modelos de dados.</p>
```

```shell
http://127.0.0.1:8000/admin/
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Manutenção e Recuperação de Credenciais

```ad-quote
title:
<p align="justify">Existem situações onde o acesso é perdido ou precisa ser alterado programaticamente. O Django oferece ferramentas tanto via terminal direto quanto via shell interativo para estas finalidades.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Alteração Direta de Senha
```

```ad-quote
title:
Utilize este comando caso você possua o nome do usuário e precise definir uma nova credencial sem entrar no ambiente Python.
```

```python
python manage.py changepassword nome_do_usuario
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Recuperação via Django Shell
```

```ad-quote
title:
Em cenários de manutenção avançada, você pode manipular o objeto do usuário diretamente no banco de dados através da API do Django.
```

```python
from django.contrib.auth.models import User

# Localiza o usuário pelo nome
user = User.objects.get(username='seu_admin')

# Define e salva a nova credencial
user.set_password('nova_senha_123')
user.save()
```

````

---
