
---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify">Ambientes de Computação de Alto Desempenho (HPC) implementam uma arquitetura de armazenamento em múltiplas camadas para resolver o conflito fundamental entre segurança e velocidade de entrada/saída de dados (I/O). Esta arquitetura se manifesta através dos sistemas de arquivos /home e /scratch, cada um otimizado para propósitos específicos no fluxo de trabalho computacional.</p>
```

```ad-quote
title:
A dicotomia entre segurança dos dados e velocidade de acesso representa o trade-off central que a arquitetura de armazenamento em HPC busca resolver através de sistemas especializados.
```

```ad-quote
title:
<p align="justify">Link: <a href="https://en.wikipedia.org/wiki/High-performance_computing">High-performance Computing</a></p>
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - O Problema Fundamental: Gargalo de I/O

```ad-quote
title:
**Contexto Técnico:**
```

```ad-quote
title:

| Fator | Impacto no Desempenho |
| --- | --- |
| Processamento Paralelo | Centenas de núcleos de CPU/GPU exigem alimentação constante de dados |
| Volume de Dados | Conjuntos de dados na escala de GBs, TBs ou PBs |
| Ociosidade | Unidades de processamento ficam ociosas aguardando operações de I/O |
| Balanceamento | Arquitetura precisa equilibrar requisitos conflitantes de armazenamento |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Dicotomia Funcional dos Dados

```ad-quote
title:
<p align="justify">Classificação dos dados baseada em requisitos de armazenamento:</p>
```

```ad-quote
title:

| Categoria | Exemplos | Características | Requisito Primário |
| --- | --- | --- | --- |
| Dados de Persistência | Códigos-fonte, scripts, arquivos de configuração | Tamanho pequeno (KB/MB), valor intelectual | SEGURANÇA (backups, integridade) |
| Dados de Execução | Datasets de treinamento, checkpoints, resultados | Tamanho gigantesco (GBs/TBs/PBs), temporários | VELOCIDADE (taxa de transferência) |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Trade-off de Engenharia

```ad-quote
title:
<p align="justify">O desafio de prover uma solução única para requisitos opostos:</p>
```

```ad-quote
title:

| Sistema Otimizado | Características | Limitações |
| --- | --- | --- |
| Para SEGURANÇA | Snapshots, redundância, backups frequentes | Lentidão em escala, alto custo para petabytes |
| Para VELOCIDADE | Sistemas de arquivos paralelos, distribuição | Backups tradicionais inviáveis, performance comprometida |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Sistema de Arquivos /home

```ad-quote
title:
Repositório Permanente do Usuário
```

```ad-quote
title:
###### **Características Técnicas**
```

```ad-quote
title:
Otimizado para segurança e persistência dos dados vitais do usuário.
```

```ad-quote
title:

| Característica | Implementação | Impacto |
| --- | --- | --- |
| Backup | Rotinas regulares de backup | Possibilidade de recuperação em falhas |
| Quotas | Limites estritos de espaço | Viabiliza backups para milhares de usuários |
| Desempenho | Protocolos como NFS sobre storage RAID | Adequado para arquivos pequenos, inadequado para I/O paralelo |

```

```ad-quote
title:
###### **Caso de Uso Correto**
```

```ad-quote
title:
Armazenamento permanente de dados da Categoria 1: códigos-fonte, scripts, arquivos de configuração, documentos e quaisquer dados pequenos e vitais que não podem ser perdidos.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Sistema de Arquivos /scratch

```ad-quote
title:
Área de Trabalho Temporária de Alto Desempenho
```

```ad-quote
title:
###### **Características Técnicas**
```

```ad-quote
title:
Otimizado para velocidade e capacidade no processamento de dados massivos.
```

```ad-quote
title:

| Característica | Implementação | Impacto |
| --- | --- | --- |
| Desempenho | Sistemas de arquivos paralelos (Lustre, GPFS) | Taxas de I/O massivas (centenas de GB/s) |
| Capacidade | Armazenamento em petabytes | Permite conjuntos de dados massivos |
| Backup | Sem garantia de backup | Trade-off para velocidade máxima |
| Volatilidade | Políticas de expurgo automático | Remove arquivos antigos para liberar espaço |

```

```ad-quote
title:
###### **Caso de Uso Correto**
```

```ad-quote
title:
Armazenamento temporário de dados da Categoria 2: datasets de entrada, checkpoints de modelos, logs e arquivos de resultado durante a execução do job.
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Fluxo de Trabalho Compulsório

```ad-quote
title:
<p align="justify">Sequência obrigatória para uso eficiente do sistema:</p>
```

```ad-quote
title:

| Estágio | Local | Ação |
| --- | --- | --- |
| Preparação | /home | Desenvolvimento de código-fonte e scripts |
| Stage-In | /home → /scratch | Cópia de datasets massivos para área de trabalho |
| Execução | /scratch | Processamento com I/O intenso no sistema rápido |
| Stage-Out | /scratch → /home | Cópia de resultados finais para local permanente |
| Limpeza | /scratch | Remoção de dados intermediários e temporários |

```

```ad-quote
title:
<p align="justify">Este fluxo garante que o I/O intenso ocorra exclusivamente no sistema de arquivos rápido (/scratch), enquanto os dados vitais permanecem seguros no sistema com backup (/home).</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Conclusão Arquitetural

```ad-quote
title:
<p align="justify">Os diretórios /home e /scratch representam componentes especializados de uma arquitetura coerente projetada para resolver o trade-off fundamental entre segurança e velocidade em ambientes HPC.</p>
```

```ad-quote
title:

| Sistema | Otimização | Propósito |
| --- | --- | --- |
| /home | SEGURANÇA | Armazenamento permanente de código e dados vitais |
| /scratch | VELOCIDADE | Processamento temporário de dados massivos |

```

```ad-quote
title:
<p align="justify">O uso indevido desta arquitetura resulta em performance degradada para todo o cluster ou em risco catastrófico de perda de dados, reforçando a importância da adesão ao fluxo de trabalho estabelecido.</p>
```
````

---