---
banner: "![[Pasted image 20251113222119.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Rsync vs. SCP: A Batalha da Cópia

```ad-quote
title:
<p align="justify">Excelente pergunta. Embora ambos usem SSH para transferir arquivos de forma segura, eles operam com filosofias MUITO DIFERENTES.</p>
```

```ad-quote
title:
<p align="justify">Em resumo: o scp é para COPIAR, o rsync é para SINCRONIZAR.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - O SCP (Secure Copy)

```ad-quote
title:
<p align="justify">Pense no scp como um cp (o comando de cópia local) que funciona pela rede. Ele é SIMPLES e DIRETO.</p>
```

```ad-quote
title:
<p align="justify">Quando você usa o scp, ele lê o arquivo de origem e o escreve INTEIRAMENTE no destino. Se o arquivo já existir, ele será SOBRESCRITO por completo.</p>
```

```ad-quote
title:
<p align="justify">A sua grande desvantagem é a eficiência: se você tem um arquivo de 10GB e muda apenas 1KB, o scp vai transferir os 10GB inteiros novamente. É INEFICIENTE para arquivos que mudam pouco.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - O Rsync (Remote Sync)

```ad-quote
title:
<p align="justify">O rsync é uma ferramenta de SINCRONIZAÇÃO INTELIGENTE.</p>
```

```ad-quote
title:
<p align="justify">A sua mágica é o "algoritmo delta" que discutimos. Antes de transferir, ele compara os blocos do arquivo na origem e no destino. Ele então transfere APENAS os blocos que mudaram (os "deltas").</p>
```

```ad-quote
title:
<p align="justify">A sua grande vantagem é a eficiência: se você tem o mesmo arquivo de 10GB e muda 1KB, o rsync transfere APENAS aquele 1KB (mais um pouco de dados de verificação). É EXPONENCIALMENTE MAIS RÁPIDO para backups e atualizações.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Comparativo Direto

```ad-quote
title:

| Característica&nbsp; | SCP (Secure Copy)&nbsp; | Rsync (Remote Sync) |
| :--- | :--- | :--- |
|**Método**|Cópia de arquivo INTEIRO.|Sincronização por "deltas" (diferenças).|
|**Eficiência**|Baixa (para arquivos existentes).|MUITO ALTA (para arquivos existentes).|
|**Uso Principal**|Transferir um arquivo novo ou sobrescrever um antigo.|Manter pastas sincronizadas, backups.|
|**Opções**|MUITO BÁSICAS.|EXTREMAMENTE PODEROSAS (--delete, --exclude, -P, etc.)|
|**Resiliência**|Ruim. Se a conexão cair, a transferência falha.|Excelente. Pode ser resumida (com a opção -P).|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )** - Quando usar cada um?

```ad-quote
title:
<p align="justify">Use o SCP quando... você só quer copiar ALGUNS POUCOS arquivos para um servidor e sabe que eles são novos ou não se importa em sobrescrevê-los. É RÁPIDO e FÁCIL para tarefas simples.</p>
```

```ad-quote
title:
<p align="justify">Use o RSYNC quando... você precisa fazer BACKUPS regulares, manter um espelho de um diretório, ou transferir arquivos MUITO GRANDES que podem sofrer interrupções. Para qualquer tarefa de sincronização, o rsync é a ferramenta SUPERIOR.</p>
```
````

---

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - O que é o Rsync?

```ad-quote
title:
<p align="justify">O rsync é um utilitário de linha de comando usado para sincronizar arquivos e pastas entre duas localizações, que podem estar no MESMO computador ou em computadores DIFERENTES (através de uma rede, geralmente usando SSH).</p>
```

```ad-quote
title:
<p align="justify">A sua GRANDE VANTAGEM é o algoritmo de "transferência delta" (delta-transfer).</p>
```

```ad-quote
title:
<p align="justify">Isso significa que, após a primeira sincronização, o rsync verifica os arquivos na origem e no destino e transfere APENAS as partes dos arquivos que mudaram. Se você tem um arquivo de 10GB e mudou apenas 1MB, ele enviará apenas 1MB, e não os 10GB novamente. Isso o torna INCRIVELMENTE RÁPIDO e eficiente para backups e transferências de grandes volumes de dados.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Por que usar o Rsync?

```ad-quote
title:

