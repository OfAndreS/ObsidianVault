---
banner: "![[Pasted image 20260107191458.png]]"
---

---

````ad-quote
title:
##### **Intro )** - Matriz de Confusão
```ad-quote
title:
A matriz de confusão é uma ferramenta fundamental para avaliar o desempenho de modelos de classificação, permitindo enxergar além da simples acurácia global. Ela funciona como um mapa que mostra onde o seu modelo está acertando e, principalmente, onde ele está _confundindo_ as classes.
```

![[Pasted image 20251103145513.png]]


```ad-quote
title:

| Conceito                    | Definição                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Verdadeiro Positivo ($TP$): | O modelo previu a classe de interesse corretamente. No seu projeto de risco, seria identificar corretamente um _inadimplente_.                                                          |
| Verdadeiro Negativo ($TN$): | O modelo previu corretamente que o registro não pertence à classe de interesse. Seria identificar um _bom pagador_.                                                                     |
| Falso Positivo ($FP$):      | Também conhecido como _erro do tipo I_. O modelo aponta um positivo que, na realidade, é negativo. Isso resultaria em negar crédito a um cliente saudável.                              |
| Falso Negativo ($FN$)       | Conhecido como _erro do tipo II_. O modelo falha em detectar um positivo real. No contexto bancário, isso é crítico, pois significa conceder crédito a alguém que entrará em _default_. |

```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **01 )** - Descrição da Métrica Acurácia - Accuracy
```ad-quote
title:
<p align="justify">A acurácia representa a métrica mais intuitiva para problemas de classificação, funcionando como um termômetro inicial sobre o aprendizado do modelo. Ela quantifica a proporção de predições corretas em relação ao volume total de casos, facilitando a comunicação com públicos que não possuem viés técnico.</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Atributos e Escala de Valor
```

```ad-quote
title:
|**Métrica**|**Descrição Detalhada**|**Papel Na Avaliação**|
|---|---|---|
|**TP / TN**|Soma dos acertos para as classes positivas e negativas.|Representa o Sucesso Global do modelo.|
|**FP / FN**|Soma dos erros de falso positivo e falso negativo.|Representa a Falha de Predição.|
|**Faixa 1.0**|Valor máximo que indica 100% de acerto nos dados.|Indica Perfeição ou possível Overfitting.|
|**Faixa 0.0**|Valor mínimo que indica erro em todas as classificações.|Indica Falha Total do algoritmo.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação Matemática e Trade-off
```

```ad-quote
title:
<p align="justify">A fórmula utiliza os quatro valores fundamentais da matriz de confusão para determinar a precisão global. Contudo, ao otimizar apenas esse índice, corre-se o risco de ignorar o custo desproporcional entre deixar passar um devedor e negar crédito a um bom pagador.</p>
```

![[Pasted image 20260108105228.png]]

```ad-quote
title:
- $$\text{Acurácia} = \frac{TP + TN}{TP + TN + FP + FN}$$
```

```ad-quote
title:
<p align="justify">O trade-off ocorre porque a acurácia trata todos os erros com o mesmo peso, o que pode mascarar prejuízos financeiros em análises de risco onde a sensibilidade aos falsos negativos é prioritária.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Limitações e Padrões de Mercado
```

```ad-quote
title:
|**Contexto**|**Referência Técnica**|**Impacto No Negócio**|
|---|---|---|
|**Modelos Iniciais**|Valores situados entre 0.75 e 0.80.|Patamar mínimo para viabilidade.|
|**Baixo Risco**|Resultados frequentemente acima de 0.90.|Padrão comum em carteiras estáveis.|
|**Desbalanceamento**|Falha grave em dados com classes minoritárias.|Risco de gerar modelos burros.|
```

