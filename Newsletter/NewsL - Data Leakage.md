
---

- Ao normalizar um dado preciso aplicar essa normalização tanto nos dados de treino quanto nos dados de teste mesmo após realizar o split e tomar os devidos cuidados visando previnir o vazamento de dados?

---

=> O que é o Target Leakage
=> Exemplos ilustrativos
=> Formas de mitigar

---
Target Leakage 

Ocorre quando o modelo possui dados que não estarão disponíveis no momento da predição.

Usar informações que não estarão disponíveis durante as previsões do mundo real leva ao Overfitting - [[DL P - Overfitting & Underfitting |{ X }]], onde o modelo tem um desempenho excepcionalmente bom em dados de treinamento e validação, mas ruim em produção. 

Na tabela abaixo referente à previsão de uma transação problemática no setor bancário temos a variável blocked. Ela atua como um exemplo clássico de um atributo que carrega informações futuras sobre a base de dados.

| id   | acquire | score | balance | blocked | target |
| ---- | ------- | ----- | ------- | ------- | ------ |
| 1024 | Yes     | 720   | 1500    | Yes     | Yes    |
| 1025 | No      | 450   | 120     | No      | No     |
| 1026 | Yes     | 890   | 5400    | No      | No     |
| 1027 | Yes     | 310   | 15      | Yes     | Yes    |
| 1028 | No      | 610   | 850     | No      | No     |

Essa marcação só é inserida no sistema após a identificação do problema e da aplicação do bloqueio pela instituição financeira. Portanto para que ela exista a resposta final já precisou ser coletada.

|       | id  | items | discount | tax   | target |
| ----- | --- | ----- | -------- | ----- | ------ |
| **0** | 701 | 3     | Yes      | 15.20 | Yes    |
| **1** | 702 | 1     | No       | 0.00  | No     |
| **2** | 703 | 5     | Yes      | 42.80 | Yes    |
| **3** | 704 | 2     | No       | 0.00  | No     |

No exemplo acima, temos uma ocorrência de target leakage mais sutil. Na construção de um modelo que visa prever uma venda no e-commerce, a variável _tax_ está presente para calcular a quantidade de impostos pagos. Entretanto, o imposto só é recolhido após a conclusão da compra. Dessa forma, o modelo pode aprender o padrão óbvio _"Se o valor do imposto é maior que zero, a compra foi realizada"_, o que enviesa o resultado final e prejudica o desempenho em produção.

Outro detalhe é que o modelo vai perceber que há uma forte correlação entre as variáveis problemáticas com a feature alvo, e como os dados de validação possuem a mesma fonte do conjunto de treino, esse padrão irá se repetir durante o processo de validação mostrando um resultado aparentemente alto. Mas esse resultado não irá se repetir quando o modelo avaliar dados do mundo real ocasionando o Overfitting.

---

raw:
Ou seja, o pré-processamento deve ser feito sempre após a divisão dos dados para impedir a contaminação de treino e teste.

Preenchimento de valores vazios, tratamento de variáveis categóricas, normalização ou padronização dos dados, etc. **Tudo deve ser feito** **após** **a divisão entre treino e teste**. Vamos ao porquê:

Imagine que em um conjunto de dados, temos uma feature com alguns valores nulos e, antes da divisão, resolvemos preenchê-los com a média dos valores existentes. Ao calcularmos essa média, estaremos usando informações de todos os dados dessa feature presentes nesse conjunto, ou seja, estaremos usando valores que futuramente estarão nos dados de teste quando realizarmos a divisão, e os dados de teste são dados que nosso modelo não pode ver na hora de treinar. Então, os valores preenchidos pela média que fizerem parte do conjunto de treino estarão contaminados com os dados de teste.

Os problemas são os mesmos citados anteriormente: um desempenho muito bom do modelo durante o treinamento e até mesmo na validação, mas um desempenho ruim na hora de avaliar novos dados.

