
---
### 1. NVIDIA NV-Embed-v2

- **Nome**: NVIDIA NV-Embed-v2

- **Diferencial**: Líder absoluto em separação geométrica de classes e agrupamento textual.

- **Hardware recomendado**: Placa gráfica com 24 GB de memória para inferência ou 40 GB para ajuste fino  

- **Próprio para produção**: Apenas com restrições; o elevado peso computacional exige servidores de ponta caros, sendo pouco viável para esteiras simples de governança.


### 2. Qwen3-Embedding-8B

- **Nome**: Qwen3-Embedding-8B

- **Diferencial**: Domínio avançado de termos financeiros, técnicos e regulatórios com suporte multilíngue.

- **Hardware recomendado**: Placa gráfica com 16 GB a 24 GB de memória.

- **Próprio para produção**: Sim, desde que otimizado com quantização de 4 ou 8 bits para reduzir o consumo de memória na infraestrutura.


### 3. SFR-Embedding-2_R

- **Nome**: SFR-Embedding-2_R

- **Diferencial**: Excelente definição de margens entre categorias conceitualmente próximas.

- **Hardware recomendado**: Placa gráfica com 24 GB de memória dedicada.

- **Próprio para produção**: Apenas com restrições; entrega ótimas margens teóricas, mas demanda instâncias dedicadas de alto custo operacional.


### 4. stella_en_1.5B_v5

- **Nome**: stella_en_1.5B_v5

- **Diferencial**: Melhor custo-benefício computacional com desempenho próximo aos modelos de 8 bilhões.

- **Hardware recomendado**: Placa gráfica comum de 8 GB a 12 GB de memória.

- **Próprio para produção**: Sim, altamente recomendado; alia precisão elevada a uma baixa pegada de memória, facilitando a implantação em servidores normais.


### 5. Alibaba-NLP/gte-Qwen2-7B-instruct

- **Nome**: Alibaba-NLP/gte-Qwen2-7B-instruct

- **Diferencial**: Aceita comandos textuais para guiar o vetor ao contexto de governança e auditoria.

- **Hardware recomendado**: Placa gráfica com 16 GB a 24 GB de memória.

- **Próprio para produção**: Sim, com recurso a compressão; viável se for necessário guiar as representações semânticas com comandos prévios em lote.