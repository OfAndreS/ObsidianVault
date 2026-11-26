---
banner: "![[Pasted image 20260107191609.png]]"
---
---

```ad-done
title:

#### **Fase 01 ) -** Regressão Linear Simples

```

---

````ad-quote
title:
##### **01 ) -** Introdução

```ad-quote
title:
<p align="justify">Neste cenário, observamos a relação direta entre um único preditor e o alvo. O objetivo principal é compreender como a variável dependente responde a mudanças na independente, utilizando a reta de ajuste para validar a suposição de linearidade do conjunto de dados.</p>
```

```ad-quote
title:
| **Componente** | **Descrição Detalhada**                                           | **Papel na Avaliação**                                          |
| -------------- | ----------------------------------------------------------------- | --------------------------------------------------------------- |
| **Fit Plot**   | Dispersão com reta de ajuste que mostra a tendência dos dados.    | Valida se a relação entre as variáveis é de fato linear.        |
| **Resíduos**   | Análise da distância entre os pontos reais e a reta de regressão. | Verifica se os erros são aleatórios ou possuem padrões ocultos. |
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 ) -** Como ler o Fit Plot - Gráfico de Ajuste

```ad-quote
title:
O _Fit Plot_ é a representação direta da relação entre a causa ($X$) e o efeito ($Y$). Ele serve para validar a premissa de _linearidade_ do modelo.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal 
```

```ad-quote
title:
###### Eixos e Reta
```

```ad-quote
title:
O eixo horizontal representa a variável independente e o vertical a variável dependente. A reta de regressão (geralmente azul ou vermelha) é a _estimativa matemática_ do modelo, definida pela equação $\hat{y} = \beta_0 + \beta_1 x$.
```

```ad-quote
title:
###### Aderência
```

```ad-quote
title:
Você deve observar o quanto os pontos (dados reais) estão "colados" à reta. Quanto mais próximos eles estiverem, maior será o _coeficiente de determinação_ ($R^2$), indicando que a variável $X$ explica bem a variabilidade de $Y$.
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Sinais de Alerta 
```

```ad-quote
title:
###### Curvaturas
```

```ad-quote
title:
Se os pontos formam um desenho em formato de "U" ou parábola em vez de seguirem a reta, a relação não é linear. Isso indica que você deve usar regressão polinomial.
```

```ad-quote
title:
###### Outliers
```

```ad-quote
title:
Pontos isolados muito distantes da massa principal podem puxar a reta para longe do comportamento real, distorcendo o _impacto marginal_ da variável.
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 ) -** Como ler o Gráfico de Resíduos

```ad-quote
title:
Se o _Fit Plot_ mostra o que o modelo acertou, o _Gráfico de Resíduos_ mostra o que ele errou. O resíduo é a diferença matemática $e = y - \hat{y}$.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal 
```

```ad-quote
title:
###### Linha Zero
```

```ad-quote
title:
O gráfico possui uma linha horizontal no valor zero. Um ponto sobre essa linha significa que o modelo acertou a predição _exatamente_.
```

```ad-quote
title:
###### Distribuição Ideal
```

```ad-quote
title:
O que você espera ver é uma _nuvem aleatória_ de pontos espalhada acima e abaixo do zero, sem nenhum formato geométrico definido. Isso comprova que o erro é puramente fruto do acaso.
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Sinais de Alerta e Falhas nas Premissas 
```

```ad-quote
title:
###### Heterocedasticidade (Efeito Funil)
```

```ad-quote
title:
Se a dispersão dos pontos começa estreita e vai abrindo conforme avançamos no eixo, a variância do erro não é constante. Isso invalida a confiabilidade dos seus _p-valores_.
```

```ad-quote
title:
###### Autocorrelação
```

```ad-quote
title:
Se os resíduos seguem uma sequência (ex: vários positivos seguidos de vários negativos), o modelo está deixando passar uma _tendência temporal_ ou lógica que deveria ter sido capturada.
```

```ad-quote
title:
###### Viés de Modelo
```

```ad-quote
title:
Se os resíduos formam uma curva, o modelo está sistematicamente errando para certas faixas de dados, reforçando a necessidade de uma função não linear.
```

````

---

> [!done] _New_

---

````ad-quote
title:

```ad-quote
title:
###### Código em Python
```

