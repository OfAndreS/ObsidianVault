
---

```ad-example

#### **Pontos & Retas Impróprios**
```

---
#### **1 ) Ponto Impróprio** (Ponto no Infinito)

```ad-quote
title: **Def**

**Definição Formal**

Um ponto impróprio (ou ponto no infinito) é um ponto que representa uma direção no espaço. Ele é definido como o ponto de intersecção de todas as retas paralelas a uma dada direção.

**Notação e Interpretação**

* No plano projetivo $\mathbb{P}^2$, um ponto é representado por coordenadas homogêneas $(x : y : w)$, onde:
    * Se $w \neq 0$, corresponde a um ponto ordinário $\left(\frac{x}{w}, \frac{y}{w}\right)$ no plano euclidiano.
    * Se $w = 0$, corresponde a um **ponto impróprio** $(x : y : 0)$, associado à direção do vetor $(x, y)$.

```

```ad-quote
title: **Def**

**Exemplo**

Considere as retas paralelas no plano euclidiano:

$$
r_1: y = 2x + 1 \quad \text{e} \quad r_2: y = 2x - 3.
$$

* Ambas têm a mesma direção $\mathbf{v} = (1, 2)$.
* Na geometria projetiva, elas se interceptam no **ponto impróprio** $(1 : 2 : 0)$.
```

![[Pasted image 20250503210208.png]]

---
#### **2 ) Reta Imprópria**

```ad-quote
title: **Def**

**Definição Formal**

A reta imprópria é o conjunto de todos os pontos impróprios de um plano. No $\mathbb{P}^2$, ela é denotada por $w = 0$.

**Interpretação Geométrica**

* No plano euclidiano $\mathbb{R}^2$, a reta imprópria pode ser imaginada como um "horizonte" que contém todas as direções possíveis.
* No espaço tridimensional $\mathbb{R}^3$, o conceito análogo é o plano impróprio.
```

```ad-quote
title: **Def**

**Equação da Reta Imprópria**

Em coordenadas homogêneas, a reta imprópria é dada por:

$$
w = 0.
$$

Qualquer ponto $(x : y : 0)$ pertence a ela.
```

---

```ad-example

#### **Segmento de Reta Orientada** / Espaço Unidimensional 
```

---
#### ***Reta Orientada*** 

```ad-quote
title: **Def**

**Ocorre quando:**
- É estabelecido na reta um sentido de percurso positivo
  
---
  
**O sentido:** 
- contrário ao positivo é negativo
  
---
  
**O sentido:** 
- positivo é indicado por uma seta
```
#### ***Segmento:***

```ad-quote
title: **Def**

**DEFINIÇÃO:** 
- Dados dois pontos distintos $A$ e $B$ quaisquer, que determinam uma reta $r$, chamaremos de segmento $AB$ ou $\overline{AB}$, ao conjunto formado por todos os pontos da reta $r$ entre $A$ e $B$.

**Obs:** Note que o segmento $\overline{AB} = \overline{BA}$. O segmento $\overline{AA}$ será considerado segmento nulo.
```
#### ***Segmento orientado:***

```ad-quote
title: **Def**

Sejam os pontos $A$ e $B$ pertencentes a uma reta orientada $r$. O segmento finito e orientado $\overrightarrow{AB}$ com início em $A$ e final em $B$ terá sua medida algébrica dado por um valor real **positivo** se sua orientação for no sentido positivo da reta $r$ e **negativo** caso contrário.

**Obs:** Note agora que $\overrightarrow{AB} \neq \overrightarrow{BA}$. O segmento orientado $\overrightarrow{AA}$ será considerado segmento orientado nulo.
```

![[Pasted image 20250503213504.png]]

---
#### **Medidas Algébricas de um Segmento**

```ad-quote
title: **Def**

Sejam dois pontos $A$ e $B$ pertencentes a uma reta orientada $r$. A medida algébrica do segmento finito e orientado $\overrightarrow{AB}$ é um número real, positivo se sua orientação for concordante com o sentido positivo da reta e é um número real negativo, em caso contrário. O número real que é a medida algébrica do segmento $\overrightarrow{AB}$ é representado por $AB$. Ao eixo se associa uma unidade de comprimento $u$.
```
###### ***Exemplo:***

