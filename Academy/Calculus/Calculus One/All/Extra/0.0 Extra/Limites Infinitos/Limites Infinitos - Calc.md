
---

> [!quote] **Teorema**
> 
> **Definição**
> - Á medida que x se torna cada vez maior (tendendo ao infinito), a fração 1/x^n se torna cada vez menor, aproximando-se de zero. Isso ocorre porque o denominador x^n cresce muito mais rapidamente que o numerador 1, fazendo com que a fração se torne infinitesimal.
> 
> **Aplicação**
> - Se $n$ é um número inteiro positivo então:
> 1.
> $$\lim_{x\to\pm\infty}\frac1{x^n}=0$$
> ---
> 2.
> $$\mathbf{ii.}\quad\lim_{x\to\pm\infty}k=k$$

>[!error] *Exemplo 01* 
>1. $$\mathbf\quad\lim_{x\to+\infty}\left(3+\frac{1}{x}\right)=\lim_{x\to+\infty}3+\lim_{x\to+\infty}\frac{1}{x}=3+0=3$$

>[!error] *Exemplo 02*
>2. $$\lim_{x\to-\infty}\left(\frac{\pi\sqrt{2}}{x^{3}}\right)=\lim_{x\to-\infty}\pi\sqrt{2}\cdot\frac{1}{x^{3}}=\lim_{x\to-\infty}\pi\sqrt{2}\cdot\lim_{x\to-\infty}\frac{1}{x^{3}}=\pi\sqrt{2}\cdot0=0$$

---

#### **Limites de Funções Racionais quando $x -> ±∞$**

>[!quote] **Execução**
>**Obs:** No cálculo de limites no infinito de funções racionais poderemos considerar apenas o limite no infinito do quociente entre os termos de maiores graus
>- Tanto do numerador
>- Quanto do denominador
>
>Em geral, podemos dividir o numerador e o denominador pela potência de $x$ que aparece no denominador.

>[!quote] 01
>**Numerador e Denominador de mesmo grau**
>$$\lim_{x\to+\infty}\frac{3x^{2}+5x-3}{2x^{2}+1}=\lim_{x\to+\infty}\frac{3+\frac{5}{x}-\frac{3}{x^{2}}}{2+\frac{1}{x^{2}}}=\frac{3+0-0}{2+0}=\frac{3}{2}$$

>[!quote] 02
>
>**Numerador com menor grau que o Denominador**
>$$\lim_{x\to-\infty}\frac{2x+3}{3x^3-2}=\lim_{x\to-\infty}\frac{\frac{2}{x^2}+\frac{3}{x^3}}{3-\frac{2}{x^3}}=\frac{0+0}{3-0}=\frac{0}{3}=0$$

>[!quote] 03 *
>**Denominador com menor grau que o Numerador** 
>$$\lim_{x\to-\infty}\frac{2x^2+4x-5}{3x+4}=\lim_{x\to-\infty}\frac{2x+4-\frac5x}{3+\frac4x}=\frac{-\infty+4-0}{3+0}=\frac{-\infty}{3}=-\infty $$
>

---
#### **Direção do Infinito**

