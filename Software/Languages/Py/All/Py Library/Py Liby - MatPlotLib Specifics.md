
---

````ad-quote
title:

##### **Intro )** - Definição

```ad-quote
title:
<p align="justify"><b>Matplotlib</b> é a biblioteca mais fundamental e amplamente utilizada para a criação de visualizações de dados estáticas, animadas e interativas em Python. Ela fornece um conjunto de ferramentas de baixo nível para criar uma vasta gama de gráficos e figuras com qualidade de publicação. Seus principais objetos são a <b>`Figure`</b> (a janela ou contêiner geral) e os <b>`Axes`</b> (os subplots individuais onde os dados são de fato plotados).</p>
```

```ad-quote
title:
<p align="justify"><b>Link:</b> <a href="[https://matplotlib.org/stable/index.html](https://matplotlib.org/stable/index.html)">Matplotlib Documentation</a></p>
```

>[!quote] **Colab:** [Matplotlib Colab](https://colab.research.google.com/) (Link de exemplo, substitua pelo seu)

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - Anatomia de um Gráfico

```ad-quote
title:
**Componentes Principais:**
```

```ad-quote
title:

| Componente | Explicação |
| --- | --- |
| `Figure` | O contêiner de mais alto nível para todos os elementos do gráfico (títulos, eixos, etc.). |
| `Axes` | A área onde os dados são plotados; um gráfico individual. Uma `Figure` pode conter múltiplos `Axes`. |
| `Axis` | Os eixos X e Y, que definem a escala e os limites dos dados. |
| `Title` | O título do `Axes` (gráfico). |
| `Labels` | Os nomes dos eixos X (`xlabel`) e Y (`ylabel`). |
| `Legend` | A legenda que descreve os diferentes conjuntos de dados plotados no `Axes`. |
| `Ticks` | As marcações nos eixos (`xticks`, `yticks`) que indicam pontos específicos. |
| `Grid` | As linhas de grade opcionais no fundo do gráfico para facilitar a leitura. |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - Criação de Gráficos / Interface Pyplot

```ad-quote
title:
<p align="justify"><b>Interface matplotlib.pyplot / Estilo MATLAB:</b></p>
```

```python
import matplotlib.pyplot as plt
import numpy as np

# Dados de exemplo
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Cria um gráfico de linha simples
plt.plot(x, y)
plt.show() # Exibe o gráfico
```

```ad-quote
title:
<p align="justify"><b>Tipos de Gráficos Comuns:</b></p>
```

```python
# Dados de exemplo
x = np.array([1, 2, 3, 4])
y1 = np.array([10, 20, 15, 25])
y2 = np.random.randn(100) # 100 números aleatórios

# Gráfico de dispersão (Scatter Plot)
plt.scatter(x, y1)
plt.show()

# Gráfico de barras (Bar Chart)
plt.bar(['A', 'B', 'C', 'D'], y1)
plt.show()

# Histograma
plt.hist(y2, bins=15)
plt.show()
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Personalização de Gráficos

```ad-quote
title:
Matplotlib oferece controle total sobre cada elemento de um gráfico, desde cores e estilos de linha até títulos e anotações.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Títulos, Rótulos e Legendas**
```

```ad-quote
title:
Funções que adicionam informações contextuais ao gráfico.
```

```python
x = np.linspace(0, 2 * np.pi, 50)
y1 = np.sin(x)
y2 = np.cos(x)

plt.plot(x, y1, label='Seno')
plt.plot(x, y2, label='Cosseno')

plt.title('Funções Trigonométricas')
plt.xlabel('Eixo X (radianos)')
plt.ylabel('Eixo Y (valor)')
plt.legend() # Ativa a legenda
plt.grid(True) # Adiciona uma grade
plt.show()
```
````

````ad-quote
title:
```ad-quote
title:
###### **Cores, Estilos e Marcadores**
```

```ad-quote
title:
Altere a aparência das linhas e pontos para diferenciar os dados.
```

```python
x = np.linspace(0, 5, 10)
y = x ** 2

# Linha vermelha ('r'), tracejada ('--'), com marcadores circulares ('o')
plt.plot(x, y, color='red', linestyle='--', marker='o')
# Formato abreviado: 'g-^' -> verde, linha sólida, marcador de triângulo
plt.plot(x, y + 10, 'g-^')
plt.show()
```
````

````ad-quote
title:
```ad-quote
title:
###### **Limites e Anotações**
```

```ad-quote
title:
Permite focar em uma área específica do gráfico ou adicionar texto explicativo.
```

```python
x = np.linspace(0, 10, 100)
y = np.sin(x)

plt.plot(x, y)
plt.xlim(0, 5) # Define o limite do eixo X de 0 a 5
plt.ylim(-1.5, 1.5) # Define o limite do eixo Y de -1.5 a 1.5

# Adiciona um texto no ponto (x,y) = (1, 0.5)
plt.text(1, 0.5, 'Um ponto de interesse')
plt.show()
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - Interface Orientada a Objetos

```ad-quote
title:
A interface OO oferece mais controle e flexibilidade, sendo a abordagem recomendada para gráficos complexos ou com múltiplos subplots.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Criação Explícita de `Figure` e `Axes`**
```

```ad-quote
title:
Em vez de usar `plt.funcao()`, você chama métodos diretamente no objeto `Axes`.
```

```python
x = np.linspace(0, 10, 100)
y = x**2

# Cria uma figura e um conjunto de eixos
fig, ax = plt.subplots()

# Usa métodos do objeto 'ax' para plotar e personalizar
ax.plot(x, y, label='Parábola')
ax.set_title('Gráfico OO')
ax.set_xlabel('Eixo X')
ax.set_ylabel('Eixo Y')
ax.legend()
plt.show()
```
````

````ad-quote
title:
```ad-quote
title:
###### **Subplots (Múltiplos Gráficos)**
```

```ad-quote
title:
A principal vantagem da abordagem OO é a facilidade para criar figuras com múltiplos gráficos.
```

```python
# Cria uma figura e uma grade de 1 linha e 2 colunas de eixos
fig, axes = plt.subplots(1, 2, figsize=(10, 4)) # figsize define o tamanho em polegadas

x = np.linspace(0, 2*np.pi, 100)
y_sin = np.sin(x)
y_cos = np.cos(x)

# Plota no primeiro eixo (índice 0)
axes[0].plot(x, y_sin, color='blue')
axes[0].set_title('Seno')

# Plota no segundo eixo (índice 1)
axes[1].plot(x, y_cos, color='red')
axes[1].set_title('Cosseno')

plt.tight_layout() # Ajusta o espaçamento para evitar sobreposição
plt.show()
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **05 )** - Métodos Úteis e Funções

