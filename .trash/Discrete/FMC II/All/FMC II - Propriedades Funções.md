---
banner: "- IMGs/Banner/All IA/Pasted image 20260311140138.png"
---

---

![[Pasted image 20260701211159.png]]

````ad-quote
title:

##### ** Intro ) -** Conjuntos

```ad-quote
title:
**Domínio** - $A$
- É o conjunto inteiro de partida. Ele contém todos os elementos que devem obrigatoriamente disparar uma seta.

---

**Contradomínio** - $B$
- É o conjunto inteiro de destino. Ele funciona como o universo amplo de todos os alvos possíveis para as setas da sua função.

---

**Imagem** - $Img(f)$
- É um subconjunto que _está contido_ no contradomínio. Ele abriga estritamente os alvos que realmente foram atingidos por alguma seta.

---

**Subconjunto** - $W$
- É qualquer pedaço aleatório que você escolha recortar dentro do seu contradomínio para fins de análise. Ele pode ser a imagem inteira, uma fração dela ou agrupar alvos completamente vazios.

---

**Imagem Inversa** - $f^{-1}(W)$
- É um subconjunto que _está contido_ no domínio original. Ele agrupa de forma exclusiva as origens que atiraram setas para dentro daquele seu recorte de teste $W$.

---

**Variável $x$**
- É um número isolado que _pertence_ ao domínio. Ele atua como a munição inicial ou o gatilho da sua equação matemática.

---

**Variável $f(x)$ ou $y$**
- É o resultado numérico final que _pertence_ à imagem. Ele é a marca exata deixada no alvo após a operação atravessar a sua função.
```
````

---

````ad-quote
title:

##### **01 ) -** Imagem de uma Função $f(A)$

```ad-quote
title:
Considere uma função $f: A \to B$. A imagem direta coleta todos os valores do contradomínio que são efetivamente atingidos por elementos do domínio.
```
````

````ad-quote
title:

###### A ) - Conjunto Imagem

```ad-quote
title:
É o conjunto de todos os elementos $y$ no contradomínio que possuem pelo menos uma pré-imagem no domínio.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $f(A) = \{y \in B \mid \exists x \in A, f(x) = y\}$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $y \in f(A)$. Logo, existe $x \in A$ tal que $f(x) = y$. 

Em provas de inclusão, utiliza-se essa existência para transitar do contradomínio de volta ao domínio, exibindo o elemento original.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
Seja $f: \mathbb{R} \to \mathbb{R}$ dada por $f(x) = x^2$ e $A = \{-1, 1\}$. A imagem desse subconjunto é $f(A) = \{1\}$.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 ) -** Injetividade de Funções

```ad-quote
title:
Considere uma função $f: A \to B$. A injetividade garante que elementos distintos do domínio nunca compartilham a mesma imagem.
```
````

````ad-quote
title:

###### A ) - Função Injetora

```ad-quote
title:
Elementos diferentes no domínio produzem valores diferentes no contradomínio; a igualdade das imagens força a igualdade dos argumentos.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\forall x_1, x_2 \in A, \; f(x_1) = f(x_2) \implies x_1 = x_2$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, a função é injetora. Ao supor $f(x_1) = f(x_2)$, deduz-se imediatamente que $x_1 = x_2$. 

Na prática, inicia-se a prova com a igualdade das imagens e manipula-se algebricamente até isolar a identidade dos argumentos. Se existir um contraexemplo com $x_1 \neq x_2$ mas $f(x_1)=f(x_2)$, a função não é injetora.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
A função $f: \mathbb{R} \to \mathbb{R}$, $f(x) = 2x$, é injetora porque $2x_1 = 2x_2 \implies x_1 = x_2$. Já $g(x) = x^2$ não é injetora, pois $g(-1) = g(1)$ mas $-1 \neq 1$.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 ) -** Sobrejetividade de Funções

```ad-quote
title:
Considere uma função $f: A \to B$. A sobrejetividade assegura que o contradomínio é totalmente coberto pelas imagens dos elementos do domínio.
```
````

````ad-quote
title:

###### A ) - Função Sobrejetora

