---
banner: "![[Pasted image 20251217151319.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O Pipeline como Filtro da Realidade

```ad-quote
title:
<p align="justify">No contexto de Risco de Crédito e Ciência de Dados, entender viéses não é um exercício de memorização enciclopédica, mas uma habilidade de diagnóstico. O viés é uma distorção que pode entrar em qualquer etapa do fluxo de trabalho: na coleta do passado, na construção do algoritmo ou na interpretação humana do futuro. Para dominar este tópico, dividimos o problema cronologicamente: o Antes (Dados), o Durante (Modelagem) e o Depois (Humano).</p>
```

![[Pasted image 20251217181130.png]]

```ad-quote
title:
<p align="justify">Para ilustrar, acompanharemos a jornada de Roberto, um aprendiz em um banco tradicional que está tentando modernizar o sistema de empréstimos. Os erros que Roberto encontra em seus arquivos, em suas calculadoras e em seus chefes ilustram perfeitamente as armadilhas que um Cientista de Dados deve evitar.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Systemic Bies

```ad-quote
title:
<p align="justify">Problemas que residem na matéria-prima. O dado já está contaminado antes mesmo de qualquer código ser escrito.</p>
```

```ad-quote
title:
###### **A Analogia de Roberto - O Arquivo Morto**
```

```ad-quote
title:
<p align="justify">Roberto vai ao porão do banco buscar os registros antigos para "ensinar" o computador. Ele encontra pastas de 1970. Nelas, ele nota que empréstimos eram sistematicamente negados a mulheres solteiras, não por falta de pagamento, mas por regras sociais da época (Viés Histórico). Ele também nota que a maioria das fichas é de clientes ricos, pois o banco não atendia bairros periféricos antigamente, deixando-o sem saber como avaliar a classe C (Viés de Representatividade). Por fim, ele vê que só existem fichas dos clientes aceitos; os rejeitados na porta nunca foram registrados, criando uma ilusão de que "todo mundo paga" (Viés de Sobrevivência).</p>
```


```ad-quote
title:
###### **Mapeamento Técnico**
```

```ad-quote
title:

|Tipo de Viés|Definição Técnica|Exemplo em Crédito|
|---|---|---|
|Histórico|O dataset reflete preconceitos sistêmicos e culturais preexistentes na sociedade.|O modelo aprende que "Mulher Solteira = Alto Risco" baseando-se em decisões machistas de décadas passadas.|
|Representatividade (Sample)|A distribuição do dataset de treino difere da população real onde o modelo será aplicado.|Treinar com 90% de clientes Classe A e tentar prever risco para Classe C, gerando alta incerteza.|
|Medida/Rótulo|O erro está na definição da variável alvo (Y). A métrica usada é um proxy imperfeito da realidade.|Usar "histórico de prisões" como sinônimo de "criminalidade". Em crédito, ocorre quando só temos o rótulo de quem foi aprovado (Selective Labels).|
|Sobrevivência|Concentração na análise apenas dos casos de sucesso ("sobreviventes"), ignorando os excluídos.|Analisar apenas o comportamento de quem pagou o empréstimo, ignorando as características cruciais de quem foi rejeitado inicialmente.|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Statistical and Computational Bies

```ad-quote
title:
###### **Conceito Central**
```

```ad-quote
title:
<p align="justify">Distorções introduzidas durante a engenharia de features ou na escolha do algoritmo, muitas vezes por simplificação excessiva.</p>
```

```ad-quote
title:
###### **A Analogia de Roberto - A Calculadora Simplista**
```

```ad-quote
title:
<p align="justify">Ao criar sua fórmula, Roberto comete erros de lógica. Ele nota que um bairro específico tem alta inadimplência e decide bloquear o CEP, sem perceber que aquele bairro é majoritariamente habitado por uma etnia específica; ele acabou de criar uma regra racista disfarçada de geográfica (Viés de Proxy). Além disso, ele tenta usar a mesma régua para medir uma padaria local e uma multinacional, misturando comportamentos incompatíveis na mesma análise (Viés de Agregação). Por fim, ele conclui que "Raça" causa inadimplência, simplesmente porque esqueceu de incluir a "Renda" na equação, que era a verdadeira causa (Viés de Variável Omitida).</p>
```


```ad-quote
title:
###### **Mapeamento Técnico**
```

```ad-quote
title:

|Tipo de Viés|Definição Técnica|Exemplo em Crédito|
|---|---|---|
|Variável Omitida|O modelo atribui efeito causal a uma variável porque a verdadeira variável explicativa foi esquecida.|O modelo culpa a "Raça" pela inadimplência porque a variável "Renda" (que explicaria a correlação) foi omitida.|
|Agregação|Utilização de um modelo único ("one-size-fits-all") para subgrupos com distribuições condicionais distintas.|Usar um único score para Pessoa Física e Pessoa Jurídica. As dinâmicas financeiras são opostas e o modelo falha para ambos.|
|Proxy|Uso de variáveis aparentemente neutras que se correlacionam fortemente com atributos protegidos.|Bloquear crédito baseando-se em CEP ou Modelo de Celular, que acabam servindo como disfarces para discriminar Raça ou Classe Social.|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Human Bies

```ad-quote
title:
###### **Conceito Central**
```

```ad-quote
title:
<p align="justify">Falhas cognitivas na interpretação dos resultados, na auditoria ou na tomada de decisão baseada no modelo.</p>
```

```ad-quote
title:
###### **A Analogia de Roberto - O Chefe Teimoso**
```

```ad-quote
title:
<p align="justify">Roberto apresenta o modelo ao seu gerente. O gerente tem certeza absoluta de que jovens não pagam contas. Quando o modelo confirma isso, ele aprova; quando o modelo diz o contrário, ele acha que é um "bug" (Viés de Confirmação). Mais tarde, o gerente começa a negar crédito para clientes antigos e confiáveis só porque o "sistema disse não", desligando seu próprio senso crítico (Viés de Automação). Para provar que o sistema é bom, Roberto faz o teste apenas com os clientes "fáceis", inflando artificialmente a nota do seu trabalho (Viés de Avaliação).</p>
```

```ad-quote
title:
###### **Mapeamento Técnico**
```

```ad-quote
title:

|Tipo de Viés|Definição Técnica|Exemplo em Crédito|
|---|---|---|
|Confirmação|Tendência de favorecer informações ou resultados que confirmam crenças preexistentes do analista.|Aceitar o modelo sem questionar quando ele confirma preconceitos (ex: jovens são maus pagadores) e auditar excessivamente quando ele os contradiz.|
|Automação|Confiança excessiva e acrítica nas decisões automatizadas, ignorando sinais contraditórios do contexto.|O gerente ignora o histórico impecável de um cliente antigo e nega o crédito apenas porque o algoritmo classificou como risco alto.|
|Avaliação|Uso de benchmarks inadequados ou dados de teste que não refletem a realidade de produção.|Validar o modelo apenas em clientes "padrão" e reportar 99% de acurácia, escondendo a falha total em perfis atípicos.|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **Conclusão )** - O Resumo Tático

```ad-quote
title:

|Tipo de Viés|Contexto|Definição Resumida|
|---|---|---|
|Viés Histórico|Dados Sociais|O passado do banco não é neutro.|
|Viés de Rótulo/Seleção|Selective Labels|O problema cego de só termos dados de quem aprovamos.|
|Viés de Proxy|Auditoria|O desafio de detectar discriminação escondida em variáveis neutras.|

```
````

---