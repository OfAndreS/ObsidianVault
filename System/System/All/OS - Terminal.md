---
banner: "![[Pasted image 20251102191152.png]]"
banner-x: 51
banner-y: 23
---
---

````ad-quote
title:

##### **Intro )** - A Comparação: CMD vs. Bash vs. PowerShell

```ad-quote
title:
<p align="justify">Absolutamente. Esta é uma comparação fundamental na computação moderna. Vou detalhar a filosofia, a arquitetura, o poder de scripting e os casos de uso de cada um.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 ) -** Visão Geral

```ad-quote
title:
###### **CMD - Prompt de Comando**
```

```ad-quote
title:
<p align="justify">O martelo antigo. É a ferramenta de linha de comando LEGADA do Windows, mantida estritamente para compatibilidade com sistemas e scripts antigos. É simples e opera com TEXTO.</p>
```

```ad-quote
title:
###### **Bash - Bourne-Again SHell**
```

```ad-quote
title:
<p align="justify">O canivete suíço universal. É o shell PADRÃO do mundo Linux e UNIX. Sua filosofia é encadear pequenas ferramentas que operam com STREAMS DE TEXTO para realizar tarefas complexas.</p>
```

```ad-quote
title:
###### **PowerShell**
```

```ad-quote
title:
<p align="justify">A ferramenta elétrica multifuncional. É o shell MODERNO da Microsoft, focado em automação e gerenciamento. Ele é CROSS-PLATFORM (roda em Windows, Linux e macOS) e opera fundamentalmente com OBJETOS estruturados, não com texto.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 ) -** A Diferença - Texto vs. Objetos

```ad-quote
title:
###### **O Mundo do TEXTO / CMD e Bash**
```

```ad-quote
title:
<p align="justify">No CMD e, de forma muito mais poderosa, no Bash, tudo é um stream de texto. Quando você executa um comando como <code>ls -l</code> (em Bash) ou <code>dir</code> (em CMD), o programa não "sabe" o que é um arquivo, um tamanho ou uma data. Ele simplesmente imprime na tela uma string de texto formatada para leitura humana. Para automação, você precisa usar outras ferramentas (como <code>grep</code>, <code>awk</code>, <code>sed</code> no Bash) para "recortar" e "analisar" (fazer parsing) esse texto.</p>
```
```ad-quote
title:
|Vantagem|
|-|
|<p align="justify">Incrivelmente flexível e universal. QUALQUER programa pode ser encadeado com outro, desde que um "leia texto" e o outro "escreva texto".</p>|

|Desvantagem|
|-|
|<p align="justify">Bastante Frágil. Se um desenvolvedor atualizar o <code>ls</code> para adicionar uma nova coluna, todos os scripts que usavam <code>awk '{print $8}'</code> para pegar o nome do arquivo podem quebrar, pois o nome do arquivo pode ter mudado para a coluna <code>$9</code>. Você está dependendo da formatação visual.</p>|

```

```ad-quote
title:
###### **O Mundo dos OBJETOS / PowerShell**
```

```ad-quote
title:
<p align="justify">O PowerShell foi criado para resolver esse problema de fragilidade, especialmente para gerenciar sistemas complexos como o Windows Server, Active Directory ou Azure. Quando você executa um comando (chamado "Cmdlet") como <code>Get-ChildItem</code> (o equivalente a <code>ls</code> ou <code>dir</code>), ele NÃO retorna texto. Ele retorna uma coleção de objetos .NET. Cada objeto tem propriedades estruturadas:</p>
```

```Bash
$arquivo = Get-ChildItem "meu_arquivo.txt"
$arquivo.Name&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;# Contém: "meu_arquivo.txt"
$arquivo.Length&nbsp; &nbsp; &nbsp; &nbsp;# Contém: 1024 (o tamanho em bytes)
$arquivo.CreationTime # Contém: um objeto de Data/Hora
$arquivo.IsReadOnly&nbsp; &nbsp;# Contém: $true ou $false
```

```ad-quote
title:
<p align="justify">Quando você usa o "pipe" (|) no PowerShell, você não está enviando texto. Você está enviando objetos inteiros para o próximo comando.</p>
```
```ad-quote
title:

|Vantagem|
|-|
|<p align="justify">ROBUSTO. Você acessa dados por nome (<code>.Length</code>), não por posição. O comando <code>Format-Table</code> pode mudar a exibição na tela, mas o objeto subjacente e suas propriedades permanecem os mesmos.</p>|

|Desvantagem|
|-|
|<p align="justify">Mais verboso e requer que os comandos sejam "conscientes" do pipeline de objetos (embora o PowerShell faça um bom trabalho em converter tipos).</p>|
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 ) -** Cenário de Batalha: Encontrar e Parar um Processo

```ad-quote
title:
<p align="justify">Vamos ver como cada shell lida com uma tarefa comum: "Encontrar e parar todos os processos do 'firefox'".</p>
```

```ad-quote
title:
###### **1. CMD (Prompt de Comando)**
```

```ad-quote
title:
<p align="justify">O CMD mal consegue fazer isso de forma automatizada.</p>
```

```Bash
# Encontra o processo e filtra o TEXTO
1. tasklist | findstr "firefox.exe"

# Você teria que LER o PID (Process ID) na tela, por exemplo 1234
# Então, você digitaria manually:
2. taskkill /F /PID 1234

# Automatizar isso em um script .bat é extremamente complexo, envolvendo loops "FOR /F" para analisar o texto.
```

```ad-quote
title:
###### **2. Bash / Shell do Linux**
```

```ad-quote
title:
<p align="justify">O Bash usa sua filosofia de ferramentas de texto encadeadas.</p>
```

```Bash
# Lista todos os processos (um grande bloco de texto)
1. 'ps aux' 

