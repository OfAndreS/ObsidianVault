
---
## **Tipagem**

>[!quote] O que é Tipagem?
>Um dos aspectos mais fundamentais em uma linguagem de programação é saber com quais tipos de dados ela trabalha e como manipulá-los utilizando variáveis.
>- Podemos definir tipos como valores que são manipulados por um programa. São os blocos básicos e principais que usamos para programar. Afinal de contas, a programação é basicamente processar dados e, para fazer isso, o programa precisa saber qual é o tipo de dado que será processado.

>[!note] Resumo
>Na **tipagem estática**: 
>- O tipo é inferido pela variável e a checagem (_type checking_) é feita durante a compilação;
>
>Na **tipagem dinâmica**: 
>- O tipo é inferido pelo valor do dado e a checagem (_type checking_) é feita em tempo de execução (_runtime_);
>  
>**Performance**:
>- Linguagens estaticamente tipadas têm uma performance de execução melhor: 
>- Pois durante a execução o código já foi “traduzido” para linguagem máquina e a checagem/tipagem das variáveis já foi feito;
>- Por outro lado, linguagens dinamicamente tipadas costumam ser mais ágeis durante o desenvolvimento e também são mais flexíveis.

>[!quote] **Para Saber Mais:** [O que são as Tipagens ](https://www.alura.com.br/artigos/o-que-sao-as-tipagens-estatica-e-dinamica-em-programacao)
##### *Principais tipos de dados*

> [!quote] **INT**
> É um número inteiro: valores numéricos inteiros. Positivos ou negativos $\text{Z}$

>[!quote] **FLOAT**
> São os números racionais. Ou chamado “ponto flutuante”: valores numéricos com casas após a vírgula positivos ou negativos ℚ

>[!quote] **BOOLEAN**
>Booleanos: são representado apenas por dois valores, “verdadeiro” e “falso”. Também chamados de operadores lógicos

>[!quote] **TEXT**
>Sequências ou cadeias de caracteres, utilizados para manipular textos e/ou outros tipos de dados não numéricos ou booleanos, como hashes de criptografia.

> [!error] Exemplo
> **JavaScript** 
> - Tem como tipos primitivos embutidos na estrutura básica da linguagem 
>   
>   Sendo elas: _number_, _string_, _boolean_ e _symbol_ (de “nome simbólico”, usado entre outras coisas para criar propriedades únicas em objetos). 
>   
> **C#**  
> - Tem uma quantidade maior de tipos primitivos, de acordo com o espaço de memória que será ocupado pela variável
>   
>   Sejam elas: _Boolean_, _Byte_, _SByte_, _Int16_, _UInt16_, _Int32_, _UInt32_, _Int64_, _UInt64_, _IntPtr_ _UIntPtr_, _Char_, _Double_ e _Single_. 
>   
>Além dos primitivos, existem outros tipos estruturados, como _funções_, _arrays_, _objetos_ e suas variações também dependem da linguagem.

---
## **Linguagens estaticamente Tipadas**

>[!quote] Utilização
>Exemplos de linguagens estaticamente tipadas são **C**, **C++**, **Java**. **Go** e **Rust**. Linguagens como **Java, C e C++** também são explicitamente tipadas, ou seja, é necessário declarar o tipo ao criar a variável.
##### *Definição*

>[!quote] Definição
>Uma linguagem é definida como _estaticamente tipada_ quando a pessoa que está programando precisa informar explicitamente o tipo de cada dado utilizado no sistema: 
>- variáveis, parâmetros de funções, valores de retorno, etc. 
>  
>Uma vez definido o tipo, estas variáveis estão restritas ao tipo declarado. 
>
>Assim, quem está programando estabelece e declara o tipo de dado que será associado à variável

> [!quote] Verificação
> A checagem (_type checking_) é [feita na compilação do programa](https://www.alura.com.br/artigos/o-que-e-compilacao) ou em tempo de execução (_runtime_), dependendo se a linguagem for compilada ou interpretada.

>[!error] Exemplo em C#
>Foram declaradas três variáveis, cada uma com um tipo de dado diferente:
>-  `String` para o texto 
>- `Int32` para um número inteiro de 32 bits e 
>- `bool` para um tipo booleano (no caso, `true`). 
>  
>Uma vez definido, o tipo de dado na variável não pode mais ser modificado; variáveis declaradas como `string`, por exemplo, só poderão receber dados desse tipo.

```C#
String mensagem = "Alura"; 
Int32 numero = 100; 
bool status = true;
```

---
## **Linguagens dinamicamente Tipadas**

>[!quote] Definição
>Nestes casos, o programa observa qual é o tipo de cada dado que está sendo declarado do código e, a partir disso, determina a tipagem. 
>- A sintaxe não exige que se informe explicitamente o tipo quando definimos variáveis; em algumas linguagens é possível informar explicitamente o tipo de dado, mas não é obrigatório.

>[!error] Exemplo em JS
>Na função abaixo não há nenhuma indicação de tipo.
>
>O tipo, que será recebido pelos parâmetros da função, será definido durante a execução do programa. A mesma função pode, pelo exemplo acima, receber tanto dados do tipo 
>- `int` (números inteiros)  
>  - `float` (números de ponto flutuante).

```js
function soma(a, b) { 
return a + b; }
```

---
## **Tipagem _Forte_ & _Fraca_**

>[!quote] Definição
>Além de utilizarem abordagens diferentes para a checagem de tipos, as linguagens também podem ter comportamentos diferentes quando o programa executa operações com tipos de dados não-esperados. 
##### _Forte_

>[!error] Exemplo em Python
>Uma tentativa de operação de soma entre string e número resulta justamente em um _type error_, ou seja, um erro de tipo: 
>- "não é possível concatenar objetos `str` e `int`".

``` python
num = "10" 
operacao = num + 10; //TypeError: cannot concatenate ‘str’ and ‘int’ objects
```
##### *Fraca*

> [!error] Exemplo em JS
> O programa não gerou erros, pois o JavaScript fez uma **conversão implícita** do valor `10` de número para string, para então concatenar com a string `”10”`. Essa é uma característica de linguagens com tipagem “fraca”, como o JavaScript e o [PHP](https://www.alura.com.br/artigos/php-uma-introducao-linguagem).

```js
const num = "10"; 
const operacao = num + 10; //1010
```

---

>[!quote] Vale salientar que
>É interessante notar, também, que linguagens com tipagem dinâmica não têm necessariamente tipagem fraca, como vimos acima com Python.

>[!error]
>Exemplos de linguagens com tipagem dinâmica e forte: 
>- Python, Ruby, Erlang, Clojure 
>  
>Exemplos de linguagens com tipagem dinâmica e fraca: 
>- JavaScript, PHP, Perl
>  
>Exemplos de linguagens com tipagem estática e forte: 
>- C#, Java, Scala
>  
>Exemplos de linguagens com tipagem estática e fraca:
>- C, C++

---
