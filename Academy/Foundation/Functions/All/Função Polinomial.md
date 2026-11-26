
## **Polinômios ou Função Polinomial**

> Conhecemos como polinômio uma expressão que indica a soma algébrica de monômios que não sejam semelhantes, ou seja, polinômio é uma expressão algébrica entre monômios. Monômio é um termo algébrico que possui coeficiente e parte literal.


#### **O que são monômios?**

> [!tip] Para compreender-se o que é um polinômio, é importante que se compreenda antes o significado de um monômio. 
> Uma expressão algébrica é conhecida como monômio quando ela possui números e letras e seus expoentes separados apenas por multiplicação. O número é conhecido como coeficiente, e as letras e seus expoentes são conhecidos como parte literal.

###### ***Exemplos:***

- $2x² → 2$ é o coeficiente; $x²$ é a parte literal.
- $√5ax → √5$ é o coeficiente; $ax$ é a parte literal.
- $b³yz² → 1$ é o coeficiente; $b³yz²$ é a parte literal.

#### **O que é um polinômio?**

> [!tip] Um polinômio nada mais é que a soma algébrica de monômios, ou seja, são mais monômios separados por adição ou subtração entre si.

###### ***Exemplos:***

- $ax² + by + 3$
- $5c³d – 4ab + 3c²$
- $2ab + b – 3xa$

De forma geral, um polinômio pode ter vários termos, ele é representado algebricamente por:

$$a_nx^n+a_{(n-1)}x^{(n-1)}+...+a_2x^2+a_1x+a$$

#### **Grau de um polinômio**

> [!tip] Para encontrar o grau do polinômio 
> Vamos separar em dois casos, quando ele possui uma única variável e quando ele possui mais variáveis. O grau do polinômio é dado pelo grau do maior de seus monômios nos dois casos.

***Polinômio que possui somente uma variável***

Quando isso ocorre, o monômio de maior grau que indica o grau do polinômio é igual ao maior expoente da variável

$a) 2x² – 3x³ + 5x – 4$ 
Note que a variável é x, e o maior expoente que ela tem é 3, então, esse é um polinômio de grau 3.

$b) 2y5 + 4y² – 2y + 8$
A variável é y, e o maior expoente é 5, então, esse é um polinômio de grau 5.

>[!tip] Quando o polinômio possui mais de uma variável em um monômio 
>Para encontrar-se o grau desse termo, é necessário somar-se o grau os expoentes de cada uma das variáveis. Sendo assim, o grau do polinômio, nesse caso, continua sendo igual ao grau do maior monômio, mas é necessário ter-se o cuidado de realizar a soma dos expoentes das variáveis de cada monômio.

$a) 2xy + 4x²y³ – 5y4$ - Analisando os monômios da parte literal temos que o grau é composto por:

- $xy$ → grau 2 = ( 1 + 1)
- $x²y³$ → grau 5 = (2 + 3)
- $y³$  → grau 3 = ( 3 + 0)

Note que o maior termo tem grau 5. Logo $x²y³$ → 5º é o grau do polinômio. 

#### **Fatoração Polinomial**

> [!note] Fatoração do polinômio $2x^2+8x+3x+12$ 
> Primeiro, perceba que não existe nenhum fator comum a todos os termos em $2x^2+8x+3x+12$ Entretanto, se agruparmos os dois primeiros termos e os dois últimos termos, cada grupo terá seu próprio MDC, ou **máximo divisor comum**:

Logo, podemos agrupa-los em dois pares que possuem divisores comuns: 

$$\underbrace{(2x^2+8x)}_{\text{primeiro agrupamento}}+\underbrace{(3x+12)}_{\text{segundo agrupamento}}$$
Em particular, há um MDC de $2x$ no primeiro agrupamento e um MDC de $3$ no segundo agrupamento. Podemos colocá-los em evidência para obter a seguinte expressão:

$$2x(x+4)+3(x+4)$$

Perceba que isso revela ainda outro fator comum entre os dois termos: $x+4$. Podemos usar a propriedade distributiva para fatorar esse fator comum.

