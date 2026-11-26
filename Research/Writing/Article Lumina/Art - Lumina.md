---
banner: Pasted image 20260827172940.png
banner-x: 50
banner-y: 35
---
---

````ad-quote
title:

```ad-quote
title:
###### Obrigações
```
````

- Todo o dataset precisa estar contido em apenas um csv.
- O dataset precisa ter variáveis demográficas e financeiras. 
- O dataset precisa ter uma variável target

---

> [!done] **_New_**

---

````ad-quote
title:

```ad-quote
title:
###### Clean ) Tratamento dos datasets
```
````

```ad-quote
title:

| Coluna           | Descrição                              |
| ---------------- | -------------------------------------- |
| column           | Nomes das features no dataset original |
| variable_type    |                                        |
| variable_subtype |                                        |
| description      | Descrição das features                 |
| transformation   |                                        |
| status           |                                        |
```

```ad-quote
title:
[X] - D02 - Default of Credit Card Clients
```

```ad-quote
title:
[O] - D04 - Mortgage data HMDA
```

```ad-quote
title:
[O] - D05 - ACSIncome
```

```ad-quote
title:
[X] - D07 - Adult Dataset
```

```ad-quote
title:
[O] - D08 - South German Credit
```

```ad-quote
title:
[O] - D17 - Bondora P2P Loans
```

```ad-quote
title:
[] - D19 - Credit Card Approval Prediction
```

---

> [!done] **_New_**

---

````ad-quote
title:

```ad-quote
title:
###### Fase 1 ) Correlação das variáveis
```
````
#### Objetivo

- Encontrar possíveis relações entre as variáveis de crédito utilizando métodos de correlação e associação para variáveis categóricas e numéricas. Dessa forma, será possível identificar alguma feature que possa ser removida  
#### Problemática
#### Referências

---

> [!done] **_New_**

---

````ad-quote
title:

```ad-quote
title:
###### Fase 2 ) Importância das variáveis
```
````

#### Objetivos

- Rodar modelos de predição visando coletar quais features contribuirão mais para a inferência do modelo especificando para o contexto em específico da base de dados. 
- Dessa forma, seria possível correlacionar a macro categoria da variável com a sua devida importância na predição. 
- Além disso, essa informação pode está contida no web site.
#### Problemática
#### Referências

---

> [!done] **_New_**

---

````ad-quote
title:

```ad-quote
title:
###### Fase 3 ) Análise da inferência
```
````

#### Objetivos

- Análise do output com as métricas de equidade

#### Problemática


#### Referências

```embed
title: "docs.google.com"
image: "https://ssl.gstatic.com/docs/common/product/docs_app_icon2.png"
description: ""
url: "https://docs.google.com/document/d/178_GkNXFOjPaXzdJiDKUbTcOJOhCT3UVSeCgBoNUOdc/edit?tab=t.0#heading=h.bwovdglk3vrf"
favicon: ""
aspectRatio: "100"
```

---
Fase 4

- Tentativa de mitigação tanto do output quanto do XAI

---
Fase 5

- Análise do que funcionou na fase 4 aplicando o XAI e a as métricas de equidade novamente
---










---
---
### **Problemas na Estrutura dos Dados**

- **Variáveis substitutas:** Uma coluna neutra pode mascarar um dado protegido. O código postal de um cliente revela a sua classe social ou etnia de forma indireta para o algoritmo.
    
- **Desbalanceamento natural:** O mercado financeiro possui muito mais clientes bons do que maus pagadores. Essa desproporção força a máquina a aprender os padrões da classe dominante. A máquina passa a ignorar as características específicas das minorias.
    
- **Incompatibilidade de regras:** Instituições diferentes possuem métricas distintas. Um banco europeu pode definir inadimplência como um atraso de noventa dias. Uma financeira pode exigir apenas trinta dias para o mesmo rótulo.
    
- **Isolamento cultural:** O comportamento de consumo muda de acordo com a geografia. Você não pode misturar linhas de bases de países diferentes. O peso do dinheiro e a economia local variam muito.
    

### **Problemas na Avaliação Estatística**

- **Ilusão de causalidade:** Dois números crescerem juntos na sua matriz de correlação não indica ligação direta. A estatística aponta uma coincidência numérica. Ela não comprova a existência de uma relação de causa e efeito no mundo físico.
    
- **Herança de preconceitos:** Os arquivos originais refletem o histórico das instituições. A política antiga de um banco pode ter negado crédito para pessoas jovens sistematicamente. O modelo estatístico vai encarar essa distorção humana como uma regra matemática exata.
    

### **Problemas na Explicabilidade**

- **Limitação do diagnóstico:** O Explainable Boosting Machine aponta com exatidão o peso de cada variável na decisão. A ferramenta não tem capacidade de julgar valores éticos. Ela não sabe se a regra aprendida é socialmente justa.
    
- **Múltiplas métricas:** Não existe uma fórmula única para definir um modelo justo. Equalizar a taxa de aprovação entre diferentes idades pode desequilibrar a taxa de falsos positivos. Isso gera um grande impasse técnico na hora de calibrar o sistema.

---
---

### **Modelos Transparentes contra Caixas Pretas**

- O artigo Stop Explaining Black Box Machine Learning Models for High Stakes Decisions foi publicado pela pesquisadora Cynthia Rudin.
    
- Esse texto é a maior referência atual para justificar a arquitetura da sua segunda fase.
    
- A autora defende que decisões críticas como a concessão de crédito financeiro nunca devem usar algoritmos fechados e obscuros.
    
- Ela argumenta a favor de modelos nativamente transparentes, validando a sua escolha por ferramentas que permitem a leitura visual direta.
    

### **O Mapa sobre Vieses e Variáveis Substitutas**

- O artigo A Survey on Bias and Fairness in Machine Learning foi escrito por Ninareh Mehrabi e um grupo de pesquisadores.
    
- Esse documento funciona como um grande catálogo sobre os problemas de justiça algorítmica modernos.
    
- O texto explica de forma muito clara como as variáveis substitutas se formam e se escondem dentro de grandes bases de dados.
    
- A leitura substitui o livro recomendado anteriormente e entrega as definições teóricas prontas para você citar na introdução do seu projeto.
    

### **A Defesa do Especialista Humano**

- O artigo Power to the People The Role of Humans in Interactive Machine Learning foi publicado por Saleema Amershi e sua equipe.
    
- Esse trabalho acadêmico consolida a importância de manter um operador humano no ciclo de aprendizado dos algoritmos.
    
- O texto demonstra que o processamento estatístico perde a sua utilidade real sem a interpretação de contexto feita por um especialista.
    
- Essa é a referência ideal para você embasar a criação da sua ferramenta de auditoria e validação de dados.



