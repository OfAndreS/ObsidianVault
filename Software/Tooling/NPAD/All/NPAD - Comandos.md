---
banner: "![[Pasted image 20251115123940.png]]"
---

---

````ad-quote
title:

##### **Principais Comandos para o Dia a Dia no Supercomputador NPAD**

```ad-quote
title:
<p align="justify">Esta é uma lista dos principais comandos que você usará no seu dia a dia no supercomputador NPAD, organizados por categoria. Pense nisto como uma "folha de cola" (cheatsheet) para começar.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Navegação e Gerenciamento de Arquivos

```ad-quote
title:
<p align="justify">Estes são os comandos fundamentais para se mover pelo sistema e manipular seus arquivos e pastas.</p>
```

```ad-quote
title:

| Comando | Descrição | Exemplo de Uso |
|---|---|---|
| `ls -lh` | Lista o conteúdo do diretório de forma detalhada e legível. | `ls -lh` |
| `cd` | **C**hange **D**irectory. Muda para outro diretório. | `cd "NN FromScratch"` |
| `cd ..` | Volta um diretório acima. | `cd ..` |
| `cd ~` | Volta para o seu diretório home, não importa onde você esteja. | `cd ~` |
| `pwd` | **P**rint **W**orking **D**irectory. Mostra o caminho completo do seu local atual. | `pwd` |
| `mkdir` | **M**a**k**e **Dir**ectory. Cria um novo diretório. | `mkdir meus_resultados` |
| `cp` | **C**o**p**y. Copia um arquivo ou diretório. | `cp arquivo.txt copia.txt` |
| `mv` | **M**o**v**e. Move ou renomeia um arquivo/diretório. | `mv antigo.txt novo.txt` |
| `rm` | **R**e**m**ove. Apaga um arquivo. (Cuidado: não tem lixeira!). | `rm arquivo_inutil.txt` |
| `rm -r` | Apaga um diretório e tudo que está dentro dele (Use com muito cuidado). | `rm -r pasta_inutil` |
| `rm -rI` | Apaga um diretório com uma mensagem de confimação. |`rm -rI pasta_inutil` |
| `rm -rf` | Apaga um diretório com arquivos protegidos. |`rm -rf pasta_inutil` |
| `cat` | Mostra o conteúdo completo de um arquivo no terminal. | `cat resultado_job.out` |
| `less` | Mostra o conteúdo de um arquivo grande, página por página (use `q` para sair). | `less arquivo_grande.log` |
| `nano` | Abre um editor de texto simples para criar ou modificar arquivos. | `nano meu_script.sh` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Gerenciamento de Jobs Slurm - [[NPAD - Slurm|{X}]]

```ad-quote
title:
<p align="justify">Comandos específicos para interagir com o sistema de filas do NPAD.</p>
```

```ad-quote
title:

| Comando | Descrição | Exemplo de Uso |
|---|---|---|
| `sbatch` | **S**ubmit **Batch** job. Envia seu script para a fila de execução. | `sbatch executar.sh` |
| `squeue -u $USER`| Mostra seus jobs que estão na fila (PD - pendente) ou rodando (R). | `squeue -u asgmoreira` |
| `scancel` | **Cancel**a um job que está na fila ou em execução. | `scancel 1530578` |
| `sinfo` | Mostra **Info**rmações sobre as partições (filas) e o estado dos nós. | `sinfo` |

```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Ambiente e Módulos - Lmod

```ad-quote
title:
<p align="justify">Para gerenciar o software disponível no ambiente.</p>
```

```ad-quote
title:

| Comando | Descrição | Exemplo de Uso |
|---|---|---|
| `module avail` | Mostra os **módulos** (softwares) **disponíveis**. | `module avail python` |
| `module load` | **Carrega** um módulo, tornando o software disponível para uso. | `module load softwares/python/3.10.5-gnu8` |
| `module list` | **Lista** os módulos que estão carregados na sua sessão atual. | `module list` |
| `module unload`| **Descarrega** um módulo que não é mais necessário. | `module unload softwares/python/3.10.5-gnu8` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - NPAD - Sincronização de Arquivos - [[NPAD - Sincronização de Arquivos|{X}]]

```ad-quote
title:
<p align="justify">Comandos para entrar/sair do cluster e mover dados.</p>
```

```ad-quote
title:

| Comando | Descrição | Exemplo de Uso |
|---|---|---|
| `ssh` | **S**ecure **Sh**ell. Conecta-se a um servidor remoto. | `ssh super-pc` |
| `scp` | **S**ecure **C**o**p**y. Copia arquivos entre seu PC e o servidor. | `scp meu_arquivo.txt super-pc:~/` |
| `exit` | Encerra sua sessão SSH. | `exit` |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Comando man

```ad-quote
title:
<p align="justify">Se você tiver dúvida sobre qualquer comando, use o <code>man</code> (de <b>man</b>ual). Ele mostra a documentação completa, explicando todas as opções disponíveis.</p>
```

```bash
# Exemplo: Para aprender todas as opções do comando ls
man ls
```
```ad-quote

<p align="justify">Pressione a tecla <code>q</code> para sair da página do manual.</p>
```

````

---