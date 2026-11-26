---
banner: "![[Pasted image 20260118174047.png]]"
---
---
#### **Intro )** - Roadmap de Domínio em PyTorch

```ad-quote
title: **Def**
**Summary:**
- PyTorch é o framework líder em pesquisa e produção de Deep Learning devido ao seu ecossistema dinâmico (grafo define-by-run), integração fluida com Python e controle granular sobre tensores, gradientes e execução em hardware acelerado.
```

> [!quote] **Link:** [PyTorch Official Documentation](https://pytorch.org/docs/stable/index.html)

> [!quote] **Link:** [Deep Learning with PyTorch: A 60 Minute Blitz](https://docs.pytorch.org/tutorials/beginner/deep_learning_60min_blitz.html)

> [!quote] **Link:** [Learn PyTorch for Deep Learning](https://www.learnpytorch.io/)

> [!quote] **Link:** [PyTorch GitHub Repository](https://github.com/pytorch/pytorch)

https://www.youtube.com/watch?v=IC0_FRiX-sw&list=PL_lsbAsL_o2CTlGHgMxNrKhzP97BaG9ZN

https://www.youtube.com/watch?v=V_xro1bcAuA&t=17s

---

>[!quote] **Vault:** [[PyT - Scratch]]

>[!quote] **Vault:** [[PyT - Programming Patterns]]

---

```ad-done
title:
#### **Phase 1 )** - Tensor Computations & Hardware Acceleration
```

---

```ad-quote
title: 
Esta fase aborda a estrutura basilar do framework: tensores n-dimensionais, compatibilidade com NumPy e despacho de cálculos para GPUs/aceleradores dedicados.
```

---
#### **01 ) -** Device Management & Hardware Acceleration (CUDA/MPS/CPU)

```ad-quote
title: **Def**
**Summary:**
- Identificação de hardware disponível via torch.cuda ou MPS, criação dinâmica do torch.device, alocação de tensores no dispositivo correto (.to(device)) e boas práticas de sincronização e medição de uso de VRAM.
```

> [!quote] **Vault:** [[PyT - Device & Hardware Acceleration]]

---

> [!done] _New_

---
#### **02 ) -** Tensor Creation, Data Types & Memory Sharing

```ad-quote
title: **Def**
**Summary:**
- Criação de tensores escalares, vetoriais e matriciais (zeros, ones, rand, arange), controle explícito de dtypes (float32, int64, bfloat16) e interoperabilidade com NumPy via torch.from_numpy compartilhando o mesmo ponteiro de memória subjacente.
```

> [!quote] **Vault:** [[PyT - Tensor Creation & Memory]]

---

> [!done] _New_

---
#### **03 ) -** Tensor Operations, Slicing & Dimension Reshaping

```ad-quote
title: **Def**
**Summary:**
- Domínio de transformações dimensionais cruciais para modelos profundos: indexação avançada, view, reshape, squeeze, unsqueeze, permute, flatten e operações matriciais com broadcasting e operador de multiplicação matricial (@).
```

> [!quote] **Vault:** [[PyT - Tensor Operations & Reshaping]]

---

```ad-done
title:
#### **Phase 2 )** - Autograd & The Functional Core
```

---

```ad-quote
title:
Compreensão profunda do motor de diferenciação automática, grafos computacionais construídos em tempo de execução e manipulação de derivadas.
```

---
#### **04 ) -** The Autograd Engine & Computational Graph

```ad-quote
title: **Def**
**Summary:**
- Como o PyTorch rastreia operações utilizando requires_grad=True, constrói grafos computacionais dinâmicos (Directed Acyclic Graphs), computa derivadas com .backward() e desliga rastreamento em inferência via torch.inference_mode() ou torch.no_grad().
```

> [!quote] **Vault:** [[PyT - Autograd & Computation Graph]]

---

> [!done] _New_

---
#### **05 ) -** Custom Operations & Gradient Manipulation

```ad-quote
title: **Def**
**Summary:**
- Extensão do motor criando funções personalizadas herdando de torch.autograd.Function com etapas manuais de forward e backward, além de técnicas de pós-processamento de gradiente como gradient clipping (clip_grad_norm_).
```

> [!quote] **Vault:** [[PyT - Custom Autograd & Gradient Clipping]]

---

```ad-done
title:
#### **Phase 3 )** - Data Pipelines & Ingestion
```

---

```ad-quote
title:
Construção de pipelines de dados performáticos e escaláveis capazes de alimentar as redes neurais sem criar gargalos de I/O ou CPU.
```

---
#### **06 ) -** Custom Datasets

```ad-quote
title: **Def**
**Summary:**
- Criação de classes customizadas herdando de torch.utils.data.Dataset através da implementação dos métodos __init__, __len__ e __getitem__, permitindo ingestão lazy de dados tabulares, imagens ou texto a partir de disco.
```

> [!quote] **Vault:** [[PyT - Custom Datasets]]

---

> [!done] _New_

---
#### **07 ) -** DataLoaders, Batching & Transforms

```ad-quote
title: **Def**
**Summary:**
- Utilização do DataLoader para minibatches automatizados, paralelização com num_workers, aceleração de transferência para GPU via pin_memory, agregação customizada de amostras com collate_fn e integração de pipelines de transformação (torchvision.transforms).
```

> [!quote] **Vault:** [[PyT - DataLoaders & Transformations]]

---

> [!done] _New_

---
#### **... ) -** Data Augmentation

```ad-quote
title: **Def**
**Summary:**
- ...
```

> [!quote] **Vault:** [[PyT - Data Augmentation]]

---

```ad-done
title:
#### **Phase 4 )** - Model Architecture & Modules (`torch.nn`)
```

---

```ad-quote
title:
Construção de blocos modulares e redes neurais escaláveis utilizando as abstrações de alto nível da biblioteca orientada a objetos.
```

---
#### **08 ) -** The `nn.Module` Base Architecture

```ad-quote
title: **Def**
**Summary:**
- Estrutura fundamental de componentes neurais: subclasse de nn.Module, instanciação de camadas no construtor, fluxo de tensores no forward(), composição em cadeia com nn.Sequential e registro automático de parâmetros e buffers da rede.
```

> [!quote] **Vault:** [[PyT - nn.Module Architecture]]

---

> [!done] _New_

---
#### **09 ) -** Core Layers, Normalization & Parameter Initialization

```ad-quote
title: **Def**
**Summary:**
- Implementação de camadas lineares (nn.Linear), convolucionais, de normalização (BatchNorm, LayerNorm), regularização (Dropout) e aplicação explícita de esquemas de inicialização estatística com o submódulo torch.nn.init.
```

> [!quote] **Vault:** [[PyT - Layers & Initialization]]

---

```ad-done
title:
#### **Phase 5 )** - The Training Lifecycle & Optimization
```

---

```ad-quote
title:
Montagem e execução do loop de treino canônico, cálculo de funções de perda e dinâmica de atualização dos parâmetros.
```

---
#### **10 ) -** Loss Functions & Numerical Stability

```ad-quote
title: **Def**
**Summary:**
- Exploração das funções de custo integradas (nn.CrossEntropyLoss, nn.BCEWithLogitsLoss, nn.MSELoss), compreendendo a importância da estabilidade numérica com logits em vez de probabilidades brutas pré-ativadas.
```

> [!quote] **Vault:** [[PyT - Loss Functions]]

---

> [!done] _New_

---
#### **11 ) -** Optimizers & Learning Rate Schedulers

```ad-quote
title: **Def**
**Summary:**
- Configuração de otimizadores via torch.optim (SGD, Adam, AdamW), gestão de weight decay, zeragem de gradientes (zero_grad(set_to_none=True)) e agendamento dinâmico de taxa de aprendizado com torch.optim.lr_scheduler.
```

> [!quote] **Vault:** [[PyT - Optimizers & LR Schedulers]]

---

> [!done] _New_

---
#### **12 ) -** The Standard Training and Validation Loop

```ad-quote
title: **Def**
**Summary:**
- Implementação limpa do ciclo completo: alternância entre model.train() e model.eval(), iteração por épocas, forward pass, retropropagação com backward(), atualização com optimizer.step() e agregação de métricas em validação.
```

> [!quote] **Vault:** [[PyT - Training & Validation Loops]]

---

```ad-done
title:
#### **Phase 6 )** - Persistence, Acceleration & Production
```

---

```ad-quote
title:
Boas práticas para exportação de modelos treinados, aceleração computacional e diagnóstico de gargalos.
```

---
#### **13 ) -** Saving, Loading & Checkpointing (`state_dict`)

```ad-quote
title: **Def**
**Summary:**
- Serialização segura de modelos utilizando torch.save e torch.load através do estado dos pesos (state_dict), salvamento de checkpoints completos com otimizador e época para retomada de treino, e introdução a formatos modernos (safetensors).
```

> [!quote] **Vault:** [[PyT - Saving & Checkpointing]]

---

> [!done] _New_

---
#### **14 ) -** Performance Acceleration, Mixed Precision & Profiling

```ad-quote
title: **Def**
**Summary:**
- Técnicas avançadas de performance: treinamento com Precisão Mista Automática (torch.amp e GradScaler), compilação de grafos com torch.compile (PyTorch 2.0+) e identificação de gargalos de memória e computação via torch.profiler.
```

> [!quote] **Vault:** [[PyT - AMP, Torch Compile & Profiling]]

---