```ad-quote
title:
<p align="justify">Em cenários onde 98% dos clientes são bons pagadores, um modelo que classifique todos como positivos terá 98% de acurácia, mas falhará em identificar 100% dos inadimplentes, tornando a métrica traiçoeira para decisões de crédito.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) Implementação em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`accuracy_score`|Função do Scikit-Learn para cálculo numérico.|Gera o índice percentual de acerto.|
|`ClassificationReport`|Visualizador da biblioteca Yellowbrick.|Gera um relatório visual completo.|
|`y_true / y_pred`|Vetores de valores reais e preditos.|Servem como base de comparação.|

```

```python
from sklearn.metrics import accuracy_score
from yellowbrick.classifier import ClassificationReport

# Cálculo da acurácia simples
acuracia = accuracy_score(y_true, y_pred)
print(f"Acurácia do Modelo: {acuracia:.4f}")

# Visualização completa com Yellowbrick
visualizer = ClassificationReport(modelo, classes=['Não Inadimplente', 'Inadimplente'])
visualizer.fit(X_train, y_train)
visualizer.score(X_test, y_test)
visualizer.show()
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 )** - Descrição da Métrica Precisão - Precision
```ad-quote
title:
<p align="justify">A precisão, também conhecida como valor preditivo positivo, foca especificamente na qualidade das predições positivas realizadas pelo modelo. Ela busca responder qual a proporção de casos classificados como positivos que são realmente verdadeiros, servindo como um controle rigoroso contra a ocorrência de falsos positivos.</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Atributos e Escala de Valor
```

```ad-quote
title:
|**Métrica**|**Descrição Detalhada**|**Papel Na Avaliação**|
|---|---|---|
|**TP**|Verdadeiros Positivos que representam os acertos da classe alvo.|Indica a Assertividade Direta do modelo.|
|**FP**|Falsos Positivos que representam alarmes falsos do sistema.|Mede o Custo da Inconveniência ou erro de alocação.|
|**Faixa 1.0**|Valor máximo que indica total confiabilidade nas predições positivas.|Indica que quando o modelo aponta algo, ele está correto.|
|**Faixa 0.0**|Valor mínimo que indica que o modelo gera apenas alarmes falsos.|Indica a Incapacidade de Filtragem da classe alvo.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação Matemática e Trade-off
```

```ad-quote
title:
<p align="justify">A métrica relaciona os acertos positivos com o total de vezes que o modelo previu a classe positiva, independentemente de ter acertado ou não. Ao aumentar a precisão, o modelo torna-se mais conservador, exigindo maior certeza antes de classificar um registro como positivo.</p>
```

```ad-quote
title:
- $$\text{Precisão} = \frac{TP}{TP + FP}$$
```

```ad-quote
title:
<p align="justify">O trade-off principal ocorre com a revocação (recall). Para garantir uma precisão elevada, o modelo ignora casos duvidosos, o que pode aumentar o número de falsos negativos e reduzir a capacidade de cobertura total dos eventos positivos reais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Limitações e Padrões de Mercado
```

```ad-quote
title:
|**Contexto**|**Referência Técnica**|**Impacto No Negócio**|
|---|---|---|
|**Sistemas de Spam**|Valores tipicamente acima de 0.95.|Evita que e-mails importantes sejam perdidos.|
|**Alta Renda**|Busca por precisão máxima na concessão.|Garante a alocação de capital em perfis seguros.|
|**Uso Isolado**|Pode ocultar a baixa detecção de casos totais.|Risco de ignorar a maioria dos positivos reais.|
```

```ad-quote
title:
<p align="justify">A precisão isolada é perigosa porque não informa sobre os casos que o modelo não conseguiu detectar. Um modelo pode atingir 100% de precisão ao encontrar apenas um caso fácil em um milhão, sendo totalmente ineficiente para a detecção da massa crítica de dados.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) Implementação em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`precision_score`|Função do Scikit-Learn para cálculo do valor preditivo.|Gera o índice de pureza das predições.|
|`PrecisionRecallCurve`|Visualizador da biblioteca Yellowbrick.|Permite analisar o equilíbrio entre métricas.|
|`y_true / y_pred`|Vetores de entrada para comparação de performance.|Base fundamental para o cálculo da métrica.|

