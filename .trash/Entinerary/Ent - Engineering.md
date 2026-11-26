
---

````ad-quote
title:
```ad-quote
title:
##### **Roteiro de Estudos Detalhado: Software Engineering**
```
```ad-quote
title:
Este é um roteiro de estudos abrangente para a formação em Engenharia de Software, projetado para transformar programadores em engenheiros completos. Dividido em módulos sequenciais, ele aborda desde a arquitetura de software e design patterns até metodologias ágeis e práticas de teste. Cada etapa equilibra conceitos teóricos com um plano de ação prático, incentivando a aplicação imediata do conhecimento. O percurso culmina em um projeto integrador que simula a construção de um sistema real. O objetivo final é capacitar o estudante a projetar e construir aplicações robustas, escaláveis e de alta qualidade.
```
````

---

> [!example] _New_

---

````ad-quote
title:
```ad-quote
title:
##### **Módulo 00:** Core Principles - O Alicerce do Bom Código
```

```ad-quote
title:
| Atributo | Descrição |
|---|---|
| `Objetivo` | Internalizar os princípios que diferenciam um código que "funciona" de um código profissional, legível e manutenível. |
| `Duração Sugerida` | 2-3 Semanas. |
```
````

````ad-quote
title:
```ad-quote
title:
###### **Semana 1 )** Clean Code - A Arte da Legibilidade
```

```ad-quote
title:

| Tópico | Detalhes |
|---|---|
| `Nomes Significativos` | A importância de nomes que revelam o propósito. Estude a diferença entre d, elapsed, e elapsedTimeInDays. Aprenda a nomear variáveis, funções e classes de forma clara e buscável. |
| `Funções` | Entenda a regra de ouro: "funções devem fazer apenas uma coisa, fazê-la bem e ser pequenas". Estude sobre o número ideal de argumentos, efeitos colaterais (side-effects) e a separação entre comandos e consultas (CQS). |
| `Comentários` | Aprenda a filosofia de que "comentários são uma falha". Entenda quando um comentário é necessário (ex: explicar a intenção por trás de uma decisão complexa) e quando ele é um sinal de que o código precisa ser reescrito para ser mais expressivo. |
| `Formatação` | A importância da consistência. Estude sobre formatação vertical (agrupamento de código) e horizontal (comprimento de linhas). |
```

```ad-quote
title:

- [ ] 01 - Nomes Significativos
- [ ] 02 - Funções
- [ ] 03 - Comentários
- [ ] 04 - Formatação
```

```ad-quote
title:
**Plano de Ação Prático**
```

```ad-quote
title:

| Ação | Detalhes |
|---|---|
| `Leitura Obrigatória` | Capítulos 1 a 6 do livro "Código Limpo" de Robert C. Martin. |
| `Exercício de Refatoração` | Pegue um projeto pessoal antigo ou um script que você escreveu. Imprima o código. Com uma caneta vermelha, circule todos os nomes de variáveis ruins, funções longas e comentários inúteis. Passe as próximas horas refatorando este código aplicando apenas os princípios desta semana. |
| `Ferramentas` | Configure e use um Linter e um Formatador de Código (ex: ESLint/Prettier para JS, Pylint/Black para Python, Checkstyle para Java) no seu editor. Deixe as ferramentas forçarem você a escrever código mais limpo. |
```

````

````ad-quote
title:
```ad-quote
title:
###### **Semanas 2-3 )** SOLID - Os Pilares do Design de Classes
```

```ad-quote
title:

| Princípio | Descrição |
|---|---|
| `(S) Single Responsibility Principle` | Entenda que uma classe deve ter apenas um motivo para mudar. |
| `(O) Open/Closed Principle` | Entenda que software deve ser "aberto para extensão, mas fechado para modificação". |
| `(L) Liskov Substitution Principle` | Entenda que subtipos devem ser substituíveis por seus tipos base sem quebrar a aplicação. |
| `(I) Interface Segregation Principle` | Entenda que é melhor ter muitas interfaces específicas do que uma única interface genérica. |
| `(D) Dependency Inversion Principle` | Entenda que módulos de alto nível não devem depender de módulos de baixo nível; ambos devem depender de abstrações. |
```

```ad-quote
title:

- [ ] 01 - S
- [ ] 02 - O
- [ ] 03 - L
- [ ] 04 - I
- [ ] 05 - D
```

```ad-quote
title:
**Plano de Ação Prático**
```

```ad-quote
title:

| Ação | Detalhes |
|---|---|
| `Criação de "Anti-Padrões"` | Para cada princípio SOLID, crie intencionalmente uma pequena classe ou conjunto de classes que o viole. Sinta a "dor" que essa violação causa (dificuldade de testar, rigidez, etc.). |
| `Refatoração Guiada` | Agora, refatore cada um dos seus "anti-padrões" para que eles sigam o princípio SOLID correspondente. Documente no Obsidian o "antes" e o "depois" com screenshots de código e explicações. |
| `Estudo de Caso` | Pesquise artigos ou vídeos que demonstrem a aplicação de SOLID em frameworks que você usa (ex: "SOLID in React Components", "SOLID in Spring"). |
```
````

