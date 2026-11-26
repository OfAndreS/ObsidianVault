
---
## **Principais Tópicos de Análise Combinatória**

>[!quote] **Princípio Fundamental da Contagem**
>- Multiplique as opções disponíveis para cada escolha para obter o total de combinações possíveis.

>[!quote] **Permutações**
>- Arranjos de todos os elementos de um conjunto onde a ordem importa, calculados pelo fatorial do número total de elementos.
>  
>- Se for uma permutação de $n$ elementos para $n$ lugares é uma permutação.

>[!quote] **Combinações**
>- Seleções de elementos de um conjunto onde a ordem não importa.

>[!quote] **Arranjos**
>- Contagem de maneiras de selecionar e ordenar $k$ elementos de um conjunto de $n$ elementos, onde a ordem importa.

>[!quote] **Binômio de Newton**
>- Expansão de expressões binomiais usando combinações
>  
> - Para saber mais sobre binômios: Função Polinomial 

>[!quote] **Permutações com Repetição**
>- Ajuste das permutações para considerar elementos repetidos, dividindo pelo fatorial das repetições.

>[!quote] **Combinações com Repetição**
>- Seleção de elementos onde cada elemento pode ser escolhido mais de uma vez, usando a fórmula

---
#### **Princípio Fundamental da Contagem**

> [!quote] **Conceito**
> Se um evento pode ocorrer de "$m$" maneiras e outro evento pode ocorrer de "$n$" maneiras, o número total de maneiras pelas quais ambos os eventos podem ocorrer é dado por $m×n$.

> [!error] _**Ex 01)**_ 
> **Quantas combinações de roupas diferentes podemos formar com 3 camisetas e 2 calças?**
> 
>  _Existem 3 maneiras de escolher a camiseta e 2 maneiras de escolher a calça._
>  - Total de combinações: $3×2=6$  maneiras diferentes.
>  
>  **Resumo:** Multiplique o número de opções disponíveis para cada escolha.

---
#### **Permutações**

> [!quote] **Conceito**
> Permutação refere-se ao arranjo de todos os elementos de um conjunto onde a ordem importa.
> 
> **Simples:** Usada quando todos os elementos são distintos.
> - Fórmula: $P(n) = n!$
>
>**Com Repetição:** Usada quando existem elementos repetidos.
>- Fórmula: $P(n;a,b,\ldots)=\frac{n!}{a!b!\ldots}$

> [!error] _**Ex 01)**_ 
> **Quantas maneiras diferentes podemos organizar as letras da palavra "AMOR"?**
> 
> Todas as letras são distintas.
> - $p(4) = 4! = 24$
> 
> **Resumo:** Calcule o fatorial do número total de elementos (ou divida pelo fatorial dos elementos repetidos, se houver).

---
#### **Combinações**

> [!quote] **Conceito**
> Combinação refere-se à seleção de elementos de um conjunto onde a ordem não importa.
> - Fórmula: 
>$$C(n,k)=\frac{n!}{k!(n-k)!}$$
>   
>**Resumo:** Calcule o fatorial do número total de elementos (ou divida pelo fatorial dos elementos repetidos, se houver).

> [!error] _**Ex 01)**_ 
> **De quantas maneiras podemos escolher 3 pessoas de um grupo de 5?**
> 
> - Use a fórmula da combinação. $C(5,3)=\frac{5!}{3!(5-3)!}=\frac{120}{6\times2}=10$
> 
> **Resumo:** Use a fórmula das combinações para calcular o número de subconjuntos possíveis.

---
#### **Arranjos**

> [!quote] **Conceito** 
> Arranjos são usados para contar a quantidade de maneiras de selecionar e ordenar "k" elementos de um conjunto de "n" elementos. Aqui, a ordem importa.
> 
> - Fórmula: $$A(n,k)=\frac{n!}{(n-k)!}$$

> [!error] _**Ex 01)**_ 
> **Quantas maneiras podemos formar um comitê de 3 pessoas a partir de um grupo de 5, considerando a ordem?**
> 
> - Use a fórmula do arranjo: $A(5,3)=\frac{5!}{(5-3)!}=\frac{120}2=60$
> 
> **Resumo:** Calcule o número de arranjos usando a fórmula para considerar a ordem dos elementos.

---
#### **Binômio de Newton**

> [!quote] **Conceito** 
> O Binômio de Newton expande expressões do tipo $(a + b)^n$ 
> - Fórmula: $$(a+b)^n=\sum_{k=0}^nC(n,k)\cdot a^{n-k}\cdot b^k$$
> - Termo Geral: $$\binom npx^{n-p}\cdot a^{p}\quad;\quad p=0,1,2,\cdots,n .$$
> - Passo a passo: **CANVA**

> [!error] _**Ex 01)**_ 
> **Expanda $(x + y)^3$**
>- Aplicando o Binômio de Newton em $(x+y)^3$:
>   $$=C(3,0)x^3y^0+C(3,1)x^2y^1+C(3,2)x^1y^2+C(3,3)x^0y^3$$
>   $$=1x^3+3x^2y+3xy^2+1y^3$$
>   
>**Resumo:** Use a fórmula do Binômio de Newton para expandir binômios.

---
#### **Permutações com Repetição**

> [!quote] **Conceito** 
> Quando existem elementos repetidos, as permutações são ajustadas dividindo-se pelo fatorial dos elementos repetidos.
> - Fórmula: 
>   $$P(n;a,b,\ldots)=\frac{n!}{a!b!\ldots}$$

> [!error] _**Ex 01)**_ 
> **Quantas permutações existem na palavra "MAMA"?**
> - Há 4 letras, onde "M" e "A" se repetem.
>   $$P(4;2,2)=\frac{4!}{2!2!}=\frac{24}4=6$$
>   
>**Resumo:** Aplique a fórmula ajustada para elementos repetidos.

---
### **Combinações com Repetição**

> [!quote] **Conceito** 
> Combinações com repetição permitem selecionar elementos de um conjunto, considerando que alguns podem ser escolhidos mais de uma vez.
> - Fórmula:
>   $$C^{\prime}(n+k-1,k)=\frac{(n+k-1)!}{k!(n-1)!}$$

> [!error] _**Ex 01)**_ 
> **Quantas maneiras diferentes podemos escolher 3 bolas de uma caixa contendo bolas de 4 cores diferentes?**
> - Use a fórmula de combinação com repetição.
>   $$C'(4+3-1,3)=C'(6,3)=\frac{6!}{3!3!}=20$$
>   
>**Resumo:** Utilize a fórmula de combinações com repetição para casos em que elementos podem ser escolhidos mais de uma vez.

---
#### **Combinação Complementar**

> [!quote] Conceito
> - Fórmula: $$\binom{n+k-1}{k-1}$$

---

