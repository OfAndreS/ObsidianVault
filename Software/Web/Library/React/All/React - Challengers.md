---
banner: Pasted image 20260712203132.png
banner-x: 50
banner-y: 35
banner-fade: 100
---
---

>[!quote] **Link:** [React Official Documentation](https://react.dev/)

---

```ad-done
title:
#### **Fase 1 ) - Profile Card ⭐**
```

---

````ad-quote
title:

##### **01 )** - Profile Card Interativo (Nível 1 - Básico)

```ad-quote
title:
<p align="justify">Construção de um cartão de apresentação pessoal e agregador de links com interface responsiva (estilo Linktree). O objetivo principal é fixar a mentalidade declarativa, a composição de componentes puros e o fluxo unidirecional de dados através de props.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">A aplicação exibe um cartão centralizado contendo imagem de avatar, nome, bio resumida, badges de competências técnicas, links externos com ícones e um botão de alternância de status de disponibilidade para trabalho.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) JSX & Sintaxe Declarativa
# Uso correto de tags auto-fecháveis, className e expressões JavaScript entre chaves {}. Emprego de Fragments (<> e </>) para não poluir o DOM com nós desnecessários.


02 ) Composição & Componentes Puros
# Criação de componentes funcionais isolados com responsabilidade única: ProfileCard, Avatar, UserInfo, SkillBadgeList, SkillBadge e LinkItem.


03 ) Props & Desestruturação
# Passagem de parâmetros tipados via props do componente pai para os filhos e utilização da prop especial children para compor wrappers reutilizáveis (CardContainer).


04 ) Renderização de Listas & Keys
# Iteração sobre arrays de objetos (skills e links) através do método .map() com chaves únicas e imutáveis (key={item.id}) no elemento raiz da iteração.


05 ) Renderização Condicional
# Renderização de badges com operador ternário (status "Disponível para Projetos" vs "Ocupado") e exibição condicional com operador lógico && (badge "Verificado").


06 ) Estilização Utilitária
# Uso de Tailwind CSS com layout Flexbox/Grid responsivo e estados interativos (hover:scale, transition).
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Componentes*
```

```bash
App
 └── CardContainer (wrapper com children)
      ├── Avatar (imagem, alt, statusIndicator)
      ├── UserInfo (nome, role, bio)
      ├── SkillList
      │    └── SkillBadge (renderizado via .map())
      └── LinkGroup
           └── LinkItem (título, url, ícone)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Nenhum erro de chave duplicada ou ausente no console (key warning).
# [x] Todos os links e dados devem vir de um array mock de dados separado.
# [x] A interface deve ser completamente responsiva (mobile-first com Tailwind CSS).


# Desafio Bônus:
# Adicionar um botão de toggle de tema local (Modo Escuro / Claro) alternando classes utilitárias no componente raiz.
```
````

---

```ad-done
title:
#### **Fase 2 ) - Task Tracker ⭐⭐**
```

---

````ad-quote
title:

##### **02 )** - Task Tracker / To-Do Interativo (Nível 2 - Básico-Intermediário)

```ad-quote
title:
<p align="justify">Gerenciador de tarefas diárias com criação, alternância de conclusão, exclusão e filtros de visualização. O foco é dominar o ciclo de reatividade básica do React, mutações imutáveis e formulários controlados.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O usuário pode inserir uma nova tarefa via campo de texto, marcar itens como concluídos via checkbox, remover tarefas da listagem e filtrar por "Todas", "Pendentes" e "Concluídas", além de visualizar um contador dinâmico de tarefas pendentes.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Estado Local com useState
# Armazenamento da lista de tarefas em um array de objetos: tasks = [{ id, title, completed, createdAt }].


02 ) Formulários Controlados (Controlled Inputs)
# Input com propriedade value atrelada a uma variável de estado. Atualização em tempo real com onChange e interceptação de onSubmit com e.preventDefault().


03 ) Imutabilidade do Estado no React
# Inserção com [...prev, newTask], remoção com filter() e toggle com map(). NUNCA utilizar métodos destrutivos como push() ou splice().


04 ) Levantamento de Estado (Lifting State Up)
# O estado reside no componente pai comum (TodoApp) e funções de callback (onToggle, onDelete, onAdd) são propagadas para os filhos via props.


05 ) Estados Derivados (Derived State)
# O filtro ativo ("all" | "pending" | "done") é mantido em estado. A lista visível NÃO deve ser duplicada em outro estado, sendo computada diretamente no corpo do componente pai.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Componentes*
```

```bash
TodoApp (mantém tasks e filter)
 ├── TodoHeader (título e contador de tarefas restantes)
 ├── TodoForm (input controlado e botão de submissão)
 ├── TodoFilterBar (botões Todas, Pendentes, Concluídas)
 └── TodoList
      ├── TodoItem (checkbox, texto com strike-through, botão delete)
      └── TodoEmptyState (renderizado se não houver tarefas no filtro)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Não permitir a adição de tarefas com títulos vazios ou apenas espaços em branco.
# [x] Garantir que o input seja limpo automaticamente após a submissão.
# [x] Manter contadores de itens restantes atualizados sem estados redundantes.


# Desafio Bônus:
# Persistir a lista de tarefas no localStorage do navegador para não perder dados ao recarregar a tela.
```
````

---

```ad-done
title:
#### **Fase 3 ) - Pomodoro Timer ⭐⭐⭐**
```

---

````ad-quote
title:

##### **03 )** - Pomodoro Timer com Áudio (Nível 3 - Intermediário)

```ad-quote
title:
<p align="justify">Cronômetro baseado no método Pomodoro para gestão de tempo de foco. Exige o entendimento rigoroso da execução de efeitos colaterais assíncronos, limpeza de memória para evitar memory leaks e manipulação de referências que não disparam renderização.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O sistema alterna entre três modos: Foco (25 min), Pausa Curta (5 min) e Pausa Longa (15 min). Permite iniciar, pausar e resetar a contagem regressiva, atualiza o título do navegador dinamicamente com os minutos restantes e emite um alerta sonoro ao término do ciclo.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Efeitos Colaterais com useEffect
# Gerenciamento do cronômetro regressivo com setInterval dentro do useEffect. Array de dependências estritamente configurado com as variáveis de ativação [isRunning, timeLeft].


02 ) Função de Limpeza (Cleanup Function)
# Retorno obrigatório de clearInterval() dentro do callback de useEffect para exterminar timers ativos e evitar múltiplos intervalos concorrentes.


03 ) Manipulação de Referências com useRef
# Armazenamento do ID do intervalo no useRef sem causar re-render. Uso de useRef para referenciar a instância de um elemento HTMLAudioElement para tocar o alerta.


04 ) Sincronização com o DOM Externo
# Atualização contínua do document.title no useEffect (ex: "(18:42) Pomodoro - Foco!").


05 ) Atualização Funcional (Functional Updates)
# Uso de setTimeLeft(prev => prev - 1) para evitar referências defasadas (stale closures) dentro do callback do timer.


06 ) Máquina de Estados Simples
# Controle de modos de sessão ('WORK' | 'SHORT_BREAK' | 'LONG_BREAK') e status ('IDLE' | 'RUNNING' | 'PAUSED').
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Componentes*
```

```bash
PomodoroApp (mantém mode, timeLeft, isRunning)
 ├── ModeSelector (tabs: Trabalho / Pausa Curta / Pausa Longa)
 ├── TimerDisplay (formatação mm:ss com zeros à esquerda e barra SVG)
 ├── TimerControls (botões Iniciar, Pausar, Resetar, Avançar)
 └── SoundNotification (elemento de áudio acionado via ref)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] O timer não pode acelerar quando o usuário clica múltiplas vezes seguidas em "Iniciar".
# [x] Ao trocar de aba ou alternar de modo, a contagem deve pausar/resetar sem vazar memória.
# [x] Formatação de minutos e segundos padronizada com dois dígitos (ex: 05:09).


# Desafio Bônus:
# Adicionar um anel de progresso circular SVG que diminui dinamicamente conforme o tempo esgota.
```
````

---

```ad-done
title:
#### **Fase 4 ) - Weather App ⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **04 )** - Weather Forecast App (Nível 4 - Intermediário Avançado)

```ad-quote
title:
<p align="justify">Painel de previsão meteorológica consumindo uma API REST pública (ex: OpenWeatherMap ou WeatherAPI). O foco é o consumo assíncrono profissional de serviços externos, abstração em Custom Hooks e blindagem visual de estados assíncronos.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O usuário digita o nome de uma cidade em um campo de busca. O aplicativo faz a requisição à API externa, exibe as condições atuais (temperatura, umidade, vento, sensação térmica, ícone do clima) e uma projeção dos próximos 5 dias, com tela de carregamento (Skeleton/Spinner) e tratamento elegante de erros.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Requisições HTTP Assíncronas
# Uso de fetch ou axios com async/await encapsulado dentro de useEffect ou handler de busca disparado pelo usuário.


02 ) A Tríade de Estados Assíncronos
# data: armazena os dados processados da API.
# isLoading: booleano que determina a exibição de Skeleton Screen ou Loading Spinner.
# error: string ou objeto para capturar mensagens de erro amigáveis ao usuário.


