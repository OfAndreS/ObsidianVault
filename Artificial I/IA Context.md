---
banner: Pasted image 20260118174047.png
banner-x: 50
banner-y: 35
banner-fade: 100
---
---

```ad-done
title:
#### **Fase 1 ) - Algoritmos Supervisionados (`Algorithms/Supervised`)**
```

---

````ad-quote
title:

##### **01 )** - Diretório `Supervised/Concepts`

```ad-quote
title:
<p align="justify">O diretório de conceitos supervisionados funciona atualmente como o núcleo teórico fundamental de todo o módulo de Inteligência Artificial, organizando a base matemática de aprendizado, otimização e diagnóstico de modelos.</p>
```

```bash
01 ) Fundamentos e Paradigmas de Aprendizado
# Definição das fronteiras entre Inteligência Artificial, Machine Learning e Deep Learning (Intro - Deep Learning, DL P - General Concepts) e classificação das modalidades de aprendizado (DL P - Modalidades do Aprendizado de Máquina).


02 ) Design Estrutural de Entradas e Saídas
# Formatação da matriz de atributos de entrada (Sup IA - Estruturando Inputs) e configuração da camada de saída de acordo com a natureza da predição binária, multiclasse ou contínua (Sup IA - Estruturando Outputs).


03 ) Quantificação de Erro e Otimização Matemática
# Formulação das funções de perda (Sup AI - Funções de Perda) para medir a distância entre predição e valor real, acoplada à atualização iterativa de parâmetros pelo Gradiente Descendente (DL P - Gradient Descent).


04 ) Diagnóstico de Generalização e Estabilidade
# Estudo do erro sistemático (DL P - Viés), do equilíbrio entre simplicidade e flexibilidade (DL P - Viés e Variância), prevenção de memorização de ruído (DL P - Overfitting & Underfitting) e avaliação em classificação (DL P - Evaluating Performance - Classification).
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Temas Faltantes e Expansão Futura (`Supervised/Concepts`)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Lacunas Já Mapeadas no Índice*
```

```ad-quote
title:
<p align="justify">Existem notas que já foram estruturadas no roteiro principal do diretório, mas que ainda aguardam a criação de seus arquivos definitivos com a formalização matemática e exemplos práticos.</p>
```

```bash
01 ) Regularização Matemática (L1, L2 e ElasticNet)
# Formalização da penalização de pesos (Lasso e Ridge) diretamente na função de custo para restringir a complexidade do modelo e conter a variância (ML - Regularização L1 e L2).


02 ) Controle Dinâmico de Treinamento
# Critérios de parada antecipada (DL - Early Stopping) baseados na divergência da curva de validação e estratégias de agendamento da taxa de aprendizado (DL - Taxa de Aprendizagem: Warmup, Step Decay, Cosine Annealing).


03 ) Engenharia de Treinamento e Validação
# Protocolos de Validação Cruzada (K-Fold, Stratified K-Fold, Leave-One-Out), prevenção contra Vazamento de Dados (Data Leakage) em pipelines temporais/tabulares e busca sistemática de hiperparâmetros (DL - Ajuste de Hiperparâmetros: Grid Search, Random Search, Otimização Bayesiana com Optuna).
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Caminhos de Expansão Teórica*
```

```bash
01 ) Teoria da Informação Aplicada ao Aprendizado
# Entropia de Shannon, Entropia Cruzada (Cross-Entropy) derivada da máxima verossimilhança e Divergência de Kullback-Leibler (KL Divergence) para medir distância entre distribuições de probabilidade.


02 ) Calibração de Probabilidades e Limiares de Decisão
# Curvas de calibração (Platt Scaling, Isotonic Regression), Brier Score e ajuste fino de Decision Thresholds para problemas com classes severamente desbalanceadas.


03 ) Interpretabilidade e Explicabilidade de Modelos (XAI)
# Valores de Shapley (SHAP), LIME, Partial Dependence Plots (PDP) e Permutation Importance para auditoria de decisões em modelos caixa-preta.
```
````

---

````ad-quote
title:

##### **02 )** - Diretório `Supervised/Architecture` (ML Clássico: `LM`, `SVM`, `EM`)

```ad-quote
title:
<p align="justify">Este segmento reúne as arquiteturas clássicas voltadas para dados tabulares e relações estatísticas estruturadas, divididas atualmente em três famílias principais de algoritmos.</p>
```

```bash
01 ) Modelos Lineares (Subpasta LM/)
# Acervo consolidado contendo a formalização matemática da Regressão Linear (Li R - Regressão Linear Formalizada), Regressão Polinomial (Po R - Regressão Polinomial Formalizada) e Regressão Logística (Lo R - Regressão Logística Formalizada), além de suas premissas estatísticas (LR - Premissas e Preparação, Lo R - Premissas e Limitações) e métricas dedicadas.


02 ) Modelos de Conjunto / Ensembles (Subpasta EM/)
# Estrutura guiada pelo índice Ensemble Models, documentando a combinação de múltiplos estimadores fracos através de paralelismo via amostragem Bootstrap (EM - Bagging Models) e aprendizado sequencial focado em resíduos (EM - Boosting Models).


03 ) Máquinas de Vetores de Suporte (Subpasta SVM/)
# Diretório já provisionado na árvore de arquiteturas com a nota índice (SVM.md) e a subpasta All/, aguardando o preenchimento de suas notas conceituais e matemáticas.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Temas Faltantes e Expansão Futura (ML Clássico)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Consolidação das Pastas Existentes (`LM`, `SVM`, `EM`)*
```

```bash
01 ) Expansão de SVM (Atualmente Vazia)
# Formulação do Hiperplano de Margem Máxima, Vetores de Suporte, Margem Suave (parâmetro C), Dualidade de Lagrange e o Truque do Kernel (Linear, Polinomial, RBF/Gaussiano) tanto para classificação (SVC) quanto regressão (SVR).


02 ) Árvores de Decisão Puras e Impureza (Base para EM)
# Algoritmo CART, cálculo de Ganho de Informação, Entropia vs. Índice Gini, poda de árvores (Pruning) e detalhamento algorítmico das implementações modernas de Gradient Boosting (XGBoost, LightGBM e CatBoost).


03 ) Modelos Lineares Generalizados (GLMs)
# Regressão de Poisson, Regressão Gamma e funções de ligação (Link Functions) para variáveis alvo que não seguem distribuição normal.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Novas Arquiteturas Clássicas para Incluir no Futuro*
```

```ad-quote
title:
| Nova Pasta Sugerida | Escopo Conceitual | Algoritmos Principais |
| :--- | :--- | :--- |
| **`Naive Bayes & Probabilistic/`** | Classificadores generativos baseados no Teorema de Bayes e independência condicional. | GaussianNB, MultinomialNB, BernoulliNB, Processos Gaussianos. |
| **`Instance-Based (k-NN)/`** | Aprendizado preguiçoso (*Lazy Learning*) baseado em proximidade geométrica no espaço de atributos. | k-Nearest Neighbors, ponderação por distância, estruturas KD-Tree e Ball-Tree. |
| **`Time Series Classical/`** | Modelagem autorregressiva e decomposição de tendência/sazonalidade antes do uso de Deep Learning. | ARIMA, SARIMA, SARIMAX, Suavização Exponencial (Holt-Winters), Prophet. |
```
````

---

````ad-quote
title:

##### **03 )** - Diretório `Supervised/Architecture` (Redes Neurais: `MLP`, `CNN` e Sequenciais)

```ad-quote
title:
<p align="justify">Dentro da camada de arquiteturas neurais, o diretório concentra a base matemática de Redes Neurais Profundas, contando hoje com as pastas de Perceptrons Multicamadas e Redes Convolucionais.</p>
```

