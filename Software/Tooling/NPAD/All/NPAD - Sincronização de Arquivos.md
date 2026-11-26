---
banner: "![[Pasted image 20251115123940.png]]"
---
---

````ad-quote
title:

##### **Intro )** - Sincronização

```ad-quote
title:
<p align="justify">Todo o guia é centrado no fluxo de trabalho específico usando o diretório Sync como a raiz de sincronização para todos os projetos.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Sincronização de Arquivos

```ad-quote
title:
<p align="justify">Todos os comandos de sincronização devem ser executados de dentro da pasta ~/Documents/Sync no seu computador local.</p>
```

```ad-quote
title:

| Localização | Caminho |
| :--- | :--- |
| **Computador Local** | <code>~/Documents/Sync/</code> |
```
````

````ad-quote
title:

```ad-quote
title:
######  A ) Criação do .rsync-ignore
```

```ad-quote
title:

| Localização | Caminho |
| :--- | :--- |
| **Computador Local** | <code>~/Documents/Sync/.rsync-ignore</code> |
```

```ad-quote
title:
<p align="justify">O arquivo .risc-ignore funciona exatamente como o .gitignore, impedindo o envio de arquivos e diretórios específicos para a nuvem. Como o comando é executado a partir de /Sync, todos os caminhos definidos no arquivo devem ser relativos a esse diretório, incluindo o nome da pasta do projeto.</p>
```

```bash
# Conteúdo de ~/Documents/SyncDesk/.rsync-ignore

# Ignora pastas do projeto "ProjetoTeste"
ProjetoTeste/.vscode/
ProjetoTeste/notebooks/
ProjetoTeste/.git/

# Ignora arquivos específicos do projeto "ProjetoTeste"
ProjetoTeste/SetupProjeto.sh

# Padrões globais (para qualquer projeto)
__pycache__/
*.pyc
*.log
.DS_Store
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Enviar - Upload Local -> Super
```

```bash
# Entre no diretório Sync
cd ~/Documents/Sync

# Execute o comando de envio
rsync -avz -e "ssh -p 4422" --exclude-from=".rsync-ignore" . super-pc:~/Sync/
```

```bash
# rsync - Programa de sincronização de arquivos.
# -avz - Flags do comando
# -e "ssh -p 4422" - Define o uso do protocolo Sync na porta 4422
# --exclude-from=".rsync-ignore" - Ignora arquivos do .rsync-ignore
# . - Conteúdo do diretório do Sync/ no super
# super-pc:~/Sync/ - Origem dos dados para a pasta Sync no super-pc
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) - Baixar - Download Super -> Local
```

```ad-quote
title:
<p align="justify">Não é necessário usar --exclude-from no download. Como os arquivos já foram filtrados no upload, o servidor está "limpo" e não contém os arquivos ignorados.</p>
```

```bash
# Entre neste diretório no seu computador
cd ~/Documents/Sync

# Execute o comando
rsync -avz -e "ssh -p 4422" super-pc:~/Sync/ .
```

```bash
# rsync - Programa de sincronização de arquivos.
# -avz - Flags do comando
# -e "ssh -p 4422" - Define o uso do protocolo SSH na porta 4422
# super-pc:~/Sync/ - Origem dos dados para a pasta Sync no super-pc
# . - Conteúdo do diretório do Sync/ no super
```

````

---

> [!done] _**New**_

---

````ad-quote
title:

##### **02 )** - Comando Alternativo

```ad-quote
title:
<p align="justify">O scp é uma alternativa para cópias rápidas e únicas, mas não deve ser usado para sincronização, pois ele copia tudo, toda vez. Use-o apenas se quiser baixar um único arquivo de resultado rapidamente.</p>
```

```bash
# Upload de um diretório - Não recomendado para sincronização
scp -r -P 4422 ~/Documents/Sync super-pc:~/

# Baixa o arquivo .out para a pasta onde você está
scp -P 4422 super-pc:~/Sync/YourDir/resultados/arq.out .
```

````

---
