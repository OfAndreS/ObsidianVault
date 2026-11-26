
---

````ad-quote
title:

##### **Intro )** - Anatomia de Redes Neurais: Ferramentas de Visualização

```ad-quote
title:
<p align="justify">Compreender a arquitetura de uma rede neural é uma etapa fundamental tanto para o desenvolvimento e depuração quanto para a comunicação de resultados. A visualização transforma um conceito abstrato de código em uma estrutura tangível, permitindo uma análise clara do fluxo de dados, da complexidade do modelo e do número de parâmetros. O ecossistema TensorFlow/Keras oferece um arsenal de ferramentas para essa finalidade, que vão desde resumos textuais instantâneos até dashboards interativos complexos.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - O Resumo Textual: model.summary()

```ad-quote
title:
**Função**
```

```ad-quote
title:
<p align="justify">O método `model.summary()` é a ferramenta de diagnóstico mais imediata. Ele imprime uma representação textual da arquitetura do modelo, listando sequencialmente cada camada, o formato de sua saída (OUTPUT SHAPE) e o número de parâmetros que ela contém (PARAM #).</p>
```

```ad-quote
title:
**Vantagens e Limitações**
```

```ad-quote
title:

| Vantagens | Limitações |
| --- | --- |
| INSTANTÂNEO E SIMPLES | Não é uma representação gráfica do fluxo de dados. |
| NENHUMA DEPENDÊNCIA EXTERNA | Em modelos complexos com múltiplos ramos (API Funcional), a estrutura linear pode ser menos intuitiva. |
| INFORMAÇÕES CRÍTICAS (PARÂMETROS) | Não exibe detalhes de conexão ou os tipos de dados. |

```

```ad-quote
title:
**Analisando a Saída**
```

```ad-quote
title:
<p align="justify">A saída do `summary` é rica em detalhes. A coluna OUTPUT SHAPE `(None, ...)` indica que o modelo pode aceitar lotes de qualquer tamanho; o `None` é um placeholder para a dimensão do BATCH. A coluna PARAM # mostra os parâmetros treináveis. Por exemplo, para uma camada DENSE com 128 unidades recebendo uma entrada de 784 características, o cálculo é `(784 pesos de entrada + 1 peso de bias) * 128 unidades = 100.480`.</p>
```

```ad-quote
title:
**Exemplo de Código**
```

```python
import tensorflow as tf

model = tf.keras.Sequential([
    tf.keras.layers.Input(shape=(28, 28)),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dense(128, activation='relu', name="camada_oculta"),
    tf.keras.layers.Dense(10, activation='softmax', name="camada_saida")
])

model.summary()
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - O Diagrama Estático: tf.keras.utils.plot_model()

```ad-quote
title:
**Função**
```

```ad-quote
title:
<p align="justify">Esta é a ferramenta nativa do Keras para gerar uma visualização gráfica e estática do modelo. Ela desenha cada camada como um nó e as conexões entre elas, criando uma imagem clara da arquitetura. É ideal para documentação, artigos acadêmicos e relatórios.</p>
```

```ad-quote
title:
**Ponto de Atenção: Dependências**
```

```ad-quote
title:
<p align="justify">Para que esta função opere, ela depende de um motor de renderização de grafos externo. É crucial instalar duas dependências:</p>
<p align="justify">1. <b>pydot (Biblioteca Python):</b> `pip install pydot`</p>
<p align="justify">2. <b>Graphviz (Software de Sistema):</b> Um binário que deve ser instalado diretamente no sistema operacional. Disponível em <a href="[https://graphviz.org/download/](https://graphviz.org/download/)">graphviz.org/download/</a>. A instalação via gerenciador de pacotes (como `apt` ou `brew`) também é uma opção.</p>
```

```ad-quote
title:
**Aprofundando os Parâmetros**
```

```ad-quote
title:

| Parâmetro | Descrição |
| --- | --- |
| `show_shapes` | (True/False) Exibe os formatos de entrada e saída de cada camada. Essencial para depuração. |
| `show_dtype` | (True/False) Mostra o tipo de dado (ex: 'float32') dos tensores. |
| `show_layer_activations`| (True/False) Indica a função de ativação utilizada em cada camada. |
| `rankdir` | Define a orientação do grafo. 'TB' (Top-to-Bottom) é o padrão. 'LR' (Left-to-Right) é útil para redes largas. |
| `dpi` | Define a resolução da imagem em pontos por polegada (dots per inch), útil para imagens de maior qualidade. |

```

```ad-quote
title:
**Exemplo de Código**
```

```python
import tensorflow as tf

# O mesmo modelo anterior
model = tf.keras.Sequential([
    tf.keras.layers.Input(shape=(28, 28), name="entrada_imagem"),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dense(128, activation='relu', name="camada_oculta"),
    tf.keras.layers.Dense(10, activation='softmax', name="camada_saida")
])

tf.keras.utils.plot_model(
    model,
    to_file='arquitetura_modelo.png',
    show_shapes=True,
    show_dtype=True,
    show_layer_activations=True,
    rankdir='TB',
    dpi=96
)
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - O Dashboard Interativo: TensorBoard

```ad-quote
title:
**O que é?**
```

```ad-quote
title:
<p align="justify">O TENSORBOARD é a suíte de visualização oficial do TensorFlow. É muito mais do que um visualizador de grafos; é um dashboard completo para monitorar, depurar e otimizar o ciclo de vida do seu modelo de machine learning.</p>
```

```ad-quote
title:
**Além do Grafo**
```

```ad-quote
title:
<p align="justify">Na aba GRAPHS, você pode explorar a arquitetura de forma interativa. Mas o TENSORBOARD também oferece:</p>
<p align="justify">- <b>SCALARS:</b> Gráficos de métricas como perda (loss) e acurácia ao longo das épocas.</p>
<p align="justify">- <b>HISTOGRAMS e DISTRIBUTIONS:</b> Visualização de como os pesos e vieses do seu modelo mudam ao longo do tempo.</p>
<p align="justify">- <b>PROFILER:</b> Ferramenta para analisar e otimizar a performance computacional do seu modelo.</p>
```

```ad-quote
title:
**Como Funciona**
```

```ad-quote
title:
<p align="justify">1. <b>Instanciar o Callback:</b> Você cria uma instância do `tf.keras.callbacks.TensorBoard`, especificando um diretório para salvar os logs.</p>
<p align="justify">2. <b>Treinar com o Callback:</b> Você passa a instância na lista de `callbacks` do método `model.fit()`.</p>
<p align="justify">3. <b>Lançar o Servidor:</b> Após o treinamento, você abre um terminal e executa `tensorboard --logdir seu_diretorio_de_logs` para iniciar o dashboard local.</p>
```

```ad-quote
title:
**Exemplo de Código**
```

```python
import tensorflow as tf
from tensorflow.keras.callbacks import TensorBoard
import datetime

# ... definição do modelo e dados de treino ...

log_dir = "logs/fit/" + datetime.datetime.now().strftime("%Y%m%d-%H%M%S")
tensorboard_callback = TensorBoard(log_dir=log_dir, histogram_freq=1)

# Supondo que x_train e y_train existem
# model.fit(x_train, y_train, epochs=10, callbacks=[tensorboard_callback])
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **04 )** - O Visualizador Universal: Netron