```bash
01 ) Anatomia e Fluxo da MLP (Subpasta MLP/)
# Estudo completo da unidade fundamental de processamento afim (MLP - Artificial Neuron), introdução de não-linearidades (MLP - Activation Functions), propagação direta de tensores (DL P - Forward Propagation) e construção prática da rede sem frameworks (MLP - Simple Neural Network From Scratch).


02 ) Estabilidade Numérica e Regularização Neural (Subpasta MLP/All/)
# Notas universais de Deep Learning que controlam o fluxo de gradientes e a distribuição das ativações internas: inicialização de pesos (DL P - Weight Initialization), normalização em lote e por camada (DL P - Batch Normalization, DL P - Layer Normalization) e desligamento estocástico de neurônios (DL P - Dropout).


03 ) Extração Espacial em Redes Convolucionais (Subpasta CNN/)
# Fundamentos da visão bidimensional em redes neurais (CNN.md), detalhando a operação matemática de convolução (CNN - Convolution) e o papel dos filtros matriciais compartilhados (CNN - Kernel).
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Temas Faltantes e Expansão Futura (Redes Neurais e Sequenciais)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Complementos para `MLP` e `CNN`*
```

```bash
01 ) Fechamento do Ciclo Matemático da MLP
# Criar as notas já referenciadas no índice de MLP mas ainda inexistentes como arquivo: DL P - Backpropagation (derivação passo a passo pela Regra da Cadeia), DL P - Optimization Algorithms (Momentum, RMSprop, Adam, AdamW) e DL P - Vanishing and Exploding Gradients.


02 ) Anatomia Completa e Evolução das CNNs
# Formalizar camadas de Pooling (Max, Average, Global), cálculo dimensional com Padding/Stride/Dilation, Convoluções 1D (para áudio e séries temporais), Depthwise Separable Convolutions (MobileNet) e Conexões Residuais/Skip Connections (ResNet).
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Nova Pasta: `RNN/` (Modelos Recorrentes e Sequenciais)*
```

```ad-quote
title:
<p align="justify">Esta é a principal lacuna imediata para acomodar seus estudos de processamento sequencial e séries temporais. Deve ser criada como irmã de <code>MLP</code> e <code>CNN</code> (ou dentro de um módulo dedicado de <code>Deep Learning/Architectures</code>).</p>
```

```bash
01 ) RNN Vanilla e Dinâmica Temporal
# Estado oculto recorrente (h_t), compartilhamento de pesos no tempo, desdobramento do grafo computacional e o algoritmo Backpropagation Through Time (BPTT), evidenciando por que gradientes somem ou explodem em sequências longas.


02 ) LSTM (Long Short-Term Memory)
# Anatomia da célula de memória (Cell State c_t) como "esteira transportadora" de gradiente e equações dos três portões: Forget Gate, Input Gate (com Candidate Layer) e Output Gate.


03 ) GRU (Gated Recurrent Unit)
# Simplificação estrutural da LSTM unificando estado de célula e estado oculto através do Update Gate e do Reset Gate, comparando custo computacional versus capacidade de retenção.


04 ) Topologias Sequenciais Avançadas
# Redes Recorrentes Bidirecionais (BiRNN / BiLSTM), Redes Recorrentes Empilhadas (Stacked RNNs) e a arquitetura Encoder-Decoder clássica (Seq2Seq) com Mecanismo de Atenção de Bahdanau/Luong.
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Nova Pasta: `Transformers/` e Fronteiras do Deep Learning*
```

```bash
01 ) A Arquitetura Transformer Base
# Fim da recorrência sequencial: Scaled Dot-Product Attention (Matrizes Query, Key, Value), Multi-Head Attention, Masked Self-Attention, Positional Encoding (Sinusoidal, Aprendido e RoPE), Residual Connections e Pre-LN vs. Post-LN.


02 ) Variantes Estruturais de Transformers
# Distinção arquitetural e matemática entre modelos Encoder-Only (família BERT/RoBERTa para representação bidirecional), Decoder-Only (família GPT/Llama autorregressiva) e Encoder-Decoder (T5, BART).


03 ) Expansões Futuras de Arquiteturas Neurais
# Graph Neural Networks (GNNs: GCN, GAT para dados em grafos), State Space Models (SSMs e arquitetura Mamba como alternativa sub-quadrática aos Transformers) e Kolmogorov-Arnold Networks (KAN).
```
````

