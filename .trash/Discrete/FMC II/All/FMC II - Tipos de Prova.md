---
banner: "![[Pasted image 20260311140138.png]]"
---

---
### 1. Provas de Inclusão de Conjuntos

- _Objetivo_: Garantir que todo elemento de um subconjunto está contido em outro formato ou operação.
    
- _Setup de Abertura_: Extraia um elemento solto do primeiro conjunto. Exemplo: Seja $x$ um elemento arbitrário pertencente a $A$.
    
- _Motor Lógico_: Aplique a definição formal da operação em que $x$ se encontra (união, interseção, domínio) e utilize as hipóteses para empurrar o elemento adiante.
    
- _Alvo Final_: Concluir dedutivamente que $x$ pertence ao conjunto de destino.
    

### 2. Provas de Igualdade de Conjuntos

- _Objetivo_: Comprovar que duas estruturas algébricas ou operacionais mapeiam exatamente os mesmos elementos.
    
- _Estratégia_: Quebre o problema em duas provas independentes aplicando a técnica da _dupla inclusão_.
    
- _Ida_: Isole um elemento de um lado da igualdade e force o seu aparecimento do outro lado.
    
- _Volta_: Inverta o ponto de partida, isolando um elemento do lado oposto e forçando o retorno lógico à primeira estrutura.
    
- _Alvo Final_: Declarar que a ocorrência irrefutável de ambas as inclusões confirma a igualdade.
    

### 3. Provas de Unicidade

- _Objetivo_: Atestar que apenas um elemento isolado satisfaz uma determinada restrição do teorema (ex: _menor elemento_, _elemento minimal_, _elemento neutro_).
    
- _Setup de Abertura_: Assuma a premissa provisória de que existem dois elementos distintos (ex: $a$ e $b$) que satisfazem integralmente a condição estipulada.
    
- _Motor Lógico_: Faça os dois elementos interagirem através de propriedades estruturais da relação. Em relações de ordem, a ferramenta letal obrigatória é a _antissimetria_.
    
- _Alvo Final_: Forçar o colapso algébrico da suposição, provando dedutivamente que $a = b$.
    

### 4. Provas de Totalidade de uma Relação

- _Objetivo_: Comprovar que nenhum elemento do conjunto de partida falhou em encontrar uma conexão lógica de destino.
    
- _Setup de Abertura_: Isole um elemento arbitrário pertencente estritamente ao conjunto de partida. Nunca inicie capturando um par ordenado de dentro da relação.
    
- _Motor Lógico_: Invoque as restrições e premissas dadas no enunciado para garantir a criação de uma rota válida a partir dessa variável de origem.
    
- _Alvo Final_: Atestar a existência algébrica de um par formado, provando a igualdade estrita do domínio.
    

### 5. Provas de Propriedades Relacionais

- _Objetivo_: Confirmar que operações entre relações (como composição ou diferença) preservam uma regra de comportamento interna (simetria, transitividade, reflexividade).
    
- _Setup de Abertura_: Insira o input elementar exigido pela propriedade em questão. Para atestar _simetria_, extraia o par $(a,b)$. Para atestar _transitividade_, extraia a corrente $(a,b)$ e $(b,c)$.
    
- _Motor Lógico_: Expanda os pares através das definições das operações de conjuntos e utilize as propriedades herdadas das hipóteses para manusear as peças.
    
- _Alvo Final_: Atingir o reflexo exigido pela propriedade. Chegar em $(b,a)$ para a simetria, ou no atalho $(a,c)$ para a transitividade.
    

### 6. Refutação de Teoremas

- _Objetivo_: Provar que uma afirmação universal contida no enunciado é matematicamente falsa.
    
- _Estratégia Obrigatória_: Abandone imediatamente o uso de variáveis genéricas, deduções algébricas e elementos arbitrários.
    
- _Motor Lógico_: Construa um _contraexemplo_ palpável.
    
- _Alvo Final_: Defina numericamente conjuntos microscópicos (ex: $A = \{1, 2\}$) e construa relações literais finitas que obedeçam obedientemente a todas as premissas do enunciado, mas que violem frontalmente a conclusão proposta na reta final.
    

---
