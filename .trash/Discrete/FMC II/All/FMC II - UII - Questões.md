---
banner: "![[Pasted image 20260311140138.png]]"
---

---

**Q1 | Inversa**

Teorema
* Se $R \subseteq A \times B$, então $(R^{-1})^{-1} = R$.

1. Seja $(a,b)$ um par ordenado arbitrário.

2. Pela definição de relação inversa, o par $(a,b)$ pertence ao conjunto $(R^{-1})^{-1}$ _se, e somente se_, o seu par espelhado $(b,a)$ pertence ao conjunto $R^{-1}$.

3. Novamente, aplicando a definição de relação inversa sobre $R^{-1}$, a conexão $(b,a)$ pertence a $R^{-1}$ _se, e somente se_, o par original $(a,b)$ pertence ao conjunto $R$.

4. Como a relação bicondicional foi mantida intacta em todas as transições lógicas, provamos que todo elemento de $(R^{-1})^{-1}$ está em $R$, e que todo elemento de $R$ está em $(R^{-1})^{-1}$.

5. Portanto, pelo axioma da extensionalidade, a igualdade está provada: $(R^{-1})^{-1} = R$.

---
---

**Q2 | Domínio | Imagem**

Teorema
- Se $R \subseteq A \times B$, então $Dom(R^{-1}) = Ran(R)$.

1. Seja $y$ um elemento arbitrário.

2. Pela definição formal de domínio de uma relação, o elemento $y$ pertence a $Dom(R^{-1})$ _se, e somente se_, existe um elemento $x \in A$ tal que o par ordenado $(y,x)$ pertence a $R^{-1}$.

3. Pela definição formal de relação inversa, a conexão $(y,x)$ pertence a $R^{-1}$ _se, e somente se_, o seu reflexo espelhado $(x,y)$ pertence à relação original $R$.

4. Pela definição formal de imagem (ou _range_), a existência de um elemento $x \in A$ que mapeia para $y$ na forma $(x,y)$ dentro do conjunto $R$ ocorre _se, e somente se_, o elemento $y$ pertence a $Ran(R)$.

5. Como o encadeamento bicondicional foi preservado intacto do início ao fim da dedução, fica provado de forma simultânea que todo elemento do domínio da inversa é um elemento da imagem da original, e vice-versa.

6. Portanto, pelo axioma da extensionalidade, a igualdade estrutural dos conjuntos está matematicamente selada: $Dom(R^{-1}) = Ran(R)$.

---
---

**Q3 | Composta | Inversa**

Teorema
- $(S \circ R)^{-1} = R^{-1} \circ S^{-1}$

1. Seja $(z,x)$ um par ordenado arbitrário.

2. Pela definição de relação inversa, o par $(z,x)$ (pertence) a $(S \circ R)^{-1}$ _se, e somente se_, o seu par espelhado $(x,z)$ (pertence) ao conjunto $S \circ R$.

3. Pela definição formal de relação composta, o par $(x,z)$ (pertence) a $S \circ R$ _se, e somente se_, existe um elemento intermediário $y$ tal que a conexão inicial $(x,y)$ (pertence) a $R$, e a conexão final $(y,z)$ (pertence) a $S$.

4. Pela definição de relação inversa, a pertinência de $(x,y)$ em $R$ ocorre _se, e somente se_, o par espelhado $(y,x)$ (pertence) a $R^{-1}$. De forma estritamente análoga, a pertinência de $(y,z)$ em $S$ ocorre _se, e somente se_, o par espelhado $(z,y)$ (pertence) a $S^{-1}$.

5. Substituindo essas equivalências no nosso passo lógico, temos que a operação ocorre _se, e somente se_, existe um $y$ tal que $(z,y)$ (pertence) a $S^{-1}$ e, em seguida, $(y,x)$ (pertence) a $R^{-1}$.

6. Pela definição formal de relação composta, a existência dessa ponte intermediária onde $S^{-1}$ atua primeiro e $R^{-1}$ atua na sequência ocorre _se, e somente se_, o par contínuo $(z,x)$ (pertence) a $R^{-1} \circ S^{-1}$.

7. Como a cadeia de equivalências lógicas (bicondicionais) foi rigorosamente mantida de ponta a ponta sem quebras, provamos simultaneamente a dupla inclusão. Portanto, $(S \circ R)^{-1} = R^{-1} \circ S^{-1}$.

---
---

**Q4 | Inversa | Injetiva**

Teorema
- Seja $R ⊆ A × B$. $R^{-1}$ é funcional se e somente se $R$ é injetiva.

Ida: Se $R^{-1}$ é funcional então R é injetiva. 
- Hip: $R^{-1}$ é uma relação funcional.

1. Suponha os pares ordenados $(x,z)$ e $(y,z)$ pertencentes a $R$.
   
2. Pela definição formal de relação inversa, se esses pares pertencem a $R$, obrigatoriamente os seus espelhados $(z,x)$ e $(z,y)$ pertencem a $R^{-1}$.
   
3. Por hipótese, sabemos que $R^{-1}$ é _funcional_. Pela definição de funcionalidade, se um mesmo elemento do domínio (neste caso, $z$) mapeia para dois elementos do contradomínio (neste caso, $x$ e $y$) dentro do conjunto $R^{-1}$, então obrigatoriamente esses elementos são idênticos. Logo, $x = y$.
   
