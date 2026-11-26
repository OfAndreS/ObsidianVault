
---

```ad-done
title:

#### **Conceitos Teóricos da Computação**

```

````ad-quote
title:
```ad-quote
title:
###### **Modelagem Relacional e Normalização**
```

>[!missing]

```ad-quote
title:
Chaves primárias, chaves estrangeiras e integridade referencial. Entenda esquemas relacionais para identificar entidades e atributos em tabelas heterogêneas.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Teoria dos Grafos e Estruturas em Rede**
```

>[!missing]

```ad-quote
title:
Grafos direcionados e rotulados com nós e arestas. Compreenda caminhos, conectividade e propriedades de redes para modelagem de conhecimento.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Lógica Matemática, Lógicas de Descrição e Lógica Deôntica**
```

>[!missing]

```ad-quote
title:
Revise os fundamentos de lógica proposicional e de predicados, as lógicas de descrição (que sustentam as linguagens ontológicas) e a lógica deôntica (obrigação, permissão e proibição), base conceitual para políticas que definem o que o cientista de dados *pode*, *deve* ou *não pode* fazer com uma feature.
```
````

```ad-done
title:

#### **Padrões e Conceitos da Web Semântica**

```

````ad-quote
title:
```ad-quote
title:
###### **Modelo de Dados RDF, Triplas e JSON-LD**
```

>[!missing]

```ad-quote
title:
Compreenda a estrutura atômica formada por sujeito, predicado e objeto, a função de URIs na identificação unívoca de dados e a especificação **W3C JSON-LD** para serializar grafos semânticos em JSON padrão (ideal para gerar o arquivo versionável de política de cada projeto).
```
````

````ad-quote
title:
```ad-quote
title:
###### **Modelagem de Ontologias: Guia *Ontology 101*, RDFS e OWL**
```

>[!missing]

```ad-quote
title:
Estude o guia prático *Ontology Development 101* (Noy & McGuinness — Stanford) junto às linguagens RDFS e OWL. Aprenda a estruturar hierarquias de classes, propriedades de objetos e de tipos de dados, herança, restrições lógicas e raciocínio ontológico sem erros lógicos antes de partir para ferramentas como o Protégé.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Validação Estrutural com W3C SHACL (*Shapes Constraint Language*)**
```

>[!missing]

```ad-quote
title:
Aprenda a criar regras de validação estrutural sobre grafos RDF para garantir que uma ficha jurídica e os metadados da ontologia estejam completos e consistentes antes da exportação.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Linguagem de Consulta SPARQL**
```

>[!missing]

```ad-quote
title:
Aprenda a sintaxe de consultas estruturadas para recuperação de grafos. Pratique filtros, padrões de triplas e agregações analíticas.
```
````

```ad-done
title:

#### **Ontologias e Vocabulários de Domínio (Estrutura do Repositório)**

```

````ad-quote
title:
```ad-quote
title:
###### **W3C Data Privacy Vocabulary (DPV) — `dpv`, `dpv-risk` e `dpv-ai`**
```

>[!missing]

```ad-quote
title:
Referência principal do projeto para estruturar classes, tags e o esboço das entidades e propriedades das 8 colunas sem reinventar padrões de mercado. Define classes em OWL/RDF para bases legais, categorias de dados, riscos, impactos e medidas de mitigação.
```
````

````ad-quote
title:
```ad-quote
title:
###### **W3C PROV-O (*Provenance Ontology*)**
```

>[!missing]

```ad-quote
title:
Fundamenta diretamente a coluna `Origem Sugerida`. Ensina a modelar a linhagem e proveniência do dado, diferenciando fontes primárias (titular), secundárias (birôs/Open Finance) e dados inferidos.
```
````

```ad-done
title:

#### **Camada 1 — Natureza do Risco, Viés e Estabilidade da Feature**

```

````ad-quote
title:
```ad-quote
title:
###### **Justiça Algorítmica e Variáveis Proxy (*Fairness and Machine Learning*, Cap. 1–3)**
```

>[!missing]

```ad-quote
title:
Obra de Barocas, Hardt & Narayanan que explica a diferença matemática entre tratamento desigual e impacto desproporcional. Fundamenta a definição das tags estruturadas das colunas `Atuação como proxie` e `Possíveis Viéses`.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Taxonomia de Viés em IA (NIST Special Publication 1270)**
```

