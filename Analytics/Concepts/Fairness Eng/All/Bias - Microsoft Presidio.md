
---

Inventário de dados

Descrição do sistema legado -> Realizar o Discovery SQL -> Exportar uma das tabelas -> Exportar -> Anonimizar.

https://dev.to/bspann/what-is-microsoft-presidio-and-why-you-need-it-setup-first-detection-6mh

https://www.alura.com.br/artigos/nltk-vs-spacy?srsltid=AfmBOoqvpzJQPb2P9cBWkDXBE2UuosvsaUISsiexl9-N3DbwXovy26Yt

https://www.gov.br/anpd/pt-br/centrais-de-conteudo/documentos-tecnicos-orientativos/estudo_tecnico_sobre_anonimizacao_de_dados_na_lgpd_uma_visao_de_processo_baseado_em_risco_e_tecnicas_computacionais.pdf/@@display-file/file

https://getprivacy.com.br/anonimizacao-de-dados-lgpd/

https://presidio.dataprivacystack.org/

The Analyzer finds PII. It combines named entity recognition (NER) from spaCy or Hugging Face transformers with regex pattern matching and contextual scoring. When you feed it text, it returns a list of detected entities with types, confidence scores, and character positions. It doesn't modify the text. It just tells you what it found.

The Anonymizer takes the analyzer's output and does something with it. Replace detected names with `<PERSON>`. Redact phone numbers entirely. Mask credit card numbers with asterisks. Hash emails. Encrypt values you need to reverse later. The anonymizer is where you decide how to handle each entity type.

Beyond those two, Presidio has additional modules for specific use cases. presidio-image-redactor handles OCR on images and redacts PII from screenshots and scanned documents. presidio-structured processes tabular data in DataFrames and JSON. We'll get to those in later parts of this series.

---
https://presidio.dataprivacystack.org/samples/
### Analyze and Anonymize CSV file

Esse é o ponto de partida ideal. Como vimos no exemplo prático anterior, exportar as tabelas do seu banco de dados para arquivos de texto separados por vírgulas é uma abordagem muito eficaz. Esse tutorial ensina detalhadamente como ler esses arquivos e aplicar as regras de privacidade direto nas colunas corretas.

### Presidio Structured Basic Usage Notebook

O seu sistema de eventos armazena informações estruturadas. A informação estruturada é aquela organizada de forma rígida em linhas e colunas dentro do banco de dados. Esse guia foca em mostrar como o motor do programa lê esse formato específico de grade com eficiência.

### Pseudonymization

Esse guia lida com a substituição de valores usando mapeamentos. Isso é muito importante para manter a lógica matemática do seu banco de dados. Como você possui tabelas distintas para palestras e avaliações, um mesmo usuário vai aparecer em vários lugares diferentes. A técnica ensinada aqui garante que o sistema substitua o nome real sempre pelo mesmo nome fictício em todas as tabelas.

### Passing a lambda as a Presidio anonymizer using Faker

Para um ambiente de ensino, entregar tabelas cheias de asteriscos dificulta a leitura e o teste de telas. Esse tutorial ensina a conectar o motor de privacidade a uma biblioteca chamada Faker. O Faker é um gerador de informações falsas. Essa união permite que você troque nomes e documentos reais por dados fictícios muito realistas.

### Analyzing structured data in batch

Quando a sua base de eventos crescer, ler uma inscrição por vez vai demorar muito. Esse documento apresenta o conceito de processamento em lote. O processamento em lote é a ação de agrupar milhares de registros em blocos e enviar todos de uma única vez para o analisador. Isso reduz drasticamente o tempo necessário para gerar a cópia pública da sua aplicação.

---

Imagem:

https://presidio.dataprivacystack.org/samples/python/plot_custom_bboxes/

csv:

[Analyze and Anonymize CSV file](https://github.com/data-privacy-stack/presidio/blob/main/docs/samples/python/process_csv_file.py)

pdf:

https://presidio.dataprivacystack.org/samples/python/example_pdf_annotation/