---
banner: "![[Pasted image 20260215205950.png]]"
---
---

```ad-done
title:
#### Fase 1 ) - Dados Nulos

```

---

````ad-quote
title:
##### **01 ) -** Variáveis NaN
```ad-quote
title:
<p align="justify">O impacto de ignorar ou tratar mal os dados faltantes é o equivalente a navegar com um mapa onde as pontes destruídas foram simplesmente apagadas do desenho: você acha que o caminho é seguro, mas a realidade é bem diferente.</p>
```

```ad-quote
title:
<p align="justify">Na ciência de dados e na estatística, o impacto se divide em três grandes problemas. Se você entender isso, saberá defender por que gastou tempo limpando os dados.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **01 ) -** Introdução de Viés - A Distorção da Realidade


```ad-quote
title:
Este é o perigo mais grave, associado principalmente ao _MNAR_ e ao _MAR_
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - O que é
```

```ad-quote
title:
<p align="justify">O viés ocorre quando a amostra que sobrou (os dados que você tem) não representa mais a população real. As médias, variâncias e correlações mudam artificialmente.</p>
```

```shell
# Imagine uma pesquisa de satisfação de um produto.

# Quem amou o produto responde.
# Quem odiou o produto responde.
# Quem achou "ok" (a maioria) tem preguiça e não responde (MNAR ou MAR).
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - O Impacto
```

```ad-quote
title:
<p align="justify">Se você calcular a média de satisfação apenas com os dados que tem, vai parecer que o produto gera reações extremas, quando na verdade a maioria das pessoas é indiferente. Seu modelo vai aprender uma regra falsa sobre o mundo.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **02 ) -** Perda de Poder Estatístico - A Incerteza

```ad-quote
title:
Este fenômeno representa o impacto primário do MCAR dentro de uma análise estatística.
`````

````ad-quote
title:

```ad-quote
title:
###### A ) - O que é
```

```ad-quote
title:
<p align="justify">Ocorre quando a ausência de dados, mesmo sendo puramente acidental, reduz o tamanho efetivo da amostra. Na estatística, uma base menor resulta em um erro padrão mais elevado, o que diminui a precisão das conclusões.</p>
```

```shell
# Tentar identificar uma música ouvindo apenas 3 segundos dela (MCAR). É muito mais difícil do que ouvir 30 segundos. Você não está enganado sobre a música, mas tem muito menos confiança sobre qual ela é.
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) - O Impacto
```
```ad-quote
title:
<p align="justify">A consequência direta é a dificuldade em provar que uma hipótese é verdadeira. A incerteza matemática cresce proporcionalmente à quantidade de dados perdidos, tornando os resultados menos robustos.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **03 ) -** Falha ou Degradação de Modelos de ML

```ad-quote
title:
A maioria dos modelos matemáticos de aprendizado de máquina não possui suporte nativo para entradas vazias.
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) - O que é
```

```ad-quote
title:
<p align="justify">Trata-se de uma limitação técnica onde algoritmos baseados em álgebra linear exigem matrizes completas. A presença de um valor nulo interrompe o cálculo dos pesos durante o treinamento do modelo.</p>
```

```bash
# Um registro de cliente é deletado apenas por não conter a idade.

# O sistema descarta o histórico de compras e a localização que estavam preenchidos.

# A base de conhecimento do modelo é reduzida de forma ineficiente.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) - O Impacto
```

```ad-quote
title:
<p align="justify">A utilização de soluções simplistas, como a exclusão de linhas, causa uma degradação severa na performance preditiva. O modelo perde a capacidade de aprender padrões complexos devido ao descarte de informações correlacionadas.</p>
```
`````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 ) -** Resumo do Impacto por Tipo

```ad-quote
title:

|**Tipo**|**O Grande Risco**|**O que acontece se eu deletar as linhas com falhas?**|
|---|---|---|
|**MCAR**|Perda de precisão (Poder Estatístico).|Seguro, mas ineficiente. Você não cria mentiras (viés), mas joga fora dados úteis e aumenta sua incerteza.|
|**MAR**|Viés nas estimativas (Distorção).|Perigoso. Ao deletar, você muda o perfil da população (ex: deleta desproporcionalmente as mulheres do dataset). O modelo fica enviesado.|
|**MNAR**|Viés severo e difícil de corrigir.|Catastrófico. Você elimina justamente o grupo que tem o comportamento que você queria estudar. O modelo aprende o oposto da realidade.|

```
````