03 ) Abstração em Custom Hook (useWeather)
# Isolamento da lógica de chamada HTTP, tratamento de parâmetros e gerenciamento dos 3 estados: const { data, loading, error, refetch } = useWeather(city).


04 ) Cancelamento de Requisições (AbortController)
# Implementação de new AbortController() no cleanup de useEffect para cancelar requisições em voo caso o usuário dispare nova busca antes da resposta anterior.


05 ) Variáveis de Ambiente (.env) no Vite
# Configuração de chaves de API usando import.meta.env.VITE_WEATHER_API_KEY.


06 ) Renderização Defensiva
# Acesso seguro a dados encadeados usando optional chaining (data?.main?.temp) e tratamento defensivo para respostas vazias ou nulas.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Componentes*
```

```bash
WeatherApp
 ├── SearchBar (input de busca com validação e botão de pesquisa)
 ├── WeatherStateContainer
 │    ├── LoadingSkeleton (renderizado quando isLoading === true)
 │    ├── ErrorAlert (renderizado quando error !== null)
 │    └── CurrentWeather (temperatura atual, cidade, clima, métricas)
 └── ForecastList (previsão dos próximos dias)
      └── ForecastCard (dia da semana, ícone, temp mín/máx)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Nenhum dado inexistente deve gerar erro de tela branca (Uncaught TypeError: undefined).
