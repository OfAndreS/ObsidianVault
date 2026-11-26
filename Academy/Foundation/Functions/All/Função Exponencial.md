---

---

---
## **Função Exponencial ou ou de crescimento exponencial** 

>  A função exponencial ocorre quando, em sua lei de formação, a variável está no expoente, com domínio e contradomínio nos números reais. O domínio da função exponencial são os números reais, e o contradomínio são os números reais positivos diferentes de zero. A sua lei de formação pode ser descrita por $f(x) =ax$ em que a é um número real positivo diferente de 1.

---
#### **Inverso da Função Exponencial**

> [!tip] Imagine que você tem uma função exponencial que transforma um número x em um número y. 
> A função inversa dessa exponencial, nesse caso, seria aquela que faz o caminho de volta: transforma o número y de volta em x. Essa função inversa é chamada de **Função Logarítmica**.

**Relação entre as duas:**

> [!quote] **Complementaridade:** 
> As funções exponencial e logarítmica são como duas faces da mesma moeda. Uma "desfaz" o que a outra "faz".

> [!quote] **Gráficos:** 
> Os gráficos dessas duas funções são simétricos em relação à reta y = x. Isso significa que se você espelhar um gráfico em relação a essa reta, obterá o gráfico da outra função.

---
#### **Estrutura** 

**Forma geral:** $f(x)=a^{x}$ onde:

- $a$ é a base (um número real positivo e diferente de 1)
- $x$ é o expoente (a variável independente)

**Base:** A base determina o comportamento da função:
 
- **a > 1:** Função crescente (valores de $f(x)$ aumentam à medida que $x$ aumenta)
- **0 < a < 1:** Função decrescente (valores de $f(x)$ diminuem à medida que $x$ aumenta)

#### **Domínio e Imagem**

- **Domínio:** O conjunto de todos os números reais (ℝ).
- **Imagem:** O conjunto dos números reais positivos (ℝ+). Isso significa que o valor de $f(x)$ sempre será positivo, independentemente do valor de $x$.

#### **Crescimento/Decrescimento**

> [!quote] **Crescimento:** 
> Quando a base $(a)$ é maior que 1, a função cresce rapidamente à medida que x aumenta. Quanto maior o valor de a, mais rápido o crescimento.

> [!quote] **Decrescimento:** 
> Quando a base $(a)$ está entre 0 e 1, a função decresce rapidamente à medida que x aumenta. Quanto mais próximo de 0 for o valor de a, mais rápido o decrescimento.

###### _**Exemplos:**_

Caso: $x > 1$
![[Pasted image 20240806075800.png]]

Caso: $0 < x < 1$ 
![[Pasted image 20240806075557.png]]

---

#### **Propriedades da função exponencial**

> [!tip] **Propriedade 01)**

Em uma função exponencial qualquer, independentemente do valor de sua base a, temos que $f(0) = 1$. Afinal, sabemos que essa é uma propriedade de Potência ou seja, todo número elevado a 0 é 1. Isso significa que o gráfico vai interceptar o eixo vertical no ponto (0,1) sempre.

> [!tip] **Propriedade 02)**

A função exponencial é injetora. Dados $x1$ e $x2$ tal que $x1 ≠ x2$ então as imagens também serão diferentes, ou seja, $f(x1) ≠ f(x2)$ o que significa que, para cada valor da imagem, existe um único valor no domínio que corresponde a essa imagem.

Ser injetiva significa que, para valores diferentes de $y$, existirá um único valor de x que faz com que $f(x)$ seja igual a $y$

> [!tip] **Propriedade 03)**

É possível saber o comportamento da função de acordo com o valor da sua base. O gráfico será crescente se a base for maior que 1 (a > 1) e decrescente se a base for menor que 1 e menor que 0 (0 < a < 1).

> [!tip] **Propriedade 04)**

O gráfico da função exponencial está sempre no 1º e 2º quadrantes, pois o contradomínio da função são os reais positivos diferentes de zero.

---
#### **Como Montar uma Função Exponencial**

> [!tip] O que é uma função exponencial
> Basicamente, ela descreve situações onde uma quantidade cresce ou decresce a uma taxa proporcional ao seu valor atual. A forma geral de uma função exponencial é:

$$f(x) = a * b^x$$
**Passos para Montar a Função**

> [!quote] **Identifique o valor inicial:** 
> Qual é o valor da quantidade no início do processo? Esse valor será o "a" na sua equação.

> [!quote] **Determine a taxa de crescimento ou decaimento:** 
> Em que proporção a quantidade aumenta ou diminui a cada período? Essa informação te ajudará a encontrar o valor de "b".

> [!quote] **Escolha a variável independente:** 
> Qual é a quantidade que está variando e que você vai usar como "x" na sua equação?

> [!quote] **Monte a equação:** 
> Substitua os valores encontrados nos passos anteriores na forma geral da função exponencial.

**Exemplo: Crescimento Populacional**

Imagine uma cidade que tem 10.000 habitantes e cresce a uma taxa de 2% ao ano. Queremos encontrar uma função que descreva a população da cidade ao longo dos anos.

> [!error] Montando a Expressão:
> **Valor inicial (a):** 10.000 habitantes
> 
> **Taxa de crescimento:** 2% ao ano, ou seja, a cada ano a população aumenta em 102% (100% + 2%). Então, b = 1,02.
> 
>  **Taxa de crescimento:** 2% ao ano, ou seja, a cada ano a população aumenta em 102% (100% + 2%). Então, b = 1,02.
>  
>  $$f(x) = 10.000 * 1.02^x$$

**Exemplo: Desvalorização de um carro**

Um carro é comprado por R$ 50.000,00 e desvaloriza 10% ao ano. Qual a função que descreve o valor do carro após x anos?

>[!error] Montando a Expressão:
>**Valor inicial (a):** R$ 50.000,00
>
>**Taxa de decaimento:** 10% ao ano, ou seja, a cada ano o valor diminui para 90% (100% - 10%). Então, b = 0,9.
>
>**Variável independente (x):** O tempo em anos.
>
>$$f(x) = 50000 * 0.9^x$$
