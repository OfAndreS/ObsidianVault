---
banner: "![[Pasted image 20251228125302.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Guia das Métricas de Regressão

```ad-quote
title:
<p align="justify">A avaliação de modelos de regressão exige um conjunto de métricas que validam tanto a precisão quanto a consistência estatística dos resultados obtidos. Enquanto o coeficiente de correlação mede o vínculo inicial entre variáveis, o _R²_ e o _R² Ajustado_ determinam a proporção da variância explicada e a eficiência da complexidade aplicada. Complementarmente, a _Estatística F_ surge como um critério de decisão para comparar modelos e verificar se a melhoria no ajuste é genuína ou fruto do acaso. Essas ferramentas permitem identificar se os padrões capturados representam a realidade dos dados ou apenas ruído aleatório. Integrar essas análises é o que garante a construção de modelos preditivos robustos, parcimoniosos e cientificamente fundamentados.</p>
```

```ad-quote
title:
|**Métrica**|**Pergunta Principal**|**Uso Prático**|
|---|---|---|
|**R**|Existe relação entre as variáveis?|Análise exploratória inicial.|
|**R²**|Quão preciso é o ajuste do modelo?|Medir desempenho preditivo bruto.|
|**R² Ajustado**|A complexidade do modelo é justificada?|Comparar modelos multivariados.|
|**Estatística F**|O modelo é estatisticamente válido?|Confirmar que os resultados não são obra do acaso.|
```

````

---

> [!done] _New_

---

````ad-quote
title:

##### **01 )** - Descrição da Métrica R

```ad-quote
title:
<p align="justify">O R, especificamente o "Coeficiente de Pearson", quantifica a Forca e Direcao da Relação Linear entre duas variáveis. É o alicerce para entender a dependência entre AtributosPreditores e o Alvo.</p>
```

![[Pasted image 20260102162032.png]]

````

````ad-quote
title:

```ad-quote
title:
###### A ) Atributos do R
```

```ad-quote
title:
|**Aspecto**|**Descrição Detalhada**|**Impacto na Análise**|
|---|---|---|
|**Intervalo**|O valor de R transita estritamente entre -1 e 1.|Define o Limite Matemático da medida.|
|**Direção**|Valores positivos indicam que as variáveis crescem juntas, enquanto valores negativos indicam uma Relação Inversa.|Determina a Tendência Do Relacionamento.|
|**Intensidade**|A proximidade de 1 ou -1 indica uma Correlação Forte. O valor 0 indica Ausência De Linearidade.|Mede a Força Do Vínculo entre as variáveis.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação Matemática
```

```ad-quote
title:
<p align="justify">No nível teórico, a correlação ρ representa a normalização da Covariância pelo Produto Dos Desvios Padrão. Isso nos dá uma medida Adimensional da dependência linear entre duas distribuições.</p>
```

```ad-quote
title:
- $$r = \rho_{X,Y} = \frac{Cov(X, Y)}{\sigma_X \sigma_Y}$$
```

```ad-quote
title:
<p align="justify">Quando temos apenas um Conjunto De Dados limitado, utilizamos a fórmula abaixo para estimar esse valor. O numerador calcula a Co-Variação dos pontos, enquanto o denominador atua como um Fator De Escala que limita o resultado ao intervalo entre -1 e 1.</p>
```

```ad-quote
title:
- $$r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Código em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`stats.pearsonr`|Algoritmo que aplica a Razão Da Covariância sobre os dados fornecidos.|Facilita a Transposição Teórica para o ambiente computacional.|
|`r`|Indicador da Força Da Relação entre as variáveis analisadas.|Define se a Conexão Linear é fraca, moderada ou intensa.|
|`pValor`|Métrica de probabilidade de o resultado ser fruto do Acaso.|Serve como critério de Confiança para validar a Correlação Significativa.|

```

