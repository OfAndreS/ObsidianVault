---
banner: "- FILES/Attachments/Pasted image 20260923211852.png"
banner-fade: 100
banner-x: 50
banner-y: 50
---
---

#### **Intro )** - Configuração e Ambiente Base — 01 (Vite, NVM, Package.json, Folders & Tooling)

```ad-quote
title:
<p align="justify">O desenvolvimento em React moderno requer a distinção clara entre dois momentos: a preparação global do sistema operacional (feita apenas uma única vez na máquina) e o fluxo contínuo de criação de projetos isolados com Vite, onde cada aplicação possui suas próprias dependências locais.</p>
```

---

### 📋 Checklist de Estudos - Tópicos a Cobrir

- [x] **01 )** - Isolamento e Instalação do Node.js LTS com Gerenciador de Versões (NVM)
- [x] **02 )** - Inicialização de Projeto React com Bundler Moderno (Vite: `npm create vite@latest`)
- [x] **03 )** - Scripts de Execução e Ciclo de Vida do Projeto (`dev`, `build`, `preview`)
- [x] **04 )** - Integração Completa de Utilitários de Estilização (Tailwind CSS v4 com Vite)
- [x] **05 )** - Configuração de Biblioteca de Ícones Vetoriais (`lucide-react`)
- [x] **06 )** - Anatomia Detalhada da Árvore de Diretórios e Arquivos do Vite
- [ ] **07 )** - Padronização e Qualidade de Código com Linter e Formatação (ESLint + Prettier)
- [ ] **08 )** - Gerenciamento de Variáveis de Ambiente no Vite (`.env`, prefixo `VITE_` e `import.meta.env`)
- [ ] **09 )** - Configuração das Ferramentas de Inspeção do Navegador (React Developer Tools)

---

```ad-done
title:
#### **Fase 1 ) - Setup Global da Máquina (Executado Apenas 1 Vez)**
```

---

````ad-quote
title:

##### **01 )** - Descrição

```ad-quote
title:
<p align="justify">Estes passos preparam o sistema operacional para executar código JavaScript fora do navegador. Você só precisa executar esses comandos na primeira vez em que estiver configurando o computador ou ao formatar o sistema. Uma vez instalados, o Node.js e o NPM ficam disponíveis globalmente no terminal.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Instalação e Carga do NVM (Node Version Manager)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Instalando o NVM via Terminal*
```

```ad-quote
title:
<p align="justify">O NVM gerencia versões do Node sem gerar conflitos de permissões com o usuário root do sistema operacional.</p>
```

```bash
# Baixa e executa o script de instalação oficial do NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Carregando o NVM no Shell Atual*
```

```ad-quote
title:
<p align="justify">Registra as variáveis e funções do NVM na sessão ativa do terminal.</p>
```

```bash
# Carrega as configurações do NVM no ambiente atual
\. "$HOME/.nvm/nvm.sh"
```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _Instalação do Node.js LTS e Verificação do NPM_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Instalando a versão estável mais recente*
```

```ad-quote
title:
<p align="justify">Instala a versão com suporte a longo prazo (LTS - Long Term Support) e valida a disponibilidade do gerenciador de pacotes NPM.</p>
```

```bash
# Instala e ativa a versão estável recomendada
nvm install --lts

# Valida se o NPM está instalado e exibe a versão atual
npm -v
```

````

---

```ad-done
title:
#### **Fase 2 ) - Fluxo Contínuo: Novo Projeto em Máquina Já Configurada**
```

---

````ad-quote
title:

##### **02 )** - Descrição

```ad-quote
title:
<p align="justify">Como a sua máquina já possui Node e NPM instalados, este é o fluxo que você repetirá SEMPRE que for iniciar uma nova aplicação ou exercício de React. Ele gera uma pasta isolada com o bundler Vite e baixa os pacotes locais necessários.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Comandos Obrigatórios_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Sequência Obrigatória Passo a Passo*
```

```bash
01 ) 
# Cria o template React em uma nova pasta chamada nome_do_projeto
npm create vite@latest nome_do_projeto -- --template react

02 ) 
# Entra na pasta do projeto onde está localizado o package.json
cd nome_do_projeto

03 ) 
# Baixa as dependências declaradas e cria a pasta local node_modules
npm install

04 ) 
# Sobe o servidor local de desenvolvimento (Hot Module Replacement ativo)
npm run dev
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Atalho de Execução em Linha Única*
```

```bash

npm create vite@latest nome_do_projeto -- --template react && cd nome_do_projeto && npm install && npm run dev

```

````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Scripts de Ciclo de Vida do Package.json_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Comandos de Execução e Compilação*
```

```ad-quote
title:
<p align="justify">Comandos nativos configurados dentro do arquivo package.json para desenvolvimento, verificação e deploy da aplicação.</p>
```

```bash
# Executa a aplicação em modo de desenvolvimento local no navegador
npm run dev

# Compila, minifica e otimiza a aplicação para a pasta dist/ (produção)
npm run build

# Executa localmente o bundle final gerado na pasta dist/ para validação
npm run preview
```

````

---

```ad-done
title:
#### **Fase 3 ) - Bibliotecas Complementares (Instalação por Projeto)**
```

