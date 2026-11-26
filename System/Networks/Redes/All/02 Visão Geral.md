
---

````ad-quote
title:
```ad-quote
title:
Inicialmente, para estruturar a Internet, existem 4 problemas fundamentais: **Nomeação e Endereçamento**, **Roteamento**, **Encaminhamento** e **Compatibilidade**. 
```
```ad-quote
title: **Problemas Fundamentais**
Quando um processo quer acessar a rede, abre um *socket* (o ponto final de um fluxo de comunicação bidirecional entre dois processos), que é associado a uma porta. Dessa forma, uma pilha de redes é conectada ao *socket*.

- **Nomeação e Endereçamento:** Endereço de rede e *hostname*. O DNS (*Domain Name System*) mapeia nomes em endereços de rede (o que a rede entende).
<br>
- **Roteamento:** Roteando pacotes por meio de dispositivos de rede (roteadores) até o destino. No roteador, uma tabela de roteamento determina para qual link de saída o pacote será enviado e calculado mediante os protocolos de roteamento.
<br>
- **Encaminhamento:** Enfileiramento (filas virtuais armazenam os pacotes) e encaminhamento (quando o link de saída está disponível). Os pacotes (cabeçalho e os dados) informam para onde vão, de onde vêm e os dados que serão enviados.
<br>
- **Confiabilidade:** Entregar os pacotes de maneira confiável. Eles podem ser perdidos, isto é, "dropados".
```
```ad-quote
title: **Largura *VS.* Latência**
**Largura de banda** representa o número de *bits* por unidade de tempo (bps). Já a **latẽncia** designa o tempo para uma mensagem se mover em un link.
- **Atraso de Transmissão:** (tamanho do pacote) / (taxa de transmissão do link).
- **Atraso de Propagação:** (comprimento do link) / (velocidade de propagação do link).
```
````

## Identificação

### Resumo

A primeira fase do sistema consiste em traduzir o endereço web legível para humanos em um endereço de _IP_ necessário para o roteamento.

### Funcionamento

O processo de resolução inicia-se quando o sistema operacional do cliente encaminha uma consulta para um servidor _resolver recursivo_, que atua como intermediário na busca pela informação. Caso o endereço solicitado não esteja presente no _cache_ local, o _resolver_ inicia uma sequência de consultas hierárquicas, começando pelos _servidores raiz_, que indicam o servidor responsável pela extensão do domínio, como o _.com_ ou _.br_. Em seguida, a consulta é direcionada aos servidores de _domínio de topo_ (TLD), que possuem os dados sobre os servidores de nomes _autoritativos_ do domínio específico solicitado. Por fim, o servidor _autoritativo_ fornece o endereço de _IP_ correspondente, permitindo que o _resolver_ armazene essa resposta temporariamente e a devolva ao cliente para que a conexão de dados possa ser efetivamente estabelecida.

### Principais problemas

- **Latência de Resolução**: O tempo necessário para realizar múltiplas consultas em servidores geograficamente distantes pode atrasar o início da comunicação de dados.
    
- **Consistência do Cache**: O parâmetro _TTL_ (_Time To Live_) gera um conflito entre a eficiência da rede e a necessidade de propagar atualizações quando um servidor muda de endereço.
    
- **Vulnerabilidades de Segurança**: A arquitetura original permite ataques de _DNS spoofing_, onde dados falsos são inseridos no _cache_ para redirecionar usuários a destinos maliciosos.
    
- **Resiliência da Infraestrutura**: A dependência de servidores de nível superior cria pontos críticos de falha que podem comprometer a acessibilidade de grandes segmentos da internet.

## Roteamento

### Resumo

O roteamento consiste em direcionar pacotes através de dispositivos interconectados até o destino final. No roteador, uma _tabela de roteamento_ determina para qual link de saída o pacote será enviado, sendo esta tabela calculada mediante protocolos de roteamento específicos.

### Funcionamento

O funcionamento do roteamento baseia-se na construção e manutenção de um mapa lógico da topologia da rede no que é chamado de _plano de controle_. Protocolos como _OSPF_ ou _BGP_ realizam a troca constante de informações de estado entre roteadores vizinhos para identificar caminhos disponíveis e determinar a rota ideal com base em métricas como número de saltos, largura de banda ou latência. Uma vez que o algoritmo de roteamento processa esses dados, ele gera a _tabela de encaminhamento_, que é consultada em tempo real para processar cada pacote que ingressa no dispositivo. Este sistema é inerentemente dinâmico, permitindo que a rede recalcule trajetórias automaticamente caso um nó ou link físico sofra uma falha, garantindo a continuidade do fluxo de dados por caminhos alternativos sem intervenção manual imediata.

### Principais problemas

- **Convergência de Rede**: O intervalo de tempo necessário para que todos os roteadores atualizem suas tabelas após uma mudança na topologia pode causar instabilidade ou perda temporária de conectividade.
    
