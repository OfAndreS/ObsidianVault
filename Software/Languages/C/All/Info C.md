
---
## **C o que é?**

>[!quote] Definição
>
>A linguagem de programação C é descrita como a linguagem mãe. Isso porque diversas outras linguagens utilizadas hoje, como: 
>- [PHP](https://www.alura.com.br/artigos/php-uma-introducao-linguagem) 
>- [Java](https://www.alura.com.br/artigos/java)
>- [C#](https://www.alura.com.br/artigos/csharp-linguagem-programacao-dotnet) 
>- **C++** 
>  
>Surgiram utilizando C como base.
>
>Ela foi criada em 1972 por Dennis Ritchie, com um dos objetivos de criar sistemas operacionais.

>[!quote] **Para Saber Mais:** [As linguagens C e C++](https://www.alura.com.br/artigos/linguagens-c-c-qual-diferenca-entre-elas#programacao-orientada-a-objetos-(poo))

---
#### **Arquivo em C no VS**

>[!quote] Explicação
>**Instalar as Extensões Necessárias:**
>- **C/C++:** Esta extensão fornece suporte básico para a linguagem C/C++, como destaque de sintaxe e autocompletar.
>
>**Criar um Novo Arquivo:**
>- Abra o Visual Studio Code
>- Vá para o menu **Arquivo** > **Novo Arquivo**
>- Salve o arquivo com a extensão `.c` | por exemplo: `meu_programa.c`
>- Importe a biblioteca `<stdio.h>`

```cpp
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
##### *Estrutura*

>[!quote] Estrutura
>**Parte 01)**
>- O arquivo começa com alguns comentários que descrevem o propósito do módulo e informação adicio nal, como nome do autor e data e nome do arquivo. Os comentários começam com /* e terminam com */.
>  
>**Parte 02)**
> - Ordens ao pré-processador, conhecidas como diretivas do pré-processador. Normalmente, incluem arquivos de cabeçalho e definição de constantes.
>
>**Parte 03)**
>- Declarações de variáveis e funções visíveis em todo o arquivo. Em outras palavras, os nomes dessas variáveis e funções podem ser utilizados em qualquer função desse arquivo. 
>- Caso se deseje limitar a visibilidade das variáveis e funções somente a esse módulo, deve ser colocado diante de seus nomes o prefixo `static;` caso contrário, a palavra reservada `extern` indica que os elementos são declarados e definidos em outro arquivo.
>
>**Parte 04)**
>- O resto do arquivo inclui definições das funções (seu corpo). Dentro de um corpo de uma função, podem ser definidas variáveis que são locais à função e que somente existem no código da função que se está executando.

![[Pasted image 20240908115859.png]]

---
#### **Aplicações:**

>[!quote]
>**Sistemas Operacionais:** 
>- O C é a linguagem predominante para o desenvolvimento de sistemas operacionais, como Linux e Unix.
>
>**Software Embarcado:** 
>- O C é amplamente utilizado em dispositivos embarcados, como microcontroladores e sistemas de controle industrial.
>  
>**Jogos:** 
>- O C é utilizado em muitos motores de jogos para criar jogos de alto desempenho.
>  
>**Aplicações Científicas:** 
>- O C é utilizado em diversas áreas da ciência para desenvolver software de simulação e análise de dados.
>  
>**Compiladores:** 
>- Muitos compiladores são escritos em C, devido à sua eficiência e capacidade de gerar código otimizado.

---
#### **Especificações**

##### *Linguagem de Médio Nível*

> [!note] Médio Nível
> O C oferece um bom equilíbrio entre a abstração de alto nível e o controle de baixo nível sobre o hardware. Isso significa que você pode escrever código eficiente e otimizado, mas ainda ter acesso a recursos de hardware quando necessário.

##### *Procedural*

> [!note] Procedural
> A estrutura de um programa em C é organizada em funções, que são blocos de código que realizam tarefas específicas. Essa abordagem modular facilita a organização e a reutilização do código.

##### *Tipada Estaticamente*

> [!note] Tipada Estaticamente:
> O tipo de uma variável é definido em tempo de compilação, o que ajuda a prevenir erros comuns de programação e melhora a eficiência do código.
> 
>

##### *Compilada*

> [!note] Compilada
> O código C é traduzido para código de máquina por um compilador, gerando um arquivo executável. Isso resulta em programas mais rápidos e eficientes do que linguagens interpretadas.

##### *Portátil*

> [!note] Portátil
> O C é projetado para ser portátil, o que significa que um programa C pode ser compilado e executado em diferentes plataformas com poucas ou nenhuma modificação.

##### *Ponteiros*

> [!note] Ponteiros
> Ponteiros são uma das características mais poderosas e perigosas do C. Eles permitem manipular a memória diretamente, o que pode levar a bugs difíceis de encontrar se não forem usados com cuidado.

##### *Sintaxe Concisa*

> [!note] Sintaxe Concisa
> A sintaxe do C é relativamente simples e concisa, o que facilita a escrita de código eficiente.

##### *Biblioteca Padrão Rica*

> [!note] Biblioteca padrão rica
> O C possui uma biblioteca padrão que oferece uma variedade de funções para realizar tarefas comuns, como entrada e saída, manipulação de strings e operações matemáticas.

##### *Orientada a Procedimentos*

> [!note] Orientada a procedimentos
> A programação em C é centrada em procedimentos, ou seja, em sequências de instruções que realizam uma tarefa específica.

---
#### **Instalação**

>[!quote] Básicas
>Para utilizar a linguagem C:
>- Artigo: [Compilando e executando programas em C/C++ no Windows | Alura](https://www.alura.com.br/artigos/compilando-executando-programas-c-c-windows?utm_source=gnarus&utm_medium=timeline)
>- Vídeo: [Como Programar em C usando o Visual Studio Code? (youtube.com)](https://www.youtube.com/watch?v=Mook-z2uvpM)

---
#### **Problemas Comuns em C**

>[!quote] Problemas em C
>Erro na compilação dos caracteres especiais:
>- [Corrigindo problemas de caracteres especiais](https://www.youtube.com/watch?v=Zw1KA4u0Fzg)

```cpp
#include <locale.h>

int main() {

    setlocale(LC_ALL, "Portuguese");

}
```

---