```Python
import numpy as np
import matplotlib.pyplot as plt

# Dados: Anos de Experiência e Salário
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y = np.array([3000, 3500, 4100, 4900, 5200, 6100, 6800, 7500, 8100, 9200])

# Cálculo da regressão simples
coef = np.polyfit(x, y, 1)
y_pred = np.polyval(coef, x)
residuos = y - y_pred

# Criação da figura
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5))

# Gráfico 1: Reta de Ajuste (Fit Plot)
ax1.scatter(x, y, color='steelblue', edgecolor='white', s=70, alpha=0.7)
ax1.plot(x, y_pred, 'r--', lw=2)
ax1.set_title('Ajuste Linear (Simples)')
ax1.set_xlabel('Anos de Experiência')
ax1.set_ylabel('Salário')

# Gráfico 2: Resíduos Individuais
ax2.scatter(x, residuos, color='#4e79a7', edgecolor='white', s=70, alpha=0.7)
ax2.axhline(0, color='black', lw=1)
ax2.set_title('Análise de Resíduos')
ax2.set_xlabel('Variável X')
ax2.set_ylabel('Erro (Real - Predito)')

plt.tight_layout()
plt.show()
```
````

---

```ad-done
title:

#### **Fase 02 ) -**  Regressão Linear Múltipla

```

---

````ad-quote
title:
##### **01 ) -** Introdução

```ad-quote
title:
<p align="justify">Na regressão multivariada, a complexidade analítica aumenta devido à presença de múltiplos preditores. Utilizamos representações que resumem a performance global e a influência individual de cada variável sob a lógica _ceteris paribus_.</p>
```

```ad-quote
title:
| **Componente** | **Descrição Detalhada** | **Papel na Avaliação** |
| -------------- | ----------------------- | ---------------------- |
| **Real vs. Predito** | Comparação entre o valor observado e a estimativa do hiperplano. | Substitui a reta de ajuste para medir a precisão global. |
| **Coeficientes** | Gráfico de barras que exibe a magnitude do peso de cada atributo. | Revela quais variáveis possuem maior impacto marginal no alvo. |
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 ) -** Como ler o Gráfico de Valores Reais vs. Predições

```ad-quote
title:
Este gráfico atua como o principal termômetro de performance global em modelos com múltiplas variáveis, substituindo a visualização da reta de ajuste simples.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal 
```

```ad-quote
title:
###### Linha de Identidade
```

```ad-quote
title:
A reta diagonal pontilhada em 45 graus representa a perfeição teórica, onde o valor real é exatamente igual ao predito pelo modelo.
```

```ad-quote
title:
###### Concentração dos Dados
```

```ad-quote
title:
Você deve observar o quanto os pontos azuis estão _esmagados_ contra essa diagonal; quanto menor a dispersão ao redor da linha, maior é a precisão do seu modelo e, consequentemente, o seu $R^2$.
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Sinais de Alerta 
```

```ad-quote
title:
###### Dispersão nos Extremos
```

```ad-quote
title:
Se os pontos começam a se afastar da diagonal conforme os valores aumentam (ou diminuem muito), isso indica que o modelo perdeu a capacidade de generalização em casos excepcionais.
```

```ad-quote
title:
###### Tendência de Nuvem
```

```ad-quote
title:
Se a nuvem de pontos parece ter uma inclinação diferente da reta vermelha, seu modelo pode estar subestimando ou superestimando sistematicamente os resultados.
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 ) -** Como ler o Gráfico de Coeficientes (Impacto)

```ad-quote
title:
Enquanto o gráfico anterior avalia a precisão, este gráfico de barras revela a _estrutura interna_ do modelo, mostrando como cada variável contribui para a decisão final.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal 
```

```ad-quote
title:
###### Magnitude das Barras
```

```ad-quote
title:
A altura ou comprimento de cada barra representa o _peso_ (coeficiente) daquela variável específica; barras mais longas indicam que aquele atributo possui maior _alavancagem_ sobre o resultado do alvo.
```

```ad-quote
title:
###### Direção do Impacto
```

```ad-quote
title:
Barras que apontam para valores positivos indicam uma relação direta (se a variável sobe, o alvo sobe), enquanto barras negativas indicam uma relação inversa.
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) Sinais de Alerta 
```