4. Como partimos de $(x,z)$ e $(y,z)$ em $R$ e, utilizando a hipótese, provamos que $x = y$, atestamos que nenhum elemento da imagem de $R$ é mapeado por mais de um elemento distinto do domínio. Portanto, por definição, $R$ é injetiva.

Volta: Se $R$ é injetiva então $R^{-1}$ é funcional. 
- Hip: $R$ é uma relação injetiva. 

1. Suponha os pares ordenados $(z,x)$ e $(z,y)$ pertencentes a $R^{-1}$.

2. Pela definição formal de relação inversa, se $(z,x)$ e $(z,y)$ pertencem a $R^{-1}$. obrigatoriamente os seus pares espelhados $(x,z)$ e $(y,z)$ pertencem à relação original $R$.

3. Por hipótese, $R$ é uma relação injetiva. Pela definição de injetividade, se dois pares ordenados mapeiam para a mesma imagem (neste caso, $z$), os elementos originais do domínio devem ser estritamente o mesmo. Logo, obrigatoriamente, $x = y$.

4. Como partimos de $(z,x)$ e $(z,y)$ em $R^{-1}$ e provamos que $x = y$, atestamos que um único elemento $z$ no domínio de $R^{-1}$ não mapeia para destinos múltiplos no contradomínio. Portanto, fica provado que a relação $R^{-1}$ é funcional.

---

```ad-done
title:
#### **Lista ) -** 11MAI e 13 MAI
```

---

**( Q1 | Simétrica | Diferença entre conjuntos )**

Teorema:
- Sejam $R_1$ e $R_2$ relações sobre $A$. Prove ou refute: Se $R_1$ e $R_2$ são simétricas, então $R_1 - R_2$ é simétrica.

1. Seja $(a,b)$ um par ordenado arbitrário pertencente a $R_1 - R_2$.

2. Pela definição formal de diferença entre relações, a pertinência a esse conjunto indica obrigatoriamente que $(a,b) \in R_1$ e $(a,b) \notin R_2$.

3. Por hipótese, $R_1$ é uma relação simétrica. Logo, como $(a,b) \in R_1$, a definição de simetria garante diretamente que a sua inversão $(b,a) \in R_1$.

4. Por hipótese, $R_2$ também é uma relação simétrica. A definição de simetria estabelece que a presença de um par exige a presença do seu inverso. Como sabemos pelo passo 2 que o par original $(a,b) \notin R_2$, a contrapositiva da simetria obriga a concluir que o par invertido $(b,a) \notin R_2$.

5. Consolidando as deduções dos passos 3 e 4, obtemos simultaneamente as restrições $(b,a) \in R_1$ e $(b,a) \notin R_2$.

6. Pela definição formal de diferença, a coexistência estrita dessas duas condições sobre o mesmo elemento implica que o par $(b,a)$ pertence ao conjunto $R_1 - R_2$.

7. Dessa forma, partimos da premissa de um par arbitrário $(a,b) \in R_1 - R_2$ e deduzimos algebricamente que o seu espelhamento $(b,a) \in R_1 - R_2$. Portanto, a relação $R_1 - R_2$ preserva a propriedade simétrica.

---

> [!done] _New_

---

**( Q2 | Domínio | Composta )**

Teorema:
- Sejam $R ⊆ A × B$ e $S ⊆ B × C$. Mostre que $Dom(S ◦ R) ⊆ Dom(R)$

- Seja $x$ um elemento arbitrário pertencente a $\text{Dom}(S \circ R)$.
    
- Pela definição formal de domínio, se $x \in \text{Dom}(S \circ R)$, obrigatoriamente existe um elemento $y$ tal que o par $(x,y) \in S \circ R$.
    
- Pela definição de composição de relações, se $(x,y) \in S \circ R$, obrigatoriamente existe um elemento intermediário $z$ tal que o primeiro passo ocorre em $R$ com o par $(x,z) \in R$, e o segundo passo ocorre em $S$ com o par $(z,y) \in S$.
    
- Observando exclusivamente a primeira parte dessa dedução, temos que o par $(x,z) \in R$. Pela definição de domínio, a existência de um destino $z$ mapeado a partir de $x$ implica diretamente que $x \in \text{Dom}(R)$.
    
- Portanto, partimos de um elemento arbitrário $x$ pertencente a $\text{Dom}(S \circ R)$ e provamos dedutivamente que $x \in \text{Dom}(R)$. Logo, a inclusão $\text{Dom}(S \circ R) \subseteq \text{Dom}(R)$ está provada e a proposição é verdadeira.

---

> [!done] _New_

---

**( Q3 | Total | Composta )**

Teorema:
- Sejam $R ⊆ A × B$ e $S ⊆ B × C$. Se $R$ e $S$ são totais, então $A \subseteq \text{Dom}(S \circ R)$

1. Seja $x$ um elemento arbitrário pertencente ao conjunto $A$.

2. Por hipótese, $R$ é uma relação total definida em $A \times B$. Logo, obrigatoriamente existe um elemento $y \in B$ tal que o par $(x,y) \in R$.