```ad-quote
title:
<p align="justify"><b>Salvando Figuras:</b></p>
```

```python
x = np.linspace(0, 10, 50)
y = x**2

plt.plot(x, y)
plt.title('Meu Gráfico')

# Salva a figura em um arquivo
# dpi = dots per inch (resolução)
# bbox_inches='tight' remove excesso de borda branca
plt.savefig('meu_grafico.png', dpi=300, bbox_inches='tight')
```

```ad-quote
title:
<p align="justify"><b>Gráficos Estatísticos (Exemplos):</b></p>
```

```python
# Dados para Boxplot
data = [np.random.normal(0, std, 100) for std in range(1, 4)]
fig, ax = plt.subplots()
ax.boxplot(data, vert=True, patch_artist=True)
ax.set_title('Boxplot')
plt.show()


# Dados para Heatmap
matrix = np.random.rand(5, 5)
fig, ax = plt.subplots()
im = ax.imshow(matrix, cmap='viridis') # cmap = mapa de cores
fig.colorbar(im) # Adiciona a barra de cores
ax.set_title('Heatmap')
plt.show()
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **06 )** - Integração com Outras Bibliotecas

```ad-quote
title:
**Matplotlib + NumPy**
```

```ad-quote
title:
NumPy é o padrão de fato para fornecer dados ao Matplotlib. A maioria das funções de plotagem é otimizada para receber `ndarrays`.
```

```python
# NumPy é usado para gerar os dados
x = np.arange(0, 4 * np.pi, 0.1)
y = np.sin(x)

# Matplotlib é usado para visualizar
plt.plot(x, y)
plt.title('Gráfico de Seno Gerado com NumPy')
plt.show()
```

```ad-quote
title:
**Matplotlib + Pandas**
```

```ad-quote
title:
A biblioteca Pandas utiliza Matplotlib como seu backend de visualização padrão. O método `.plot()` de um DataFrame é um atalho conveniente.
```

```python
import pandas as pd

# Cria um DataFrame de exemplo
data = {'vendas': [15, 32, 25, 40], 'ano': [2021, 2022, 2023, 2024]}
df = pd.DataFrame(data)

# O método .plot() do Pandas usa Matplotlib por baixo dos panos
df.plot(x='ano', y='vendas', kind='bar', title='Vendas Anuais')
plt.ylabel('Unidades Vendidas')
plt.show()
```

````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **07 )** - Dicas de Performance

```ad-quote
title:

| Situação | Dica de Otimização | Explicação |
| --- | --- | --- |
| Gráficos com muitos pontos (>10k) | Use marcadores simples (`marker='.'`) ou não use marcadores. Se possível, faça uma amostragem dos dados. | Renderizar marcadores complexos para milhares de pontos é lento. A plotagem de linhas é muito mais rápida. |
| Múltiplos plots em um loop (animações) | Crie a `Figure` e o `Axes` fora do loop e apenas atualize os dados do plot (`line.set_data()`) a cada iteração. | Recriar a figura inteira a cada passo do loop consome muita memória e poder de processamento. |
| Consumo de memória com muitos gráficos | Feche as figuras que não são mais necessárias usando `plt.close(fig)` ou `plt.close('all')`. | Matplotlib mantém as figuras na memória até que sejam explicitamente fechadas. |
| Gráficos complexos com muitos elementos | Use a interface Orientada a Objetos. | A interface OO dá um controle mais granular e evita que o estado global do `pyplot` se torne confuso e lento. |

```

```ad-quote
title:
<p align="justify">Para visualizações estáticas com qualidade de publicação, Matplotlib é extremamente eficiente. O gargalo geralmente não está na biblioteca em si, mas na quantidade de dados sendo renderizada. Para exploração interativa de datasets massivos, bibliotecas como Plotly, Bokeh ou Datashader podem oferecer uma experiência mais fluida.</p>
```
````

---