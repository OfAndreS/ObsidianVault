
---

https://www.w3schools.com/js/

>[!quote] **Vault:** [[JS - Array.Prototype]]

---
---
##### Mutabilidade das variáveis

No JavaScript existem tipos primitivos e tipos por referência. Para os tipos primitivos, a atribuição copia o valor diretamente na memória, permitindo que a nova variável seja alterada sem afetar a original. Já para os tipos por referência, a atribuição copia apenas o ponteiro que aponta para o mesmo objeto alocado na memória Heap. Como ambas compartilham esse mesmo endereço, qualquer mutação feita na estrutura da variável A afeta diretamente a variável B.

```js
// Exemplo com tipo primitivo: cópia direta de valor
let pontuacaoA = 100;
let pontuacaoB = pontuacaoA; // Copia apenas o valor numérico

pontuacaoB = 250; // Modifica somente a variável B

console.log(pontuacaoA); // 100 (a variável original permaneceu intacta)
console.log(pontuacaoB); // 250


// Exemplo com tipo por referência: compartilhamento de endereço na memória
const jogadorA = {
  nome: "Lucas",
  nivel: 1
};

const jogadorB = jogadorA; // Copia a referência para o mesmo objeto

jogadorB.nivel = 2; // Altera a estrutura interna usando o apelido B

console.log(jogadorA.nivel); // 2 (o objeto original também refletiu a mudança)
console.log(jogadorB.nivel); // 2
```

Dessa forma, para trabalhar com os tipos de referência sem alterar o valor da variável original é necessário entender a notação para cada tipo de dado de referência.

###### Listas com métodos que alteram a memória

Métodos nativos comuns não devolvem uma nova lista, eles alteram diretamente a gaveta de memória original.

```javascript
const filaDeTarefas = ["Compilar", "Testar"];

// Maneira problemática: altera a lista original
function processarFilaIncorreta(lista) {
  lista.push("Publicar"); // Modifica diretamente o endereço original
  return lista;
}

// Maneira segura: clona a lista antes de alterar
function processarFilaSegura(lista) {
  const novaFila = [...lista]; // Cria um novo array na memória
  novaFila.push("Publicar");
  return novaFila;
}

const resultado = processarFilaSegura(filaDeTarefas);
console.log(filaDeTarefas); // Mantém apenas ["Compilar", "Testar"]
console.log(resultado);    // ["Compilar", "Testar", "Publicar"]

```

###### Objetos literais com múltiplos níveis de profundidade

Quando um objeto guarda outro objeto por dentro, o operador de espalhamento convencional só protege a primeira camada. A camada interna continua compartilhando o mesmo endereço.

```javascript
const perfilOriginal = {
  usuario: "andre",
  preferencias: {
    tema: "escuro"
  }
};

// Cópia superficial: perigosa para dados aninhados
const copiaSuperficial = { ...perfilOriginal };
copiaSuperficial.preferencias.tema = "claro";

// O tema no objeto original também mudou para claro
console.log(perfilOriginal.preferencias.tema); // "claro"

// Solução segura para aninhamento: cópia profunda
const perfilOriginal2 = {
  usuario: "andre",
  preferencias: {
    tema: "escuro"
  }
};

const copiaProfunda = structuredClone(perfilOriginal2);
copiaProfunda.preferencias.tema = "claro";

console.log(perfilOriginal2.preferencias.tema); // Permanece "escuro"
console.log(copiaProfunda.preferencias.tema);   // "claro"

```

###### Instâncias de datas nativas

O tipo Date possui métodos de alteração interna de valor que mutam a mesma referência de tempo na memória sem gerar uma nova data.

