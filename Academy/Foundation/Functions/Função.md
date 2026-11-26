
---
## **O que é uma função:**

> [!quote] Definição
>  Função é uma regra que relaciona cada elemento de um conjunto 
>  - (representado pela variável x)
> 
A um único elemento de outro conjunto 
> - (representado pela variável y). 
>   
>Para cada valor de x, podemos determinar um valor de y, dizemos então que “y está em função de x”.

>[!quote] Definição Formal:
>Se os elementos do domínio e da imagem de uma função pertencem ao conjunto dos números inteiros, por exemplo, dizemos que $f:  →$  lemos que “$f$ é uma função cujo domínio pertence aos inteiros e cuja imagem pertence aos inteiros” ou, simplesmente, “$f$ é uma função de inteiros em inteiros”.
>- Prova de um intervalo da função

---
#### **Funções**

> [!note] 01 - Uma reta no plano cartesiano.
>   **[[Função Linear]]** 

> [!note] 02 - Generalização da função linear, podendo interceptar o eixo y em qualquer ponto
>  **[[Função Afim]]** 

>[!note] 03 - Forma uma parábola quando graficada
> **[[Função Quadrática]]** 

>[!note] 04 - Uma soma de termos com potências inteiras não negativas de uma variável
> **[[Função Polinomial]]** 

> [!note] 05 - Crescimento ou decrescimento muito rápido, com a variável no expoente
>  **[[Função Exponencial]]** 

> [!note] 06 - Inversa da função exponencial, utilizada para resolver equações exponenciais
>  **[[Função Logarítmica]]** 

 > [!note] 07 - Relacionadas a ângulos e lados de triângulos. descrevendo fenômenos periódicos
 >  **[[Funções Trigonométricas]]** 

---
#### **Tipos de Funções**

##### *Função sobrejetora*

 > [!quote] Definição
 > Dizemos que uma função é sobrejetora se todos os elementos do contradomínio pertencem ao conjunto da imagem. 
 > - Isto é, se todos os elementos “recebem uma seta vinda do domínio, ou, simplesmente, se o conjunto da imagem e do contradomínio são iguais.” 
 > 
 > Um mesmo elemento do contradomínio pode receber uma correspondência de mais de um elemento do domínio.

![[Pasted image 20240822114719.png]]

##### *Função Injetora*

 > [!quote] Definição
>É uma função onde cada elemento do domínio é mapeado para um elemento único no contradomínio. Em outras palavras, elementos distintos do domínio sempre terão imagens distintas no contradomínio.
>$$f(x_1)\neq f(x_2)$$

![[Pasted image 20240822115333.png]]

##### *Função Bijetora* 

 > [!quote] Definição 
 > Uma função é bijetora se ela for sobrejetora e injetora simultaneamente
 > 
 > - Se todos os elementos do contradomínio pertencem ao conjunto da imagem e um elemento do contradomínio corresponde a um único elemento do domínio.
 >
 >Prova da Bijetividade de uma função:
 >- Caso seja um Sistema: 

![[Pasted image 20240822115755.png]]

---
##### *Função Simples* 

 > [!quote] Definição  
 > Uma função é dita simples se ela não é injetora nem sobrejetora.

![[Pasted image 20240822120008.png]]

---
#### **Funções Compostas**

 > [!quote] Definição
 > Sejam $f$ : $X$ → $Y$ e $g$ : $U$ → $V$ duas funções, com $Y$ ⊂ $U$. A função composta de $g$ com $f$ é a função denotada por $(g$ ◦ $f)$  com domínio em $X$ e contradomínio em $V$ , que a cada elemento $x$ ∈ $X$ faz corresponder o elemento $v = (g ◦ f) (x) = g(f(x))$ ∈ $V$ Diagramaticamente.
 > - Mais sobre o assunto [[Funções Compostas]]

![[Pasted image 20240822165120.png]]

---
#### **Inverso**

