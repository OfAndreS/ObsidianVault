
---
## **Regra da potência inversa**

>[!quote] **Def**
>
**Seja $n \neq -1$, a integral de $x^n$ é dada por:**
>
>$$\int x^n dx = \frac{x^{n+1}}{n+1} + C$$
>
>**Onde:**
>
>* $x^n$ é a função que estamos integrando.
>* $n+1$ é o novo expoente.
>* $\frac{1}{n+1}$ é o fator de ajuste.
>* $C$ é a constante de integração.
>
>---
>
>**Por que $n \neq -1$?**
>
>Se $n = -1$, a fórmula não se aplica porque o denominador $n+1$ se torna zero, o que é indefinido.
>
>Neste caso especial, a integral de $x^{-1}$ é:
>
>$$\int x^{-1} dx = \int \frac{1}{x} dx = \ln|x| + C$$

>[!quote] ***Khan:*** [Revisão da regra da potência reversa](https://pt.khanacademy.org/math/calculus-all-old/integration-calc/indefinite-integrals-intro-calc/a/reverse-power-rule-review)

---
#### **Fórmula Geral para a Integral de um Polinômio**

>[!quote] **Def**
>Se o polinômio for da forma:
>
>$$P(x) = a_n x^n + a_{n-1}x^{n-1} + ... + a_1x + a_0$$
>
>a integral será:
>
>$$\int P(x) dx = \int (a_n x^n + a_{n-1}x^{n-1} + ... + a_1x + a_0) dx$$
>
>---
>
>Usando a linearidade da integral ($\int (f(x) + g(x)) dx = \int f(x) dx + \int g(x) dx$), resolvemos termo a termo:
>
>$$\int P(x) dx = \frac{a_n x^{n+1}}{n+1} + \frac{a_{n-1}x^{n}}{n} + ... + \frac{a_1x^2}{2} + a_0x + C$$
>
>onde $C$ é a constante de integração.

>[!quote] ***Khan:*** [Regra da potência reversa](https://pt.khanacademy.org/math/calculus-all-old/integration-calc/indefinite-integrals-intro-calc/e/integration)

---