3. Por hipótese, $S$ é uma relação total definida em $B \times C$. Como atestamos a existência de $y \in B$, obrigatoriamente existe um elemento $z \in C$ tal que o par $(y,z) \in S$.

4. Dessa forma, pela definição formal de relação composta, a coexistência sucessiva de $(x,y) \in R$ e $(y,z) \in S$ garante a existência do salto direto $(x,z) \in S \circ R$.

5. Pela definição formal de domínio de uma relação, o fato de $(x,z) \in S \circ R$ implica diretamente que a sua origem $x \in \text{Dom}(S \circ R)$.

6. Portanto, como partimos de um elemento arbitrário $x \in A$ e demonstramos dedutivamente que $x$ também está presente em $\text{Dom}(S \circ R)$, a inclusão $A \subseteq \text{Dom}(S \circ R)$ está matematicamente provada.

---

> [!done] _New_

---

**( Q4 | Ordem Total | Minimal | Unicidade)**

Teorema:
- Seja $R ⊆ A × A$ uma relação parcial e $B ⊆ A$. Se $R$ é uma relação de ordem total e $b$ é um elemento minimal de $B$, então b é o único elemento minimal de $B$.

1. Suponha, por hipótese, que o conjunto $B$ possua dois elementos minimais distintos, os quais denominaremos $a$ e $b$.

2. Por hipótese, $R$ é uma relação de ordem total. Portanto, para todo $a,b \in B$, a propriedade da comparabilidade garante que $aRb$ _ou_ $bRa$.

3. _Caso 1_: Se a relação for $aRb$. Por hipótese, o elemento $b$ é minimal. Portanto, para que a afirmação $aRb$ seja verdadeira em um conjunto onde $b$ não pode ser antecedido por elementos distintos, obrigatoriamente $a = b$.

4. _Caso 2_: Se a relação for $bRa$. Por hipótese, o elemento $a$ também é minimal. Portanto, de forma análoga, para que a afirmação $bRa$ não viole a minimalidade de $a$, obrigatoriamente $a = b$.

5. Como a restrição imposta pela ordem total (comparabilidade) exige a ocorrência obrigatória de pelo menos um dos dois cenários de conexão, e em ambos os cenários a definição de minimalidade colapsa as variáveis em uma igualdade algébrica incontornável, fica matematicamente provado que $a = b$.

6. Portanto, assumir a existência de dois elementos minimais resulta na confirmação algébrica de que eles representam o mesmo elemento. Logo, o elemento minimal $b$ é único.

---

> [!done] _New_

---
###### **( Q5 | Composta | União de conjuntos )**

Teorema
- $(S \cup T) \circ R = (S \circ R) \cup (T \circ R)$

Ida: $(S \cup T) \circ R \subseteq (S \circ R) \cup (T \circ R)$

1. Seja $(a,b)$ um par ordenado arbitrário pertencente a $(S \cup T) \circ R$.

2. Pela definição formal de relação composta, obrigatoriamente existe um elemento intermediário $y$ tal que o primeiro passo ocorre em $R$, ou seja, $(a,y) \in R$, e o segundo passo ocorre na união, ou seja, $(y,b) \in (S \cup T)$.

3. Pela definição de união de conjuntos, se $(y,b) \in (S \cup T)$, então $(y,b) \in S$ _ou_ $(y,b) \in T$.

4. Temos agora dois cenários possíveis a partir do mesmo ponto de partida $(a,y) \in R$:

5. Caso 1: Se $(a,y) \in R$ e $(y,b) \in S$, então, pela definição de composição, o par original $(a,b) \in (S \circ R)$.

6. Caso 2: Se $(a,y) \in R$ e $(y,b) \in T$, então, de forma análoga, $(a,b) \in (T \circ R)$.

7. Como o par $(a,b)$ obrigatoriamente pertence a um resultado _ou_ ao outro, pela definição de união, concluímos que $(a,b) \in (S \circ R) \cup (T \circ R)$.

8. Logo, a inclusão $(S \cup T) \circ R \subseteq (S \circ R) \cup (T \circ R)$ está provada.

Volta: $(S \circ R) \cup (T \circ R) \subseteq (S \cup T) \circ R$

1. Seja $(a,b)$ um par ordenado arbitrário pertencente a $(S \circ R) \cup (T \circ R)$.

2. Pela definição de união, $(a,b) \in (S \circ R)$ _ou_ $(a,b) \in (T \circ R)$.

3. Caso 1: Se $(a,b) \in (S \circ R)$, então, pela definição formal de relação composta, obrigatoriamente existe um elemento $y$ tal que $(a,y) \in R$ e $(y,b) \in S$.

4. Caso 2: Se $(a,b) \in (T \circ R)$, então, pela definição formal de relação composta, obrigatoriamente existe um elemento $y$ tal que $(a,y) \in R$ e $(y,b) \in T$.

5. Pela definição de união, se $(y,b) \in S$ _ou_ $(y,b) \in T$, então $(y,b) \in (S \cup T)$.

6. Novamente pela definição de relação composta, se $(y,b) \in (S \cup T)$ e $(a,y) \in R$, então $(a,b) \in (S \cup T) \circ R$.

7. Dessa forma, partimos de um par ordenado arbitrário pertencente a $(S \circ R) \cup (T \circ R)$ e chegamos em $(a,b) \in (S \cup T) \circ R$. Portanto, a inclusão reversa está confirmada e a proposição de igualdade é verdadeira.