>[!quote] **Definição**
>Quando dizemos que o limite de f(x), quando x tende a "a", é menos infinito, estamos dizendo que: [Limites infinitos: algebricamente](https://pt.khanacademy.org/math/differential-calculus/dc-limits/dc-infinite-limits/e/limits-at-infinity-where-f-x--is-unbounded)
>- À medida que x se aproxima de "a", os valores de f(x) se tornam cada vez mais negativos.
>- Não importa quão grande seja o número negativo que você escolher, sempre será possível encontrar um valor de x suficientemente próximo de "a" para que f(x) seja menor do que esse número negativo.
>  
>**Aplicação**
>- Se $n$ é um número inteiro positivo então:
>  1. $$\quad\lim_{x\to0^+}\frac1{x^n}=+\infty $$
> ---
>2. $$\lim\limits_{x\to0^-}\frac{1}{x^n}=\begin{cases}+\infty,\textit{se n é par}\\-\infty,\textit{se n é ímpar}\end{cases}$$
>   

>[!quote] **Visual**
>**Tendendo ao mais infinito**
>$$\lim_{x\to3^{+}}\frac{x}{x-3}=\frac{3}{0^{+}}=+\infty $$
>  ---
>**Tendendo ao menos infinito**
> $$\operatorname*{lim}_{x\to3^{\pm}}\frac{x}{{x-3}_{}}=\frac{3}{0}=-\infty $$

>[!error] *Exemplo 01*
>1. $$ \lim_{x\to0}\left(x^{3}+2\sqrt[3]{x}+\frac{1}{x^{2}}\right)=\lim_{x\to0}x^{3}+\lim_{x\to0}2\sqrt[3]{x}+\lim_{x\to0}\frac{1}{x^{2}}=0$$

---
#### **Assíntotas**

>[!quote] **Definição**
>**Assíntotas verticais** 
>- Envolvem limites infinitos
>  
>**Assíntotas horizontais** 
>- Envolvem limites no infinito
##### *Horizontal*

>[!quote] **Execução**
>Calcular o limite quando $(x → +\infty)$ & $(x →-\infty)$

> [!error] *Exemplo 01*
> **Questão 01) - H**
> 
> $$f(x) = \frac{3x}{x-1}$$
> 
> ---
> 
> **RESOLUÇÃO (+∞)**
> 
> $$\lim_{x \to +\infty} f(x) = \lim_{x \to +\infty} \frac{3x}{x-1} = \lim_{x \to +\infty} \frac{\frac{3x}{x}}{\frac{x}{x} - \frac{1}{x}} = \lim_{x \to +\infty} \frac{3}{1 - \frac{1}{x}} = \frac{3}{1 - 0} = 3$$
> 
> ---
> **RESOLUÇÃO (-∞)**
> 
> $$\lim_{x \to -\infty} f(x) = \lim_{x \to -\infty} \frac{3}{1 - \frac{1}{x}} = \frac{3}{1 - 0} = 3$$
> 
> 
> Logo, 3 é a assíntota Horizontal da questão.

> [!error] *Exemplo 02*
> **Questão 02) - H**
> 
> $$y=\frac{x}{\sqrt{x^{2}+2}}$$
> 
> ---
> 
> **RESOLUÇÃO (+∞)**
> 
> $$\lim_{x\to+\infty}\frac{x}{\sqrt{x^{2}+z}}=\lim_{x\to+\infty}\frac{\frac{x}{x}}{\frac{\sqrt{x^{2}+z}}{\sqrt{x^{2}}}}=\lim_{x\to+\infty}\frac{1}{\sqrt{1+\frac{z}{x^{2}}}}=\frac{1}{\sqrt{1+0}}=1$$
> 
> ---
> **RESOLUÇÃO (-∞)**
> 
> $$\lim_{n\to-\infty}\frac{-\frac{x}{xy}}{\frac{\sqrt{x^{2}+2}}{\sqrt{x^{2}}}}=\lim_{n\to-\infty}\frac{-1^{2}}{\sqrt{1+\frac{2}{x^{2}}}}=\frac{-1}{\sqrt{1+0}}=\frac{-1}{1}=-1$$
> 
> 
> Logo, S = {1, -1} são as assíntotas Horizontais da questão.
##### *Vertical*

>[!quote] **Definição**
>Supor um $x_0$ de tal forma que $f(x)/g(x)$ quando $g(x_0)$ seja igual a 0
>

> [!error] *Exemplo 01*
> **Questão 01) - V**
> 
> $$f(x) = \frac{3x}{x-1}$$
> 
> ---
> **RESOLUÇÃO ($x^+$)**
> 
> $$\lim_{x \to 1^{+}} \frac{3x}{x-1} = \frac{3}{0^{+}} = \infty$$
> 
> ---
> **RESOLUÇÃO ($x^-$)**
> 
> $$\lim_{x \to 1^{-}} \frac{3x}{x-1} = \frac{3}{0^{-}} = -\infty$$
> 
> 
> Logo, 1 é a assíntota Vertical da questão.

> [!error] *Exemplo 02*
> **Questão 03) - V**
> 
> $$f(x)=\frac{x}{x^{2}-9}$$
> 
> ---
> **RESOLUÇÃO ($x^+$)**
> 
> $$\operatorname*{lim}_{x\rightarrow3^{+}}\frac{x}{x^{2}-9}=\frac{3}{0^{+}}=+\infty $$ && $$\lim_{x\to-3^{+}}\frac{x}{x^{2}-9}=\frac{-3}{0^{-}}=+\infty $$
> 
> ---
> **RESOLUÇÃO ($x^-$)**
> 
> $$\lim_{x\to3^{-}}\frac{x}{x^{2}-9}=\frac{3}{0^{-}}=-\infty$$ && $$\lim_{x\to-3^{-}}\frac{x}{x^{2}-9}=\frac{-3}{0^{+}}=-\infty $$
> 
> 
> Logo, S = {3, -3} são as assíntotas Horizontais da questão.

---
