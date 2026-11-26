---
banner: "![[Pasted image 20251217151319.png]]"
---

---

````ad-quote
title:

##### Intro ) - A Emergência da Consciência Algorítmica

```ad-quote
title:
<p align="justify">A disciplina de AI Fairness não nasceu de uma curiosidade teórica, mas como uma resposta urgente à automação de decisões sensíveis. Historicamente, a discriminação estatística era humana (como o "Redlining" dos anos 60). Com o advento do Big Data e Deep Learning (2000-2010), criou-se a ilusão da "Caixa Preta" neutra, onde se acreditava que a matemática seria imune a preconceitos. Essa ilusão ruiu em 2016 com o escândalo do algoritmo COMPAS, revelando que modelos podiam replicar racismo sistêmico. Hoje, vivemos a Era Regulatória (GDPR, LGPD), onde a governança é mandatória.</p>
```


````

---

> [!done] _New_

---

````ad-quote
title:

##### **01 ) -** Definição e Objetivo

```ad-quote
title:
###### Conceito Central
```

```ad-quote
title:
<p align="justify">A Mitigação de Vieses é o conjunto de intervenções no ciclo de vida do Machine Learning para corrigir disparidades que afetam grupos protegidos (raça, gênero, idade). O foco desloca-se da pura precisão matemática para a Equidade Algorítmica: impedir a reprodução de estigmas históricos.</p>
```

```ad-quote
title:
###### A Analogia da Balança Viciada
```

```ad-quote
title:
<p align="justify">Imagine uma balança digital usada para pesar mérito. Se a balança foi calibrada usando pesos "padrão" que eram historicamente mais leves para um grupo específico, ela sempre indicará que esse grupo tem "menos peso" (menos mérito), mesmo que a medição eletrônica esteja funcionando perfeitamente. A mitigação de viés não é sobre consertar o visor da balança, mas recalibrar o sensor para considerar as distorções estruturais dos pesos usados no passado.</p>
```

````

---

> [!done] _New_

---

````ad-quote
title:

##### **02 ) -** Tipos de Viés

```ad-quote
title:
###### Conceito Central
```

```ad-quote
title:
<p align="justify">O viés não surge do nada; ele é herdado dos dados, do desenho da coleta ou das escolhas de representação.</p>
```


```ad-quote
title:
###### Representação Técnica - Tipologia
```

```ad-quote
title:

|Origem|Descrição|
|---|---|
|Viés Histórico (Structural)|O dado reflete desigualdades reais e sistêmicas (ex: disparidade salarial histórica). O modelo aprende o padrão estatístico, mas ele é socialmente injusto.|
|Viés de Amostragem (Representation)|O dataset falha em representar a diversidade da população (ex: reconhecimento facial treinado majoritariamente com homens brancos).|
|Viés de Rótulo (Measurement)|O "gabarito" usado é imperfeito. Usar "prisões" como proxy para "crime" gera erro, pois certas áreas são mais policiadas que outras.|
|Variáveis Proxy|Atributos aparentemente neutros (CEP, histórico de navegação) que atuam como disfarces para atributos protegidos (raça, classe).|
```

````

---

> [!done] _New_

---

````ad-quote
title:

##### 03 ) - Métricas de Equidade 
```ad-quote
title:
###### Conceito Central
```

```ad-quote
title:
<p align="justify">Não existe uma definição única de "Justiça". Matematicamente, diferentes definições de equidade podem ser conflitantes entre si.</p>
```

```ad-quote
title:
###### Representação Técnica - As Três Réguas
```

```ad-quote
title:

|Métrica|Definição e Aplicação|
|---|---|
|Paridade Demográfica|Exige que a taxa de aprovação seja idêntica para todos os grupos, independente do mérito individual. Foca na igualdade de resultado.|
|Igualdade de Oportunidade|Exige que a taxa de acerto entre os qualificados (True Positives) seja igual. É o padrão para concessão de crédito, focando no mérito.|
|Calibração|Exige que um mesmo score de risco (ex: 70%) signifique a mesma probabilidade real de acontecimento para todos os grupos.|
```

````

---

> [!done] _New_

---

````ad-quote
title:

##### **04 ) -** Pipeline de Mitigação e Trade-off

```ad-quote
title:
###### Conceito Central
```

```ad-quote
title:
<p align="justify">A intervenção pode ocorrer em três estágios distintos do desenvolvimento do modelo, sempre considerando o "Custo da Justiça".</p>
```

```ad-quote
title:
###### Estratégias de Intervenção
```

```ad-quote
title:

|Estágio|Ação Técnica|
|---|---|
|Pré-processamento (Dados)|Atua antes do treino. Inclui rebalanceamento (reweighting) das amostras, remoção de correlações ou coleta de novos dados para melhorar a representatividade.|
|In-processamento (Algoritmo)|Atua durante o treino. Altera a função de perda (Loss Function) para penalizar estatisticamente a discriminação (ex: Adversarial Debiasing).|
|Pós-processamento (Decisão)|Atua após o treino. Ajusta os limiares de decisão (Thresholds) para cada grupo para compensar disparidades nas pontuações brutas.|
```

```ad-quote
title:
###### O Dilema Acurácia vs. Equidade
```

```ad-quote
title:
<p align="justify">Existe um trade-off inerente. Impor restrições de equidade geralmente causa uma leve redução na acurácia global do modelo quando comparada aos dados históricos (que são enviesados). O objetivo é encontrar o ponto ótimo (Pareto Frontier) onde a perda de performance é mínima e o ganho social é máximo.</p>
```


````

---