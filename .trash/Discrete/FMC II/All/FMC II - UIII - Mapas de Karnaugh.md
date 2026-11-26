
---

| **x \ yz** | **00** | **01** | **11** | **10** |
| ---------- | ------ | ------ | ------ | ------ |
| 0          | 1      | 1      | 0      | 0      |
| 1          | 1      | 1      | 0      | 1      |


Criação do mapa

- Elaborar o mapa utilizando o código de grey
- Encontrar os valores 1 par a par.

Simplificação da expressão 

- Desenhar grupos que sejam potências de 2
- ...

### **1. A Regra do Tamanho (Potências de Dois)**

A quantidade de células dentro de um agrupamento deve ser estritamente uma _potência de dois_. São permitidos blocos contendo 1, 2, 4, 8 ou 16 células. Agrupamentos com 3 ou 5 células são estruturalmente inválidos e quebram a matemática booleana.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$1$|$1$|$1$|$0$|
|$1$|$0$|$0$|$0$|$0$|

_Análise da Falha:_ É estruturalmente proibido circular os três elementos 1 numa única elipse. O método obriga a criar um bloco de tamanho 2 abrangendo as colunas 00 e 01, e um segundo bloco de tamanho 2 abrangendo as colunas 01 e 11, aplicando a regra da sobreposição.

### **2. A Regra da Orientação (Proibição Diagonal)**

Os blocos devem ser formados exclusivamente nas direções _horizontal_ ou _vertical_, desenhando retângulos ou quadrados perfeitos. É matematicamente proibido conectar células na diagonal. O padrão diagonal puramente isolado resulta sempre na operação de _Ou Exclusivo_.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$1$|$0$|$1$|$0$|
|$1$|$0$|$1$|$0$|$1$|

_Análise da Falha:_ As células ativas formam um tabuleiro de xadrez. Nenhum contacto ortogonal existe. Tentar unir estas células traçando linhas diagonais é um erro primário. Cada elemento 1 terá de ser extraído como um bloco unitário.

### **3. A Regra da Maximização (O Maior Bloco)**

A prioridade absoluta do método é expandir o bloco para o seu _tamanho máximo_ suportado pela matriz. Se desenhar dois agrupamentos de tamanho 2 quando as células permitiam a formação de um único bloco de tamanho 4, a sua redução falhou. Blocos maiores forçam o corte de mais variáveis.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$1$|$1$|$0$|$0$|
|$1$|$1$|$1$|$0$|$0$|

_Análise da Falha:_ Formar um laço para a linha superior e outro para a linha inferior resulta em dois termos $(x' \land y') \lor (x \land y')$, o que não é a forma mínima. A execução correta exige a fusão de todos os quatro elementos 1 num quadrado único, resultando apenas no termo $y'$.

### **4. A Regra da Sobreposição (Intersecção Obrigatória)**

Uma mesma célula que contém o valor 1 pode pertencer a múltiplos blocos de forma simultânea. A sobreposição não é opcional, ela é _obrigatória_ se a utilização de uma célula vizinha já englobada permitir duplicar o tamanho do novo bloco que está a ser traçado.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$0$|$1$|$1$|$0$|
|$1$|$0$|$0$|$1$|$0$|

_Análise Correta:_ Mapeia-se inicialmente o laço horizontal na linha superior (colunas 01 e 11). O elemento na posição $x=1, yz=11$ não deve ser agrupado sozinho. Ele deve sobrepor-se ao 1 que está imediatamente acima dele, formando um laço vertical de tamanho 2 e garantindo o corte da variável $x$.

### **5. A Regra da Redundância (O Limite da Sobreposição)**

Todo agrupamento traçado na matriz precisa englobar pelo menos _uma_ célula que ainda não pertença a nenhum outro bloco. Um laço onde absolutamente todos os elementos já foram circulados noutras etapas gera um termo repetido e invalida a minimização da equação.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$1$|$1$|$1$|$1$|
|$1$|$1$|$1$|$1$|$1$|

_Análise da Falha:_ Se a tabela estiver inteiramente preenchida com uns, formará um único bloco de tamanho 8 cobrindo o mapa inteiro (resultado lógico: 1). Desenhar agrupamentos intermédios de 4 ou 2 células dentro deste bloco máximo gera termos redundantes inúteis.

### **6. A Regra do Cilindro (Fechamento pelas Bordas)**

A matriz topológica não possui limites rígidos nas extremidades. A coluna da extrema esquerda é vizinha lógica direta da coluna da extrema direita. A linha do topo é vizinha direta da linha da base. O fechamento de blocos através das _bordas opostas_ é exigido sempre que maximizar a área do agrupamento.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$1$|$0$|$0$|$1$|
|$1$|$0$|$0$|$0$|$0$|

_Análise Correta:_ Isolar o 1 da coluna 00 num laço e o 1 da coluna 10 noutro laço é um erro. Como ambas as extremidades diferem em apenas uma variável no código de Gray, formam em conjunto um laço cilíndrico horizontal de tamanho 2, resultando em $(x' \land z')$.

### **7. A Regra do Bloco Unitário (O Último Recurso)**

O agrupamento de tamanho 1 é executado apenas quando a célula se encontra _totalmente isolada_, sem vizinhos ortogonais diretos ou conexões cilíndricas possíveis. A extração de um bloco unitário transcreve todas as variáveis do mapa para a equação sem cortes.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$0$|$0$|$0$|$0$|
|$1$|$0$|$1$|$0$|$0$|

_Análise Correta:_ A célula em $x=1, yz=01$ está cercada de zeros em todas as direções. Como não se pode aplicar nenhuma regra de maximização, extraem-se integralmente os seus eixos. A inversão incide apenas sobre as variáveis ancoradas em 0, resultando no termo $(x \land y' \land z)$.

### **8. A Regra de Extração (O Teste de Oscilação)**

Ao avaliar as coordenadas de um bloco finalizado, qualquer variável que alterar o seu estado (transitar de 0 para 1, ou de 1 para 0) dentro dos limites desse bloco é _apagada_ da equação. Variáveis ancoradas de forma estática no valor 1 são preservadas na sua forma direta. Variáveis ancoradas no valor 0 sofrem _inversão_ obrigatória.

_Exemplo Prático:_

|$x$ \ $yz$|$00$|$01$|$11$|$10$|
|---|---|---|---|---|
|$0$|$1$|$1$|$0$|$0$|
|$1$|$0$|$0$|$0$|$0$|

_Análise Correta:_ No laço horizontal da primeira linha: a variável $x$ está fixa em 0 (preserva-se $x'$); a variável $y$ está fixa em 0 em ambas as colunas (preserva-se $y'$); a variável $z$ transita do valor 0 na primeira coluna para o valor 1 na segunda coluna (corta-se a variável). O termo final é $(x' \land y')$.