# [x] O usuário deve receber feedback visual instantâneo ao pesquisar (loading indicator).
# [x] A chave da API não deve estar hardcoded diretamente nos componentes JSX.


# Desafio Bônus:
# Implementar um seletor para alternar unidades de medida (°C / °F) recalculando a interface instantaneamente.
```
````

---

```ad-done
title:
#### **Fase 5 ) - Mini E-Commerce ⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **05 )** - Mini E-Commerce com Carrinho Global (Nível 5 - Avançado)

```ad-quote
title:
<p align="justify">Catálogo de produtos com carrinho de compras lateral interativo e persistente. Elimina o problema de Prop Drilling através do gerenciamento de estado global nativo com Context API e padronização de ações com useReducer.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 5.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O sistema exibe uma grade de produtos com fotos, preços e categorias. O usuário pode adicionar itens ao carrinho, incrementar/decrementar quantidades, remover itens e visualizar o subtotal atualizado. Um drawer lateral exibe os itens adicionados e reflete o total de itens em um badge no cabeçalho.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Estado Global com Context API
# Criação do CartContext usando createContext() e encapsulamento da aplicação com um componente Provedor customizado (CartProvider).


02 ) Gerenciamento Robusto com useReducer
# Centralização da máquina de estados do carrinho com ações tipadas: 'ADD_TO_CART' | 'REMOVE_FROM_CART' | 'INCREMENT_QTY' | 'DECREMENT_QTY' | 'CLEAR_CART'.
# Lógica pura: se o item já existe, incrementa quantidade; se decrementado a zero, remove automaticamente.


03 ) Custom Hook Consumidor Blindado (useCart)
# Hook utilitário que chama useContext(CartContext) e lança um erro explicativo caso seja invocado fora da árvore do CartProvider.


04 ) Performance & Memoização com useMemo
# Cálculo de valores derivados complexos (total de itens, subtotal monetário, frete estimado) memoizados para não recalcular em re-renders alheios.


05 ) Sincronização com localStorage
# Leitura inicial do carrinho salva no localStorage e atualização automática no useEffect sempre que o carrinho mudar.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Componentes*
```

```bash
CartProvider (engloba toda a aplicação com CartContext.Provider)
 └── App
      ├── Navbar (logo, categorias e botão do carrinho com badge animado)
      ├── ProductCatalog (grid responsivo de itens)
      │    └── ProductCard (imagem, preço formatado, botão "Adicionar")
      └── CartDrawer (painel lateral retrátil)
           ├── CartHeader (título e botão fechar)
           ├── CartItemList
           │    └── CartItem (foto, controles + e -, preço individual e remover)
           └── CartFooter (subtotal, cálculo de frete e botão Checkout)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Nenhuma prop de carrinho deve ser repassada via prop drilling pelos componentes intermediários.
# [x] Recarregar a página deve manter os itens no carrinho exatamente como estavam.
# [x] Formatação monetária padronizada com new Intl.NumberFormat('pt-BR', { style: 'currency' }).


# Desafio Bônus:
# Implementar um campo de cupom de desconto com validação imediata (ex: 'REACT10' aplica 10% off).
```
````

---

