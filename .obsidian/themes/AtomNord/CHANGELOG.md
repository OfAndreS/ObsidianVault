# Histórico de Ajustes: Tema AtomNord (Obsidian)

Documento de registro técnico dos problemas encontrados, decisões tomadas e soluções implementadas no tema **AtomNord** do Obsidian.

---

## 1. Visão Geral das Modificações (V-1.0)

O objetivo principal foi aproximar o tema da paleta Nord autêntica, clareando suavemente a interface sem alterar o contraste de leitura, inserindo um grid sutil de fundo e preservando a identidade visual dos blocos de texto e código.

### Ajustes Estruturais de Cores
- **Barras laterais e Barra de título**:
  - *Antes*: `#272c36` (muito escuro / carvão, fora da paleta Nord).
  - *Depois*: `#2e3440` (`--nord0`), o tom ardósia clássico oficial da paleta Polar Night.
- **Fundo do Editor (`--background-primary`)**:
  - *Antes*: `#2e3440`.
  - *Depois*: `#343b48`, clareado com suavidade mantendo o tom nórdico e harmonia com o texto.
- **Divisórias (`--background-modifier-border`)**:
  - Ajustadas para `rgba(76, 86, 106, 0.35)`.

### Grid Técnico de Fundo
- Implementado no container de leitura e edição (`.markdown-source-view.mod-cm6` e `.markdown-preview-view`):
  ```css
  --nord-grid-color: rgba(136, 192, 208, 0.04);
  --nord-grid-size: 28px;

  .workspace-split.mod-root .markdown-source-view.mod-cm6,
  .workspace-split.mod-root .markdown-preview-view {
    background-image: 
      linear-gradient(to right, var(--nord-grid-color) 1px, transparent 1px),
      linear-gradient(to bottom, var(--nord-grid-color) 1px, transparent 1px);
    background-size: var(--nord-grid-size) var(--nord-grid-size);
  }
  ```

### Elementos Mantidos Intocados
- Títulos (`h1` a `h6` e `.inline-title`).
- Links internos e externos.
- Formatação geral do texto.
- Blocos de código (`pre`, `code`, `.HyperMD-codeblock`) e realce de sintaxe.

---

## 2. Problemas Enfrentados e Soluções Técnicas

### Problema 1: Linhas do grid vazando por dentro dos blocos `> [!*]` e `ad-*`
- **Causa**: Callouts nativos e blocos do plugin Admonition utilizam fundos com canal alfa translúcido (ex: `rgba(..., 0.1)`). Por causa dessa transparência, as linhas do grid passavam por dentro dos blocos.
- **Tentativas que falharam**:
  - *Forçar `.cm-sizer` a ser opaco*: Tornou o documento um cartão rígido e quebrou o fluxo natural.
  - *Pseudo-elemento `::before`*: O `::before` no stacking context foi renderizado por cima do fundo colorido, apagando as cores distintas de cada callout e deixando todos com a mesma cor cinza do editor.
- **Solução Correta**: Uso de `color-mix(in srgb, <cor> 10%, var(--background-primary)) !important`. Mistura 10% da cor própria do bloco com a cor de fundo sólida do editor, resultando na **mesma tonalidade original**, mas com **100% de opacidade**, bloqueando o grid.

---

### Problema 2: Incompatibilidade de sintaxe entre `> [!*]` e `ad-*`
- **Causa**:
  - Em callouts nativos (`> [!*]`), o Obsidian passa `--callout-color` como uma tupla de números (ex: `136, 192, 208`), exigindo `rgb(...)`.
  - No plugin Admonition (`ad-*`), o script injeta a variável inline já formatada como string de cor pronta (ex: `--callout-color: rgb(61, 61, 61)`). Usar `rgb(var(--callout-color))` gerava `rgb(rgb(...))`, que é sintaxe CSS inválida e era descartada pelo navegador.
- **Solução Correta**: Cascata com tratamento específico:
  ```css
  /* Callouts nativos */
  .callout, .admonition {
    background-color: color-mix(in srgb, rgb(var(--callout-color)) 10%, var(--background-primary)) !important;
    background-color: color-mix(in srgb, var(--callout-color, rgb(61, 61, 61)) 10%, var(--background-primary)) !important;
  }
  ```

---

### Problema 3: Blocos aninhados (`ad-*` dentro de outro `ad-*`) perdendo contraste
- **Causa**: Ao forçar a mistura com `var(--background-primary)` em todos os níveis, as camadas filhas tinham o mesmo valor opaco que a camada pai, perdendo o contraste progressivo.
- **Solução Correta**:
  - **Camada externa (raiz)**: Mistura com `var(--background-primary)` (100% opaca) para bloquear o grid.
  - **Camadas internas (filhas)**: Misturam com `transparent`. Elas acumulam seu tom naturalmente sobre o bloco pai, preservando o escurecimento e contraste progressivo sem que o grid apareça (pois o bloco pai já bloqueia o grid).
  ```css
  .callout .callout,
  .admonition .admonition,
  .callout .admonition,
  .admonition .callout {
    background-color: color-mix(in srgb, rgb(var(--callout-color)) 10%, transparent) !important;
    background-color: color-mix(in srgb, var(--callout-color, rgb(61, 61, 61)) 10%, transparent) !important;
  }
  ```

---

### Problema 4: `ad-done` ainda transparente
- **Causa**: O snippet ativo `.obsidian/snippets/blue-adamotion.css` é carregado após o tema e sobrescrevia a regra com `rgba(136, 192, 208, 0.1)`.
- **Solução Correta**: Atualização de `.obsidian/snippets/blue-adamotion.css` e `.obsidian/themes/AtomNord/custom-admonition.css` para utilizar a mesma fórmula sólida:
  ```css
  background-color: color-mix(in srgb, rgb(136, 192, 208) 10%, var(--background-primary)) !important;
  ```

---

### Problema 5: `> [!quote]` nativo ainda transparente
- **Causa**: No Obsidian nativo, `> [!quote]` usa strings como `var(--text-muted)` ou nomes de variáveis para `--callout-color`, fazendo `rgb(...)` falhar.
- **Solução Correta**: Adição de regra específica com fallback para tupla e valor nomeado:
  ```css
  .callout[data-callout="quote"],
  .callout[data-callout="cite"] {
    background-color: color-mix(in srgb, rgb(var(--callout-color, 158, 158, 158)) 10%, var(--background-primary)) !important;
    background-color: color-mix(in srgb, var(--callout-color, var(--text-muted)) 10%, var(--background-primary)) !important;
  }
  ```

---

## 3. Arquivos Modificados
- [theme.css](file:///home/andre/Documents/VaultObsidian/.obsidian/themes/AtomNord/theme.css): Folha de estilo principal do tema AtomNord.
- [blue-adamotion.css](file:///home/andre/Documents/VaultObsidian/.obsidian/snippets/blue-adamotion.css): Snippet ativo do usuário para customização do callout done/check.
- [custom-admonition.css](file:///home/andre/Documents/VaultObsidian/.obsidian/themes/AtomNord/custom-admonition.css): Cópia local de segurança dentro da pasta do tema.
