---
banner: "![[Pasted image 20260115190114.png]]"
---
---

```ad-done
title:

#### **Fase 01 ) -** Diagnóstico Visual de Nulidade

```

---

````ad-quote
title:
##### **01 ) -** Introdução

```ad-quote
title:
<p align="justify">A análise visual de dados faltantes é a etapa preliminar para identificar a natureza da ausência de informação. O objetivo é distinguir se os dados faltam de maneira totalmente aleatória (MCAR) ou se existe um padrão sistemático (MAR) que exige tratamento específico.</p>
```

```ad-quote
title:
| **Ferramenta** | **Descrição Detalhada** | **Papel na Avaliação** |
| -------------- | ----------------------- | ---------------------- |
| **Matriz de Nulidade** | Visualização direta da presença ou ausência de dados em cada linha. | Identifica padrões globais e sistemáticos de preenchimento. |
| **Boxplot Comparativo** | Comparação de distribuições entre quem respondeu e quem não respondeu. | O detector mais robusto para identificar dependências (MAR). |
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 ) -** Como ler a Matriz de Nulidade (Matrix Plot)

```ad-quote
title:
Este gráfico exibe a totalidade do dataset, onde áreas escuras representam dados presentes e áreas brancas representam dados faltantes.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal
```

![[Pasted image 20260116215830.png]]

```ad-quote
title:
###### Listras Aleatórias
```

```ad-quote
title:
Se você observa linhas brancas finas espalhadas pelo gráfico sem um desenho claro, isso sugere que os dados faltam ao acaso (MCAR), sem interferência externa.
```

```ad-quote
title:
###### Blocos Alinhados
```

```ad-quote
title:
A presença de grandes blocos brancos que coincidem em diferentes colunas indica correlação de nulidade. Exemplo: registros sem data de saída também não possuem motivo de saída.
```

````

````ad-quote
title:

```ad-quote
title:
###### Código em Python - Matriz de Nulidade
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

> [!done] _New_

---

````ad-quote
title:
##### **03 ) -** Como ler o Boxplot Comparativo

```ad-quote
title:
Esta técnica divide os dados em dois grupos lógicos: as observações que possuem valor para a variável $X$ e as observações onde $X$ é nulo. Compara-se então uma variável $Y$ (como Idade) entre esses grupos.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal
```

![[Pasted image 20260116220041.png]]

```ad-quote
title:
###### Caixas Alinhadas
```

```ad-quote
title:
Quando as medianas e o formato das caixas são equivalentes entre os dois grupos, a ausência da variável $X$ não está relacionada à variável $Y$. Isso aponta para MCAR.
```

```ad-quote
title:
###### Desnível das Caixas
```

```ad-quote
title:
Se uma caixa é significativamente mais alta ou baixa que a outra, existe um mecanismo MAR. Isso prova que a falta de informação em $X$ depende dos valores de $Y$.
```

````

````ad-quote
title:

```ad-quote
title:
###### Código em Python - Boxplot Comparativo
```

