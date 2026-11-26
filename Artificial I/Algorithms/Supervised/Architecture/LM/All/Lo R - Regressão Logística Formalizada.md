---
banner: "![[Pasted image 20260107191458.png]]"
---
---

````ad-quote
title:

##### **Intro )** - Algoritmo de Classificação - Regressão Logística

```ad-quote
title:
<p align="justify">A Regressão Logística é um modelo estatístico utilizado para prever a probabilidade de um evento pertencer a uma classe específica. Diferente da regressão linear, o objetivo aqui é mapear os dados para um intervalo discreto, geralmente entre 0 e 1, permitindo a tomada de decisão em problemas binários.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Etapa de Predição - Forward Pass

```ad-quote
title:
<p align="justify">Nesta fase inicial, o modelo transforma as entradas em uma probabilidade contínua através de dois passos matemáticos fundamentais.</p>
```

```ad-quote
title:
|**Componente**|**Descrição Detalhada**|**Papel na Análise**|
|---|---|---|
|**Combinação Linear**|Representa a soma ponderada das entradas pelos pesos do modelo.|Calcula a _pontuação bruta_ ou $z$ antes da ativação.|
|**Ativação Sigmoide**|Função matemática que comprime qualquer valor real para o intervalo [0, 1].|Transforma o resultado linear em uma _estimativa de probabilidade_.|
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) Combinação Linear - $z$
```

```ad-quote
title:
O modelo realiza o somatório das variáveis independentes multiplicadas pelos seus respectivos coeficientes, somado ao termo de intercepto.
```

```ad-quote
title:
- $$z = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \dots + \beta_n x_n$$
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Função Sigmoide - $\sigma$
```

```ad-quote
title:
Aplicamos a função logística para garantir que o _output_ represente a probabilidade de $y=1$ dado um conjunto de entradas $x$.
```

```ad-quote
title:
- $$P(y=1|x) = \sigma(z) = \frac{1}{1 + e^{-z}}$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Avaliação do Erro - Log Loss

```ad-quote
title:
<p align="justify">Para que o modelo aprenda, precisamos quantificar a distância entre a probabilidade prevista e o rótulo real (0 ou 1). Utilizamos a função de custo Log Loss.</p>
```

```ad-quote
title:
###### A ) Função de Custo ($J$)
```

```ad-quote
title:
Esta fórmula penaliza previsões confiantes que estão erradas, garantindo que o modelo busque parâmetros que maximizem a verossimilhança dos dados.
```

```ad-quote
title:
- $$J(\beta) = -\frac{1}{m} \sum_{i=1}^{m} [y^{(i)} \ln(p^{(i)}) + (1 - y^{(i)}) \ln(1 - p^{(i)})]$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Otimização - Gradient Descent

```ad-quote
title:
<p align="justify">O ajuste dos parâmetros ocorre através da minimização do erro. O algoritmo calcula a direção do declive máximo para atualizar os pesos de forma iterativa.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Cálculo do Gradiente
```

```ad-quote
title:
Determinamos a derivada parcial da função de custo em relação a cada peso para entender como alterar cada $\beta$ para reduzir o erro global.
```

```ad-quote
title:
- $$\frac{\partial J(\beta)}{\partial \beta_j} = \frac{1}{m} \sum_{i=1}^{m} (p^{(i)} - y^{(i)}) x_j^{(i)}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Regra de Atualização
```

```ad-quote
title:
O novo valor de cada coeficiente é obtido subtraindo o gradiente multiplicado pela _taxa de aprendizado_ ($\alpha$).
```

```ad-quote
title:
- $$\beta_j := \beta_j - \alpha \frac{\partial J(\beta)}{\partial \beta_j}$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Decisão Final - Inferência

```ad-quote
title:
<p align="justify">Após a obtenção das probabilidades, aplicamos um ponto de corte (threshold) para classificar o dado em uma categoria discreta.</p>
```

```ad-quote
title:
###### A ) Regra de Decisão
```

```ad-quote
title:
Utilizamos um valor crítico $k$ (geralmente 0.5) para definir o rótulo final $\hat{y}$.
```

```ad-quote
title:
- $$\hat{y} = \begin{cases} 1 & \text{se } \sigma(z) \geq k \\ 0 & \text{se } \sigma(z) < k \end{cases}$$
```
````

---

```ad-done
title:
##### **Fase 02 ) -** Execução em Python
```

---

````ad-quote
title:
```ad-quote
title:
###### C ) Código em Python
```

```ad-quote
title:

|**Elemento**|**Descrição**|**Papel na Estatística**|
|---|---|---|
|`LogisticRegression`|Classe que implementa o modelo de classificação linear.|Gerencia o processo de treinamento e inferência binária.|
|`predict_proba`|Método que retorna a probabilidade para cada classe.|Exibe o resultado direto da _ativação sigmoide_.|
|`predict`|Método que retorna a classe final (0 ou 1).|Aplica o _threshold_ de decisão automaticamente.|

```

```python
from sklearn.linear_model import LogisticRegression

# Inicialização e Treinamento
modelo_log = LogisticRegression()
modelo_log.fit(X_train, y_train)

# Predição de Probabilidades e Classes
probs = modelo_log.predict_proba(X_test)
classes = modelo_log.predict(X_test)

print(f"Probabilidades: {probs[0]}")
print(f"Classificação Final: {classes[0]}")
```

````

---