```ad-quote
title:
###### Magnitude Desproporcional
```

```ad-quote
title:
Se uma única variável apresenta uma barra imensa comparada às outras sem uma justificativa teórica sólida, isso pode ser um indício de _multicolinearidade_, onde variáveis redundantes confundem o aprendizado do algoritmo.
```

```ad-quote
title:
###### Variáveis Irrelevantes
```

```ad-quote
title:
Barras muito curtas ou próximas de zero sugerem que aquele atributo tem pouco ou nenhum impacto real no fenômeno estudado, podendo ser candidatos à remoção para simplificar o modelo.
```

````

---

> [!done] _New_

---

````ad-quote
title:

```ad-quote
title:
###### Código em Python
```

```Python
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt

# Treinamento do modelo múltiplo
modelo = LinearRegression()
modelo.fit(X_multi, y_real)
y_pred_multi = modelo.predict(X_multi)

# Criação da figura
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5))

# Gráfico 1: Real vs Predito
ax1.scatter(y_real, y_pred_multi, color='steelblue', edgecolor='white', s=70, alpha=0.7)
ax1.plot([y_real.min(), y_real.max()], [y_real.min(), y_real.max()], 'r--', lw=2)
ax1.set_title('Valores Reais vs. Predições')
ax1.set_xlabel('Real')
ax1.set_ylabel('Predito')

# Gráfico 2: Magnitude dos Coeficientes
labels = ['BMI', 'BP', 'S1', 'S5'] # Exemplo de features do dataset
ax2.bar(labels, modelo.coef_[:4], color=['#4e79a7', '#f28e2b', '#e15759', '#76b7b2'], alpha=0.8)
ax2.axhline(0, color='black', lw=1)
ax2.set_title('Impacto das Variáveis (Pesos)')
ax2.set_ylabel('Valor do Coeficiente')

plt.tight_layout()
plt.show()
```
````

---

```ad-done
title:

#### **Fase 03 ) -** Validação Estatística de Resíduos

```

---

````ad-quote
title:
##### **01 ) -** Introdução

```ad-quote
title:
<p align="justify">Estes diagnósticos são fundamentais para validar as premissas de _normalidade_ e _homocedasticidade_ que sustentam a confiabilidade dos testes de hipótese e dos p-valores.</p>
```

```ad-quote
title:
| **Componente** | **Descrição Detalhada** | **Papel na Avaliação** |
| -------------- | ----------------------- | ---------------------- |
| **Histograma** | Distribuição de frequência dos erros do modelo. | Verifica se os resíduos seguem uma distribuição normal centrada no zero. |
| **Q-Q Plot** | Comparação de quantis teóricos versus observados. | Teste rigoroso para identificar falhas em casos extremos. |
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 ) -** Como ler o Histograma de Resíduos

```ad-quote
title:
O histograma é a ferramenta visual primária para verificar a _distribuição de frequência_ dos erros do modelo.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal
```

```ad-quote
title:
###### Centralidade
```

```ad-quote
title:
O pico da distribuição deve estar localizado exatamente sobre o _valor zero_. Um deslocamento sugere a presença de um viés constante não capturado.
```

```ad-quote
title:
###### Simetria
```

```ad-quote
title:
O que se espera ver é uma curva em formato de sino (_Gaussiana_) equilibrada. A assimetria indica que o modelo subestima ou superestima valores sistematicamente.
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **03 ) -** Como ler o Normal Q-Q Plot

```ad-quote
title:
Este gráfico compara os quantis dos resíduos com os quantis de uma distribuição normal teórica para validar a integridade estatística.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal
```

```ad-quote
title:
###### Linha Diagonal
```

```ad-quote
title:
A reta representa a _normalidade perfeita_. Se os pontos seguirem esta linha, os erros são puramente aleatórios e gaussianos.
```

```ad-quote
title:
###### Extreamidades
```

```ad-quote
title:
Pontos que se curvam para longe da linha nas pontas indicam que o modelo falha em prever _eventos raros_ ou extremos (caudas pesadas).
```

````

---

> [!done] _New_

---

````ad-quote
title:

```ad-quote
title:
###### Código em Python
```

