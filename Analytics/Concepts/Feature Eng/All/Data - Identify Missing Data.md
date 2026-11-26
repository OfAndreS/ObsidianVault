---
banner: "![[Pasted image 20260215205950.png]]"
---

---

```ad-done
title:
#### Fase 1 ) - Inspeção Visual Espacial
```

---

````ad-quote
title:
##### **01 ) -** O Alvo - A Integridade Estrutural do Dataset

```ad-quote
title:
<p align="justify">Estrutura do banco de dados.</p>
```

```ad-quote
title:
<p align="justify">Diferente de testes estatísticos que miram nas médias ou variâncias, a Matriz de Nulidade mira no processo de coleta. Ela analisa a relação entre a posição do dado e sua existência. Ao trabalhar com modelos de Credit Risk, o alvo seria identificar, por exemplo, se todos os clientes de uma determinada região ou safra possuem os mesmos campos vazios, o que invalidaria a generalização do seu modelo para esse grupo.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **02 ) -** Método - Visualização de Matriz Binária

```ad-quote
title:
<p align="justify">O método consiste em converter todo o seu Dataframe em um mapa de pixels.</p>
```

![[Pasted image 20260116215830.png]]

````

````ad-quote
title:

```ad-quote
title:
###### A ) Como funciona
```

```ad-quote
title:
<p align="justify">Para cada célula do seu conjunto de dados, o algoritmo atribui uma cor (geralmente cinza escuro ou preto) se o dado estiver presente e uma cor diferente (branco) se o dado for nulo NaN.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Representação
```

```ad-quote
title:
<p align="justify">O eixo horizontal representa as colunas (variáveis) e o eixo vertical representa o índice (geralmente as linhas ou o tempo).</p>
```
````

````ad-quote
title: 

```ad-quote
title:
###### C ) Sparkline
```

```ad-quote
title:
<p align="justify">No lado direito da matriz, costuma haver uma linha que resume a contagem de dados preenchidos por linha, ajudando a identificar rapidamente quais registros estão quase vazios.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **03 ) -** Objetivo - Identificar Padrões Espaciais de Nulidade

```ad-quote
title:
<p align="justify">O objetivo principal não é apenas contar quantos nulos existem (isso um df.isnull().sum() resolveria), mas sim entender a distribuição e a correlação visual dessas ausências. Através desse método, buscamos:</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Detectar falhas sistêmicas
```

```ad-quote
title:
<p align="justify">Identificar se os dados faltantes ocorrem em "blocos". Se você vir uma faixa branca horizontal que atravessa várias colunas, isso indica que para aquele registro específico (ou período de tempo), o sistema de coleta falhou totalmente.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Identificar padrões temporais
```

```ad-quote
title:
<p align="justify">Em séries temporais, a matriz revela se os dados começaram a faltar a partir de uma data específica (indicando uma mudança de sensor ou regra de negócio).</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Avaliar a aleatoriedade visual
```

```ad-quote
title:
<p align="justify">Se os "buracos" brancos estiverem espalhados de forma homogênea como ruído, há uma indicação visual de MCAR (Missing Completely at Random). Se estiverem concentrados, o dado provavelmente é MAR ou MNAR.</p>
```
````

---

```ad-done
title:
#### Fase 2 ) - Análise de Correlação de Nulidade
```

---

````ad-quote
title:
##### **01 ) -** O Alvo - A Relação de Interdependência entre Colunas

```ad-quote
title:
<p align="justify">O alvo desta técnica não são os valores das variáveis em si (como o Peso ou a Altura), mas sim o padrão de ocorrência das lacunas.</p>
```

```ad-quote
title:
<p align="justify">O foco recai nas variáveis incompletas, mirando especificamente nos pares de colunas que apresentam algum grau de nulidade. Como alvo secundário, temos o diagnóstico do pipeline e do próprio sistema de coleta de dados. Uma correlação inesperada pode apontar para um erro no software de extração ou em um sensor específico que falha sempre que outro entra em atividade.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **02 ) -** Método - Coeficiente de Correlação de Máscaras Binárias

```ad-quote
title:
<p align="justify">O método consiste em transformar o seu dataframe original em uma matriz booleana. Nesta matriz, cada célula recebe o valor 1 se o dado for nulo (NaN) e o valor 0 se o dado estiver presente.</p>
```



````

````ad-quote
title:

```ad-quote
title:
###### A ) Lógica Matemática
```

```ad-quote
title:
A partir dessa transformação, calculamos o coeficiente de correlação (geralmente de Pearson) entre as colunas dessa nova matriz. Se $M_x$ e $M_y$ são as variáveis indicadoras de nulidade para as colunas $X$ e $Y$, buscamos o valor de correlação:
```

```ad-quote
title:
- $$\rho_{M_x, M_y} = \frac{\text{cov}(M_x, M_y)}{\sigma_{M_x} \sigma_{M_y}}$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **03 ) -** Objetivo - Identificar Dependências de Ausência