```javascript
const dataInicio = new Date("2026-10-01");

// Maneira problemática: avança o dia na própria referência
const prazoFinal = dataInicio;
prazoFinal.setDate(15);

console.log(dataInicio.toISOString()); // Virou dia 15 sem você perceber

// Maneira segura: criar uma nova instância passando o carimbo original
const dataCriacao = new Date("2026-10-01");
const dataEntrega = new Date(dataCriacao.getTime());
dataEntrega.setDate(15);

console.log(dataCriacao.toISOString()); // Permanece dia 01
console.log(dataEntrega.toISOString()); // Reflete dia 15

```

###### Coleções estruturadas como Map e Set

Essas coleções guardam referências para suas chaves e valores. Atribuir a mesma coleção para uma nova variável apenas replica o canal de acesso.

```javascript
const categoriasOriginais = new Set(["Frontend", "Backend"]);

// Maneira problemática: compartilhamento de referência
const novasCategorias = categoriasOriginais;
novasCategorias.add("DevOps");

console.log(categoriasOriginais.has("DevOps")); // Retorna true

// Maneira segura: instanciar uma nova coleção a partir da existente
const categoriasBase = new Set(["Frontend", "Backend"]);
const categoriasAtualizadas = new Set(categoriasBase);
categoriasAtualizadas.add("DevOps");

console.log(categoriasBase.has("DevOps"));        // false (isolado)
console.log(categoriasAtualizadas.has("DevOps")); // true

```

---
---

Operador ternário
```js 

const permicaoParaBeber (idade > 18) ? "Sim, pode comprar cerveja!" : "Não, pode comprar cerveja!"

```

Empilhamento de operadores ternátios
```js 

let = temIdentidade = true

const permicaoParaBeber = (idade > 18) ? "Sim, pode comprar cerveja!" 
	: (temIdentidade) 

```

---

Funções são dados e podem ser armazenadas em variáveis.

```js
// Function declaration

function execute() {
	// ...
} 

```

```js
// Function expression

const execute = myFunction() {
	// ...
} 

```

```js
// Arrow Function

const min = (a,b) => a > b ? b : a

```

A função no JavaScript sempre retorna algo. Dessa forma, caso a função esteja vazia ela retorna um ripo padrão da linguágem "undefined".

```js
function execute(a, b, c) {
	// ...
} 

exe = execute(1,2,3) // 
console.log(exe) // undefined
```

Caso um dos parâmetros não receba um valor durante a execução da função ele também irá operar com "undefined"

```js
function execute(a, b, c) {
	console.log(a) // 1
	console.log(b) // 2
	console.log(c) // undefined
} 

exe = execute(1,2)
```

Também é possível chamar uma função com mais parâmetros do que foi especificado originalmente. Entretanto, se a função não foi preparada para tal operação os parâmetros extras serão ignorados.

Funções podem ser declaradas uma dentro da outra.

```js

function someDosQuadrados(a,b) {
	function quadrado(x) {
		return x * x
	}
	
	return quadrado(a) + quadrado(b)
}
```

- Funções Closure

- Função como parâmetro

---
---

Objetos 

Objetos com funções

Funções construtoras

Objetos Classes
- No JavaScript as classes chegaram de forma tardia e não estavam no projeto inicial da linguágem. Dessa forma, internamente o JS converte todas as classes para funções.

---
---

Arrays

---
---

#### Map Functions

##### Map Functions com uma lista de objetos
```js
function transformarProdutosParaExibicao(produtos) {

  return produtos.map((produto) => {
    // Criamos um objeto novo copiando os dados manualmente
    return {
      id: produto.id,
      titulo: produto.nome.toUpperCase(),
      precoFormatado: `R$ ${produto.preco.toFixed(2)}`.replace(".", ","),
      destaque: produto.preco > 200,
      slug: produto.nome.toLowerCase().replaceAll(" ", "-")
    };
  });
}


const entrada = [
  { id: 1, nome: "Mouse Gamer", preco: 89.90, categoria: "perifericos" },
  { id: 2, nome: "Monitor Ultrawide 29", preco: 1299.00, categoria: "monitores" }
];

const resultado = transformarProdutosParaExibicao(entrada);
```