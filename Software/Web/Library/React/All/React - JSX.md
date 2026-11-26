
---

https://coddy.tech/docs/pt/react/jsx

---
---
JSX é uma extensão de sintaxe do JavaScript que permite escrever marcação parecida com HTML dentro do seu código. Componentes React retornam JSX para descrever o que deve aparecer na tela, e uma ferramenta de build o compila em chamadas de função JavaScript comuns. Ele se parece com HTML, mas algumas regras são diferentes, e as chaves permitem colocar qualquer valor JavaScript na marcação.

---
---

#### Retorne um único elemento raiz

A regra de retornar um único elemento raiz é uma exigência técnica de como o React compila o JSX para JavaScript.

##### Por que o erro acontece

Cada tag JSX que você escreve é convertida para uma chamada da função `React.createElement`.

Em JavaScript, uma função comum só pode retornar um único valor por vez. Se você tenta colocar dois elementos soltos lado a lado no retorno da função, o compilador não consegue executar o código.

##### O exemplo incorreto

Veja o que gera um erro imediato no React:

```jsx
// Errado: Dois elementos soltos no retorno
function PerfilUsuario() {
  return (
    <h1>Nome do Usuário</h1>
    <p>Descrição sobre a carreira e formação do usuário.</p>
  );
}

```

O JavaScript enxerga esse retorno como duas chamadas independentes soltas sem um recipiente:

```javascript
// O que o compilador tenta fazer nos bastidores (inválido):
return (
  React.createElement("h1", null, "Nome do Usuário")
  React.createElement("p", null, "Descrição...")
);

```

##### O que você deveria fazer

A solução adequada varia de acordo com a necessidade visual e estrutural do seu componente:

##### 1. Usar um Fragmento (A melhor opção na maioria dos casos)

Quando os elementos só precisam ficar juntos para satisfazer a regra do compilador, sem precisar de estilização, classes ou alinhamento no elemento pai, utilize a sintaxe de Fragmento vazio (`<> </>`).

```jsx
// Correto: Fragmento agrupa os itens sem criar nós no navegador
function PerfilUsuario() {
  return (
    <>
      <h1>Nome do Usuário</h1>
      <p>Descrição sobre a carreira e formação do usuário.</p>
    </>
  );
}

```

No navegador, o fragmento desaparece por completo. Ele entrega apenas o título e o parágrafo diretamente para a página, mantendo a estrutura limpa.

##### 2. Usar uma tag semântica (Quando o bloco tem significado estrutural)

Se o conjunto de elementos representa um bloco específico do documento, prefira tags semânticas da web em vez de uma div genérica:

```jsx
// Correto: Tag semântica apropriada para um bloco de conteúdo independente
function PerfilUsuario() {
  return (
    <article className="cartao-perfil">
      <h1>Nome do Usuário</h1>
      <p>Descrição sobre a carreira e formação do usuário.</p>
    </article>
  );
}

```

##### 3. Usar uma div (Quando você precisa de uma caixa genérica para estilos ou eventos)

Se o bloco precisa de regras de posicionamento visual, uma classe específica de layout ou um evento de clique em toda a área, uma div é a ferramenta adequada:

```jsx
// Correto: A div tem função real de estilo e interação
function PerfilUsuario({ aoClicar }) {
  return (
    <div className="conteiner-destaque" onClick={aoClicar}>
      <h1>Nome do Usuário</h1>
      <p>Descrição sobre a carreira e formação do usuário.</p>
    </div>
  );
}

```

Em resumo: embrulhe sempre seus elementos em um contêiner comum. Use o fragmento vazio por padrão para não gerar elementos inúteis na página, e adote tags reais apenas quando houver necessidade de estilização, semântica ou eventos.