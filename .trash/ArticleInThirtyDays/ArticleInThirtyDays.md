
---
### **Fase 01: Catalogação dos Conjuntos de Dados**

_Output esperado:_ PreDatasets.xlsx

Esta etapa inicial consiste em uma busca sistemática em repositórios públicos e plataformas de dados abertos para identificar e catalogar os principais conjuntos de dados de risco de crédito disponíveis na literatura e no mercado. O objetivo é estabelecer um _corpus_ empírico representativo e abrangente para alicerçar a pesquisa.

### **Fase 02: Extração e Limpeza de Metadados**

_Output esperado:_ PosDatasetsClean.xlsx

Após a catalogação, realiza-se a aquisição dos arquivos identificados. O foco primário desta fase não é o conteúdo analítico das observações, mas a extração estruturada dos metadados. São isoladas e consolidadas informações essenciais, como a nomenclatura original das variáveis e a dimensão tabular de cada base, gerando um dicionário de dados bruto unificado.

### **Fase 03: Pipeline de Classificação com NLP**

A etapa central do experimento aplica técnicas avançadas de Processamento de Linguagem Natural, operando paralelamente em um ambiente de computação de alta performance.

### **3.1) Classificação Macro**

_Output esperado:_ MacroTaxonomyClassification.csv

Esta fase mapeia as variáveis brutas para dimensões de alto nível, fundamentando-se rigorosamente na taxonomia definida pelo artigo de referência. O processo utiliza o modelo de linguagem _Gemma4-27b-it_ sob uma arquitetura de dupla passagem, que combina a inferência primária de mapeamento com uma auditoria sintética de regras estritas. Posteriormente, os resultados preditos são submetidos a uma triagem humana especializada, implementando um ciclo _Human-in-the-Loop_ para correção ativa de falhas e garantia de alta precisão conceitual.

### **3.2) Classificação Micro**

_Output esperado:_ MicroTaxonomyClassification.csv

Com as variáveis previamente alocadas em suas respectivas macro categorias, esta etapa final executa a resolução de entidades e a normalização semântica. O algoritmo atua de forma evolutiva para agrupar termos redundantes e variações nominais, unificando-os sob um conceito canônico padronizado e agnóstico a janelas de tempo. Essa abordagem reduz drasticamente a cardinalidade informacional, entregando um dicionário de variáveis limpo, livre de ruídos e ideal para a modelagem preditiva subsequente.