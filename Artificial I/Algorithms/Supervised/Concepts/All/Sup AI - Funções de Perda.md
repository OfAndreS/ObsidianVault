
---

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Mean Absolute Error (MAE) / Erro Absoluto Médio_
```

````ad-quote
title:
```ad-quote
title:
###### A ) _**REGRESSÃO** - Univariada / Multivariada_
```

```ad-quote
title:
<p align="justify">Calcula a média das diferenças absolutas entre os valores reais e as predições do modelo. Como não eleva os valores ao quadrado, mede o erro de forma linear, tratando todas as distâncias de forma proporcional.</p>
```

```ad-quote
title:
<p align="justify">Especialmente recomendada quando o conjunto de dados possui outliers que não devem distorcer o comportamento geral do modelo.</p>
```
````

````ad-quote
title:
```ad-quote
title:
1. $$MAE = \frac{1}{n}\sum_{i=1}^{n}|y_i - \hat{y}_i|$$
```
- $n$: Número total de amostras analisadas.
- $y_i$: Valor contínuo real da amostra $i$.
- $\hat{y}_i$: Valor contínuo predito pelo modelo para a amostra $i$.
````

````ad-quote
title:
```ad-quote
title:
###### **Observação** 
```
```ad-quote
title:
<p align="justify">Embora seja robusto contra outliers, o MAE apresenta uma desvantagem matemática: sua derivada não é contínua no ponto zero. Isso pode causar instabilidade e oscilações no final do treinamento durante a otimização por gradiente descendente.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _Mean Squared Error (MSE) / Erro Quadrático Médio_
```

````ad-quote
title:
```ad-quote
title:
###### A ) _**REGRESSÃO** - Univariada / Multivariada_
```

```ad-quote
title:
<p align="justify">Calcula a média dos quadrados das diferenças entre os valores reais e as predições. A operação de elevação ao quadrado penaliza erros maiores de forma exponencial, fazendo com que desvios grandes gerem um custo altíssimo.</p>
```

```ad-quote
title:
<p align="justify">Ideal para cenários onde erros grandes são intoleráveis e o modelo precisa ser forçado a evitá-los ao máximo.</p>
```
````

````ad-quote
title:
```ad-quote
title:
2. $$MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2$$
```
- $n$: Número total de amostras analisadas.
- $y_i$: Valor contínuo real da amostra $i$.
- $\hat{y}_i$: Valor contínuo predito pelo modelo para a amostra $i$.
````

````ad-quote
title:
```ad-quote
title:
###### **Observação** 
```
```ad-quote
title:
<p align="justify">O MSE possui uma superfície de erro continuamente diferenciável, o que torna o cálculo dos gradientes muito estável. Contudo, se a base de dados contiver outliers gerados por ruído de medição, o MSE deslocará a reta de predição de forma drástica para tentar reduzir esses erros específicos.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.3 ) - _Root Mean Squared Error - RMSE_
```

````ad-quote
title:
```ad-quote
title:
###### A ) _**REGRESSÃO** - Univariada / Multivariada_
```

```ad-quote
title:
<p align="justify">Representa a raiz quadrada da média dos erros elevados ao quadrado. O seu propósito principal é corrigir uma distorção dimensional provocada pelo MSE. Ao aplicar a raiz quadrada sobre o resultado acumulado dos quadrados, a métrica de erro final retorna exatamente para a mesma unidade de medida original dos dados do problema.</p>
```

```ad-quote
title:
<p align="justify">Sendo altamente recomendada para cenários onde erros grandes não podem ser tolerados e o resultado da perda precisa ser interpretado diretamente na mesma escala física ou financeira da variável alvo (ex: metros, dólares, quilogramas).</p>
```
````

````ad-quote
title:

```ad-quote
title:
3. $$RMSE = \sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2}$$
```
- $n$: Número total de amostras analisadas.
    
- $y_i$: Valor contínuo real da amostra $i$.
    
- $\hat{y}_i$: Valor contínuo predito pelo modelo para a amostra $i$.

````

````ad-quote
title:

```ad-quote
title:
###### **Observação** 
```
```ad-quote
title:
<p align="justify">Por ser uma transformação monotônica do MSE, minimizar o MSE ou o RMSE leva exatamente ao mesmo ponto de convergência dos pesos do modelo. Por uma questão de eficiência computacional, a maioria das bibliotecas de Machine Learning utiliza o MSE internamente para calcular os gradientes durante o treinamento (poupando o custo de processar a raiz quadrada a cada iteração) e adota o RMSE apenas na etapa de validação e testes para gerar relatórios com leitura clara para engenheiros e cientistas de dados.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.4 ) - _Binary Cross-Entropy (BCE) / Log Loss_
```

````ad-quote
title:
```ad-quote
title:
###### A ) _**CLASSIFICAÇÃO** - Binária_
```

```ad-quote
title:
<p align="justify">Mede a distância entre duas distribuições de probabilidade para cenários binários. A penalidade cresce de forma logarítmica à medida que a probabilidade predita se afasta do rótulo real. Se o modelo errar com alto nível de certeza, a perda tende ao infinito.</p>
```

```ad-quote
title:
<p align="justify">Recomendada para problemas em que a saída do modelo é uma probabilidade entre 0 e 1 e deseja-se penalizar fortemente erros cometidos com alta confiança.</p>
```
````

````ad-quote
title:
```ad-quote
title:
4. $$BCE = -\frac{1}{n}\sum_{i=1}^{n}\left[y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i)\right]$$
```
- $n$: Número total de amostras analisadas.
- $y_i$: Rótulo real da amostra $i$ (obrigatoriamente o valor binário 0 ou 1).
- $\hat{y}_i$: Probabilidade estimada pelo modelo de a amostra $i$ pertencer à classe 1.
````

````ad-quote
title:
```ad-quote
title:
###### **Observação** 
```
```ad-quote
title:
<p align="justify">Para o uso correto desta fórmula, a saída final do modelo precisa ser mapeada estritamente no intervalo entre 0 e 1. Portanto, é obrigatório o uso da função de ativação <i>Sigmoid</i> na última camada da rede neural antes de computar a perda.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.5 ) - _Categorical Cross-Entropy (CCE) / Entropia Cruzada Multiclasse_
```

````ad-quote
title:

```ad-quote
title:
###### A ) _**CLASSIFICAÇÃO** - MULTICLASSE EXCLUDENTE_
```

```ad-quote
title:
<p align="justify">Generalização da entropia cruzada para problemas com mais de duas categorias. Ela calcula o logaritmo negativo da probabilidade predita associada estritamente à classe que representa o rótulo correto da amostra, ignorando as probabilidades das classes incorretas.</p>
```

```ad-quote
title:
<p align="justify">Indicada para tarefas como classificação de imagens entre gato, cachorro ou pássaro, onde as categorias são mutuamente exclusivas e a soma das probabilidades deve ser igual a 1.</p>
```
````

````ad-quote
title:
```ad-quote
title:
5. $$CCE = -\frac{1}{n}\sum_{i=1}^{n}\sum_{j=1}^{C} y_{i,j} \log(\hat{y}_{i,j})$$
```
- $n$: Número total de amostras analisadas.
- $C$: Quantidade total de classes existentes no problema.
- $y_{i,j}$: 1 se $j$ é a classe correta para a amostra $i$, senão 0.
- $\hat{y}_{i,j}$: Probabilidade que o modelo calculou para a amostra $i$ pertencer à classe $j$.
````

````ad-quote
title:
```ad-quote
title:
###### **Observação** 
```
```ad-quote
title:
<p align="justify">Esta formulação exige que os alvos reais y estejam codificados no formato <i>One-Hot Encoding</i> (vetores binários). Além disso, para assegurar que a soma de todas as probabilidades preditas seja igual a 1, a arquitetura deve utilizar a função de ativação <i>Softmax</i> na camada de saída.</p>
```
````

---