---

```ad-done
title:
#### **Fase 2 ) - Aprendizado Não-Supervisionado (`Algorithms/Unsupervised`)**
```

---

````ad-quote
title:

##### **04 )** - Diretórios `Unsupervised/Concepts` e `Unsupervised/Architecture`

```ad-quote
title:
<p align="justify">O módulo não-supervisionado cobre a descoberta de estruturas latentes, agrupamentos e compressão dimensional em dados sem rótulos, possuindo uma árvore de pastas já desenhada para receber diversas famílias de algoritmos.</p>
```

```bash
01 ) Conceitos e Limitações Espaciais (Subpasta Concepts/)
# Conta com a nota índice (Unsupervised IA.md) e o estudo aprofundado sobre como a esparsidade afeta métricas de distância em altas dimensões (uSup IA - Maldição da Dimensionalidade).


02 ) Agrupamento / Clustering (Subpastas K-Means/, DBSCAN/, Hierarchical/)
# Possui a estrutura de K-Means já populada com a teoria e formulação matemática de centróides e inércia (K-Means.md, KM - K-Means Formalizado), enquanto DBSCAN e Hierarchical (Hier.md) contam com as pastas criadas em estágio inicial.


03 ) Redução de Dimensionalidade e Representações (Subpastas PCA/, t-SNE/, UMAP/, Auto Encoders/, Embeddings/)
# Diretórios estruturados na árvore de arquiteturas não-supervisionadas (incluindo PCA.md), servindo atualmente como esqueletos organizacionais prontos para o detalhamento matemático.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 4.1 ) - _Temas Faltantes e Expansão Futura (`Unsupervised`)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Preenchimento das Pastas Já Criadas*
```

```bash
01 ) Clustering Baseado em Densidade e Hierarquia (DBSCAN e Hierarchical)
# Formalizar conceitos de Core Points, Border Points e Noise no DBSCAN (parâmetros Epsilon e MinPts), sua evolução para HDBSCAN, além de Dendrogramas e matrizes de ligação (Single, Complete, Ward Linkage) no agrupamento hierárquico.


02 ) Redução de Dimensionalidade Linear e Não-Linear (PCA, t-SNE, UMAP)
# Decomposição em Autovalores/Autovetores da matriz de covariância e Decomposição em Valores Singulares (SVD) no PCA; minimização de divergência KL entre probabilidades de vizinhança no t-SNE; e preservação topológica de variedades (Manifold Learning) no UMAP.


03 ) Autoencoders e Espaços Latentes
# Arquitetura Encoder-Bottleneck-Decoder, reconstrução via MSE, Denoising Autoencoders, Sparse Autoencoders e a transição probabilística para os Variational Autoencoders (VAE) com o Reparameterization Trick.


04 ) Embeddings e Representação Vetorial
# Como transformar entidades discretas em vetores contínuos densos, álgebra vetorial semântica, aprendizado contrastivo (Contrastive Learning) e indexação em bancos vetoriais (HNSW, FAISS).
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Expansões Futuras para Aprendizado Não-Supervisionado*
```

```ad-quote
title:
| Tema Faltante | O que abordar |
| :--- | :--- |
| **Métricas de Avaliação Interna** | Silhouette Score, Davies-Bouldin Index, Calinski-Harabasz e Método do Cotovelo (Inércia/WCSS) para avaliar clusters sem rótulos reais. |
| **Gaussian Mixture Models (GMM)** | Agrupamento probabilístico suave (*Soft Clustering*) treinado via algoritmo de Expectativa-Maximização (EM). |
| **Detecção de Anomalias e Outliers** | Isolation Forest, Local Outlier Factor (LOF), One-Class SVM e uso de erro de reconstrução de Autoencoders para detecção de fraudes/falhas. |
| **Self-Supervised Learning (SSL)** | O elo moderno entre o não-supervisionado e o Deep Learning: tarefas pretextuais, Masked Autoencoders (MAE), SimCLR e DINO. |
```
````

---

