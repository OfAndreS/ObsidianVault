
---

````ad-quote
title:

##### **Intro )** - Por que Utilizar Ambientes Virtuais?

```ad-quote
title:
<p align="justify">A principal razão para usar ambientes virtuais é o Gerenciamento de Dependências. Imagine que você está trabalhando em dois projetos diferentes: o "Projeto A" que utiliza a versão 1.0 de uma biblioteca, e o "Projeto B", que necessita da versão 2.0 da mesma biblioteca. Sem um ambiente virtual, você teria um conflito, pois não é possível ter duas versões da mesma biblioteca instaladas globalmente ao mesmo tempo.</p>
<p align="justify">Com ambientes virtuais, cada projeto tem seu próprio espaço isolado com suas próprias dependências, resolvendo o conflito de versões e trazendo outros benefícios importantes:</p>
```
````

````ad-quote
title:

##### **01 )** - Boas Práticas

```ad-quote
title:

**Um ambiente por projeto:** 
- Crie um novo ambiente virtual para cada projeto Python que você iniciar.

**Não versione a pasta do ambiente:** 
- Adicione o nome da pasta do seu ambiente virtual (ex: `venv/`) ao seu arquivo `.gitignore` para evitar que ela seja enviada para o seu repositório de controle de versão.

**Mantenha `requirements.txt` atualizado:** 
- Sempre que adicionar ou remover uma dependência, atualize o seu arquivo `requirements.txt`.
```

```ad-quote
title:
<p align="justify">A adoção do uso de ambientes virtuais é um passo crucial para um desenvolvimento Python mais profissional, organizado e livre de problemas de dependências. Ao seguir este guia, você estará apto a gerenciar seus projetos de forma eficiente e colaborativa.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Criando um Ambiente Virtual com `venv`

```ad-quote
title:
O Python já vem com um módulo integrado para a criação de ambientes virtuais chamado `venv`. Para começar, abra o seu terminal, navegue até a pasta do seu projeto e execute o comando abaixo.
```

```ad-quote
title:

Substitua nome_do_ambiente pelo nome que você deseja dar ao seu ambiente virtual. Uma convenção comum é utilizar venv ou .venv.

**Comando de Criação:**

```

```bash
python -m venv nome_do_ambiente
```

```ad-quote
title:

Este comando criará uma pasta chamada `venv` no diretório do seu projeto. Essa pasta conterá uma cópia do interpretador Python e toda a estrutura necessária para instalar pacotes de forma isolada.

**Exemplo:**

```

```bash
py -3.12 -m venv venv
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Ativando o Ambiente Virtual

```ad-quote
title:
<p align="justify">Após a criação, o ambiente virtual precisa ser "ativado". O comando de ativação varia de acordo com o sistema operacional.</p>

Uma vez ativado, o nome do ambiente virtual aparecerá no início da linha do seu terminal, indicando que você está trabalhando dentro dele. 
- `(venv) C:\caminho\do\projeto>`.

```

```ad-quote
title:
**No Windows / Prompt de Comando - CMD:**
```
```bash

venv\Scripts\activate.bat

```

```ad-quote
title:
**No Windows / PowerShell:**

```

```powershell
# Pode ser necessário primeiro permitir a execução de scripts no PowerShell com o comando: 
# Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
.\venv\Scripts\Activate.ps1
```

```ad-quote
title:
**No macOS e Linux:**
```

```bash

source venv/bin/activate

```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Instalando Pacotes no Ambiente Virtual

```ad-quote
title:
Com o ambiente ativado, você pode instalar as bibliotecas necessárias para o seu projeto usando o `pip`. As instalações ficarão restritas a este ambiente.
```

```ad-quote
title:
**Exemplo de Instalação:**
- Para instalar a biblioteca `requests`:
```

```bash
pip install requests
```

```ad-quote
title:
**Verificando Pacotes Instalados:**
- Para listar os pacotes no ambiente atual:
```
```bash
pip list
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Gerenciando Dependências com `requirements.txt`

```ad-quote
title:
Para facilitar a replicação do seu ambiente em outras máquinas, é uma boa prática listar todas as dependências do projeto em um arquivo chamado `requirements.txt`.
```

```ad-quote
title:
**Gerando o Arquivo de Dependências:**
- Utilize o comando `pip freeze` para salvar os pacotes e suas versões no arquivo:
```

```bash
pip freeze > requirements.txt
```

```ad-quote
title:
**Instalando a Partir do Arquivo:**
- Para instalar todas as dependências listadas no arquivo em um novo ambiente:
```
```bash
pip install -r requirements.txt
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Desinstalando uma Dependência

