
---

````ad-quote
title:

##### **Intro )** - Desafios Clássicos de Modelagem Computacional

```ad-quote
title:
<p align="justify">Com certeza! Aqui está uma lista dos principais desafios clássicos para o treinamento em modelagem computacional, organizados por nível de dificuldade.</p>
```

```ad-quote
title:
<p align="justify">Esses problemas são "clássicos" porque cada um ensina um conjunto fundamental de habilidades e conceitos, formando uma base sólida para resolver problemas muito mais complexos no futuro.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **01 )** - 🚀 Nível Iniciante: Fundamentos e Lógica Direta

```ad-quote
title:
<p align="justify">Nesta fase, o objetivo é traduzir regras bem definidas em um programa funcional, aprendendo a lidar com estado, tempo discreto e aleatoriedade.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **1. Modelo de Crescimento Populacional (Exponencial e Logístico)**
```

```ad-quote
title:
<p align="justify">Simule o crescimento de uma população ao longo do tempo.</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">Comece com um modelo exponencial simples (ex: a população dobra a cada ano) e depois adicione uma "capacidade de suporte" do ambiente, transformando-o em um crescimento logístico que se estabiliza.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Loops, atualização de estado, feedback simples (no modelo logístico) e a base para sistemas dinâmicos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **2. O Passeio do Bêbado (Random Walk)**
```

```ad-quote
title:
<p align="justify">Um indivíduo começa no ponto (0,0) de uma grade.</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">A cada passo, ele se move aleatoriamente para norte, sul, leste ou oeste. Modele a trajetória dele por N passos e calcule a distância final da origem.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Geração de números aleatórios, manipulação de coordenadas (estado), e visualização de dados. É a base para entender processos estocásticos como o movimento de partículas ou a flutuação de preços de ações.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **3. Simulação de Monte Carlo para Roleta de Cassino**
```

```ad-quote
title:
<p align="justify">Modele uma roleta com suas probabilidades (números, cores, par/ímpar).</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">Simule milhares de rodadas com uma estratégia de aposta fixa (ex: sempre apostar no vermelho) e calcule o ganho/perda esperado do jogador e do cassino.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Probabilidade, geração de números aleatórios, e o conceito central do método de Monte Carlo: usar a aleatoriedade para estimar resultados.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **4. Simulação de Fila Simples (Um Caixa de Supermercado)**
```

```ad-quote
title:
<p align="justify">Clientes chegam a um caixa em intervalos de tempo variáveis (ex: entre 1 e 5 minutos).</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">O tempo para atender cada cliente também varia (ex: entre 2 e 6 minutos). Simule o sistema por algumas horas e meça o tamanho médio da fila e o tempo de espera médio.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Conceitos de teoria das filas, gerenciamento de eventos discretos e coleta de métricas de desempenho.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **02 )** - 🧠 Nível Intermediário: Interações e Sistemas Dinâmicos

```ad-quote
title:
<p align="justify">Aqui, os modelos envolvem múltiplos componentes que interagem entre si, muitas vezes resultando em comportamentos de grupo que não são óbvios apenas olhando as regras individuais.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **1. Modelo Predador-Presa (Equações de Lotka-Volterra)**
```

```ad-quote
title:
<p align="justify">Simule a dinâmica de duas populações: presas (ex: coelhos) e predadores (ex: raposas).</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">O número de coelhos aumenta na ausência de raposas, e o número de raposas aumenta com a abundância de coelhos. As raposas morrem de fome sem coelhos.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Modelar sistemas de equações diferenciais acopladas, observar ciclos e oscilações, e entender a dinâmica de sistemas ecológicos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **2. O Jogo da Vida de Conway**
```

```ad-quote
title:
<p align="justify">Um "autômato celular" em uma grade 2D. Cada célula pode estar "viva" ou "morta".</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">O estado de uma célula na próxima geração é determinado por regras simples baseadas no número de vizinhos vivos.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Manipulação de matrizes (grades), lógica de vizinhança e, mais importante, o conceito de emergência: como regras locais muito simples podem gerar padrões globais incrivelmente complexos e dinâmicos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **3. Modelo de Propagação de Doenças (SIR)**
```

