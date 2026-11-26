
---

Populações jovens ou habitantes de países em desenvolvimento costumam carecer de um histórico financeiro formal, o que limita a capacidade dos modelos de avaliação clássicos de estimar uma pontuação de risco precisa (ZP 14, 13). Para superar essa limitação, diversas instituições financeiras passaram a integrar fontes de dados alternativas em suas bases de treinamento, buscando mapear o comportamento rotineiro e a cultura de crédito local de cada indivíduo (ZP 12). É justamente a combinação dessas novas métricas com o avanço tecnológico do Big Data que tem provocado uma profunda transformação na área de avaliação de risco e previsão de inadimplência (Hurley and Adebayo 2017).

O uso irrestrito de dados alternativos, contudo, apresenta um desafio técnico. Essas informações podem atuar como variáveis proxy, revelando traços sensíveis do consumidor de forma indireta (ZP 15). Esse risco exige atenção redobrada diante do avanço das leis de proteção de dados, a exemplo da LGPD e da GDPR. A legislação atual impõe limites e trata cada tipo de informação de maneira diferente. Uma variável macroeconômica, por exemplo, possui regras de uso mais flexíveis. Já uma variável de saúde sofre restrições severas e o seu processamento inadequado configura violação de privacidade. Portanto, inserir uma variável no algoritmo sem perceber o seu peso discriminatório pode comprometer a validade jurídica e técnica de todo o modelo de predição.

Para lidar com esse risco, este artigo propõe a construção de uma ferramenta de triagem para atuar como um filtro preventivo de governança. O objetivo do sistema é funcionar como um classificador automatizado, capaz de identificar a natureza de uma nova variável antes que ela seja integrada aos modelos de crédito. O estudo utiliza a taxonomia de (Çallı e Coşkun 2021) para estruturar essa classificação inicial. O modelo original dos autores divide as variáveis de risco financeiro em dez categorias: Socioeconomic, Demographic, Values, Attitudes and Behavioral, Institutional and Financial, Personality, Situational, Educational, Macroeconomic, Health-Related e Alternative. O mapeamento prévio nesses grupos permite separar de forma escalável as informações de uso livre daquelas que exigem amparo legal. Essa separação impede que atributos protegidos afetem o modelo de previsão de forma acidental.

Apesar de sua utilidade, a taxonomia original cobre apenas o aspecto teórico do problema. A implementação em bancos de dados reais exige também o tratamento de metadados. O artigo introduz uma décima primeira categoria chamada Operational para suprir essa exigência. Essa nova classe organiza apenas os atributos do sistema, como as chaves de identificação e os registros de tempo. Essa adição fornece a dimensão estrutural necessária para garantir a auditoria automática do fluxo de dados.

Superar a dimensão teórica e construir essa arquitetura automatizada esbarra em obstáculos técnicos e regulatórios. Para que o filtro consiga classificar novas informações de forma automática, ele precisa ser treinado com exemplos reais. O desafio inicial, portanto, é a escassez de bases de dados rotuladas. Como os bancos e as instituições financeiras mantêm os dicionários de dados isolados para cumprir exigências regulatórias, as variáveis alternativas disponíveis na literatura apresentam nomenclaturas heterogêneas e descrições muito diversas \cite{mwesigwa2026credit}. Além desse desafio com os dados de treinamento, a crescente complexidade das aplicações de Inteligência Artificial levanta preocupações críticas sobre a governança no setor financeiro \cite{kurshan2021governance}. A literatura alerta sobre os riscos dos modelos opacos. Por consequência, a adoção de algoritmos com explicabilidade intrínseca torna-se indispensável para garantir a auditoria, a supervisão humana e o cumprimento das novas diretrizes regulatórias \cite{anomah2026bridging}.

