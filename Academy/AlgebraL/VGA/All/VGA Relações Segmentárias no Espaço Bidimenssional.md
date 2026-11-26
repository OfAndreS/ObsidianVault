
---

```ad-example

#### **Sistema Cartesiano**
```

---
#### **Ortogonal**

```ad-quote
title: **Def**

Um sistema de eixos ortogonais no plano é constituído de duas retas orientadas 
- $x$ e $y$ 
  
perpendiculares entre si e de mesma origem $O$. 

---

Sendo:

- A reta orientada $x$ é denominada eixo $x$ ou eixo das abscissas; 
- A reta orientada $y$ é denominada eixo $y$ ou eixo das ordenadas; 

Os eixos $x$ e $y$ são os eixos coordenados e dividem o plano em quatro partes ou quadrantes.

```

```ad-quote
title: **Def**

Por um ponto qualquer $P$ do plano traçam-se perpendiculares sobre cada um dos dois eixos, determinando neles os pontos $P_x$ e $P_y$ de tal sorte que $x = \overline{OP_x}$ e $y = \overline{OP_y}$.

Sendo:

$$ P = (x, y) $$

```

![[Pasted image 20250504165928.png]]
#### **Oblíquo**

```ad-quote
title: **Def**

O **sistema cartesiano oblíquo** é uma variação do sistema cartesiano tradicional em que os eixos coordenados (x e y) não são perpendiculares, mas formam um ângulo **θ ≠ 90°** entre si. Nele, as coordenadas de um ponto ainda são definidas por projeções paralelas aos eixos, mas as fórmulas de distância e inclinação são ajustadas devido à obliquidade. Esse sistema é útil em contextos específicos, como geometria projetiva ou quando a simetria do problema se adapta melhor a eixos não ortogonais. No entanto, a maioria das aplicações práticas prefere o sistema ortogonal por simplificar cálculos.
```

![[Pasted image 20250504170025.png]]

---

```ad-example

#### **Operações & Igualdades** / Pares ordenados
```

---
#### **Operações Padrões**

```ad-quote
title: **Def**

**Adição**

$$
(x_1, y_1) + (x_2, y_2) = (x_1 + x_2, y_1 + y_2)
$$

**Exemplo:**

$(2, 5) + (1, -3) = (3, 2)$
```

```ad-quote
title: **Def**

**Multiplicação por um número Real K**

$$
k (x_1, y_1) = (kx_1, ky_1)
$$

**Exemplo:**

$3 (5, -1) = (15, -3)$

```

```ad-quote
title: **Def**

**Igualdade de Dois Pares Ordenados**

$$
(x_1, y_1) = (x_2, y_2) \Leftrightarrow x_1 = x_2 \text{ e } y_1 = y_2
$$

**Exemplo:**

$(x - 1, y + 3) = (1, 7)$

Onde:
$x - 1 = 1 \rightarrow x = 2$
$y + 3 = 7 \rightarrow y = 4$
```

---
#### **Distância Entre Pontos**

```ad-quote
title: **Def**

Dados dois pontos $P_1 = (x_1, y_1)$ e $P_2 = (x_2, y_2)$, deseja-se calcular a distância $d$ entre $P_1$ e $P_2$. Aplicando o teorema de Pitágoras ao triângulo retângulo $P_1AP_2$, tem-se:

$$
d^2 = (x_2 - x_1)^2 + (y_2 - y_1)^2
$$

$$
d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}
$$

```

---
#### **Baricentro de um Triângulo**

```ad-quote
title: **Def**

O **baricentro** ($G$) é o ponto de intersecção das medianas de um triângulo, onde cada mediana é o segmento que liga um vértice ao ponto médio do lado oposto. Ele divide cada mediana na razão $2 : 1$, sendo $\frac{2}{3}$ da distância a partir do vértice e $\frac{1}{3}$ a partir do lado oposto.
```

 ```ad-quote
title: **Def**

**Coordenadas do Baricentro:**

Dado um triângulo com vértices $A(x_1, y_1)$, $B(x_2, y_2)$ e $C(x_3, y_3)$, suas coordenadas são:

$$
G\left(\frac{x_1 + x_2 + x_3}{3}, \frac{y_1 + y_2 + y_3}{3}\right)
$$

```

```ad-quote
title: **Def**

**Centro de Massa:**

* Corresponde ao centroide se o triângulo tiver densidade uniforme.
* Ponto de equilíbrio se o triângulo fosse uma placa rígida.

**Sempre Interno:**

* Localiza-se dentro do triângulo, mesmo em casos obtusângulos ou escalenos.

```

![[Pasted image 20250504175352.png]]

---