# Filtra esse texto, pegando apenas linhas com a string 'firefox'
2. 'grep 'firefox'' 

# Remove a linha do próprio comando 'grep'
3. 'grep -v 'grep'' 

# Analisa o texto e extrai a segunda coluna (que é o PID)
4. 'awk '{print $2}'' 

# Pega a lista de PIDs e os envia para o comando 'kill'
5. 'xargs kill -9' 

ps aux | grep 'firefox' | grep -v 'grep' | awk '{print $2}' | xargs kill -9
```

```ad-quote
title:
<p align="justify">Observação: Ferramentas mais simples como <code>pkill firefox</code> existem, mas o exemplo acima mostra a filosofia clássica de "encanamento" de texto.</p>
```

```ad-quote
title:
###### **3. PowerShell**
```

```ad-quote
title:
<p align="justify">O PowerShell usa seu pipeline de objetos.</p>
```

```PowerShell
# 1. 'Get-Process -Name "firefox"' -> Pega todos os OBJETOS de processo
#    cuja nome da PROPRIEDADE 'Name' é 'firefox'.
# 2. '|' -> Envia esses OBJETOS para o próximo comando.
# 3. 'Stop-Process' -> Recebe os OBJETOS de processo e os para.
Get-Process -Name "firefox" | Stop-Process
```

```ad-quote
title:
<p align="justify">A diferença é gritante. A versão do PowerShell é legível, robusta e não depende de análise de texto.</p>
```

````


---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 ) -** Tabela de Comparação Detalhada

```ad-quote
title:

| Característica | CMD (Prompt de Comando) | Bash (Shell do Linux) | PowerShell |
| :--- | :--- | :--- | :--- |
| **Origem** | MS-DOS (Década de 80) | UNIX / GNU (Iniciado em 1989) | Microsoft (2006) |
| **Plataforma** | Apenas Windows | Linux, macOS, UNIX (e Windows via WSL) | Cross-Platform (Windows, Linux, macOS) |
| **Paradigma** | Texto Simples (Legado) | Streams de Texto (Filosofia UNIX) | Objetos (.NET) |
| **Unidade de Dados** | String de Texto | Stream de Texto | Objeto ([System.Object]) |
| **O "Pipe" (\|)** | Envia a SAÍDA DE TEXTO crua | Envia um STREAM DE TEXTO (stdout) | Envia OBJETOS inteiros (pipeline) |
| **Scripting** | Arquivos de Lote (.bat) | Shell Script (.sh) | PowerShell Script (.ps1) |
| **Poder da Linguagem** | Muito Fraco. Aritmética básica, loops FOR complexos, sem funções reais. | Poderoso. Excelente para manipulação de arquivos, texto e automação de sistema. | Completo. Uma linguagem de programação orientada a objetos com classes, módulos, APIs .NET, etc. |
| **Sintaxe** | Comandos curtos (dir, del, copy) | Ferramentas (ls, rm, cp, grep, awk) | Cmdlets Verbo-Substantivo (Get-ChildItem, Remove-Item, Copy-Item) |
| **Ecossistema** | APIs do Windows (limitado) | GNU Coreutils, POSIX | Framework .NET, APIs do Windows, Azure, SQL |

```
`````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão ) -** Quando Usar Cada Um

```ad-quote
title:
###### **Use o CMD para...**
```

```ad-quote
title:
<p align="justify">Quase nunca. Seu único uso moderno é para compatibilidade com scripts .bat antigos ou para comandos de rede rápidos que você memorizou (como <code>ipconfig</code>, <code>ping</code>, <code>tracert</code>).</p>
```

```ad-quote
title:
###### **Use o Bash...**
```

```ad-quote
title:
<p align="justify">Seu dia a dia no Linux. É a ferramenta-padrão para navegar, gerenciar arquivos, instalar pacotes e interagir com o sistema.</p>
<p align="justify">Automação de servidores Linux. É a "cola" do ecossistema Linux. Perfeito para scripts que movem arquivos, leem logs, compilam programas e gerenciam serviços.</p>
<p align="justify">WSL no Windows. Para ter o poder do ecossistema de ferramentas GNU (como <code>grep</code>, <code>awk</code>, <code>sed</code>) dentro do Windows.</p>
```

```ad-quote
title:
###### **Use o PowerShell para...**
```

```ad-quote
title:
<p align="justify">Gerenciamento e Automação do Windows. Esta é sua MAIOR força. Gerenciar Active Directory, SQL Server, Exchange, ou o próprio Windows, é 1000x mais fácil com PowerShell.</p>
<p align="justify">Gerenciamento de Nuvem. É a linguagem principal para automação do MICROSOFT AZURE.</p>
<p align="justify">Scripts Cross-Platform. Se você precisa escrever UM script de automação que deve rodar da mesma forma em um servidor Windows e em um servidor Linux.</p>
<p align="justify">Trabalhar com Dados Estruturados. Se sua tarefa envolve analisar um JSON ou CSV, fazer uma chamada de API REST e usar os resultados, o PowerShell é NATIVAMENTE muito superior ao Bash.</p>
```

```ad-quote
title:
###### **Síntese Final**
```

```ad-quote
title:
<p align="justify">Para você, que usa Zorin OS (Bash) e o supercomputador NPAD (Bash), mas inevitavelmente interage com o Windows, entender Bash é essencial para seu trabalho diário, e entender PowerShell é um diferencial profissional GIGANTESCO para automação em ambientes corporativos e de nuvem.</p>
```
````

---