---

```ad-done
title:
#### Fase 2 ) - Anatomia da Aleatoriedade em Dados Faltantes

```

---

````ad-quote
title:
##### **01 ) -** O Conceito de Aleatório
```ad-quote
title:
<p align="justify">Na linguagem do dia a dia, aleatório significa caos. Na Estatística, aleatório significa Probabilidade. Quando um dado falta, não dizemos que não há causa, mas que a falta segue uma regra matemática definida.</p>
```

```ad-quote
title:
<p align="justify">A grande confusão reside na diferença entre a probabilidade que afeta a todos igualmente e aquela que muda conforme as características do indivíduo.</p>
```

>[!quote] **Note** [[Prob - Definição da Aleatoriedade]]

````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **01 ) -** MCAR - Missing Completely at Random - O Acidente Puro


```ad-quote
title:
A falta de dados não tem correlação com nenhuma variável do seu banco de dados.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - O que é
```

```ad-quote
title:
<p align="justify">Trata-se de uma causa externa e imprevisível. É o erro do sensor ou o café derramado na ficha técnica que impede a leitura da informação, independentemente do valor que ali estaria.</p>
```

```shell
# Imagine jogar um dado para cada registro do dataset.

# Se o resultado for 6, apagamos o valor daquela célula.
# Não importa se o paciente é jovem, idoso, rico ou pobre.
# A chance de o dado sumir é a mesma para todos (Puro Acidente).
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - O Impacto
```

```ad-quote
title:
<p align="justify">Se você excluir essas linhas, seu dataset fica menor, mas a média e a distribuição continuam fiéis à realidade. O custo aqui não é a mentira (viés), mas a perda de precisão estatística.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **02 ) -** MAR - Missing at Random - O Padrão Explicável

```ad-quote
title:
A falta de dados tem um padrão sistemático, mas esse padrão é explicado por outras colunas que você já possui.
````

````ad-quote
title:

```ad-quote
title:
###### A ) - O que é
```

```ad-quote
title:
<p align="justify">Ocorre quando um grupo específico tende a não responder, mas esse grupo é identificado por dados observados. É uma aleatoriedade condicional: é aleatório dentro do subgrupo.</p>
```

```shell
# No dataset do Titanic, quem não sobreviveu tem mais dados de idade faltando.

# Homens: Moeda (50% de chance de falta).
# Mulheres: Dado de 20 lados (5% de chance de falta).
# O padrão parece bagunçado no total, mas é previsível se você separar por sexo.
```

````

````ad-quote
title:
```ad-quote
title:
###### B ) - O Impacto
```
```ad-quote
title:
<p align="justify">É o cenário ideal para imputação. Como a explicação está visível em outras colunas, modelos de Machine Learning conseguem aprender a regra de omissão e preencher o buraco com maior segurança.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **03 ) -** MNAR - Missing Not at Random - O Padrão Invisível

```ad-quote
title:
A falta de dados depende diretamente do próprio valor que deveria estar preenchido naquela célula.
```

````

````ad-quote
title:
```ad-quote
title:
###### A ) - O que é
```

```ad-quote
title:
<p align="justify">O motivo da omissão é a própria informação oculta. É o caso da censura deliberada ou da vergonha, onde o valor extremo causa a sua própria ausência no banco de dados.</p>
```

```bash
# Pessoas com Renda Altíssima deixam o campo em branco por privacidade.

# Você não tem colunas que indiquem quem são esses ricos.
# Você apenas vê uma massa de dados nulos sem explicação aparente.
# O motivo da falta é o fato de o valor ser, por exemplo, maior que R$ 50.000.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) - O Impacto
```

```ad-quote
title:
<p align="justify">O perigo é altíssimo. Se você usar a média para preencher, errará gravemente, pois quem faltou não é a média (está no topo ou na base). Exige análise de sensibilidade ou consulta a especialistas.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 ) -** O Interrogatório dos Dados

```ad-quote
title:

|**Pergunta de Diagnóstico**|**Resultado SIM**|**Conceito Chave**|
|---|---|---|
|Existe padrão conectando a falta com outras colunas visíveis?|**MAR**|A explicação está nos dados que eu vejo.|
|Se eu soubesse o valor oculto, ele seria o motivo da omissão?|**MNAR**|O motivo é o próprio segredo.|
|Parece ser apenas um erro técnico ou azar sem ligações?|**MCAR**|Incerteza pura e simples.|

```
````

---