```

```python
from sklearn.metrics import precision_score
from yellowbrick.classifier import PrecisionRecallCurve

# Cálculo da precisão simples
precisao = precision_score(y_true, y_pred)
print(f"Precisão do Modelo: {precisao:.4f}")

# Visualização da Curva Precision-Recall com Yellowbrick
viz = PrecisionRecallCurve(modelo)
viz.fit(X_train, y_train)
viz.score(X_test, y_test)
viz.show()
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **03 )** - Descrição da Métrica Recall - Sensitivity
```ad-quote
title:
<p align="justify">O recall, também chamado de revocação ou sensibilidade, mede a capacidade do modelo em identificar todos os casos positivos reais presentes no conjunto de dados. Esta métrica é fundamental em cenários onde omitir um evento positivo acarreta riscos elevados, como na detecção de fraudes ou em diagnósticos médicos críticos.</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Atributos e Escala de Valor
```

```ad-quote
title:
|**Métrica**|**Descrição Detalhada**|**Papel Na Avaliação**|
|---|---|---|
|**TP**|Verdadeiros Positivos corretamente identificados pelo algoritmo.|Representa a Capacidade de Detecção real.|
|**FN**|Falsos Negativos onde o modelo falhou em ver a classe positiva.|Representa a Taxa de Omissão do sistema.|
|**Faixa 1.0**|Valor máximo que indica a captura de todos os positivos reais.|Indica que nada de importante passou despercebido.|
|**Faixa 0.0**|Valor mínimo que indica cegueira total para a classe alvo.|Indica falha crítica na identificação de eventos.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação Matemática e Trade-off
```

```ad-quote
title:
<p align="justify">A métrica foca na proporção de acertos dentro do universo total de casos que eram efetivamente positivos. Em modelos de risco de crédito, um índice elevado assegura que a maioria dos inadimplentes potenciais foi mapeada, protegendo o patrimônio da instituição financeira.</p>
```

```ad-quote
title:
- $$Recall = \frac{TP}{TP + FN}$$
```

```ad-quote
title:
<p align="justify">O trade-off ocorre diretamente com a precisão. Para elevar o recall, o modelo tende a se tornar mais alarmista e baixar seus critérios de corte, o que acaba classificando muitos casos negativos como positivos de forma equivocada.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Limitações e Padrões de Mercado
```

```ad-quote
title:
|**Contexto**|**Referência Técnica**|**Impacto No Negócio**|
|---|---|---|
|**Fraudes**|Valores comumente acima de 0.90.|Evita perdas financeiras por não detecção.|
|**Saúde**|Busca por valores próximos a 1.0.|Minimiza o risco de liberar pacientes doentes.|
|**Risco de Crédito**|Depende do apetite de risco da empresa.|Equilibra segurança com a experiência do cliente.|
```

```ad-quote
title:
<p align="justify">O recall pode ser enganoso se analisado isoladamente. Um modelo que classifique todos os clientes como inadimplentes terá recall de 100%, mas será inútil para o negócio por não distinguir bons pagadores. Por isso, deve ser interpretado junto à precisão ou pelo F1-Score.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) Implementação em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`recall_score`|Função do Scikit-Learn para cálculo da sensibilidade.|Gera o índice de cobertura da classe alvo.|
|`DiscriminationThreshold`|Visualizador da biblioteca Yellowbrick.|Auxilia no ajuste do ponto de corte ideal.|
|`y_true / y_pred`|Vetores com os dados reais e as predições.|Base de dados para o cálculo de desempenho.|

```