Outra situação é durante o tratamento de variáveis categóricas. Ao utilizarmos um encoder, ou codificador, para transformar as features categóricas antes da divisão em treino e teste, a lógica é a mesma do caso acima. Além disso, mesmo após a divisão, podemos ter problemas se utilizarmos o método _fit_transform_ nos dados de teste (ou validação) em vez de apenas o _transform_. Segue um exemplo genérico abaixo para ilustrar:

X_valid = encoder.fit_transform(X_valid)

Nunca utilize o método _fit_transform_ no conjunto de dados de teste, apenas nos dados de treino. Nos dados de teste, utilize apenas o _transform_. Veja abaixo:

X_train = encoder.fit_transform(X_train)  
X_valid = encoder.transform(X_valid)

Ou seja, o codificador aprende apenas com o padrão dos dados de treino e realiza, com base neles, a transformação nas variáveis categóricas dos dados de teste. Se o _fit_ fosse utilizado também nos dados de teste, isso resultaria em uma contaminação dos dados de teste com informações do conjunto de treinamento.

---
```embed
title: "Data Leakage: O que é? Como evitar?"
image: "https://miro.medium.com/v2/resize:fit:1200/1*01v95QfBuWS_-RnANkWQIA.jpeg"
description: "No campo dos problemas em ciência de dados, ele é pouca mídia, mas muito futebol."
url: "https://medium.com/@andreycp17/data-leakage-o-que-%C3%A9-como-evitar-ba1fa8c9db70"
favicon: ""
aspectRatio: "66.66666666666666"
```
---
```embed
title: "O que é vazamento de dados no aprendizado de máquina? | IBM"
image: "https://www.ibm.com/content/dam/worldwide-content/stock-assets/adb-stk/ul/g/b3/7e/adobestock_637245990.jpeg/_jcr_content/renditions/cq5dam.web.1280.1280.jpeg"
description: "O vazamento de dados no aprendizado de máquina ocorre quando um modelo usa informações durante o treinamento que não estariam disponíveis no momento da previsão."
url: "https://www.ibm.com/br-pt/think/topics/data-leakage-machine-learning"
favicon: ""
aspectRatio: "66.640625"
```
---
```embed
title: "12. Common pitfalls and recommended practices"
image: "https://scikit-learn.org/stable/_static/scikit-learn-logo-notext.png"
description: "The purpose of this chapter is to illustrate some common pitfalls and anti-patterns that occur when using scikit-learn. It provides examples of what not to do, along with a corresponding correct ex..."
url: "https://scikit-learn.org/stable/common_pitfalls.html"
favicon: ""
aspectRatio: "54.151624548736464"
```
---
```embed
title: "Pipelines no Scikit-Learn: Transformações sem Data Leakage"
image: "https://sigmoidal.ai/wp-content/uploads/2026/07/pipelines-scikit-learn-capa.jpg"
description: "Você sabia que é possível \"ver a prova antes\" sem perceber ao treinar um modelo de machine learning? Esse erro"
url: "https://sigmoidal.ai/pipelines-scikit-learn/"
favicon: ""
aspectRatio: "56.2799043062201"
```
---
```embed
title: "Data Leakage"
image: "https://www.kaggle.com/open-graph/images/Notebooks/3115809"
description: "Explore and run AI code with Kaggle Notebooks | Using data from multiple data sources"
url: "https://www.kaggle.com/code/alexisbcook/data-leakage"
favicon: ""
aspectRatio: "53.57142857142857"
```
---
```embed
title: "Data Leakage: uma verdadeira ARMADILHA para o cientista de dados"
image: "https://i.ytimg.com/vi/cauYnbfiayU/maxresdefault.jpg"
description: "Atenção: Data Leakage não é um vazamento de dados como você vê no noticiário. No vídeo de hoje, convidamos quatro especialistas do nosso time para falar sobr..."
url: "https://www.youtube.com/watch?v=cauYnbfiayU"
favicon: ""
aspectRatio: "56.25"
```
---


