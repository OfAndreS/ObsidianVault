
---
#### 1. PyTorch Puro: Padrão POO Clássico

No PyTorch puro, a Programação Orientada a Objetos é a abordagem canônica. Você herda de `nn.Module`, declara as camadas no método `__init__` e define o fluxo dos tensores no método `forward`.

```python
import torch
import torch.nn as nn
from torch.utils.data import DataLoader, TensorDataset


# 1. Definição da arquitetura via POO
class ClassificadorBinario(nn.Module):

    def __init__(self, dimensao_entrada: int):
        super().__init__()
        self.camada_linear = nn.Linear(dimensao_entrada, 1)
        self.ativacao = nn.Sigmoid()

    def forward(self, x: torch.Tensor) -> torch.Tensor:
        x = self.camada_linear(x)
        return self.ativacao(x)


# 2. Dados e inicialização
dados_x = torch.randn(100, 2)
dados_y = torch.randint(0, 2, (100, 1)).float()
carregador = DataLoader(TensorDataset(dados_x, dados_y), batch_size=16)

modelo = ClassificadorBinario(dimensao_entrada=2)
criterio = nn.BCELoss()
otimizador = torch.optim.SGD(modelo.parameters(), lr=0.01)

# 3. Loop de treino explícito
for epoca in range(3):
    modelo.train()
    for lote_x, lote_y in carregador:
        otimizador.zero_grad()
        saida = modelo(lote_x)
        perda = criterio(saida, lote_y)
        perda.backward()
        otimizador.step()

```

---

### 2. PyTorch Ignite: Padrão Idiomático de Motores e Eventos

O padrão recomendado no Ignite utiliza fábricas de alto nível como `create_supervised_trainer`. Você não precisa escrever a lógica do passo de treino manualmente.

Você registra funções decoradas que escutam eventos emitidos pelo motor (`Engine`).

```python
from ignite.engine import Events, create_supervised_trainer
import torch
import torch.nn as nn
from torch.utils.data import DataLoader, TensorDataset

carregador = DataLoader(
    TensorDataset(torch.randn(100, 2), torch.randint(0, 2, (100, 1)).float()),
    batch_size=16,
)

modelo = nn.Sequential(nn.Linear(2, 1), nn.Sigmoid())
otimizador = torch.optim.SGD(modelo.parameters(), lr=0.01)
criterio = nn.BCELoss()

# Criação do motor de treino supervisionado nativo
treinador = create_supervised_trainer(modelo, otimizador, criterio)


# Manipulador de eventos declarativo
@treinador.on(Events.EPOCH_COMPLETED)
def registrar_fim_epoca(engine):
    print(f"Época {engine.state.epoch} finalizada com sucesso.")


treinador.run(carregador, max_epochs=3)

```

---

### 3. PyTorch Lightning: Padrão de Engenharia de Ciclo de Vida

No Lightning, o padrão correto unifica a arquitetura e as regras de treino dentro de um `LightningModule`.

Você delega a execução, alocação de dispositivos e registros para o objeto `Trainer`.

```python
import pytorch_lightning as pl
import torch
import torch.nn as nn
from torch.utils.data import DataLoader, TensorDataset


class ModuloClassificacao(pl.LightningModule):

    def __init__(self):
        super().__init__()
        self.rede = nn.Sequential(nn.Linear(2, 1), nn.Sigmoid())
        self.criterio = nn.BCELoss()

    def forward(self, x):
        return self.rede(x)

    # Passo de treinamento obrigatório
    def training_step(self, lote, lote_idx):
        x, y = lote
        predicoes = self(x)
        perda = self.criterio(predicoes, y)
        self.log("perda_treino", perda)
        return perda

    # Definição do otimizador desacoplada do loop
    def configure_optimizers(self):
        return torch.optim.SGD(self.parameters(), lr=0.01)


carregador = DataLoader(
    TensorDataset(torch.randn(100, 2), torch.randint(0, 2, (100, 1)).float()),
    batch_size=16,
)

treinador = pl.Trainer(max_epochs=3, enable_progress_bar=False)
treinador.fit(ModuloClassificacao(), carregador)

```

---

### 4. Hugging Face Accelerate: Padrão Não Invasivo de Hardware

O Accelerate busca manter o código o mais próximo possível do Python nativo. Ele injeta gerenciamento de hardware por meio de uma única chamada `accelerator.prepare()`.

Você mantém o laço de treino manual, mas substitui o cálculo de gradiente por `accelerator.backward()`.

```python
from accelerate import Accelerator
import torch
import torch.nn as nn
from torch.utils.data import DataLoader, TensorDataset

accelerator = Accelerator()

carregador = DataLoader(
    TensorDataset(torch.randn(100, 2), torch.randint(0, 2, (100, 1)).float()),
    batch_size=16,
)

modelo = nn.Sequential(nn.Linear(2, 1), nn.Sigmoid())
criterio = nn.BCELoss()
otimizador = torch.optim.SGD(modelo.parameters(), lr=0.01)

# Prepara simultaneamente dados, modelo e otimizador para qualquer hardware
modelo, otimizador, carregador = accelerator.prepare(
    modelo, otimizador, carregador
)

for epoca in range(3):
    modelo.train()
    for lote_x, lote_y in carregador:
        otimizador.zero_grad()
        saida = modelo(lote_x)
        perda = criterio(saida, lote_y)
        accelerator.backward(perda)
        otimizador.step()

```

---

### Comparação de Paradigmas

| Framework | Paradigma Central | Ponto Central de Abstração | Manutenção do Loop `for` |
| --- | --- | --- | --- |
| **PyTorch Puro** | Programação Orientada a Objetos | `torch.nn.Module` | Sim (manual) |
| **PyTorch Ignite** | Orientado a Eventos (*Engine*) | `create_supervised_trainer` | Não (interno ao motor) |
| **PyTorch Lightning** | Engenharia de Ciclo de Vida | `LightningModule` + `Trainer` | Não (automatizado) |
| **HF Accelerate** | Injeção de Dependência de Hardware | `accelerator.prepare()` | Sim (manual assistido) |

---