
---

>[!quote] **Def**
>A decomposição em frações parciais é uma técnica fundamental no cálculo de integrais de funções racionais. Ela consiste em expressar uma função racional como a soma de frações mais simples, facilitando assim a sua integração.

---

>[!tip] ## **Método Heaviside**

---
#### **Passos Gerais para Decomposição em Frações Parciais**

>[!quote] **Def**
>**Verificar o grau do numerador e denominador:**
>- Se o grau do numerador for maior ou igual ao do denominador, realizar a divisão polinomial para obter uma função racional própria.
>-  Caso contrário, prosseguir diretamente para o método de frações parciais.
>  
>---
>
>**Fatorar o denominador:**
>- Fatorar o denominador $D(x)$ em fatores lineares e/ou quadráticos irredutíveis.
>  
>---
>
>**Decompor a função em frações parciais:**
>- A forma da decomposição depende dos fatores do denominador.
>
>---
>
>**Integrar cada termo:**
>- Cada fração parcial é integrada separadamente.

---
#### **1 ) Fatores Lineares Simples**

>[!quote] **Def**
>Se $D(x) = (x-a)(x-b)$, decompomos a função racional $\frac{P(x)}{D(x)}$ como:
>
>$$\frac{P(x)}{(x-a)(x-b)} = \frac{A}{x-a} + \frac{B}{x-b}$$
>
>---
>
>**O método de Heaviside é usado para determinar A e B:**
>  * Multiplica-se ambos os lados pelo denominador comum $(x-a)(x-b)$.
>  * Para encontrar A, substitui-se $x = a$ no restante da equação.
>  * Para encontrar B, substitui-se $x = b$ na equação.

### **2. Fatores Lineares Repetidos**

>[!quote] **Def**
Se $D(x) = (x-a)^n$, a decomposição será:
>
>$$\frac{P(x)}{(x-a)^n} = \frac{A_1}{x-a} + \frac{A_2}{(x-a)^2} + \cdots + \frac{A_n}{(x-a)^n}$$
>
>---
>
>* Determina-se cada coeficiente $A_k$ resolvendo um sistema linear ou expandindo e comparando os coeficientes de $x$.

#### **3 ) Fatores Quadráticos Irredutíveis**

>[!quote] **Def**
>* Se $D(x) = (x^2 + px + q)$, a fração parcial correspondente será:
>$$\frac{A}{x^2 + px + q}$$
>Ou para fatores quadráticos repetidos:
>$$\frac{A}{x^2 + px + q} + \frac{Bx+C}{(x^2 + px + q)^2}$$
>
>---
>
>* Aqui, A, B e C são determinados resolvendo o sistema de equações obtido pela comparação de coeficientes.

#### **4 ) Combinação de Fatores Lineares e Quadráticos**

>[!quote] **Def**
>* Quando o denominador contém fatores lineares e quadráticos, aplica-se a combinação dos métodos acima.

---

>[!tip] ## **Padrão**

---

#### 01) Decompositores com fatores lineares distintos 

>[!quote] **Def**
>Se o denominador tem apenas fatores lineares distintos, como $(x-a)(x-b)$, a fração é decomposta assim:
>
>$$\frac{P(x)}{(x-a)(x-b)} = \frac{A}{x-a} + \frac{B}{x-b}$$
>
>* Cada fator linear gera um termo na decomposição.
>* A e B são constantes determinadas resolvendo um sistema de equações.
>
>---
>
>**Exemplo:**
>
>$$\frac{5x+7}{(x-2)(x+3)} = \frac{A}{x-2} + \frac{B}{x+3}$$

---
#### 02) Denominadores com fatores lineares repetidos

>[!quote] **Def**
>Se o denominador tem fatores lineares repetidos, como $(x-a)^n$, incluímos termos para cada potência do fator, até $n$:
>
>$$\frac{P(x)}{(x-a)^n} = \frac{A_1}{x-a} + \frac{A_2}{(x-a)^2} + \cdots + \frac{A_n}{(x-a)^n}$$
>
>---
>**Exemplo:**
>
>$$\frac{x^2+3}{(x+1)^3} = \frac{A}{x+1} + \frac{B}{(x+1)^2} + \frac{C}{(x+1)^3}$$

---
#### 03) Denominadores com fatores quadráticos irredutíveis distintos

>[!quote] **Def**
Um fator quadrático irredutível é um polinômio de segundo grau que não pode ser fatorado em números reais (exemplo: $x^2+1$).
>
>Para cada fator quadrático irredutível, usamos um termo da forma:
>
>$$\frac{Ax+B}{x^2+px+q}$$
>
onde $Ax+B$ é um polinômio de grau 1.
>
>---
>
>**Exemplo:**
>
>$$\frac{x^3+2}{(x-1)(x^2+4)} = \frac{A}{x-1} + \frac{Bx+C}{x^2+4}$$

---
#### 04) Denominadores com fatores quadráticos irredutíveis repetidos

>[!quote] **Def**
Se o fator quadrático irredutível aparece com multiplicidade, como $(x^2+px+q)^n$, incluímos termos para cada potência até $n$:
>
>$$\frac{P(x)}{(x^2+px+q)^n} = \frac{A_1x+B_1}{x^2+px+q} + \frac{A_2x+B_2}{(x^2+px+q)^2} + \cdots + \frac{A_nx+B_n}{(x^2+px+q)^n}$$
>
>---
>
>**Exemplo:**
>
>$$\frac{x^3}{(x^2+1)^2} = \frac{Ax+B}{x^2+1} + \frac{Cx+D}{(x^2+1)^2}$$

---
#### 05) Casos mistos (combinação de tipos)

>[!quote] **Def**
Se o denominador contém fatores lineares e quadráticos, repetidos ou não, a decomposição considera todos os tipos mencionados acima. Cada fator (linear ou quadrático) contribui com seus termos.
>
>---
>
>**Exemplo:**
>
>$$\frac{x^4+5x^2+7}{(x-2)^2(x^2+1)} = \frac{A}{x-2} + \frac{B}{(x-2)^2} + \frac{Cx+D}{x^2+1}$$

---
#### 06) Fração imprópria

>[!quote] **Def**
Se o grau do numerador é maior ou igual ao grau do denominador, primeiro devemos realizar a divisão polinomial para reescrever a fração como a soma de um polinômio e uma fração própria. Depois, aplicamos a decomposição em frações parciais apenas à fração própria.
>
>---
>
>**Exemplo:**
>
>$$\frac{x^3+x^2+1}{x^2+1} \text{ Dividindo: } x+1 + \frac{x}{x^2+1}$$
>
>Agora, aplicamos frações parciais apenas a $\frac{x}{x^2+1}$.

---