---

> [!example] _New_

---

````ad-quote
title:
```ad-quote
title:
##### **Módulo 01 )** Software Architecture - A Visão do Todo
```

```ad-quote
title:
| Atributo | Descrição |
|---|---|
| `Objetivo` | Aprender a tomar decisões de alto nível que definirão a estrutura, escalabilidade e manutenibilidade do sistema. |
| `Duração Sugerida` | 2 Semanas. |
```

```ad-quote
title:

| Tópico | Detalhes |
|---|---|
| `Atributos de Qualidade (Não-Funcionais)` | Vá além do "o que" o software faz e foque no "como". Estude a fundo: Performance, Escalabilidade, Disponibilidade, Resiliência, Segurança e Manutenibilidade. Entenda que eles são interdependentes e que existem trade-offs. |
| `Padrões Arquiteturais Fundamentais` | Monolito vs. Microsserviços, Arquitetura em Camadas (Layered), Arquitetura Orientada a Eventos (Event-Driven), Arquitetura Hexagonal (Ports & Adapters). |
```

```ad-quote
title:
- [ ] 01 - Atributos de Qualidade (Não-Funcionais)
- [ ] 02 - Padrões Arquiteturais Fundamentais
```

```ad-quote
title:
**Plano de Ação Prático**
```

```ad-quote
title:

| Ação | Detalhes |
|---|---|
| `Exercício de Análise` | Escolha 3 aplicativos que você usa diariamente (ex: Spotify, Instagram, Gmail). Para cada um, escreva uma nota no Obsidian especulando sobre: Quais são seus atributos de qualidade mais críticos? Qual padrão arquitetural eles provavelmente usam e por quê? |
| `Exercício de Desenho` | Imagine que você vai construir um sistema de "blog simples". Desenhe a arquitetura dele em um diagrama (use ferramentas como diagrams.net ou Excalidraw) de duas formas diferentes: uma usando uma arquitetura em camadas monolítica e outra usando microsserviços. Liste os prós e contras de cada abordagem para este caso de uso específico. |
```
````

---

> [!example] _New_

---

````ad-quote
title:
```ad-quote
title:
##### **Módulo 02 )** Design Patterns - Soluções Reutilizáveis
```

```ad-quote
title:
| Atributo | Descrição |
|---|---|
| `Objetivo` | Dominar um vocabulário de soluções testadas e comprovadas para problemas recorrentes de design de software. |
| `Duração Sugerida` | 3-4 Semanas. |
```

```ad-quote
title:

| Categoria | Padrões Sugeridos |
|---|---|
| `Criacionais (Como criar objetos)` | Factory Method, Singleton, Builder. |
| `Estruturais (Como compor objetos)` | Adapter, Decorator, Facade. |
| `Comportamentais (Como objetos se comunicam)` | Strategy, Observer, Command. |
```

```ad-quote
title:
- [ ] 01 - Padrões Criacionais
- [ ] 02 - Padrões Estruturais
- [ ] 03 - Padrões Comportamentais
```

```ad-quote
title:
**Plano de Ação Prático**
```

```ad-quote
title:

| Ação | Detalhes |
|---|---|
| `Leitura Obrigatória` | Use o site Refactoring.Guru como sua principal fonte. Ele tem explicações claras, analogias e exemplos de código. |
| `Implementação do Zero` | Para cada padrão estudado, crie um novo mini-projeto e implemente-o do zero na sua linguagem de programação preferida. Não copie e cole. Digite o código para internalizar a estrutura. |
| `Identificação em Código Real` | Procure por implementações desses padrões em bibliotecas ou frameworks de código aberto que você admira. Ver como eles são usados em um contexto real é extremamente valioso. |
```
````

---

> [!example] _New_

---

````ad-quote
title:
```ad-quote
title:
##### **Módulo 03 )** Methodologies & Processes - Como o Software é Construído
```

```ad-quote
title:
| Atributo | Descrição |
|---|---|
| `Objetivo` | Entender os processos e rituais que as equipes usam para entregar software de forma eficiente e colaborativa. |
| `Duração Sugerida` | 1 Semana. |
```

```ad-quote
title:

| Tópico | Detalhes |
|---|---|
| `SDLC (Ciclo de Vida)` | Entenda as fases clássicas: Requisitos, Design, Implementação, Testes, Implantação e Manutenção. |
| `Cascata (Waterfall) vs. Ágil (Agile)` | Entenda a diferença fundamental de filosofia. |
| `Agile Manifesto` | Leia e entenda os 4 valores e 12 princípios. |
| `Scrum` | Aprofunde-se nos 3 papéis (PO, SM, Dev Team), 5 eventos (Sprint, Planning, Daily, Review, Retrospective) e 3 artefatos (Product Backlog, Sprint Backlog, Increment). |
| `Kanban` | Foco em fluxo contínuo, limitação de trabalho em progresso (WIP) e visualização do trabalho. |
```

