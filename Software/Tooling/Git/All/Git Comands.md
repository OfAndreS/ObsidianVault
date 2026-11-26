---
banner: Pasted image 20260712203132.png
banner-x: 50
banner-y: 35
banner-fade: 100
---
---

>[!quote] **Link:** [Git Reference Documentation](https://git-scm.com/docs)

---

```ad-done
title:
#### **Fase 1 ) - Configuração e Inicialização**
```

---

````ad-quote
title:

##### **01 )** - Configuração Inicial

```ad-quote
title:
<p align="justify">Comandos fundamentais para configurar a identidade do usuário e o ambiente de trabalho no Git. Estas configurações são essenciais antes de iniciar qualquer versionamento.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Identidade e Ambiente_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">A configuração do Git define parâmetros essenciais gravados em cada commit (como nome de autor e e-mail), além de ferramentas fundamentais de apoio como o editor de texto padrão e a visualização completa das preferências ativas.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git config --global user.name "Seu Nome"
# Define seu nome de usuário global.


02 ) git config --global user.email "seu@email.com"
# Define seu e-mail global.


03 ) git config --global core.editor "code"
# Configura o editor padrão (ex: VSCode).


04 ) git config --list
# Exibe todas as configurações atuais.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Iniciar Repositórios

```ad-quote
title:
<p align="justify">Comandos para começar o versionamento de um projeto, seja criando um novo repositório localmente ou clonando um existente de uma fonte remota.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Criação e Clonagem_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Todo versionamento inicia com a criação de uma base Git local na pasta do projeto atual ou pelo download completo de uma árvore de trabalho já existente a partir de uma fonte remota.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git init
# Cria um novo repositório local na pasta atual.


02 ) git clone <URL>
# Clona um repositório remoto para a máquina local.
```
````

---

```ad-done
title:
#### **Fase 2 ) - Ciclo de Trabalho Local**
```

---

````ad-quote
title:

##### **03 )** - Trabalhando com Alterações

```ad-quote
title:
<p align="justify">Fluxo de trabalho principal para monitorar, preparar (stage) e salvar (commit) mudanças nos arquivos, além de comandos para restaurar estados anteriores.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Stage e Commits_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O ciclo de vida das modificações circula entre a área de trabalho não rastreada, a área de preparação temporária (Stage/Index) e a persistência final no histórico imutável (Commit). Comandos de restauração garantem controle sobre reversões locais rápidas.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git status
# Mostra arquivos modificados ou rastreados.


02 ) git add <arquivo>
# Adiciona um arquivo específico ao STAGE.


03 ) git add .
# Adiciona todos os arquivos modificados ao STAGE.


04 ) git commit -m "Mensagem"
# Cria um COMMIT com as alterações preparadas.


05 ) git commit --amend
# Corrige ou altera o último COMMIT realizado.


06 ) git restore <arquivo>
# Descarta alterações não commitadas no arquivo.


07 ) git restore --staged <arquivo>
# Remove o arquivo do STAGE sem perder as alterações.


08 ) git reset <arquivo>
# Funciona de forma similar ao restore --staged.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Histórico e Comparações

```ad-quote
title:
<p align="justify">Ferramentas para visualizar a linha do tempo do projeto, inspecionar o histórico de commits e comparar diferenças entre versões ou estados de arquivos.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.1 ) - _Linha do Tempo e Inspeção_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">A auditoria contínua do projeto é feita inspecionando logs estruturados e identificando diferenças pontuais linha por linha entre a pasta de trabalho, a área de stage e commits históricos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git log
# Exibe o histórico completo de commits.


02 ) git log --oneline --graph
# Mostra o histórico resumido com gráfico de BRANCHES.


03 ) git diff
# Mostra alterações que ainda não foram para o STAGE.


04 ) git diff --staged
# Compara alterações no STAGE com o último COMMIT.


05 ) git show <commit>
# Exibe os detalhes e mudanças de um COMMIT específico.
```
````

---

```ad-done
title:
#### **Fase 3 ) - Ramificação e Colaboração**
```

---

````ad-quote
title:

##### **05 )** - Gerenciamento de Branches

```ad-quote
title:
<p align="justify">Comandos para criar, listar, trocar e manipular ramificações (branches), permitindo o desenvolvimento paralelo e organizado de funcionalidades.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 5.1 ) - _Ramificações e Mesclagem_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Branches isolam novas funcionalidades ou correções sem afetar o código principal estável. Ao final do desenvolvimento, as ramificações podem ser mescladas via merge (preservando bifurcações) ou rebase (linearizando o histórico).</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git branch
# Lista as BRANCHES locais existentes.


02 ) git branch <nome>
# Cria uma nova BRANCH.


03 ) git checkout <branch>
# Alterna para uma BRANCH existente.


04 ) git checkout -b <nova-branch>
# Cria e alterna imediatamente para uma nova BRANCH.


05 ) git merge <branch>
# Combina a BRANCH especificada com a atual.


06 ) git rebase <branch>
# Reorganiza os COMMITS criando um histórico linear.


07 ) git branch -d <branch>
# Remove uma BRANCH (apenas se já mesclada).


08 ) git branch -D <branch>
# Força a exclusão de uma BRANCH (mesmo não mesclada).
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Trabalhando com Remotos

```ad-quote
title:
<p align="justify">Operações para conectar o repositório local a servidores remotos (como GitHub ou GitLab), permitindo o envio e recebimento de código.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 6.1 ) - _Sincronização com Servidor_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Repositórios remotos estabelecem a ponte entre o desenvolvimento local e a nuvem colaborativa, viabilizando o envio de commits (push), a obtenção de metadados remotos (fetch) e a integração direta de atualizações (pull).</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git remote -v
# Lista os repositórios remotos configurados.