---

> [!done] _New_

---
###### **( Q8 | União de conjunto | Ordem Parcial ) - Tipo 6**

Teorema:
- Suponha que $R_1$ e $R_2$ sejam ordens parciais em A. $R_1 ∪ R_2$ deve ser uma ordem parcial em A?

1. Contra exemplo! 

---

> [!done] _New_

---
###### **( Q9 | Ordem Parcial | Inversa ) - Tipo 5**

Teorema: 
- Suponha que $R$ seja uma ordem parcial em $A$. $R^{−1}$ também é uma ordem parcial em $A$?

Intro:
* Para atestar que $R^{-1}$ é uma ordem parcial, é obrigatório provar de forma sequencial que ela herda as três propriedades estruturais de $R$: reflexividade, antissimétrica e transitividade.

Prova para reflexibilidade:

1. Seja $x$ um elemento arbitrário pertencente ao conjunto $A$. 

2. Por hipótese, $R$ é uma ordem parcial, logo possui o comportamento reflexivo. Portanto, o par $(x,x) \in R$. 

3. Pela definição formal de relação inversa, ao espelharmos as coordenadas do par original, obtemos exatamente o mesmo par $(x,x) \in R^{-1}$. 

4. Como todo $x \in A$ possui a conexão em espelho em $R^{-1}$, fica provado que a relação inversa é reflexiva.

Prova para antissimetria:

1. Sejam $(x,y) \in R^{-1}$ e $(y,x) \in R^{-1}$. 

2. Pela definição de relação inversa, a presença desses dois caminhos espelhados garante obrigatoriamente que as suas origens invertidas pertencem a $R$. Logo, extraímos que $(y,x) \in R$ e $(x,y) \in R$. 

3. Por hipótese, $R$ é uma ordem parcial e, consequentemente, antissimétrica. A coexistência simultânea de caminhos de ida e volta entre as mesmas variáveis em $R$ força a igualdade algébrica estrita $x = y$. 

4. Como a suposição de ida e volta no cenário de $R^{-1}$ colapsou as variáveis na mesma igualdade, fica provado que a relação inversa mantém a antissimetria.

Prova para transitividade:

1. Sejam os pares encadeados $(x,y) \in R^{-1}$ e $(y,z) \in R^{-1}$. 

2. Pela definição de relação inversa, os componentes espelhados devem constar na relação de origem. Logo, deduzimos que $(y,x) \in R$ e $(z,y) \in R$. 

3. Para visualizar a mecânica, reordenamos a sequência temporal dessa corrente dentro do conjunto $R$, obtendo: $(z,y) \in R$ e $(y,x) \in R$. 

4. Por hipótese, $R$ é uma ordem parcial e, portanto, transitiva. A ocorrência dessa corrente sequencial conectada pelo elemento intermediário $y$ aciona o atalho obrigatório entre a origem e o destino final. Logo, $(z,x) \in R$. 

5. Aplicando a definição de relação inversa uma última vez sobre esse atalho de fechamento, se $(z,x) \in R$, então a sua contraparte $(x,z) \in R^{-1}$. 

6. Como partimos do encadeamento $(x,y)$ e $(y,z)$ em $R^{-1}$ e o desenvolvimento algébrico atestou a presença do atalho $(x,z) \in R^{-1}$, fica provado que a relação inversa é transitiva.

Conclusão: 

- Como as deduções lógicas atestaram a validade inquebrável da reflexividade, antissimetria e transitividade, a proposição é verdadeira. A relação $R^{-1}$ configura uma ordem parcial em $A$.

---

> [!done] _New_

---
###### **( Q10 | Intersecção de conjuntos | Inversa ) - Tipo 5**

Teorema:
- Suponha que $R$ e $S$ sejam relações de $A$ para $B$. $(R ∩ S)^{−1} = R^{−1} ∩ S^{−1}$

Ida: $(R ∩ S)^{−1} \subseteq R^{−1} ∩ S^{−1}$

1. Seja $(a,b)$ um par ordenado arbitrário pertencente a $(R \cap S)^{-1}$.

2. Pela definição formal de relação inversa, se $(a,b) \in (R \cap S)^{-1}$, então obrigatoriamente o seu inverso espelhado $(b,a) \in (R \cap S)$.

3. Pela definição de interseção entre conjuntos, se $(b,a) \in (R \cap S)$, então $(b,a) \in R$ _e_ $(b,a) \in S$.

4. Novamente pela definição de relação inversa, se $(b,a) \in R$, então a sua contraparte $(a,b) \in R^{-1}$. De forma estritamente análoga, se $(b,a) \in S$, então $(a,b) \in S^{-1}$.

5. Novamente pela propriedade da interseção de conjuntos, a coexistência restrita de $(a,b) \in R^{-1}$ _e_ $(a,b) \in S^{-1}$ obriga que $(a,b) \in (R^{-1} \cap S^{-1})$.

6. Logo, partimos de um par ordenado $(a,b) \in (R \cap S)^{-1}$ e provamos dedutivamente que o mesmo está contido em $(R^{-1} \cap S^{-1})$. Portanto, a inclusão $(R \cap S)^{-1} \subseteq (R^{-1} \cap S^{-1})$ está matematicamente provada.

 Volta: $R^{-1} \cap S^{-1} \subseteq (R \cap S)^{-1}$

