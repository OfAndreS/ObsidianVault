
---

>[!quote] **YouTube:** [Play](https://www.youtube.com/watch?v=qxIaW-WvLDU&list=PL-wATfeyAMNrtbkCNsLcpoAyBBRJZVlnf&index=3)

---

````ad-quote
title:

##### **01 )** - Neurônio

```ad-quote
title:
<p align="justify">Um neurônio artificial é a unidade fundamental de processamento de uma rede neural. Ele opera como uma equação matemática desenhada para receber, ponderar e transformar dados. A sua função central é consolidar múltiplas informações numéricas em um único resultado. O neurônio avalia a importância de cada dado de entrada através de multiplicadores, soma os valores obtidos e submete o total a um filtro matemático.</p>
```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Cálculo base_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Representação*
```
![[Pasted image 20250805113940.png]]
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Fórmula*
```

```ad-quote
title:

 $$z = \sum_{i=1}^{n} (w_i \cdot x_i) + b$$
```

```ad-quote
title:
$x_1 \ )$
- Correspondem aos dados numéricos exatos fornecidos ao modelo.

---

$w_1 \ )$
- Determinam a importância matemática de cada variável de entrada no cálculo geral.

---

$b \ )$
- Funciona como uma constante de ajuste. Ele desloca o limiar do resultado independentemente das entradas recebidas.

---

$\sum \ )$
- Agrega todas as multiplicações entre as entradas e os seus respectivos pesos para gerar um valor consolidado.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _Função de ativação [[MLP - Activation Functions | { X }]]_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *O que é*
```
```ad-quote
title:
<p align="justify">Após o cálculo da soma ponderada ( z ), o resultado é passado por uma função de ativação. Esta função é um componente não-linear que decide qual será a saída do neurônio com base no valor de z. A não-linearidade permite que as redes neurais aprendam padrões complexos e sem elas, uma rede neural, não importando o quão profunda, se comportaria como um simples modelo linear.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Fórmula*
```

```ad-quote
title:
1. $$y = f(z) = f(\sum_{i=1}^{n} (w_i \cdot x_i) + b)$$
```

```ad-quote
title:
<p align="justify">A saída do neurônio ( y ) é, portanto, o resultado da função de ativação ( f ) aplicada ao somatório ( z ):</p>
```

````

---

```ad-example

#### **Exemplo Prático: Um Neurônio em Ação**
```

---

````ad-quote
title:

##### **01 )** - Cenário Baseado na Imagem

```ad-quote
title:
<p align="justify">Vamos aplicar os conceitos a um exemplo numérico concreto, baseado na imagem fornecida. Neste caso, nosso neurônio possui 3 entradas e vamos assumir que o <b>bias (b) é 0</b>.</p>
```
````

![[Pasted image 20250805120536.png]]

````ad-quote
title:

**Passo 1: Definir Inputs e Pesos**
```ad-quote
title:
<p align="justify">Primeiro, listamos os vetores de input (os valores dentro dos círculos laranja) e de pesos (os valores nas linhas de conexão).</p>

- **Vetor de Inputs (X):**
$$X = [0.5, 0.3, 0.2]$$

- **Vetor de Pesos (W):**
$$W = [0.4, 0.7, 0.2]$$
```

````

````ad-quote
title:

**Passo 2: Calcular o Somatório (z)**
```ad-quote
title:
<p align="justify">Agora, calculamos a soma ponderada, multiplicando cada input pelo seu peso correspondente e somando os resultados.</p>

$$z = \sum_{i=1}^{n} (w_i \cdot x_i) + b$$$$z = (0.5 \cdot 0.4) + (0.3 \cdot 0.7) + (0.2 \cdot 0.2) + 0$$$$z = 0.20 + 0.21 + 0.04$$
$$z = 0.45$$

<p align="justify">Este valor, 0.45, é o que o neurônio agregou antes de decidir se e com que intensidade deve "disparar".</p>
```
````

````ad-quote
title:

**Passo 3: Aplicar a Função de Ativação Sigmoide**
```ad-quote
title:
<p align="justify">O valor de z é então passado para a função de ativação. Usaremos a função <b>Sigmoide</b>, que irá comprimir o resultado em um valor entre 0 e 1.</p>

$$y = f(z) = \sigma(z) = \frac{1}{1 + e^{-z}}$$$$y = \sigma(0.45) = \frac{1}{1 + e^{-0.45}}$$$$y \approx \frac{1}{1 + 0.6376}$$
$$y \approx \frac{1}{1.6376} \approx 0.6106$$
```
````

````ad-quote
title:

**Resultado Final (y)**
```ad-quote
title:
<p align="justify">O output final do neurônio é aproximadamente <b>0.6106</b>. Este é o sinal que ele enviará para os neurônios da próxima camada da rede. Ele representa a "força de ativação" do neurônio em resposta aos inputs que recebeu.</p>
```
````