Para solucionar essas duas barreiras, a escassez de dados e a necessidade de transparência, a metodologia deste trabalho propõe um fluxo em três etapas. Primeiro, o projeto resolve a falta de dados gerando um conjunto sintético de treinamento com o modelo de linguagem Gemma4 31B \cite{team2024gemma}. O processo fundamenta a amostragem diretamente nos conceitos da literatura por meio da técnica de few-shot prompting \cite{brown2020language}. Segundo, o modelo BAAI/bge-large-en-v1.5 \cite{xiao2024cpack} vetoriza essas entradas textuais para capturar o contexto semântico exigido. Esse modelo é calibrado utilizando uma função Batch Hard Triplet Loss \cite{hermans2017defense} para maximizar a separação entre as categorias da taxonomia e melhorar a coesão interna de cada classe. Por fim, a arquitetura utiliza três algoritmos clássicos para realizar a classificação final das variáveis: Regressão Logística, Random Forest e Support Vector Machine \cite{fabian2011scikit}. A escolha por esses modelos em vez de redes complexas oferece a explicabilidade intrínseca e a rastreabilidade matemática estritamente necessárias para uma implantação em conformidade com as legislações de proteção de dados vigentes.

---
---

Young populations and inhabitants of developing countries often lack a formal financial history. This absence limits the ability of classical evaluation models to estimate accurate risk scores (ZP 14, 13). To overcome this limitation, many financial institutions now integrate alternative data sources into their training datasets. This approach aims to map the routine behavior and local credit culture of each individual (ZP 12). The combination of these new metrics with the technological advancements of Big Data has triggered a profound transformation in the field of risk assessment and default prediction (Hurley and Adebayo 2017).

The unrestricted use of alternative data, however, presents a technical challenge. This information can act as proxy variables, indirectly revealing sensitive consumer traits (ZP 15). This risk demands heightened attention given the advancement of data protection laws, such as the LGPD and the GDPR. Current legislation imposes limits and treats each type of information differently. A macroeconomic variable, for instance, operates under flexible usage rules. Conversely, a health-related variable faces severe restrictions, and processing it improperly constitutes a privacy violation. Therefore, introducing a variable into the algorithm without identifying its discriminatory weight can compromise the legal and technical validity of the entire prediction model.

To address this risk, this study proposes building a screening tool to act as a preventive governance filter. The system functions as an automated classifier, designed to identify the nature of a new variable before integrating it into credit models. The methodology uses the taxonomy of (Çallı and Coşkun 2021) to structure this initial classification. The original model divides financial risk variables into ten categories: Socioeconomic, Demographic, Values, Attitudes and Behavioral, Institutional and Financial, Personality, Situational, Educational, Macroeconomic, Health-Related, and Alternative. Mapping variables into these groups beforehand allows for the scalable separation of freely usable information from data requiring legal justification. This separation prevents protected attributes from accidentally affecting the prediction model.

Despite its utility, the original taxonomy covers only the theoretical aspect of the problem. Real-world database implementation also requires metadata processing. The study introduces an eleventh category called Operational to meet this requirement. This new class exclusively organizes system attributes, such as identification keys and timestamps. This addition provides the structural dimension necessary to ensure the automatic auditing of the data flow.

Moving beyond the theoretical dimension to build this automated architecture introduces technical and regulatory obstacles. For the filter to classify new information automatically, the training process requires real examples. The initial challenge, therefore, is the scarcity of labeled datasets. Because banks and financial institutions keep data dictionaries isolated to comply with regulatory requirements, the alternative variables available in the literature present heterogeneous nomenclatures and highly diverse descriptions \cite{mwesigwa2026credit}. Beyond this training data challenge, the growing complexity of Artificial Intelligence applications raises critical concerns regarding governance in the financial sector \cite{kurshan2021governance}. The literature warns against the risks of opaque models. Consequently, adopting algorithms with intrinsic explainability becomes indispensable to ensure auditing capabilities, human oversight, and compliance with new regulatory guidelines \cite{anomah2026bridging}.

To resolve the barriers of data scarcity and the need for transparency, the methodology of this work proposes a three-stage workflow. First, the project addresses the lack of data by generating a synthetic training set using the Gemma4 31B language model \cite{team2024gemma}. The process grounds the sampling directly in literature concepts through the few-shot prompting technique \cite{brown2020language}. Second, the BAAI/bge-large-en-v1.5 model \cite{xiao2024cpack} vectorizes these textual inputs to capture the required semantic context. A Batch Hard Triplet Loss function \cite{hermans2017defense} calibrates this model to maximize the separation between taxonomy categories and improve the internal cohesion of each class. Finally, the architecture employs three classical algorithms to perform the final classification of the variables: Logistic Regression, Random Forest, and Support Vector Machine \cite{fabian2011scikit}. Selecting these models over complex neural networks offers the intrinsic explainability and mathematical traceability strictly necessary for an implementation that complies with current data protection legislation.

