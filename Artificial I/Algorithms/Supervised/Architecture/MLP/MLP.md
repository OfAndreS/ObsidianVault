---
banner: "![[Pasted image 20260118174047.png]]"
---
---
#### **Intro )** - Multilayer Perceptron (MLP)

```ad-quote
title: **Def**
**Summary:**
- Estudo focado na anatomia matemática, na topologia de camadas densas e no fluxo de tensores que diferenciam as Redes Neurais Profundas dos modelos clássicos de aprendizado de máquina.
```

---

```ad-done
title:
#### **Phase 1 )** - Network Anatomy and Forward Flow
```

---

```ad-quote
title: 
Esta fase foca na fundação estrutural do modelo, no processamento afim de entradas e em como a informação flui através de camadas ocultas até a predição.
```

---
#### **01 ) -** The Foundation - Artificial Neurons and Dense Layers

```ad-quote
title: **Def**
**Summary:**
- Estudo da Unidade Fundamental (Perceptron) que compõe as redes e como ela realiza o Processamento Afim (Pesos e Viés: $z = Wx + b$) dos dados de entrada em camadas totalmente conectadas.
```

> [!quote] **Vault:** [[MLP - Artificial Neuron]]

---

> [!done] _New_

---
#### **02 ) -** Activation Functions

```ad-quote
title: **Def**
**Summary:**
- Compreensão de como introduzir Não-Linearidade (ReLU, Sigmoid, Tanh, Leaky ReLU) para que a rede consiga mapear superfícies de decisão complexas e não colapse em uma simples transformação linear.
```

> [!quote] **Vault:** [[MLP - Activation Functions]]

---

> [!done] _New_

---
#### **03 ) -** Cost and Loss Functions

```ad-quote
title: **Def**
**Summary:**
- Quantificação do erro entre a saída predita pela rede e o rótulo real, direcionando o aprendizado através de funções matemáticas diferenciáveis (como MSE para regressão e Cross-Entropy para classificação).
```

> [!quote] **Vault:** [[DL P - Cost and Loss Functions]]

---

```ad-done
title:
#### **Phase 2 )** - Training and Optimization
```

---

```ad-quote
title:
Nesta etapa, o foco é o algoritmo de retropropagação do erro e as técnicas numéricas para navegar pela superfície de custo em direção ao mínimo global ou local.
```

---
#### **04 ) -** Forward & Backpropagation

```ad-quote
title: **Def**
**Summary:**
- O fluxo de propagação para frente e o processo de Retropropagação Do Erro (aplicação iterativa da Regra da Cadeia) para computar os gradientes da função de perda em relação a cada peso e viés.
```

> [!quote] **Vault:** [[DL P - Forward Propagation]]

> [!quote] **Vault:** [[DL P - Backpropagation]]

---

> [!done] _New_

---
#### **05 ) -** Optimization Algorithms

```ad-quote
title: **Def**
**Summary:**
- Dinâmica de atualização dos parâmetros utilizando algoritmos baseados em gradiente, desde o Gradiente Descendente Estocástico (SGD) com Momentum até métodos adaptativos (Adam, RMSprop).
```

> [!quote] **Vault:** [[DL P - Gradient Descent]]

> [!quote] **Vault:** [[DL P - Optimization Algorithms]]

---

```ad-done
title:
#### **Phase 3 )** - Numerical Stability and Acceleration
```

---

```ad-quote
title:
Técnicas implementadas na inicialização e dentro das camadas para estabilizar o fluxo dos gradientes e acelerar a convergência do treinamento.
```

---
#### **06 ) -** Weight Initialization and Gradient Dynamics

```ad-quote
title: **Def**
**Summary:**
- Diagnóstico de falhas estruturais onde o Gradiente Desaparece (Vanishing) ou Explode (Exploding), mitigados pelo uso de técnicas adequadas de inicialização (He/Kaiming para ReLU, Xavier/Glorot para Tanh/Sigmoid).
```

> [!quote] **Vault:** [[DL P - Vanishing and Exploding Gradients]]

> [!quote] **Vault:** [[DL P - Weight Initialization]]

---

> [!done] _New_

---
#### **07 ) -** Internal Normalization - Batch & Layer Norm

```ad-quote
title: **Def**
**Summary:**
- Estratégias arquiteturais para estabilizar a distribuição das ativações internas: Batch Normalization (calculada através das amostras do minilote) e Layer Normalization (calculada através dos atributos de cada amostra individualmente, eliminando a dependência do tamanho do batch). Ambas suavizam a superfície de perda e viabilizam taxas de aprendizado maiores.
```

> [!quote] **Vault:** [[DL P - Batch Normalization]]

> [!quote] **Vault:** [[DL P - Layer Normalization]]

---

```ad-done
title:
#### **Phase 4 )** - Regularization and Practice
```

---

```ad-quote
title:
Mecanismos para prevenir o sobreajuste (overfitting), garantir alta capacidade de generalização e consolidar a teoria em código funcional.
```

---
#### **08 ) -** Architectural Regularization - Dropout

```ad-quote
title: **Def**
**Summary:**
- Método para reduzir a co-adaptação excessiva entre neurônios desligando-os aleatoriamente durante o treino, atuando como regularizador arquitetural contra overfitting.
```

> [!quote] **Vault:** [[DL P - Dropout]]

> [!quote] **Vault:** [[DL P - Overfitting & Underfitting]]

---

> [!done] _Prática_

---
#### **Practice ) -** Building an MLP from Scratch

```ad-quote
title: **Def**
**Summary:**
- Implementação manual das matrizes de pesos, passos de forward, cálculo analítico de gradientes e passo de descida sem o uso de frameworks automáticos de autograd, fixando os conceitos matemáticos fundamentais.
```

> [!quote] **Vault:** [[MLP - Simple Neural Network From Scratch]]

---