02 ) git remote add <nome> <URL>
# Adiciona um novo repositório REMOTE.


03 ) git push origin <branch>
# Envia os COMMITS locais para o repositório REMOTE.


04 ) git push -u origin <branch>
# Envia e define o UPSTREAM para tracking automático.


05 ) git pull origin <branch>
# Baixa e mescla automaticamente alterações remotas.


06 ) git fetch origin
# Baixa alterações remotas sem realizar a mesclagem.
```
````

---

```ad-done
title:
#### **Fase 4 ) - Controle de Estados e Recuperação**
```

---

````ad-quote
title:

##### **07 )** - Desfazendo Ações

```ad-quote
title:
<p align="justify">Comandos críticos para reverter estados, corrigir erros ou desfazer commits, variando desde operações suaves até resets destrutivos.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 7.1 ) - _Reversões e Resets_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Operações de reversão tratam desde a retirada de commits preservando modificações em stage (--soft) até a eliminação irreversível de alterações (--hard). O comando revert difere do reset por registrar um novo commit que anula as mudanças anteriores sem apagar o histórico.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git reset --soft <commit>
# Remove COMMITS, mas mantém alterações no STAGE.


02 ) git reset --mixed <commit>
# Padrão: remove COMMITS e tira do STAGE, mantendo arquivos.


03 ) git reset --hard <commit>
# ALERTA: Perde todos os COMMITS e alterações nos arquivos.


04 ) git revert <commit>
# Cria um novo COMMIT que desfaz as mudanças do anterior.


05 ) git revert --no-commit <commit>
# Reverte as mudanças para o estado de trabalho sem criar COMMIT.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Comportamento dos Modos de Reset*
```

```ad-quote
title:
| Modo&nbsp; | Working Directory&nbsp; | Staging Area (Index)&nbsp; | Histórico (HEAD)&nbsp; |
| :--- | :--- | :--- | :--- |
| `--soft` | Inalterado | Inalterado | Movido |
| `--mixed` (padrão) | Inalterado | Resetado | Movido |
| `--hard` | Destruído | Destruído | Movido |
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **08 )** - Stash (Salvamento Temporário)

```ad-quote
title:
<p align="justify">Funcionalidade para guardar temporariamente alterações não finalizadas, permitindo trocar de contexto sem precisar fazer um commit incompleto.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 8.1 ) - _Pilha de Modificações_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">O Stash funciona como um armário temporário estruturado em pilha (LIFO). Ele armazena arquivos modificados e indexados, restaurando a branch para o estado limpo do último commit para que você possa executar outras tarefas emergenciais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git stash
# Armazena alterações não commitadas em uma pilha.


02 ) git stash list
# Lista todos os STASHES guardados.


03 ) git stash apply
# Recupera o último STASH sem removê-lo da lista.


04 ) git stash pop
# Aplica o último STASH e o remove da lista.


05 ) git stash drop
# Deleta um STASH específico da lista.
```
````

---

```ad-done
title:
#### **Fase 5 ) - Versionamento e Manutenção**
```

---

````ad-quote
title:

##### **09 )** - Tags (Versões)

```ad-quote
title:
<p align="justify">Utilizado para marcar pontos específicos na história do repositório como importantes, geralmente para lançamentos de versões (releases).</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 9.1 ) - _Marcadores de Release_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Tags atuam como marcadores indeléveis fixados a um commit específico, muito utilizadas para sinalizar lançamentos formais (releases) e marcos de versões do produto.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git tag
# Lista as TAGS existentes no repositório.


02 ) git tag v1.0.0
# Cria uma TAG leve para a versão especificada.


03 ) git tag -a v1.0.0 -m "Mensagem"
# Cria uma TAG anotada com mensagem descritiva.


04 ) git push --tags
# Envia todas as TAGS locais para o repositório REMOTE.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **10 )** - Utilitários Avançados

```ad-quote
title:
<p align="justify">Ferramentas poderosas para análise, depuração e manutenção do repositório, úteis para resolver problemas complexos ou limpar o ambiente.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 10.1 ) - _Diagnóstico e Manutenção_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definições*
```

```ad-quote
title:
<p align="justify">Recursos de alta precisão que auxiliam na recuperação de referências perdidas (reflog), isolamento binário de falhas (bisect), transporte seletivo de commits entre branches (cherry-pick) e faxina definitiva de arquivos não monitorados (clean).</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Comandos*
```

```bash
01 ) git reflog
# Registro completo de ações, vital para recuperação de dados.


02 ) git bisect
# Realiza busca binária para identificar qual COMMIT introduziu um BUG.


03 ) git cherry-pick <commit>
# Aplica um COMMIT específico de outra via na BRANCH atual.


04 ) git clean -n
# Simula a remoção de arquivos não rastreados (dry-run).


05 ) git clean -f
# Remove permanentemente arquivos não rastreados.
```
````

---