1. Seja $(a,b)$ um par ordenado arbitrário pertencente a $R^{-1} \cap S^{-1}$.

2. Pela definição formal de interseção de conjuntos, a pertinência a esse conjunto exige obrigatoriamente que $(a,b) \in R^{-1}$ _e_ $(a,b) \in S^{-1}$.

3. Pela definição de relação inversa, se $(a,b) \in R^{-1}$, então o seu inverso espelhado $(b,a) \in R$. De forma estritamente análoga, se $(a,b) \in S^{-1}$, então $(b,a) \in S$.

4. Consolidando as deduções do passo anterior, temos a coexistência de $(b,a) \in R$ _e_ $(b,a) \in S$. Novamente pela definição de interseção, isso implica diretamente que o par original se encontra na intersecção dos conjuntos originais. Logo, $(b,a) \in (R \cap S)$.

5. Aplicando a definição de relação inversa uma última vez, se o par $(b,a) \in (R \cap S)$, a sua contraparte espelhada pertence obrigatoriamente ao inverso dessa relação. Portanto, $(a,b) \in (R \cap S)^{-1}$.

6. Dessa forma, partimos de um par arbitrário $(a,b) \in R^{-1} \cap S^{-1}$ e provamos dedutivamente que o mesmo está contido em $(R \cap S)^{-1}$. Portanto, a inclusão reversa $R^{-1} \cap S^{-1} \subseteq (R \cap S)^{-1}$ está confirmada.


Conclusão

- Como a demonstração de _ida_ estabeleceu a contenção $(R \cap S)^{-1} \subseteq R^{-1} \cap S^{-1}$ e a demonstração de _volta_ atestou a contenção recíproca $R^{-1} \cap S^{-1} \subseteq (R \cap S)^{-1}$, a exigência da dupla inclusão foi plenamente satisfeita. Está provada a igualdade de conjuntos $(R \cap S)^{-1} = R^{-1} \cap S^{-1}$.

---

```ad-done
title: 
#### **MULTIPROVA ) -** 16MAI-FMC2
```

---
###### **( Q1 | Composta | Funcional ) - Tipo 5**

Sejam $R$ e $S$ relações tais que $R$ é de $A$ para $B$ e $S$ é de $B$ para $C$. Mostre que:

Teorema: 
- a) Se $R$ e $S$ são funcionais, então $S \circ R$ é funcional.

1. Suponha dois pares ordenados arbitrários $(x,y)$ e $(x,z)$ pertencentes a $(S \circ R)$.

2. Pela definição formal de relação composta, a existência desses caminhos garante a existência de elementos intermediários. Logo, existem $a$ e $b$ tais que $(x,a) \in R$ e $(a,y) \in S$, e de forma análoga, $(x,b) \in R$ e $(b,z) \in S$.

3. Por hipótese, $R$ é uma relação funcional. Como temos os pares $(x,a) \in R$ e $(x,b) \in R$ partindo da mesma origem, a definição de funcionalidade obriga que os destinos sejam iguais. Logo, $a = b$.

4. Como atestamos a igualdade $a = b$, podemos substituir a variável $b$ por $a$ na segunda etapa do mapeamento. Dessa forma, as premissas $(a,y) \in S$ e $(b,z) \in S$ transformam-se em $(a,y) \in S$ e $(a,z) \in S$.

5. Por hipótese, $S$ também é uma relação funcional. Como temos dois pares com a mesma origem $a$ mapeando para destinos possivelmente distintos em $S$, a propriedade funcional colapsa os destinos obrigatoriamente na igualdade $y = z$.

6. Logo, partimos do pressuposto da existência de dois pares $(x,y), (x,z) \in (S \circ R)$ e atestamos dedutivamente que $y = z$. Portanto, está provado que a relação composta $S \circ R$ é funcional.

Teorema: 
- b) Se $R$ e $S$ são totais, então $S \circ R$ é total.

1. Seja $a$ um elemento arbitrário pertencente a $A$.

2. Por hipótese, $R$ é uma relação total definida de $A$ para $B$. Logo, dado que $a \in A$, por definição de relação total, obrigatoriamente existe um $b \in B$ tal que $(a,b) \in R$.

3. Por hipótese, $S$ é uma relação total definida de $B$ para $C$. Logo, dado que o passo anterior atestou a existência de $b \in B$, por definição de relação total, existe um $c \in C$ tal que $(b,c) \in S$.

4. Pela definição formal de relação composta, a coexistência das conexões conectadas $(a,b) \in R$ e $(b,c) \in S$ garante dedutivamente a existência do par contínuo $(a,c) \in S \circ R$.

5. Pela definição de domínio da relação, se $(a,c) \in S \circ R$, então a origem $a \in \text{Dom}(S \circ R)$.

6. Como partimos de um elemento $a$ arbitrário pertencente a $A$ e inferimos algebricamente que $a \in \text{Dom}(S \circ R)$, a inclusão $A \subseteq \text{Dom}(S \circ R)$ está provada, confirmando que a relação composta $S \circ R$ é total.

---

```ad-done
title: 
#### **12.1 ) -** Outros exerc ́ıcios
```

