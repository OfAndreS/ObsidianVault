
---

>[!example] ### **Introduction to AI **

---

```ad-quote
title: **Def**

A Inteligência Artificial (IA) é um campo da ciência da computação que se dedica a criar máquinas capazes de realizar tarefas que, até então, eram exclusivas da inteligência humana. Essas tarefas incluem:  

**Raciocínio:** 
- Capacidade de resolver problemas e tomar decisões.
  
**Aprendizado:** 
- Habilidade de adquirir conhecimento e melhorar o desempenho com a experiência.
  
**Percepção:** 
- Capacidade de interpretar e compreender dados sensoriais, como imagens e sons.
  
**Linguagem natural:** 
- Habilidade de entender e gerar linguagem humana.
```

---
#### **Como a IA funciona?**

```ad-quote
title: **Def**

A IA funciona através de algoritmos e modelos matemáticos que permitem que as máquinas processem grandes volumes de dados, identifiquem padrões e tomem decisões. Esses algoritmos podem ser divididos em duas categorias principais:

- **Aprendizado de máquina (Machine Learning):** Os algoritmos de aprendizado de máquina permitem que as máquinas aprendam com os dados sem serem explicitamente programadas.
- **Aprendizado profundo (Deep Learning):** Uma subcategoria do aprendizado de máquina que utiliza redes neurais artificiais para aprender padrões complexos em grandes volumes de dados.  
    
```

---
#### **Tipos de IA:**

```ad-quote
title: **Def**

A IA pode ser classificada em diferentes tipos, dependendo de sua capacidade e funcionalidade:

**IA fraca (ou IA estreita):** 
- É projetada para realizar tarefas específicas, como reconhecimento facial ou tradução de idiomas.

**IA forte (ou IA geral):** 
- Possui a capacidade de realizar qualquer tarefa intelectual que um ser humano possa realizar.

**Superinteligência artificial:** 
- Uma forma hipotética de IA que supera a inteligência humana em todos os aspectos.
```

---
#### **Aplicações da IA:**

```ad-quote
title: **Def**

A IA está presente em diversas áreas do nosso dia a dia, como:

- Assistentes virtuais (Siri, Alexa, Google Assistente)
- Sistemas de recomendação (Netflix, Spotify)
- Carros autônomos
- Diagnóstico médico
- Detecção de fraudes
- Tradução de idiomas
- Chatbots
```

---

>[!example] ### **What's an Angent **

---

```ad-quote
title: **Def**

Um **agente de IA** é uma entidade autônoma que:

1. **Percebe** seu ambiente por meio de **sensores** (dados, câmeras, microfones, etc.). 
2. **Age** sobre esse ambiente usando **atuadores** (motores, telas, respostas, etc.).    
3. **Toma decisões** racionais para alcançar objetivos específicos, baseando-se em regras, aprendizados ou funções de utilidade.


Exemplos incluem robôs aspiradores, assistentes virtuais (como Siri) e sistemas de recomendação (como Netflix). Sua eficiência depende do ambiente (observável, estático, multiagente) e de sua estrutura (reativa, baseada em objetivos ou aprendizado).
```

---

>[!tip] **Tipos de Agente**

---

```ad-quote
title: **Def**

**01 ) Agente Humano:**

Um Agente Humano é uma pessoa que age como um agente de tomada de decisões, utilizando seus sentidos (visão, audição, tato, etc.) para perceber o ambiente e suas capacidades físicas e cognitivas para agir.  

**Percepção**: 
- Usa órgãos sensoriais (olhos, ouvidos, etc.).  

**Ação**: 
- Pode interagir fisicamente (mover objetos, falar) ou digitalmente (digitar, usar interfaces). 

**Exemplo**: Um operador humano controlando um robô em uma fábrica ou um médico usando um sistema de diagnóstico por IA para tomar decisões.  
```

```ad-quote
title: **Def**

**02 ) Agente Robótico:**

Um Agente Robótico** é um sistema autônomo ou semi-autônomo que interage com o mundo físico por meio de sensores e atuadores.  

**Percepção**: 
- Sensores como câmeras, sensores de proximidade, giroscópios, etc. 

**Ação**: 
- Atuadores como motores, braços robóticos, rodas, etc.

**Exemplo**: Um robô aspirador (como o Roomba) que mapeia um ambiente e limpa sozinho, ou um drone autônomo que faz entregas. 

```

