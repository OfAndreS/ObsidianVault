---
banner: "![[Pasted image 20251113222119.png]]"
---

---

>[!quote] **Link:** [Linux Roadmap](https://roadmap.sh/linux)

---
**00 ) - O Vocabulário do Shell - Comandos Essenciais**

- **Summary:**
    
    - Uma nota de referência rápida para os comandos que você usará em todos os outros tópicos. O foco aqui não é o fluxo de dados (que está no 01), mas a execução atômica: como ler arquivos rapidamente (`cat`, `less`, `head`), gerenciar o histórico de comandos e atalhos de teclado do terminal.

>[!quote] **Vault:** [[Linux - Manipulação de Arquivos e Pastas]]


---
#### **02 )** - A Geografia do Sistema - FHS

```ad-quote
title: **Def**
**Summary:**
- Sem teoria sobre "o que é um arquivo". O foco aqui é decorar o mapa da cidade. Entender onde o Linux guarda os logs (`/var/log`), onde ficam as configurações (`/etc`) e onde você deve (e não deve) salvar seus projetos.
```

> [!quote] **Vault:** [[Linux - Filesystem Hierarchy]]

---

> [!done] _New_

---
#### **03 )** - Manipulação de Fluxos - Pipes & Redirection

```ad-quote
title: **Def**
**Summary:**
- A aplicação prática da E/S. Como pegar a saída de um erro de compilação e salvar num arquivo de texto? Como filtrar logs em tempo real? O domínio dos operadores `|`, `>`, `>>` e `2>`.
```

> [!quote] **Vault:** [[Linux - STDOUT vs STDERR]]

> [!quote] **Vault:** [[Linux - Comandos Com Pipe]]

> [!quote] **Vault:** [[Linux - Filtrando Logs com Grep]]

---

> [!done] _New_

---
#### **04 )** - Permissões na Prática - chmod & chown

```ad-quote
title: **Def**
**Summary:**
- Nada de teoria sobre listas de controle de acesso. Aqui o foco é resolver o erro "Permission Denied". Como tornar um script executável (`+x`), como corrigir dono de arquivos (`chown`) e entender a notação octal (755 vs 644) no dia a dia.
```

> [!quote] **Vault:** [[Prática - Calculando Permissões Octais]]

> [!quote] **Vault:** [[Prática - Tornando Scripts Executáveis (chmod +x)]]

> [!quote] **Vault:** [[Prática - O Grupo Sudoers]]

---

```ad-done
title: 

#### **Fase 2 ) - Ferramentas do Desenvolvedor - O "Tooling"**
```

---
#### **05 )** - Gerenciamento de Pacotes e Bibliotecas

```ad-quote
title: **Def**
**Summary:**
- Como instalar o compilador C, o Python e drivers da Nvidia. Diferença prática entre `apt` (Debian/Zorin) e gerenciadores de linguagem (`pip`, `conda`). Onde as bibliotecas `.so` (Shared Objects) são instaladas.
```

> [!quote] **Vault:** [[Prática - APT update, upgrade e install]]

> [!quote] **Vault:** [[Prática - Compilando do Fonte (Make & Install)]]

> [!quote] **Vault:** [[Prática - Lidando com Dependências Quebradas]]

---

> [!done] _New_

---
#### **06 )** - Variáveis de Ambiente - $PATH

```ad-quote
title: **Def**
**Summary:**
- O motivo número 1 de dores de cabeça em dev. Como fazer o terminal reconhecer onde você instalou o Java ou o CUDA Toolkit. Editando o `.bashrc` ou `.zshrc` para persistir configurações.
```

> [!quote] **Vault:** [[Prática - O que é o $PATH e como editar]]

> [!quote] **Vault:** [[Prática - Criando Alias para produtividade]]

> [!quote] **Vault:** [[Prática - Variáveis de Sessão vs Permanentes]]

---

> [!done] _New_

---
#### **07 )** - Conectividade Remota - SSH & Transferência

```ad-quote
title: **Def**
**Summary:**
- Essencial para o seu uso do NPAD. Gerar chaves SSH (para não digitar senha), configurar o arquivo `~/.ssh/config` (para criar atalhos de conexão) e usar `rsync` para sincronizar pastas de projeto grandes de forma eficiente.
```

> [!quote] **Vault:** [[Prática - Gerando Chaves SSH (ssh-keygen)]]

> [!quote] **Vault:** [[Prática - Configurando Host Alias (~.ssh/config)]]

> [!quote] **Vault:** [[Linux - Sincronizando Pastas com Rsync]]

---

```ad-done
title: 

#### **Fase 3 ) - Controle e Monitoramento - SysAdmin Mode**
```

---
#### **08 )** - Monitoramento de Recursos - Real-time

```ad-quote
title: **Def**
**Summary:**
- A prática do gerenciamento de memória e CPU. Usar `htop` para matar processos travados, `nvidia-smi` para ver se o treino de Deep Learning está usando a GPU, e `df` para checar espaço em disco.
```

> [!quote] **Vault:** [[Prática - Htop e Kill Process]]

> [!quote] **Vault:** [[Prática - Monitorando GPU (nvidia-smi)]]

> [!quote] **Vault:** [[Prática - Espaço em Disco (du & df)]]

---

> [!done] _New_

---
#### **09 )** - Logs e Diagnóstico

```ad-quote
title: **Def**
**Summary:**
- O sistema quebrou, e agora? Como ler os "diários" do sistema (`journalctl`) e logs de kernel (`dmesg`) para descobrir por que um dispositivo USB não foi reconhecido ou por que o sistema reiniciou sozinho.
```

> [!quote] **Vault:** [[Prática - Lendo o Journalctl]]

> [!quote] **Vault:** [[Prática - Logs do Kernel (dmesg)]]

> [!quote] **Vault:** [[Prática - Logs de Aplicação em /var/log]]

---

> [!done] _New_

---

#### **10 )** - Automação Básica - Cron & Scripts

```ad-quote
title: **Def**
**Summary:**
- Como agendar um script para rodar toda madrugada (Cron) e como escrever pequenos scripts em Bash para automatizar a limpeza de arquivos temporários ou backups.
```

> [!quote] **Vault:** [[Prática - Agendamento com Crontab]]

> [!quote] **Vault:** [[Prática - Primeiro Script Bash (.sh)]]

---