```ad-done
title:
#### **Fase 3 ) - IA Generativa e Avaliação (`Generative` & `Evaluation`)**
```

---

````ad-quote
title:

##### **05 )** - Diretório `Algorithms/Generative`

```ad-quote
title:
<p align="justify">O diretório de Inteligência Artificial Generativa separa os fundamentos probabilísticos de geração da engenharia de Grandes Modelos de Linguagem, encontrando-se atualmente em fase inicial de estruturação.</p>
```

```bash
01 ) Conceitos Generativos (Subpasta Concepts/)
# Contém o arquivo índice Generative AI.md reservado para receber a teoria sobre modelagem de distribuições de probabilidade e geração de dados sintéticos.


02 ) Arquitetura e Infraestrutura de LLMs (Subpasta Architecture/LLM/)
# Reúne a nota principal LLM.md com referências de execução em produção e containers de alto desempenho (vLLM, Apptainer), acompanhada do diagrama arquitetural em LLM.excalidraw.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 5.1 ) - _Temas Faltantes e Expansão Futura (`Generative`)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Fundamentos de IA Generativa (`Generative/Concepts`)*
```

```bash
01 ) Modelos Discriminativos vs. Modelos Generativos
# A diferença matemática entre modelar a probabilidade condicional P(Y|X) (classificar uma fronteira de decisão) e modelar a distribuição conjunta P(X,Y) ou marginal P(X) para amostrar novos dados sintéticos.


02 ) Estratégias de Decodificação e Amostragem (Sampling)
# Greedy Search, Beam Search, Temperature Scaling, Top-K Sampling e Top-P (Nucleus Sampling) controlando o equilíbrio entre determinismo factual e criatividade estocástica.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Ciclo Completo de LLMs e Modelos de Difusão (`Generative/Architecture`)*
```

```bash
01 ) Pré-Treinamento, Adaptação e Alinhamento de LLMs
# Scaling Laws (Chinchilla), Supervised Fine-Tuning (SFT), métodos eficientes em parâmetros (PEFT: LoRA, QLoRA, DoRA) e alinhamento com preferências humanas (RLHF com PPO, DPO e GRPO).


02 ) Engenharia de Sistemas com LLMs (RAG e Agentes)
# Arquitetura completa de Retrieval-Augmented Generation (Chunking, Reranking, Hybrid Search), Function/Tool Calling, raciocínio em cadeia (Chain-of-Thought, ReAct) e orquestração multi-agente.


03 ) Otimização de Inferência em Produção
# Mecânica do KV Cache, PagedAttention (vLLM), Quantização pós-treinamento (GPTQ, AWQ, GGUF, FP8), FlashAttention e Speculative Decoding.


04 ) Geração Visual e Áudio (GANs e Modelos de Difusão)
# Redes Adversariais Generativas (Jogo Minimax entre Gerador e Discriminador, Wasserstein GAN) e Modelos de Difusão Latente (DDPM, adição/remoção iterativa de ruído gaussiano, U-Net condicionada por CLIP e Flow Matching).
```
````

---

````ad-quote
title:

##### **06 )** - Diretório `Evaluation`

```ad-quote
title:
<p align="justify">Localizado na raiz de <code>Artificial I</code>, o diretório de avaliação centraliza o instrumental matemático e geométrico para aferir a qualidade dos modelos preditivos e descritivos.</p>
```

```bash
01 ) Diagnóstico de Classificação (Subpasta Evaluation/All/)
# Guiado pelo índice Metrics.md, documenta a estrutura de acertos e erros (Verdadeiros/Falsos Positivos e Negativos) através da nota MV - Matriz de Confusão.


02 ) Geometria e Proximidade (Subpasta Evaluation/All/)
# Formalização das medidas de similaridade e dissimilaridade em espaços vetoriais através da nota Met - Métricas de Distância (Euclidiana, Manhattan, Cosseno, etc.).


03 ) Notas de Avaliação Distribuídas em Outros Diretórios
# Atualmente, o Vault também possui estudos de métricas alocados dentro de modelos lineares e conceitos supervisionados (LR - Métricas de Regressão, Ro R - Métricas de Classificação e DL P - Evaluating Performance - Classification) que se conectam diretamente a este diretório.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 6.1 ) - _Temas Faltantes e Expansão Futura (`Evaluation`)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Unificação e Novas Famílias de Métricas*
```

