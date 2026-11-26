
---

````ad-quote
title:
```ad-quote
title:
##### **1 ) -** Diagramas e Elementos Extremos
```

```ad-quote
title:
- [ ] 25 e 27 de maio[cite: 1, 2]
```

```ad-quote
title:

|Assunto|
|-|
|- Construção de Diagrama de Hasse.[cite: 1, 2]|
|- Diferenciação entre elemento máximo/mínimo e elemento máximal/minimal.[cite: 1, 2]|
|- Identificação de limitantes: limitante superior e limitante inferior de um subconjunto.[cite: 1, 2]|
|- Definição de cadeia e ordenação topológica.[cite: 1, 2]|
```

````

````ad-quote
title:
```ad-quote
title:
##### **2 ) -** Reticulados e Propriedades
```

```ad-quote
title:
- [ ] 29 de maio[cite: 1, 2]
```

```ad-quote
title:

|Assunto|
|-|
|- Estrutura base de Reticulados (lattices).|
|- Definição do menor limitante superior e maior limitante inferior.|
|- Propriedades de Idempotência, Comutatividade, Associatividade e Absorção.|
|- Análise de teoremas fundamentais aplicados à estrutura de reticulados.|
```

````

````ad-quote
title:
```ad-quote
title:
##### **3 ) -** Álgebra Booleana e Exercícios
```

```ad-quote
title:
- [ ] 01 de junho[cite: 2]
```

```ad-quote
title:

|Assunto|
|-|
|- Simplificação de expressões e demonstrações utilizando propriedades da álgebra booleana.|
|- Análise de isomorfismo entre reticulados e álgebra booleana.|
|- Resolução de exercícios: Diagramas de Hasse, ordenação topológica, elementos extremos, limitantes e álgebra booleana.|
|- Entrega da prova.|
```

````

---
### Tipos de Questões Abordadas no Documento

A análise estrutural do material revela que as questões estão agrupadas em cinco categorias operacionais principais dentro da teoria das ordens.

### Construção e Interpretação de Diagramas de Hasse

O documento exige a conversão de grafos direcionados brutos, matrizes ou descrições de conjuntos em representações hierárquicas otimizadas.

- _Identificação de laços_: O primeiro passo é localizar e apagar mentalmente ou fisicamente todos os laços de autorreferência (nós que apontam para si mesmos), pois a reflexividade é presumida na estrutura.
    
- _Eliminação da transitividade_: Rastrei caminhos longos. Se existir uma aresta conectando um nó $a$ diretamente a um nó $c$, e também existir um caminho de $a$ para $b$ e de $b$ para $c$, a aresta direta de $a$ para $c$ é redundante e deve ser apagada da representação visual.
    
- _Orientação espacial_: Posicione os nós dominadores na parte superior e os subordinados na parte inferior. Ao garantir o fluxo unidirecional ascendente, as setas das arestas perdem a utilidade e devem ser removidas para limpar o diagrama.
    

### Mapeamento de Elementos Extremos

Diversas questões exigem a varredura do grafo para classificar a hierarquia terminal dos nós em maximais, minimais, máximos ou mínimos.

- _Isolamento local (Maximais e Minimais)_: Para achar os minimais, procure _qualquer_ nó na base estrutural que não possua arestas chegando por baixo. Para achar os maximais, procure _qualquer_ nó no topo que não possua arestas saindo por cima. É comum haver múltiplos nós nessa categoria simultaneamente.
    
- _Convergência global (Máximos e Mínimos)_: Verifique se os elementos isolados no passo anterior são únicos. Para que o diagrama possua um mínimo (o limite $0$), _todos_ os caminhos possíveis precisam nascer obrigatoriamente do mesmo nó basal. Para possuir um máximo (o limite $1$), _todos_ os caminhos precisam morrer obrigatoriamente no mesmo nó superior.
    

### Operações de Limitantes e Extremos Relativos

O material cobra a aplicação localizada das regras de conjunto para encontrar o supremo e o ínfimo de frações isoladas do reticulado.

- _Seleção do alvo_: Delimite estritamente o subconjunto exigido pelo enunciado (ex: $B=\{c, d, e\}$) e ignore temporariamente o resto do grafo.
    
- _Rastreamento superior e Supremo_: Siga as arestas subindo a partir de todos os elementos do subconjunto alvo. Todo nó que interceptar o caminho de _todos_ os elementos do alvo ao mesmo tempo é classificado como um limitante superior. Dentre essa lista de limitantes superiores, localize qual deles está posicionado geometricamente mais abaixo no gráfico. Esse nó exato é o _supremo_ (o menor limitante superior).
    
- _Rastreamento inferior e Ínfimo_: Inverta a lógica visual. Desça pelas arestas a partir do subconjunto alvo. Todo nó de encontro coletivo é um limitante inferior. Aquele que estiver posicionado geometricamente mais acima no gráfico é o _ínfimo_ (o maior limitante inferior).
    

### Ordenação Topológica

Exige-se a destruição sequencial do reticulado para convertê-lo em uma única estrutura de cadeia linear.

- _Extração da base_: Identifique um elemento minimal (nó sem subordinação prévia).
    
- _Transferência e quebra_: Remova esse nó do diagrama bidimensional e coloque-o como o primeiro item da sua nova cadeia linear. Apague instantaneamente todas as arestas que estavam conectadas a ele.
    
- _Repetição em loop_: O ato de apagar as arestas criará novos elementos minimais no que restou do diagrama. Repita a extração e a quebra sucessivamente até que o grafo original desapareça e reste apenas uma linha reta vertical.
    

### Provas e Simplificações Booleanas

As questões teóricas exigem atestar ou refutar propriedades lógicas de reticulados algébricos.

- _Verificação estrutural rápida_: Antes de calcular divisores ou complementaridade, aplique as regras visuais. Se o diagrama testado apresentar assimetria de eixos, esconder as formas proibidas (pentágonos ou diamantes no meio da estrutura) ou tiver um total de nós diferente das potências exatas de 2 ($2^n$), decrete a reprovação imediata.
    
- _Redução de expressões_: Para equações longas repletas de $\vee$ e $\wedge$, o algoritmo de resolução consiste em localizar padrões redundantes e substituí-los através das leis fornecidas nos teoremas documentados. As prioridades de substituição direta são a regra da _idempotência_ (remover literais duplicados) e a regra da _absorção_ (colapsar termos aninhados repetidos).
    

Qual dessas cinco tipologias tem causado a maior taxa de bloqueio analítico durante a sua resolução prática?