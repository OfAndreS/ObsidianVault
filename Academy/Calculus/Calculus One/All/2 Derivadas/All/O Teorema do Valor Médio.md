
---
### **Conceito Central**

>[!tip] **Def**
>O teorema garante a existência de um ponto no intervalo $[a,b]$ onde a taxa de variação instantânea _Derivada_ é igual à taxa de variação média no intervalo.

>[!quote] **Def**
>
>O Teorema do Valor Médio (TVM) é um resultado fundamental em cálculo diferencial, enunciado da seguinte forma:
>
>Seja $f(x)$ uma função contínua em um intervalo fechado $[a, b]$ e diferenciável em um >intervalo aberto $(a, b)$, então existe pelo menos um ponto $c$ em $(a, b)$ tal que:
>
$$f'(c) = \frac{f(b) - f(a)}{b - a}$$
>
>Essa equação indica que existe um ponto $c$ onde a inclinação da tangente à curva $f(x)$ (derivada $f'(c)$) é igual à inclinação da reta secante que conecta os pontos $(a, f(a))$ e $(b, f(b))$.

>[!quote] **Khan:** [Artigo](https://pt.khanacademy.org/math/differential-calculus/dc-analytic-app/dc-mvt/a/review-establishing-differentiability-for-mvt)

>[!quote] **Khan:** [Como usar o teorema do valor médio](https://pt.khanacademy.org/math/differential-calculus/dc-analytic-app/dc-mvt/e/mean-value-theorem)

---
#### **Teorema do Valor Médio: Uma Explicação Intuitiva**

>[!quote] **Def**
>Imagine dirigir de uma cidade A para uma cidade B. Sua velocidade média é dada por:
>
>$$VelocidadeMédia = \frac{DistânciaTotal}{TempoTotal}$$
>
>O Teorema do Valor Médio (TVM) afirma que, em algum momento durante a viagem, sua velocidade instantânea (marcada pelo velocímetro) será exatamente igual à velocidade média.
>
>No contexto de funções, isso implica que a curva $f(x)$ terá uma tangente paralela à secante que conecta $f(a)$ a $f(b)$.

![[Pasted image 20241205094410.png]]

>[!error] _Exemplo_

>[!error] :
>Considere $f(x) = x^2$ no intervalo $[1, 3]$.
>
>1. A inclinação da secante é:
>
>  $$\frac{f(3) - f(1)}{3 - 1} = \frac{9 - 1}{2} = 4.$$
>
>2. Encontramos $c$ tal que $f'(c) = 4$. Como $f'(x) = 2x$, temos:
>
>   $$2c = 4 \implies c = 2.$$
>
>O ponto $c = 2$ satisfaz o TVM.

---
