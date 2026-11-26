
---
## **Notação Base**

>[!quote] Notação
>A notação em uma linguagem de programação é o conjunto de regras e símbolos utilizados para escrever instruções que um computador possa entender e executar. É como a gramática de uma língua, definindo a estrutura e o significado das palavras (palavras-chave), frases (comandos) e textos (programas).
>

>[!quote] **Para Saber Mais:** [Manual de sintaxe C](https://www.feg.unesp.br/Home/PaginasPessoais/profmarcosapereira3168/programacaodecomputadoresi/manual-de-sintaxe-da-linguagem-c.pdf)
##### *Imprimir um dado*

```C

printf()

```
##### *Fazer um comentário*

```
\\ 

/* */
```
##### *Ler um dado*

```C

scanf("%d", &testeVariavel)

```

>[!quote] Explicação:
>Para realizar um input em C é necessário declarar o tipo de dado esperado. Neste exemplo `%d` que representa os números inteiros. Além de ser preciso declarar a variável em que esse dado vai ser armazenado,  tendo um `&` antes da mesma.
##### *Concatenação em C*

```
int numeroDoTeste;
int senha;
printf("Número do teste: %d. Senha do teste: %d , numeroDoTeste, senha);
```

> [!quote] Explicação:
> Sendo o `%d` a um inteiro. Após finalizar a string é necessário declarar esse inteiro / variável.
> - Cada tipo de variável tendo sua respectiva sigla.
##### *Variáveis constantes ou Const*

```

const int x5 = 100;


```

>[!quote] Explicação:
>A palavra reservada `const` pode ser situada antes de uma declaração de tipo para indicar ao compilador que não se pode modificar o valor

---
#### **Escopo em C**

>[!quote] Definição
>Escopo de uma variável são "os lugares onde podemos usá-la". Sempre que declaramos uma variável, podemos usá-la em qualquer lugar dentro das "chaves" que ela está, e nas "chaves" de dentro (por exemplo, se temos um `if`).
##### *Escopo Geral*

```C
int main() {
  int variavel;

  //  posso usar ela aqui
  variavel = variavel + 1;

 if(ALGUMA CONDICAO) {
    // posso usar aqui também
    variavel = variavel + 1;
}

}

```
##### *Escopo Limitado*

```C
int main() {
 if(ALGUMA CONDICAO) {

    int variavel = 1;

    // posso usar aqui
    variavel = variavel + 1;
  }

  // aqui nao posso usar, porq
  ue ela nao existe aqui
  variavel = variavel + 1; // nao funciona

}
```

---
