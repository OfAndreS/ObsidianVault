
---

````ad-quote
title:

```ad-quote
title:
<p align="justify">A Biblioteca OS é uma das bibliotecas padrão mais poderosas do Python, fornecendo uma maneira portátil de usar funcionalidades dependentes do sistema operacional. Com ela, é possível interagir com o sistema de arquivos, gerenciar processos, acessar variáveis de ambiente e muito mais, tudo isso de forma agnóstica ao sistema operacional subjacente (seja Windows, Linux ou macOS).</p>

<p align="justify">Este guia detalha as principais funções disponíveis na Biblioteca OS, organizadas em categorias para facilitar a compreensão e a consulta.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Gerenciamento de Arquivos e Diretórios

```ad-quote
title:
<p align="justify">Essas funções permitem criar, remover, inspecionar e manipular arquivos e diretórios no sistema de arquivos.</p>
```

```ad-quote
title:

| Função | Descrição |
|---|---|
| `listdir(path='.')` | Retorna uma lista contendo os nomes das entradas no diretório dado por *path*. |
| `mkdir(path)` | Cria um diretório chamado *path*. |
| `makedirs(path, exist_ok=False)` | Cria diretórios recursivamente. Se `exist_ok` for `True`, não levanta exceção se o diretório já existir. |
| `remove(path)` | Remove (deleta) o arquivo *path*. |
| `rmdir(path)` | Remove (deleta) o diretório *path*. O diretório deve estar vazio. |
| `removedirs(path)` | Remove diretórios recursivamente. Tenta remover todos os diretórios vazios pai no caminho especificado. |
| `rename(src, dst)` | Renomeia o arquivo ou diretório de *src* para *dst*. |
| `renames(old, new)` | Renomeia recursivamente, criando diretórios intermediários para *new* se necessário. |
| `stat(path)` | Obtém o status de um arquivo ou descritor de arquivo. Retorna um objeto com informações como tamanho, datas, etc. |
| `scandir(path='.')` | Retorna um iterador de objetos `os.DirEntry` correspondentes às entradas no diretório. É mais eficiente que `listdir()`. |
| `walk(top)` | Gera os nomes de arquivos em uma árvore de diretórios, percorrendo a árvore de cima para baixo ou de baixo para cima. |
| `link(src, dst)` | Cria um link físico apontando para *src* chamado *dst*. |
| `symlink(src, dst)` | Cria um link simbólico apontando para *src* chamado *dst*. |
| `unlink(path)` | Sinônimo para `remove()`. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Navegação e Manipulação de Caminhos (Paths)

```ad-quote
title:
<p align="justify">Funções para consultar e alterar o diretório de trabalho atual e manipular caminhos de arquivos. Muitas operações detalhadas de caminhos estão no submódulo `os.path`.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `getcwd()` | Retorna uma string representando o diretório de trabalho atual. |
| `chdir(path)` | Altera o diretório de trabalho atual para *path*. |
| `os.path.join(path, *paths)` | Junta um ou mais componentes de caminho de forma inteligente. Essencial para código multiplataforma. |
| `os.path.abspath(path)` | Retorna uma versão absoluta e normalizada do nome do caminho *path*. |
| `os.path.basename(path)` | Retorna o nome base (arquivo ou último diretório) do caminho *path*. |
| `os.path.dirname(path)` | Retorna o nome do diretório do caminho *path*. |
| `os.path.exists(path)` | Retorna `True` se *path* se refere a um caminho existente. |
| `os.path.isdir(path)` | Retorna `True` se *path* for um diretório existente. |
| `os.path.isfile(path)` | Retorna `True` se *path* for um arquivo regular existente. |
| `os.path.getsize(path)` | Retorna o tamanho, em bytes, de *path*. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Gerenciamento de Processos

```ad-quote
title:
<p align="justify">Funções para executar comandos do sistema e gerenciar informações sobre processos.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `system(command)` | Executa o comando (uma string) em um subshell. |
| `startfile(path)` | Inicia um arquivo com sua aplicação associada (apenas para Windows). |
| `getpid()` | Retorna o ID do processo atual. |
| `getppid()` | Retorna o ID do processo pai. |
| `kill(pid, sig)` | Envia o sinal *sig* para o processo *pid*. |
| `cpu_count()` | Retorna o número de CPUs no sistema. |
| `getlogin()` | Retorna o nome do usuário logado no terminal controlador do processo. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Variáveis de Ambiente

```ad-quote
title:
<p align="justify">Funções para interagir com as variáveis de ambiente do sistema operacional.</p>
```
```ad-quote
title:

| Objeto/Função | Descrição |
|---|---|
| `environ` | Um objeto de mapeamento que representa as variáveis de ambiente. `os.environ['HOME']`. |
| `getenv(key, default=None)` | Obtém o valor de uma variável de ambiente. Retorna `default` se a variável não existir. |
| `putenv(key, value)` | Define o valor da variável de ambiente *key* para a string *value*. |
| `unsetenv(key)` | Remove (deleta) a variável de ambiente *key*. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Permissões e Propriedade de Arquivos

```ad-quote
title:
<p align="justify">Funções para gerenciar permissões de acesso e propriedade de arquivos e diretórios.</p>
```
```ad-quote
title:

| Função | Descrição |
|---|---|
| `access(path, mode)` | Verifica se o processo real tem acesso a *path*. *mode* pode ser `os.F_OK`, `os.R_OK`, `os.W_OK`, `os.X_OK`. |
| `chmod(path, mode)` | Altera o modo (permissões) do caminho *path* para o numérico *mode*. |
| `chown(path, uid, gid)` | Altera o ID do proprietário (uid) e do grupo (gid) do caminho *path*. (Não disponível no Windows). |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Informações e Funções do Sistema Operacional

```ad-quote
title:
<p align="justify">Funções que fornecem informações gerais sobre o sistema operacional ou funcionalidades de baixo nível.</p>
```
```ad-quote
title:

| Objeto/Função | Descrição |
|---|---|
| `name` | O nome do módulo do sistema operacional importado. `posix` para Linux/macOS, `nt` para Windows. |
| `uname()` | Retorna informações que identificam o sistema operacional atual. (Não disponível no Windows). |
| `urandom(n)` | Retorna *n* bytes de dados aleatórios e criptograficamente seguros. |
| `linesep` | A string usada para separar linhas nesta plataforma (`'\n'`, `'\r\n'`). |
| `sep` | O separador de caminhos usado pelo sistema operacional (`'/'` ou `'\'`). |
| `curdir` | A string que representa o diretório atual (e.g., `'.'`). |
| `pardir` | A string que representa o diretório pai (e.g., `'..'`). |

```
````

---