---
banner: "![[Pasted image 20260215205950.png]]"
---
---

````ad-quote
title:

##### **Intro )** - Imputação por Média e Mediana

```ad-quote
title:
<p align="justify">A imputação por média e mediana é uma técnica de preenchimento de valores ausentes que utiliza a tendência central dos dados observados. Esta abordagem visa manter a integridade do dataset para algoritmos que não suportam entradas nulas, exigindo cautela para não distorcer as propriedades estatísticas originais.</p>
```

````

>[!quote] **Link:** [Numerical - Mean Median](https://feature-engine.trainindata.com/en/1.8.x/user_guide/imputation/MeanMedianImputer.html)

---

```ad-done
title:

#### **Fase 1 ) - Caso Ideal**

```

---

````ad-quote
title:

##### **01 )** - Premissas e Contexto Teórico

```ad-quote
title:
<p align="justify">Para que a substituição univariada seja válida, o analista deve garantir que a natureza da "falta" e o tipo de variável permitam tal operação sem comprometer a análise.</p>
```

```ad-quote
title:
|**Requisito**|**Descrição Técnica**|**Restrição Aplicada**|
|---|---|---|
|**Tipo de Dado**|A técnica é exclusiva para variáveis quantitativas (numéricas).|Inaplicável a dados categóricos nominais.|
|**Mecanismo MCAR**|Os dados devem ser Missing Completely at Random (totalmente ao acaso).|Se houver padrão na falta (MAR/MNAR), haverá viés.|
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Cenário Ideal de Aplicação

```ad-quote
title:
<p align="justify">Embora existam técnicas mais sofisticadas (como KNN ou MICE), a imputação por média ou mediana permanece como a escolha ótima em situações específicas onde o equilíbrio entre custo computacional e precisão estatística é necessário.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Baixo Volume de Ausência
```

```ad-quote
title:
<p align="justify">A técnica brilha quando a proporção de dados faltantes é pequena (geralmente inferior a 5%). Nesse limiar, a distorção causada na variância e nas correlações é estatisticamente desprezível para a maioria dos modelos preditivos robustos.</p>
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Necessidade de Baseline - MVP
```

```ad-quote
title:
<p align="justify">No início de um projeto de Data Science, o objetivo é estabelecer uma métrica de referência rapidamente. Esta técnica permite criar um modelo funcional (MVP) sem complexidade de engenharia, servindo de base para comparar ganhos futuros com métodos mais complexos.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Restrições de Produção - Baixa Latência
```

```ad-quote
title:
<p align="justify">Em sistemas de tempo real onde a velocidade de inferência é crítica, métodos complexos podem ser inviáveis. A média ou mediana é apenas um valor escalar armazenado na memória. A substituição ocorre em tempo constante $O(1)$, enquanto métodos como KNN exigiriam cálculos pesados de distância no momento da predição.</p>
```
````

---

```ad-done
title:

#### **Fase 2 ) - Características da Técnica**

```

---

````ad-quote
title:

##### **03 )** - Impactos Estatísticos Completos

```ad-quote
title:
<p align="justify">A imputação univariada não afeta apenas a dispersão e a relação entre variáveis. Ela altera fundamentalmente a geometria da densidade de probabilidade e pode introduzir erros sistemáticos se as premissas não forem perfeitas.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Encolhimento da Variância
```

```ad-quote
title:
Ao preencher as lacunas com um único valor repetido, a dispersão dos dados em torno do centro diminui drasticamente.
```

```ad-quote
title:
A curva de distribuição torna-se artificialmente mais estreita. Isso gera uma falsa sensação de precisão, levando o modelo a subestimar a incerteza e os riscos associados àquelas observações.
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Diluição de Correlações
```

```ad-quote
title:
A covariância natural entre as variáveis é quebrada, pois os valores imputados permanecem estáticos enquanto as outras variáveis continuam variando.
```

```ad-quote
title:
A força da relação linear entre preditores enfraquece. O algoritmo pode deixar de identificar padrões importantes, pois a pista que uma variável fornecia sobre a outra se perde no ruído gerado pelos valores constantes.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Distorção da Forma - Curtose
```

```ad-quote
title:
Ocorre um acúmulo excessivo de observações exatamente no ponto da média ou mediana, criando um pico artificial no histograma.
```



```ad-quote
title:
A distribuição torna-se leptocúrtica (pontiaguda). Isso viola a premissa de normalidade exigida por muitos testes estatísticos e modelos paramétricos, invalidando intervalos de confiança e testes de hipótese.
```
````

````ad-quote
title:
```ad-quote
title:
###### D ) Introdução de Viés - Bias
```

```ad-quote
title:
O método assume que os dados faltantes são idênticos, em média, aos dados observados.
```

```ad-quote
title:
Se a ausência do dado estiver relacionada ao próprio valor (ex: pessoas mais ricas não revelam salário), a imputação pela média observada deslocará o centro da distribuição para baixo. O modelo aprenderá uma realidade distorcida, gerando erros sistemáticos nas previsões.
```
````

---

```ad-done
title:

#### **Fase 3 ) - Particularidade do Método**

```

---

````ad-quote
title:

##### **04 )** - Métrica de Impacto - Distribuição de Probabilidade

```ad-quote
title:
<p align="justify">A escolha entre utilizar a média ou a mediana está diretamente ligada a curva de probabilidade associada a coluna de dados em questão.</p>
```

![[Pasted image 20260122201801.png]]
````

````ad-quote
title:

```ad-quote
title:
###### A ) Curva Normal - Média Aritmética
```

```ad-quote
title:
Indicada para distribuições simétricas ou normais. Considera todos os valores da amostra como centro de gravidade, mas é altamente sensível a extremos.
```

```ad-quote
title:
- $$\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i$$
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Curva Assimétrica - Mediana
```

```ad-quote
title:
Indicada para distribuições assimétricas ou com muitos outliers. Representa o valor central que divide a amostra, ignorando a magnitude das extremidades.
```

```ad-quote
title:
- $$Md = \begin{cases} x_{(\frac{n+1}{2})} & \text{se } n \text{ é ímpar} \\ \frac{x_{(\frac{n}{2})} + x_{(\frac{n}{2} + 1)}}{2} & \text{se } n \text{ é par} \end{cases}$$
```
````

---

```ad-done
title:

#### **Fase 4 ) - Implementação da Técnica**

```

---

````ad-quote
title:
```ad-quote
title:  
**Py ) Código em Python**
```

```python
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split

