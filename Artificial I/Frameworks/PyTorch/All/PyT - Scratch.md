
---

Para criar um dataset customizado no PyTorch, basta herdar da classe `Dataset` e implementar três métodos básicos. O `__init__` carrega ou aponta para a fonte dos dados, o `__len__` retorna a quantidade total de linhas e o `__getitem__` busca uma amostra específica pelo índice, separando as features do rótulo (`label`).

```python
import pandas as pd
import torch
from torch.utils.data import Dataset

class WaterDataset(Dataset):
    def __init__(self, csv_path):
        super().__init__()
        df = pd.read_csv(csv_path)
        self.data = df.to_numpy()

    def __len__(self):
        return self.data.shape[0]

    def __getitem__(self, idx):
        features = self.data[idx, :-1]
        label = self.data[idx, -1]
        return features, label

```

Depois de instanciar o dataset, usamos o `DataLoader` para organizar a entrega desses dados ao modelo. Ele agrupa as amostras em lotes (`batch_size`) e embaralha a ordem dos dados a cada época (`shuffle=True`), o que evita que a rede vicie na sequência original do arquivo durante o treinamento.

```python

dataset_train = WaterDataset(
    "water_train.csv"
)

from torch.utils.data import DataLoader

dataloader_train = DataLoader(
    dataset_train,
    batch_size=2,
    shuffle=True,
)

```

---

Uma arquitetura padrão no PyTorch define as camadas e parâmetros treináveis no método construtor `__init__`, enquanto o método `forward` executa a passagem direta (forward pass) dos dados tanto no treino quanto na inferência.

```python
import torch
import torch.nn as nn
import torch.nn.functional as F

class Net(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc1 = nn.Linear(9, 16)
        self.fc2 = nn.Linear(16, 8)
        self.fc3 = nn.Linear(8, 1)

    def forward(self, x):
        x = F.relu(self.fc1(x))
        x = F.relu(self.fc2(x))
        x = torch.sigmoid(self.fc3(x))
        return x

net = Net()

```

---

O processo de treinamento no PyTorch inicia com a definição da função de perda e do otimizador. O código usa dois loops aninhados: o loop externo itera pelas épocas e o loop interno itera pelos lotes de dados (_batches_). Em cada lote, o algoritmo zera os gradientes acumulados, executa a passagem direta (_forward pass_), calcula a perda, propaga os gradientes (_backward pass_) e atualiza os pesos do modelo.

```python
import torch
import torch.nn as nn
import torch.optim as optim

# Loss function and optimizer initialization
criterion = nn.BCELoss()
optimizer = optim.SGD(net.parameters(), lr=0.01)

# Training loop
for epoch in range(1000):
    for features, labels in dataloader_train:
        optimizer.zero_grad()
        outputs = net(features)
        loss = criterion(outputs, labels.view(-1, 1))
        loss.backward()
        optimizer.step()

```

---

O processo de avaliação inicia com a definição da métrica de acurácia binária. Em seguida, o modelo entra em modo de avaliação e desativa os gradientes. O código itera pelos lotes de teste no Data Loader. A rede processa os dados de entrada e gera probabilidades. O algoritmo converte as probabilidades em rótulos binários pelo limiar de 0,5. A métrica acumula os resultados de cada lote. No final, o programa calcula e imprime a acurácia consolidada.

```python
from torchmetrics import Accuracy

acc = Accuracy(task="binary")

net.eval()
with torch.no_grad():
    for features, labels in dataloader_test:
        outputs = net(features)
        preds = (outputs >= 0.5).float()
        acc(preds, labels.view(-1, 1))

accuracy = acc.compute()
print(f"Accuracy: {accuracy}")

```

----
