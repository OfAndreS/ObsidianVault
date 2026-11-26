
---

https://youtu.be/4b5d3muPQmA?si=cMlNBQ3pEIS8lll5

Com certeza! O K-means é um dos algoritmos mais elegantes da aprendizagem não supervisionada justamente pela sua simplicidade matemática. Ele funciona através de um processo iterativo chamado _Expectation-Maximization_ (Expectativa-Maximização).

Aqui está a sequência lógica das fórmulas, separadas por fase:

---

## **Fórmulas de Treinamento (Ajuste do Modelo)**

O objetivo do treinamento é encontrar a posição ideal dos centroides que minimize a _inércia_ (ou soma dos quadrados intra-cluster).

### 1. Inicialização

Primeiro, escolhemos $k$ pontos iniciais para serem os centroides $\mu_1, \mu_2, \dots, \mu_k$. Isso pode ser feito de forma aleatória ou usando métodos mais inteligentes como o _K-means++_.

### 2. Atribuição de Clusters (Passo de Expectativa)

Para cada ponto do seu conjunto de dados $x^{(i)}$, calculamos a distância até cada centroide e o atribuímos ao mais próximo. A métrica padrão é a _Distância Euclidiana ao Quadrado_:

$$d(x^{(i)}, \mu_j) = \|x^{(i)} - \mu_j\|^2$$

A fórmula de atribuição para encontrar o índice do cluster $c^{(i)}$ é:

$$c^{(i)} := \arg\min_{j} \|x^{(i)} - \mu_j\|^2$$

### 3. Atualização dos Centroides (Passo de Maximização)

Após todos os pontos serem atribuídos, recalculamos a posição de cada centroide $\mu_j$ tirando a _média aritmética_ de todos os pontos que foram atribuídos a ele:

$$\mu_j := \frac{\sum_{i=1}^{m} 1\{c^{(i)} = j\} x^{(i)}}{\sum_{i=1}^{m} 1\{c^{(i)} = j\}}$$

Onde $1\{c^{(i)} = j\}$ é uma função indicadora que vale $1$ se o ponto pertencer ao cluster $j$ e $0$ caso contrário.

### 4. Função de Custo (Inércia)

O algoritmo repete os passos 2 e 3 até que os centroides não mudem significativamente. O que estamos tentando minimizar matematicamente é a função $J$:

$$J = \sum_{i=1}^{m} \|x^{(i)} - \mu_{c^{(i)}}\|^2$$

---

## **Fórmulas de Inferência (Predição)**

Na fase de inferência, os centroides $\mu_j$ já estão fixos (o modelo está treinado). Quando chega um novo dado $x_{novo}$, o processo é simplificado, pois não há atualização.

### 1. Cálculo de Proximidade

Calculamos a distância do novo ponto para os centroides finais obtidos no treino:

$$d(x_{novo}, \mu_j) = \|x_{novo} - \mu_j\|^2$$

### 2. Atribuição Final

O novo ponto recebe o rótulo do cluster cujo centroide é o mais próximo:

$$y_{pred} = \arg\min_{j} \|x_{novo} - \mu_j\|^2$$

Nesta fase, o custo computacional é muito baixo, pois você apenas compara o novo vetor com $k$ vetores fixos, o que torna o K-means muito _eficiente_ para sistemas em tempo real.

---

O que acha de explorarmos como escolher o valor ideal de $k$ usando a matemática do _Método do Cotovelo_ (Elbow Method)? Seria um ótimo próximo passo!

---

- **Definição de k:** Você escolhe quantos grupos deseja encontrar.
    
- **Inicialização:** Escolha aleatória de $k$ pontos para serem os primeiros centroides ($\mu_j$).
    
- **Atribuição:** Cada ponto $x^{(i)}$ do dataset "escolhe" o centroide mais próximo usando a distância ao quadrado $\|x^{(i)} - \mu_j\|^2$.
    
- **Atualização (O passo que faltou):** Para cada cluster formado, você calcula a **média aritmética** de todos os pontos que foram atribuídos a ele. Essa média se torna o _novo centroide_.
    
- **Cálculo da Variação (Inércia):** Agora sim, calcula-se a soma das distâncias ao quadrado de cada ponto até o seu _novo_ centroide.
    
- **Repetição:** Os passos 3, 4 e 5 são repetidos. O algoritmo não testa combinações aleatórias, ele _refina_ a posição dos centroides a cada rodada até que eles parem de se mover (convergência).

---
## **O Ciclo de Memória do Algoritmo**

A cada rodada (ou iteração), o algoritmo realiza uma troca de informações:

1. **Uso do Valor Guardado:** No início da iteração $t+1$, o algoritmo não sabe nada sobre os pontos, ele apenas conhece as coordenadas dos centroides que foram calculadas no final da iteração $t$.
    
2. **Nova Atribuição:** Ele usa essas coordenadas "guardadas" para calcular as distâncias e decidir a qual grupo cada ponto $x^{(i)}$ pertence agora.
    
3. **Sobrescrita:** Após reatribuir todos os pontos, ele calcula a nova média:
    
    $$\mu_j = \frac{1}{|S_j|} \sum_{x^{(i)} \in S_j} x^{(i)}$$
    
    Onde $S_j$ é o conjunto de pontos atribuídos ao cluster $j$. Esse novo valor da média _substitui_ o valor anterior na memória para a próxima rodada.