>[!missing]

```ad-quote
title:
Guia *Identifying and Managing Bias in AI*, que fornece uma taxonomia clara para classificar origens de viés (sistêmico, estatístico e humano) em categorias padronizadas no banco de dados para a Camada 1.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Estabilidade de Dados (*Data Drift*, PSI e ISO/IEC 5259)**
```

>[!missing]

```ad-quote
title:
Delimitam a dimensão de estabilidade e qualidade de dados da coluna `Demanda de Governança`. Ensinam a definir regras de monitoramento contínuo entre dados declarados e dados reais.
```
````

```ad-done
title:

#### **Camada 2 — Dimensão de Impacto, Regulação e Explicabilidade**

```

````ad-quote
title:
```ad-quote
title:
###### **Base Jurídica Nacional (LGPD Arts. 5º, 6º, 7º e 20 + Lei 14.181/2021)**
```

>[!missing]

```ad-quote
title:
Base normativa essencial (incluindo a Lei do Superendividamento) para tipificar as tags estruturadas de `Justificativa Legal` e `Implicações Legais` no contexto brasileiro.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Frameworks de Risco e Regulação de IA (NIST AI RMF 1.0 e EU AI Act Arts. 9, 10 e 13)**
```

>[!missing]

```ad-quote
title:
Ensinam a vincular a severidade do risco à finalidade de uso do modelo (ex: concessão de crédito vs. marketing), estruturando a matriz de impacto da Camada 2.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Interpretabilidade em ML (*Towards A Rigorous Science of Interpretable ML*)**
```

>[!missing]

```ad-quote
title:
Artigo de Doshi-Velez & Kim que fundamenta a coluna `Explicabilidade Necessária`. Ajuda a traduzir níveis de exigência jurídica ("Alta", "Média", "Baixa") em restrições técnicas de algoritmos (ex: exigir SHAP ou modelos lineares).
```
````

```ad-done
title:

#### **Paradigmas de Integração, Mapeamento e Validação de Políticas**

```

````ad-quote
title:
```ad-quote
title:
###### **Integração de Dados Baseada em Ontologias**
```

>[!missing]

```ad-quote
title:
Estude arquiteturas que utilizam ontologias como esquemas globais mediadores. Compreenda a separação entre camadas de dados locais e a visão semântica integrada.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Padrões Declarativos RML, R2RML e YARRRML**
```

>[!missing]

```ad-quote
title:
Aprenda como regras declarativas conectam colunas de tabelas a propriedades ontológicas e estude o formato legível YARRRML para simplificar a criação de mapeamentos.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Políticas Declarativas com Open Policy Agent (OPA) e Linguagem Rego**
```

>[!missing]

```ad-quote
title:
Ponte para o back-end: ensina a criar políticas declarativas desacopladas do código da API que cruzam as tags da Camada 1 e da Camada 2, validam o arquivo exportável (JSON/JSON-LD) de um projeto e retornam alertas ou bloqueios automatizados.
```
````

```ad-done
title:

#### **Ferramentas e Tecnologias de Software**

```

````ad-quote
title:
```ad-quote
title:
###### **Linguagem Python e Biblioteca Pandas**
```

>[!done]

```ad-quote
title:
Domine a manipulação e limpeza de arquivos de dados tabulares. Extraia tipos estatísticos e distribuições numéricas das colunas analisadas.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Biblioteca RDFLib**
```

>[!missing]

```ad-quote
title:
Pratique a instanciação de grafos RDF em memória com código Python. Carregue arquivos locais, serialize triplas (incluindo JSON-LD) e execute consultas SPARQL programaticamente.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Motor de Mapeamento Morph-KGC**
```

>[!missing]

```ad-quote
title:
Utilize este pacote Python para converter tabelas em grafos semânticos. Execute regras de mapeamento declarativo com alto desempenho computacional.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Software Stanford Protégé**
```

>[!missing]

```ad-quote
title:
Instale este software gráfico aberto em seu computador. Inspecione e modele hierarquias de classes, propriedades e axiomas (como W3C DPV, PROV-O e FIBO) antes de escrever scripts.
```
````
