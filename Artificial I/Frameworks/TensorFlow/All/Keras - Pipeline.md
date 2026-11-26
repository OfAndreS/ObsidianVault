---
banner: "![[Pasted image 20251015133226.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O Fluxo de Trabalho e Hiperparâmetros em Keras

```ad-quote
title:
<p align="justify">Esta é a descrição de um pipeline genérico para projetos com Keras, focado principalmente em MLPs. No entanto, a mesma estrutura pode ser aplicada na maioria das aplicações que utilizam este framework.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - O Pipeline Padrão de um Projeto em Keras

```ad-quote
title:
<p align="justify">Toda implementação em Keras, do modelo mais simples ao mais complexo, segue um fluxo de trabalho lógico e sequencial. Dominar essa sequência torna o desenvolvimento muito mais intuitivo.</p>
```

```
meu_novo_projeto/
│
├── configs/
│   └── params.yml
│
├── data/
│   ├── raw/
│   └── processed/
│
├── models/
│
├── notebooks/
│   └── exploracao_de_dados.ipynb
│
├── src/
│   │
│   ├── Core/
│   │   ├── __init__.py
│   │   └── core.py       # Carregar o modelo e fazer previsões
│   │
│   ├── Training/
│   │   ├── __init__.py
│   │   └── training.py           # Orquestra o treinamento
│   │
│	│── Processing/
│	│	├── __init__.py
│	│	└──processing.py      # Carrega e pré-processa os dados
│	│
│   └── Shared/
│       ├── __init__.py
│       └── utils.py           # Funções úteis compartilhadas
│
│
└── requirements.txt
```

```ad-quote
title:
###### **Comandos para criação do projeto**
```

```bash
nano SetupProjeto.sh
```

```ad-quote
title:
Após crar o arquivo ".sh" com o nano, basta copiar e colar todos os comandos abaixo.
```

```bash
#!/bin/bash
# Script para criar a estrutura atualizada do projeto
# Execute este script DENTRO do diretório raiz do seu projeto (ex: ./meu_novo_projeto/)

echo "Criando diretórios..."

# Criar as pastas principais
mkdir -p configs
mkdir -p data/raw
mkdir -p data/processed
mkdir -p models
mkdir -p notebooks

# Criar as subpastas de src (com a primeira letra maiúscula conforme o diagrama)
mkdir -p src/Core
mkdir -p src/Training
mkdir -p src/Processing
mkdir -p src/Shared

echo "Criando arquivos..."

# Arquivos da raiz e configurações
touch requirements.txt
touch configs/params.yml
touch notebooks/exploracao_de_dados.ipynb

# Arquivos do módulo Core
touch src/Core/__init__.py
touch src/Core/core.py

# Arquivos do módulo Training
touch src/Training/__init__.py
touch src/Training/training.py

# Arquivos do módulo Processing
touch src/Processing/__init__.py
touch src/Processing/processing.py

# Arquivos do módulo Shared
touch src/Shared/__init__.py
touch src/Shared/utils.py

# Listar a estrutura criada para verificação
echo "Estrutura de pastas e arquivos criada com sucesso:"
ls -R
```
```ad-quote
title:
Por fim, o comando chmod serve para informar ao sistema operacional que o arquivo "SetupProjeto.sh" agora é executavel. Sendo, o "+x" responsável por adicionar a permição necessária para a execução.
```

```bash
chmod +x SetupProjeto.sh

./SetupProjeto.sh
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Carga e Preparação dos Dados

```ad-quote
title:
<p align="justify">Nenhuma rede neural funciona sem dados. Esta é a base de tudo.</p>
```

```ad-quote
title:
###### **Carga dos Dados:**
```

```ad-quote
title:
<p align="justify">Ler os dados de arquivos (CSV, imagens, etc.) ou usar datasets prontos (como os do keras.datasets).</p>
```

```ad-quote
title:
###### **Análise Exploratória - EDA:**
```

```ad-quote
title:
<p align="justify">Entender a distribuição dos dados, a quantidade de amostras por classe, a presença de valores ausentes, etc.</p>
```

```ad-quote
title:
###### **Pré-processamento:**
```

```ad-quote
title:
<p align="justify">Transformar os dados brutos em um formato que a rede neural possa consumir eficientemente. Isso inclui:</p>
```