```ad-quote
title:
<p align="justify">O grande objetivo é descobrir se a falta de uma informação carrega um significado sobre a falta de outra. Isso permite distinguir mecanismos de perda de dados nas seguintes frentes:</p>
```

![[Pasted image 20260116215929.png]]

````

````ad-quote
title:

```ad-quote
title:
###### A ) Detectar Sincronia
```

```ad-quote
title:
<p align="justify">Se a correlação entre duas variáveis for próxima de 1, isso prova que quando um dado falta na coluna A, ele também faltará na coluna B. Isso é um indicativo fortíssimo de que o dado não é MCAR (Totalmente Aleatório), mas sim resultado de um processo estruturado, como uma seção de um formulário que foi pulada por um perfil específico de usuário.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Eliminar Ruído
```

```ad-quote
title:
<p align="justify">Se as correlações forem próximas de 0, os eventos de perda de dados são independentes, o que simplifica o uso de técnicas de imputação em modelos de Machine Learning.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **04 ) -** Cuidados Técnicos e Limitações

```ad-quote
title:
<p align="justify">Apesar de ser uma ferramenta poderosa, a Análise de Correlação de Nulidade possui limitações intrínsecas que exigem atenção extra para não gerar falsas interpretações.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) O Ponto Cego das Variáveis Completas
```

```ad-quote
title:
<p align="justify">Este é o cuidado técnico mais importante. Ferramentas como o heatmap do missingno costumam filtrar e esconder colunas que não possuem nenhum dado faltante. No entanto, a definição de MAR (Missing at Random) é justamente quando uma variável completa explica a ausência de outra. Se você olhar apenas para o mapa de correlação, poderá concluir que a falta é aleatória quando, na verdade, ela depende de uma variável que não está aparecendo no gráfico por estar 100% preenchida.</p>
```



````

````ad-quote
title:

```ad-quote
title:
###### B ) A Armadilha do Baixo Volume (Ruído Estatístico)
```

```ad-quote
title:
<p align="justify">Para que uma correlação seja confiável, é necessária uma massa crítica de dados faltantes. Se o seu dataframe possui 10.000 linhas, mas apenas 5 delas têm dados nulos nas colunas A e B, a correlação pode aparecer como 1 (perfeita) apenas por coincidência. Sempre verifique a contagem absoluta de nulos antes de dar peso à correlação. Em amostras pequenas, o coeficiente de correlação é extremamente sensível a outliers.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Correlação não é Causalidade de Nulidade
```

```ad-quote
title:
<p align="justify">Ver que a Variável A e a Variável B faltam juntas não diz por que elas faltam. Pode ser uma falha de software onde o sistema trava e não grava os últimos campos de um formulário. Também pode ser um comportamento do usuário: em modelos de Credit Risk, um cliente que se recusa a declarar o Patrimônio Total frequentemente também se recusará a declarar a Renda Mensal. A correlação é alta, mas a causa é o perfil do respondente (MNAR), e não um erro técnico.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) A Natureza Binária do Teste
```

```ad-quote
title:
<p align="justify">A correlação de nulidade ignora os valores dos dados. Ela apenas olha para a existência ou ausência da informação. Isso significa que ela pode identificar padrões entre colunas, mas falha totalmente em detectar se a falta depende do próprio valor que deveria estar lá. Se pessoas com salários altos escondem a renda, a correlação de nulidade entre Renda e outras colunas pode ser baixa, escondendo um viés de MNAR perigoso para seus modelos de Machine Learning.</p>
```
````

---

```ad-done
title:
#### Fase 3 ) - Teste de Independência por Grupos - Busca por MAR
```

---

````ad-quote
title:
##### **01 ) -** O Alvo - A Distribuição da Variável Indicadora

```ad-quote
title:
<p align="justify">O foco analítico reside na verificação de se a probabilidade de um dado estar ausente em uma coluna específica apresenta correlação estatística com os valores observados em outras variáveis independentes do conjunto de dados. O alvo é a distribuição da variável indicadora de nulidade em relação às variáveis completas.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **02 ) -** Método - Segregação e Comparação de Grupos

```ad-quote
title:
<p align="justify">O procedimento fundamenta-se na segregação da amostra em dois grupos mutuamente exclusivos baseados na coluna incompleta: o Grupo de Presença (dados existentes) e o Grupo de Ausência (dados faltantes).</p>
```

