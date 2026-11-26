---
banner: "- FILES/Attachments/Pasted image 20260923211852.png"
banner-fade: 100
banner-x: 50
banner-y: 50
---

---

#### **Intro )** - Navegação SPA e Estado Global no React — 05 (Router, SPA, Layouts, Context API & Zustand)

Aplicações modernas no formato Single Page Application (SPA) dependem de roteamento dinâmico no lado do cliente sem recarregar a página e de um mecanismo centralizado para compartilhar dados entre múltiplos componentes sem a complexidade do Prop Drilling. Esta nota cobre desde a biblioteca de rotas padrão do ecossistema até soluções nativas e externas de estado global.

---

### 📋 Checklist de Estudos - Tópicos a Cobrir

- [ ] **01 )** - Conceito de Single Page Application (SPA), Client-Side Routing e History API do Navegador
- [ ] **02 )** - Configuração e Estruturação do `react-router-dom` (`createBrowserRouter` e `RouterProvider` / `<BrowserRouter>`)
- [ ] **03 )** - Definição de Rotas Básicas com `<Routes>` e `<Route>`
- [ ] **04 )** - Navegação Declarativa com `<Link>` e `<NavLink>` (estilos e classes de rota ativa)
- [ ] **05 )** - Navegação Programática com o Hook `useNavigate`
- [ ] **06 )** - Rotas Dinâmicas e Extração de Parâmetros de URL com o Hook `useParams`
- [ ] **07 )** - Parâmetros de Busca (Query Strings) com o Hook `useSearchParams`
- [ ] **08 )** - Rotas Aninhadas (Nested Routes) e Layouts Compartilhados com `<Outlet />`
- [ ] **09 )** - Tratamento de Erros de Rota e Página 404 Not Found (`path="*"`)
- [ ] **10 )** - Proteção de Rotas Autenticadas (Padrão Protected Routes / Private Routes)
- [ ] **11 )** - O Problema do "Prop Drilling" e a Necessidade de Estado Global
- [ ] **12 )** - Estado Global Nativo com Context API (`createContext`, `Provider` e `useContext`)
- [ ] **13 )** - Padrão de Provedor Customizado (Custom Provider Component + Custom Hook de consumo)
- [ ] **14 )** - Introdução a Gerenciadores de Estado Modernos Externos (Zustand: Stores atômicas e seletores)

---

#### **Fase 1 ) - Roteamento com React Router**

---

##### **01 )** - Descrição

Instalação e configuração de rotas declarativas para estruturar a navegação de uma SPA sem recarregamentos de página.

##### 1.1 ) - _Configuração Inicial de Rotas_

###### A ) *Definição do Roteador e Rotas Principais*

```jsx
// Exemplo de configuração de BrowserRouter ou createBrowserRouter
```

###### B ) *Navegação com Link e NavLink*

```jsx
// Exemplo de navegação entre rotas
```

---

#### **Fase 2 ) - Parâmetros e Rotas Aninhadas**

---

##### **02 )** - Descrição

Captura de IDs dinâmicos na URL e reaproveitamento de cascas de interface (Headers, Sidebars) via layouts aninhados.

##### 2.1 ) - _Uso de useParams e Outlet_

###### A ) *Captura de Parâmetros de URL (useParams)*

```jsx
// Exemplo de rota dinâmica /produtos/:id
```

###### B ) *Layout compartilhado com Outlet*

```jsx
// Exemplo de componente Layout com <Outlet />
```

---

#### **Fase 3 ) - Estado Global com Context API e Zustand**

---

##### **03 )** - Descrição

Evitar a passagem excessiva de props (prop drilling) compartilhando estados entre componentes de qualquer nível da árvore.

##### 3.1 ) - _Context API Nativa_

###### A ) *Criação de Contexto e Provedor Customizado*

```jsx
// Exemplo de Custom Provider com useContext
```

##### 3.2 ) - _Zustand (Gerenciamento Moderno e Simplificado)_

###### A ) *Criação de Store com Zustand*

```jsx
// Exemplo de store Zustand
```

---
