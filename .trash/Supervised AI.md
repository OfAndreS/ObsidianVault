---
banner: "![[Pasted image 20251002111625.png]]"
banner-x: 50
banner-y: 45
---
---

![[Task - Bases.base#Predictive AI]]

---
#### **Intro )** - Fundamentos e Mecânica Interna

```ad-quote
title: **Def**
**Summary:**
- Introdução aos conceitos de Inteligência Artificial, Machine Learning e Deep Learning, e como eles se aplicam ao processamento de áudio. Visão geral do curso e dos pré-requisitos.
```

> [!quote] **Vault:** [[Intro - Deep Learning]]

>[!quote] **Vault:** [[DL P - General Concepts]]

>[!quote] **Vault:** [[DL P - Modalidades do Aprendizado de Máquina]]

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
#### **00 ) -** A Base - Neurônios Artificiais

```ad-quote
title: **Def**
**Summary:**
 - Estudo da Unidade Fundamental que compõe as redes e como ela realiza o Processamento Linear de dados de entrada.
```

> [!quote] **Vault:** [[DL P - Neuronio Artificial]]

---

> [!done] _New_

---
#### **01 ) -** Não-Linearidade - Funções de Ativação

```ad-quote
title: **Def**
**Summary:**
- Compreensão de como introduzir Complexidade Matemática para que a rede aprenda Padrões Não Lineares.
```

> [!quote] **Vault:** [[DL - Funções de Ativação]]

---

> [!done] _New_

---
#### **02 ) -** Design de Saída - Estruturando Inputs e Outputs

```ad-quote
title: **Def**
**Summary:**
- Definição da Arquitetura Com Base No Problema, conectando a camada final à Natureza Da Predição (Binária, Multiclasse, etc.).
```

> [!quote] **Vault:** [[Sup IA - Estruturando Inputs]]

> [!quote] **Vault:** [[Sup IA - Estruturando Outputs]]

---

> [!done] _New_

---
#### **03 ) -** Evolução de Fluxo - Conexões Residuais Skip Connections

```ad-quote
title: **Def**
**Summary:**
- Estudo de técnicas que permitem que a informação pule camadas, facilitando o treinamento de Redes Muito Profundas.
```

> [!quote] **Vault:** [[DL - Conexões Residuais]]

---

```ad-done
title:
### **Fase 2 ) -** O Mecanismo de Aprendizado e Otimização
```

---

```ad-quote
title:
Nesta etapa, o foco é o Aparato Matemático que permite ao modelo ajustar seus parâmetros internos.
```

---
#### **04 ) -** Quantificando o Erro - Funções de Custo Loss

```ad-quote
title: **Def**
**Summary:**
- Definição da métrica que quantifica a Distância Entre A Predição e o Valor Real desejado.
```

> [!quote] **Vault:** [[DL P - Funções de Custo]]

---

> [!done] _New_

---
#### **05 ) -** O Motor do Aprendizado - Backpropagation e Gradiente Descendente

```ad-quote
title: **Def**
**Summary:**
- O processo de Retropropagação Do Erro para atualizar os pesos e vieses da rede de forma iterativa.
```

> [!quote] **Vault:** [[DL P - Forward Propagation]]

> [!quote] **Vault:** [[DL P - Gradient Descent]]

> [!quote] **Vault:** [[DL P - Backpropagation]]

---

> [!done] _New_

---
#### **06 ) -** Estabilidade Numérica - O Problema do Gradiente

```ad-quote
title: **Def**
**Summary:**
- Diagnóstico de falhas onde o Gradiente Desaparece Ou Explode, impedindo que as camadas iniciais aprendam corretamente.
```

> [!quote] **Vault:** [[DL - Vanishing and Exploding Gradients]]

---

> [!done] _New_

---
#### **07 ) -** Eficiência - Otimizadores e Inicialização de Pesos

```ad-quote
title: **Def**
**Summary:**
- Uso de algoritmos como Adam e técnicas como He Initialization para garantir uma Convergência Rápida E Estável.
```

> [!quote] **Vault:** [[DL - Algoritmos de Otimização]]

> [!quote] **Vault:** [[DL P - Inicialização de Pesos]]

---

```ad-done
title:
#### **Fase 3 ) -** Diagnóstico Validação e Generalização
```

---

```ad-quote
title:
Fase crítica para garantir que a IA Preditiva seja confiável e funcione em Dados Reais Não Vistos.
```

---
#### **08 ) -** Dados do Mundo Real - Lidando com Desbalanceamento - OBS

```ad-quote
title: **Def**
**Summary:**
- Estratégias para treinar modelos quando uma Classe É Muito Mais Frequente que a outra, evitando Predições Viesadas.
```

> [!quote] **Vault:** [[DL - Class Imbalance]]

---

> [!done] _New_

---
#### **09 ) -** Métricas de Avaliação de Performance

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
#### **10 ) -** Controle de Treinamento - Overfitting e Early Stopping

```ad-quote
title: **Def**
**Summary:**
- Identificação do momento em que o modelo começa a Decorar O Ruído e aplicação da Interrupção Antecipada para preservar a Generalização.
```

> [!quote] **Vault:** [[DL P - Overfitting & Underfitting]]

> [!quote] **Vault:**  [[DL - Early Stopping]]

---

> [!done] _New_

---
#### **11 ) -** O Equilíbrio - Viés e Variância - Bias-Variance Tradeoff

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
#### **12 ) -** Refinamento Dinâmico - Taxa de Aprendizagem e Batch Normalization

```ad-quote
title: **Def**
**Summary:**
- Ajuste do Hiperparâmetro Mais Importante e normalização das ativações para um Fluxo De Gradiente mais suave.
```

> [!quote] **Vault:** [[DL - Taxa de Aprendizagem]]

> [!quote] **Vault:** [[DL P - Normalização em Batch]]

---

```ad-done
title:
#### **Fase 4 ) -** Robustez e Técnicas Avançadas
```

---

```ad-quote
title:
Técnicas para elevar o desempenho e reaproveitar conhecimento em problemas complexos.
```

---
#### **13 ) -** Regularização - Dropout e L1/L2

```ad-quote
title: **Def**
**Summary:**
- Métodos para reduzir a Dependência Excessiva de certos neurônios, tornando a Rede Mais Robusta.
```

> [!quote] **Vault:** [[DL P - Dropout]]

---

> [!done] _New_

---
#### **14 ) -** Eficiência de Conhecimento - Transfer Learning e Fine-Tuning

```ad-quote
title: **Def**
**Summary:**
- Como adaptar Modelos Pré-Treinados para novas tarefas, economizando Tempo E Recursos Computacionais.
```

> [!quote] **Vault:** [[DL - Aprendizagem por Transferência]]

> [!quote] **Vault:** [[DL - Ajuste Fino]]

---

> [!done] _New_

---
#### **15 ) -** Preparação e Expansão - Processamento e Aumento de Dados - OBS

```ad-quote
title: **Def**
**Summary:**
- Técnicas para enriquecer o conjunto de treino e garantir que a IA seja Invariante A Pequenas Alterações nos inputs.
```

> [!quote] **Vault:** [[DL - Processamento e Aumento de Dados]]

---

> [!done] _New_

---
#### **16 ) -** Busca Pela Excelência - Ajuste de Hiperparâmetros

```ad-quote
title: **Def**
**Summary:**
- Métodos sistemáticos para encontrar a Configuração Ideal de camadas, neurônios e taxas de aprendizado.
```

> [!quote] **Vault:** [[DL - Ajuste de Hiperparâmetros]]

---
