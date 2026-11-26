
---

```ad-quote
title:

##### 1.1 ) - _Contexto histórico_
```

```ad-quote
title:  

As ferramentas de tradução automática sempre habitaram a imaginação humana. Exemplos clássicos, como os dispositivos UT (_Universal Translator_) presentes no seriado de televisão ficcional americano _Star Trek_, já expressavam o desejo de solucionar as barreiras criadas pela distância linguística.  
  
Nesse cenário, o processamento e a tradução de linguagem natural tornaram-se um dos primeiros campos explorados pelas técnicas que hoje formam a inteligência artificial. Ainda nos anos 1950, os compiladores surgiram como as primeiras ferramentas automatizadas visando realizar a tradução entre um pseudo-inglês e o código de máquina. Com o passar do tempo, ferramentas como o Google Tradutor em suas primeiras versões começaram a surgir a partir de processos determinísticos e estatísticos. Embora tenham viabilizado, pela primeira vez, uma tradução generalista minimamente satisfatória, esses sistemas realizavam substituições muito rígidas e não consideravam o contexto do parágrafo como um todo. Por consequência, mesmo que o sistema traduzisse corretamente a maioria das palavras isoladas, o texto final carecia da fluência e dos ajustes naturais que uma boa leitura nativa exige.  

Dessa forma, o estado da arte atual abandonou a estrutura mecânica originada nos compiladores e refinada pelo Google Tradutor original. A tradução automatizada migrou definitivamente para o universo das redes neurais, uma evolução que revolucionou por completo o campo da tradução autônoma. Entretanto, por mais que o cenário atual esteja bastante avançado e um dispositivo UT não seja mais ficção, mas sim parte do cotidiano das pessoas, obter uma tradução com qualidade acadêmica utilizando as técnicas mais avançadas de LLMs ainda exige o uso de estratégias específicas ao solicitar um texto. Neste artigo, vamos explorar quais técnicas podemos utilizar e como mitigar os vícios de linguagem presentes nesses modelos.
```

---

> [!done] **_New_**

---

```ad-quote
title:

##### 2.1 ) - _Calibração de Estilo_
```

```ad-quote
title:  

Antes de enviar o seu texto, você deve ensinar o tom exato que deseja. Escolha um parágrafo de um artigo bem escrito da sua área e envie junto com este comando. Essa ação ajusta o vocabulário da máquina para o padrão da conferência.
```

````ad-quote
title:  

```txt
Role: You are an expert academic editor specialized in Computer Science and Machine Learning.
Context: I am preparing a research paper about credit risk datasets for the BRACIS conference.
Task: Read the following reference paragraph extracted from an accepted paper. Analyze its tone, sentence length, and vocabulary. Do not translate anything yet. Just confirm you understood the academic style and summarize its main structural characteristics.

Reference Text: [Cole aqui um parágrafo de um artigo em inglês que você admira]
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Tradução com Restrições_
```

```ad-quote
title:  

Após a ferramenta confirmar que compreendeu o estilo de referência, você envia o trecho do seu manuscrito original. Este comando instrui a inteligência artificial a priorizar a fluidez e proíbe explicitamente os vícios comuns de linguagem.
```

````ad-quote
title:  

```txt
Task: Now, act as a native English academic translator. Translate the following Portuguese text into English following the exact style you just analyzed.

Rules:
1. Read the source text to fully understand the scientific meaning and methodology.
2. Forget the exact Portuguese sentence structure. Do not do a word-for-word translation.
3. Write directly in English using active voice as the default structure.
4. Strictly avoid AI cliche words such as: delve, seamlessly, moreover, foster, robust, comprehensive, paradigm, pivotal.
5. Prioritize absolute fluency and readability over literal translation. Maintain all technical terminology related to credit risk classification.

Source Text: [Cole aqui um ou dois parágrafos do seu artigo em português]
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.3 ) - _Refinamento Iterativo_
```

