
---

### Estrutura de Diretório Sugerida

```
digit_classifier/
├── configs/
│   └── params.yml
│
├── data/
│   └── (Este diretório pode ficar vazio, mas é boa prática para dados externos)
│
├── logs/
│   └── (Logs do TensorBoard serão salvos aqui)
│
├── models/
│   └── (Modelos treinados serão salvos aqui, ex: digit_classifier.h5)
│
├── reports/
│   └── figures/
│       └── (Gráficos e visualizações salvas)
│
├── src/
│   ├── __init__.py
│   ├── data_processing.py
│   ├── model.py
│   ├── train.py
│   ├── evaluate.py
│   └── utils.py
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

### Explicação Detalhada de Cada Componente

#### 📂 `configs/`

Contém arquivos de configuração para evitar "hardcoding" (deixar valores fixos no meio do código).

- **`params.yml`**: Um arquivo YAML (ou JSON) para guardar parâmetros que você pode querer ajustar, como o número de épocas, tamanho do lote (batch size), número de neurônios, caminhos de arquivos, etc.
    
    YAML
    
    ```
    # Exemplo de params.yml
    data:
      test_split_ratio: 0.2
      random_state: 42
    
    training:
      epochs: 20
      batch_size: 32
      validation_split: 0.1
    
    model:
      neurons_layer1: 128
      neurons_layer2: 64
      output_classes: 10
      input_shape: 64
    ```
    

#### 📂 `data/`

Diretório destinado a armazenar os dados. Embora neste projeto o dataset seja carregado diretamente do Scikit-learn, em um projeto real, você teria aqui os arquivos brutos (ex: `digits.csv`).

#### 📂 `logs/`

Destinado a salvar os logs de treinamento para análise posterior, principalmente para o **TensorBoard**. Cada execução do script de treino criaria uma subpasta com timestamp aqui dentro.

#### 📂 `models/`

Local onde os artefatos do modelo treinado são salvos (ex: arquivos `.h5` ou o formato `SavedModel` do TensorFlow). Isso permite que você carregue um modelo já treinado para fazer previsões sem precisar treiná-lo novamente.

#### 📂 `reports/`

Contém os resultados e visualizações gerados pelo projeto.

- **`figures/`**: Subdiretório para salvar os gráficos, como a curva de acurácia/perda e a visualização das previsões.
    

#### 📂 `src/` (Source Code)

O coração do projeto, contendo todo o código Python de forma modular.

- **`__init__.py`**: Um arquivo (geralmente vazio) que indica ao Python que o diretório `src/` é um pacote, permitindo importações relativas entre os módulos.
    
- **`data_processing.py`**:
    
    - **Responsabilidade:** Carregar, escalar e dividir os dados.
        
    - **Funções:** `load_and_prepare_data(test_size, random_state)`.
        
- **`model.py`**:
    
    - **Responsabilidade:** Definir a arquitetura do modelo Keras.
        
    - **Funções:** `build_classifier_model(input_shape, num_classes, units_l1, units_l2)`.
        
- **`train.py`**:
    
    - **Responsabilidade:** Orquestrar o processo de treinamento.
        
    - **Lógica:**
        
        1. Carrega os parâmetros do `configs/params.yml`.
            
        2. Chama a função de `data_processing.py` para obter os dados.
            
        3. Chama a função de `model.py` para construir a arquitetura.
            
        4. Compila e treina o modelo (`.compile()`, `.fit()`).
            
        5. Salva o modelo treinado na pasta `models/`.
            
        6. Salva os gráficos de treinamento em `reports/figures/`.
            
- **`evaluate.py`**:
    
    - **Responsabilidade:** Avaliar um modelo já treinado.
        
    - **Lógica:**
        
        1. Carrega um modelo salvo da pasta `models/`.
            
        2. Carrega os dados de teste.
            
        3. Executa `.evaluate()` e exibe as métricas de desempenho.
            
        4. Pode gerar um relatório de classificação ou uma matriz de confusão.
            
- **`utils.py`**:
    
    - **Responsabilidade:** Conter funções de ajuda reutilizáveis.
        
    - **Funções:** Funções para salvar gráficos (`save_plots`), carregar configurações, etc.
        

#### Arquivos na Raiz do Projeto

- **`.gitignore`**: Especifica quais arquivos e pastas devem ser ignorados pelo Git (ex: `__pycache__/`, `logs/`, `models/`, ambientes virtuais).
    
- **`README.md`**: O documento principal do projeto. Explica o que o projeto faz, quais são as dependências e como executar os scripts (`train.py`, `evaluate.py`).
    
- **`requirements.txt`**: Lista todas as bibliotecas Python necessárias para o projeto (tensorflow, scikit-learn, numpy, matplotlib, PyYAML). Permite que outros configurem o ambiente facilmente com o comando `pip install -r requirements.txt`.
    

Essa estrutura separa claramente a **configuração**, os **dados**, o **código-fonte** e os **resultados**, tornando o projeto escalável, profissional e muito mais fácil de entender e colaborar.