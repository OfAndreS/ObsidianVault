---
banner: "![[Pasted image 20260311140138.png]]"
---
---

![[Pasted image 20260404163411.png]]

### **Guia de Riscos e Dificuldades**

Abaixo estão descritos os problemas estruturais e algébricos que você encontrará ao resolver cada tipo de questão da lista apresentada.

### **1. Funções Racionais (Frações com Variável no Denominador)**

- **Exercícios:** (g), (h), (i) e (j)
    
- **O problema na Injetividade:** Ao fazer $f(x_1) = f(x_2)$, você precisará multiplicar cruzado e agrupar os termos. A dificuldade é puramente algébrica (fatoração e cancelamento) para isolar a igualdade $x_1 = x_2$.
    
- **O problema na Sobrejetividade:** Ao igualar a fração a $y$ e tentar isolar o $x$, você encontrará uma nova fração onde $y$ estará no denominador. Isso revela uma restrição na imagem. Para um determinado valor de $y$, o denominador zera, o que prova que esse valor de $y$ não possui origem. Logo, a função não será sobrejetiva em $\mathbb{R}$.
    
- **O problema no Domínio:** Funções racionais possuem restrição de domínio (o denominador não pode ser zero). Como o enunciado define todas as funções de $\mathbb{R} \to \mathbb{R}$, a existência de um valor de $x$ que zera o denominador anula a própria definição inicial da função no conjunto dos reais.
    

### **2. Funções Definidas por Partes**

- **Exercícios:** (a) e (b)
    
- **O problema na Injetividade:** Não basta provar a injetividade de cada sentença isolada. Você deve provar que os conjuntos de imagens das duas partes não se interceptam. Se a primeira sentença e a segunda sentença puderem gerar o mesmo valor de saída para valores de entrada diferentes, a função global deixa de ser injetiva.
    
- **O problema na Sobrejetividade:** A imagem total da função será a união das imagens de cada parte. Você precisa calcular o intervalo de saída da primeira parte, o intervalo de saída da segunda parte e verificar se a união desses dois intervalos cobre todo o conjunto dos números reais ($\mathbb{R}$).
    

### **3. Funções Quadráticas Restritas**

- **Exercício:** (a) (na primeira sentença $x^2 + 3x$)
    
- **O problema na Injetividade:** Funções quadráticas completas não são injetivas no domínio dos reais, pois possuem simetria (parábola). A dificuldade está em avaliar se a restrição do domínio dada no enunciado ($x \ge 0$) removeu a metade simétrica da curva. Se removeu, a função torna-se injetiva naquele intervalo.
    
- **O problema na Inversa:** Para isolar o $x$ em uma equação quadrática do tipo $y = x^2 + 3x$, você precisará utilizar a fórmula de Bhaskara ou o método de completar quadrados. O isolamento resultará em uma raiz quadrada com duplo sinal ($\pm$). Você deverá usar a restrição do domínio ($x \ge 0$) para decidir qual sinal é logicamente válido.
    

### **4. Funções Baseadas em Conjuntos Numéricos**

- **Exercício:** (b)
    
- **Dificuldade Argumentativa:** Esta função separa os elementos entre racionais ($\mathbb{Q}$) e irracionais ($\mathbb{R} \setminus \mathbb{Q}$). Você não conseguirá isolar variáveis através de álgebra comum. A resolução exige demonstração por propriedades analíticas dos números (por exemplo, provar se a soma de um número irracional com um inteiro pode ou não resultar em um número racional).
    

### **5. Funções Lineares (Polinômios de 1º Grau)**

- **Exercícios:** (c), (d), (e) e (f)
    
- **Características:** Não apresentam problemas estruturais. O isolamento algébrico é direto tanto para testar a sobrejetividade quanto para encontrar a função inversa. Todas as quatro funções deste grupo são bijetivas em $\mathbb{R} \to \mathbb{R}$.

````ad-quote
title:
##### **Possibilidade1 ) -** A Função Linear

```ad-quote
title:
**Assumir P:**

- Suponha que $f(x) = \frac{x}{3} + \frac{3}{2}$ e que $f(x_1) = f(x_2)$.
    

**Usar a definição:**

- Por definição de _função injetora_, precisamos mostrar que a igualdade das imagens implica na igualdade dos domínios, ou seja, $x_1 = x_2$.
    

**Desenvolver a dedução:**

Vamos analisar a igualdade algébrica:

1. $$\frac{x_1}{3} + \frac{3}{2} = \frac{x_2}{3} + \frac{3}{2}$$
    
2. $$\frac{x_1}{3} = \frac{x_2}{3}$$
    
3. $$x_1 = x_2$$
    

**Concluir Q:**

- Como a álgebra nos levou diretamente à igualdade das entradas, concluímos que a função é _injetora_. Qualquer função desse formato linear seguirá este mesmo percurso.
```
````

---

````ad-quote
title:
##### **Possibilidade 2 ) -** A Função Racional

```ad-quote
title:
**Assumir P:**

- Suponha que $f(x) = \frac{3x-2}{1-x}$ e que $f(x_1) = f(x_2)$.

**Usar a definição:**

- Por definição de _função injetora_, precisamos provar que a condição garante que $x_1 = x_2$.

**Desenvolver a dedução:**

Vamos analisar a igualdade aplicando a multiplicação cruzada e a distributiva:

1. $$\frac{3x_1-2}{1-x_1} = \frac{3x_2-2}{1-x_2}$$

2. $$(3x_1-2)(1-x_2) = (3x_2-2)(1-x_1)$$

3. $$3x_1 - 3x_1x_2 - 2 + 2x_2 = 3x_2 - 3x_2x_1 - 2 + 2x_1$$

4. $$3x_1 + 2x_2 = 3x_2 + 2x_1$$

5. $$3x_1 - 2x_1 = 3x_2 - 2x_2$$

6. $$x_1 = x_2$$

**Concluir Q:**

- A álgebra se sustenta perfeitamente após a eliminação dos termos repetidos em ambos os lados. Portanto, a função é _injetora_.
```
````

````ad-quote
title:
##### **Possibilidade 3 ) -** A Função Quadrática com Restrição

```ad-quote
title:
**Assumir P:**

- Suponha que $f(x) = x^2 + 3x$, considerando a restrição de domínio $x \ge 0$, e que $f(x_1) = f(x_2)$.

**Usar a definição:**

- Por definição de _função injetora_, precisamos provar que, estritamente dentro deste domínio específico, teremos $x_1 = x_2$.

**Desenvolver a dedução:**

Vamos analisar a igualdade agrupando todos os termos e fatorando a expressão:

1. $$x_1^2 + 3x_1 = x_2^2 + 3x_2$$

2. $$x_1^2 - x_2^2 + 3x_1 - 3x_2 = 0$$

3. $$(x_1 - x_2)(x_1 + x_2) + 3(x_1 - x_2) = 0$$

4. $$(x_1 - x_2)(x_1 + x_2 + 3) = 0$$

**Concluir Q:**

- Para que o produto seja igual a zero, um dos fatores precisa ser zero. A possibilidade $x_1 + x_2 + 3 = 0$ é matematicamente impossível, pois a restrição de domínio determina que as entradas são não-negativas, o que significa que essa soma _nunca_ será zero. Logo, a única solução possível é $x_1 - x_2 = 0$, resultando em $x_1 = x_2$. Graças à restrição, este trecho da função é _injetor_.
```
````

---