```ad-done
title:
#### **Fase 6 ) - Blog SPA ⭐⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **06 )** - Blog & Portal SPA Multi-páginas (Nível 6 - Avançado)

```ad-quote
title:
<p align="justify">Plataforma de publicação de artigos no formato Single Page Application completa com múltiplas telas, navegação fluida sem recarregamento, rotas dinâmicas com parâmetros de URL e cascas compartilhadas de layout.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 6.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">A plataforma possui páginas de Início (listagem de posts recentes), Artigos (com busca e filtro por tags via URL), Detalhe do Artigo (/posts/:id ou :slug), Sobre Nós e uma página de erro customizada 404 (Not Found) para URLs desconhecidas.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Configuração Moderna do React Router DOM
# Definição de rotas declarativas com createBrowserRouter e injeção com <RouterProvider router={router} />.


02 ) Layouts Aninhados & Outlet
# Componente RootLayout com Navbar e Footer compartilhados em todas as telas, injetando páginas dinâmicas através de <Outlet />.


03 ) Navegação Declarativa & Programática
# Uso de <NavLink> com função className={({ isActive }) => ...} para realçar abas ativas. Uso do hook useNavigate() para redirecionamentos programáticos.


04 ) Rotas Dinâmicas & Hook useParams
# Registro da rota path: "/posts/:postId" e extração do identificador com const { postId } = useParams().


05 ) Query Strings & Hook useSearchParams
# Sincronização de filtros de pesquisa e categoria na URL (/posts?category=react&search=hooks) para permitir compartilhamento de links filtrados.


06 ) Rota Coringa 404 & errorElement
# Rota coringa com path: "*" apontando para NotFound404 e tratamento de exceções via errorElement.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Componentes e Rotas*
```

```bash
Roteador (createBrowserRouter)
 └── RootLayout (Navbar + <Outlet /> + Footer)
      ├── Route "/" ───────────► HomePage (banners, posts em destaque)
      ├── Route "/posts" ──────► PostsPage (busca com useSearchParams e grid)
      ├── Route "/posts/:id" ──► PostDetailPage (consumo dinâmico com useParams)
      ├── Route "/about" ──────► AboutPage (estática)
      └── Route "*" ───────────► NotFoundPage (404 com botão "Voltar ao Início")
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Toda a navegação deve ocorrer sem recarregar o navegador (Client-Side Routing estrito).
# [x] Digitar um ID de artigo inexistente deve renderizar um aviso de "Artigo Não Encontrado".
# [x] Parâmetros de pesquisa na URL devem persistir ao compartilhar ou recarregar a URL.


# Desafio Bônus:
# Adicionar um botão de "Voltar ao topo" (Scroll-to-top) acionado automaticamente a cada troca de rota.
```
````

---

```ad-done
title:
#### **Fase 7 ) - Kanban Board ⭐⭐⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **07 )** - Kanban Board Interativo com Zustand (Nível 7 - Expert)

```ad-quote
title:
<p align="justify">Quadro de produtividade e gestão ágil de tarefas (estilo Trello/Jira). O projeto exercita o controle de estado global de alto desempenho através de stores atômicas com Zustand, manipulação de drag-and-drop e otimização cirúrgica de re-renderizações.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 7.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">O quadro é composto por múltiplas colunas (ex: "A Fazer", "Em Andamento", "Revisão", "Concluído"). O usuário pode criar novos cartões, editar títulos e descrições diretamente na interface (edição inline), adicionar tags coloridas, excluir cartões e arrastar tarefas entre diferentes colunas ou reordená-las dentro da mesma coluna.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Estado Global Atômico com Zustand
# Criação da store via create() com métodos manipuladores (moveCard, addCard, deleteCard, editCard).
# Consumo com seletores atômicos: const moveCard = useKanbanStore(state => state.moveCard) para evitar re-renders em nós irmãos.


02 ) Persistência Transparente com Middleware
# Configuração do middleware persist() do Zustand para sincronizar o board automaticamente no localStorage.


03 ) Integração de Drag and Drop
# Uso de biblioteca moderna (@dnd-kit/core ou @hello-pangea/dnd) gerenciando eventos onDragStart, onDragOver e onDragEnd com reordenação imutável dos arrays.


04 ) Otimização de Performance
# Emprego de React.memo nos componentes individuais de cartão (<KanbanCard />) e memoização de handlers pesados com useCallback.


05 ) Identificadores Únicos & Edição Inline
# Geração de IDs padronizados usando crypto.randomUUID() e edição inline com alternância de modo (leitura vs input).
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Estrutura de Componentes*
```

