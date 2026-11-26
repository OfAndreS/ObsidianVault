
---

#### .map()

O método map do JavaScript funciona como uma esteira de transformação. Ele percorre cada elemento de uma lista original, aplica uma instrução definida por você em cada um deles e entrega uma nova lista, com exatamente o mesmo tamanho, contendo os resultados transformados. A lista original nunca é alterada nesse processo.

###### Exemplo basico em JavaScript puro

```javascript
const precos = [10, 20, 30];

const precosDobrados = precos.map(preco => preco * 2);

console.log(precosDobrados);

```

```shell
# Output:
[ 20, 40, 60 ]

```

###### 1. Transformacao de dados brutos da API para modelos visuais

Muitas vezes, a API entrega dados técnicos ou incompletos para a interface. O React precisa transformar essa estrutura antes de exibir. O map serve para formatar textos, converter unidades ou criar rótulos amigáveis.

```javascript
const usuariosApi = [
  { id: 1, nome: "Carlos", sobrenome: "Silva", ativo: true },
  { id: 2, nome: "Mariana", sobrenome: "Costa", ativo: false }
];

const usuariosFormatados = usuariosApi.map(usuario => ({
  id: usuario.id,
  nomeCompleto: `${usuario.nome} ${usuario.sobrenome}`,
  statusTexto: usuario.ativo ? "Online" : "Desconectado"
}));

console.log(usuariosFormatados);

```

```shell
# Output:
[
  { id: 1, nomeCompleto: 'Carlos Silva', statusTexto: 'Online' },
  { id: 2, nomeCompleto: 'Mariana Costa', statusTexto: 'Desconectado' }
]

```

###### 2. Conversao de listas simples em opcoes de campos de selecao

Campos do tipo select costumam exigir objetos com formato padronizado, geralmente contendo campos de valor e texto de exibição. O map converte uma lista simples de categorias em uma lista estruturada compatível com esses componentes.

```javascript
const categorias = ["Eletronicos", "Livros", "Roupas"];

const opcoesSelect = categorias.map((categoria, index) => ({
  value: index + 1,
  label: categoria
}));

console.log(opcoesSelect);

```

```shell
# Output:
[
  { value: 1, label: 'Eletronicos' },
  { value: 2, label: 'Livros' },
  { value: 3, label: 'Roupas' }
]

```

###### 3. Atualizacao imutavel de itens especificos em um estado

No React, nunca alteramos listas de estado diretamente. Para modificar um item específico (como alternar uma tarefa entre concluída e pendente), usamos o map. Ele percorre a lista, altera apenas o item que atende a uma condição e mantém os outros intactos, retornando um novo array para a aplicação.

```javascript
const tarefas = [
  { id: 101, titulo: "Comprar cafe", finalizada: false },
  { id: 102, titulo: "Responder emails", finalizada: false }
];

const idParaAlternar = 101;

const tarefasAtualizadas = tarefas.map(tarefa => {
  if (tarefa.id === idParaAlternar) {
    return { ...tarefa, finalizada: !tarefa.finalizada };
  }
  return tarefa;
});

console.log(tarefasAtualizadas);

```

```shell
# Output:
[
  { id: 101, titulo: 'Comprar cafe', finalizada: true },
  { id: 102, titulo: 'Responder emails', finalizada: false }
]

```

---
---
#### .filter()

O método filter funciona como uma peneira seletiva. Ele percorre cada item da lista original e avalia uma condição lógica definida por você. Se o item passar no teste (retornar verdadeiro), ele entra no novo array; se falhar (retornar falso), ele fica de fora. A lista original permanece totalmente intacta, gerando um novo array que pode ter o mesmo tamanho, ser menor ou até terminar vazio.

###### Exemplo basico em JavaScript puro

```javascript
const numeros = [5, 12, 8, 130, 44];

const maioresQueDez = numeros.filter(numero => numero > 10);

console.log(maioresQueDez);

```

