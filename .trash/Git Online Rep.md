
---

>[!example] ### **Manipulando Repositório Online**

---
#### **01 ) Subir um repositório local para o GitHub**

```bash
# Inicializar um repositório Git (se ainda não tiver)
git init

# Adicionar todos os arquivos ao staging area
git add .

# Fazer o primeiro commit
git commit -m "Primeiro commit"

# Criar um repositório no GitHub manualmente e copiar a URL (HTTPS ou SSH)

# Adicionar o repositório remoto (substitua URL pela sua)
git remote add origin https://github.com/seu-usuario/seu-repositorio.git

# Enviar o código para o GitHub (branch main/master)
git push -u origin main
# ou, se estiver usando a branch master antiga:
git push -u origin master
```

```ad-quote
title: **Def**

**Observações:**

- Se o repositório no GitHub for privado, você precisará de uma **chave SSH** configurada ou **token de acesso pessoal** (caso use HTTPS).
    
- O `-u` no `git push` define a branch padrão para futuros pushes.
```

---
#### **02) Clonar um repositório do GitHub para sua máquina**

```bash
# Copie a URL do repositório (HTTPS ou SSH) no GitHub
git clone https://github.com/seu-usuario/seu-repositorio.git

# Entrar na pasta do projeto
cd seu-repositorio
```

**Opções úteis:**

```ad-quote
title: **Clonar em uma pasta específica:**
```

```cpp
git clone https://github.com/seu-usuario/seu-repositorio.git minha-pasta
```

```ad-quote
title: **Clonar apenas uma branch específica:**
```

```cpp
git clone --branch nome-da-branch https://github.com/seu-usuario/seu-repositorio.git
```

---
#### **Comandos Adicionais Úteis**

```ad-quote
title: **Verificar repositórios remotos**:
```

```cpp
git remote -v
```

```ad-quote
title: **Alterar URL do remote** (se necessário):
```

```cpp
git remote set-url origin nova-url.git
```

```ad-quote
title: **Atualizar repositório local** (após clonar):
```

```cpp
git pull origin main
```

---
#### **Dica Importante**

```ad-quote
title: Use **SSH** para maior segurança (configure uma chave SSH no GitHub):
```

```cpp
git remote set-url origin git@github.com:seu-usuario/seu-repositorio.git
```

---

>[!example] ### **Lidando com conflitos**

---
#### **Evitando Conflitos**

```ad-quote
title: **Sempre atualize sua branch local antes de trabalhar**:
```

```cpp
git pull origin main
```

```ad-quote
title: Use `rebase` em vez de `merge` para manter o histórico limpo**:
```

```cpp
git pull --rebase origin main
```
---
#### **Identificar que há um conflito**

```ad-quote
title: **Def**

Ao tentar fazer um `git merge` ou `git pull`, você verá uma mensagem como:
```

```cpp
CONFLICT (content): Merge conflict in arquivo.txt
Automatic merge failed; fix conflicts and then commit the result.
```

---
#### **Comandos para Resolver o Conflito**

```ad-quote
title: **Def**

**Passo 1: Verificar os arquivos em conflito**
- Isso mostrará quais arquivos têm conflitos (marcados como **"both modified"**).
```

```cpp
git status
```

```ad-quote
title: **Def**

**Passo 2: Abrir o arquivo conflitante**
- Os conflitos aparecem no arquivo assim:
```

```cpp
<<<<<<< HEAD  
Seu código atual (na branch atual)
=======  
Código vindo da branch que está sendo mesclada
>>>>>>> branch-que-esta-sendo-merged
```

```ad-quote
title: **Def**

**Passo 3: Editar o arquivo manualmente**
- Remova os marcadores (`<<<<<<<`, `=======`, `>>>>>>>`).
    
- Escolha qual versão manter ou combine as alterações manualmente.
```

```cpp
Texto mantido da branch atual
Alguma alteração mesclada da outra branch
```

```ad-quote
title: **Def**

**Passo 4: Adicionar o arquivo resolvido ao staging**

```

```cpp
git add arquivo-conflitante.txt
```

```ad-quote
title: **Def**

**Passo 5: Finalizar o merge**

```

```cpp
git commit -m "Resolvendo conflito de merge entre branch-X e main"
```

```ad-quote
title: **Def**

**Passo 6 (Opcional): Se quiser cancelar o merge**

```

```cpp
//Se você não consegue resolver o conflito e quer abortar:
git merge --abort
```

```cpp
//Ou, se já começou a editar:
git reset --hard
```

---
