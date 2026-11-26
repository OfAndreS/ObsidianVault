---
banner: "![[Pasted image 20260215205950.png]]"
---
---

````ad-quote
title:
##### **01 ) -** Variáveis Numéricas / Quantitativas

```ad-quote
title:
Também conhecidas como variáveis quantitativas, representam valores que descrevem uma _magnitude_ mensurável. A principal característica que as define é a capacidade de realizar operações aritméticas lógicas com elas. Calcular a média de uma idade faz sentido; calcular a média de números de telefone, não.
```
````

````ad-quote
title:
##### _Subdivisões_

```ad-quote
title:
###### A ) Discretas
```

```ad-quote
title:
<p align="justify">São valores finitos ou contáveis, geralmente resultantes de um processo de contagem. Entre dois valores consecutivos, não existe um valor intermediário válido.</p>
```

```bash
# Exemplo:

# [Número de acessos a um servidor, quantidade de itens no estoque, número de filhos] (Não é possível ter 2,5 filhos).
```

```ad-quote
title:
###### B ) Contínuas
```

```ad-quote
title:
<p align="justify">São valores que podem assumir qualquer ponto numérico dentro de um intervalo, incluindo frações infinitesimais. Geralmente resultam de medições físicas ou temporais.</p>
```

```bash
# Exemplo:

# [Voltagem de um sensor, peso de uma carga, tempo de latência de uma requisição]
```

````

````ad-quote
title:
##### _Principais Problemas_

```ad-quote
title:
###### A ) Escalas Desproporcionais
```

```ad-quote
title:
<p align="justify">Este é o problema mais comum em algoritmos baseados em distância (como KNN ou K-Means) e em redes neurais. Se uma variável varia de 0 a 1 (ex: taxa de erro) e outra de 1.000 a 100.000 (ex: salário), o modelo dará um peso excessivo à variável de maior magnitude apenas porque os números são maiores, não porque ela é mais importante.</p>
```

```ad-quote
title:
###### B ) Outliers - Valores Atípicos
```

```ad-quote
title:
<p align="justify">Valores numéricos extremos que se desviam drasticamente da média podem distorcer completamente o treinamento do modelo. Em uma regressão linear, por exemplo, um único outlier pode puxar a linha de tendência para longe do padrão real dos dados.</p>
```

```ad-quote
title:
###### C ) Distribuição Assimétrica - Skewness
```

```ad-quote
title:
<p align="justify">Muitos modelos estatísticos assumem que os dados numéricos seguem uma distribuição normal (curva de sino). Dados financeiros ou de tempo de espera, por exemplo, costumam ter uma cauda longa à direita (muitos valores baixos e poucos valores extremamente altos), o que pode reduzir a performance preditiva.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **02 ) -** Variáveis Categóricas / Qualitativas

```ad-quote
title:
Também chamadas de qualitativas, descrevem características, rótulos ou qualidades de uma observação. Elas dividem os dados em grupos ou _baldes_. Mesmo que venham representadas como números no banco de dados, esses números não possuem valor matemático de quantidade, funcionando apenas como _etiquetas_.
`````

````ad-quote
title:
##### _Subdivisões_

```ad-quote
title:
###### A ) Nominais
```

```ad-quote
title:
<p align="justify">Não existe nenhuma ordem ou hierarquia inerente entre as categorias. Nenhuma é _maior_ ou _melhor_ que a outra dentro do conjunto de dados analisado.</p>
```

```bash
# Exemplo:

# [Sistemas Operacionais (Linux, Windows, macOS), Cores, Países]
```

```ad-quote
title:
###### B ) Ordinais
```

```ad-quote
title:
<p align="justify">Existe uma ordem lógica e sequencial clara entre as categorias, embora a distância matemática entre elas não seja necessariamente quantificável.</p>
```

```bash
# Exemplo:

# [Nível de escolaridade (Fundamental, Médio, Superior), Estágio do câncer (I, II, III, IV), Avaliação de satisfação]
```

```ad-quote
title:
###### C ) Binárias 
```

```ad-quote
title:
<p align="justify">Um caso especial onde existem apenas duas categorias possíveis para a observação ou variável.</p>
```

```bash
# Exemplo:

# [Spam/Não Spam, Aprovado/Reprovado, 0/1]
```

`````

````ad-quote
title:
##### _Principais Problemas_

```ad-quote
title:
###### A ) Alta Cardinalidade
```

```ad-quote
title:
<p align="justify">Ocorre quando uma variável possui um número excessivo de valores únicos. O uso de técnicas como _One-Hot Encoding_ pode expandir o dataset excessivamente, gerando o problema da _dimensionalidade esparsa_ e lentidão no processamento.</p>
```

```ad-quote
title:
###### B ) Rótulos Raros
```

```ad-quote
title:
<p align="justify">Categorias com baixíssima frequência que podem causar _overfitting_. O modelo pode aprender regras específicas demais para casos isolados. Geralmente, agrupa-se esses valores em uma categoria genérica denominada _Outros_.</p>
```

```ad-quote
title:
###### C ) Inconsistência de Texto
```

```ad-quote
title:
<p align="justify">Devido à entrada humana, variações como _São Paulo_ e _SP_ podem ser interpretadas como categorias distintas. Isso demanda uma _limpeza rigorosa_ de strings antes da fase de modelagem estatística.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 ) -** Python Code

```ad-quote
title:

<p align="justify">É possível determinar automaticamente se uma variável é categórica ou numérica com base no seu tipo de dado e comportamento.</p>

```

```python
import pandas as pd
from pandas.api.types import is_numeric_dtype

def var_type_classification(serie: pd.Series) -> str:
    serie_clean = serie.dropna()
    
    if len(serie_clean) == 0:
        return 'Vazia'
        
    if not is_numeric_dtype(serie_clean):
        return 'Cat'
        
    if (serie_clean % 1 != 0).any():
        return 'Con'
        
    qtd_unicos = len(serie_clean.unique())
    proporcao_unicos = qtd_unicos / len(serie_clean)
    
    if proporcao_unicos > 0.05 and qtd_unicos > 20:
        return 'Con'
    else:
        return 'Dis'
```

```python
list_type_cols = {col: var_type_classification(df_penguins[col]) for col in df_penguins.columns}

for col, type in list_type_cols.items():
	print(f"Col: {col:<15} | Type: {type}")
```
````


---