---
---

  Ferramenta de classificação para dados sensíveis não são novidades no mercado, diversas soluções já existem e integram o desenvolvimento de . Entretanto, a grande maioria dessas soluções focam na identificação após o dedo sensível ser cole

---
---
- Essa ferramenta reside no momento da modelagem do modelo anterior a coleta do dado
  
- Por mais que existam soluções tais como o Microsoft Presidio, a literatura carece de um modelo de prevenção -> Após a coleta do dado a LGPD exige que as amostras sejam guardadas por um período expressivo de tempo.

---
---

ZP 12 - Mwesigwa et al. 2026
- Os provedores de crédito estão aprimorando seus modelos preditivos. As instituições financeiras fazem isso ao incorporar fontes de dados alternativas em seus conjuntos de treinamento. Essas novas variáveis focam em capturar padrões de comportamento e a cultura de crédito local. O objetivo final é treinar algoritmos de pontuação muito mais precisos e adaptados à realidade do consumidor.

ZP - 13 - Björkegren & Grissen
- Bancos e instituições financeiras tradicionais não conseguem prover serviços de crédito eficientes para a população de países em desenvolvimento devido à falta de histórico bancário formal dos indivíduos. Entretanto, com a popularização do telefone celular e a coleta automática de dados, agora é possível inferir o perfil de um bom pagador sem a necessidade de registros financeiros prévios.

ZP 11 - Tounsi et al .
- As instituições financeiras constroem os modelos clássicos de pontuação de crédito usando informações de sistemas transacionais tradicionais. Esses sistemas incluem as plataformas de OLTP, que processam transações online de forma imediata. A lista também engloba sistemas de Core Banking, softwares de ERP para planejar os recursos da empresa, aplicativos de CRM para gerenciar o relacionamento com o cliente e os registros das agências de proteção ao crédito. Os dados básicos dos consumidores processados nessas ferramentas são bem convencionais. Eles incluem informações simples como data de nascimento, gênero, renda e situação atual de emprego.

ZP 14 - Gou et al .
- O histórico de crédito tradicional não oferece informações suficientes para avaliar o perfil de todos os consumidores. Essa falta de dados prejudica principalmente a avaliação dos clientes mais jovens, que não tiveram tempo de construir um histórico financeiro e costumam representar um risco maior para os bancos. A solução para contornar essa limitação e tornar a pontuação mais precisa é incorporar fontes de dados alternativas utilizando a tecnologia do Big Data.

ZP 15 - Schwarcz and Prince
- Este artigo defende que a Inteligência Artificial e o Big Data mudam as regras do jogo quando o assunto é o risco dessa discriminação não intencional. Os sistemas inteligentes alimentados por grandes volumes de dados possuem uma estrutura que busca a discriminação por procuração de forma automática. Isso ocorre sempre que o sistema é impedido de acessar os dados reais sobre quem pertence a um grupo protegido pela lei. Apenas proibir o acesso do algoritmo aos dados substitutos mais óbvios não resolve o problema. Essa proibição faz apenas com que a inteligência artificial procure e encontre outros dados substitutos menos óbvios para contornar a regra.



---
---
## Ferramentas de Anonimização e Descoberta de Dados

**Microsoft Presidio e Google Cloud DLP**

Essas tecnologias rastreiam textos e bancos de dados em busca de informações pessoais identificáveis. O foco delas é encontrar nomes, números de documentos e endereços para mascarar esses registros. A principal diferença para a sua proposta é o momento de atuação e o tipo de dado analisado. Esses sistemas leem o registro físico e real do cliente após a coleta. A sua arquitetura analisa apenas a descrição da variável no dicionário de dados antes de a coleta acontecer.

  

**Amazon Macie**

Esse é um serviço de segurança que utiliza aprendizado de máquina para descobrir e classificar dados sensíveis em ambientes de nuvem. Ele funciona varrendo os arquivos armazenados para alertar sobre vazamentos ou falhas de segurança. A comparação segue a mesma lógica anterior. O sistema da Amazon foca na proteção de arquivos que já existem no armazenamento. O seu classificador atua na governança preventiva antes de o dado chegar ao banco de dados.

  

## Ferramentas de Governança de Inteligência Artificial

**IBM AI Fairness 360**