```Python
import scipy.stats as stats
import matplotlib.pyplot as plt

# Cálculo dos resíduos do modelo múltiplo
residuos_multi = y_real - y_pred_multi

# Criação da figura
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5))

# Gráfico 1: Histograma de Distribuição
ax1.hist(residuos_multi, bins=20, color='steelblue', edgecolor='white', alpha=0.7, density=True)
ax1.set_title('Distribuição dos Erros')
ax1.set_xlabel('Resíduo')

# Gráfico 2: Normal Q-Q Plot
stats.probplot(residuos_multi, dist="norm", plot=ax2)
ax2.get_lines()[0].set_markerfacecolor('steelblue')
ax2.get_lines()[0].set_markeredgecolor('white')
ax2.set_title('Gráfico Normal Q-Q')

plt.tight_layout()
plt.show()
```
````

---

```ad-done
title:

#### **Fase 04 ) -** Auditoria de Vieses e Influência

```

---

````ad-quote
title:
##### **01 ) -** Introdução

```ad-quote
title:
<p align="justify">A auditoria de modelos identifica riscos estruturais, como a _multicolinearidade_ (redundância entre variáveis) e a presença de pontos que exercem influência desproporcional sobre os coeficientes.</p>
```

```ad-quote
title:
| **Componente** | **Descrição Detalhada** | **Papel na Avaliação** |
| -------------- | ----------------------- | ---------------------- |
| **Heatmap** | Matriz de correlação entre variáveis independentes. | Identifica preditores redundantes que confundem o modelo. |
| **Distância de Cook** | Medida de influência de cada observação nos parâmetros. | Detecta _outliers influentes_ que podem distorcer o impacto real. |
```
````

---

> [!done] _New_

---

````ad-quote
title:
##### **02 ) -** Como ler o Heatmap de Correlação

```ad-quote
title:
O mapa de calor identifica a _colinearidade_ interna entre os atributos antes ou após o treinamento do sistema.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal
```

```ad-quote
title:
###### Intensidade das Cores
```

```ad-quote
title:
Cores muito intensas entre duas variáveis independentes sinalizam redundância. Isso infla o erro padrão e prejudica a validade do _Teste F_.
```

```ad-quote
title:
###### Coeficiente de Pearson
```

```ad-quote
title:
Valores próximos de $1$ ou $-1$ indicam forte correlação. Na auditoria, busca-se evitar que preditores "digam a mesma coisa" para manter a estabilidade dos betas.
```

````

---

> [!done] _New_

---

````ad-quote
title:
##### **03 ) -** Como ler a Distância de Cook

```ad-quote
title:
Diferente de um outlier comum, a _Distância de Cook_ foca no poder que um único ponto tem de alterar a inclinação da reta.
```
````

````ad-quote
title:

```ad-quote
title:
###### A ) Interpretação Principal
```

```ad-quote
title:
###### Alavancagem
```

```ad-quote
title:
Qualquer ponto que se destaque significativamente acima da média dos demais deve ser auditado. Ele pode representar um erro de coleta ou um caso atípico.
```

```ad-quote
title:
###### Estabilidade
```

```ad-quote
title:
Se o modelo for muito sensível a poucos pontos, ele perde a capacidade de _generalização_, tornando a análise de impacto marginal pouco confiável.
```

````

---

> [!done] _New_

---

````ad-quote
title:

```ad-quote
title:
###### Código em Python
```

```Python
import seaborn as sns
import statsmodels.api as sm
import numpy as np
import matplotlib.pyplot as plt

# Cálculo da Distância de Cook via statsmodels
X_const = sm.add_constant(X_multi)
influence = sm.OLS(y_real, X_const).fit().get_influence()
cooks = influence.cooks_distance[0]

# Criação da figura
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5))

# Gráfico 1: Mapa de Calor de Colinearidade
sns.heatmap(df.drop(columns=['target']).corr(), annot=False, cmap='RdBu', center=0, ax=ax1)
ax1.set_title('Matriz de Correlação (Multicolinearidade)')

# Gráfico 2: Distância de Cook (Influência)
ax2.stem(np.arange(len(cooks)), cooks, markerfmt=",", linefmt="steelblue")
ax2.set_title('Distância de Cook (Pontos Influentes)')
ax2.set_xlabel('Índice da Amostra')
ax2.set_ylabel('Influência')

plt.tight_layout()
plt.show()
```
````

---

