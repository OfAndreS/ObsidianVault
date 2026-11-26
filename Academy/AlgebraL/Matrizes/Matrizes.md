
---
## **O que é uma Matriz**

>[!quote] Sejam $m, n ∈ N*$
>Uma matriz (real) do tipo m × n (lê-se: m por n) 
>- é uma “tabela” disposta em m linhas e n colunas.
>
>Denotamos os números reais que formam a i-ésima linha de
uma matriz A por 
$$a_{i1},a_{i2},\ldots,a_{in}$$
>  
>E sua j-ésima coluna por
$$a_{1j},a_{2j},\ldots,a_{mj}.$$
>
>Assim temos:
>$$A=\begin{bmatrix}a_{11}&\ldots&a_{1n}\\\vdots&\ddots&\vdots\\a_{m1}&\ldots&a_{mn}\end{bmatrix}$$

>[!quote] **Khan:** [Matrizes](https://pt.khanacademy.org/math/algebra-home/alg-matrices)
##### _Composição_

>[!quote] $a_{ij}$
>Chamamos de entradas, de uma matriz A, os reais $a_{ij}$ que a
compõem. Poderemos indicar uma matriz A do tipo $m × n$ com
entradas  $a_{ij}$ por
> $$A=\left(a_{ij}\right)_{m\times n}$$

![[Pasted image 20240826092059.png]]

##### *Lei Fundamental Equivalente*

>[!quote] São Verdades Absolutas
>Para toda matriz $B_{n×1}$ o sistema linear $AX = B$ admite
>uma única solução
>- Não importa qual seja a matriz B (desde que tenha n linhas e 1 coluna), o sistema de equações lineares representado por AX = B sempre terá exatamente uma solução.
>  
>**Caso Uma das posteriores seja falsa**
>- O sistema linear AX = B pode não ter solução, ou pode ter infinitas soluções, dependendo da matriz B.

>[!quote] São Verdades Absolutas
>A é invertível 
>- Uma matriz é invertível se existe outra matriz, chamada de inversa, que ao ser multiplicada por A resulta na matriz identidade
>- A existência da inversa está diretamente ligada à resolução de sistemas lineares. Se uma matriz é invertível, podemos usar sua inversa para resolver o sistema AX = B de forma direta

>[!quote] São Verdades Absolutas
>det A ≠ 0
>- Se o determinante de uma matriz é diferente de zero, isso indica que a matriz é invertível.

![[Pasted image 20240826115216.png]]

---
#### **Operações Elementares**

>[!quote] Definição
>As operações sobre linhas de uma matriz podem ser usadas para resolver sistemas de equações, mas antes de analisarmos o porquê, vamos praticar um pouco.

>[!quote] **Khan:** [Operações sobre linhas de uma matriz](https://pt.khanacademy.org/math/algebra-home/alg-matrices/alg-elementary-matrix-row-operations/a/matrix-row-operations)
##### *Troca de duas linhas*

>[!quote] São Operações Elementares 
>Troca de posição entre duas linhas $l_i$ e $l_j$
> - $$(I_i\leftrightarrow I_j)$$

>[!quote] Exemplo Troca De Linhas
>Realize a operação $L_1\leftrightarrow L_2$ na matriz a seguir: 
>$$\begin{bmatrix}4&8&3\\2&4&5\\7&1&2\end{bmatrix}$$
>Solução
>
> $L_1\leftrightarrow L_2$ significa a troca entre as linhas 1 e 2
> $$\begin{bmatrix}4&8&3\\2&4&5\\7&1&2\end{bmatrix}\xrightarrow{L_{1}\leftrightarrow L_{2}}\begin{bmatrix}2&4&5\\4&8&3\\7&1&2\end{bmatrix}$$
##### *Multiplicação de uma linha por uma constante diferente de zero*

>[!quote] São Operações Elementares 
>Multiplicação de uma linha $l_i$ por um escalar $λ ≠ 0$
>- $$(I_i\to\lambda I_i)$$

>[!error] Exemplo Multiplicação Por Escalar 
>Realize a operação $3L_2\to L_2$ na matriz a seguir:
>
>$$\begin{bmatrix}6&6&1\\2&3&0\\4&5&9\end{bmatrix}$$
>Solução:
>
>$3L_2\to L_2$ Significa substituir $L_2$ a linha 2 por outra com 3 vezes o seu valor
>
>$$\begin{bmatrix}6&6&1\\2&3&0\\4&5&9\end{bmatrix}\text{se torna}\begin{bmatrix}6&6&1\\3\cdot2&3\cdot3&3\cdot0\\4&5&9\end{bmatrix}=\begin{bmatrix}6&6&1\\6&9&0\\4&5&9\end{bmatrix}$$
>
>Para indicar esta operação sobre linhas, geralmente vemos a seguinte notação:
>
>$$\begin{bmatrix}6&6&1\\2&3&0\\4&5&9\end{bmatrix}\xrightarrow{3R_{2}\to R_{2}}\begin{bmatrix}6&6&1\\6&9&0\\4&5&9\end{bmatrix}$$
##### *Adição de uma linha à outra*

>[!quote] São Operações Elementares 
>Substituição de uma linha $l_j$ por $l_j$ + $λl_i$ Sendo  $λ ≠ 0$
>- $$(I_j\to I_j+\lambda I_i)$$

>[!error] Exemplo Adição entre Linhas 
>Realize a operação $L_1+L_2\to L_2$ na matriz a seguir:
>
>$$\begin{bmatrix}2&3&4\\0&8&1\end{bmatrix}$$
>Solução
>
>$L_1+L_2\to L_2$ significa substituir a 2 linha pela soma das 1 e 2 linhas.
>
>$$\begin{bmatrix}2&3&4\\0&8&1\end{bmatrix}\text{se torna}\begin{bmatrix}2&3&4\\2+0&3+8&4+1\end{bmatrix}=\begin{bmatrix}2&3&4\\2&11&5\end{bmatrix}$$
>
>Para indicar esta operação sobre linhas, podemos utilizar a seguinte notação:
>
>$$\begin{bmatrix}2&3&4\\0&8&1\end{bmatrix}\xrightarrow{R_1+R_2\to R_2}\begin{bmatrix}2&3&4\\2&11&5\end{bmatrix}$$

---
#### **Multiplicação de Matrizes**

>[!Quote] Definição
>Essa operação só pode ser realizada se o número de colunas da primeira matriz for igual ao número de linhas da segunda matriz.
>- O resultado dessa multiplicação será uma nova matriz (a matriz produto) 
>- Com a quantidade de linhas da primeira matriz e a quantidade de colunas da segunda matriz.
>  $$\begin{bmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\\a_{31}&a_{32}\end{bmatrix}_{3\times2}\cdot\begin{bmatrix}b_{11}&b_{12}\\b_{21}&b_{22}\end{bmatrix}_{2\times2}=\begin{bmatrix}a_{11}\cdot b_{11}+a_{12}\cdot b_{21}&a_{11}\cdot b_{12}+a_{12}\cdot b_{22}\\a_{21}\cdot b_{11}+a_{22}\cdot b_{21}&a_{21}\cdot b_{12}+a_{22}\cdot b_{22}\\a_{31}\cdot b_{11}+a_{32}\cdot b_{21}&a_{31}\cdot b_{12}+a_{32}\cdot b_{22}\end{bmatrix}_{3\times2}$$
>  

>[!quote] **Khan:** [Multiplicação de matrizes](https://pt.khanacademy.org/math/precalculus/x9e81a4f98389efdf:matrices/x9e81a4f98389efdf:multiplying-matrices-by-matrices/a/multiplying-matrices)

>[!error] Exemplo 01)
>Calcule a multiplicação $A⋅B$ para as matrizes:
$$A = \begin{bmatrix}1&5\\3&2\end{bmatrix}\quad e \quad B =\begin{bmatrix}4&8\\7&0\end{bmatrix}$$
>Considere C = $A⋅B$ Como o número de linhas de A e o número de colunas de B, a ordem de C é 2x2.
>$$C=\begin{bmatrix}c_{11}&c_{12}\\c_{21}&c_{22}\end{bmatrix}$$
> Agora vamos encontrar cada elemento de C. Lembre-se de que cada
> elemento $c_{ij}$ corresponde a uma relação entre a linha _i_ de A e a coluna _j_ de B:
> $$\begin{bmatrix}1&5\\3&2\end{bmatrix}\cdot\begin{bmatrix}4&8\\7&0\end{bmatrix} = \begin{bmatrix}c_{11}&c_{12}\\c_{21}&c_{22}\end{bmatrix}$$
> Sendo os cálculos:
> $$c_{11}=1\cdot4+5\cdot7 = 39$$
> $$c_{12}=1\cdot8+5\cdot0 = 8$$
> $$c_{12}=1\cdot8+5\cdot0 = 8$$
> $$c_{22}=3\cdot8+2\cdot0 = 24$$
> Resultando na Matriz C: 
> $$C=\begin{bmatrix}39&8\\26&24\end{bmatrix}$$

--- 
#### **Inverso de uma Matriz**

>[!quote]
>Para Inverter uma Matriz de qualquer ordem precisamos igualar a mesma a identidade. 
>- Uma vez que uma Matriz $A$ multiplicada pelo seu inverso resulta na Matriz identidade.
>

>[!quote] **Khan:** [ Matriz inversa](https://pt.khanacademy.org/math/algebra-home/alg-matrices/alg-determinants-and-inverses-of-large-matrices/e/matrix_inverse_3x3)

>[!quote] Passo a passo
 >**Passo 1: Verifique se a matriz $A$ é invertível**
>- Uma matriz só tem inversa se for quadrada e seu determinante for diferente de zero $(\det(A)\neq0)$
>  
>**Passo 2: Escreva a matriz  $A$  ao lado da matriz identidade** 
>
>- Forme uma matriz aumentada colocando a matriz  $A$  ao lado da matriz identidade III de mesma ordem. Isso é representado como:
>
>$$\begin{bmatrix}A&|&I\end{bmatrix}$$
>
>Por exemplo, se $A$ for uma matriz $2\times2$
>
>$$\begin{bmatrix}a_{11}&a_{12}&|&1&0\\a_{21}&a_{22}&|&0&1\end{bmatrix}$$
>
>**Passo 3: Use operações elementares nas linhas**
>
>- O objetivo é transformar a matriz $A$ na identidade $I$ usando operações elementares nas linhas (troca de linhas, multiplicação de uma linha por um escalar diferente de zero e adição de múltiplos de uma linha a outra).
>
>$$\begin{bmatrix}I&|&A^{-1}\end{bmatrix}$$
>
>onde $A^{-1}$ é a inversa da matriz $A$

---
#### **Determinantes** 


> [!quote] Definição 
> Calculamos determinantes somente de matrizes quadradas, ou seja, matrizes em que a quantidade de colunas e a quantidade de linhas são iguais. 
> - Para calcular o determinante de uma matriz, precisamos analisar a ordem dela, ou seja, se ela é 1x1, 2x2, 3x3 e assim sucessivamente.
>   
>Quanto maior a sua ordem, mais difícil será encontrar o determinante.
>
>Matriz $2×2$: [Det Matriz 2x2](https://pt.khanacademy.org/math/algebra-home/alg-matrices/alg-determinant-of-2x2-matrix/v/finding-the-determinant-of-a-2x2-matrix)
>Matriz $3×3$: [Det Matriz 3x3](https://pt.khanacademy.org/math/algebra-home/alg-matrices/alg-determinants-and-inverses-of-large-matrices/e/matrix_determinant_3x3)
 
##### *Determinante Matriz 2x2* 

> [!quote] Definição
> Para uma matriz $2×2$ da forma:
> 
> $$A=\begin{bmatrix}a&b\\c&d\end{bmatrix}$$
> 
> O determinante de $A$ denotado por $det⁡(A)$ ou $|A|$ é calculado da seguinte forma:
> 
> $$\det(A)=ad-bc$$
> 
>Multiplicamos a diagonal principal e subtraímos da multiplicação da diagonal secundária

##### *Determinante Matriz 3x3* 

> [!quote] Definição
> Para uma matriz $3×3$ da forma:
> 
>$$A=\begin{bmatrix}a&b&c\\d&e&f\\g&h&i\end{bmatrix}$$
>
>O determinante de $A$ é calculado usando a Regra de Sarrus, que consiste em somar e subtrair produtos das diagonais principal e secundária. 
>
>- Repetimos as duas primeiras linhas da Matriz
>  
>$$A=\begin{bmatrix}a&b&c\\d&e&f\\g&h&i\end{bmatrix}\begin{matrix}a&b\\d&e\\g&h\end{matrix}$$
>
>- Multiplique os elementos das diagonais principais
>- Multiplique os elementos das diagonais secundárias
>- Subtraia a soma dos produtos das diagonais secundárias da soma dos produtos das diagonais principais:
>  $$\det(A)=(aei+bfg+cdh)-(ceg+bdi+afh)$$

##### *Determinante Matriz nxn* 


---