```ad-quote
title: **Def**
**03 ) Agente Software:**

Um Agente Software** é um programa de computador que opera em ambientes virtuais, executando tarefas automatizadas sem intervenção física direta.  

**Percepção**: 
- Entradas digitais (dados, cliques, APIs, sensores virtuais).

**Ação**: 
- Saídas digitais (envio de mensagens, alteração de bancos de dados, controle de sistemas).  

- **Exemplo**: Um chatbot que responde perguntas, um algoritmo de negociação em bolsa de valores ou um assistente virtual como a Siri ou Alexa.  
```

---

>[!tip] **Conceito de Agente**

---

```ad-quote
title: **Def**


###### **Definição**: 
- Um agente é qualquer entidade que percebe o ambiente por meio de sensores e age sobre ele por meio de atuadores.

---

***Agente humano***: 
- Sensores (olhos, ouvidos) e atuadores (mãos, pernas).
   
***Agente robótico***: 
- Sensores (câmeras, GPS) e atuadores (motores).
   
***Agente de software***: 
- Sensores (teclado, mouse) e atuadores (tela, mensagens de rede).

```
#### **Função do Agente**:

>[!quote] **Def**
>O comportamento do agente é descrito por uma função matemática $f$ que mapeia sequências de percepções $P$ para ações $A$:
>$$f:P^*\to A$$

---

>[!tip] **Racionalidade dos Agentes**

---

```ad-quote
title: **Def**

**Fatores de Racionalidade**:
 
1. **Medida de Desempenho**: Critério para avaliar o sucesso do agente.
        
2. **Conhecimento Prévio**: Informações sobre o ambiente.
        
3. **Ações Disponíveis**: Opções que o agente pode executar.
        
4. **Sequência de Percepções**: Histórico de percepções e ações.
        

**Agente Racional**: Seleciona ações que maximizam sua medida de desempenho, considerando os fatores acima.

**Racionalidade vs. Onisciência**:

- Racionalidade: Maximiza o desempenho esperado com base nas percepções disponíveis.

- Onisciência: Maximiza o desempenho real, conhecendo os resultados exatos das ações (idealizado).
```

---

>[!tip] **Ambientes de Tarefa (PEAS)**

---

```ad-quote
title: **Def**

O ambiente de tarefa é definido pelo acrônimo **PEAS**:

- **Performance (Desempenho)**: Critérios de sucesso.
    
- **Environment (Ambiente)**: Contexto onde o agente opera.
    
- **Actuators (Atuadores)**: Dispositivos para agir no ambiente.
    
- **Sensors (Sensores)**: Dispositivos para perceber o ambiente.
    

**Exemplos**:

**Motorista de Táxi Automatizado**:
    
- Desempenho: Segurança, velocidade, conforto.
        
- Ambiente: Ruas, outros veículos, pedestres.
        
- Sensores: Câmera, GPS.
        
- Atuadores: Volante, freio.
        
**Sistema de Diagnóstico Médico**:
    
- Desempenho: Saúde do paciente, custos.
        
- Ambiente: Paciente, hospital.
        
- Sensores: Entrada de sintomas.
        
- Atuadores: Exibição de diagnósticos.
```

---

>[!tip] **Propriedades dos Ambientes**

---

```ad-quote
title: **Def**

**Observabilidade**:
    
- **Completamente observável**: 
  Todos os dados do ambiente são acessíveis (ex.: xadrez).
        
- **Parcialmente observável**: 
  Algumas informações estão ocultas (ex.: dirigir um carro).
```

```ad-quote
title: **Def**

**Número de Agentes**:
    
- **Único agente**: 
	Sem interferência externa (ex.: palavras cruzadas). 
- **Multiagente**: 
	Interação entre agentes (ex.: jogos multiplayer).
```

```ad-quote
title: **Def**

**Determinismo**:
    
- **Determinístico**: 
  Ações têm resultados previsíveis (ex.: jogo da velha).
   
- **Estocástico**: 
  Incerteza nos resultados (ex.: previsão do tempo).
```