```ad-quote
title:

|Técnica de Pré-processamento|Descrição e Objetivo|
|---|---|
|Normalização/Padronização|Colocar os dados em uma escala comum (ex: 0 a 1 para normalização, ou média 0 e desvio padrão 1 para padronização). Isso é Crucial para a convergência do modelo.|
|Codificação - Encoding|Transformar variáveis categóricas em números (ex: One-Hot Encoding para labels de classificação com keras.utils.to_categorical).|
|Redimensionamento - Reshaping|Ajustar o formato (shape) do tensor de entrada. Por exemplo, para uma CNN, uma imagem de 28x28 pixels precisa ser um tensor de (28, 28, 1) ou (28, 28, 3).|
|Divisão em Treino, Validação e Teste|Separar o conjunto de dados para treinar, ajustar e avaliar o modelo de forma imparcial.|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Definição da Arquitetura do Modelo

```ad-quote
title:
<p align="justify">Aqui você constrói o "cérebro" da sua aplicação. Em Keras, isso geralmente é feito de duas formas:</p>
```

```ad-quote
title:
###### **API Sequencial - keras.Sequential:**
```

```ad-quote
title:
<p align="justify">Ideal para a maioria dos casos, onde as camadas são empilhadas em uma sequência linear, uma após a outra.</p>
```

```python
from tensorflow import keras
from keras import layers

model = keras.Sequential([
    layers.Input(shape=(784,)), # Camada de entrada
    layers.Dense(128, activation='relu'), # Camada oculta
    layers.Dropout(0.2),
    layers.Dense(10, activation='softmax') # Camada de saída
])
```

```ad-quote
title:
###### **API Funcional - keras.Model:**
```

```ad-quote
title:
<p align="justify">Mais flexível e poderosa, usada para modelos com múltiplas entradas/saídas, branches compartilhadas ou arquiteturas mais complexas (como Redes Residuais - ResNets).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Compilação do Modelo

```ad-quote
title:
<p align="justify">Antes de treinar, você precisa configurar o processo de aprendizagem. Isso é feito com o método model.compile().</p>
```

```ad-quote
title:
|Componente de Compilação|Descrição e Objetivo|
|---|---|
|Otimizador - optimizer|O algoritmo que ajustará os pesos da rede para minimizar o erro (ex: Adam, SGD, RMSprop).|
|Função de Perda - loss|A métrica que o otimizador tentará minimizar. A escolha depende do tipo de problema (ex: `categorical_crossentropy` para classificação multiclasse, `binary_crossentropy` para binária, `mse` para regressão).|
|Métricas - metrics|Métricas adicionais para monitorar o desempenho durante o treino e teste, mas que não são usadas para otimizar o modelo (ex: accuracy, precision, recall).|
```

```python
model.compile(optimizer='adam',
              loss='categorical_crossentropy',
              metrics=['accuracy'])
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Treinamento do Modelo

```ad-quote
title:
<p align="justify">É aqui que a mágica acontece. O modelo aprende a partir dos dados de treino usando o método model.fit().</p>
```

```ad-quote
title:

|Parâmetro|Finalidade|
|---|---|
|Dados de Treino|`x_train` e `y_train`.|
|Épocas - epochs|O número de vezes que o modelo verá o conjunto de dados de treino completo.|
|Tamanho do Lote - batch_size|O número de amostras que o modelo processa antes de atualizar os pesos.|
|Dados de Validação - validation_data|Um conjunto de dados separado para avaliar o modelo ao final de cada época, ajudando a identificar overfitting.|
```

```python
history = model.fit(x_train, y_train,
                    epochs=10,
                    batch_size=32,
                    validation_data=(x_val, y_val))
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **06 )** - Avaliação do Modelo

```ad-quote
title:
<p align="justify">Após o treino, você precisa verificar o desempenho final do modelo em um conjunto de dados que ele nunca viu: o conjunto de teste. Isso é feito com o model.evaluate().</p>
```

```python
test_loss, test_acc = model.evaluate(x_test, y_test, verbose=2)
print(f'\nAcurácia no teste: {test_acc}')
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **07 )** - Inferência - Fazer Previsões

```ad-quote
title:
<p align="justify">Com um modelo treinado e avaliado, você pode usá-lo para fazer previsões em novos dados com model.predict().</p>
```

```python
predictions = model.predict(new_data)
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **08 )** - Checklist de Hiperparâmetros para Otimização

```ad-quote
title:
<p align="justify">Estes são os "botões" que você pode girar para ajustar o comportamento e o desempenho da sua rede. É aqui que sua pesquisa em otimização entra em jogo.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **09 )** - Hiperparâmetros da Arquitetura da Rede

```ad-quote
title:
<p align="justify">Definem a estrutura do modelo.</p>
```

```ad-quote
title:

|Hiperparâmetro&nbsp; | O que é?&nbsp; | Dicas e Observações |
| :--- | :--- | :--- |
|**Número de Camadas Ocultas**|A profundidade da rede.|Comece com poucas (1 a 3) e aumente se o modelo apresentar Underfitting (não aprender bem). Redes muito profundas podem sofrer com o desaparecimento do gradiente.|
|**Número de Neurônios por Camada**|A largura da rede em cada camada.|Não há regra fixa. Padrões comuns são potências de 2 (32, 64, 128, 256). Camadas em formato de "funil" (diminuindo o número de neurônios) são comuns.|
|**Função de Ativação**|Define a saída de um neurônio. Introduz não-linearidade.|**relu:** Padrão ouro para camadas ocultas. É computacionalmente eficiente. **sigmoid:** Usada na camada de saída para classificação binária. **softmax:** Usada na camada de saída para classificação multiclasse. **tanh:** Similar à sigmoid, mas mapeia para [-1, 1].|
|**Inicializador de Pesos (kernel_initializer)**|O método para definir os pesos iniciais da rede.|**glorot_uniform** (padrão para Dense) e **he_normal** (bom para relu) são excelentes pontos de partida. Uma má inicialização pode impedir a convergência.|
|**Regularização (kernel_regularizer)**|Técnica para penalizar pesos grandes e evitar Overfitting.|**L1:** Pode zerar alguns pesos (bom para feature selection). **L2 (Weight Decay):** Penaliza pesos grandes, forçando uma distribuição mais suave. É a mais comum.|
|**Dropout**|Técnica de regularização que "desliga" aleatoriamente neurônios durante o treino para evitar que a rede dependa demais de alguns caminhos específicos.|Um valor entre 0.2 e 0.5 é um bom ponto de partida. Geralmente colocado após camadas densas ou convolucionais.|
|**Batch Normalization**|Normaliza a saída de uma camada antes de passar para a próxima.|Ajuda a estabilizar e acelerar o treinamento, permitindo taxas de aprendizado mais altas. Geralmente inserida entre a camada linear e a função de ativação.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **10 )** - Hiperparâmetros do Processo de Treinamento

```ad-quote
title:
<p align="justify">Controlam como o modelo aprende.</p>
```

```ad-quote
title:

|Hiperparâmetro&nbsp; | O que é?&nbsp; | Dicas e Observações |
| :--- | :--- | :--- |
|**Otimizador (optimizer)**|O algoritmo de otimização.|**Adam:** É o padrão hoje em dia. Robusto, rápido e geralmente funciona bem com pouca configuração. **SGD (com momentum):** Pode alcançar melhores resultados, mas exige mais ajuste fino da taxa de aprendizado. **RMSprop**, **Adagrad.**|
|**Taxa de Aprendizado (learning_rate)**|O Mais Importante. O tamanho do passo que o otimizador dá para minimizar a função de perda.|Pequena demais: A convergência será muito lenta. Grande demais: O otimizador pode "pular" o mínimo e divergir. Comece com o padrão do Adam (geralmente 0.001) e ajuste (ex: 1e-4, 1e-5).|
|**Função de Perda (loss)**|Como o erro do modelo é calculado.|**categorical_crossentropy:** Classificação multiclasse (labels com one-hot encoding). **sparse_categorical_crossentropy:** Classificação multiclasse (labels como inteiros). **binary_crossentropy:** Classificação binária. **mse / mae:** Regressão.|
|**Número de Épocas (epochs)**|Quantas vezes o dataset de treino é percorrido.|Treine por épocas suficientes até que a perda de validação comece a estagnar ou aumentar. Use EarlyStopping (um callback) para parar automaticamente.|
|**Tamanho do Lote (batch_size)**|Número de amostras por atualização do gradiente.|Pequeno: Treino mais lento e ruidoso, mas pode generalizar melhor. Grande: Treino mais rápido, usa mais memória e pode convergir para mínimos locais "sharp" (ruins). Valores comuns são 32, 64, 128.|
|**Callbacks**|Funções para executar em diferentes pontos do treinamento.|**EarlyStopping:** Para o treino quando uma métrica (ex: val_loss) para de melhorar. Essencial para evitar overfitting e economizar tempo. **ModelCheckpoint:** Salva o melhor modelo encontrado durante o treino. **ReduceLROnPlateau:** Reduz a taxa de aprendizado quando o treino estagna.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **Conclusão )**

```ad-quote
title:
<p align="justify">Lembre-se que a busca pelos melhores hiperparâmetros é um processo experimental. Técnicas como Grid Search, Random Search ou Otimização Bayesiana (usando ferramentas como Keras Tuner ou Optuna) podem automatizar esse processo.</p>
```

```ad-quote
title:
<p align="justify">Espero que este guia detalhado ajude você em seus estudos e projetos na UFRN! Se tiver mais dúvidas, pode perguntar.</p>
```
````

---