```ad-quote
title:
**O que é?**
```

```ad-quote
title:
<p align="justify">NETRON é um visualizador de modelos de machine learning de código aberto e multiplataforma. Ele não é parte do TensorFlow, mas é uma ferramenta extremamente popular na comunidade. Sua principal vantagem é a simplicidade e a capacidade de abrir uma vasta gama de formatos de modelos salvos.</p>
```

```ad-quote
title:
**Vantagens e Uso**
```

```ad-quote
title:
<p align="justify">Para usar o NETRON, você não precisa escrever código. Basta salvar seu modelo treinado em um arquivo (como `.h5`, `.keras`, ou `.onnx`) e arrastá-lo para a interface do Netron (seja a versão web ou o aplicativo de desktop). Ele exibe um grafo interativo e limpo, onde você pode clicar em cada camada para inspecionar seus atributos, pesos e vieses. É a ferramenta ideal para inspecionar rapidamente modelos pré-treinados ou compartilhados por outros.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **Conclusão )** - Tabela Comparativa

```ad-quote
title:

| Ferramenta | Formato | Principal Vantagem | Caso de Uso Ideal |
| --- | --- | --- | --- |
| `model.summary()` | TEXTO (TABELA) | Simplicidade e rapidez, sem dependências. | Para uma verificação rápida de sanidade, ordem das camadas e contagem de parâmetros. |
| `plot_model()` | GRÁFICO (IMAGEM) | Gera um diagrama limpo e estático, ideal para documentação. | Para incluir a arquitetura em relatórios, artigos ou apresentações formais. |
| TENSORBOARD | GRÁFICO INTERATIVO | Completo e integrado ao ciclo de treino, monitora tudo. | Para depuração profunda, análise de performance e otimização do processo de treinamento. |
| NETRON | GRÁFICO INTERATIVO | Universal, simples (arrastar e soltar), ótimo para inspecionar arquivos. | Para analisar rapidamente um arquivo de modelo salvo (`.h5`, `.keras`) sem executar código. |

```
````

---