![[Pasted image 20250503220009.png]]

---
#### **Razão Simples de Três Pontos** / Alinhados

```ad-quote
title: **Def**

**Definição Formal**

Dados três pontos colineares $A$, $B$ e $P$ em um espaço afim, a razão simples (ou razão afim) é definida como:

$$
(A, B; P) = \frac{\overrightarrow{AP}}{\overrightarrow{PB}}
$$

---

**Onde:**

* $\overrightarrow{AP}$ e $\overrightarrow{PB}$ são vetores orientados na reta suporte.
* A notação $(A, B; P)$ indica que $A$ e $B$ são pontos de referência e $P$ é o ponto cuja razão é calculada.

```

```ad-quote
title: **Def**

**Propriedades Fundamentais**

* $(A, B; P) > 0$ se $P$ está fora do segmento $AB$.

---
  
* $(A, B; P) < 0$ se $P$ está entre $A$ e $B$.
  
---

* $(A, B; P) = 0$ se $P \equiv A$.
  
---

* Indefinida se $P \equiv B$ (divisão por zero).

```

![[Pasted image 20250503221312.png]]

---
#### **Abscissas na Reta** / Ponto Origem

```ad-quote
title: **Def**

O ponto $O$ (origem) divide o eixo $r$ em duas semirretas, onde: 
- A semirreta positiva é indicada pela seta. 
- É negativa a outra semirreta. 
  
Ao eixo se fixa *a priori* uma unidade de comprimento. Chama-se **abscissa** $x_1$ de um ponto $P_1$ de uma reta orientada $r$, à medida do segmento orientado e finito $\overline{OP_1}$, da origem a esse ponto, antecedida do sinal de (+) ou (–) conforme o ponto $P_1$ pertença à semirreta positiva ou negativa. Há uma correspondência bijetiva entre os números reais e os pontos de uma reta.
```

![[Pasted image 20250503223254.png]]

---
#### **Distância em Uma Dimensão** / Reta Real

```ad-quote
title: **Def**

Dados dois pontos $A$ e $B$ em uma reta numérica com coordenadas $x_A$ e $x_B$, a distância entre eles é:

$$
d(A, B) = |x_B - x_A|
$$
```
###### ***Exemplo:***

```ad-quote
title: **Def**

**Dado que:**

$A = 3$ e $B = -2$

**Logo:**

$d(A, B) = |-2 - 3| = |-5| = 5$

```

---

> [!tip] #### **Razão Simples de 3 Pontos por suas Abscissas**

---

```ad-quote
title: **Def**

**Conceito Fundamental**

Dados dois pontos $P_1(x_1)$ e $P_2(x_2)$ em uma reta, queremos encontrar as coordenadas de um ponto $P(x)$ que divide o segmento $\overline{P_1P_2}$ em uma razão $k$.

* **Razão k:**

A razão $k$ é definida como a relação entre as distâncias $\overline{P_1P}$ (parte inicial) e $\overline{PP_2}$ (parte final):

$$
k = \frac{\overline{P_1P}}{\overline{PP_2}}
$$

```

```ad-quote
title: **Def**


**Dedução da Fórmula**

Usando coordenadas, expressamos as distâncias como diferenças entre as abscissas:

$$
k = \frac{x - x_1}{x_2 - x}
$$

```

```ad-quote
title: **Def**
**
Fórmula Final**
   $$
   x = \frac{x_1 - kx_2}{1 - k}
   $$

```

```ad-quote
title: **Def**

**Interpretação** **Geométrica**

* **Razão positiva ($k > 0$):**
   $P$ está entre $P_1$ e $P_2$.

   **Exemplo:** Se $k = 1$, $P$ é o ponto médio:
   $$
   x = \frac{x_1 + x_2}{2}
   $$

---

* **Razão negativa ($k < 0$):**
   $P$ está fora do segmento $\overline{P_1P_2}$.

   **Exemplo:** Se $k = -2$, $P$ está além de $P_2$.
```

![[Pasted image 20250503224738.png]]

---
