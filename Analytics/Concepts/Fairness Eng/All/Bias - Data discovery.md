---
banner: Pasted image 20260716172629.png
banner-x: 50
banner-y: 47
---
---

````ad-quote
title:
##### **Intro ) -** Data discovery

```ad-quote
title:
<p align="justify">Se você está desenvolvendo algo que lida com dados de usuários e os envia para um LLM, você tem um problema relacionado a PII (Personally Identifiable Information). Nomes, e-mails, números de telefone, números de cartão de crédito e números de documentos de identificação (como o CPF ou SSN) estão presentes em chamados de suporte, registros de chat, documentos e campos de banco de dados. Sempre que você insere esses dados em um prompt, está enviando informações pessoais de alguém para o endpoint de um modelo de terceiros. Talvez isso seja aceitável para o seu caso de uso; talvez não. De qualquer forma, você deve saber o que há nos seus dados antes de realizar essa chamada.</p>
```
````

>[!quote] **Link:** [Web Article 1](https://www.machertecnologia.com.br/lgpd-data-discovery-descoberta-dados-automatizada/)

>[!quote] **Link:** [Web Article 2](https://www.osano.com/articles/data-discovery)

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - O que é Data discovery em termos de conformidade com a privacidade

```ad-quote
title:
<p align="justify">O conceito de descoberta de dados, conhecido como Data Discovery, possui aplicações amplas. No mercado em geral, o processo explora e classifica informações para gerar inteligência e orientar estratégias de negócios. O foco deste artigo, no entanto, é a aplicação dessa prática na conformidade com as leis de privacidade. Nesse cenário específico, a descoberta serve para rastrear e gerenciar dados com o objetivo de garantir a segurança e cumprir exigências legais.</p>
```
```ad-quote
title:
<p align="justify">As regulamentações atuais exigem que as empresas respondam rapidamente aos pedidos dos clientes sobre os seus próprios registros. O grande desafio é que as informações costumam estar espalhadas por dezenas de aplicativos e sistemas diferentes. Realizar essa busca de forma manual consome muito tempo e gera riscos de multas por negligência. Por esse motivo, o uso de ferramentas automatizadas para mapear a infraestrutura tornou-se essencial.</p>
```
```ad-quote
title:
<p align="justify">Esses softwares utilizam algoritmos de busca para localizar dados sensíveis em fontes variadas, como bancos de dados, documentos e e-mails. A categoria de dados sensíveis engloba informações que exigem proteção rigorosa por revelarem detalhes íntimos dos indivíduos. A lista inclui dados financeiros, registros de saúde, dados biométricos, origem racial, opiniões políticas e orientação sexual.</p>
```
```ad-quote
title:
<p align="justify">O mapeamento contínuo dessas informações sustenta as políticas de governança e de segurança da organização. A governança define as regras de controle de acesso e os prazos de retenção dos arquivos. A descoberta de dados fornece a visibilidade exata para aplicar essas regras na prática. Sem saber onde as informações sensíveis estão armazenadas e para onde elas fluem, a empresa fica incapaz de agir e vulnerável a vazamentos.</p>
```
````

> [!done] **_New_**

```ad-quote
title:
##### 1.1 ) - _Passos para a implementação do data discovery_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Mapeamento de sistemas de dados*
```

```ad-quote
title:
<p align="justify">A localização de todas as fontes de informações da empresa é o passo inicial. O uso de ferramentas automatizadas estrutura a base e substitui processos manuais lentos para cumprir os requisitos de conformidade.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) *Identificação de bases irrelevantes*
```

```ad-quote
title:
<p align="justify">Sistemas desativados ou sem dados pessoais devem ser isolados e sinalizados. A triagem prévia evita buscas desnecessárias e desperdício de tempo nas fases seguintes.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) *Geração de metadados*
```

```ad-quote
title:
A classificação das bases úteis com etiquetas de identificação guia a descoberta dos dados. O registro de metadados exige os seguintes parâmetros:
```

```bash
# C1 Conexões e direção do fluxo de informações
#
# O mapeamento rastreia a origem e o destino de cada informação pela rede da empresa.


# C2 Responsável técnico pela base
#
# O sistema indica qual equipe ou funcionário gerencia aquele repositório de arquivos.


# C3 Tipologia dos campos e definição do conteúdo armazenado
#
# As ferramentas atuais utilizam machine learning (aprendizado de máquina, em que o sistema aprende a reconhecer padrões sozinho) para classificar os dados. Isso permite categorizar um volume gigante de informações de forma automática e rápida, eliminando a dependência do trabalho manual.
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) *Localização de dados específicos*
```

```ad-quote
title:
<p align="justify">As buscas ocorrem apenas nas bases mapeadas e etiquetadas. O rastreamento do fluxo de informações documentado agiliza o atendimento a requisições de acesso ou exclusão de registros.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### E ) *Monitoramento contínuo*
```

```ad-quote
title:
<p align="justify">O ambiente tecnológico de uma empresa muda todos os dias. Novos clientes realizam cadastros e as equipes criam novos arquivos. Uma ferramenta eficiente não faz apenas uma busca única. Ela repete as varreduras de forma periódica e automática. Esse ciclo constante garante que o mapa de informações permaneça atualizado e pronto para auditorias a qualquer momento.</p>
```
````

> [!done] New

```ad-quote
title:
##### 1.3 ) - _Exemplo fluxo de dados_
```

**Coleta Direta**

O participante acessa a plataforma e realiza o cadastro com nome e e-mail. Em seguida, o perfil é completado com CPF, data de nascimento, foto e endereço. Durante a inscrição, também é possível informar alergias e necessidades de acessibilidade. Essa etapa representa o momento em que a plataforma recebe a informação em primeira mão.

**Cópia Entre Sistemas**

O organizador extrai listas com os participantes que informaram alergias ou restrições de acessibilidade para preparar a estrutura do evento. O nome e as informações de saúde saem do banco de dados principal e viram uma planilha separada. O administrador também exporta relatórios financeiros das inscrições com valores e métodos de pagamento para realizar o controle de caixa. O registro da compra passa a existir em um arquivo isolado.

**Dados Vindos de Terceiros**

No pagamento via cartão de crédito, a plataforma se comunica com um gateway externo. Esse sistema aprova a compra e devolve um código de transação para o sistema de palestras. Esse código fica salvo no registro financeiro da inscrição. Isso representa um dado gerado e enviado por uma empresa terceira.

**O Desafio da Privacidade**

Caso ocorra um pedido de exclusão de dados, a organização enfrenta um problema de fragmentação. As informações não estão centralizadas no perfil principal do usuário. É necessário apagar os dados médicos da lista de alimentação, remover as restrições da lista de acessibilidade e desvincular o código de transação dos relatórios exportados.

> [!done] New

##### 1.4 ) - _Aplicação do fluxo de dados_

**1. Mapeamento de sistemas de dados**

A ferramenta de descoberta se conecta ao banco de dados principal do sistema de palestras. Ela varre as tabelas onde as informações originais ficam guardadas, como a tabela PESSOA e a tabela ENDERECO. Em seguida, o software procura pelos arquivos secundários na rede da empresa. Ele localiza as listas de participantes com restrições exportadas pela organização e os relatórios de pagamentos aprovados exportados pela administração.

**2. Identificação de bases irrelevantes**

O sistema analisa as estruturas mapeadas e separa o que não envolve privacidade. Ele identifica que a tabela PREDIO guarda apenas os nomes e os endereços dos locais físicos. Ele também nota que a tabela SALA guarda apenas a capacidade e o nome dos espaços. Esses repositórios são marcados como irrelevantes e ficam de fora das próximas etapas de busca.

**3. Geração de metadados**

A plataforma aplica as etiquetas de identificação nas bases consideradas úteis.

- **3.1 Conexões e direção do fluxo** A ferramenta registra que os dados da tabela PESSOA_ALERGIA saem do sistema e alimentam uma lista externa gerada para a equipe de organização. Ela também mapeia que a tabela PAGAMENTO recebe o código de transação diretamente de um gateway externo.

- **3.2 Responsável técnico** O mapa indica que o perfil de Organizador é o responsável pelas listas de participantes com necessidades de acessibilidade. O perfil de Administrador fica marcado como o responsável pela exportação dos dados financeiros.

- **3.3 Tipologia dos campos** O motor de inteligência artificial lê as colunas e classifica o conteúdo de forma automática. Ele etiqueta a coluna cpf na tabela PESSOA como um documento oficial. Ele classifica o campo foto_url como um dado de identificação visual. O campo detalhes, localizado na tabela PESSOA_RESTRICAO, recebe a etiqueta de dado sensível de saúde.


**4. Localização de dados específicos**

Um participante solicita a exclusão total do seu cadastro na plataforma. A ferramenta usa o mapa criado para encontrar todas as ramificações de forma ágil. Ela localiza o registro principal na tabela PESSOA e o endereço na tabela ENDERECO. Ao mesmo tempo, o sistema aponta que o nome do usuário está na lista externa de alimentação e que o código de transação dele está no relatório financeiro exportado.

**5. Monitoramento contínuo**

O uso da plataforma ocorre de forma diária. Novos visitantes criam contas informando nome e e-mail. Os organizadores criam novos eventos e novas palestras. O administrador exporta novos relatórios financeiros de inscrições para fazer a conciliação da semana. A ferramenta de descoberta realiza varreduras automáticas todos os dias para detectar esses novos cadastros e arquivos. Essa repetição garante que os novos dados recebam as etiquetas corretas imediatamente.

> [!done] New

##### 1.5 ) - _Ferramentas que compõem o Data Discovery_

https://home.bigid.com/demo

**Corporativas**

https://www.forcepoint.com/blog/insights/pii-data-discovery-tools
- 6 Best PII Data Discovery Tools

https://netwrix.com/en/resources/blog/pii-discovery-tools/
- Top 10 PII discovery tools

**Open Source**

PII-Codex
Microsoft Presidio

> [!done] New

##### 1.6 ) - _Discovery em diferentes tipos de dados_

- [ ] Nesta fase pretendo aplicar o MP ou o PII-Codex em diferentes tipos de dados

Texto: e-mail's, relatório entre membros da empresa...
Tabelas: csv's, xlsm's...
Banco de dados: SQL...

---

```ad-done
title:

#### **Fase 2 ) - ...**

```

---
##### **02 ) -** Data Anonymizatio

https://www.imperva.com/learn/data-security/anonymization/
- Fala sobre os tipos de anonimização.

## **06 ) Técnicas de tratamento e anonimização**

Aqui estão os métodos que você pode abordar nesse novo módulo.

1. Censura direta A ferramenta substitui a palavra sensível pelo nome da categoria correspondente. O nome do cliente desaparece e o espaço recebe apenas a etiqueta pessoa. Essa é a abordagem mais simples e corta totalmente a leitura do dado.
    
2. Mascaramento parcial O sistema esconde apenas um trecho da informação com caracteres especiais. O computador mantém os três primeiros dígitos de um documento e troca o restante por asteriscos. Essa técnica ajuda os atendentes de suporte a confirmarem a identidade do cliente sem ver a numeração completa.
    
3. Criptografia irreversível O programa aplica uma função matemática conhecida como hash. Esse cálculo transforma a palavra original em uma sequência embaralhada de letras e números que não pode ser desfeita. Os cientistas de dados usam muito essa técnica para agrupar clientes semelhantes sem saber a identidade real de nenhum deles.
    
4. Pseudonimização O computador troca a informação verdadeira por um dado falso do mesmo formato. O sistema substitui o nome real do cliente por um nome inventado aleatoriamente. O texto continua natural para a leitura humana e a privacidade do usuário permanece garantida.

---

## **01 ) Implementação ideal do Data Discovery**

Apresentação da arquitetura lógica e do fluxo que a ferramenta segue para encontrar e proteger as informações sensíveis dentro de um ambiente corporativo.

## **02 ) Considerações na escolha da ferramenta**

Estudo dos critérios fundamentais para selecionar a tecnologia correta, avaliando a amplitude de cobertura, a precisão da classificação, a visibilidade de acesso, a capacidade de correção e o alinhamento com as normas de conformidade.

## **03 ) Tipos de ferramentas**

Comparação entre as soluções disponíveis no mercado, diferenciando as plataformas corporativas comerciais das alternativas de código aberto.

## **04 ) Métodos utilizados**

Exposição das abordagens técnicas tradicionais e modernas empregadas na varredura de dados, englobando listas de bloqueio, expressões regulares, reconhecimento por inteligência artificial, validação matemática e análise de contexto.

## **05 ) Aplicação prática do Microsoft Presidio**

Demonstração completa da ferramenta aplicada a casos reais do dia a dia das empresas:

- Listagem e explicação das categorias padrão de entidades mapeadas
    
- Varredura e avaliação visual de textos em português e em inglês
    
- Inspeção de mensagens de e-mail com a inserção de regras personalizadas e a análise de riscos de falsos positivos
    
- Processamento automatizado de colunas sensíveis em planilhas estruturadas no formato CSV
    
- Leitura óptica e anonimização de dados confidenciais presentes em imagens médicas

---

### **Área de teste livre**

Você pode criar uma caixa de texto vazia na tela. O público sugere frases durante a apresentação. Você digita a sugestão e o sistema colore as informações sensíveis na mesma hora. Isso prova que a ferramenta funciona de verdade e reage a cenários que não estavam programados no roteiro.

---