---

````ad-quote
title:

##### **03 )** - Descrição

```ad-quote
title:
<p align="justify">Bibliotecas de interface e ícones são instaladas de forma local dentro da pasta de cada projeto. Se você quiser utilizá-las em um novo projeto, é necessário rodar o comando de instalação e registrar as configurações dentro da pasta correspondente.</p>
```
````

> [!quote] **Link:** [Tailwind CSS with Vite Documentation](https://tailwindcss.com/docs/installation/using-vite)

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Tailwind CSS com Vite_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Instalação do Pacote Principal e Plugin do Vite*
```

```ad-quote
title:
<p align="justify">Adiciona o framework utilitário de CSS e o plugin oficial de integração e build otimizado para o Vite.</p>
```

```bash
# Executar dentro da pasta do projeto
npm install tailwindcss @tailwindcss/vite
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Registro do Plugin no vite.config.js*
```

```ad-quote
title:
<p align="justify">Importe o Tailwind e adicione <code>tailwindcss()</code> na lista de plugins do arquivo central de configuração do Vite.</p>
```

```javascript
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";
import tailwindcss from "@tailwindcss/vite";

export default defineConfig({
  plugins: [tailwindcss(), react()],
});
```

````

````ad-quote
title:

```ad-quote
title:
###### C ) *Importação do Tailwind no CSS Principal (src/index.css)*
```

```ad-quote
title:
<p align="justify">No seu arquivo CSS global (normalmente <code>src/index.css</code>), adicione a diretiva oficial do Tailwind na primeira linha do documento.</p>
```

```css
@import "tailwindcss";
```

````

````ad-quote
title:

```ad-quote
title:
###### D ) *Verificação da Importação no Ponto de Entrada (src/main.jsx)*
```

```ad-quote
title:
<p align="justify">No arquivo <code>src/main.jsx</code>, certifique-se de que existe o import do arquivo CSS global para que os estilos sejam aplicados a toda a árvore de componentes.</p>
```

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App.jsx';
import './index.css';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
);
```

````

> [!done] **_New_**

```ad-quote
title:

##### 3.2 ) - _Biblioteca de Ícones (Lucide React)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Instalação do Lucide React*
```

```ad-quote
title:
<p align="justify">Fornece centenas de ícones vetoriais modernos importáveis como componentes React. <b>Nota:</b> O Lucide não é obrigatório para aprender React básico; instale apenas quando for desenhar interfaces visuais com ícones.</p>
```

```bash
# Executar dentro da pasta do projeto onde deseja usar ícones
npm install lucide-react
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Instalação Conjunta Opcional (Tailwind + Lucide)*
```

```ad-quote
title:
<p align="justify">Caso queira inicializar um novo projeto já com Tailwind e Lucide de uma só vez:</p>
```

```bash
npm install tailwindcss @tailwindcss/vite lucide-react
```

````

---

```ad-done
title:
#### **Fase 4 ) - Arquitetura de Arquivos e Diretórios**
```

---

````ad-quote
title:

##### **04 )** - Descrição

```ad-quote
title:
<p align="justify">Compreender a estrutura de arquivos gerada pelo Vite é fundamental para organizar adequadamente componentes, assets e configurações da aplicação React.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.1 ) - _Estrutura de Diretórios_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Árvore do Projeto*
```

```text
nome_do_projeto/
├── node_modules/           # Pacotes baixados localmente
├── public/                 # Arquivos estáticos na raiz
│   └── vite.svg
├── src/                    # Código-fonte da aplicação React
│   ├── assets/             # Imagens e mídias
│   │   └── react.svg
│   ├── App.css             # Estilos do componente principal App
│   ├── App.jsx             # Componente raiz da interface
│   ├── index.css           # Estilos globais da aplicação
│   └── main.jsx            # Ponto de entrada: monta o App no DOM
├── .gitignore              # Lista de arquivos e pastas ignorados pelo Git
├── index.html              # Documento HTML principal (<div id="root">)
├── package-lock.json       # Versões resolvidas das dependências
├── package.json            # Dependências e metadados
└── vite.config.js          # Arquivo de configuração e plugins do Vite
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Descrição Detalhada dos Arquivos Principais*
```

```bash
01 ) package.json
# Lista todas as dependências instaladas no projeto, scripts de execução (dev, build) e metadados da aplicação.

02 ) package-lock.json
# Grava a versão exata de cada dependência e subdependência instalada para garantir reproducibilidade em outras máquinas.

03 ) node_modules/
# Pasta gerada pelo comando npm install onde residem todos os códigos compilados das bibliotecas. Nunca deve ser versionada no Git.

04 ) index.html
# Página HTML raiz servida pelo servidor web. Contém o elemento <div id="root"></div> onde todo o React é montado via JavaScript.

05 ) src/main.jsx
# Ponto de entrada JavaScript. Usa createRoot para capturar o elemento "root" do index.html e injetar o componente <App />.

06 ) src/App.jsx
# Componente funcional principal da aplicação. É a partir dele que os demais componentes e telas são compostos.

07 ) vite.config.js
# Arquivo central de configuração do Vite onde são declarados plugins (como o suporte oficial ao React e Tailwind).
```

````

---