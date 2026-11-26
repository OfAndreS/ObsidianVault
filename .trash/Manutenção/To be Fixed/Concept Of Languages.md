
---
#### **Biblioteca**

>[!quote] O que é?
>**Uma biblioteca na programação é como uma caixa de ferramentas para desenvolvedores.**
>
> Imagine que você está construindo uma casa: 
> - você não precisa criar cada prego, cada tijolo ou cada ferramenta do zero. Você compra esses materiais prontos em uma loja de construção. 
>   
>Da mesma forma, uma biblioteca em programação fornece um conjunto de códigos pré-escritos e organizados que podem ser reutilizados em diferentes projetos.

>[!quote] Termos mais técnicos
>Uma biblioteca é uma coleção de subprogramas (funções, classes, etc.) que oferecem funcionalidades específicas. Esses subprogramas podem ser usados por outros programas para realizar tarefas comuns, como:
>
>**Manipulação de dados:** 
>- Leitura e escrita de arquivos, formatação de texto, etc.
>  
>**Cálculos matemáticos:** 
>- Operações complexas, estatística, trigonometria, etc.
>
>**Interação com o sistema:** 
>- Acesso ao sistema operacional, criação de interfaces gráficas, etc.
>  
>**Comunicação:** 
>- Envio e recebimento de dados pela rede, acesso a bancos de dados, etc.

---
#### **Operadores**

>[!quote] Operadores de
>Aritméticos

![[Pasted image 20240908155517.png]]

>[!quote] Operadores 
>Relacionais

![[Pasted image 20240908155644.png]]

>[!quote] Operadores 
>Matemáticos

![[Pasted image 20240908160141.png]]

---
#### **Loops**

>[!quote] Quando usar Loops
>**for:** 
>- Quando sabemos o número exato de iterações.
>
>**while:** 
>- Quando a condição de parada depende de um cálculo ou de uma entrada do usuário.
>  
>**do-while:** 
>- Quando queremos garantir que o bloco de código seja executado pelo menos uma vez.
>  
>**foreach:** 
>- Para percorrer elementos de um array ou lista de forma mais concisa.

---
#### **Else If** 

>[!quote] Definição
>Quando executado um código utilizando a definição `else if` é permitido criar uma série de condições em cadeia onde quando a primeira for verdadeira o código termina sua execução.

``` C
if (condição1) { 
// Código a ser executado se condição1 for verdadeira 
} 
else if (condição2) { 
// Código a ser executado se condição1 for falsa e condição2 for verdadeira 
} 
else if (condição3) { 
// Código a ser executado se condição1 e condição2 forem falsas e condição3 for verdadeira 
} 
else { 
// Código a ser executado se nenhuma das condições anteriores for verdadeira 
}
```

---
#### **Arrays vs Listas**

>[!quote] Qual a Diferença?
>**Arrays** e **listas** são estruturas de dados utilizadas para armazenar coleções de elementos. Embora ambas sirvam a esse propósito, possuem características e aplicações distintas.

![[Pasted image 20240917105844.png]]
##### *Arrays*

>[!quote] Especificações
>**Tamanho fixo:** 
>- A quantidade de elementos em um array é definida no momento de sua criação e não pode ser alterada posteriormente.
>  
>**Acesso direto:** 
>- Cada elemento de um array possui um índice numérico que permite o acesso direto a ele. Isso torna a busca por elementos muito eficiente.
>  
>**Tipo de dados homogêneo:** 
>- Geralmente, os elementos de um array devem ser do mesmo tipo de dado (por exemplo, todos inteiros ou todos strings).
>  
>**Alocação contígua na memória:** 
>- Os elementos de um array são armazenados em posições de memória consecutivas, o que otimiza o acesso.

>[!quote] Quando se usa um Array?
>- Quando você sabe exatamente quantos elementos precisará armazenar e essa quantidade não vai mudar.
> - Quando o acesso rápido a elementos por índice é fundamental para sua aplicação.
> - Quando a homogeneidade dos dados é importante.
##### *Listas*

>[!quote] Especificações 
>**Tamanho dinâmico:** 
>- Listas podem crescer ou diminuir de tamanho durante a execução do programa.
>  
>**Acesso por índice:** 
>- Assim como arrays, os elementos de uma lista podem ser acessados por índice.
>  
>**Tipos de dados heterogêneos:** 
>- Geralmente, as listas podem armazenar elementos de diferentes tipos de dados.
>  
>**Alocação não necessariamente contígua:** 
>- Os elementos de uma lista podem estar dispersos na memória, o que pode levar a um desempenho ligeiramente inferior em algumas operações.

>[!quote] Quando usar listas?
>- Quando você não sabe de antemão quantos elementos precisará armazenar.
>- Quando a flexibilidade para adicionar ou remover elementos é importante.
>- Quando você precisa armazenar dados de diferentes tipos.

---
#### **Char vs String**

>[!quote] Qual a diferença?
>**Char** e **String** são tipos de dados utilizados para representar texto em programação, mas possuem características distintas:

![[Pasted image 20240917165555.png]]
##### *Char*

>[!quote] Especificação
>**Um único caractere:** 
>- Representa apenas um único caractere, como uma letra, um número ou um símbolo.
>  
>**Tipo de dado primitivo:** 
>- Geralmente é considerado um tipo de dado primitivo em muitas linguagens de programação, o que significa que ele representa um valor diretamente, sem ser um objeto.
>  
>**Tamanho fixo:** 
>- Ocupa uma quantidade fixa de memória para armazenar um único caractere.

```
java

char letra = 'a';
```
##### *String*

>[!quote] Especificação
>**Sequência de caracteres:** 
>- Representa uma sequência de zero ou mais caracteres. Uma string é, basicamente, um conjunto de chars.
>  
>**Tipo de dado composto:** 
>- É considerado um tipo de dado composto ou objeto em muitas linguagens, o que significa que possui propriedades e métodos associados.
>
>**Tamanho variável:** 
>- Pode armazenar um número variável de caracteres, desde uma string vazia até uma string muito longa.

```
java

String palavra = "Olá, mundo!";
```

---
