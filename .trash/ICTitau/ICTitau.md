
---

https://www.periodicos.capes.gov.br/index.php/acesso-cafe.html

---
No mundo moderno existe várias travas e contrapesos para a concessão de crédito nos bancos. Leis e regulamentações estão a todo vapor em todo o mundo visando criar um ambiente onde a discriminação não é um fator decisivo para o acesso monetário. Dessa forma, estou criando um processo de análise das variáveis mais utilizadas no meio financeiro e acadêmico aspirando elaborar um compilado das melhores técnicas de preprocessamento e normalização do ponto de vista computacional, tendo em vista que sou o membro oriundo da ciência da computação que integra a equipe de desenvolvimento. 


---
**Busca Focada em Variáveis:** 

"credit scoring" AND ("input variables" OR "features" OR "predictors") AND ("review" OR "survey" OR "mapping")

**Busca Focada em Machine Learning:** 

"machine learning" AND "credit risk" AND "feature selection" AND "systematic review"

---

## Sugestão de Termos de Busca para 2026

Para encontrar o que há de mais moderno e que complemente este PDF, tente estas _strings_ no Google Scholar ou Elicit:

- `"credit scoring" AND "large language models" AND "feature selection"`
    
- `"alternative data" AND "credit risk" AND "deep learning" AND "2022..2026"`
    
- `"algorithmic bias" AND "credit scoring" AND "mitigation techniques"`

---
### **1. Revisões Sistemáticas de Alto Impacto (2024-2025)**

- **Performance, Fairness, and Explainability in AI-Based Credit Scoring: A Systematic Literature Review (2025)**
    
    - _O que ele adiciona_: Este artigo revisa 43 estudos e é crucial para o seu trabalho porque ele conecta a "Justiça" ($Fairness$) com a "Explicabilidade". Ele analisa como as instituições de crédito navegam entre o desempenho do modelo e a transparência exigida por regulações.
        
    - _Destaque_: Aponta que não existe um modelo de justiça universal, variando conforme a jurisdição e o contexto do dado.
        
- **The 40-year journey for fairness in credit: A systematic review (2024/2025)**
    
    - _O que ele adiciona_: Oferece uma perspectiva histórica valiosa. Ele mapeia como saímos de análises centradas apenas em dados para tendências de otimização de algoritmos lideradas pela ciência da computação.
        
    - _Destaque_: É excelente para fundamentar a parte de _Viés Sistêmico_ do seu relatório, rastreando as fontes de discriminação ao longo de quatro décadas de concessão de crédito.
        
- **Towards Fair AI: Mitigating Bias in Credit Decisions (2025)**
    
    - _O que ele adiciona_: Como vimos, este é o seu pilar central. Ele revisou 414 artigos para identificar que raça e gênero são os atributos sensíveis mais estudados, sendo a "Paridade Estatística" a métrica de justiça mais comum.
        

### **2. Abordagens Técnicas Específicas para sua Matriz**

- **Bias Detection and Mitigation in Credit Scoring Using Deep Learning (2024)**
    
    - _O que ele adiciona_: Se o seu projeto na UFRN envolver modelos mais complexos (como Redes Neurais), este artigo é a fonte ideal. Ele propõe um framework que integra _adversarial debiasing_ e _re-weighting_ de amostras.
        
    - _Destaque_: Ele detalha especificamente técnicas de _pré-processamento_ para transformar o dataset antes do treino, o que se encaixa na sua caixa de "Soluções Gerais".
        
- **An Analytical Framework for Bias Mitigation through Fairness-Constrained Neural Optimization (2025)**
    
    - _O que ele adiciona_: Foca intensamente em _Constraint Optimization_ (Otimização Restrita). É a fonte perfeita para a sua "Técnica de Solução Individual", mostrando como integrar restrições de paridade demográfica diretamente na função de perda ($loss function$) do modelo.
        

### **3. Estudos de Caso e Regulação**