```bash
KanbanBoard (invoca useKanbanStore com seletores)
 ├── BoardHeader (estatísticas rápidas, filtro por tag e botão "Nova Coluna")
 └── DndContext (wrapper de drag-and-drop)
      └── ColumnContainer
           └── KanbanColumn (renderiza coluna e container droppable)
                ├── ColumnHeader (título, contador de cards e menu)
                ├── CardList (área receptora)
                │    └── KanbanCard (item draggable, tags, título, botão delete)
                └── AddCardButton / InlineCardForm
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] O arrasto de um cartão deve refletir visualmente em tempo real sem atrasos.
# [x] Recarregar a página não pode reverter a posição ou o conteúdo das tarefas alteradas.
# [x] Cards não afetados pelo drag-and-drop não devem sofrer re-renderizações desnecessárias.


# Desafio Bônus:
# Permitir a criação de novas colunas customizadas pelo próprio usuário diretamente na tela.
```
````

---

```ad-done
title:
#### **Fase 8 ) - SaaS Dashboard ⭐⭐⭐⭐⭐⭐⭐⭐**
```

---

````ad-quote
title:

##### **08 )** - SaaS Dashboard Enterprise (Nível 8 - Master / Enterprise)

```ad-quote
title:
<p align="justify">Painel administrativo completo de uma aplicação SaaS simulada. O desafio máximo integra arquitetura corporativa: fluxo completo de autenticação com barreiras de segurança, validação estrita de formulários com schemas tipados, interceptores de requisição, lazy loading e gráficos analíticos.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 8.1 ) - _Detalhamento do Desafio_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Objetivo & Escopo*
```

```ad-quote
title:
<p align="justify">A aplicação contempla tela de Login/Cadastro com validação completa de campos (senhas fortes, formato de email), barreira de proteção de rotas privadas (impedindo acesso de usuários não logados ao dashboard), painel administrativo com gráficos de vendas e métricas de desempenho (Recharts), tabela com paginação e busca, e mecanismo de troca de tema (Dark/Light).</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Conceitos Técnicos Obrigatórios*
```

```bash
01 ) Fluxo Completo de Autenticação
# AuthContext para centralizar o estado do usuário (user, token, isAuthenticated, login, logout) e persistência do token de sessão.


02 ) Rotas Protegidas (Protected Routes Pattern)
# Componente guardião <ProtectedRoute>: se isAuthenticated for false, redireciona para /login via <Navigate to="/login" replace />; se true, renderiza <Outlet />.


03 ) Formulários de Alta Performance com Schema Zod
# Uso de React Hook Form (useForm) integrado com Zod (@hookform/resolvers/zod) para validação estrita e mensagens de erro específicas por campo.


04 ) Code Splitting & Lazy Loading
# Isolamento de rotas pesadas via React.lazy() com envelopamento em <Suspense fallback={<DashboardLoadingSkeleton />}>.


05 ) Visualização de Dados & Gráficos
# Integração de biblioteca de gráficos (Recharts) com containers responsivos (ResponsiveContainer) para métricas de conversão e faturamento.


06 ) Modais, Portais & Tema Global
# Modais de confirmação via ReactDOM.createPortal() e suporte a tema Claro/Escuro alternando a classe 'dark' no elemento raiz HTML.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Arquitetura de Pastas e Roteamento Enterprise*
```

```bash
src/
 ├── assets/
 ├── components/
 │    ├── ui/ (Button, Input, Card, Modal, Badge)
 │    └── layout/ (Sidebar, Topbar, ProtectedLayout)
 ├── context/ (AuthContext.tsx, ThemeContext.tsx)
 ├── hooks/ (useAuth, useTheme, useDebounce)
 ├── pages/
 │    ├── auth/ (LoginPage, RegisterPage)
 │    └── dashboard/ (OverviewPage, AnalyticsPage, UsersPage, SettingsPage)
 ├── routes/
 │    ├── index.tsx (definição de rotas públicas e <ProtectedRoute>)
 └── schemas/ (authSchemas.ts, userSchemas.ts com Zod)
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Critérios de Aceite & Desafio Bônus*
```

```bash
# Critérios de Aceite:
# [x] Nenhuma rota sob /dashboard pode ser acessada por URL direta se o usuário não estiver autenticado.
# [x] O formulário deve bloquear submissão e exibir erros claros se os critérios do schema Zod falharem.
# [x] As páginas pesadas do dashboard devem ser empacotadas em chunks isolados via React.lazy().
# [x] O logout deve limpar imediatamente o estado de autenticação e redirecionar para o login.


# Desafio Bônus:
# Simular um interceptor HTTP com atraso artificial (delay) e injeção automática do cabeçalho Bearer Token.
```
````

---