```python
from sklearn.metrics import recall_score
from yellowbrick.classifier import DiscriminationThreshold

# Cálculo direto da revocação
revocacao = recall_score(y_true, y_pred)
print(f"Recall do Modelo: {revocacao:.4f}")

# Visualização do impacto do limiar no Recall
visualizer = DiscriminationThreshold(modelo)
visualizer.fit(X, y)
visualizer.show()
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **04 )** - Descrição da Métrica F1-Score
```ad-quote
title:
<p align="justify">O F1-Score é a média harmônica entre a precisão e o recall, servindo como uma métrica única que busca equilibrar a exatidão e a abrangência do modelo. No seu trabalho de iniciação científica e análise de modelos de risco, esta métrica é fundamental para penalizar valores extremos e garantir que o classificador seja eficiente em ambas as frentes simultaneamente, especialmente em conjuntos de dados desbalanceados.</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Atributos e Escala de Valor
```

```ad-quote
title:
|**Componente**|**Descrição Detalhada**|**Papel Na Avaliação**|
|---|---|---|
|**Precisão**|Proporção de identificações positivas que foram realmente corretas.|Mede a exatidão das predições positivas.|
|**Recall**|Proporção de positivos reais que foram identificados corretamente.|Mede a abrangência da detecção do modelo.|
|**Faixa 1.0**|Valor máximo que representa um equilíbrio perfeito entre as métricas.|Indica um modelo altamente confiável e abrangente.|
|**Faixa 0.0**|Valor mínimo que indica falha crítica em um dos pilares base.|Indica ineficiência total na detecção ou precisão.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação Matemática e Trade-off
```

```ad-quote
title:
<p align="justify">Diferente da média aritmética, a média harmônica é mais sensível a valores baixos, forçando o resultado para baixo se uma das métricas for medíocre. Ao otimizar o F1-Score, assume-se que a precisão e o recall possuem o mesmo peso estratégico para o problema em questão.</p>
```

```ad-quote
title:
- $$F1 = 2 \cdot \frac{\text{Precisão} \cdot \text{Recall}}{\text{Precisão} + \text{Recall}}$$
```

```ad-quote
title:
<p align="justify">O trade-off reside na perda de priorização de um erro específico. Em cenários de crédito, se o custo de um falso negativo for muito superior ao de um falso positivo, um F1-Score elevado pode mascarar um risco financeiro latente por não permitir o ajuste fino de pesos individuais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Limitações e Padrões de Mercado
```

```ad-quote
title:
|**Contexto**|**Referência Técnica**|**Impacto No Negócio**|
|---|---|---|
|**Crédito**|Valores comumente acima de 0.70.|Define a segurança conforme o apetite de risco.|
|**Áudio/Multiclasse**|Referência científica acima de 0.80.|Padrão ouro para publicações em GTZAN/RAVDESS.|
|**Geral**|Ignora os Verdadeiros Negativos (TN).|Pode omitir a eficácia na classificação de negativos.|
```

```ad-quote
title:
<p align="justify">A principal limitação é o foco exclusivo na classe positiva. Em cenários onde a classificação correta da classe negativa é igualmente vital, recomenda-se complementar a análise com o Coeficiente de Correlação de Matthews (MCC) ou a Acurácia Balançada para uma visão mais holística do desempenho.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) Implementação em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`f1_score`|Função do Scikit-Learn para o cálculo da média harmônica.|Gera o índice consolidado de desempenho.|
|`ClassificationReport`|Visualizador da biblioteca Yellowbrick.|Permite comparar o F1-Score entre diferentes classes.|
|`average='macro'`|Parâmetro para cálculo em problemas multiclasse.|Trata todas as classes com pesos iguais no resultado.|

```

```python
from sklearn.metrics import f1_score
from yellowbrick.classifier import ClassificationReport

# Cálculo do F1-Score para classificação binária
# y_true: valores reais | y_pred: valores previstos
valor_f1 = f1_score(y_true, y_pred)
print(f"F1-Score do modelo: {valor_f1:.4f}")

# No contexto de múltiplas classes (como no GTZAN)
# f1_macro = f1_score(y_true, y_pred, average='macro')

# Visualização com Yellowbrick para comparar F1 entre classes
visualizer = ClassificationReport(modelo, classes=['Classe_0', 'Classe_1'])
visualizer.fit(X_train, y_train)
visualizer.score(X_test, y_test)
visualizer.show()
```

````