```python
from scipy import stats

# Exemplo: Existe relação entre tempo de estudo e desempenho?
r, pValor = stats.pearsonr(horasDeEstudo, notasDoAluno)

print(f"Coeficiente de Correlação (r): {r}")
print(f"Significância (p-value): {pValor}")
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 )** - Descrição da Métrica R²
```ad-quote
title:
<p align="justify">Quantificamos a Precisão Do Modelo comparando o que foi previsto com o que realmente aconteceu. Essa análise permite entender o Erro Acumulado e a Eficiência Da Regressão em capturar a Variabilidade Dos Dados.</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Atributos das Somas Quadráticas
```

```ad-quote
title:
|**Métrica**|**Descrição Detalhada**|**Papel Na Avaliação**|
|---|---|---|
|**SSres**|Soma Dos Quadrados Dos Resíduos que mede a Diferença Quadrática entre predição e real.|Mede o Erro Não Explicado pelo modelo.|
|**SStot**|Soma Total Dos Quadrados baseada na Variabilidade Natural em torno da média.|Estabelece a Base De Comparação teórica.|
|**R²**|Veredito Final que indica a Porcentagem De Variância capturada.|Define a Qualidade Global Do Ajuste.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação Matemática
```

```ad-quote
title:
<p align="justify">O cálculo do Erro Acumulado foca na distância entre os pontos observados e a reta de regressão. Já a variabilidade total foca na distância dos pontos para a média global.</p>
```

```ad-quote
title:
- $$SS_{res} = \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$
- $$SS_{tot} = \sum_{i=1}^{n} (y_i - \bar{y})^2$$
```

```ad-quote
title:
<p align="justify">A Identidade Do Coeficiente De Determinação é obtida pela razão entre o erro do modelo e a variabilidade total, subtraída da unidade para expressar a Precisão Relativa.</p>
```

```ad-quote
title:
- $$R^2 = 1 - \frac{SS_{res}}{SS_{tot}}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Código em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`r2_score`|Função da biblioteca Sklearn que quantifica a Variância Explicada.|Avalia a Qualidade Global Do Ajuste do modelo aos dados.|
|`y_real`|Vetor contendo os valores observados experimentalmente.|Fornece a Referência Real para o cálculo do erro.|
|`y_pred`|Vetor com as estimativas geradas pelo Modelo De Regressão.|Representa o Desempenho Preditivo que será validado.|

```

```python
from sklearn.metrics import r2_score

# Calculando o Coeficiente de Determinação (R²)
# y_real: valores verdadeiros | y_pred: valores preditos
valor_r2 = r2_score(y_real, y_pred)

print(f"Coeficiente de Determinação (R²): {valor_r2:.4f}")
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **03 )** - Descrição da Métrica R² Ajustado

```ad-quote
title:
<p align="justify">Esta métrica corrige a Deficiência Do R² original ao aplicar uma Penalização baseada no número de Preditores em relação ao Tamanho Da Amostra. É fundamental para evitar o Overfitting em modelos complexos.</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Lógica de Relevância
```

```ad-quote
title:
|**Conceito**|**Mecanismo de Ação**|**Impacto na Modelagem**|
|---|---|---|
|**Inclusão de Variável**|O valor só aumenta se a nova variável trouxer Melhoria Real acima do acaso.|Protege a Parcimônia Do Modelo.|
|**Variável Irrelevante**|Se o novo atributo for ruído, o valor do ajuste cairá automaticamente.|Evita a Inflação Artificial Da Precisão.|
|**Graus de Liberdade**|Leva em conta o Número De Variáveis e o Total De Observações.|Gera uma Estimativa Mais Conservadora.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Equação com Graus de Liberdade
```

```ad-quote
title:
<p align="justify">A formulação matemática ajusta o R² multiplicando o erro residual pela proporção dos Graus De Liberdade do sistema, garantindo que o modelo não seja premiado apenas por adicionar complexidade.</p>
```

```ad-quote
title:
- $$\bar{R}^2 = 1 - \left[ \frac{(1 - R^2)(n - 1)}{n - k - 1} \right]$$
```

