
---

>[!tip] ### **Condicionais in C++**

---
#### ***if***

>[!quote] **Def**
>**`if`:** Executa um bloco de código **apenas se** uma condição especificada for verdadeira.
###### _**Exemplo:**_

```
if (condição) {
    // Código a ser executado se a condição for verdadeira
}
```

---
#### ***else if***

>[!quote] **Def**
>**`else if`:** Usado em conjunto com `if` para verificar **múltiplas condições** em sequência. Se a condição do `if` for falsa, verifica a condição do `else if`. Pode haver múltiplos `else if`.
###### _**Exemplo:**_

```
if (condição1) {
    // Código se condição1 for verdadeira
} else if (condição2) {
    // Código se condição1 for falsa E condição2 for verdadeira
} else {
	// Caso contrário é executado 
}
```

---
#### ***switch-case***

>[!quote] **Def**
>**`switch`:** Seleciona um bloco de código para executar com base no valor de uma **variável**. É uma alternativa mais limpa para múltiplos `else if` quando se compara uma variável com diversos valores constantes.
###### _**Exemplo:**_

```
switch (variavel) {
    case valor1:
        // Código a ser executado se variavel == valor1
        break; // Importante para sair do switch após a execução do caso
    case valor2:
        // Código a ser executado se variavel == valor2
        break;
    default:
        // Código a ser executado se variavel não corresponder a nenhum dos casos anteriores
        break; // O 'default' é opcional, mas recomendado
}
```

---

>[!tip] ### **Loops in C++**

---
#### ***while***

>[!quote] **Def**
>**`while`:** Executa um bloco de código **enquanto** uma condição especificada for verdadeira. É útil quando você não sabe quantas iterações serão necessárias antecipadamente; o loop continua até que a condição se torne falsa.
###### _**Exemplo:**_

```
while (condição) {

    // Código a ser repetido enquanto a condição for verdadeira
    
}
```

---
#### ***do-while***

>[!quote] **Def**
>**`do-while`:** Similar ao `while`, mas garante que o bloco de código seja executado **pelo menos uma vez**, pois a condição é verificada **após** a primeira execução.
###### _**Exemplo:**_

```
do {

    // Código a ser repetido pelo menos uma vez, e depois enquanto a condição for verdadeira
    
} while (condição);
```

---
#### ***for***

>[!quote] **Def**
>**`for`:** Executa um bloco de código um número **específico de vezes**. É ideal quando você sabe de antemão quantas iterações são necessárias. Geralmente usado para iterar sobre sequências ou coleções de dados.
>
>**`inicialização`:** 
>- Executada **apenas uma vez** no início do loop. Geralmente inicializa um contador.
>
>---
>
>**`condição`:** 
>- Verificada **antes de cada iteração**. Se for verdadeira, o loop continua; se for falsa, o loop termina.
>  
>---
>
>**`incremento`:** 
>- Executado **após cada iteração**. Geralmente incrementa ou decrementa o contador.
###### _**Exemplo:**_

```
for (inicialização; condição; incremento) {

    // Código a ser repetido enquanto a condição for verdadeira
    
}
```

---
#### ***for-each***

>[!quote] **Def**
>Introduzido no C++11, o _range-based for loop_, frequentemente chamado de `foreach` por sua semelhança com construções em outras linguagens, simplifica a iteração sobre elementos de **sequências, contêineres** (como `std::vector`, `std::array`, etc.), e **outros intervalos**. Ele abstrai a complexidade da iteração manual com iteradores, tornando o código mais limpo e legível ao percorrer todos os elementos de uma coleção.

>[!quote] **Def**
>**`declaração_de_intervalo`:** 
>- Declara uma variável que receberá o valor de cada elemento da sequência em cada iteração do loop. Você pode usar `auto` para deixar o compilador inferir o tipo, ou especificar o tipo explicitamente (ex: `int`, `tipo_do_elemento&`, `const tipo_do_elemento&`).
>
>---
>
>**`expressão_de_intervalo`:** 
>- Representa a sequência, contêiner, array ou qualquer objeto que define um intervalo sobre o qual se deseja iterar. Exemplos incluem um `std::vector`, um array C-style, uma string, ou qualquer tipo que suporte iteração com iteradores begin() e end().
>  
###### _**Exemplo:**_

```
for (inicialização; condição; incremento) {

    // Código a ser repetido enquanto a condição for verdadeira
    
}
```
###### _**Exemplo Prático:**_

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numeros = {1, 2, 3, 4, 5};

    // Usando foreach (range-based for loop) para iterar sobre o vetor
    for (int numero : numeros) {
        std::cout << "Número: " << numero << std::endl;
    }

    std::cout << "\nIterando com auto (inferência de tipo):" << std::endl;
    for (auto num : numeros) { // 'auto' infere o tipo como int
        std::cout << "Número: " << num << std::endl;
    }

    std::cout << "\nIterando com referência para modificar elementos (cuidado!):" << std::endl;
    for (int& num_ref : numeros) { // 'int&' para obter uma referência a cada elemento
        num_ref *= 2; // Dobrando o valor de cada elemento no vetor original
    }
    for (const auto& num_const_ref : numeros) { // 'const auto&' para leitura eficiente sem modificação
        std::cout << "Número (modificado): " << num_const_ref << std::endl;
    }

    return 0;
}
```

---