> [!quote] 
> É a função $\mathbf{f}(\mathbf{x})^{-1}$ que faz exatamente o inverso da função $f(x)$. Para que uma função admita uma inversa, ela precisa ser bijetora.
> - Ou seja, injetora e sobrejetora ao mesmo tempo. A lei de formação de uma função inversa faz o contrário do que a função $f(x)$ faz.

> [!error] Exemplo)
> - Se a função pega um valor do domínio e soma 2, 
> - A função inversa ao invés de somar subtrai 2. 
>   
>Encontrar a lei de formação da função inversa nem sempre é uma tarefa fácil, sendo necessário inverter as incógnitas x e y, bem como isolar y na nova equação.

![[Pasted image 20240822233746.png]]


---
#### **Funções Periódicas** 

> [!quote] Uma função f : R → R chama-se periódica quando existe $T ∈ R$
tal que $f(t + T) = f(t)$ para todo $t ∈ R$. Ao menor
número $T > 0$ que faz a propriedade anterior ser satisfeita,
damos o nome de período da função f.


 > [!quote] Simplificação do termo
 > A definição formal pode parecer um pouco complexa, mas a ideia por trás dela é bem intuitiva. Imagine que você está andando em uma esteira. A esteira se move de forma repetitiva, não é? A cada passo que você dá, o padrão da esteira se repete. 
 > Exemplos:
 > - [[Funções Trigonométricas]]

> [!quote] **Periódica:** 
>
 - Uma função é periódica se seus valores se repetem em intervalos regulares.

> [!quote] **$T$:** 
>
 - Esse número representa o intervalo em que a função se repete. É como o comprimento da esteira antes de começar a repetir o padrão.

> [!quote] **$f(t+T) = f(t)$:** 
>
- Essa parte da definição garante que, se você avançar um período (T) a partir de qualquer ponto (t), o valor da função será o mesmo. É como se a esteira estivesse no mesmo lugar após um ciclo completo.
  
![[Pasted image 20240817195109.png]]

---
#### **Funções Ímpares e Pares** 

> [!quote] Funções ímpar par
> Uma função $f : R → R$ é par quando se tem $f(−t) = f(t)$ para
todo $t ∈ R$ Se for o caso de $f(−t) = −f(t)$ para todo $t ∈ R$,
dizemos que f é ímpar.

> [!quote] Simplificação do termo
> Imagine o gráfico de uma função como um desenho em um papel. Se você dobrar o papel ao longo do eixo y (eixo vertical), o gráfico de uma função par vai coincidir com ele mesmo. Já o gráfico de uma função ímpar, quando dobrado ao longo do eixo y, vai ser a imagem espelhada do outro lado do eixo.
> Exemplo: 
> - A função seno é ímpar
> - A função cosseno é par.
##### *Funções Pares*

> [!quote] **Funções Pares**
> **Definição formal:** Uma função $f$ é par se $f(-t) = f(t)$ para todo $t$.
> -  **Interpretação:** Se você trocar o valor de $t$ por $-t$ (ou seja, inverter o sinal de $t$) e calcular o valor da função, o resultado será o mesmo.

> [!error] **Exemplo:** par
> - **Exemplo:** A função $f(x) = x²$ é par, pois $f(-x) = (-x)² = x² = f(x)$.
>   
>O gráfico de uma função par é simétrico em relação ao eixo y.

![[Pasted image 20240817201025.png]]
##### *Função ímpar*

> [!quote] **Funções ímpares**
> **Definição formal:** Uma função $f$ é ímpar se $f(-t) = -f(t)$ para todo $t$.
> -  **Interpretação:** Se você trocar o valor de $t$ por $-t$ e calcular o valor da função, o resultado será o oposto do valor original.

> [!error] **Exemplo:** ímpar
> - **Exemplo:** A função $f(x) = x³$ é ímpar, pois $f(-x) = (-x)³ = -x³ = -f(x)$.
>   
>O gráfico de uma função ímpar é simétrico em relação à origem (0,0).

![[Pasted image 20240817201403.png]]

---
