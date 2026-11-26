
---

```ad-example

#### **05 ) - Planos em Posições Particulares**
```

---

````ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

A análise dos coeficientes $(a, b, c)$ e do termo independente $(d)$ na equação geral do plano $ax+by+cz+d=0$ permite identificar rapidamente sua posição e orientação em relação aos eixos e planos do sistema cartesiano. Esses são conhecidos como casos particulares ou posições notáveis.
````

````ad-quote
title: 

##### _Casos Notáveis_

```ad-quote
title: **Def**

A seguir, são apresentados os principais casos particulares, baseados nos coeficientes nulos na equação geral do plano.

**1. Plano que passa pela Origem**
- **Condição:** O termo independente é nulo.
- **Equação:** $$ax+by+cz=0$$
- **Justificativa:** As coordenadas da origem $(0,0,0)$ satisfazem a equação: $a(0)+b(0)+c(0)=0$.
- **Exemplo (a):** $$3x+y-4z=0$$

---

**2. Plano Paralelo a um dos Eixos Coordenados**
- **Condição:** O coeficiente da variável correspondente ao eixo é nulo. O termo independente `d` deve ser não nulo $(d \neq 0)$.
- **Paralelo ao eixo x ($a=0$):** $$by+cz+d=0$$- **Paralelo ao eixo y ($b=0$):**$$ax+cz+d=0$$- **Paralelo ao eixo z ($c=0$):**$$ax+by+d=0$$- **Exemplo (b):**$$2x+3z-3=0$$ (Plano paralelo ao eixo y, pois $b=0$)

---

**3. Plano que Contém um dos Eixos Coordenados**
- **Condição:** O coeficiente da variável correspondente ao eixo é nulo, e o termo independente `d` também é nulo.
- **Contém o eixo x ($a=0, d=0$):** $$by+cz=0$$- **Contém o eixo y ($b=0, d=0$):**$$ax+cz=0$$- **Contém o eixo z ($c=0, d=0$):**$$ax+by=0$$- **Exemplo (c):**$$4x+3y=0$$ (Contém o eixo z, pois $c=0, d=0$)
- **Exemplo (d):** $$x-4z=0$$ (Contém o eixo y, pois $b=0, d=0$)

---

**4. Plano Paralelo a um dos Planos Coordenados**
- **Condição:** Os coeficientes de duas variáveis são nulos. O termo independente `d` deve ser não nulo $(d \neq 0)$.
- **Paralelo ao plano xy ($a=0, b=0$):** $$cz+d=0 \Rightarrow z = k$$- **Paralelo ao plano xz ($a=0, c=0$):**$$by+d=0 \Rightarrow y = k$$- **Paralelo ao plano yz ($b=0, c=0$):**$$ax+d=0 \Rightarrow x = k$$- **Exemplo (e):**$$x-3=0$$ (Plano paralelo ao plano yz, pois $b=0, c=0$)
````

---

```ad-example

#### **02 ) - Retas em Posições Particulares**
```

---

````ad-quote
title: **Def**

##### _Definição_

```ad-quote
title: **Def**

As posições particulares de uma reta no espaço tridimensional são determinadas pelas características de seu **vetor diretor** $\vec{v}=(a,b,c)$ e de um **ponto** $P_0(x_0, y_0, z_0)$ pelo qual ela passa. A análise de componentes nulos no vetor diretor ou de coordenadas nulas no ponto define o posicionamento da reta em relação aos eixos e planos cartesianos.
````

````ad-quote
title: **Def**

##### _Casos Notáveis_

```ad-quote
title: **Def**

Os principais casos são definidos a partir das componentes do vetor diretor $\vec{v}=(a,b,c)$.

**1. Reta Paralela a um dos Eixos Coordenados**
- **Condição:** Duas das componentes do vetor diretor são nulas.
- **Paralela ao eixo x ($b=0, c=0$):** O vetor diretor é $\vec{v}=(a,0,0)$. A reta é descrita pelas equações:
  $$\begin{cases} y = y_0 \\ z = z_0 \end{cases}$$
- **Paralela ao eixo y ($a=0, c=0$):** O vetor diretor é $\vec{v}=(0,b,0)$. A reta é descrita por:
  $$\begin{cases} x = x_0 \\ z = z_0 \end{cases}$$
- **Paralela ao eixo z ($a=0, b=0$):** O vetor diretor é $\vec{v}=(0,0,c)$. A reta é descrita por:
  $$\begin{cases} x = x_0 \\ y = y_0 \end{cases}$$

---

**2. Reta Paralela a um dos Planos Coordenados**
- **Condição:** Uma das componentes do vetor diretor é nula. A reta está contida em um plano paralelo ao plano coordenado correspondente.
- **Paralela ao plano xy ($c=0$):** O vetor diretor é $\vec{v}=(a,b,0)$. A reta está inteiramente contida no plano:
  $$z = z_0$$
- **Paralela ao plano xz ($b=0$):** O vetor diretor é $\vec{v}=(a,0,c)$. A reta está inteiramente contida no plano:
  $$y = y_0$$
- **Paralela ao plano yz ($a=0$):** O vetor diretor é $\vec{v}=(0,b,c)$. A reta está inteiramente contida no plano:
  $$x = x_0$$

---

**3. Casos Especiais de Contenção**

- **A. Reta Contida em um Plano Coordenado:**
  - **Condição:** A reta é paralela a um plano coordenado e a coordenada correspondente do ponto $P_0$ é nula.
  - **Contida no plano xy:** ($c=0, z_0=0$)
    
  $$\begin{cases} x = x_0 + at \\ y = y_0 + bt \\ z = 0 \end{cases}$$
  - **Contida no plano xz:** ($b=0, y_0=0$)
    
  $$\begin{cases} x = x_0 + at \\ y = 0 \\ z = z_0 + ct \end{cases}$$
  - **Contida no plano yz:** ($a=0, x_0=0$)
    
  $$\begin{cases} x = 0 \\ y = y_0 + bt \\ z = z_0 + ct \end{cases}$$

- **B. Os Próprios Eixos Coordenados:**
  - **Condição:** A reta é paralela a um eixo e passa pela origem $(x_0=y_0=z_0=0)$.
  - **Eixo x:** Descrito pelas equações $y=0$ e $z=0$.
  - **Eixo y:** Descrito pelas equações $x=0$ e $z=0$.
  - **Eixo z:** Descrito pelas equações $x=0$ e $y=0$.
````

---