```ad-quote
title:  

A primeira resposta do modelo raramente é perfeita. Utilize este último comando para forçar a ferramenta a simplificar a estrutura e remover qualquer artificialidade restante na leitura.
```

````ad-quote
title:  

```txt
Task: Review the English translation you just generated. 

Rules:
1. Identify any sentence that is too long or complex and split it into two shorter sentences.
2. Remove unnecessary filler words and redundant transitional phrases.
3. Ensure the text flows naturally, exactly as a human researcher would speak during a presentation.
4. Output only the final polished text without any additional commentary.
```
````

```ad-quote
title:  

O ideal é executar esse ciclo alimentando o sistema com pequenas partes do texto de cada vez. Processar a introdução inteira de uma vez pode fazer o modelo perder o foco nas restrições.
```

---

> [!done] **_New_**

---

```ad-quote
title:

##### 3.1 ) - _Recomendação para o texto de referência_
```

```ad-quote
title:  

Essa matéria foi originalmente pensada para traduções de artigos científicos. Dessa forma, segue em anexo de uma recomendação para o texto de referência. Este parágrafo foi retirado da introdução do artigo _A Longitudinal Systematic Review of Credit Risk Assessment and Credit Default Predictors_
```

````ad-quote
title:

```
This study aims to reveal the predictors of individuals’ financial behavior associated with credit default for accurate and reliable credit risk assessment. Within the scope of credit use research, a systematic review of 108 studies was performed. Among the reviewed studies, a fair number have analyzed the determinants of default and delinquency. A remarkable number has examined the factors affecting outstanding and problematic debt levels, and some have investigated the financial behavior in terms of responsibility, debt repayment, and credit misuse. A wide range of socioeconomic, demographic, psychological, situational, and behavioral factors was explored, and their role in predicting the investigated outcome domain at various time-points was analyzed. The main analysis techniques and mix of predictors in papers also differed based on different time periods. While the synthesis of findings revealed some strong and consistent predictors for each outcome variable, mixed results were obtained for some factors. Additionally, a cluster of new practices that includes a wide range of alternative factors to improve prediction accuracies were uncovered. Study findings revealed a paradigm shift regarding the use of nontraditional data sources, especially big data, and novel techniques.

In recent years, socioeconomic developments and the spending patterns of individuals and populations have expanded the use of credit. Since individuals use credit to fulfill various needs, lending has started to produce more revenue for banks and other financial institutions. Credit can boost the economy and solve cash-related issues in the markets when used properly. Nevertheless, they inflict damages and disruption to the economy when used carelessly (Alma Çallı, 2019). The root causes of the credit crisis in 2008 are still unresolved. On the other side, the unpaid amount of credit worldwide has doubled in accordance with the lending rate of 2008, and more credit decisions are being made on an ongoing basis (van Thiel & van Raaij, 2019). Financial organizations should analyze credit applications based on scientific methods to prevent economic and social damages (Alma Çallı, 2019) and reduce credit risks.  Credit risk-related research is vital for guiding new researchers and practitioners who want to improve their credit risk management practices. For this reason, algorithms integrating various criteria and models have been developed to predict risk-based credit scores (Alma Çallı, 2019). The study of Durand (1941) is the most significant first phase in

developing credit scoring techniques. Risk factors were determined, and their weights were calculated empirically for the first time. Nonetheless, past payment behavior and behavioral variables that are closely related to default risk were not considered. Capon (1982) reported that the characteristics of applicants, which are directly and closely related to credibility, were ignored in credit scoring models at that time. However, after the 1980s, the focus was on searching for new predictor variables, as computers and statistical programs became accessible and powerful (Bumacov et al., 2017).  After the 1990s, the subject of default risk gained renewed interest as a consequence of the introduction of the Basel Capital Accords, which had a profound effect on credit risk management processes. With the introduction of Basel II in 2004, banks had to calculate their risks on the basis of the
```
````

---