```bash
01 ) Métricas de Ranking e Sistemas de Recomendação
# Precision@K, Recall@K, Mean Average Precision (MAP), Mean Reciprocal Rank (MRR) e Normalized Discounted Cumulative Gain (nDCG), essenciais para avaliar motores de busca e pipelines de RAG.


02 ) Métricas para Geração de Texto e LLMs
# Métricas léxicas clássicas (BLEU, ROUGE, METEOR), métricas semânticas baseadas em embeddings (BERTScore) e paradigmas modernos de avaliação (LLM-as-a-Judge, RAGAS para avaliar fidelidade e relevância de contexto).


03 ) Métricas de Visão Computacional e Áudio
# Intersection over Union (IoU / Jaccard Index), mean Average Precision (mAP) para detecção de objetos, Dice Coefficient para segmentação médica/visual e Word Error Rate (WER) para reconhecimento de fala.


04 ) Testes Estatísticos para Comparação de Modelos
# Teste de McNemar, Teste t pareado em validação cruzada (5x2cv) e intervalos de confiança via Bootstrap para provar se o ganho de um modelo sobre outro é estatisticamente significativo.
```
````

---

```ad-done
title:
#### **Fase 4 ) - Aplicações e Ferramentas (`Applications` & `Frameworks`)**
```

---

````ad-quote
title:

##### **07 )** - Diretório `Applications` (`Language Processor` & `Computer Vision`)

```ad-quote
title:
<p align="justify">O diretório de aplicações conecta a teoria matemática das arquiteturas aos domínios reais de dados não-estruturados, traduzindo modelos em soluções para texto e imagem.</p>
```

```bash
01 ) Processamento de Linguagem Natural (Subpasta Language Processor/)
# Estruturado pelo roteiro completo em três fases (NLP.md), já possui as notas fundamentais sobre segmentação de texto em unidades semânticas (NLP - Tokenização) e avaliação de previsibilidade e variação textual (NLP - Burstiness & Perplexity).


02 ) Visão Computacional (Subpasta Computer Vision/)
# Conta com o diretório dedicado e a nota índice inicial (CV.md) criados para centralizar o processamento de imagens e vídeo.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 7.1 ) - _Temas Faltantes e Expansão Futura (`Applications`)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Desenvolvimento das Notas Pendentes em `Language Processor`*
```

```bash
01 ) Representações Clássicas e Semânticas (Já listadas no índice NLP.md)
# Criar as notas pendentes do roteiro: NLP - Vetores de Estatísticas de Palavras (Bag-of-Words, N-Grams, TF-IDF, BM25), NLP - Word Embeddings (Word2Vec CBOW/Skip-Gram, GloVe, FastText) e NLP - Vetores Densos e Bancos Vetoriais.


02 ) Tarefas Fundamentais de PLN
# Reconhecimento de Entidades Nomeadas (NER), POS Tagging, Análise de Sentimento, Modelagem de Tópicos (LDA, BERTopic), Sumarização Extrativa vs. Abstrativa e NLP - Grounding e Conhecimento.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Construção Completa de `Computer Vision` e Novos Domínios*
```

```ad-quote
title:
| Subdiretório | Temas Faltantes para Construir |
| :--- | :--- |
| **`Computer Vision/`** | Representação digital de imagens (tensores RGB, espaços de cor HSV/Lab), filtragem espacial (Sobel, Gaussiano), Data Augmentation geométrico/fotométrico, Detecção de Objetos (família YOLO, Faster R-CNN), Segmentação Semântica e de Instância (U-Net, Mask R-CNN, SAM) e Vision Transformers (ViT, Swin Transformer). |
| **`Audio & Speech/` (Novo)** | Ponte direta com seus estudos em `Analytics/Types/Audio`: pré-processamento de sinais em IA (STFT, Mel-Spectrograms, MFCCs), Classificação de Áudio, Reconhecimento Automático de Fala (ASR / Whisper), Diarização de Locutores e Síntese de Voz (TTS). |
| **`Reinforcement Learning/` (Novo)** | Processos de Decisão de Markov (MDP), Equação de Bellman, Trade-off Exploration vs. Exploitation, Q-Learning, Deep Q-Networks (DQN), Actor-Critic e Proximal Policy Optimization (PPO). |
```
````