```Python
import seaborn as sns

def plot_missing_boxplot(df: pd.DataFrame, target_var: str, control_var: str):
    """
    Compara a distribuição de uma variável NUMÉRICA (control_var)
    entre os grupos que responderam e não responderam a target_var.
    
    Args:
        target_var: A coluna que possui dados faltantes.
        control_var: Uma coluna NUMÉRICA completa para comparação (ex: Idade, Preço).
    """
    plt.figure(figsize=(10, 6))
    
    # Cria cópia para não alterar o df original
    temp_df = df.copy()
    temp_df['is_missing'] = temp_df[target_var].isnull()
    
    sns.boxplot(x='is_missing', y=control_var, data=temp_df, showfliers=False)
    
    plt.title(f'Hipótese MAR: A falta de "{target_var}" afeta "{control_var}"?')
    plt.xlabel(f'{target_var} está ausente?')
    plt.ylabel(control_var)
    plt.xticks([0, 1], ['Não (Dado Presente)', 'Sim (Dado Faltante)'])
    plt.show()
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **04 ) -** Outras Ferramentas de Diagnóstico

```ad-quote
title:
Além das visualizações primárias, utilizamos mapas de calor e gráficos de dispersão para auditar relações complexas de dependência entre variáveis.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Heatmap de Correlação de Nulidade
```

![[Pasted image 20260116215929.png]]

```ad-quote
title:
###### O que observar
```

```ad-quote
title:
Este mapa não mede a correlação de valores numéricos, mas a correlação da existência do dado.
```

```ad-quote
title:
###### Interpretação
```

```ad-quote
title:
|**Valor**|**Significado**|**Conclusão sobre o Tipo**|
|---|---|---|
|**Negativo (-)**|Um aparece, o outro some (Inverso).|**MAR** (Existe Padrão)|
|**Positivo (+)**|Ambos somem juntos (Sincronizado).|**MAR** (Existe Padrão)|
|**Zero (0)**|Sem relação nenhuma.|**MCAR** (Aleatório)|
```

```ad-quote
title:
Um valor próximo de $1$ indica que se a Variável A estiver ausente, a Variável B também estará. Um valor de $0$ indica que não há relação entre a perda de dados dessas colunas.
```

````

````ad-quote
title:

```ad-quote
title:
###### Código em Python - Heatmap de Correlação
```

```Python
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

````ad-quote
title:

```ad-quote
title:
###### B ) Scatter Plot com Marcação
```

![[Pasted image 20260116220206.png]]

```ad-quote
title:
###### O que observar
```

```ad-quote
title:
Plota-se duas variáveis observadas (ex: Idade vs Renda) e destaca-se em vermelho os pontos onde uma terceira variável (ex: Peso) está ausente.
```

```ad-quote
title:
###### Interpretação
```

```ad-quote
title:
Se os pontos vermelhos estão misturados uniformemente, a perda é aleatória. Se estão concentrados em um canto (ex: apenas em alta renda), confirma-se o padrão MAR.
```

````

````ad-quote
title:

```ad-quote
title:
###### Código em Python - Scatter/Strip Plot de Densidade
```

```Python
def plot_missing_scatter(df: pd.DataFrame, target_var: str, control_var: str):
    """
    Plota os pontos individuais (Scatter 1D) para visualizar a densidade
    e concentração dos dados faltantes em relação a uma variável de controle.
    """
    plt.figure(figsize=(10, 6))
    
    temp_df = df.copy()
    temp_df['is_missing'] = temp_df[target_var].isnull()
    
    # Usamos StripPlot pois o ScatterPlot tradicional falha quando X é nulo
    sns.stripplot(
        x='is_missing', 
        y=control_var, 
        data=temp_df, 
        jitter=True,        # Espalha os pontos para ver a densidade
        alpha=0.6,          # Transparência
        palette=['blue', 'red'], 
        order=[False, True] # Azul na esquerda, Vermelho na direita
    )
    
    plt.title(f'Densidade de Nulos: Onde estão concentrados os erros de "{target_var}"?')
    plt.xlabel(f'{target_var} está ausente?')
    plt.ylabel(control_var)
    plt.xticks([0, 1], ['Dados Presentes (Azul)', 'Dados Faltantes (Vermelho)'])
    plt.show()
```
````

---

> [!done] _New_

---

````ad-quote
title:

```ad-quote
title:
###### Exemplo de Uso
```

```Python
# Carregue seus dados
df = pd.read_csv('seu_arquivo.csv')

# 1. Visão Geral
plot_nullity_matrix(df)
plot_nullity_correlation(df)

# 2. Investigação Específica (Ex: Faltam idades para quem pagou barato?)
# target_var = Variável com nulos (ex: 'Age')
# control_var = Variável numérica completa (ex: 'Fare')
plot_missing_boxplot(df, target_var='Age', control_var='Fare')
plot_missing_scatter(df, target_var='Age', control_var='Fare')
```
````

---


