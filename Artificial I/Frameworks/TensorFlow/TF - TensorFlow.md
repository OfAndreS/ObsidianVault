---
banner: "![[Pasted image 20260317154844.png]]"
banner-x: 50
banner-y: 40
---

---
#### **Intro )** - Roteiro de Domínio em TensorFlow

```ad-quote
title: **Def**
**Summary:**
- A recente revolução do Deep Learning foi impulsionada pela união de três forças: a imensa disponibilidade de dados, o avanço do poder computacional, especialmente com as GPUs, e o desenvolvimento de algoritmos e frameworks cada vez mais sofisticados. No coração desses frameworks está o Tensor, uma estrutura de dados que elegantemente generaliza conceitos como escalares, vetores e matrizes para qualquer número de dimensões.
```

> [!done] _New_

> [!quote] **Vault:** [[KerasPipeline]]

> [!quote] **Vault:** [[TF - Roteiro]]

---

```ad-done
title:
#### **Fase 1 )** - Fundamentos Matemáticos e Tensores
```

```ad-quote
title:
Esta fase estabelece a base conceitual sobre tensores e apresenta o ecossistema TensorFlow, seus objetivos e componentes principais.
```

---

> [!done] _New_

---
#### **01 ) -** O que é o TensorFlow?

```ad-quote
title: **Def**
**Summary:**
- O objetivo é introduzir os conceitos essenciais sobre o que é o TensorFlow, sua arquitetura, vantagens e principais casos de uso.
```

> [!quote] **Vault:** [[Intro - TensorFLow]]

> [!quote] **Vault:** [[Keras - Pipeline]]

---

> [!done] _New_

---
#### **02 ) -** Tensores e Operações Básicas

```ad-quote
title: **Def**
**Summary:**
- O foco deste tópico é aprender sobre tensores como a unidade fundamental de dados, incluindo sua criação, manipulação e operações matemáticas básicas.
```

> [!quote] **Vault:** [[TF - Tensores e Operações]]

> [!quote] **Vault:** [[TF - Variáveis e Placeholders]]

---

```ad-done
title:
#### **Fase 2 )** - Processamento e Pipelines de Dados
```

```ad-quote
title:
Nesta fase o objetivo é dominar a ingestão, transformação e otimização de fluxos de dados para alimentar os modelos de forma eficiente.
```

---

> [!done] _New_

---
#### **06 ) -** API tf.data

```ad-quote
title: **Def**
**Summary:**
- O foco é aprender a criar pipelines de dados eficientes para carregar e pré-processar grandes volumes de dados de forma performática.
```

> [!quote] **Vault:** [[TF - API tf.data]]

> [!quote] **Vault:** [[TF - Carregamento de Dados]]

---

> [!done] _New_

---
#### **07 ) -** Pré-processamento e Aumento de Dados

```ad-quote
title: **Def**
**Summary:**
- Este tópico concentra-se em aplicar transformações nos dados para melhorar a performance do modelo, especialmente em rotinas de visão computacional.
```

> [!quote] **Vault:** [[TF - Pré-processamento de Dados]]

> [!quote] **Vault:** [[TF - Data Augmentation]]

---

> [!done] _New_

---
#### **14 ) -** TFRecords e Serialização de Dados

```ad-quote
title: **Def**
**Summary:**
- O foco é converter datasets pesados no formato binário nativo da biblioteca, garantindo a leitura mais rápida possível pelo hardware durante o treinamento.
```

> [!quote] **Vault:** [[TF - Serialização TFRecord]]

> [!quote] **Vault:** [[TF - Protobuf e Parsing]]

---

```ad-done
title:
#### **Fase 3 )** - Arquiteturas de Redes Neurais
```

```ad-quote
title:
Exploração das diferentes formas de construir modelos, desde sequências simples até redes complexas como CNNs e RNNs.
```

---

> [!done] _New_

---
#### **03 ) -** API Sequencial vs. API Funcional

```ad-quote
title: **Def**
**Summary:**
- Neste tópico, você aprenderá as duas principais formas de construir modelos no Keras e quando utilizar cada uma de acordo com a complexidade da rede.
```

> [!quote] **Vault:** [[Keras - API Sequencial]]

> [!quote] **Vault:** [[Keras - API Funcional]]

---

> [!done] _New_

---
#### **04 ) -** Camadas e Funções de Ativação

```ad-quote
title: **Def**
**Summary:**
- O foco é explorar os diferentes tipos de camadas e funções de ativação, compreendendo seu papel matemático na construção de redes neurais profundas.
```

> [!quote] **Vault:** [[Keras - Tipos de Camadas]]

> [!quote] **Vault:** [[Keras - Diagnostico Estrutura]]

---

> [!done] _New_

---
#### **11 ) -** Redes Neurais Convolucionais - CNNs

```ad-quote
title: **Def**
**Summary:**
- O objetivo é estudar arquiteturas voltadas para tarefas de visão computacional, explorando a extração de características por meio de filtros espaciais.
```

> [!quote] **Vault:** [[TF - CNN Layars]]

---

> [!done] _New_