- **AI-powered credit risk assessment and algorithmic fairness in digital lending: A comprehensive analysis (2025)**
    
    - _O que ele adiciona_: Analisa o cenário do empréstimo digital nos EUA. Ele explora três critérios primários de justiça: _Independência_, _Separação_ e _Calibragem_.
        
    - _Destaque_: Ajuda a definir os critérios de "O viés permanece na variável?" do seu fluxograma.

---
 **Consultas para Revisões Sistemáticas (Para a Base Teórica)**

Essas buscas visam encontrar artigos que, assim como o "Towards Fair AI", já fizeram o trabalho de filtrar centenas de outros estudos.

- `"systematic literature review" AND "bias mitigation" AND "credit scoring"`
    
- `"survey" AND "fairness in machine learning" AND "financial services"`
    
- `"state-of-the-art" AND "algorithmic fairness" AND "credit risk assessment"`
    
- `"mapping study" AND "bias identification" AND "credit models"`
    

 **Consultas Focadas na Natureza do Dado e Técnicas (Para a sua Matriz)**

Use estas consultas para encontrar a correlação exata entre o _tipo de variável_ (nominal, contínua, etc.) e o _método de tratamento_.

- `"bias mitigation techniques" AND "quantitative vs qualitative data" AND "credit"`
    
- `"impact of data types" ON "fairness metrics" IN "credit scoring"`
    
- `"pre-processing vs in-processing bias mitigation" AND "credit risk"`
    
- `"handling nominal variables" IN "fairness-aware machine learning"`
    
- `"feature engineering" AND "bias reduction" AND "credit datasets"`

---

## Comparativo das Definições de Equidade

|**Conceito**|**Tipo**|**Foco Principal**|**Aplicação Ideal**|
|---|---|---|---|
|_Statistical Parity_|Métrica|Igualdade de resultados entre grupos.|Seleção inicial de candidatos.|
|_Equalized Odds_|Métrica|Igualdade de taxas de acerto e erro (TP e FP).|Quando o custo do erro é alto para ambos os lados.|
|_Equal Opportunity_|Métrica|Igualdade na taxa de verdadeiros positivos.|Concessão de benefícios ou crédito.|
|_Awareness_|Abordagem|Tratar indivíduos similares de forma similar.|Casos que exigem métricas de distância individual.|
|_Unawareness_|Abordagem|Ignorar atributos sensíveis explicitamente.|Baseline inicial (geralmente insuficiente).|

---

https://www.youtube.com/watch?v=sMc6_A3Sk78&list=WL&index=5

https://www.youtube.com/watch?v=p5yY2MyTJXA

---

Quando digo que as métricas são matematicamente incompatíveis, refiro-me ao que na literatura chamamos de _Teoremas de Impossibilidade da Equidade_ (como os demonstrados por Kleinberg, Chouldechova e outros).

---

- **"21 Fairness Definitions and Their Politics" (Arvind Narayanan)**: Este é, talvez, o material mais influente para entender por que existem tantos conceitos de justiça. Narayanan explica de forma magistral como diferentes definições matemáticas (como _Paridade Demográfica_ vs. _Igualdade de Oportunidades_) refletem diferentes visões de mundo. É essencial para a fundamentação teórica do seu relatório.
    
- **"Fairness and Machine Learning" (Barocas, Hardt & Narayanan)**: O capítulo 2 deste livro é inteiramente dedicado às métricas. Ele detalha os conflitos matemáticos entre elas e é ideal para quem, como você, possui uma base sólida em Ciência da Computação.
    
- **"Fairness in Credit Scoring: Assessment, Implementation and Profit Implications" (Kozodoi et al., 2022)**: Este artigo é obrigatório para o seu tema específico. Ele analisa como cada métrica afeta o _lucro_ e a _equidade_ em bases de dados reais de crédito, fornecendo o vocabulário de negócios necessário para a sua discussão.
    
- **"Fairness Definitions Explained" (Verma & Rubin, 2018)**: Um excelente material de consulta rápida que agrupa as métricas em categorias (equidade de grupo, individual e causal), facilitando a organização das suas notas no _Obsidian_.