```ad-quote
title:
Onde n representa o Tamanho Da Amostra e k representa o Número De Variáveis independentes.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Código em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`n`|Variável que armazena o número total de observações.|Representa o Tamanho Da Amostra disponível.|
|`k`|Variável que define a quantidade de preditores independentes.|Indica o Grau De Complexidade da estrutura do modelo.|
|`r2_adj`|Resultado da aplicação da fórmula de correção sobre o R².|Gera uma métrica de Precisão Realista para modelos multivariados.|

```

```python
import numpy as np

# n = número de amostras | k = número de variáveis preditoras
n = len(y_real)
k = 3  # Exemplo hipotético de preditores

# Cálculo manual baseado na fórmula estatística
r2_adj = 1 - ((1 - valor_r2) * (n - 1) / (n - k - 1))

print(f"R² Ajustado: {r2_adj:.4f}")
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **04 )** - Descrição da Estatística F (F-Test)

```ad-quote
title:
<p align="justify">A Estatística F funciona como um Juiz Final para o modelo. Enquanto o R² indica quanto da variância foi explicada, o Teste F determina se essa explicação é Estatisticamente Significativa, comparando modelos de diferentes complexidades.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Lógica de Comparação
```

```ad-quote
title:
|**Conceito**|**Mecanismo de Ação**|**Impacto na Análise**|
|---|---|---|
|**Modelo Simples vs. Fit**|Compara o modelo atual contra um modelo que contém apenas a média.|Valida se o modelo é melhor do que um palpite nulo.|
|**Modelos Aninhados**|Avalia se adicionar novas variáveis (modelo múltiplo) melhora o ajuste significativamente.|Decide se a complexidade extra é justificada.|
|**Razão de Variância**|Mede a razão entre a Variância Explicada e a Variância Residual.|Gera o valor F para comparação com a Distribuição F.|
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação Matemática
```

```ad-quote
title:
<p align="justify">Para comparar um modelo ajustado contra a média simples, utilizamos a redução na Soma Dos Quadrados dividida pelos Graus De Liberdade.</p>
```

```ad-quote
title:
- $$F = \frac{(SS_{mean} - SS_{fit}) / (p_{fit} - p_{mean})}{SS_{fit} / (n - p_{fit})}$$
```

```ad-quote
title:
<p align="justify">No caso de Modelos Aninhados, testamos se o modelo mais complexo (múltiplo) reduz o erro de forma mais eficiente que o modelo restrito (simples).</p>
```

```ad-quote
title:
- $$F = \frac{(SS_{simple} - SS_{multiple}) / (p_{multiple} - p_{simple})}{SS_{multiple} / (n - p_{multiple})}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Código em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel Na Estatística**|
|---|---|---|
|`f_pvalue`|Probabilidade associada à estatística F calculada.|Se for menor que 0.05, indica que o modelo é significativo.|
|`f_statistic`|O valor bruto da razão de variância do modelo.|Indica a força da evidência contra a hipótese nula.|

```

```python
import statsmodels.api as sm

# Utilizando statsmodels para obter o F-Test completo
X = sm.add_constant(horasDeEstudo) # Adiciona intercepto
modelo = sm.OLS(notasDoAluno, X).fit()

print(f"Estatística F: {modelo.fvalue}")
print(f"P-valor do Teste F: {modelo.f_pvalue}")
```

```python
from sklearn.feature_selection import f_regression
from sklearn.metrics import mean_squared_error

# 1. Teste F Univariado (Significância individual de cada variável)
f_stats, p_values = f_regression(X, y)

# 2. Base para Teste de Modelos Aninhados (Manual)
# Treina-se o modelo e extrai o erro para calcular o SS(multiple)
y_pred = modelo.predict(X_test)
mse = mean_squared_error(y_test, y_pred)
ss_multiple = mse * len(y_test)

print(f"F-Statistics individuais: {f_stats}")
print(f"P-valores individuais: {p_values}")
```

````

---



