---
banner: "![[Pasted image 20260107191458.png]]"
---
---
#### **Intro )** - Fundamentos da Regressão Logística

```ad-quote
title: **Def**
**Summary:**
- A Regressão Logística é o _Alicerce De Classificação_ no _aprendizado de máquina_. Ela expande a regressão linear através de uma função de ativação, permitindo que o modelo tome decisões _binárias_ ou _multinomiais_ com base em _probabilidades_.
```

> [!done] **_New_**

```ad-quote
title: 
>[!quote] **Link:** [StatQuest - Logistic Regression](https://youtube.com/playlist?list=PLblh5JKOoLUKxzEP5HA2d-Li7IJkHfXSe&si=-dBBuFvr-9JnQagh)

>[!quote] **Link:** [Andrew Ng - Logistic Regression](https://www.youtube.com/watch?v=HIQlmHxI6-Y)
```

---

```ad-done
title:
#### **Fase 1 )** - Geometria da Probabilidade e Espaço Logit
```

---

```ad-quote
title: 
Esta fase foca na compreensão de como _esmagar_ uma reta infinita em um intervalo limitado entre _0 e 1_ para modelar incertezas.
```

---

> [!done] **_New_**

---
#### **01 ) -** Regressão Logística Formalizada

```ad-quote
title: **Def**
**Summary:**
- Estudo da _Função Sigmoide_ e sua aplicação sobre a _Combinação Linear_. Compreensão da _Razão De Chances (Odds)_ e como o _Logit_ lineariza a relação probabilística para o treinamento.
```

>[!quote] **Vault:** [[Lo R - Regressão Logística Formalizada]]

---

> [!done] **_New_**

---
#### **02 ) -** Regressão Logística - Premissas e Preparações

```ad-quote
title: **Def**
**Summary:**

- O modelo se divide entre aplicações _binárias_, _multinomiais_ e _ordinais_, exigindo rigor no tratamento de _outliers_ e _multicolinearidade_ para assegurar a validade das inferências estatísticas.
```

>[!quote] **Vault:** [[Lo R - Premissas e Limitações]]

---

> [!done] **_New_**

---
#### **03 ) -** Regressão Logística - Threshold e Regras de Decisão

```ad-quote
title: **Def**
**Summary:**
- Definição do _Limiar De Decisão (Threshold)_ para converter probabilidades em saídas discretas. Análise de como a escolha do _threshold_ impacta o rigor do modelo em cenários de risco.
```

> [!quote] **Vault:** [[RL - Threshold e Decisão]]

---

```ad-done
title:
#### **Fase 2 ) -** Otimização de Classificação e Extensões
```

---

```ad-quote
title: 
Nesta etapa, exploramos como o modelo avalia o erro de predição e como ele lida com múltiplas classes sob a ótica da _Teoria da Informação_.
```

---
#### **04 ) -** Função de Custo - Log Loss e Entropia Cruzada

```ad-quote
title: **Def**
**Summary:**
- Estudo da _Log Loss_ como mecanismo de punição para incertezas e erros de confiança. Compreensão da natureza _convexa_ desta função para garantir a eficiência da otimização.
```

> [!quote] **Vault:** [[RL - Log Loss e Funções de Custo]]

---

> [!done] **_New_**

---
#### **05 ) -** Multiclasse - De Sigmoid para Softmax

```ad-quote
title: **Def**
**Summary:**
- Expansão do modelo para cenários com mais de duas categorias. Diferenciação entre a ativação _Sigmoid_ (binária) e _Softmax_ (multicomial), essencial para classificação de _gêneros musicais_ ou _imagens_.
```

> [!quote] **Vault:** [[RL - Regressão Multinomial e Softmax]]

---

```ad-done
title:
#### **Fase 3 ) -** Métricas de Classificação e Auditoria
```

---

```ad-quote
title: 
Fase crítica onde o foco deixa de ser a variância explicada e passa a ser a _precisão_ e a _capacidade de separação_ entre as classes.
```

---
#### **06 ) -** Métricas de Avaliação - Desempenho e Separabilidade

```ad-quote
title: **Def**
**Summary:**
- A matriz de confusão decompõe erros e acertos para extrair métricas de _Precision_ e _Recall_, enquanto a curva ROC e o AUC quantificam a capacidade global de separação entre as classes em diferentes limiares de decisão.
```

> [!quote] **Vault:** [[Ro R - Métricas de Classificação]]

> [!quote] **Vault:** [[RL - Análise ROC e AUC]]

---

> [!done] **_New_**

---
#### **07 ) -** Análises do Modelo - Validando a Estrutura

```ad-quote
title: **Def**
**Summary:**
- Está nota visa criar uma série de códigos simples para plotar uma série de gráficos para análise e produção de forma automática.
```

>[!quote] **Vault:** [[LC - Visual Diagnostics & Plots]]

---

```ad-done
title:
#### **Fase 4 ) -** Auditoria e Análises do Modelo
```

---

```ad-quote
title: 
Esta etapa final é dedicada à _governança_ e ao _rigor estatístico_. O objetivo é auditar a estrutura interna do classificador para identificar instabilidades matemáticas, como a _multicolinearidade_.
```

---
#### **08 ) -** Auditoria e Vieses - Premissas de Classificação

```ad-quote
title: **Def**
**Summary:**
- Verificação de _Independência_, _Multicolinearidade_ (via VIF) e influência de _Outliers_ no ajuste da fronteira de decisão. Identificação de _separação perfeita_ nos dados.
```

> [!quote] **Vault:** [[RL - Auditoria e Limitações]]

---