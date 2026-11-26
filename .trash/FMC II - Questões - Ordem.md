---
banner: "![[Pasted image 20260311140138.png]]"
---

---

Q1 ) - Seja $R ⊆ A \times A$ uma relação parcial e $B ⊆ A$. Se $B$ possuir um menor elemento, esse elemento é único.

1. Suponha que $B$ possua dois menores elementos distintos, denominados $x$ e $y$.

2. Pela definição formal de menor elemento, se $x$ assume essa posição, ele obrigatoriamente antecede todos os elementos de $B$. Como $y \in B$, conclui-se que $xRy$.

3. De forma estritamente análoga, se $y$ também é classificado como menor elemento, ele antecede todos os elementos de $B$. Como $x \in B$, conclui-se que $yRx$.

4. Por hipótese, $R$ é uma relação de ordem parcial. Por definição, toda relação de ordem parcial possui a propriedade _antissimétrica_.

5. Pela definição formal de antissimétrica, a coexistência das conexões $xRy$ e $yRx$ no mesmo conjunto implica diretamente na igualdade dos elementos. Portanto, $x = y$.

6. Como assumir a existência de dois menores elementos nos forçou dedutivamente a atestar que eles são o mesmo elemento, está provado que o menor elemento de $B$, se existir, é obrigatoriamente único.

---
---

Q2 ) - Seja $R ⊆ A \times A$ uma relação parcial e $B ⊆ A$. Se $b$ é o menor elemento de $B$, então $b$ é um elemento minimal de $B$. Ademais, $b$ é o único elemento minimal de $B$.

_Parte 1: Prova de que o menor elemento é minimal_

1. Suponha que $b$ seja o menor elemento de $B$. Pela definição formal, para qualquer elemento $x \in B$, tem-se obrigatoriamente a relação $bRx$.

2. Para provar que $b$ é minimal, deve-se mostrar que não existe elemento estritamente menor que ele. Suponha, por hipótese, que exista um $x \in B$ tal que $xRb$.

3. Como $b$ é o menor elemento, a relação $bRx$ continua sendo verdadeira.

4. Por hipótese, $R$ é uma relação de ordem parcial e, portanto, antissimétrica. A existência simultânea dos caminhos $xRb$ e $bRx$ implica diretamente que $x = b$.

5. Como atestamos que qualquer elemento $x$ que ouse anteceder $b$ é, na verdade, o próprio $b$, não existe $x \in B$ com $x \neq b$ tal que $xRb$. Logo, $b$ é um elemento minimal.

_Parte 2: Prova de que o elemento minimal é único_

6. Suponha que exista um elemento minimal arbitrário $m \in B$.

7. Como $b$ é o menor elemento de $B$, por definição, ele antecede todos os elementos do conjunto. Logo, como $m \in B$, a relação $bRm$ é obrigatoriamente verdadeira.

8. Pela definição formal de elemento minimal, um elemento só é minimal se não existir nenhum outro elemento distinto que o anteceda. Como temos $bRm$, a única forma de $m$ manter o seu status de minimal é se a igualdade for verdadeira. Logo, obrigatoriamente, $b = m$.

9. Como qualquer elemento minimal $m$ assumido resulta ser o próprio $b$, está provado que $b$ é o _único_ elemento minimal de $B$.