- **Ciclos de Roteamento (Loops)**: Inconsistências temporárias nas tabelas de roteadores vizinhos podem fazer com que um pacote seja enviado continuamente entre os mesmos dispositivos, consumindo recursos de rede sem atingir o destino.
    
- **Segurança de Prefixos (Hijacking)**: A confiança implícita em certos protocolos permite que uma rede anuncie falsamente a posse de determinados endereços de _IP_, desviando o tráfego global para destinos ilegítimos.
    
- **Escalabilidade das Tabelas**: O crescimento exponencial da rede mundial exige que os roteadores de borda gerenciem centenas de milhares de rotas, o que demanda hardware com alta capacidade de memória e processamento.

## Encaminhamento

### Resumo

O encaminhamento, ou _forwarding_, é o processo interno de um roteador que consiste em mover um pacote de uma interface de entrada para a interface de saída apropriada. Enquanto o roteamento define a estratégia global, o encaminhamento é a ação de execução imediata e local.

### Funcionamento

Este processo ocorre no que chamamos de _plano de dados_ e é otimizado para desempenho em escala de nanossegundos. Ao receber um pacote, o _hardware_ do roteador examina os campos do cabeçalho, especificamente o endereço de destino, e realiza uma consulta em uma estrutura de dados de alta velocidade chamada _tabela de encaminhamento_ (ou _Forwarding Information Base_). Esta tabela é uma versão condensada da tabela de roteamento, projetada para buscas binárias extremamente rápidas, muitas vezes utilizando memórias especializadas conhecidas como _TCAM_. Uma vez identificada a porta de saída, o pacote é transferido através da _matriz de comutação_ (_switching fabric_) interna do dispositivo. Se a porta de destino estiver congestionada, o pacote é colocado em _filas virtuais_ (_buffers_) de memória até que o link esteja disponível para a transmissão física.

### Principais problemas

- **Estouro de Buffer (Packet Drop)**: Quando a taxa de entrada de dados supera a capacidade de saída por um tempo prolongado, as filas de memória se esgotam e o roteador é forçado a descartar os pacotes excedentes.
    
- **Atraso de Fila (Queuing Delay)**: O tempo de espera dentro dos _buffers_ aumenta a latência total da rede, impactando diretamente o desempenho de aplicações sensíveis ao tempo.
    
- **Bloqueio de Cabeça de Fila (HOL Blocking)**: Uma falha estrutural onde um pacote aguardando uma porta de saída congestionada impede que outros pacotes atrás dele sigam para portas que estão totalmente livres.
    
- **Gargalos na Matriz de Comutação**: Se a capacidade interna de transferência do roteador for inferior à soma das velocidades de todas as suas portas, o dispositivo se torna um limitador de desempenho para a rede.

## Confiabilidade

### Resumo

A confiabilidade refere-se à garantia de que os pacotes de dados sejam entregues ao destino final de forma íntegra e na ordem correta. Como a infraestrutura da rede é inerentemente não confiável e pode descartar pacotes devido a falhas ou congestionamento, essa camada é responsável por detectar perdas e solicitar a retransmissão da informação.

### Funcionamento

Diferente do roteamento e do encaminhamento, a confiabilidade é geralmente implementada nas extremidades da rede através do _Protocolo de Controle de Transmissão_ (TCP). O processo baseia-se no estabelecimento de uma conexão lógica onde cada pacote enviado recebe um número de sequência único para que o destino possa reconstruir a mensagem original. Ao receber um dado, o destinatário envia uma confirmação de recebimento (_ACK_) ao remetente; caso este não receba a confirmação dentro de um intervalo de tempo determinado (_timeout_), ele assume que o pacote foi descartado e realiza a retransmissão automática. Além disso, o protocolo utiliza mecanismos de _controle de fluxo_ e _controle de congestionamento_, ajustando a velocidade de envio conforme a capacidade de processamento do receptor e a saturação dos links intermediários, evitando que a rede entre em colapso por excesso de tráfego.

### Principais problemas

- **Latência de Retransmissão**: O tempo necessário para detectar uma perda e reenviar o dado aumenta o atraso total da comunicação, o que pode tornar a conexão instável para aplicações em tempo real.
    
- **Overhead de Controle**: O envio constante de confirmações e a manutenção de cabeçalhos complexos consomem largura de banda que poderia ser utilizada para o tráfego de dados úteis.
    
- **Bloqueio de Cabeça de Fila (Camada de Transporte)**: Se um pacote inicial é perdido, todos os pacotes subsequentes que já chegaram ao destino ficam retidos no _buffer_ aguardando a retransmissão do dado faltante para que a ordem seja restaurada.
    
- **Ineficiência em Links de Alta Latência**: Em conexões com tempos de resposta muito altos (como satélites), o mecanismo de espera pelas confirmações pode limitar severamente a taxa de transferência real, mesmo que haja banda disponível.