````

````ad-quote
title:

```ad-quote
title:
###### A ) Codificação e Seleção
```

```ad-quote
title:
<p align="justify">Inicia-se com a codificação de uma variável indicadora binária (dummy) para a coluna alvo. Em seguida, faz-se a seleção de uma variável auxiliar que esteja integralmente preenchida na base de dados.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Aplicação de Testes Estatísticos
```

```ad-quote
title:
<p align="justify">Aplica-se testes de comparação de distribuições entre os dois grupos. O Teste T de Student é utilizado para variáveis com distribuição normal e variâncias homogêneas. O Teste de Mann-Whitney U é utilizado como alternativa não-paramétrica quando a normalidade dos dados não pode ser assumida. Por fim, o Teste Qui-Quadrado é aplicado quando a variável auxiliar é categórica.</p>
```



````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **03 ) -** Objetivo - Diagnosticar o Mecanismo MAR

```ad-quote
title:
<p align="justify">O propósito técnico é diagnosticar o mecanismo de ausência do tipo Missing at Random (MAR). Ao comprovar que a falta de informação pode ser explicada ou prevista por outras variáveis conhecidas, o analista obtém a fundamentação necessária para aplicar métodos de Imputação Condicional (como MICE ou K-NN) em vez da exclusão simples de registros, o que preserva o poder estatístico da amostra e reduz o viés sistemático.</p>
```



````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **04 ) -** Pontos de Atenção!

```ad-quote
title:
<p align="justify">Este estágio da análise estatística é fundamental para validar a integridade de modelos de Machine Learning e processamento de dados, especialmente em contextos como análise de risco. Contudo, exige cuidados específicos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Violação de Assunções
```

```ad-quote
title:
<p align="justify">A aplicação de testes paramétricos em dados que não seguem uma distribuição normal ou que possuem variâncias heterogêneas pode levar a erros do tipo I ou II no diagnóstico do mecanismo.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) Poder Estatístico vs. Relevância Prática
```

```ad-quote
title:
<p align="justify">Em grandes volumes de dados, diferenças mínimas entre as médias podem resultar em um $p < 0,05$; portanto, é imperativo calcular o tamanho do efeito (como o D de Cohen) para medir a magnitude real da dependência.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) Complexidade Multivariada
```

```ad-quote
title:
<p align="justify">A análise bivariada pode falhar em detectar relações de dependência que só se manifestam através da interação de múltiplas variáveis. Em casos complexos, recomenda-se o uso de modelos de Regressão Logística para modelar a probabilidade de ausência.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### D ) Ocultação de MNAR
```

```ad-quote
title:
<p align="justify">A confirmação de um padrão MAR não garante a inexistência de MNAR (Missing Not at Random). Se o motivo da ausência for simultaneamente dependente de variáveis observadas e do próprio valor oculto, o tratamento exigirá modelos de seleção ainda mais robustos.</p>
```
````

---

## 4. Teste Global de Hipótese (Consistência de Médias)

