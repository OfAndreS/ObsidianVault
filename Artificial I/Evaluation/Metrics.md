
---
#### **01 ) -** Métricas de Distância

```ad-quote
title: **Def**
**Summary:**
- 
```

>[!quote] **Vault:** [[Met - Métricas de Distância]]

---

> [!done] **_New_**

---

## 1. Métricas de Classificação (Binária e Multiclasse)

### Suíte da Matriz de Confusão

- Acurácia
    
- Precisão
    
- Revocação / Sensibilidade (_Recall_ / _Sensitivity_)
    
- F1-Score
    
- Especificidade (_Specificity_)
    
- Coeficiente Kappa de Cohen
    

### Ordenação e Discriminação

- AUC-ROC
    
- Coeficiente de Gini
    
- Estatística Kolmogorov-Smirnov (KS)
    

### Calibração e Incerteza

- Log Loss (_Binary Cross-Entropy_)
    
- Brier Score
    
- Diagrama de Confiabilidade (_Calibration Curve_)
    

### Performance em Dados Desbalanceados

- Coeficiente de Correlação de Matthews (MCC)
    
- Curva de Precisão-Revocação (_PR Curve_)
    
- AUC-PR
    
- Acurácia Balanceada
    

---
## 2. Métricas de Regressão

### Erros de Magnitude e Escala

- Erro Médio Absoluto (MAE)
    
- Erro Médio Percentual Absoluto (MAPE)
    
- Erro Quadrático Médio (MSE)
    
- Raiz do Erro Quadrático Médio (RMSE)
    

### Variância e Ajuste do Modelo

- Coeficiente de Determinação (R²)
    
- R² Ajustado
    
- Variância Explicada
    

---
## 3. Métricas de Agrupamento (Clustering)

### Validação de Estrutura e Coesão

- Coeficiente de Silhueta (_Silhouette Score_)
    
- Índice Calinski-Harabasz
    
- Índice Davies-Bouldin
    

### Comparação com Rótulos Externos

- Índice Rand Ajustado (ARI)
    
- Informação Mútua Normalizada (NMI)
    
- Homogeneidade, Completude e V-Measure
    

---

## 4. Métricas de Ranking e Recomendação

### Relevância e Precisão de Ordenação

- Ganho Cumulativo Descontado Normalizado (NDCG)
    
- Precisão em K (P@K)
    
- _Mean Reciprocal Rank_ (MRR)
    
- _Average Precision_ (AP)
    

---

## 5. Métricas de Processamento de Linguagem Natural (NLP)

### Qualidade de Geração e Tradução

- BLEU Score
    
- ROUGE (N, L, S)
    
- METEOR
    

### Probabilidade e Ajuste de Linguagem

- Perplexidade (_Perplexity_)
    
- _Word Error Rate_ (WER)
    

---

## 6. Métricas de Visão Computacional

### Localização e Identificação de Objetos

- _Intersection over Union_ (IoU)
    
- _Mean Average Precision_ (mAP)
    
- Erro de Distância Euclidiana
    

---

Com essa estrutura, recomendo que no seu Obsidian você use a pasta principal para o tipo de métrica (ex: **Regressão**) e cada nota interna represente um cluster (ex: **Erros de Magnitude.md**). Dentro de cada nota, você utiliza subtítulos para as métricas individuais.

Essa abordagem reduzirá drasticamente o número de arquivos, mantendo a teoria conectada e facilitando a comparação entre fórmulas _irmãs_. Gostaria que eu criasse um exemplo de como seria a estrutura de links entre essas notas dentro do aplicativo?