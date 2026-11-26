---
banner: "- FILES/Attachments/Pasted image 20260923211852.png"
banner-fade: 100
banner-x: 50
banner-y: 50
---
---

#### **Intro )** - JSX - Props - Components

Uma aplicação React concatena vários componentes que são funções JavaScript visando dividir uma interface complexa em múltiplas partes reutilizáveis e desenvolvidas de forma paralela.

---

### 📋 Checklist de Estudos - Tópicos a Cobrir

- [x] **01 )** - Fluxo de Renderização e Ponto de Entrada (`index.html`, `main.jsx`, `App.jsx`)
- [x] **02 )** - Criação, Modularização e Composição de Componentes Funcionais
- [ ] **03 )** - Fundamentos e Regras da Sintaxe JSX (Expressões `{ }`, Tag Raiz e Atributos em CamelCase)
- [ ] **04 )** - Fragmentos do React (`<React.Fragment>` e `<>...</>`)
- [x] **05 )** - Passagem e Recebimento de Props Básicas (Argumentos Dinâmicos Pai -> Filho)
- [ ] **06 )** - Desestruturação de Props e Valores Padrão (Default Props / Default Parameters)
- [ ] **07 )** - A Propriedade Especial `children` e Padrão de Composição (Slots e Wrappers)
- [ ] **08 )** - Renderização Condicional (Ternário `? :`, Curto-Circuito `&&` e `if/else`)
- [ ] **09 )** - Renderização de Coleções e Listas com `.map()`
- [ ] **10 )** - A Importância da Prop `key` na Reconciliação (Identidade Estável de Elementos)
- [ ] **11 )** - Manipulação de Eventos no JSX (`onClick`, `onChange`, Synthetic Events e Funções Anônimas)

---

#### **Fase 1 ) - Fluxo de Renderização e Componentes**

---

##### **01 )** - Descrição

O arquivo index.html inicia os arquivos na pasta src, utilizando JavaScript para renderizar os componentes na tela. O arquivo main.jsx é responsável por definir o ponto de entrada e quais componentes do arquivo App.jsx serão renderizados inicialmente.

##### 1.1 ) - _Componente Base_

###### A ) *Estrutura do Componente Principal (App.jsx)*

```jsx
import * as React from 'react';

function App() {
  return (
    <div>
      <h1>"Welcome!!!"</h1>
    </div>
  );
}

export default App;
```

---

#### **Fase 2 ) - Criação e Composição de Componentes**

---

##### **02 )** - Descrição

Para manter o código modular e organizado, criamos componentes em arquivos separados dentro da pasta src/components/ e os importamos nos componentes que precisam exibi-los.

##### 2.1 ) - _Novo Componente_

###### A ) *Criação do arquivo do componente*

```bash
# Criação do arquivo do componente na pasta de componentes
touch src/components/NomeDoComponente.jsx
```

###### B ) *Código do componente (NomeDoComponente.jsx)*

```jsx
function NomeDoComponente() {
  return (
    <div>
      <h1>Mensagem.</h1>
    </div>
  );
}

export default NomeDoComponente;
```

###### C ) *Importação e renderização no App.jsx*

```jsx
import * as React from 'react';
import NomeDoComponente from "./components/NomeDoComponente";

function App() {
  return (
    <div>
      <h1>"Welcome!!!"</h1>
      {/* Tudo no arquivo NomeDoComponente.jsx será renderizado aqui */}
      <NomeDoComponente />
    </div>
  );
}

export default App;
```

---

#### **Fase 3 ) - Passagem de Dados (Props)**

---

##### **03 )** - Descrição

As props no React funcionam exatamente como argumentos que você passa para uma função. O componente pai envia uma informação e o componente filho recebe essa informação dentro de um objeto para usá-la na tela dinamicamente entre chaves.

##### 3.1 ) - _Envio e Recebimento de Props_

###### A ) *Enviando dados pelo Componente Pai (App.jsx)*

```jsx
import * as React from 'react';
import NomeDoComponente from "./components/NomeDoComponente";

function App() {
  return (
    <div>
      <h1>"Welcome!!!"</h1>
      {/* Aqui enviamos a informação mensagem como uma prop */}
      <NomeDoComponente mensagem="Esta é uma mensagem vinda do componente pai!" />
    </div>
  );
}

export default App;
```

###### B ) *Recebendo dados no Componente Filho (NomeDoComponente.jsx)*

O componente App define a propriedade chamada mensagem com um texto personalizado. O componente NomeDoComponente recebe esse dado no parâmetro props e o exibe dinamicamente entre chaves acessando props.mensagem.

```jsx
// O componente filho recebe as props como parâmetro
function NomeDoComponente(props) {
  return (
    <div>
      {/* Acessamos o valor enviado pelo pai usando props.nomeDaPropriedade */}
      <h1>{props.mensagem}</h1>
    </div>
  );
}

export default NomeDoComponente;
```

---
