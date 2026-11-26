---
banner: "![[Pasted image 20251004162220.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Formalização do Algoritmo de Otimização por Descida de Gradiente 

```ad-quote
title:
<p align="justify">O texto a seguir formaliza o processo iterativo de atualização de parâmetros em um modelo de aprendizado de máquina, utilizando o algoritmo de Descida de Gradiente.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **00 )** - Principal Analogia - A Grande Campanha pelo Vale da Vitória

```ad-quote
title:

<p align="justify">No universo do aprendizado de máquina, o treinamento de uma rede neural pode ser visto como uma grande campanha militar. O objetivo final é conquistar uma posição estratégica inexpugnável no campo de batalha: o VALE DA VITÓRIA, um lugar que representa o menor erro possível para o modelo, o seu MÍNIMO GLOBAL.</p>

<p align="justify">Nesta campanha, o cérebro de toda a operação é o GENERAL, que representa o algoritmo de otimização, como o GRADIENT DESCENT. Ele nunca pisa no campo de batalha; de sua tenda de comando, ele toma a decisão mais crucial de todas: para onde e com que velocidade mover seu exército. Seu exército são as TROPAS, a representação de todos os parâmetros – os pesos e vieses da rede. A posição exata de cada soldado no mapa é o valor de um parâmetro, e a formação completa do exército é o estado atual do modelo.</p>

<p align="justify">A campanha começa com o exército posicionado aleatoriamente no terreno, geralmente no topo de uma colina alta, uma posição tática terrível com um erro elevado. Para iniciar o avanço, o General precisa de inteligência. Ele não envia um soldado qualquer; ele despacha seu BATEDOR DE ELITE, que representa o algoritmo de BACKPROPAGATION. Este batedor é um especialista em topografia, equipado com uma ferramenta especial – um "teodolito de causalidade", análogo à regra da cadeia do cálculo. Com ela, ele não apenas informa a direção geral da descida. Ele volta com um relatório de uma precisão impecável, o GRADIENTE, detalhando a contribuição exata de cada batalhão e de cada soldado para a vulnerabilidade atual do exército. O relatório diz: _"General, para a descida mais eficiente, o 3º Batalhão deve recuar 5 passos, enquanto a 5ª Companhia deve avançar 2 passos para a direita..."_</p>

<p align="justify">De posse dessa informação vital, o General toma sua decisão. Ele consulta seu LIVRO DE ESTRATÉGIA, que é a TAXA DE APRENDIZAGEM (LEARNING RATE). Se for um general agressivo, ele ordenará marchas longas, cobrindo terreno rapidamente, mas correndo o risco de passar direto pelo vale. Se for cauteloso, ordenará avanços curtos e metódicos, um caminho mais lento, porém mais seguro. Com base na sua estratégia e no relatório do batedor, ele emite a ORDEM DE MARCHA, a atualização dos pesos, e o exército inteiro se move para uma nova posição, ligeiramente melhor e em uma altitude mais baixa. Este ciclo de obter inteligência (Backpropagation) e mover as tropas (Gradient Descent) se repete incessantemente. Uma campanha de um dia inteiro, onde todas as forças inimigas são engajadas, é conhecida como uma ÉPOCA.</p>

<p align="justify">Contudo, o campo de batalha é traiçoeiro. O exército pode descer para um pequeno vale e o batedor informar que todas as direções a partir dali são para cima. Este é o VALE DA EMBOSCADA, um MÍNIMO LOCAL, que pode enganar um general inexperiente a pensar que a guerra acabou.</p>

<p align="justify">Para evitar tais armadilhas, generais experientes empregam unidades de elite, como as FORÇAS ESPECIAIS "ADAM", uma analogia aos otimizadores avançados. Esta unidade aprimora a inteligência. Ela possui um DRONE DE RECONHECIMENTO (MOMENTUM), que se lembra da trajetória recente do exército, aconselhando o general a manter o "embalo" na direção geral do avanço para não ficar preso em pequenas crateras. Além disso, possui BATEDORES ESPECIALIZADOS (TAXAS DE APRENDIZAGEM ADAPTATIVAS), que analisam o terreno de cada batalhão individualmente, permitindo que o general dê ordens de marcha personalizadas: passos longos e rápidos para as tropas em planícies, e passos curtos e cuidadosos para aquelas em desfiladeiros.</p>