Esse é um conjunto de ferramentas focado na detecção e na correção de viés algorítmico. Os cientistas de dados utilizam os códigos dessa biblioteca para testar se as predições finais do modelo estão prejudicando grupos protegidos. A sua ferramenta se destaca ao atuar na raiz do problema de forma preventiva. A solução da IBM analisa o peso estatístico do dado durante ou após o treinamento matemático. A sua proposta bloqueia a entrada de variáveis proxy na etapa de concepção das regras de negócios.

  

**Fairlearn**

Essa é uma biblioteca de código aberto também voltada para a avaliação de justiça em sistemas de inteligência artificial. Ela fornece métricas para o desenvolvedor entender como as previsões afetam populações diferentes. O contraste com o seu artigo é o alvo da análise. Essa biblioteca avalia as métricas de saída do algoritmo. A sua arquitetura garante a segurança estrutural das variáveis de entrada por meio de modelos clássicos e transparentes.

  

## Plataformas de Catálogo e Metadados

**Collibra Data Governance e Informatica Enterprise Data Catalog**

Essas plataformas empresariais organizam o fluxo de informações em grandes companhias. Elas automatizam a descoberta de dados e aplicam rótulos de conformidade para adequação a leis de privacidade. O grande contraste metodológico reside na estrutura técnica de classificação. Esses catálogos comerciais costumam utilizar dicionários estáticos ou expressões regulares simples. O seu projeto aplica uma arquitetura avançada de vetorização semântica para compreender o contexto prático de categorias complexas, como atitudes e comportamentos sociais.

  

Você gostaria de utilizar alguma dessas categorias específicas para começarmos a redigir o primeiro parágrafo da sua nova seção de trabalhos relacionados?

---
---
Related Work

O mercado atual de tecnologia possui soluções consolidadas para a proteção de privacidade. Ferramentas como o Microsoft Presidio, o Google Cloud DLP e o Amazon Macie são amplamente utilizadas na indústria. O objetivo central desses sistemas é localizar informações de identificação pessoal e aplicar rotinas de anonimização. No entanto, a atuação dessas tecnologias ocorre no nível das instâncias de dados. Isso significa que elas rastreiam os valores reais preenchidos pelos clientes, como números de documentos ou endereços físicos armazenados.

Essa característica define o momento de intervenção e a tecnologia de base. Tais soluções operam na proteção de bancos de dados já populados ou em fluxos de memória de trânsito. O funcionamento delas depende do reconhecimento de entidades nomeadas e de padrões fixos para encontrar vazamentos. Esse modelo corretivo cumpre o seu papel na segurança da informação. Contudo, ele exige a coleta prévia do dado em algum nível.

A arquitetura proposta neste artigo atua de forma complementar a esses sistemas corporativos para preencher essa lacuna técnica. Em vez de inspecionar os registros físicos dos usuários, a abordagem foca na governança preventiva. Enquanto as plataformas convencionais buscam formatos fixos em dados brutos, o filtro aqui proposto avalia a descrição da variável para compreender o seu significado. Isso cria uma camada de proteção focada no desenho do projeto, resguardando os modelos de crédito contra atributos inadequados antes do início da coleta de dados.

---
---
Para preencher o termo de autorização de publicação da SBC, você deve preencher os campos referentes ao autor e à obra. Veja como proceder em cada parte:

  

- **CEDENTE(S):** Insira o nome do(s) autor(es) da obra. Caso haja mais de um autor, coloque os nomes de todos conforme a autoria do artigo.      

- **DO OBJETO (TÍTULO):** Insira o título exato do seu artigo acadêmico ou trabalho que será publicado.      

- **DO OBJETO (VEÍCULO):** Indique o nome do evento, simpósio ou veículo onde a obra será publicada (por exemplo, WICS 2020).      

- **Data e Assinatura do Agente Autorizado:** No final do documento, preencha a data da assinatura (cidade, dia, mês e ano). No campo reservado ao "Agente autorizado", o autor responsável por assinar o documento em nome de todos os coautores deve preencher o seu próprio **Nome** e assinar.      

---
---

### 4. Geração Sintética e Avaliação com Modelos de Linguagem

- **Conteúdo / Cursos**: Artigos seminais sobre Self-Instruct (Wang et al.) e UltraFeedback (Cui et al.).