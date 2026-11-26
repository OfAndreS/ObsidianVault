
---

````ad-quote
title:

##### **Matplotlib** - Um Guia Essencial para Visualização de Dados em Python


```ad-quote
title:
<p align="justify">Matplotlib é a biblioteca fundamental para a criação de visualizações estáticas, animadas e interativas em Python. Entender sua estrutura é mais importante do que memorizar todas as funções. Quase todo gráfico que você cria envolve a manipulação de dois objetos principais: a <b>Figure</b> (a janela ou página inteira) e os <b>Axes</b> (os "gráficos" individuais dentro da figura, com os eixos x e y).</p>

<p align="justify">A seguir, apresentamos as funções e métodos mais cruciais do Matplotlib, organizados em torno de suas duas principais interfaces de uso.</p>
```
````

>[!quote] **Link: ** [Galeria Oficial do Matplotlib](https://matplotlib.org/stable/gallery/index.html).

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - A Interface 

```ad-quote
title:
<p align="justify">Esta é a forma mais comum e direta de começar a plotar. As funções em `pyplot` operam implicitamente na figura e nos eixos "atuais". É excelente para análise exploratória de dados e gráficos rápidos.</p>
```

```ad-quote
title:

###### **Comandos Básicos e de Gerenciamento**

| Função (`plt.`) | Descrição | Exemplo de Uso |
|---|---|---|
| `figure()` | Cria uma nova figura (janela). | `plt.figure(figsize=(10, 6))` |
| `show()` | Exibe todas as figuras criadas. | `plt.show()` |
| `savefig()` | Salva a figura atual em um arquivo. | `plt.savefig('meu_grafico.png')` |
| `title()` | Define o título do gráfico (axes). | `plt.title('Vendas Mensais')` |
| `xlabel()` / `ylabel()` | Define o rótulo dos eixos X e Y. | `plt.xlabel('Mês'); plt.ylabel('Receita (R$)')` |
| `grid()` | Adiciona uma grade ao gráfico. | `plt.grid(True)` |
| `legend()` | Exibe a legenda do gráfico. | `plt.legend(['Linha 1', 'Linha 2'])` |
| `xlim()` / `ylim()` | Define os limites dos eixos X e Y. | `plt.xlim(0, 10)` |
| `xticks()` / `yticks()` | Define as marcações (ticks) dos eixos. | `plt.xticks([0, 5, 10])` |
| `subplot()` | Cria múltiplos gráficos em uma única figura. | `plt.subplot(1, 2, 1) # (1 linha, 2 colunas, 1º gráfico)`|
| `subplots()` | Cria uma figura e um conjunto de subplots de uma vez (mais moderno). | `fig, ax = plt.subplots()` |

###### **Funções de Plotagem (`plt.`)**

| Função | Descrição | Exemplo de Uso |
|---|---|---|
| `plot()` | Gráfico de linhas. O mais fundamental de todos. | `plt.plot(meses, vendas)` |
| `scatter()` | Gráfico de dispersão, para visualizar a relação entre duas variáveis. | `plt.scatter(peso, altura)` |
| `bar()` | Gráfico de barras verticais. | `plt.bar(categorias, valores)` |
| `barh()` | Gráfico de barras horizontais. | `plt.barh(categorias, valores)` |
| `hist()` | Histograma, para visualizar a distribuição de uma variável. | `plt.hist(dados, bins=20)` |
| `pie()` | Gráfico de pizza. | `plt.pie(valores, labels=categorias)` |
| `boxplot()` | Diagrama de caixa (boxplot), para visualizar distribuições. | `plt.boxplot(dados)` |
| `imshow()` | Exibe dados como uma imagem (ex: matrizes, pixels). | `plt.imshow(matriz_de_dados)` |
| `errorbar()` | Gráfico de linhas com barras de erro. | `plt.errorbar(x, y, yerr=erros)` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - A API Orientada a Objetos / Controle Total

```ad-quote
title:
Esta abordagem é mais explícita e robusta. Você primeiro cria os objetos `Figure` e `Axes` (geralmente com `plt.subplots()`) e depois chama métodos diretamente nesses objetos. Isso evita ambiguidades e é a forma recomendada para gráficos que exigem personalização detalhada.
```

```ad-quote
title:
###### **Estrutura Básica**
```python
import matplotlib.pyplot as plt
import numpy as np

# 1. Criar a Figura e os Eixos
fig, ax = plt.subplots(figsize=(10, 6))

# 2. Plotar os dados usando métodos do objeto 'ax'
x = np.linspace(0, 10, 100)
ax.plot(x, np.sin(x), label='Seno')
ax.scatter(x, np.cos(x), label='Cosseno')

# 3. Customizar usando métodos 'set_*' do objeto 'ax'
ax.set_title('Funções Trigonométricas')
ax.set_xlabel('Eixo X')
ax.set_ylabel('Eixo Y')
ax.grid(True)
ax.legend()

# 4. Exibir o gráfico
plt.show()
```
```ad-quote
title:

###### **Mapeamento de Funções: `pyplot` vs. Métodos de `Axes`**

| Função `pyplot` (`plt.`) | Método `Axes` Equivalente (`ax.`) |
|---|---|
| `plot(...)` | `ax.plot(...)` |
| `scatter(...)` | `ax.scatter(...)` |
| `bar(...)` | `ax.bar(...)` |
| `hist(...)` | `ax.hist(...)` |
| `title(...)` | `ax.set_title(...)` |
| `xlabel(...)` | `ax.set_xlabel(...)` |
| `ylabel(...)` | `ax.set_ylabel(...)` |
| `xlim(...)` | `ax.set_xlim(...)` |
| `ylim(...)` | `ax.set_ylim(...)` |
| `xticks(...)` | `ax.set_xticks(...)` e `ax.set_xticklabels(...)` |
| `legend()` | `ax.legend()` |
| `grid()` | `ax.grid()` |

```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - Módulos e Funcionalidades Adicionais

```ad-quote
title:
Além do `pyplot`, o Matplotlib possui módulos especializados para funcionalidades mais complexas.
```

```ad-quote
title:

| Componente | Propósito / Exemplo de Uso |
|---|---|
| **Estilos (`plt.style`)** | **Propósito:** Alterar a aparência global dos gráficos com estilos pré-definidos. <br> **Exemplo:** `plt.style.use('ggplot')` |
| **Cores (`matplotlib.colors`)** | **Propósito:** Módulo para manipulação de cores e mapas de cores (colormaps). <br> **Exemplo:** `ax.scatter(x, y, c=z, cmap='viridis')` |
| **Texto e Anotações (`ax.text`, `ax.annotate`)** | **Propósito:** Adicionar texto ou anotações em pontos específicos do gráfico. <br> **Exemplo:** `ax.annotate('Pico', xy=(np.pi/2, 1), xytext=(2, 1.5), arrowprops=dict())` |
| **Plotagem 3D (`mpl_toolkits.mplot3d`)** | **Propósito:** Ferramentas para criar gráficos de superfície, dispersão e linhas em 3D. <br> **Exemplo:** `from mpl_toolkits.mplot3d import Axes3D; ax = fig.add_subplot(111, projection='3d')` |
| **Animações (`matplotlib.animation`)** | **Propósito:** Criar animações a partir de uma sequência de frames. <br> **Exemplo:** `from matplotlib.animation import FuncAnimation` |
| **Widgets (`matplotlib.widgets`)** | **Propósito:** Adicionar elementos interativos como sliders e botões aos gráficos. <br> **Exemplo:** `from matplotlib.widgets import Slider` |

```
````

---

```python
def plotInfo(npArrayMemoryValues):

"""

Plota e salva um gráfico dos valores de memória.

"""

plt.figure(figsize=(10, 6))

plt.plot(range(len(npArrayMemoryValues)), npArrayMemoryValues, marker='o', linestyle='-')

# Melhoria: Adicionar rótulos para clareza

plt.title('Uso de Memória (RSS) Durante as Iterações')

plt.xlabel('Iteração do Loop')

plt.ylabel('Uso de Memória (MB)')

plt.grid(True)

plt.savefig("uso_de_memoria.png")

plt.show()
```

```python
import matplotlib.pyplot as plt
import numpy as np

# Dados
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

# Cria uma figura e uma grelha de 2 linhas por 1 coluna
# fig = a figura inteira
# ax = um array de "eixos" (axes), um para cada subplot
fig, ax = plt.subplots(nrows=2, ncols=1, figsize=(10, 8)) # 2 linhas, 1 coluna

# --- Plotar no primeiro subplot (ax[0]) ---
ax[0].plot(x, y1)
ax[0].set_title('Gráfico Seno')

# --- Plotar no segundo subplot (ax[1]) ---
ax[1].plot(x, y2, color='red')
ax[1].set_title('Gráfico Cosseno')

# Ajusta o layout para não haver sobreposição
fig.tight_layout()

# Salva a figura inteira (que contém os dois gráficos)
fig.savefig('graficos_combinados.png')
plt.close(fig)
```

```python
import matplotlib.pyplot as plt
import numpy as np

# Dados
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

# 1. Cria a figura inteira
plt.figure(figsize=(10, 8))

# 2. Ativa o primeiro subplot (grelha 2x1, posição 1)
plt.subplot(2, 1, 1) # (2 linhas, 1 coluna, seleciona o 1º)
plt.plot(x, y1)
plt.title('Gráfico Seno')

# 3. Ativa o segundo subplot (grelha 2x1, posição 2)
plt.subplot(2, 1, 2) # (2 linhas, 1 coluna, seleciona o 2º)
plt.plot(x, y2, color='red')
plt.title('Gráfico Cosseno')

# 4. Salva a figura inteira
plt.savefig('graficos_subplot_singular.png')
plt.close()
```