<p align="justify">Assim, a campanha se desenrola. Enquanto o General (Gradient Descent) é quem toma a decisão final e move o exército, sua campanha seria cega e fadada ao fracasso sem a inteligência precisa e detalhada do seu Batedor de Elite (Backpropagation). Um é o estrategista; o outro, o fornecedor da informação indispensável que torna a estratégia possível, trabalhando em uma simbiose perfeita para, passo a passo, guiar o exército para fora das colinas do erro e levá-lo à glória no Vale da Vitória.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Objetivo

```ad-quote
title:
Minimizar uma função de custo $J(\theta)$, que é parametrizada por um vetor de parâmetros $\theta$ (incluindo pesos e vieses). O processo para atualizar o vetor de parâmetros $\theta$ pode ser decomposto nos seguintes estágios para uma única iteração:
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Propagação Direta (Forward Propagation) e Cálculo do Custo

```ad-quote
title:
Dado um lote (batch) de dados de treinamento, o modelo utiliza seu conjunto de parâmetros atual, $\theta_{atual}$, para realizar uma passagem direta (forward pass). Nesta etapa, as predições do modelo, denotadas por $\hat{y}$, são geradas. Em seguida, essas predições são comparadas com os rótulos verdadeiros, $y$, por meio da função de custo $J(\theta_{atual})$. O resultado é um valor escalar que quantifica o erro agregado do modelo para o estado atual de seus parâmetros.
```

```ad-quote
title:
###### **Custo:**
```

```ad-quote
title:
$$Custo = J(\theta_{atual})$$
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Propagação Reversa (Backward Propagation) e Cálculo do Gradiente

```ad-quote
title:
O passo crucial é determinar a contribuição de cada parâmetro em $\theta$ para o erro total. Isso é alcançado ao computar o gradiente da função de custo em relação ao vetor de parâmetros. O gradiente, denotado por $\nabla_{\theta}J(\theta_{atual})$, é um vetor cujos componentes são as derivadas parciais da função de custo em relação a cada parâmetro individual:
```

```ad-quote
title:
$$\nabla_{\theta}J(\theta_{atual}) = \begin{bmatrix} \frac{\partial J}{\partial \theta_1} \\ \frac{\partial J}{\partial \theta_2} \\ \vdots \\ \frac{\partial J}{\partial \theta_n} \end{bmatrix}$$
```

```ad-quote
title:
<p align="justify">Por definição, este vetor aponta na direção de crescimento máximo da função de custo. Em redes neurais, o algoritmo computacionalmente eficiente para calcular este gradiente é a Retropropagação do Erro (Backpropagation).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Atualização dos Parâmetros (O Passo de Descida)

```ad-quote
title:
Para minimizar o custo, os parâmetros são ajustados na direção oposta à do gradiente. A magnitude desse ajuste é controlada por um hiperparâmetro escalar chamado taxa de aprendizado (learning rate), denotado por $\alpha$. A regra de atualização de parâmetros é formalmente definida como:
```

```ad-quote
title:
$$\theta_{novo} \leftarrow \theta_{atual} - \alpha \nabla_{\theta}J(\theta_{atual})$$
```

```ad-quote
title:
<p align="justify">Onde:</p>
```

```ad-quote
title:
* $\theta_{novo}$ é o vetor de parâmetros atualizado que será usado na próxima iteração.
* $\theta_{atual}$ é o vetor de parâmetros da iteração corrente.
* $\alpha$ é a taxa de aprendizado, que modula o tamanho do passo de atualização.
* $\nabla_{\theta}J(\theta_{atual})$ é o gradiente da função de custo calculado no ponto $\theta_{atual}$.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )** - Ciclo Iterativo

```ad-quote
title:
Esses três estágios constituem uma única iteração (ou step). O processo é repetido sucessivamente a cada lote de dados. A cada passo, a configuração dos parâmetros $\theta$ "desce" a paisagem de custo, convergindo progressivamente para um ponto de mínimo (seja ele local ou global). A convergência é tipicamente alcançada quando o gradiente se aproxima de zero ($\nabla_{\theta}J(\theta) \approx 0$), fazendo com que as atualizações nos parâmetros se tornem insignificantes.
```
````

---