```ad-quote
title:
Ocorre quando a imagem de $f$ é exatamente igual ao contradomínio $B$; todo elemento de $B$ é imagem de pelo menos um elemento de $A$.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\forall y \in B, \; \exists x \in A : f(x) = y$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, a função é sobrejetora. Para um $y \in B$ arbitrário, garante-se a existência de algum $x \in A$ que satisfaz $f(x) = y$. 

Em provas, fixa-se um $y$ genérico do contradomínio e resolve-se a equação $f(x) = y$ para exibir o $x$ correspondente. Se o valor de $x$ sempre pertencer ao domínio $A$, a função é sobrejetiva.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
Seja $f: \mathbb{R} \to \mathbb{R}_{\ge 0}$, $f(x) = x^2$. Dado $y \ge 0$, o número $x = \sqrt{y}$ pertence a $\mathbb{R}$ e satisfaz $f(x) = y$, logo $f$ é sobrejetora. Se o contradomínio fosse $\mathbb{R}$, a função não seria sobrejetora, pois números negativos nunca são atingidos.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 ) -** Bijetividade e Função Identidade $\iota_{X}$

```ad-quote
title:
Considere a combinação das propriedades de injetividade e sobrejetividade. A bijetividade caracteriza as funções que admitem uma inversa, cuja composição resulta na função identidade.
```
````

````ad-quote
title:

###### A ) - Função Bijetiva e Identidade

```ad-quote
title:
Uma função é bijetiva quando é simultaneamente injetora e sobrejetora. A função identidade $\iota_X: X \to X$ é o mapeamento que não altera os elementos: $\iota_X(x) = x$. A existência de uma inversa $f^{-1}$ está condicionada à bijetividade.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $f: A \to B$ é bijetiva $\iff$ $f$ é injetora e $f$ é sobrejetora.
- $\iota_X(x) = x$ para todo $x \in X$.
- Se $f$ é bijetiva, existe $f^{-1}: B \to A$ tal que:
    - $f^{-1} \circ f = \iota_A$  ($f^{-1}(f(x)) = x$ para todo $x \in A$)
    - $f \circ f^{-1} = \iota_B$  ($f(f^{-1}(y)) = y$ para todo $y \in B$)
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $f$ é bijetiva e $g$ é a sua inversa. Consequentemente, as composições satisfazem $(g \circ f)(x) = \iota_A(x)$ e $(f \circ g)(y) = \iota_B(y)$. 

Essas igualdades são a ferramenta central para manipulações algébricas com funções inversas. Para provar que uma candidata $g$ é de fato a inversa de $f$, basta verificar essas duas identidades.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
A função $f: \mathbb{R} \to \mathbb{R}$, $f(x) = 2x$, é bijetiva. Sua inversa é $g(x) = \frac{x}{2}$. Verificando: $(g \circ f)(x) = g(2x) = \frac{2x}{2} = x = \iota_{\mathbb{R}}(x)$ e $(f \circ g)(y) = f\!\left(\frac{y}{2}\right) = 2 \cdot \frac{y}{2} = y = \iota_{\mathbb{R}}(y)$.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 ) -** Imagem Inversa $f^{-1}(W)$

```ad-quote
title:
Considere uma função $f: A \to B$ e um subconjunto $W \subseteq B$. A pré-imagem recupera todos os elementos do domínio cujas imagens pertencem a $W$.
```
````

````ad-quote
title:

###### A ) - Conjunto Pré-Imagem

```ad-quote
title:
É o conjunto de todos os $x \in A$ que satisfazem $f(x) \in W$. Diferentemente da função inversa, a pré-imagem está definida para qualquer função, independentemente de bijetividade.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $f^{-1}(W) = \{x \in A \mid f(x) \in W\}$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $x \in f^{-1}(W)$. Pela equivalência lógica da definição, conclui-se imediatamente que $f(x) \in W$. 

Reciprocamente, se soubermos que $f(x) \in W$, deduzimos que $x \in f^{-1}(W)$.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
Seja $f: \mathbb{R} \to \mathbb{R}$, $f(x) = x^2$, e $W = [0, 1]$. Então $f^{-1}(W) = \{x \in \mathbb{R} \mid x^2 \in [0,1]\} = [-1, 1]$.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 ) -** Complemento de um Conjunto ($\overline{A}$)

```ad-quote
title:
Considere um conjunto universo $U$ e um subconjunto $A \subseteq U$. O complemento reúne exatamente os elementos do universo que não pertencem a $A$.
```
````

````ad-quote
title:

###### A ) - Conjunto Complementar

```ad-quote
title:
É o conjunto de todos os elementos do universo $U$ que estão fora de $A$, representando a negação do pertencimento a $A$ dentro daquele contexto.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $\overline{A} = U - A = \{x \in U \mid x \notin A\}$
- $x \in \overline{A} \iff x \notin A$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, $x \in \overline{A}$. Deduz-se diretamente que $x \notin A$. 

Essa negação é frequentemente utilizada em provas por contradição ou para aplicar as leis de De Morgan, transformando a afirmação sobre o complemento em uma afirmação sobre o não-pertencimento.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
Seja $U = \{1, 2, 3, 4\}$ e $A = \{2, 3\}$. O complementar de $A$ em relação a $U$ é $\overline{A} = \{1, 4\}$.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **07 ) -** Restrição de Domínio e Axiomas de Função