```ad-quote
title:
- [ ] 01 - SDLC (Ciclo de Vida)
- [ ] 02 - Cascata vs. Ágil
- [ ] 03 - Agile Manifesto
- [ ] 04 - Scrum
- [ ] 05 - Kanban
```

```ad-quote
title:
**Plano de Ação Prático**
```

```ad-quote
title:

| Ação | Detalhes |
|---|---|
| `Gerencie seu Estudo com Kanban` | Use uma ferramenta (Trello, Jira, ou o plugin Kanban do Obsidian) para gerenciar este roteiro de estudos. Crie colunas "A Fazer", "Fazendo", "Feito". |
| `Simule um Sprint` | Tente planejar uma semana de estudos como um "Sprint". Defina um "Sprint Goal" e faça uma "review" no final da semana para ver o que você concluiu. |
```
````

---

> [!example] _New_

---

````ad-quote
title:
```ad-quote
title:
##### **Módulo 04 )** Testing & Quality - Garantindo que Tudo Funciona
```

```ad-quote
title:
| Atributo | Descrição |
|---|---|
| `Objetivo` | Aprender a escrever código que não apenas funciona, mas que é comprovadamente correto e resiliente a mudanças. |
| `Duração Sugerida` | 2 Semanas. |
```

```ad-quote
title:

| Tópico | Detalhes |
|---|---|
| `Pirâmide de Testes` | Entenda a proporção ideal entre Testes de Unidade, Integração e End-to-End (E2E). |
| `Testes de Unidade` | O que são, por que são importantes. Aprenda o padrão AAA (Arrange, Act, Assert). |
| `TDD (Test-Driven Development)` | O ciclo Red-Green-Refactor. Entenda a filosofia de escrever o teste antes do código de produção. |
| `Mocks, Stubs & Fakes` | Aprenda a isolar a unidade sob teste de suas dependências. |
| `Code Review & Análise Estática` | Entenda a importância da revisão por pares e do uso de ferramentas que encontram problemas antes mesmo de o código ser executado. |
```

```ad-quote
title:
- [ ] 01 - Pirâmide de Testes
- [ ] 02 - Testes de Unidade
- [ ] 03 - TDD (Test-Driven Development)
- [ ] 04 - Mocks, Stubs & Fakes
- [ ] 05 - Code Review & Análise Estática
```

```ad-quote
title:
**Plano de Ação Prático**
```

```ad-quote
title:

| Ação | Detalhes |
|---|---|
| `Escolha um Framework` | Aprenda a usar um framework de testes popular para sua linguagem (ex: JUnit para Java, PyTest para Python, Jest para JavaScript/TypeScript). |
| `Pratique TDD` | Crie uma classe simples (ex: uma Calculadora) usando estritamente o ciclo TDD. Escreva um teste que falha, faça-o passar da forma mais simples possível e depois refatore. |
| `Teste o Código Antigo` | Volte aos projetos que você usou nos módulos anteriores e escreva testes de unidade para eles. Isso vai revelar a dificuldade de testar código que não foi projetado para ser testável. |
```
````

---

> [!example] _New_

---

````ad-quote
title:
```ad-quote
title:
##### **Projeto Prático Integrador (Capstone)**
```

```ad-quote
title:
| Atributo | Descrição |
|---|---|
| `Duração` | Contínua, ao longo de todo o estudo. |
| `Ideia` | Construir uma API REST para um sistema de gerenciamento de tarefas (To-Do List API). |
```

```ad-quote
title:
| Fase | Atividades |
|---|---|
| `Fase 1 (Módulo 00 e 03)` | Crie o projeto e o repositório. Defina os requisitos básicos. Gerencie as tarefas em um quadro Kanban. Comece a criar as entidades (Models) e serviços aplicando os princípios de Clean Code e SOLID desde a primeira linha. |
| `Fase 2 (Módulo 04)` | Comece a implementar os endpoints (criar, ler, atualizar, deletar tarefas) usando TDD. Para cada nova funcionalidade, escreva os testes de unidade primeiro. |
| `Fase 3 (Módulo 01 e 02)` | Conforme o projeto cresce, pare e pense na Arquitetura. Refatore o código para uma Arquitetura em Camadas. Identifique uma oportunidade para usar um Design Pattern. Exemplo: use o padrão Strategy para permitir diferentes formas de ordenar as tarefas. |
| `Fase 4 (Revisão Contínua)` | Periodicamente, faça um "auto-code review" do seu projeto. Documente suas decisões de design no Obsidian, criando notas sobre por que você escolheu um determinado padrão ou arquitetura para resolver um problema específico. |
```

```ad-quote
title:
- [ ] 01 - Fase 1 (Módulo 00 e 03)
- [ ] 02 - Fase 2 (Módulo 04)
- [ ] 03 - Fase 3 (Módulo 01 e 02)
- [ ] 04 - Fase 4 (Revisão Contínua)
```

````

---
