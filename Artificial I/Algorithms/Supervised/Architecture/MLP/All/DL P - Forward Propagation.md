
---

````ad-quote
title:

##### **01 )** - Por que Redes Neurais?

```ad-quote
title:
<p align="justify">Imagine que você quer separar pontos em um gráfico. Se esses pontos puderem ser separados por uma única linha reta, isso é um <b>problema linear</b>. Um único neurônio artificial, como o Perceptron, é muito bom em resolver esse tipo de problema. Ele consegue "aprender" a traçar essa linha reta.</p>
<p align="justify">No entanto, a maioria dos problemas do mundo real não é tão simples. Pense em reconhecer um rosto em uma imagem ou traduzir um texto. Esses são <b>problemas não-lineares</b>, o que significa que não podem ser resolvidos com uma única linha reta. Para lidar com essa complexidade, precisamos de algo mais poderoso.</p>
<p align="justify">É aí que entram as redes neurais. Ao conectar vários neurônios em camadas, criamos uma rede capaz de aprender e modelar relações muito mais complexas e não-lineares. Em vez de uma única linha reta, a rede pode criar "fronteiras de decisão" curvas e intrincadas, permitindo-lhe resolver problemas muito mais sofisticados.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Componentes de uma Rede Neural Artificial

```ad-quote
title:
<p align="justify">Uma rede neural é inspirada no cérebro humano e é composta por vários elementos que trabalham em conjunto:</p>
```

```ad-quote
title:

**Neurônios:**
- São as unidades computacionais fundamentais da rede. Cada neurônio recebe uma ou mais entradas, realiza um cálculo simples e produz uma saída.

**Camadas:**
- Os neurônios são organizados em camadas:
- **Camada de Entrada (Input Layer):** É por onde os dados brutos são inseridos na rede. Por exemplo, cada neurônio poderia representar um pixel de uma imagem.
- **Camadas Ocultas (Hidden Layers):** São as camadas intermediárias onde a maior parte do "processamento pesado" acontece. Quanto mais camadas, mais complexas as relações que a rede pode aprender.
- **Camada de Saída (Output Layer):** É a camada final que produz o resultado. Por exemplo, a categoria de um objeto ("gato", "cachorro").

**Conexões Ponderadas:**
- Cada neurônio em uma camada é conectado aos neurônios da camada seguinte. Cada conexão tem um **peso**, que representa a força e a importância daquela conexão. A rede "aprende" ajustando esses pesos.

**Funções de Ativação:**
- Uma função que processa a informação em cada neurônio (exceto na entrada). Ela introduz a não-linearidade, permitindo que a rede aprenda padrões complexos. Exemplos comuns são Sigmoide, ReLU e Tanh.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Perceptron de Múltiplas Camadas (MLP)

```ad-quote
title:
<p align="justify">O Perceptron de Múltiplas Camadas (MLP) é um tipo clássico e fundamental de rede neural. Suas principais características são:</p>
```

```ad-quote
title:
**Múltiplas Camadas:** 
- Possui pelo menos três camadas: uma de entrada, uma ou mais ocultas e uma de saída.

**Feed-forward (Alimentação Direta):** 
- A informação flui em uma única direção, da entrada para a saída, sem ciclos.

**Totalmente Conectado:** 
- Geralmente, cada neurônio de uma camada se conecta a todos os neurônios da camada seguinte.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Processo Computacional em um MLP

```ad-quote
title:
<p align="justify">O fluxo de informação em um MLP, chamado de <b>propagação direta</b> (forward propagation), segue passos matemáticos bem definidos, transformando a entrada em uma saída final.</p>
```

```ad-quote
title:
**Passo 1: Entrada da Rede**
Os dados são inseridos na rede como um vetor de entrada. Por exemplo, um vetor com n características.

1. $$X = [x_1, x_2, \dots, x_n]$$
```

```ad-quote
title:
**Passo 2: Da Entrada para a Camada Oculta**
O vetor de entrada é multiplicado pela matriz de pesos da primeira camada oculta ($W_1$) e um viés ($b_1$) é somado. O resultado é a entrada líquida ($H_{net}$), que é então passada por uma função de ativação ($f$) para gerar a saída da camada oculta ($H_{out}$).

1. $$H_{net} = W_1 \cdot X^T + b_1$$
   
2. $$H_{out} = f(H_{net})$$
```

```ad-quote
title:
**Passo 3: Da Camada Oculta para a Camada de Saída**
A saída da camada oculta ($H_{out}$) torna-se a entrada para a próxima camada. O processo se repete: é multiplicada pela matriz de pesos da camada de saída ($W_2$), um viés ($b_2$) é somado, e o resultado é passado por uma função de ativação para produzir a saída final da rede ($Y$).

1. $$Y_{net} = W_2 \cdot H_{out}^T + b_2$$
2. $$Y = f(Y_{net})$$
```
````

![[Pasted image 20250808194957.png]]

---

> [!example] **_Python_**

---

```python
import numpy as np

# Função de ativação Sigmoide e sua aplicação
def sigmoid(x):
    return 1 / (1 + np.exp(-x))

# Dados de entrada
X = np.array([0.5, 0.3, 0.2])

# Pesos e vieses (gerados aleatoriamente para o exemplo)
# Conexões da camada de entrada (3 neurônios) para a oculta (4 neurônios)
W1 = np.random.rand(4, 3)
b1 = np.random.rand(4)

print(W1)

# Conexões da camada oculta (4 neurônios) para a de saída (1 neurônio)
W2 = np.random.rand(1, 4)
b2 = np.random.rand(1)

# Passo 1: Cálculo da saída da camada oculta
h_net = np.dot(W1, X) + b1
h_out = sigmoid(h_net)

# Passo 2: Cálculo da saída final da rede
y_net = np.dot(W2, h_out) + b2
Y = sigmoid(y_net)

print("\n\n|  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  \n\n")
print(f"| Simulando a Propagação Direta em um MLP...\n")
print(f"| Vetor de Entrada (X): {X}")
print(f"| Saída da Camada Oculta (H_out): {np.round(h_out, 5)}")
print(f"| Saída Final da Rede (Y): {np.round(Y, 5)}\n\n")

```

---