```ad-quote
title:
Considere uma função $f: A \to B$ e um subconjunto $C \subseteq A$. A restrição do domínio delimita a atuação da função original exclusivamente aos elementos do novo conjunto base.
```
````

````ad-quote
title:
###### A ) - Prova de Relação Funcional

```ad-quote
title:
Para demonstrar que uma relação derivada, como $g = f \cap (C \times B)$, constitui uma função matemática, exige-se a comprovação de dois axiomas operacionais inegociáveis: a _totalidade_ e a _unicidade_.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
Totalidade / Existência 
- $$\forall x \in C, \exists y \in B \mid (x, y) \in g$$

Unicidade 
- $$(x, y_1) \in g \land (x, y_2) \in g \implies y_1 = y_2$$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, a demonstração da _unicidade_ exige assumir preliminarmente que $(x, y_1) \in g$ e $(x, y_2) \in g$. Pela definição de intersecção, transfere-se o pertencimento dos pares para a função original $f$, o que força a dedução lógica de que $y_1 = y_2$. Para atestar a _totalidade_, toma-se um $x \in C$ arbitrário, aplica-se a regra de inclusão para inferir $x \in A$ e utiliza-se a garantia de mapeamento de $f$ para confirmar a existência do par $(x, y)$ na intersecção com o produto cartesiano.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
Seja a função original $f: \mathbb{R} \to \mathbb{R}$. Ao aplicar uma restrição de domínio ao subconjunto $C = \mathbb{N}$, a relação estrutural resultante $f \cap (\mathbb{N} \times \mathbb{R})$ preserva o mapeamento único e garante a cobertura de todos os naturais, mantendo o seu status de função.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **08 ) -** Função, Domínio e Contradomínio

```ad-quote
title:
Considere os conjuntos $A$ e $B$. Uma função é uma relação estrutural que mapeia cada elemento do domínio a um único correspondente no contradomínio.
```
````

````ad-quote
title:
###### A ) - Relação Funcional (Totalidade e Unicidade)

```ad-quote
title:
O domínio $A$ é o conjunto de partida, onde a função está obrigatoriamente definida para todos os seus elementos. O contradomínio $B$ é o conjunto de chegada, que abriga os possíveis valores a serem mapeados.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $f: A \to B$
- $\forall x \in A, \exists! y \in B \mid (x, y) \in f$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, tem-se uma função $f: A \to B$. Dado um elemento arbitrário $x \in A$, extrai-se imediatamente como consequência lógica inflexível que existe um, e apenas um, $y \in B$ tal que $f(x) = y$. Essa garantia de mapeamento absoluto é o motor primário para transitar variáveis entre os conjuntos em provas diretas.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
Seja $A = \{1, 2\}$ e $B = \{3, 4, 5\}$. A relação $f = \{(1, 3), (2, 4)\}$ configura uma função, pois todo elemento do domínio $A$ possui mapeamento único e exclusivo no contradomínio $B$.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **09 ) -** Composição de Funções

```ad-quote
title:
Considere as funções $f: A \to B$ e $g: B \to C$. A composição estabelece uma nova função aplicando o resultado do mapeamento interno como argumento direto para a função externa.
```
````

````ad-quote
title:
###### A ) - Aplicação Sucessiva

```ad-quote
title:
A imagem da primeira função serve como base de domínio para a segunda. O elemento extraído de $A$ é mapeado para $B$ através da lei de $f$, e esse exato resultado é transportado para $C$ através da lei de $g$.
```

```ad-quote
title:
###### Definição Formal
```

```ad-quote
title:  
- $g \circ f: A \to C$
- $(g \circ f)(x) = g(f(x))$
```

```ad-quote
title:
###### Uso da Hipótese
```

```ad-quote
title:  
Por hipótese, manipula-se um elemento submetido à composição $(g \circ f)(x)$. O desenvolvimento da prova exige o desmembramento da cadeia de fora para dentro: extrai-se primeiramente o parâmetro interno $y = f(x)$, garantindo que $y \in B$, para em seguida aplicar a função final $g(y)$, assegurando que o resultado alcance o conjunto $C$.
```
````

````ad-quote
title:
###### Ex ) Exemplo

```ad-quote
title:  
Sejam $f(x) = x + 1$ e $g(x) = x^2$. A composição avaliada para a variável $x = 2$ resulta no encadeamento direto $(g \circ f)(2) = g(f(2)) = g(3) = 9$.
```
````

---