---

````ad-quote
title:

##### **08 )** - Diretório `Frameworks` (`TensorFlow` & `PyTorch`)

```ad-quote
title:
<p align="justify">O diretório de frameworks documenta a tradução dos conceitos matemáticos em código executável, cobrindo a manipulação de tensores, pipelines de dados e APIs de construção de redes neurais.</p>
```

```bash
01 ) Fundamentos e Ingestão no TensorFlow (Subpasta TensorFlow/)
# Guiado pela nota TF - TensorFlow e pelo roteiro TF - Roteiro, abrange a introdução ao ecossistema (Intro - TensorFLow), manipulação algébrica de tensores (TF - Tensores e Operações) e construção de pipelines assíncronos de leitura e transformação (TF - API tf.data).


02 ) Modelagem de Alto Nível com Keras (Subpasta TensorFlow/All/)
# Documenta todo o ciclo de vida de redes neurais na API Keras: construção de camadas (Keras - API Sequencial, Keras - Sequencial Simple Dir, TF - CNN Layars), diagnóstico topológico (Keras - Diagnostico Estrutura), configuração de otimizadores/perdas (Keras - Compilação de Modelos) e execução de treino/validação (Keras - Métodos Fit e Evaluate, Keras - Pipeline).


03 ) Ecossistema PyTorch (Subpasta PyTorch/)
# Possui o diretório e o arquivo principal (PyTorch.md) inicializados, aguardando a adição das notas práticas na subpasta All/.
```
````

> [!done] **_New_**

```ad-quote
title:

##### 8.1 ) - _Temas Faltantes e Expansão Futura (`Frameworks`)_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Expansão de `PyTorch` e Recursos Avançados de `TensorFlow`*
```

```bash
01 ) Estruturação Completa do Ecossistema PyTorch
# Manipulação de torch.Tensor e aceleração em GPU (CUDA), mecânica do grafo dinâmico e diferenciação automática (torch.autograd), criação de arquiteturas modulares herdando de nn.Module, pipelines com Dataset e DataLoader, e escrita do Training/Validation Loop explícito (optimizer.zero_grad, loss.backward, optimizer.step).


02 ) Tópicos Avançados em TensorFlow / Keras
# Keras Functional API e Subclassing API para arquiteturas não-lineares (múltiplas entradas/saídas e conexões residuais), Callbacks customizados (ModelCheckpoint, TensorBoard, ReduceLROnPlateau) e compilação de grafos com @tf.function.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Novas Pastas de Ferramentas para o Ecossistema de IA*
```

```ad-quote
title:
| Nova Pasta Sugerida | Função no Ecossistema | Principais Tópicos para Documentar |
| :--- | :--- | :--- |
| **`Scikit-Learn/`** | Padronização de Machine Learning Clássico e pré-processamento tabular. | `Pipeline`, `ColumnTransformer`, `FunctionTransformer`, estimadores customizados (`BaseEstimator`) e integração com Pandas/Polars. |
| **`Hugging Face/`** | Padrão da indústria para uso de Transformers, LLMs e Datasets. | Bibliotecas `transformers` (`AutoModel`, `AutoTokenizer`), `datasets`, `accelerate` (treino distribuído), `peft` (LoRA) e `trl`. |
| **`MLOps & Serving/`** | Rastreamento de experimentos, empacotamento e deploy de modelos em produção. | MLflow, Weights & Biases (W&B), exportação e otimização de grafos (ONNX, TensorRT) e containerização para GPUs (Docker, Apptainer). |
```
````

---