```shell
[ 12, 130, 44 ]

```

###### 1. Remocao imutavel de itens de uma lista de estado

No React, excluir um elemento de uma lista de estado nunca deve ser feito com métodos que alteram a lista original, como o splice. Usamos o filter para manter todos os itens cujo identificador seja diferente daquele que o usuário escolheu apagar.

```javascript
const notificacoes = [
  { id: 1, mensagem: "Bem-vindo ao sistema" },
  { id: 2, mensagem: "Sua fatura foi paga" },
  { id: 3, mensagem: "Novo acesso detectado" }
];

const idParaRemover = 2;

const notificacoesAposExclusao = notificacoes.filter(item => item.id !== idParaRemover);

console.log(notificacoesAposExclusao);

```

```shell
[
  { id: 1, mensagem: 'Bem-vindo ao sistema' },
  { id: 3, mensagem: 'Novo acesso detectado' }
]

```

###### 2. Campo de busca em tempo real

Em telas com campos de pesquisa, o componente armazena o texto digitado e usa o filter para exibir apenas os registros que contenham esse termo no título ou nome, geralmente ignorando diferenças entre maiúsculas e minúsculas.

```javascript
const produtos = [
  { id: 101, nome: "Teclado Mecanico sem fio" },
  { id: 102, nome: "Mouse Gamer RGB" },
  { id: 103, nome: "Monitor Ultrawide 29" }
];

const termoDigitado = "teclado";

const produtosFiltrados = produtos.filter(produto =>
  produto.nome.toLowerCase().includes(termoDigitado.toLowerCase())
);

console.log(produtosFiltrados);

```

```shell
[
  { id: 101, nome: 'Teclado Mecanico sem fio' }
]

```

###### 3. Segmentacao por categorias ou abas de status

Muito comum em painéis administrativos ou lojas virtuais, onde o usuário clica em botões como "Todos", "Pendentes" ou "Concluídos" para alternar a visualização. O filter avalia a propriedade de status de cada item em relação ao filtro ativo.

```javascript
const pedidos = [
  { id: 501, cliente: "Joao", status: "entregue" },
  { id: 502, cliente: "Ana", status: "pendente" },
  { id: 503, cliente: "Marcos", status: "entregue" }
];

const abaSelecionada = "pendente";

const pedidosExibidos = pedidos.filter(pedido => {
  if (abaSelecionada === "todos") return true;
  return pedido.status === abaSelecionada;
});

console.log(pedidosExibidos);

```

```shell
[
  { id: 502, cliente: 'Ana', status: 'pendente' }
]

```

---
---

### 1. reduce

Condensa um array inteiro em um único valor, seja um total numérico, um objeto agrupador ou uma estrutura remodelada. Essencial para cálculos de checkout, balanços financeiros e agregações de dados antes da renderização.

### 2. find

Retorna o primeiro elemento que atende a uma condição lógica específica. É a ferramenta padrão para carregar páginas de detalhes a partir de um identificador na URL ou destacar um item selecionado pelo usuário.

### 3. some e every

Métodos de checagem condicional que retornam respostas booleanas. São indispensáveis para lógica de interface, como habilitar botões de envio de formulários, checar permissões de acesso ou exibir alertas de inconsistência.

### 4. toSorted

Versão moderna e imutável da ordenação tradicional de listas, gerando um novo array ordenado sem modificar a fonte original. Fundamental para tabelas interativas onde o usuário clica nas colunas para ordenar por data, preço ou ordem alfabética.

### 5. flatMap

Combina a transformação de cada elemento com o nivelamento de sublistas em um único passo. Muito útil para lidar com respostas de APIs que trazem listas aninhadas, como tags de postagens ou dependências de tarefas.

### 6. includes

Verifica a presença exata de um item primitivo dentro de uma lista simples. É amplamente aplicado em filtros com caixas de seleção múltipla para verificar se uma categoria ou opção específica está ativa.