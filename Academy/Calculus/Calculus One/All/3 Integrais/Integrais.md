
---

>[!quote] **Def**
>**Definição:**
>- integrais são ferramentas matemáticas usadas para calcular áreas, volumes, deslocamentos, e outras quantidades acumulativas. Intuitivamente, a integral pode ser vista como o processo de "soma contínua" de infinitos elementos infinitamente pequenos.
>
>**Existem dois tipos principais de integrais no Cálculo 1:** 
>- integrais definidas 
>- integrais indefinidas.

![[Pasted image 20241212190459.png]]
##### _Etapas Gerais do Cálculo de Integrais_

> [!quote] **Def**
> 1. Identifique o tipo de integral (definida ou indefinida).
> 2. Determine uma antiderivada para a função integrada.
> 3. (Se definida) Substitua os limites superior e inferior para calcular o valor acumulado.

---
#### **Integral Definida**

>[!quote] **Def** 
>A integral **Definida** calcula o valor acumulado de uma função em um intervalo $[a,b]$. É representada como: 
>  
>  $$ \int_a^b f(x) dx $$
>  
>---
>  
>**Geometricamente:** 
>- Essa operação é usada para encontrar a área sob a curva $f(x)$, acima do eixo $x$, e entre os limites $x=a$ e $x=b$.
>  
>**O Teorema Fundamental do Cálculo** 
>- Conecta a integral definida com a derivada, permitindo que a integração seja realizada usando uma antiderivada.
>  

>[!quote] **Def**
>_**Lembre-se:**_ _a integral definida sempre nos dá a variação líquida de uma grandeza, não o valor atual da grandeza. Para encontrar o valor atual, devemos adicionar uma condição inicial à integral definida._
#### **Integral Indefinida**

>[!quote] **Def** 
>A integral **Indefinida** busca encontrar a função original $F(x)$ cuja derivada é $f(x)$. É representada como: 
>
>$$ \int f(x) dx = F(x) + C $$
>  
>Aqui, $C$ é a constante de integração, que reflete a família de funções com a mesma derivada.
>
>---
>
>$f(x)$ 
>- É a função a ser integrada (função integrando)
>  
>$F(x)$ 
>- É a função primitiva de $f(x)$ tal que $F'(x) = f(x)$
>  
>$C$ 
>- É a constante de integração, pois a derivada de uma constante é zero.

---
#### **Primitivas**

>[!quote] **Def**
>As primitivas (ou funções primitivas) são um conceito central no cálculo integral. De forma
>simples, a primitiva de uma função $f(x)$ é uma outra função $F(x)$ cuja derivada resulta em $f(x)$. Em outras palavras:
>
$$F'(x) = f(x)$$
>
>A relação entre a derivada e a primitiva é direta, e ela é fundamental no cálculo porque mostra como o processo de integração é o "inverso" do processo de derivação.

>[!quote] **_Notação_**
>A Integral de $f(x)$ é representada por:
>
>$$\int f(x) dx = F(x) + C$$
>
>Sendo $F(x)$ sua primitiva
>
>---
>
>$dx$
>- O $dx$ indica que estamos integrando em relação à variável $x$.
>
>$C$
>- A constante $C$ representa uma família de funções, todas com a mesma derivada. Isso ocorre porque a derivada de uma constante é zero.
>

>[!quote] ***Khan:*** [Primitivas e integrais indefinidas](https://pt.khanacademy.org/math/calculus-all-old/integration-calc/antiderivatives-calc/v/antiderivatives-and-indefinite-integrals)

---

>[!error] **Link Part**

---
#### _**Regras de Integração**_

>[!quote] **Def**
>As **regras de integração** são um conjunto de ferramentas que utilizamos para encontrar as primitivas de funções, ou seja, para resolver integrais. Elas são como um conjunto de receitas que nos guiam no processo de encontrar a função original a partir de sua derivada.
##### _Tabelada_

>[!quote] ***Vault:*** [[Integração Tabelada]]
##### _Simples_

>[!quote] ***Vault:*** [[Potência inversa]]
##### _Por Partes_

>[!quote] ***Vault:*** [[Integração Por Partes]]
##### _Frações Parciais_

>[!quote] ***Vault:*** [[Decomposição em Frações Parciais]]

---
#### _**Soma de Riemann**_

>[!quote] **Def**
>A Soma de Riemann os permite aproximar a área sob uma curva, ou seja, o valor de uma integral definida. Essa técnica consiste em dividir a região sob a curva em um grande número de retângulos e, em seguida, somar as áreas desses retângulos. À medida que aumentamos o número de retângulos, a aproximação se torna cada vez mais precisa.

>[!quote] ***Vault:*** [[Somatório]]

>[!quote] ***Vault:*** [[Soma de Riemann]]

---
#### **Identidades Trigonométricas**

> [!quote] **Def: **
>As identidades trigonométricas são equações fundamentais que relacionam funções trigonométricas, como seno, cosseno, tangente e secante. Elas incluem as identidades pitagóricas, como $\sin^2(x) + \cos^2(x) = 1$, e expressões de ângulo duplicado, como $\cos^2(x) = \frac{1+\cos(2x)}{2}$. Essas fórmulas são essenciais para simplificar expressões, resolver equações e calcular integrais.

---

- Integrais por substituição
[Integração por substituição: integrais indefinidas (prática) | Khan Academy](https://pt.khanacademy.org/math/calculus-all-old/integration-techniques-calc/u-substitution-calc/e/integration-by-u-substitution)