---
#### **12 ) -** Redes Neurais Recorrentes (RNNs e LSTMs)

```ad-quote
title: **Def**
**Summary:**
- O foco é compreender as redes focadas em processamento de sequências, aplicáveis na modelagem de linguagem natural e análise de séries temporais.
```

> [!quote] **Vault:** [[TF - Redes Recorrentes]]

> [!quote] **Vault:** [[TF - LSTMs]]

---

```ad-done
title:
#### **Fase 4 )** - Otimização e Treinamento
```

```ad-quote
title:
Técnicas para compilar, treinar, regularizar e ajustar modelos, incluindo estratégias de otimização de hiperparâmetros e treinamento distribuído.
```

---

> [!done] _New_

---
#### **05 ) -** Compilação, Treinamento e Callbacks

```ad-quote
title: **Def**
**Summary:**
- O objetivo é aprender a compilar modelos, definir as estratégias de cálculo de erro e otimizadores, além de utilizar rotinas para monitorar o treinamento em tempo real.
```

> [!quote] **Vault:** [[Keras - Compilação de Modelos]]

> [!quote] **Vault:** [[Keras - Métodos Fit e Evaluate]]

> [!quote] **Vault:** [[Keras - Callbacks]]

---

> [!done] _New_

---
#### **08 ) -** Transfer Learning e Regularização

```ad-quote
title: **Def**
**Summary:**
- Aprender a utilizar pesos de redes pré-treinadas e aplicar técnicas para penalizar o modelo, melhorando a generalização e evitando o sobreajuste aos dados.
```

> [!quote] **Vault:** [[TF - Transfer Learning]]

> [!quote] **Vault:** [[TF - Técnicas de Regularização]]

---

> [!done] _New_

---
#### **10 ) -** Treinamento Distribuído e Personalização

```ad-quote
title: **Def**
**Summary:**
- O foco é aprender a escalar o treinamento em múltiplos dispositivos simultâneos e criar componentes personalizados para necessidades de arquitetura específicas.
```

> [!quote] **Vault:** [[TF - Treinamento Distribuído]]

> [!quote] **Vault:** [[TF - Personalização Avançada]]

---

> [!done] _New_

---
#### **16 ) -** Keras Tuner e Otimização de Hiperparâmetros

```ad-quote
title: **Def**
**Summary:**
- O objetivo é automatizar a busca pela melhor arquitetura e parâmetros ideais, substituindo a tentativa manual por algoritmos de busca sistemática.
```

> [!quote] **Vault:** [[Keras - Hyperparameter Tuning]]

> [!quote] **Vault:** [[Keras - Tuner Search Strategies]]

---

```ad-done
title:
#### **Fase 5 )** - Implantação e Produção
```

```ad-quote
title:
Preparação de modelos para o mundo real, incluindo otimização para dispositivos móveis e integração com sistemas de produção.
```

---

> [!done] _New_

---
#### **09 ) -** TensorFlow Extended (TFX) e TensorFlow Lite

```ad-quote
title: **Def**
**Summary:**
- O objetivo é explorar fluxos de produção profissionais e a otimização de redes para execução leve em dispositivos móveis ou sistemas embarcados.
```

> [!quote] **Vault:** [[TF - TensorFlow Extended]]

> [!quote] **Vault:** [[TF - TensorFlow Lite]]

---

> [!done] _New_

---
#### **17 ) -** Assinaturas de Modelos e Serving Avançado

```ad-quote
title: **Def**
**Summary:**
- O foco é preparar a exportação definitiva da rede e configurar a infraestrutura de predição contínua para responder a requisições em ambientes de produção.
```

> [!quote] **Vault:** [[TF - Serving e Assinaturas]]

---

```ad-done
title:
#### **Fase 6 )** - Ferramentas de Ecossistema e Visualização
```

```ad-quote
title:
Uso de ferramentas de diagnóstico e perfilamento para identificar gargalos e otimizar o desempenho dos modelos.
```

---

> [!done] _New_

---
#### **15 ) -** TensorFlow Profiler e Diagnóstico de Performance

```ad-quote
title: **Def**
**Summary:**
- Aprender a utilizar ferramentas avançadas para identificar gargalos de processamento entre as unidades de computação, otimizando o fluxo geral do modelo.
```

> [!quote] **Vault:** [[TF - TensorBoard Profiler]]

> [!quote] **Vault:** [[TF - Análise de Gargalos]]

---

```ad-done
title:
#### **Fase 7 )** - Customização e Controle Total
```

```ad-quote
title:
Para quem necessita de controle absoluto sobre o fluxo de treinamento e a arquitetura, esta fase aborda a criação de componentes do zero.
```

---

> [!done] _New_

---
#### **13 ) -** Model Subclassing e Custom Training Loops

```ad-quote
title: **Def**
**Summary:**
- O objetivo é aprender a criar modelos e camadas do zero absoluto, além de escrever laços de treinamento personalizados para controle total sobre o fluxo de gradientes.
```

> [!quote] **Vault:** [[TF - Model Subclassing]]

> [!quote] **Vault:** [[TF - Custom Training Loops]]

---