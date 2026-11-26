
---
#### **Intro )** - Fundamentos e Mecânica Interna

```ad-quote
title: **Def**
**Summary:**
- Introdução aos conceitos de Inteligência Artificial, Machine Learning e Deep Learning, e como eles se aplicam ao processamento de áudio. Visão geral do curso e dos pré-requisitos.
````

> [!quote] **Vault:** [[Intro - Deep Learning]]

> [!quote] **Vault:** [[DL P - General Concepts]]

> [!quote] **Vault:** [[DL P - Modalidades do Aprendizado de Máquina]]

> [!quote] **Draw:** [[Supervised.excalidraw]]

---

> [!done] _New_

---

```ad-quote
title: **Def - Métodos de divisão para os dados**
**Summary:**
- Os dados de treino são aplicados para capacitar o modelo durante a fase de aprendizado, enquanto os dados de validação, quando disponíveis, servem para avaliar o desempenho intermediário e ajustar os parâmetros do sistema. Por fim, os dados de teste funcionam como uma base de informações inéditas, que nunca foram apresentadas ao algoritmo no processo de treinamento, possuindo o objetivo exclusivo de verificar a qualidade e a eficácia final do modelo configurado.
```

---

```ad-done
title:
#### **Fase 1 )** - Arquitetura e Representação Preditiva
```

---

```ad-quote
title: 
Esta fase foca na fundação estrutural do modelo e em como a informação flui para gerar uma Predição Inicial.
```

---
#### **01 ) -** Design de Saída - Estruturando Inputs e Outputs

```ad-quote
title: **Def**
**Summary:**
- Definição da Arquitetura Com Base No Problema, conectando a saída do modelo à Natureza Da Predição (Binária, Multiclasse, Regressão, etc.).
```

> [!quote] **Vault:** [[Sup IA - Estruturando Inputs]]

> [!quote] **Vault:** [[Sup IA - Estruturando Outputs]]

---

> [!done] _New_

---
#### **02 ) -** Quantificando o Erro - Funções de Custo Loss

```ad-quote
title: **Def**
**Summary:**
- Definição da métrica que quantifica a Distância Entre A Predição e o Valor Real desejado.
```

> [!quote] **Vault:** [[Sup AI - Funções de Perda]]

---

> [!done] _New_

---
#### **03 ) -** Gradiente Descendente

```ad-quote
title: **Def**
**Summary:**
- O processo de otimização matemática para atualizar os parâmetros do modelo de forma iterativa buscando o menor erro possível.
```

> [!quote] **Vault:** [[DL P - Gradient Descent]]

---

```ad-done
title:
#### **Fase 2 ) -** Diagnóstico e Validação
```

---

```ad-quote
title:
Fase crítica para garantir que a IA Preditiva seja confiável e funcione em Dados Reais Não Vistos.
```

---
#### **05 ) -** Métricas de Avaliação de Performance

```ad-quote
title: **Def**
**Summary:**
- Uso de Ferramentas De Diagnóstico como Matriz De Confusão, F1-Score e MSE para validar a Eficácia Do Modelo.
```

> [!quote] **Vault:** [[DL P - Evaluating Performance - Classification]]

> [!quote] **Vault:** [[DL - Evaluating Performance - Regretion]]

---

> [!done] _New_

---
#### **06 ) -** Controle de Treinamento - Overfitting e Early Stopping

```ad-quote
title: **Def**
**Summary:**
- Identificação do momento em que o modelo começa a Decorar O Ruído e aplicação da Interrupção Antecipada para preservar a Generalização.
```

> [!quote] **Vault:** [[DL P - Overfitting & Underfitting]]

> [!quote] **Vault:** [[DL - Early Stopping]]

---

> [!done] _New_

---
#### **07 ) -** O Equilíbrio - Viés e Variância - Bias-Variance Tradeoff

```ad-quote
title: **Def**
**Summary:**
- Estudo do Compromisso Entre Simplicidade E Complexidade para alcançar o Erro Mínimo No Teste.
```

> [!quote] **Vault:** [[DL P - Viés]]

> [!quote] **Vault:** [[DL P - Viés e Variância]]

---

> [!done] _New_

---
#### **08 ) -** Refinamento Dinâmico - Taxa de Aprendizagem

```ad-quote
title: **Def**
**Summary:**
- Ajuste do Hiperparâmetro Mais Importante (Learning Rate) para garantir uma convergência eficiente e evitar saltos drásticos na otimização.
```

> [!quote] **Vault:** [[DL - Taxa de Aprendizagem]]

---

```ad-done
title:
#### **Fase 3 ) -** Técnicas Avançadas
```

---

```ad-quote
title:
Técnicas para elevar o desempenho e reaproveitar conhecimento em problemas complexos.
```

---
#### **09 ) -** Regularização - L1 e L2

```ad-quote
title: **Def**
**Summary:**
- Métodos de penalização matemática para reduzir a complexidade do modelo, evitando pesos excessivamente grandes e tornando o algoritmo Mais Robusto.
```

> [!quote] **Vault:** [[ML - Regularização L1 e L2]]

---

> [!done] _New_

---
#### **10 ) -** Processamento e Aumento de Dados - OBS

```ad-quote
title: **Def**
**Summary:**
- Técnicas para enriquecer o conjunto de treino e garantir que a IA seja Invariante A Pequenas Alterações nos inputs.
```

> [!quote] **Vault:** [[DL - Processamento e Aumento de Dados]]

---

> [!done] _New_

---
#### **11 ) -** Ajuste de Hiperparâmetros

```ad-quote
title: **Def**
**Summary:**
- Métodos sistemáticos (como Grid Search e Random Search) para encontrar a Configuração Ideal do modelo.
```

> [!quote] **Vault:** [[DL - Ajuste de Hiperparâmetros]]

---

**XX ) - O Limite Espacial - A Maldição da Dimensionalidade**

**XX ) - O Inimigo Silencioso - Vazamento de Dados (Data Leakage)**

**XX ) - A Prova de Fogo - Validação Cruzada (Cross-Validation)**

https://www.youtube.com/watch?v=fSytzGwwBVw