---

(e) Suponha que $R$ é uma relação de equivalência em $A$, $S$ é uma relação de equivalência em $B$ e $A \cap B = \varnothing$.

i. Prove que $R \cup S$ é uma relação de equivalência em $A \cup B$.  
ii. Prove que, para todo $x \in A$,  
$[x]_{R \cup S} = [x]_R$,

1. Seja $x$ um elemento arbitrário pertencente a $[x]_{R \cup S}$.
2. Pela definição de classe de equivalência, se $x \in [x]_{R \cup S}$, então 

---

> [!done] _New_

---
Teorema:
- Suponha que $R$ é uma relação de equivalência em $A$, $S$ é uma relação de equivalência em $B$ e $A \cap B = \varnothing$. Prove que $R \cup S$ é uma relação de equivalência em $A \cup B$.  

Reflexiva:

1. Seja $a$ um elemento arbitrário pertencente a $A \cup B$.

2. Pela definição formal de união de conjuntos, a pertinência desse elemento dita que $a \in A$ _ou_ $a \in B$. Diante dessa disjunção lógica, a prova subdivide-se em dois casos estruturais.

3. _Caso 1_: Assumindo que $a \in A$. Por hipótese, $R$ é uma relação de equivalência sobre o conjunto $A$ e, consequentemente, reflexiva. Logo, o par $(a,a) \in R$.

4. _Caso 2_: Assumindo que $a \in B$. Por hipótese, $S$ é uma relação de equivalência sobre o conjunto $B$ e, consequentemente, reflexiva. Logo, o par $(a,a) \in S$.

5. A consolidação dos dois casos garante que obrigatoriamente $(a,a) \in R$ _ou_ $(a,a) \in S$. Pela definição de união de conjuntos, a ocorrência de pelo menos uma dessas pertinências atesta que o par $(a,a) \in (R \cup S)$.

6. Como a extração de um elemento arbitrário $a \in A \cup B$ forçou dedutivamente o mapeamento do par $(a,a) \in (R \cup S)$, a propriedade reflexiva da relação unida está matematicamente provada.

Simétrica:

1. Seja $(a,b)$ um par ordenado arbitrário pertencente a $(R \cup S)$.

2. Pela definição formal de união de conjuntos, se $(a,b) \in (R \cup S)$, então $(a,b) \in R$ _ou_ $(a,b) \in S$. Diante dessa disjunção lógica, a prova subdivide-se em dois casos.

3. _Caso 1_: Assumindo que $(a,b) \in R$. Por hipótese, $R$ é uma relação de equivalência sobre o conjunto $A$ e, consequentemente, simétrica. Logo, por definição de simetria, obrigatoriamente o par $(b,a) \in R$.

4. _Caso 2_: Assumindo que $(a,b) \in S$. Por hipótese, $S$ é uma relação de equivalência sobre o conjunto $B$ e, consequentemente, simétrica. Logo, por definição de simetria, obrigatoriamente o par $(b,a) \in S$.

5. A consolidação dos dois casos garante que, independentemente da rota original, obrigatoriamente $(b,a) \in R$ _ou_ $(b,a) \in S$. Pela definição de união de conjuntos, a ocorrência dessa disjunção atesta que $(b,a) \in (R \cup S)$.

6. Como partimos de um par ordenado arbitrário $(a,b) \in (R \cup S)$ e deduzimos algebricamente que o seu inverso espelhado $(b,a) \in (R \cup S)$, está provado que a relação unida é simétrica.

Transitiva:

1. Sejam $(a,b)$ e $(b,z)$ pertencentes a $R \cup S$. 
   
2. Pela definição formal de união de conjuntos, se $(a,b)$ e $(a,z)$, então $(a,b), (a,z) \in R$ ou $(a,b), (a,z) \in S$. Logo, diante dessa disjunção lógica a prova se divide sem dois casos.
   
3. Suponha, por absurdo, o caso misto em que $(a,b) \in R$ e $(b,z) \in S$. Como $R \subseteq A \times A$, o elemento intermediário $b \in A$. Como $S \subseteq B \times B$, o mesmo elemento intermediário $b \in B$. Logo, $b \in (A \cap B)$. Por hipótese do teorema, $A \cap B = \emptyset$. A coexistência do elemento em conjuntos disjuntos gera uma impossibilidade lógica. O cenário inverso ($(a,b) \in S$ e $(b,z) \in R$) gera o mesmo absurdo. Portanto, os cruzamentos mistos são impossíveis.

4. Diante da impossibilidade atestada, a relação força o confinamento das variáveis. Restam estritamente dois cenários viáveis para a prova: ambos os pares pertencem a $R$, ou ambos pertencem a $S$.
   
5. Caso 1: Assumindo que $(a,b), (a,z) \in R$. Por hipótese, $R$ é uma relação de equivalência sobre o conjunto $A$, consequentemente transitiva. Logo, pela definição formal de relação transitiva, obrigatoriamente o par ordenado $(a,z) \in R$. 
   
6. Caso 2: Assumindo que $(a,b), (a,z) \in S$. Por hipótese, $S$ é uma relação de equivalência sobre o conjunto $S$, consequentemente transitiva. Logo, pela definição formal de relação transitiva, obrigatoriamente o par ordenado $(a,z) \in S$. 
   