# 1. Geração do Dataset
data = {
    'Renda': [5000, 6200, np.nan, 4800, 15000, np.nan, 5200, 5800, 22000, 6000],
    'Idade': [25, 30, 45, np.nan, 50, 32, np.nan, 28, 60, 29],
    'Target': [0, 0, 1, 0, 1, 1, 0, 0, 1, 0]
}
df = pd.DataFrame(data)
X = df[['Renda', 'Idade']]
y = df['Target']
```

```python
# 2. Separação (Anti-Leakage)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# --- INÍCIO DO TRATAMENTO MANUAL ---

# 3. Criação da Coluna Indicadora (Missing Indicator)
# Deve ser feito antes da imputação para capturar onde estão os nulos.
# O sufixo .astype(int) converte True/False para 1/0.
cols_to_impute = ['Renda', 'Idade']

for col in cols_to_impute:
    X_train[f'{col}_is_missing'] = X_train[col].isna().astype(int)
    X_test[f'{col}_is_missing'] = X_test[col].isna().astype(int)

# 4. Cálculo da Estatística (Fit)
# Calculamos a mediana APENAS no set de treino.
# O resultado é uma Series contendo a mediana para cada coluna.
medianas_do_treino = X_train[cols_to_impute].median()

print(f"Medianas aprendidas:\n{medianas_do_treino}\n")

# 5. Aplicação da Imputação (Transform)
# Usamos o método fillna passando as medianas calculadas no passo anterior.
# O Pandas alinha automaticamente as colunas pelo nome.
X_train_filled = X_train.fillna(medianas_do_treino)
X_test_filled = X_test.fillna(medianas_do_treino) # CRÍTICO: Usar mediana do treino aqui

# --- VERIFICAÇÃO ---
print("=== Set de Treino Tratado (Amostra) ===")
print(X_train_filled.head(3))
print("\n=== Set de Teste Tratado (Amostra) ===")
print(X_test_filled.head(3))
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Prevenção de Data Leakage
```

```ad-quote
title:
<p align="justify">No desenvolvimento de modelos, a imputação deve seguir rigorosos protocolos para evitar o vazamento de informações do teste para o treino.</p>
```

```ad-quote
title:
Observe que a variável `medianas_do_treino` foi derivada exclusivamente de `X_train`. Ao aplicar o método `.fillna()` no `X_test`, passamos essa mesma variável. Isso garante que nunca olhamos para a distribuição do teste para preencher os buracos, simulando corretamente a realidade de produção.
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Coluna Indicadora
```

```ad-quote
title:  
Técnica de criar uma variável booleana para informar ao modelo quais valores foram originalmente imputados.
```

```ad-quote
title:
A lógica `isna().astype(int)` cria manualmente as flags binárias. É crucial executar este passo antes da imputação, caso contrário, os nulos desapareceriam e perderíamos a informação de que aquele dado era originalmente ausente.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Alinhamento de Índices
```

```ad-quote
title:  
Utilização de ferramentas como o SimpleImputer para automatizar o fluxo de pré-processamento dentro da validação cruzada.
```

```ad-quote
title:
Uma vantagem do Pandas é que, ao passar uma Série (resultado do `.median()`) para o `.fillna()`, ele mapeia os valores usando o nome das colunas. Isso evita erros de preencher a coluna Idade com a média da coluna Renda, garantindo integridade na transformação.
```
````

---