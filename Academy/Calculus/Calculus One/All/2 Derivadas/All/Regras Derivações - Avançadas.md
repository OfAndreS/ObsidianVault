
---

>[!quote] **Def**
>Algumas regras fundamentais utilizadas na derivação direta.
>
>Sendo elas:
>- *Derivada do Produto*
>- *Derivada do Quociente*
##### *Derivada do Produto*

>[!quote] **Def**
>Para derivar o produto de duas funções, usamos a seguinte fórmula
>
>**Fórmula:**
>- Se $f(x) = g(x) \cdot h(x)$, então 
>$$f′(x)=g′(x)⋅h(x)+g(x)⋅h′(x)$$
>
>**Khan:** [Regra do produto](https://pt.khanacademy.org/math/calculus-all-old/taking-derivatives-calc/product-rule-calc/v/applying-the-product-rule-for-derivatives)

>[!error] *Exemplo*
>**Problema:**
>- Calcule a derivada de $f(x) = x^2 \cdot \sin(x)$
>
>**Solução:**
>
>- Seja $g(x) = x^2$ e $h(x) = \sin(x)$
>
>Derivamos cada função separadamente:
>- $g′(x)=2x$
>- $h′(x)=cos(x)$
>  
>Aplicando a regra do produto:
>
>1. $$f′(x)=(2x)⋅sin(x)+(x2)⋅cos(x)$$
>2. $$f′(x)=2xsin(x)+x2cos(x)$$
##### *Derivada do Quociente*

>[!quote] **Def**
>Para derivar o quociente de duas funções, usamos a seguinte fórmula:
>
>**Fórmula:**
>- Se $f(x) = \frac{g(x)}{h(x)}$, então 
>$$f'(x) = \frac{g'(x) \cdot h(x) - g(x) \cdot h'(x)}{[h(x)]^2}$$
>
>**Khan:** [Regra do quociente](https://pt.khanacademy.org/math/calculus-all-old/taking-derivatives-calc/quotient-rule-calc/v/quotient-rule-from-product-rule)

>[!error] *Exemplo*
>**Problema:**
>- Calcule a derivada de$f(x) = \frac{x^2}{\cos(x)}$
>
>**Solução:**
>
>- Seja $g(x)=x^2$ e $h(x)=cos⁡(x)h(x) = \cos(x)$
>
>Derivamos cada função separadamente:
>- $g′(x)=2x$
>- $h′(x)=−sin(x)$
>  
>Aplicando a regra do quociente:
>
>1. $$f'(x)=\frac{(2x)\cdot\cos(x)-(x^2)\cdot(-\sin(x))}{[\cos(x)]^2}$$
>   
>Simplificando:
>
>2. $$f'(x)=\frac{2x\cos(x)+x^2\sin(x)}{\cos^2(x)}$$

---
