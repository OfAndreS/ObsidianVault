
---
## **A Fórmula dos Limites**

>[!quote] Definição
>A fórmula dos limites é um conceito fundamental no cálculo e nos permite analisar o comportamento de uma função à medida que a variável independente se aproxima de um determinado valor.
>$$lim(x→a) f(x) = L$$
>
>**lim** 
>- Abreviação da palavra "limite", indicando que estamos interessados no comportamento da função em um ponto específico.
>  
>**x→a** 
>- Significa que a variável x está se aproximando do valor a. A seta (→) indica a aproximação, e "a" é o valor para o qual x está tendendo.
>
>**f(x)** 
>- É a função que estamos analisando. 
>
>**= L** 
>- Indica que o limite da função f(x), quando x se aproxima de a, é igual a L. O valor L é o limite da função nesse ponto.
> 
>**Khan:** [Limites e continuidade](https://pt.khanacademy.org/math/differential-calculus/dc-limits)
>
>**Calculadora:** [Calculadora de limites](https://pt.symbolab.com/solver/limit-calculator)
##### *Elementos Chave e o que Eles Significam:*

>[!quote] **Função (f(x))** 
>- A regra que associa cada valor de x a um único valor de y.

>[!quote] **Variável Independente (x)** 
>- A entrada da função, o valor que você pode escolher.

>[!quote] **Limite (L)**
>- O valor para o qual a função se aproxima quando x se aproxima de a.

>[!quote] **Ponto de Acumulação (a)** 
>- O valor para o qual x está tendendo.
##### *Tipos de Limites:*

>[!quote] **Limites Laterais** 
>- Quando nos aproximamos de um ponto por valores maiores (limite pela direita) ou menores (limite pela esquerda). [Limites laterais a partir de gráficos](https://pt.khanacademy.org/math/ap-calculus-ab/ab-limits-new/ab-1-3/v/one-sided-limits-from-graphs)

>[!quote] **Limites no Infinito** 
>- Quando x tende a infinito positivo ou negativo.

>[!quote] **Limites Infinitos** 
>- Quando o valor da função cresce ou decresce indefinidamente.
##### *Definição Precisa de Limite*

>[!quote] Definição
>Em termos simples, o limite de uma função em um determinado ponto 
>- É o valor para o qual a função se aproxima quando a entrada (o valor de $x$) se aproxima desse ponto. 
>  
>Como se estivéssemos "observando" o comportamento da função à medida que nos aproximamos de um determinado valor de $x$.
>
>**Quest:** Olhar: Definição Precisa Limite | Pasta EXTRA

>[!quote] **Definição Formal** 
>Dada uma função $f(x)$ dizemos que o limite de $f(x)$ quando $x$ tende a $a$ é $L$ 
>
>$$lim(x→a) f(x) = L$$
>
>Para qualquer número positivo ε (por menor que seja), existe um número positivo δ tal que:
>
>- Se $0 < |x - a| < δ$ Então $|f(x) - L| < ε$.
>  
>O que isso significa?
>- **ε:** Representa uma distância muito pequena em torno do valor $L$
>- **δ:** Representa uma distância muito pequena em torno do valor $a$.
>- **|x - a| < δ:** Significa que x está muito próximo de $a$, mas diferente de $a$.
>- **|f(x) - L| < ε:** Significa que o valor de $f(x)$ está muito próximo de $L$.

>[!quote] **Em resumo:**
>- A definição formal nos diz que podemos tornar f(x) tão próximo de L quanto quisermos (controlando ε), desde que façamos x suficientemente próximo de a (controlando δ).
##### *Indeterminações*

>[!quote] Definição
>Ao calcular limites, podemos encontrar situações em que a substituição direta de x por a resulta em expressões como | $0/0$ | $∞/∞$ | $∞ - ∞$ | etc. Essas são chamadas de indeterminações e requerem técnicas especiais para serem resolvidas, como 
>- Fatoração 
>- Racionalização 
>- Aplicação de regras de L'Hôpital.
>  
>**Atacando indeterminações** [Cálculo: Indeterminação](https://www.youtube.com/watch?v=P4GQORp0g6c&list=PLTPg64KdGgYhACfQUtMf3CuhWOfLoTf_a&index=8)


---

>[!error] **Link Part**

---
#### **Operações básicas**

>[!quote] **Observações**
> **Obs 01)**
>- Essas regras são fundamentais para o cálculo de limites de funções mais complexas.
>  
>**Obs 02)**
>- É importante lembrar que essas regras são válidas desde que os limites individuais das funções existam e o limite do denominador seja diferente de zero no caso do quociente.
>  
>**Obs 03)**
>- Em alguns casos, pode ser necessário usar técnicas como fatoração, racionalização ou substituição para simplificar a expressão antes de aplicar as regras.
>  
##### *Limite da Soma / Diferença*

>[!quote] **Definição**
>**Khan:** [Limites somas e diferenças](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-limit-prop/e/limits-of-combined-functions-sums)
>
>**Regra:** 
>- O limite da soma de duas funções é igual à soma dos limites individuais das funções.
>- O limite da diferença de duas funções é igual à diferença dos limites individuais das funções.
>  
>**Formalmente**:
>
>$$\lim_{x\to c}(f(x)\pm g(x))=L_1\pm L_2$$
>
>

>[!error] *Exemplo Limite da Soma / Diferença*
>Considere: 
>
>$f(x)=2x$ 
>
>$g(x)=3x$. 
>
>Queremos calcular:
>
>$$\lim_{x\to1}\left(f(x)\pm g(x)\right)$$
>
>Aqui, temos:
>
>$$\lim_{x\to1}f(x)=\lim_{x\to1}2x=2\quad\text{e}\quad\lim_{x\to1}g(x)=\lim_{x\to1}3x=3$$
>
>Logo:
>
>$$\lim_{x\to1}\left(2x\pm 3x\right)=2\pm 3$$
>
>Sendo: 
>
>$x_1 = 5$ 
>
>$x_2 = 1$
##### *Limite do Produto*

>[!quote] **Definição**
>**Khan:** [Limites produtos e quocientes](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-limit-prop/e/limits-of-combined-functions-graphs)
>
>**Regra:** 
>- O limite do produto de duas funções é igual ao produto dos limites individuais das funções.
>
>**Formalmente**:
>
>$$\lim_{x\to c}(f(x)\cdot g(x))=L_1\cdot L_2$$

>[!error] *Exemplo Limite do Produto*
>Considere: 
>
>$f(x)=2x$ 
>
>$g(x)=3x$. 
>
>Queremos calcular: 
>
>$$\lim_{x\to1}\left(f(x)\cdot g(x)\right)$$
>
>Aqui, temos:
>
>$$\lim_{x\to1}f(x)=\lim_{x\to1}2x=2\quad\text{e}\quad\lim_{x\to1}g(x)=\lim_{x\to1}3x=3$$
>
>Logo:
>
>$$\lim_{x\to1}(2x\cdot3x)=2\cdot3$$
>
>Sendo:
>
>$x_1 = 6$
##### *Limite do Quociente*

>[!quote] **Definição**
>**Khan:** [Limites produtos e quocientes](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-limit-prop/e/limits-of-combined-functions-graphs)
>
>**Regra:** 
>- O limite do quociente de duas funções é igual ao quociente dos limites individuais das funções, desde que o limite do denominador seja diferente de zero.
>
>**Formalmente**:
>
>$$\lim_{x\to c}\left(\frac{f(x)}{g(x)}\right)=\frac{L_1}{L_2}$$

>[!error] *Exemplo Limite do Quociente*
>Considere: 
>
>$f(x)=2x$ 
>
>$g(x)=3x$. 
>
>Queremos calcular: 
>
>$$\lim_{x\to c}\left(\frac{f(x)}{g(x)}\right)=\frac{L_1}{L_2}$$
>
>Aqui, temos:
>
>$$\lim_{x\to1}f(x)=\lim_{x\to1}2x=2\quad\text{e}\quad\lim_{x\to1}g(x)=\lim_{x\to1}3x=3$$
>
>Logo:
>
>$$\lim_{x\to1}\left(\frac{2x}{3x}\right)=\frac23$$
>
>Sendo:
>
>$x_1 = 2/3$
##### *Limite de uma Potência*

>[!quote] **Definição**
>**Regra:** 
>- O limite de uma função elevada a uma potência é igual ao limite da função elevado à potência.
>
>**Formalmente**:
>
>$$\lim_{x\to c}\left(f(x)^{\frac rs}\right)=\left(\lim_{x\to c}f(x)\right)^{\frac rs}=L^{\frac rs}$$
>
>**Condição:** 
>- $L>0$ é importante porque potências fracionárias podem não ser definidas para números negativos. Sendo $r/s$ um número racional
>

>[!error] *Exemplo Limite da Potência*
>Considere:
>
>$$f(x)=(2x+1)$$
>
>Queremos calcular:
>
>$$\lim_{x\to1}\left(f(x)^{\frac32}\right)$$
>
>Calculamos o limite de $f(x)$ em $x=1$
>
>$$\lim_{x\to1}(2x+1)=2(1)+1=3$$
>
>Agora aplicamos a regra da potência:
>
>$$\lim_{x\to1}\left((2x+1)^{\frac32}\right)=3^{\frac32}=\sqrt{3^3}=\sqrt{27}$$
>
>Sendo:
>
>$x_1 = \sqrt{27}$

##### *Limites por Trigonometria*

>[!quote] **Limite Fundamental Trigonométrico**
>$$\lim_{\theta\to0}\frac{\sin\theta}{\theta}=1$$
>

> [!quote] **Identidades Trigonométricas Fundamentais**
> **Relação Pitagórica:** 
>    $$sen²(θ) + cos²(θ) = 1$$
>   ---
>**Tangente:** 
>   $$tan(θ)= \frac{sen(θ)}{cos(θ)}$$
>  ---
>**Cotangente:** 
>  $$cot(θ) = \frac{cos (θ)}{sen(θ)}$$
>  ---
> **Secante:** 
> $$sec(θ) = \frac{1}{cos(θ)}$$
>  ---
> **Cossecante:** 
> $$cosec( θ ) = \frac{1}{sen(θ)}$$

> [!quote] **Fórmulas de Ângulo Duplo**
> **Seno duplo de θ**
>  $$sen(2θ) = 2senθcosθ$$
>---
>**Cosseno duplo de θ**
>   $$cos(2θ) = cos²θ - sen²θ  (=) 2cos²θ - 1  (=) 1 - 2sen²θ$$

> [!quote] **Fórmulas de Redução de Potência**
>**Redução do Seno**
> $$sen^{2}\theta=\frac{1-\cos\left(2\theta\right)}{2}$$
> ---
> 
> **Redução do Cosseno**
> $$\cos^{2}\theta=\frac{1+\cos\left(2\theta\right)}{2}$$
> 

##### Links
**Watch:** [Limite Fundamental Trigonométrico - Teoria](https://www.youtube.com/watch?v=qurAykEsxio&list=PLTPg64KdGgYhACfQUtMf3CuhWOfLoTf_a&index=15) 
**Watch:** [Limite Fundamental Trigonométrico - Ex](https://www.youtube.com/watch?v=eK52KtZSM28&list=PLTPg64KdGgYhACfQUtMf3CuhWOfLoTf_a&index=14)

---
#
---
#### **Limites por Gráficos**

> [!quote] Definição 
> Há uma importante diferença entre o valor do qual uma função se aproxima—o que chamamos de _limite_—e o valor da função em si. Gráficos são ótimas ferramentas para entender essa diferença. 
> - Uma vez que o valor definido pela função e o gráfico não são os mesmo.
>   
>$$\lim_{x\to a}f(x)=f(a)$$
>  
>Logo, a afirmação acima é falsa.
>
>[Como estimar os valores de limites](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-from-graphs-calc/e/two-sided-limits-from-graphs?classCode=DFS8P8JM) [Como estimar os valores de limites(artigo)](https://pt.khanacademy.org/math/ap-calculus-ab/ab-limits-new/ab-1-3/a/approximating-limit-values-from-a-graph)

>[!quote] **Limites de Funções Compostas**
>
>**Khan:** [Limites de funções compostas](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-limit-prop/e/limits-of-composite-functions--graphs)
##### *Limites Existentes*

>[!quote] **Às vezes o valor do limite é igual ao valor da função**
>- **|**  $f(x)=-1.4$  **|**  $lim g(x) = -1.4$  **|** 

![[Pasted image 20240919121943.png]]

>[!quote] **Mas, às vezes, o valor do limite não é igual ao valor da função.**
>- **|** $f(x) = 2$  **|**  $limg(x) = 4.4$  **|** 

![[Pasted image 20240919122406.png]]

>[!quote] **Aviso**
>**Reforço do conceito-chave:** 
>- O valor da função é irrelevante para determinar o limite. O que realmente importa é descobrir de qual valor está se aproximando conforme nos aproximamos cada vez mais do valor definido.
>
>**Condição de existência**
>- Para existir um limite o valor tem que se aproximar de $x$ dos dois lados. Caso contrário este limite não existe.
##### *Limites Inexistentes*

>[!quote] **Por outro lado, quando a função é definida para algum valor de $x$, isso não significa que o limite necessariamente exista.**
>- **|** $f(x) = 3$ **|** Limite inexistente **|**

![[Pasted image 20240919123612.png]]

---
#
---
#### **Calculo Limites Laterais**

>[!quote] **Lúdico**
>**Imagine uma estrada que leva a uma montanha.** 
>- À medida que você se aproxima do topo, a altitude vai aumentando. Mas e se a estrada se bifurcar antes do topo, criando dois caminhos distintos? Cada caminho levaria a uma altitude diferente no ponto mais próximo do topo.
>  
>**Em cálculo.** 
>- Em vez de uma estrada, temos uma função; em vez do topo da montanha, temos um ponto específico no gráfico da função; e em vez dos dois caminhos, temos duas maneiras de nos aproximar desse ponto: pela esquerda e pela direita.
##### *Definição Formal*

>[!quote] **Bilateral**
>Para o limite Bilateral existir os dois limites laterais obrigatoriamente tem que dar o mesmo valor.
>- Se $f$ não tem um limite bilateral em c, ainda pode ter um limite lateral, ou seja, um limite cuja aproximação ocorre apenas de um lado. Se a aproximação for feita pelo lado direito, o limite será um limite à direita. Se for pelo lado esquerdo, será um limite à esquerda.

>[!quote] **Direita**
>**Limite Lateral à Direita:** 
>- Quando nos aproximamos de um valor "a" por valores maiores que "a" (pela direita no gráfico), dizemos que estamos calculando o limite lateral à direita.
>  
>**Em notação matemática:**
>- Limite lateral à direita de $f(x)$ quando $x$ se aproxima de a: $lim_{(x→a⁺)} f(x)$

>[!quote] **Esquerda**
>**Limite Lateral à Esquerda:** 
>- Quando nos aproximamos de "a" por valores menores que "a" (pela esquerda no gráfico), dizemos que estamos calculando o limite lateral à esquerda.
>  
>**Em notação matemática:**
>- Limite lateral à esquerda de $f(x)$ quando $x$ se aproxima de a: $lim_{(x→a⁻)} f(x)$

>[!error] **Exemplo**
>Imagine a função $f(x) = \frac1x$ Se tentarmos calcular o limite quando $x$ se aproxima de $0$ veremos que:
>
>**Limite lateral à direita:** 
>- Quando $x$ se aproxima de $0$ pela direita (valores positivos muito pequenos), $f(x)$ tende a $+∞$.
>  
>**Limite lateral à esquerda:** 
>- Quando $x$ se aproxima de $0$ pela esquerda (valores negativos muito próximos de $0$), $f(x)$ tende a $-∞$.
>  
>Como os limites laterais são diferentes, o limite geral de $f(x)$ quando $x$ se aproxima de $0$ não existe. Isso indica uma assíntota vertical em $x = 0$.

>[!quote] Khan

- [Limites no infinito de funções racionais (prática) | Khan Academy](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-at-infinity-calc/e/limits-at-infinity-where-x-is-unbounded)
- [Limites no infinito de funções racionais com trigonometria (prática) | Khan Academy](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-at-infinity-calc/e/limits-at-infinity-of-rational-functions-trig)
- [Limites usando identidades trigonométricas (prática) | Khan Academy](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-of-trigonometric-functions-calc/e/find-limits-using-trig-identities?classCode=DFS8P8JM)
- [Limites infinitos: algebricamente (prática) | Khan Academy](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/unbounded-limits-calc/e/limits-at-infinity-where-f-x--is-unbounded?classCode=DFS8P8JM)
---
#
---
#### **Tipos Limites ao Infinito**

>[!quote] **Definição**
>Limites ao infinito referem-se ao comportamento de uma função quando a variável independente se aproxima de valores extremamente grandes (ou pequenos) no eixo dos números reais. Em termos mais simples, estamos interessados em saber como a função se comporta à medida que sua variável tende para o infinito positivo $(+∞)$ ou para o infinito negativo $(-∞)$. 
>**Execução:** [[Limites Infinitos - Calc]]
##### **Principais Pontos dos Limites ao Infinito**

>[!quote] Info
>**Limites** 
>- Ao calcular limites de funções, a direção em que a variável independente se aproxima do infinito influencia o resultado. Por exemplo, o limite de $1/x$ quando $x$ tende a $+∞$ é zero, enquanto o limite quando x tende a $-∞$ também é zero. No entanto, a função se aproxima de zero por valores positivos em um caso e por valores negativos no outro.
>
>**Assíntotas** 
>- As assíntotas, retas que um gráfico se aproxima sem tocar, podem ser horizontais, verticais ou oblíquas. A direção do infinito influencia a posição da assíntota horizontal.
>
**Intervalos** 
>- Ao descrever intervalos, usamos o infinito positivo e negativo para indicar que o intervalo não tem limite superior ou inferior. Por exemplo, o intervalo (2, +∞) inclui todos os números maiores que 2.
>  
>**Exercícios:** [Cálculo: Limites Envolvendo o Infinito)](https://www.youtube.com/watch?v=MKms8CesZn8&list=PLTPg64KdGgYhACfQUtMf3CuhWOfLoTf_a&index=11) 51 - 66
##### *Limite ao Infinito Positivo (+∞) / Negativo (-∞)*

>[!quote] (+∞)
>Examina o comportamento de uma função à medida que a variável independente cresce indefinidamente. Por exemplo
> $$\lim_{x\to+\infty}f(x)$$

>[!quote] (-∞)
>Analisa o comportamento da função quando a variável tende para valores muito negativos. Exemplo:
>$$\lim_{x\to-\infty}f(x)$$
##### **Assíntota Vertical**

>[!quote] Def
>Uma assíntota vertical é uma reta vertical (x = c) que o gráfico de uma função se aproxima indefinidamente quando x se aproxima de um determinado valor c. Isso ocorre quando a função "explode" para cima ou para baixo à medida que x se aproxima de c.
##### *Identificando uma assíntota vertical*

>[!quote] Info
>**Limites laterais**
>- Calcule os limites laterais da função quando x se aproxima de c pela esquerda e pela direita. Se um ou ambos os limites forem infinitos (positivo ou negativo), então x = c é uma assíntota vertical.
>  
>**Denominador:** 
>- Em funções racionais, as assíntotas verticais geralmente ocorrem nos valores de x que anulam o denominador, desde que o numerador não se anule para o mesmo valor de x.

>[!error] *Exemplo*
>A função $f(x) = 1/(x-2)$ tem uma assíntota vertical em $x = 2$. 
>- À medida que x se aproxima de $2$ pela esquerda, $f(x)$ tende a $-∞$. À medida que $x$ se aproxima de $2$ pela direita, $f(x)$ tende a $+∞$.
##### **Assíntota Horizontal**

>[!quote] Def 
>Uma assíntota horizontal é uma reta horizontal (y = b) que o gráfico de uma função se aproxima indefinidamente quando x tende a +∞ ou -∞. Isso significa que os valores da função se aproximam de um número fixo b quando x se torna muito grande (positivo ou negativo).
##### *Como identificar uma assíntota horizontal*

>[!quote] Info
>**Limites no infinito:** 
>  - Calcule os limites da função quando x tende a +∞ e -∞. Se ambos os limites existirem e forem iguais a um número b, então y = b é uma assíntota horizontal.
>  
>  **Graus do numerador e denominador:** 
>  - Em funções racionais, a existência e o valor da assíntota horizontal dependem do grau do polinômio do numerador e do denominador.

>[!error] *Exemplo*
>A função $f(x) = (2x+1)/(x-3)$ tem uma assíntota horizontal em $y = 2$. 
>- Quando $x$ tende a $+∞$ ou $-∞$, o termo dominante no numerador e no denominador é $x$. Dividindo ambos por $x$, obtemos $f(x) ≈ 2$ quando $x$ é muito grande em valor absoluto.

---
#
---
#### **Calculando Continuidade**

>[!quote] **Definição**
>As leis de continuidade descrevem as operações básicas com funções contínuas. Se temos funções $f(x)$e $g(x)$ que são contínuas em um ponto $a$, então as operações como soma, subtração, multiplicação e divisão (desde que o denominador não seja zero) também produzem funções contínuas em $a$. Isso significa que, ao combinar funções contínuas, a continuidade é preservada, permitindo manipulações mais flexíveis ao resolver problemas.
>
###### **Links:**

**Khan** 
1. [Tipos de descontinuidades](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-discontinuities/v/types-of-discontinuities)
2. [Continuidade em um ponto](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-point-continuity/v/continuity-at-a-point)
3. [Continuidade em um intervalo](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-interval-continuity/v/continuity-over-an-interval)
4. [Remoção de descontinuidades por fatoração](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-removing-discontinuity/v/defining-a-function-at-a-point-to-make-it-continuous)

**Aulas:**
1. [Cálculo: Continuidade em um Ponto](https://www.youtube.com/watch?v=iiOrtGZVqnk&list=PLTPg64KdGgYhACfQUtMf3CuhWOfLoTf_a&index=16)
2. [Cálculo: Teorema do Valor Intermediário](https://www.youtube.com/watch?v=ibXf6AAIuQM&list=PLTPg64KdGgYhACfQUtMf3CuhWOfLoTf_a&index=19)

##### *Continuidade em um Ponto*

>[!quote] **Leis de continuidade**
>**Continuidade em um Ponto**: Uma função é contínua em um ponto $x=ax$ se satisfizer três condições:
>- $f(a)$ está definido.
>- O limite de $f(x)$ quando $x$ se aproxima de $a$ existe.
>- O valor de $f(a)$ é igual ao limite de $f(x)$ quando $x$ se aproxima de $a$.
>  
>Se qualquer uma dessas condições falhar, a função não será contínua em $a$
##### *Continuidade no Domínio/Intervalo*

>[!quote]
>Uma função é dita contínua em um intervalo se for contínua em cada ponto desse intervalo. Isso implica que não há interrupções, saltos ou buracos no gráfico da função ao longo do intervalo. Por exemplo, 
>- A função $f(x)=x^2$ é contínua para todos os números reais
>- Enquanto uma função como $f(x) = \frac{1}{x}$​ não é contínua no domínio dos números reais 
>  
>Devido à descontinuidade em $x=0$.

>[!quote] **Def**
>As seguintes funções são contínuas em todos os pontos de seus domínios:
>
>**Polinomiais:** 
>- Funções que podem ser expressas como a soma de potências de x com coeficientes reais.
>  
>---
>  
>**Racionais:** 
>- Quocientes de duas funções polinomiais.
>---
>**Raiz:** 
>- Funções que envolvem raízes, como a raiz quadrada.
>---  
>**Trigonométricas:** 
>- Seno, cosseno, tangente e suas inversas.
>---  
>**Trigonométricas inversas:** 
>- Arcoseno, arcocosseno, arcotangente.
>---  
>**Exponenciais:** 
>- Funções da forma a^x, onde a é uma constante positiva.
>--- 
>**Logarítmicas:** 
>- Funções da forma logₐ(x).
##### *Continuidade em um Ponto na Extremidade*

>[!quote] 
Para uma função ser contínua em um ponto de extremidade (como $a$ em $[a,b]$) 
>- só é necessário verificar a continuidade pelo lado de dentro do intervalo. Por exemplo, se a função está definida e o limite à direita de $a$ é igual ao valor de $f(a)$, então $f$ é contínua no ponto $a$. Esse conceito é especialmente importante em intervalos fechados onde só existe um dos lados (direito ou esquerdo) para avaliar.

---
#
---
#### **Técnicas básicas Limites**

> [!quote] **O limite de uma função** 
>Nos permite estudar o comportamento de uma função à medida que a variável independente se aproxima de um determinado valor. 
>   
>Existem diversas técnicas para determinar o limite de uma função. A escolha da técnica mais adequada dependerá da forma da função e do ponto em que se deseja calcular o limite.
##### *Substituição direta*

>[!quote] **Definição**
>A técnica mais simples
>- Se a função é contínua no ponto em questão, basta substituir o valor de $x$ no qual se deseja calcular o limite.
>  
>**Khan:** [Limites por substituição direta](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-from-equations-calc/e/find-limits-by-direct-substitution) **|** [limites que não existem](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-from-equations-calc/e/identify-undefined-limits-by-direct-substitution) 

>[!error] *Substituição Direta*
>**Exemplo:** Limite de $f(x) = x²$ quando $x$ tende a $2$. Basta calcular $f(2) = 2² = 4$.
>- Substituir na expressão
##### *Simplificação algébrica*

>[!quote] **Definição** 
>Muitas vezes, funções podem ser simplificadas antes de aplicar o limite.
>- Fatore e simplifique as operações 
>  
>**Khan:** [Limites por fatoração](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-with-factoring-and-rationalizing-calc/e/two-sided-limits-using-algebra)

>[!error] *Simplificação Algébrica*
>**Exemplo:** Limite de $(x² - 4) / (x - 2)$ quando $x$ tende a $2$. Fatorando o numerador, temos $(x+2)(x-2) / (x-2)$. Simplificando, obtemos o limite de $x+2$ quando $x$ tende a $2$, que é $4$.
>- Fatore os termos.
>
##### *Racionalização*

>[!quote] **Definição**
>Utilizada quando a função envolve raízes.
>- Multiplica-se o numerador e o denominador pelo conjugado do termo irracional.
>- Um limite composto por $\frac00$ ainda pode existir. Entretanto $x/0$ é indefinido
>- Utilizado quando tem uma raiz quadrada
>- Sempre igualar a um $g(x)$. Quando igualada o limite some
>  
>**Khan:** [Limites usando conjugados](https://pt.khanacademy.org/math/calculus-all-old/limits-and-continuity-calc/limits-with-factoring-and-rationalizing-calc/e/limits_2)

>[!error] *Racionalização*  
>**Exemplo:** Limite de $(√(x+1) - 1) / x$ quando $x$ tende a $0$. 
>- Multiplicando pelo conjugado, simplificando e aplicando o limite, encontra-se o resultado.

---
#
---
#### **Técnicas Avançadas Limites**

>[!quote] **Aviso**
>**Observação:** 
>- A escolha da técnica mais adequada dependerá do contexto do problema e da complexidade da função.
##### *Teorema do Confronto*

>[!quote] **Definição**
>**Quando usar:** 
>Empregado quando uma função está "presa" entre outras duas funções cujo limite é conhecido.
>
> **Como funciona:** 
>  -  Se $f(x) ≤ g(x) ≤ h(x)$  para todo $x$ em um intervalo em torno de $c$ e $lim f(x) = lim h(x) = L$ quando $x$ tende a $c$, então $lim g(x) = L$ quando $x$ tende a $c$.
>    
>**Interpretação:**
>- Imagine três funções em um gráfico. Se o gráfico de $f(x)$ estiver sempre "espremido" entre os gráficos de $g(x)$ e $h(x)$ em torno de um ponto c. E se os gráficos de $g(x)$ e $h(x)$ se aproximarem do mesmo valor $L$ quando $x$ se aproxima de c então o gráfico de $f(x)$ também se aproximará de $L$.
>
>**YouTube:** [Teorema do Confronto](https://www.youtube.com/watch?v=r4ISeX3tSQk&list=PLb735fZHArLauSdbh2AQuEnwSVlqDmhUl&index=1)

>[!quote] **Estratégia Geral para Aplicação:**
>**Identificar a função:** 
>- Determine a função cujo limite você deseja calcular.
>  
>**Encontrar as "fatias de pão":**
>- Encontre duas funções $g(x)$ e $h(x)$ que satisfaçam a desigualdade $g(x) ≤ f(x) ≤ h(x)$ em uma vizinhança do ponto c.
>  
>**Calcular os limites das "fatias":** 
>- Determine os limites de $g(x)$ e $h(x)$ quando $x$ se aproxima de c.  
>  
>**Aplicar o teorema:** 
>- Se os limites de $g(x)$ e $h(x)$ forem iguais, então o limite de $f(x)$ também será igual a esse valor.

>[!error] **Exemplo Genérico:**
>
>Seja $f(x)$ uma função qualquer. Suponha que existam funções $g(x) = x²$ e $h(x) = 2x²$ tais que:
>- $x² ≤ f(x) ≤ 2x²$ para todo $x$ próximo de 0.
>  
>Como 
>- $lim (x → 0) x² = 0$ 
>- $lim (x → 0) 2x² = 0$ 
>  
>Pelo Teorema do Confronto, podemos concluir que:  
>- $lim (x → 0) f(x) = 0$
##### *Regra de L'Hôpital (imcomplet)*

>[!quote] **Definição**
>**Quando usar:** 
>- Essa regra é especialmente útil em casos de indeterminação do tipo 0/0 ou ∞/∞, ou seja, quando tanto o numerador quanto o denominador tendem a zero ou a infinito.
>  
>**Como funciona:** 
>- Deriva-se o numerador e o denominador separadamente e calcula-se o limite da nova função obtida. Se a indeterminação persistir, repete-se o processo.
>  
>**Exemplo:** Limite de $(sin(x))/x$ quando $x$ tende a $0$.
>- Derivando numerador e denominador, temos: $lim (cos(x))/1$ quando $x$ tende a $0$.
>- Substituindo $x$ por $0$, obtemos $cos(0) = 1$.
>- Portanto, o limite original é 1.

---
#
---
