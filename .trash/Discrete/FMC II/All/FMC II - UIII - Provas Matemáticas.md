
---
### Propriedades para Intervalos Contínuos (Questões a e b)

Para resolver a determinação de maximais e minimais em subconjuntos contínuos como $A \subseteq \mathbb{R}$, você necessita estritamente de dois conceitos estruturais:

- _Definições Formais de Extremos:_
    
    - _Maximal:_ Um elemento $a \in A$ é maximal se, e somente se, não existir nenhum $x \in A$ tal que $a < x$.
    
    - _Minimal:_ Um elemento $a \in A$ é minimal se, e somente se, não existir nenhum $x \in A$ tal que $x < a$.
    
- _Densidade dos Números Reais:_ Propriedade analítica que estabelece que, entre quaisquer dois números reais distintos, sempre existe outro número real.
    
    - _Aplicação na letra (a):_ Como vimos, é a propriedade de densidade que justifica o uso do ponto médio para provar que o intervalo aberto $0 < x < 1$ não possui elemento maximal nem minimal.
    
    - _Aplicação na letra (b):_ A presença da restrição fechada na inequação $x \le 1$ bloqueia a continuidade da densidade no limite superior. Ao testar a definição de maximal, o elemento $1$ satisfaz a condição, pois pertence ao conjunto e não existe nenhum número maior que ele dentro de $A$.
    

### Propriedades para Verificação de Ordens Parciais (Exemplos 1 a 6)

O comando "verificar" nessa seção da lista significa que você deve demonstrar que as relações apresentadas formam ou não uma _relação de ordem parcial_. Para que qualquer relação seja classificada dessa forma, você é obrigado a provar que ela satisfaz simultaneamente as três propriedades matemáticas abaixo:

- _Reflexividade:_ Para todo elemento $x$ pertencente ao conjunto, a relação deve ser válida para ele mesmo.
    
    - _Exemplo matemático:_ $\forall x \in A$, $x \mathrel{R} x$.
    
    - _Como aplicar:_ No item 1, você precisa argumentar que todo conjunto é subconjunto de si mesmo ($X \subseteq X$). No item 3, que todo número divide a si mesmo.
    
- _Antissimetria:_ Para quaisquer elementos $x$ e $y$ pertencentes ao conjunto, se $x$ se relaciona com $y$, e $y$ se relaciona com $x$, então obrigatoriamente eles são o mesmo elemento.
    
    - _Exemplo matemático:_ Se $x \mathrel{R} y$ e $y \mathrel{R} x$, então $x = y$.
    
    - _Como aplicar:_ No item 2, se $x \le y$ e $y \le x$, a única conclusão lógica na aritmética é que $x = y$.
    
- _Transitividade:_ Para quaisquer elementos $x$, $y$ e $z$, se o primeiro se relaciona com o segundo, e o segundo se relaciona com o terceiro, então o primeiro tem que se relacionar com o terceiro.
    
    - _Exemplo matemático:_ Se $x \mathrel{R} y$ e $y \mathrel{R} z$, então $x \mathrel{R} z$.
    
    - _Como aplicar:_ No item 5, se a palavra $x$ é prefixo de $y$, e $y$ é prefixo de $z$, é necessário concluir que $x$ também funciona como prefixo direto de $z$.
    

A sua resolução para essa parte da lista deve ser estruturada testando exaustivamente essas três propriedades para cada um dos seis casos. Caso você encontre um contraexemplo que fure uma única propriedade, a verificação falha e você deve concluir que não se trata de uma ordem parcial.