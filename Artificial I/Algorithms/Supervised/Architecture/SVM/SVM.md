
---

https://www.youtube.com/watch?v=efR1C6CvhmE

---
##### 01 ) - ...

<p align="justify">Eles distinguem duas classes encontrando o hiperplano ideal que maximiza a margem entre os pontos de dados mais próximos de classes opostas. O número de atributos dos dados de entrada determina se o hiperplano é uma linha em um espaço 2D ou um plano em um espaço n-dimensional. Como vários hiperplanos podem ser encontrados para diferenciar as classes, maximizar a margem entre os pontos permite que o algoritmo encontre o melhor limite de decisão entre as classes. Isso, por sua vez, permite uma boa generalização dos novos dados e a realização de previsões de classificação precisas. As linhas adjacentes ao hiperplano ideal são conhecidas como vetores de suporte, pois esses vetores percorrem os pontos de dados que determinam a margem máxima.</p>

---

Classificação binária

---
##### 02 ) - Model Architecture

Ele define matematicamente o custo de um erro de classificação durante o treinamento, atuando diretamente na rigidez da margem.

- _C baixo:_ Aplica uma penalidade branda aos erros. O algoritmo opta por traçar uma margem de separação ampla e suave, aceitando que alguns pontos fiquem do lado errado. Isso força um modelo mais simples, elevando o viés para garantir uma variância controlada e melhor generalização.
    
- _C alto:_ Aplica uma penalidade severa a qualquer violação de margem. O algoritmo estreita a fronteira ao máximo para tentar classificar _todos_ os pontos de treino corretamente. O resultado é uma linha de decisão nervosa e hiperajustada, com baixo viés, mas altíssima variância (risco crítico de _overfitting_).
    

### **2. Função de Kernel**

É o motor de elevação dimensional. Define qual equação será utilizada para projetar os dados em um espaço superior.

- _Linear_: Força uma separação estritamente reta.
    
- _Polinomial_: Permite separações com curvaturas estruturadas de acordo com o grau do polinômio escolhido.
    
- _RBF (Radial Basis Function)_: O padrão absoluto da indústria. Consegue criar mapeamentos de distâncias radiais, permitindo isolar pontos em formatos perfeitamente circulares ou sinuosos.
    

### **3. Coeficiente Gama ($\gamma$)**

Este parâmetro é ativado ao utilizar _kernels_ não-lineares, especialmente o RBF. Ele define o raio de influência que um único vetor de suporte exerce no traçado da fronteira.

- _Gama baixo:_ A influência geométrica de cada ponto é espalhada por uma longa distância. Pontos distantes ainda afetam o cálculo da margem, resultando em regiões de decisão amplas, conectadas e de contornos suaves.
    
- _Gama alto:_ A influência geométrica é estrangulada e se torna estritamente local. O algoritmo passa a desenhar fronteiras extremamente apertadas ao redor de cada ponto individual, criando "ilhas" isoladas de classificação pelo mapa.

---

- Maximal Margin Classifiers

- Support Vector Classifiers 

- Support vector machines

ref: https://medium.com/@chukwubuikemstephen10/understanding-the-difference-between-the-maximal-margin-classifier-the-support-vector-classifier-0d2b750a3be5

- d? 

---
##### 03 ) - The Training Loop

- Start with data in a relatively low dimension
- Move the data into a higher dimension using [Kernel Functions](https://www.youtube.com/watch?v=Q7vT0--5VII)
- Find a support vector classifier that separates the higher dimensional data into two groups


---
##### 04 ) - Post-Training

- Evaluation Metrics

- Inference