```ad-quote
title:
<p align="justify">Divida uma população em três compartimentos: Suscetível, Infectado e Recuperado.</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">Modele como os indivíduos se movem entre esses compartimentos com base em uma taxa de contágio e uma taxa de recuperação.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Modelagem compartimental, um pilar da epidemiologia. Mostra como mudanças em parâmetros (ex: taxa de contágio) podem alterar drasticamente o resultado de uma epidemia (ex: o pico de infectados).</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **4. Modelo Balístico com Resistência do Ar**
```

```ad-quote
title:
<p align="justify">Calcule a trajetória de um projétil (ex: bala de canhão).</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">Diferente do modelo de física do ensino médio, inclua a força de arrasto do ar, que depende da velocidade do projétil.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Resolução numérica de equações diferenciais (ex: Método de Euler), modelagem de forças não-lineares e a importância de refinar modelos com fatores do mundo real.</p>
```
````

---

> [!example] **_New_**

---

````ad-quote
title:

##### **03 )** - 🌌 Nível Avançado: Comportamento Emergente e Alta Complexidade

```ad-quote
title:
<p align="justify">Estes desafios envolvem um grande número de agentes, interações complexas e, muitas vezes, exigem otimização de performance. O foco é entender fenômenos de larga escala que surgem de baixo para cima.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **1. Modelo de Segregação de Schelling**
```

```ad-quote
title:
<p align="justify">Um modelo clássico de "modelo baseado em agentes" (Agent-Based Model - ABM).</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">Agentes de dois grupos diferentes são distribuídos em uma grade. Cada agente quer viver em uma vizinhança onde pelo menos X% dos vizinhos são do mesmo grupo que ele. Se um agente está "infeliz", ele se muda para um local aleatório.</p>

<b>Principais Conceitos:</b>
- <p align="justify">A base de ABM, feedback social e como preferências individuais "leves" podem levar a uma segregação em nível macro muito forte e surpreendente.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **2. Simulação de Fluxo de Tráfego (Autômato Celular)**
```

```ad-quote
title:
<p align="justify">Modele carros em uma estrada de uma dimensão (uma fila).</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">Cada carro tem uma velocidade e segue regras simples: se não há nada na frente, acelere; se um carro está muito perto, desacelere; mova-se.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Como fenômenos complexos de tráfego (engarrafamentos "fantasmas" que surgem do nada) podem emergir de regras de decisão simples dos motoristas. É um ótimo exercício de otimização e análise de sistemas complexos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **3. Simulação de Dinâmica Molecular (Gás em uma Caixa)**
```

```ad-quote
title:
<p align="justify">Modele centenas de partículas em um espaço 2D, onde cada uma obedece às leis de Newton.</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">As partículas colidem umas com as outras e com as paredes da caixa de forma elástica.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Otimização de performance (verificar colisões é computacionalmente caro), integração de leis da física para múltiplos corpos e como propriedades macroscópicas (pressão, temperatura) emergem do comportamento de componentes microscópicos.</p>
```
````

````ad-quote
title:

```ad-quote
title:
###### **4. Simulação de Condução de Calor em uma Placa 2D**
```

```ad-quote
title:
<p align="justify">Crie uma grade para representar uma placa de metal.</p>
```

```ad-quote
title:
<b>O Desafio:</b>
- <p align="justify">Fixe a temperatura de algumas bordas (ex: uma borda "quente" e três "frias"). Calcule como o calor se distribui pela placa até que ela atinja um estado de equilíbrio.</p>

<b>Principais Conceitos:</b>
- <p align="justify">Resolução numérica de equações diferenciais parciais (PDEs), métodos de relaxação (como o método de Jacobi) e visualização de campos contínuos.</p>
```
````

---