7. A consolidação dos dois casos garante que obrigatoriamente $(a,z) \in R$ ou $(a,z) \in S$. Logo, pela definição formal de união $(a,z) \in (R \cup S)$.
   
8. Como partimos de dois pares ordenados arbitrários $(a,b)$ e $(b,z)$ pertencentes a $R \cup S$ e chegamos que o par ordenado $(a,z)$ também está presente em $R \cup S$ está provado que a relação é transitiva. 

---

> [!done] _New_

---

Suponha que $R$ é uma relação de equivalência em $A$, $S$ é uma relação de equivalência em $B$ e $A \cap B = \varnothing$. Prove que, para todo $x ∈ A$,

- a) - $[x]_{R∪S} = [x]_R$

e para todo $y ∈ B$,

- b) - $[y]_{R∪S} = [y]_S$

Prova Ida)

1. Seja $y$ um elemento arbitrário tal que $y \in [x]_{R \cup S}$.

2. Pela definição de classe de equivalência, se $y \in [x]_{R \cup S}$, então $(y,x) \in (R \cup S)$.

3. Pela definição de união de conjuntos, se $(y,x) \in (R \cup S)$, então $(y,x) \in R$ _ou_ $(y,x) \in S$. Diante dessa disjunção lógica, a prova subdivide-se.

4. _Caso 1_: Supondo que $(y,x) \in R$. Pela definição de classe de equivalência, conclui-se que $y \in [x]_R$.

5. _Caso 2_: Supondo que $(y,x) \in S$. Como, por hipótese, o elemento de referência $x \in A$ e a relação $S$ é definida estritamente em $B \times B$, a premissa de que $A \cap B = \emptyset$ inviabiliza a formação de pontes com origens disjuntas. Logo, o caso colapsa em um absurdo lógico, restando como válida apenas a dedução do Caso 1.

6. Como partimos de um elemento arbitrário $y \in [x]_{R \cup S}$ e atestamos dedutivamente que o mesmo $y \in [x]_R$, a primeira inclusão está provada.

Prova Volta)

1. Seja $y$ um elemento arbitrário tal que $y \in [x]_R$.

2. Pela definição formal de classe de equivalência, essa pertinência exige obrigatoriamente que $(y,x) \in R$.

3. Pela definição de união de conjuntos, se um par ordenado pertence estruturalmente a um conjunto isolado, ele automaticamente compõe a união desse conjunto base com qualquer outro agrupamento. Logo, deduz-se que $(y,x) \in (R \cup S)$.

4. Se o par $(y,x) \in (R \cup S)$, pela definição de classe de equivalência aplicada à relação unida, a origem pertence à classe de equivalência do destino. Logo, $y \in [x]_{R \cup S}$.

5. Como partimos da premissa de que $y \in [x]_R$ e deduzimos o encadeamento até $y \in [x]_{R \cup S}$, a inclusão reversa está provada.

Conclusão 
- Como o confinamento dos elementos através da dupla inclusão foi satisfeito rigorosamente, atestamos sem saltos lógicos que a igualdade algébrica $[x]_{R \cup S} = [x]_R$ é verdadeira para todo $x \in A$.

---

> [!done] _New_

---
Teorema:
- Suponha que $R$ e $S$ são relações de equivalência em $A$. Seja $T = R \cap S$. Prove que $T$ é uma relação de equivalência em $A$.  

---

> [!done] _New_

---

Teorema:
- Suponha que $R$ e $S$ são relações de equivalência em $A$. Seja $T = R \cap S$. Prove que, para todo $x \in A$, $[x]_T = [x]_R \cap [x]_S$.

Ida:

1. Seja $y$ um elemento arbitrário tal que $y \in [x]_T$.

2. Pela definição formal de classe de equivalência, se $y \in [x]_T$, então $(y,x) \in T$.

3. Por hipótese, $T = R \cap S$. Substituindo a relação, temos que $(y,x) \in (R \cap S)$.

4. Pela definição de interseção de conjuntos, se $(y,x) \in (R \cap S)$, então $(y,x) \in R$ e $(y,x) \in S$.

5. Pela definição de classe de equivalência, se $(y,x) \in R$, então $y \in [x]_R$.

6. De forma análoga, se $(y,x) \in S$, então $y \in [x]_S$.

7. Pela definição de interseção de conjuntos, se $y \in [x]_R$ e $y \in [x]_S$, então $y \in ([x]_R \cap [x]_S)$.

8. Como partimos de $y \in [x]_T$ e deduzimos o encadeamento até $y \in ([x]_R \cap [x]_S)$, está provada a inclusão $[x]_T \subseteq ([x]_R \cap [x]_S)$.

---

> [!done] _New_

---

Teorema:
- $R \circ î_A = R$

---

```ad-done
title: 
#### **8.1 ) -** Exercícios
```

---
Questão 2 )

Teorema:
- Seja $R$ uma relação simétrica e transitiva sobre um conjunto $A$. Mostre que, se para todo $x \in A$, existe $y \in A$ tal que $xRy$, então $R$ é reflexiva.

1. Seja $x$ um elemento arbitrário pertencente a $A$.

2. Por hipótese do teorema, para todo elemento em $A$, existe um correspondente tal que a relação se aplica. Logo, garante-se a existência de um elemento $y \in A$ tal que $(x,y) \in R$.