```ad-quote
title:
<p align="justify">Assim como é possível instalar pacotes, você também pode removê-los facilmente do seu ambiente virtual. Isso é útil para limpar dependências que não são mais necessárias no projeto, mantendo seu arquivo requirements.txt enxuto e relevante.</p>
```

```ad-quote
title:
**Comando para Desinstalar:**
```

```bash
pip uninstall nome_do_pacote
```

```ad-quote
title:
**Exemplo:**

O terminal pedirá uma confirmação (<code>Proceed (y/n)?</code>). Digite <code>y</code> e pressione Enter para confirmar a remoção.
- Para desinstalar a biblioteca `requests`:
```

```bash
pip uninstall requests
```

```ad-quote
title:
**Atualizando o `requirements.txt`:**
<p align="justify">Após desinstalar um pacote, é crucial atualizar seu arquivo `requirements.txt` para refletir essa mudança. Isso garante que outras pessoas que configurem o projeto não instalem pacotes desnecessários. Basta executar o comando `freeze` novamente:</p>
```

```bash
pip freeze > requirements.txt
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Desativando o Ambiente Virtual

```ad-quote
title:
<p align="justify">Quando terminar de trabalhar no seu projeto, você pode desativar o ambiente virtual e retornar ao interpretador Python global do sistema. O nome do ambiente virtual desaparecerá da linha de comando após a execução.</p>

```

```ad-quote
title:
**Comando para Desativar:**
```

```bash
deactivate
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **09 )** - Escrevendo um `requirements.txt` Manualmente

```ad-quote
title:
<p align="justify">Embora gerar o `requirements.txt` com `pip freeze` seja comum e ideal para fixar as versões de um ambiente que funciona, há situações em que você vai querer escrever ou editar este arquivo manualmente. Isso é útil para definir as dependências de um novo projeto, para especificar faixas de versões mais flexíveis em vez de versões exatas, ou para criar um arquivo de dependências "limpo", contendo apenas os pacotes principais, e não as sub-dependências.</p>
```

```ad-quote
title:
**Formato Básico e Especificadores de Versão**
<p align="justify">A sintaxe é simples: um pacote por linha. Para garantir a estabilidade e reprodutibilidade do seu projeto, você pode usar operadores para especificar as versões das dependências.</p>

- `requests==2.31.0` # Instala **exatamente** a versão 2.31.0. Ideal para produção.
- `numpy>=1.20.0` # Instala a versão 1.20.0 ou **qualquer outra mais recente**.
- `pandas<=2.1.0` # Instala a versão 2.1.0 ou **qualquer outra mais antiga**.
- `django~=4.2` # **Versão compatível**. Instala a versão 4.2 ou qualquer outra da série 4.x (ex: 4.3, 4.4), mas **não instalará** a 5.0. É ótimo para aceitar correções de bugs sem quebrar a compatibilidade.
- `scipy!=1.8.0` # Instala qualquer versão, **exceto** a 1.8.0.
- `matplotlib>=3.0.0,<4.0.0` # Instala qualquer versão dentro de um **intervalo específico**.
```

```ad-quote
title:
**Exemplo de um Arquivo `requirements.txt` Manual**
<p align="justify">Um arquivo bem estruturado pode combinar diferentes especificadores para equilibrar flexibilidade e estabilidade. Você também pode adicionar comentários usando `#`.</p>

```text
# ===============================
# Arquivo de Dependências do MeuProjeto
# ===============================

# Framework Web
# Permite atualizações menores, mas não a versão 3.0
Flask~=2.3.0

# Para interagir com APIs
requests>=2.28.0,<3.0.0

# Para manipulação de dados
# Fixamos a versão do pandas para garantir consistência nos resultados
pandas==2.0.3

# Para computação científica, aceitando versões mais recentes
numpy>=1.20.0
```
```
````