```ad-quote
title: **Def**

**Episódico vs. Sequencial**:
    
- **Episódico**: 
Tarefas independentes (ex.: inspeção de peças).
- **Sequencial**: 
  Ações afetam o futuro (ex.: mercado financeiro).
```

```ad-quote
title: **Def**

**Estático vs. Dinâmico**:
    
- **Estático**: 
  Ambiente não muda durante a decisão (ex.: jogos de tabuleiro).
        
- **Dinâmico**: 
  Ambiente muda durante a interação (ex.: tráfego aéreo).
```

```ad-quote
title: **Def**

**Discreto vs. Contínuo**:

- **Discreto**: 
  Estados e ações finitos (ex.: grid).
- **Contínuo**: 
  Valores contínuos (ex.: controle de volante).
```

---

>[!tip] **Estruturas dos Agentes**

---

```ad-quote
title: **Def**


Os agentes são compostos por:

**Arquitetura**: 
- Sensores e atuadores.
   
**Programa**: 
- Função que mapeia percepções em ações.
   
```

```ad-quote
title: **Def**

**Tipos de Agentes**:

**Dirigido por Tabela**:

- Usa uma tabela pré-definida de ações para cada sequência de percepções.

- **Desvantagem**: Tabelas são inviáveis para ambientes complexos (ex.: xadrez).

---

**Reativo Simples**:

- Toma decisões com base apenas na percepção atual (ex.: aspirador robótico).
   
- **Limitação**: Não armazena histórico de percepções.

---

**Reativo Baseado em Modelo**:

- Mantém um estado interno do ambiente e usa modelos para prever ações.

- **Aplicação**: Ambientes determinísticos.

---
  
**Baseado em Objetivo**:

- Seleciona ações para alcançar objetivos específicos (ex.: planejamento de rotas).

- **Vantagem**: Flexibilidade e autonomia.

---

**Baseado em Utilidade**:

- Maximiza uma função de utilidade, considerando resultados esperados.
  
- **Aplicação**: Ambientes com incerteza.

---

**Agente que Aprende**:

- Melhora seu desempenho com a experiência (ex.: aprendizado de máquina).
 
- **Vantagem**: Adaptabilidade a ambientes desconhecidos.
```

---

>[!tip] **PEAS**

---
#### **1 ) Performance**

```ad-quote
title: **Def**

**O que é:** 
- Critérios que avaliam o quão bem o agente está desempenhando sua tarefa.

---

**Exemplos:**

- Para um **aspirador robótico**: "Quantidade de sujeira removida por tempo" ou "Consumo de energia".

- Para um **sistema de recomendação**: "Precisão das sugestões" ou "Taxa de cliques".

**Objetivo:** Definir métricas claras para sucesso ou falha.
```

---
#### **Environment (Ambiente)**

```ad-quote
title: **Def**

**O que é:**

- O contexto em que o agente opera, incluindo características físicas ou virtuais.
    

---

**Classificação do ambiente:**

- **Observável vs. Parcialmente Observável:**
    
    - Se o agente tem acesso completo ou limitado ao estado do ambiente.
        
- **Determinístico vs. Estocástico:**
    
    - Se as ações têm resultados previsíveis ou aleatórios.
        
- **Estático vs. Dinâmico:**
    
    - Se o ambiente muda enquanto o agente delibera.
        
- **Discreto vs. Contínuo:**
    
    - Se o tempo/espaço é dividido em passos ou é fluido.
        

**Exemplo:**

- Um **carro autônomo** opera em um ambiente **dinâmico, contínuo e parcialmente observável**.
    
```

---

```ad-quote
title: **Def**

### **Actuators (Atuadores)**

**O que é:**

- Mecanismos que o agente usa para interagir com o ambiente.
    

---

**Exemplos:**

- **Braço robótico:** Motores que movem as juntas.
    
- **Agente de software:** Comandos que atualizam um banco de dados.
    

**Função:**

- Converter decisões do agente em ações físicas ou virtuais.
```


ˋˋˋˋˋˋ