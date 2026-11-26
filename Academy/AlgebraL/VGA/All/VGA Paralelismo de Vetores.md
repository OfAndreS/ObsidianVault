
---
#### **01 )** - *Definição*

```ad-quote
title: **Def**

Dois vetores **$\vec{u}$** e **$\vec{v}$** são **paralelos** se um for múltiplo escalar do outro, ou seja, se existir um escalar **$k \neq 0$** tal que:  

$$
\vec{u} = k \cdot \vec{v}
$$

- **$k > 0$** → Mesmo sentido 
- **$k < 0$** → Sentidos opostos (**antiparalelos**) 
```

---
#### **02 )** - *Condição de Paralelismo / Forma Analítica*

```ad-quote
title: **Def**

Sejam dois vetores em $\mathbb{R}^3$:  

$$
\vec{u} = (u_1, u_2, u_3) \quad \text{e} \quad \vec{v} = (v_1, v_2, v_3)
$$

Eles são paralelos **se e somente se**:  

$$
\frac{u_1}{v_1} = \frac{u_2}{v_2} = \frac{u_3}{v_3} = k
$$

**Observação:** Se algum $v_i = 0$, então $u_i$ também deve ser $0$ para que sejam paralelos.  
```

---
#### **03 )** - *Propriedades Importantes*

```ad-quote
title: **Def**

**Vetor nulo** 
- $\vec{0}$ é paralelo a qualquer vetor, pois $\vec{0} = 0 \cdot \vec{v}$.  

**Vetores iguais** 
- são paralelos (caso $k = 1$).  

**Vetores colineares** 
- Na mesma reta são paralelos.  
```

---
#### **04 )** - *Visualização Geométrica*

```ad-quote
title: **Def**

A igualdade persiste se os vetores forem representados por pontos. Seja:

1. $$\vec{u} = (B - A) \ \ e \ \ \vec{v} = (C - D)$$

Então:

2. $$(C - D) = k(B - A)$$

```
###### ***Exemplos:***

```ad-quote
title: **Def**

Enfatizando o paralelismo dos vetores representados por suas imagens geométricas, podemos afirmar que:
```

![[Pasted image 20250531212416.png]]

---

>[!error] **Ex )** - *Vetores Paralelos* 

---
##### *Exemplo 01)*

```ad-quote
title: **Def**

###### **Dados os Vetores:**
1. $$\vec{u} = (6, -2, 4) \ \ e \ \ \vec{v} = (-9, 3, -6)$$

---

###### **Passo 1 )** - *Verificar se um é múltiplo escalar do outro*

Queremos encontrar um escalar \( k \) tal que:

2. $$\vec{u} = k \cdot \vec{v}$$

Isso significa:

3. $$(6, -2, 4) = k \cdot (-9, 3, -6)$$

---

###### **Passo 2 )** - *Igualar as componentes e resolver para \( k \)*
1. **Para $x$:**
   $$
   6 = k \cdot (-9) \implies k = -\frac{6}{9} = -\frac{2}{3}
   $$

2. **Para $y$:**
   $$
   -2 = k \cdot 3 \implies k = -\frac{2}{3}
   $$

3. **Para $z$:**
   $$
   4 = k \cdot (-6) \implies k = -\frac{4}{6} = -\frac{2}{3}
   $$

**Conclusão:** Todas as componentes resultam no mesmo $( k = -\frac{2}{3} )$.  

---

###### **Passo 3 )** - *Interpretação*
Como $( k = -\frac{2}{3} )$ é **Negativo**, os vetores são **Paralelos com sentidos opostos** / Antiparalelos.  
- Podemos escrever:  
  $$
  \vec{u} = -\frac{2}{3} \cdot \vec{v}
  $$

---

**Passo 4: Representação Gráfica (Ideia Visual)**
- Se $(\vec{v})$ aponta para uma direção, $(\vec{u})$ aponta na **direção oposta**, com **2/3 do comprimento**.  
```

---

>[!error] **Ex )** - *Vetores Não Paralelos* 

---
##### *Exemplo 02)*

```ad-quote
title: **Def**


###### **Dados os Vetores:**
1. $$\vec{a} = (2, 3, 1) \ \ e \ \ \vec{b} = (4, 1, 5)$$

---

###### **Passo 1 )** - *Verificar se um é múltiplo escalar do outro*

Queremos encontrar um escalar \( k \) tal que:

2. $$\vec{a} = k \cdot \vec{b}$$

Isso significa:

3. $$(2, 3, 1) = k \cdot (4, 1, 5)$$

---

###### **Passo 2 )** - *Igualar as componentes e resolver para \( k \)*
1. **Para $x$:**
    $$
    2 = k \cdot 4 \implies k = \frac{2}{4} = \frac{1}{2}
    $$

2. **Para $y$:**
    $$
    3 = k \cdot 1 \implies k = 3
    $$

3. **Para $z$:**
    $$
    1 = k \cdot 5 \implies k = \frac{1}{5}
    $$

**Conclusão:** Os valores de \( k \) obtidos para cada componente são **diferentes** ($\frac{1}{2} \neq 3 \neq \frac{1}{5}$).

---

###### **Passo 3 )** - *Interpretação*
Como **não existe um único escalar** \( k \) que satisfaça a igualdade para todas as componentes, os vetores $\vec{a}$ e $\vec{b}$ **Não São Paralelos**. Isso significa que eles apontam em direções distintas e não estão sobre a mesma linha ou linhas paralelas.
- Não podemos escrever $\vec{a}$ como um múltiplo escalar de $\vec{b}$ (ou vice-versa).

---

**Passo 4: Representação Gráfica (Ideia Visual)**
- Os vetores $\vec{a}$ e $\vec{b}$ terão direções diferentes no espaço tridimensional. Se suas origens coincidirem, eles formarão um ângulo entre si que não será $0^\circ$ nem $180^\circ$.
```

---