- **Método**: Teste de Little (_Little's MCAR Test_).
    
- **Objetivo**: Validar estatisticamente se o dataset, como um todo, pode ser considerado _Missing Completely at Random_ (MCAR).
    
- **Alvo**: A estrutura global das médias de todos os padrões de resposta do dataset.
    
- _Lógica_: O alvo é a hipótese nula $H_0$ (os dados são _MCAR_). O método calcula a distância de Mahalanobis entre as médias de diferentes padrões de nulidade. Se o teste falhar (p-valor baixo), você sabe que seu conjunto de dados tem um viés que a simples exclusão de linhas não resolverá.
    

---

## 5. Análise de Sensibilidade e Modelagem de Seleção

- **Método**: Imputação por Padrões e Análise de Impacto (Delta-Adjustment).
    
- **Objetivo**: Identificar _Missing Not at Random_ (MNAR), onde o motivo da falta é o próprio valor que não foi registrado.
    
- **Alvo**: A estabilidade dos coeficientes do modelo final (como a sua _ResNet-18_ ou um modelo de crédito).
    

_O Processo:_ Como não podemos testar o que não vemos, o alvo aqui é o "pior cenário". Nós imputamos valores deliberadamente baixos e depois deliberadamente altos. Se a performance do seu modelo de crédito oscilar drasticamente entre esses cenários, você tem evidências de _MNAR_. O tratamento exigirá modelos mais complexos, como o de _Heckman_.

---

### Resumo Comparativo do Pipeline

|**Fase**|**Método Principal**|**Alvo do Teste**|**O que ele revela**|
|---|---|---|---|
|**Visual**|_Missingno Matrix_|Estrutura das linhas|Falhas sistêmicas (não-aleatórias)|
|**Relacional**|_Correlation Heatmap_|Relação entre nulos|Dependência entre variáveis|
|**Estatística**|_Mann-Whitney U_|Relação Nulo vs. Observado|Identifica o tipo _MAR_|
|**Global**|_Little's Test_|Dataset completo|Valida o tipo _MCAR_|
|**Analítica**|_Sensitivity Analysis_|Estabilidade do modelo|Identifica o risco de _MNAR_|

Como você mencionou que está trabalhando com modelos de _Deep Learning_ e áudio, a fase 1 e 3 são as mais cruciais para garantir que sua _ResNet_ não aprenda ruídos técnicos da coleta.

Gostaria que eu escrevesse um script em Python que execute a **Fase 3** (comparando as médias das suas variáveis de crédito para identificar o tipo MAR) de forma automática para todas as suas colunas?

---

````ad-quote
title:

```ad-quote
title:
###### Py 1 ) - Matriz de Nulidade
```

```Python
import missingno as msno
import matplotlib.pyplot as plt
import pandas as pd

def plot_nullity_matrix(df: pd.DataFrame):
    """
    Exibe a matriz de nulidade para identificar padrões visuais
    (listras ou blocos) em todo o dataset.
    """
    msno.matrix(df, fontsize=10)
    plt.title('Matriz de Nulidade: Visão Global', fontsize=16)
    plt.show()
```
````

---

````ad-quote
title:

```ad-quote
title:
###### Py 2 ) - Coeficiente de Correlação de Máscaras Binárias
```

```Python
import missingno as msno
import matplotlib.pyplot as plt
import pandas as pd

def plot_nullity_correlation(df: pd.DataFrame):
    """
    Exibe o mapa de calor que mostra se a presença de uma variável
    está correlacionada com a presença de outra (-1 a +1).
    """
    # O heatmap exige pelo menos 2 variáveis com nulos para funcionar
    msno.heatmap(df, cmap='RdBu', fontsize=10)
    plt.title('Correlação de Ausência (Dependência entre Colunas)', fontsize=16)
    plt.show()
```
````

---

````ad-quote
title:

```ad-quote
title:
###### Py 3 ) - Segregação e Comparação de Grupos
```

```python
import pandas as pd
import numpy as np
from scipy import stats

def diagnosticar_mar(df, col_alvo, cols_teste):
    """
    Realiza o teste de independência por grupos para identificar MAR.
    
    Parâmetros:
    df: DataFrame do pandas.
    col_alvo: A coluna que possui dados faltantes (alvo da investigação).
    cols_teste: Lista de colunas numéricas completas para testar a dependência.
    """
    resultados = []
    
    # Criando a variável indicadora (Máscara de Nulidade)
    # 0 = Dado Presente, 1 = Dado Faltante
    mask_faltante = df[col_alvo].isnull()
    
    for col in cols_teste:
        # Segmentação dos grupos
        grupo_presente = df.loc[~mask_faltante, col].dropna()
        grupo_faltante = df.loc[mask_faltante, col].dropna()
        
        # Verificação de tamanho mínimo para o teste
        if len(grupo_presente) < 3 or len(grupo_faltante) < 3:
            continue
            
        # Teste de Normalidade (Shapiro-Wilk) para escolher o método
        # Se p > 0.05, assume-se normalidade
        _, p_norm_pres = stats.shapiro(grupo_presente.sample(min(len(grupo_presente), 500)))
        _, p_norm_falt = stats.shapiro(grupo_faltante.sample(min(len(grupo_faltante), 500)))
        
        is_normal = p_norm_pres > 0.05 and p_norm_falt > 0.05
        
        if is_normal:
            # Teste T de Student (Paramétrico)
            t_stat, p_val = stats.ttest_ind(grupo_presente, grupo_faltante, equal_var=False)
            metodo = "Teste T"
        else:
            # Teste de Mann-Whitney U (Não-paramétrico)
            u_stat, p_val = stats.mannwhitneyu(grupo_presente, grupo_faltante)
            metodo = "Mann-Whitney U"
            
        resultados.append({
            'Variavel': col,
            'Metodo': metodo,
            'Media_Grupo_Presente': grupo_presente.mean(),
            'Media_Grupo_Faltante': grupo_faltante.mean(),
            'P-Valor': p_val,
            'MAR_Detectado': p_val < 0.05
        })
    
    return pd.DataFrame(resultados)
```

````