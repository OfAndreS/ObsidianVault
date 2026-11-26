
---

````ad-quote
title:

##### **Intro )** - Guia de Instalação do Conda no Linux

```ad-quote
title:
<p align="justify">Instalar o Conda em um sistema operacional Linux é um processo direto que envolve o download de um script de instalação e sua execução no terminal. O Conda é um gerenciador de pacotes e ambientes de código aberto que simplifica a instalação e o gerenciamento de softwares e bibliotecas, especialmente para ciência de dados.</p>
```

```ad-quote
title:
<p align="justify">O método de instalação é o mesmo para ambas as distribuições. Para a maioria dos usuários, o Miniconda é recomendado por ser mais leve e flexível.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Anaconda vs Miniconda

```ad-quote
title:
<p align="justify">Existem duas versões principais do instalador:</p>
```

```ad-quote
title:

| Distribuição | Descrição | Uso Recomendado |
| --- | --- | --- |
| Anaconda | Uma distribuição completa com Conda e mais de 150 pacotes pré-instalados | Iniciantes e quem busca uma configuração completa de imediato |
| Miniconda | Uma instalação mínima com apenas o Conda e suas dependências | Usuários que preferem instalar pacotes conforme a necessidade |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Passo a Passo da Instalação

```ad-quote
title:
**1. Baixe o Script de Instalação:**
```

```ad-quote
title:
<p align="justify">Abra o seu terminal e use o comando wget para baixar a versão mais recente do instalador do Miniconda. Para uma arquitetura de 64 bits (a mais comum), o comando é:</p>
```

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

```ad-quote
title:
**2. Execute o Script de Instalação:**
```

```ad-quote
title:
<p align="justify">Após o download ser concluído, execute o script baixado usando o bash:</p>
```

```bash
bash Miniconda3-latest-Linux-x86_64.sh
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Configuração Inicial

```ad-quote
title:
**3. Siga as Instruções na Tela:**
```

```ad-quote
title:
<p align="justify">O instalador irá guiá-lo através do processo:</p>
```

```ad-quote
title:
- Pressione Enter para revisar o contrato de licença.
- Digite yes e pressione Enter para aceitar os termos da licença.
- Pressione Enter para confirmar o local de instalação padrão.
- Digite yes e pressione Enter para inicializar o Miniconda3.
```

```ad-quote
title:
**4. Reinicie o Terminal:**
```

```ad-quote
title:
<p align="justify">Feche e reabra o seu terminal para que as alterações no PATH entrem em vigor.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Verificação da Instalação

```ad-quote
title:
**5. Verifique a Instalação:**
```

```ad-quote
title:
<p align="justify">Para confirmar que o Conda foi instalado com sucesso, execute o seguinte comando para ver a versão:</p>
```

```bash
conda --version
```

```ad-quote
title:
<p align="justify">Você também pode listar os pacotes instalados no ambiente base com:</p>
```

```bash
conda list
```

```ad-quote
title:
<p align="justify">Com esses passos, o Conda estará instalado e pronto para ser usado no seu sistema Linux. Você pode agora começar a criar ambientes virtuais e instalar os pacotes necessários para os seus projetos.</p>
```
````

---