| Benefício&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|**Eficiência**|Como mencionado, ele só copia as diferenças, economizando tempo e largura de banda.|
|**Versatilidade**|Funciona para backups locais (ex: de uma pasta para um HD externo) e remotos (ex: do seu notebook para um servidor).|
|**Preservação de Atributos**|Consegue preservar permissões de arquivos, timestamps (datas de modificação), propriedade (dono/grupo) e links simbólicos.|
|**Resiliência**|Se a transferência for interrompida, você pode simplesmente rodar o comando de novo e ele continuará de onde parou (especialmente com a opção -P).|

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Como Funciona (Sintaxe e Opções Comuns)

```ad-quote
title:
<p align="justify">A sintaxe básica é:</p>
```

```bash
rsync [OPÇÕES] <ORIGEM> <DESTINO>
```

```ad-quote
title:
<p align="justify">O comando mais comum que você verá é o rsync -avh. Vamos ver o que isso significa:</p>
```

```ad-quote
title:

| Opção&nbsp; | Nome&nbsp; | Descrição |
| :--- | :--- | :--- |
|**-a**| (archive) | Este é o modo "arquivo" e é ESSENCIAL. Ele é um atalho para um conjunto de outras opções (-rlptg, que significam: recursivo, preservar links, permissões, tempos e grupos). Basicamente, use isso se você quiser que o destino seja uma cópia fiel da origem.|
|**-v**| (verbose) | Mostra no terminal quais arquivos estão sendo copiados. Útil para ver o progresso.|
|**-h**| (human-readable) | Exibe os tamanhos dos arquivos em um formato legível (ex: 10M, 5K) em vez de bytes.|
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Exemplo 1: Sincronização Local

```ad-quote
title:
<p align="justify">Imagine que você quer fazer backup da sua pasta Documentos para um HD externo montado em /media/backup:</p>
```

```bash
rsync -avh /home/usuario/Documentos/ /media/backup/Documentos/
```

```ad-quote
title:
###### **NOTA IMPORTANTE SOBRE A BARRA /**
```

```ad-quote
title:

| Comando&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|rsync -avh /origem/ ... (com barra)|Copia o CONTEÚDO da pasta origem para dentro do destino.|
|rsync -avh /origem ... (sem barra)|Copia a PRÓPRIA PASTA origem para dentro do destino, criando destino/origem.|

```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Exemplo 2: Sincronização Remota (via SSH)

```ad-quote
title:
<p align="justify">Este é o uso mais poderoso. Para enviar sua pasta Projetos para um servidor remoto:</p>
```

```bash
# SINTAXE: rsync [OPÇÕES] <ORIGEM_LOCAL> usuario@servidor:<DESTINO_REMOTA>
rsync -avh /home/usuario/Projetos/ usuario@192.168.1.10:/home/usuario/backups/
```

```ad-quote
title:
<p align="justify">Para baixar (fazer "download") do servidor para sua máquina, basta inverter:</p>
```

```bash
# SINTAXE: rsync [OPÇÕES] usuario@servidor:<ORIGEM_REMOTA> <DESTINO_LOCAL>
rsync -avh usuario@192.168.1.10:/home/usuario/backups/ /home/usuario/Projetos_backup/
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Opções Avançadas Úteis

```ad-quote
title:

| Opção&nbsp; | Descrição&nbsp; |
| :--- | :--- |
|**--delete**|Esta opção faz um "espelho" real. Se um arquivo existe no destino mas NÃO existe mais na origem, ele será APAGADO do destino. Use com CUIDADO!|
|**-n ou --dry-run**|FAZ UMA SIMULAÇÃO. Mostra o que o rsync iria fazer (quais arquivos copiaria ou apagaria) sem realmente fazer nada. ÓTIMO para testar um comando complexo.|
|**-P**|Combina --progress (mostra o progresso de arquivos grandes) e --partial (mantém arquivos parcialmente transferidos se a conexão cair, permitindo resumir depois).|
|**--exclude="PADRAO"**|Permite excluir arquivos ou pastas. Por exemplo, para ignorar a pasta node_modules ou arquivos .log (veja exemplo abaixo).|

```

```ad-quote
title:
###### **Exemplo com --exclude:**
```

```bash
rsync -avh --exclude="node_modules" --exclude="*.log" /home/usuario/Projetos/ usuario@servidor:/backup/
```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">O rsync é uma ferramenta fundamental para qualquer pessoa que gerencia servidores ou precisa de rotinas de backup robustas e rápidas.</p>
```

```ad-quote
title:
<p align="justify">Você gostaria de ver algum exemplo mais específico, como configurar uma rotina de backup ou como usar chaves SSH com o rsync para não precisar digitar a senha?</p>
```
````

---