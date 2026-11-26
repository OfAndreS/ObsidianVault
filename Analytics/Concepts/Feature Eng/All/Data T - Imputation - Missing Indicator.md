---
banner: "![[Pasted image 20260115190114.png]]"
---
---

````ad-quote
title:

##### **Intro )** - Missing Indicator

```ad-quote
title:
<p align="justify">A técnica de adicionar uma variável para capturar NA consiste em criar uma nova coluna binária para cada variável que possui dados faltantes. Esta abordagem transforma a falta de informação em uma feature explícita, permitindo que o modelo identifique padrões preditivos na própria ausência do dado original.</p>
```

````

> [!quote] **Link:** [Imputation - Add Missing Indicator](https://feature-engine.trainindata.com/en/1.8.x/user_guide/imputation/AddMissingIndicator.html)

---

```ad-done
title:

#### **Fase 1 ) - Caso Ideal**

```

---

````ad-quote
title:

##### **01 )** - Premissas e Contexto Teórico

```ad-quote
title:
<p align="justify">A fundamentação teórica desta técnica repousa na ideia de que a ausência não ocorre por acaso, mas carrega um significado intrínseco sobre a observação.</p>
```

```ad-quote
title:
|**Requisito**|**Descrição Técnica**|**Impacto no Modelo**|
|---|---|---|
|**Mecanismo MNAR**|Os dados são Missing Not At Random (não aleatórios).|O modelo aprende que a omissão do dado é um sinal preditivo.|
|**Duplo Sinal**|Combinação de um valor imputado com uma flag binária.|O algoritmo diferencia valores reais de valores estimados.|
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Cenário Ideal de Aplicação

```ad-quote
title:
<p align="justify">Diferente das imputações simples, o indicador de ausência é superior quando a falta da informação está correlacionada com a variável resposta (target).</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Valor Preditivo da Omissão
```

```ad-quote
title:
<p align="justify">Em cenários como análise de crédito, o fato de um cliente não declarar renda pode indicar um perfil de risco específico. O indicador permite que o modelo aprenda pesos distintos para quem informou e para quem omitiu o dado.</p>
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Complemento à Imputação Univariada
```

```ad-quote
title:
<p align="justify">É ideal quando se deseja usar média ou mediana, mas há receio de perder a informação da distribuição original. O indicador atua como uma compensação estatística, sinalizando onde a "mentira" da imputação foi inserida.</p>
```
````

---

```ad-done
title:

#### **Fase 2 ) - Características da Técnica**

```

---

````ad-quote
title:

##### **03 )** - Impactos Estatísticos Completos

```ad-quote
title:
<p align="justify">O uso de indicadores binários altera a estrutura do espaço de características, trazendo benefícios na captura de padrões, mas exigindo cautela com a eficiência do modelo.</p>
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) Expansão do Espaço de Atributos
```

```ad-quote
title:
A dimensionalidade do dataset pode dobrar se todas as colunas originais apresentarem valores nulos.
```

```ad-quote
title:
Este aumento exige atenção à maldição da dimensionalidade, especialmente em datasets com muitas colunas e poucas observações, podendo aumentar o tempo de treinamento.
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) Preservaçãoda Variância e Viés
```

```ad-quote
title:
Ao manter a marcação do dado ausente, evita-se que a substituição posterior mascare completamente a realidade.
```

```ad-quote
title:
O modelo consegue ajustar seus coeficientes para compensar o erro introduzido pela média ou mediana, mantendo a integridade da predição para o grupo de dados conhecidos.
```
````

````ad-quote
title:
```ad-quote
title:
###### C ) Risco de Multicolinearidade
```

```ad-quote
title:
Pode surgir uma correlação indesejada entre o novo indicador binário e outras variáveis explicativas.
```

```ad-quote
title:
Em modelos de regressão linear, isso deve ser monitorado de perto através do VIF (Variance Inflation Factor), pois pode instabilizar a estimativa dos coeficientes.
```
````

---

```ad-done
title:

#### **Fase 3 ) - Particularidade do Método**

```

---

````ad-quote
title:

##### **04 )** - Métrica de Impacto - Estrutura de Feature Engineering

```ad-quote
title:
<p align="justify">A maior particularidade é que este método é dependente: ele prepara o terreno para uma imputação subsequente, garantindo a rastreabilidade do erro.</p>
```


````

````ad-quote
title:

```ad-quote
title:
###### A ) Lógica de Transformação Binária
```

```ad-quote
title:
Para cada variável original, cria-se uma contraparte booleana que isola a ocorrência do nulo como uma nova dimensão de análise.
```

```ad-quote
title:
- $$I_{X} = \begin{cases} 1, & \text{se } x \text{ é nulo} \\ 0, & \text{se } x \text{ possui valor} \end{cases}$$
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) Composição do Dataset Final
```

```ad-quote
title:
O conjunto final de dados combina a informação "suavizada" pela imputação central com a precisão do indicador de ausência.
```

```ad-quote
title:
- $$X_{final} = \{X_{imputado}, I_{X}\}$$
```
````

---