3. Por hipótese, $R$ é uma relação simétrica. Pela definição de simetria, se atestamos que $(x,y) \in R$, obrigatoriamente $(y,x) \in R$.

4. Por hipótese, $R$ é uma relação transitiva. Como as deduções anteriores garantiram a coexistência do trajeto contínuo $(x,y) \in R$ e $(y,x) \in R$, a propriedade transitiva impõe a existência do par ordenado $(x,x) \in R$.

5. Como partimos de um único elemento arbitrário $x \in A$ e deduzimos algebricamente que $(x,x) \in R$, está provado que a relação $R$ é reflexiva.

---

> [!done] _New_

---
Questão 3 a )

Teorema:
- Ache os fechos reflexivo, simétrico e transitivo da relação $A = \{a, b, c, d\}$ e $R = \{(a, a), (a, b), (b, c), (c, d)\}$  

Fecho Reflexivo
- $S_{ref} = \{(a, a), (b, b), (c, c), (d, d), (a, b), (b, c), (c, d)\}$

Fecho Simétrico
- $S_{sim} = \{(a, a), (a, b), (b, a), (b, c), (c, b), (c, d), (d, c)\}$

Fecho Transitivo
- $S_{tran} = \{(a, a), (a, b), (b, c), (c, d), (a, c), (b, d), (a, d)\}$

---

> [!done] _New_

---
Questão 3 b )

1. Ache os fechos reflexivo, simétrico e transitivo da relação $R = \{(x, y) \in \mathbb{R} \times \mathbb{R} : x < y\}$

---

> [!done] _New_

---
Questão 4 a )

Teorema:
- Sejam $R_1$ e $R_2$ relações de ordem parcial sobre um conjunto $A$. Considere que $R_1 \subseteq R_2$, $B \subseteq A$ e $b \in B$. Se $b$ é o menor elemento de $B$ em relação à $R_1$, então $b$ é o menor elemento de $B$ em relação à $R_2$.  

1. Por hipótese do teorema, $b$ é o menor elemento do conjunto $B$ em relação à ordem parcial $R_1$.

2. Seja $x$ um elemento arbitrário pertencente a $B$.

3. Pela definição formal de menor elemento, a premissa inicial garante que a origem $b$ conecta-se a todos os elementos do referido conjunto. Logo, obrigatoriamente, o par ordenado $(b,x) \in R_1$.

4. Por hipótese algébrica, temos que $R_1 \subseteq R_2$. Pela definição de subconjunto, se atestamos o mapeamento prévio de $(b,x) \in R_1$, deduzimos infalivelmente que $(b,x) \in R_2$.

5. Como partimos de um elemento arbitrário $x \in B$ e garantimos dedutivamente que o par ordenado de conexão $(b,x)$ sobrevive intacto no conjunto $R_2$, a exigência estrutural de mapeamento universal para todo o subconjunto é satisfeita na nova relação.

6. Portanto, está provado que $b$ é o menor elemento de $B$ em relação a $R_2$.

---

> [!done] _New_

---
Questão 4 b )

Teorema:
- Sejam $R_1$ e $R_2$ relações de ordem parcial sobre um conjunto $A$. Considere que $R_1 \subseteq R_2$, $B \subseteq A$ e $b \in B$. Se $b$ é um elemento minimal de $B$ em relação à $R_1$, então $b$ é um elemento minimal de $B$ em relação à $R_2$.

1. Seja o conjunto base $A = \{1, 2\}$ e o subconjunto de avaliação $B = \{1, 2\}$.

2. Defina a ordem parcial $R_1 = \{(1,1), (2,2)\}$. Sob o escopo desta relação, atesta-se que o elemento $2$ é _minimal_, pois não existe nenhum elemento distinto posicionado abaixo dele no mapeamento direcional.

3. Defina a ordem parcial $R_2 = \{(1,1), (2,2), (1,2)\}$. A exigência de inclusão ditada pela hipótese ($R_1 \subseteq R_2$) é rigorosamente respeitada.

4. Ao avaliar o elemento $2$ sob a ótica de $R_2$, constatamos que o novo par ordenado $(1,2)$ subordina o destino à origem.

Conclusão:
- Como $1 \neq 2$, a restrição fundamental foi corrompida. O elemento $2$ destituiu-se da minimalidade.

---

> [!done] _New_

---

$A = \{2, 3, \dots, 20\}), (R = \{(x, y) : x$ e $y$ possuem a mesma quantidade de fatores primos$. Ex: $((4, 6) \in R)$ pois $(4 = 2 \cdot 2)$ e $(6 = 2 \cdot 3)$.

1. Supondo que $A$ seja uma relação de equivalência vamos achar as classes de equivalências. 

2 = 2 (1 primos) 
3 = 3 (1 primos) 
4 = 2 * 2 (2 primos) 
5 = 5 (1 primos) 
6 = 2 * 3 (2 primos) 
7 = 7 (1 primos) 4
8 = 2 * 2 * 2 (3 primos) 1 
9 = 3 * 3 (2 primos) 
10 = 5 * 2 (2 primos) 4

$P = \{ \{2,3,5,7\} \{4,6,9,10\} \{ 8 \} \}$ 

---