$$2x(x+4)+3(x+4)=(x+4)(2x+3)$$

Como o polinômio agora é expresso como um produto de dois binômios, ele está na forma fatorada. 

**Sendo sua forma final:** $(x+4)(2x+3)$

#### **Fatoração Polinomial de 2 grau**

> Esta fatoração, implica nas Função Quadrática ou de 2 grau. Desta forma, veremos como fatorar um polinômio na forma $x^2+bx+c$ como um produto de dois binômios.

> [!note] Para fatorar uma função entre dois binômios 
> precisamos encontrar dois números cujo sua soma seja correspondente ao ( $b$ ) da função e sua multiplicação seja correspondente ao ( $c$ ) da função quadrática. 

###### ***Exemplos:***

Fatoração da Função: $x^2+5x+6$ 

Para fatorar $x^2+5x+6$ precisamos primeiro encontrar dois números cujo produto seja 6 (a constante) e cuja soma seja 5 (o coeficiente de $x$).

Podemos criar uma lista de todos os números cujo produto é 6. Então, dentro dessa lista, procuramos aqueles cuja soma é 5.

$$\begin{aligned}
&\text{Produto: }m\cdot n=6&& \text{Soma: }m+n \\
&1\cdot6=6&& 1+6=7 \\
&2\cdot3=6&& 2+3=5 \\
&(-1)\cdot(-6)=6&& (-1)+(-6)=-7 \\
&(-2)\cdot(-3)=6&& (-2)+(-3)=-5 
\end{aligned}$$

Podemos então somar cada um destes números a $x$ para formar os dois fatores binomiais:

$$(x+2)(x+3)$$

Concluindo, fatoramos o trinômio assim:

$$x^2+5x+6=(x+2)(x+3)$$

#### **Fatoração Polinomial de 2 grau caso o $a$ da função não seja 1**

**Link:** [Coeficiente principal ≠ 1 ](https://pt.khanacademy.org/math/algebra/x2f8bb11595b61c86:quadratics-multiplying-factoring/x2f8bb11595b61c86:factor-quadratics-grouping/a/factoring-quadratics-leading-coefficient-not-1)

#### **Teorema das Raízes Racionais** 

> [!note] **Passo 1: Escrever o polinômio na forma geral**

Considere um polinômio $$p(x)=a_nx^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0$$Onde$$a_n,a_{n-1},\ldots,a_1,a_0$$​São coeficientes inteiros e $a_{n}$​ é o coeficiente do termo de maior grau, enquanto $a_{0}$​ é o termo constante.

> [!note] **Passo 2: Identificar os coeficientes**

Identifique o coeficiente do termo de maior grau $a_{n}$​ e o termo constante $a_{0}$
​
**Obs:** Caso não tenha termo constante
- O polinômio tem 0 como raiz
- É necessário fatorar para prosseguir 

> [!error] _**Exemplo:**_
> 
> $p(x)=x^4-x^3-2x^2+2x.$
> 
> Após fatorar fica: 
> 
> $p(x)=x(x^3-x^2-2x+2)$

> [!note] Passo 3: Determinar os divisores de $a_{0}$​​ e $a_{n}$​

Liste todos os divisores (positivos e negativos) do termo constante $a_{0}$​ e do coeficiente principal $a_{n}$​.

- Os divisores de $a_{0}$ são os possíveis valores de $p$.
- Os divisores de $a_{n}$ são os possíveis valores de $q$

Substitua cada uma das possíveis raízes racionais $\frac{p}{q}$ no polinômio $p(x)$ e verifique se o resultado é zero. Se $p\left(\frac pq\right)=0$ então $\frac{p}{q}$ é uma raiz do polinômio.
  
> [!note] Passo 6: Divisão do polinômio (se necessário)

Se uma raiz $r$ for encontrada, divida o polinômio $p(x)$ por $(x−r)$ para encontrar um polinômio de grau menor. Isso facilita encontrar outras raízes, sejam elas racionais ou irracionais.










