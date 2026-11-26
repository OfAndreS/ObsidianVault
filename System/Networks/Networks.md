
---

03 - https://www.youtube.com/watch?v=TRVWIbYN4EE
04 - https://www.youtube.com/watch?v=mY0Vu9KSjMs
05 - https://www.youtube.com/watch?v=nu0WVpVw3C4
06 - https://www.youtube.com/watch?v=SLcas9BBEWk
07 - https://www.youtube.com/watch?v=zngSXGLxk4k

https://www.ibm.com/br-pt/think/topics/networking

https://www.alura.com.br/artigos/rede-de-computadores?srsltid=AfmBOoolsPg27vU_Saruk7u6HohN2Gg_toVVEoH2smfHXzsEvkoyABkF

![[Pasted image 20260709085123.png]]

### **Introdução e Fundamentos**

**O núcleo da rede, atrasos e modelo de serviço**

- A internet é uma gigantesca rede composta por outras redes menores. Os dispositivos que usamos diariamente formam a _borda da rede_. No meio do caminho, temos os roteadores, que formam o _núcleo da rede_. A função principal do núcleo é garantir a _comutação de pacotes_. Isso significa empurrar pequenos pedaços de dados de um ponto ao outro até o destino final. Durante essa viagem, os pacotes sofrem influência do cenário físico, podendo ocorrer _atraso_ ou _perda de pacotes_. Para organizar toda essa complexidade e garantir a _vazão_ adequada, a rede utiliza um _modelo de camadas_. Cada camada resolve um problema de comunicação específico e presta serviços para a camada imediatamente acima.

### **Camada de Aplicação**

**A Web, HTTP e Correio eletrônico**

- Na camada superior da arquitetura, os programas conversam através do modelo _cliente-servidor_. O processo que faz o pedido é o cliente, e o equipamento central que aguarda para responder é o servidor. O coração da Web é o _HTTP_. Ele atua como um _protocolo sem estado_, tratando cada requisição como um evento isolado. Para os sites lembrarem de você, o navegador guarda um _cookie_, que funciona como um crachá de identificação para a sessão. O correio eletrônico também usa essa camada, mas divide o trabalho. O protocolo _SMTP_ apenas empurra a mensagem do remetente até os servidores. Para puxar a mensagem da _caixa de correio_ até a tela do usuário, o sistema utiliza o _POP3_ (que baixa e apaga do servidor) ou o _IMAP_ (que apenas reflete os dados sincronizados).

**DNS: o serviço de diretório da Internet**

- O _DNS_ surge para resolver a limitação da memória humana. Ele realiza a _resolução de nomes_, traduzindo o _nome de hospedeiro_ salvo em linguagem natural para o _endereço IP_ numérico correspondente. Isso permite que a infraestrutura saiba exatamente para qual dispositivo enviar os dados.

**Distribuição de arquivos P2P**

- Quando uma aplicação precisa enviar arquivos massivos para uma grande base de usuários, a arquitetura cliente-servidor torna-se insuficiente. A necessidade de enviar o mesmo arquivo repetidas vezes cria um gargalo. Para contornar essa limitação, a _arquitetura P2P_ utiliza uma lógica descentralizada. Os dispositivos recebem partes iniciais do arquivo e atuam simultaneamente como clientes e servidores, distribuindo os dados entre si. Esse compartilhamento contínuo entre os _pares_, gerenciado pelo protocolo _BitTorrent_, garante a _escalabilidade_ do sistema. Cada novo usuário adiciona naturalmente mais capacidade de transmissão à rede.

### **Camada de Transporte**

**Programação de sockets, Multiplexação e Demultiplexação**

- Descendo para a camada intermediária, os dados precisam ser entregues aos programas corretos. Quando múltiplas aplicações tentam enviar dados, a camada de transporte coleta as informações através de seus respectivos _sockets_. Nesse momento, ocorre a _multiplexagem_. Ela consiste em rotular os dados adicionando o número da _porta_ de origem e de destino antes de enviá-los para a camada inferior. No sentido inverso, ao receber novos dados da rede, a camada de transporte realiza a _demultiplexagem_. Ela examina os rótulos de cada pacote para identificar a _porta_ de destino e direciona a informação com precisão para o aplicativo correspondente.

**Transporte não orientado para conexão (UDP) e orientado para conexão (TCP)**

- Na hora de transportar a informação, o sistema exige uma escolha de arquitetura. O protocolo _UDP_ prioriza a agilidade de transmissão ao abrir mão da _confiabilidade_. Ele dispara os dados sem verificar a entrega, sendo a opção ideal para transmissões de vídeo ao vivo. Em contrapartida, o protocolo _TCP_ garante a _confiabilidade_ absoluta e a entrega ordenada, sacrificando parte da velocidade para focar na segurança. Para conseguir essa segurança, ele exige um ritual inicial chamado _three-way handshake_ (aperto de mão de três vias). O cliente envia um toque de sincronização chamado _SYN_. O servidor responde com um _SYN-ACK_ para confirmar o recebimento e pedir sua própria sincronização. Por fim, o cliente devolve um _ACK_ final de confirmação, estabelecendo uma conexão sólida antes de enviar qualquer dado real.

### **Módulo 3: Camada de Rede**

**Repasse e roteamento** 

- A camada de rede é responsável por mover os dados pela infraestrutura da internet. Esse trabalho é dividido em duas ações. O _roteamento_ é a inteligência global do sistema, responsável por calcular todo o caminho que o dado fará da origem ao destino. Já o _repasse_ é a ação mecânica local do roteador, que consiste em pegar o pacote que chegou por uma porta e direcioná-lo rapidamente para a porta de saída adequada.

**Redes de datagramas** 

- Na internet, os dados viajam de forma completamente independente. A informação é dividida em blocos chamados _datagramas_. A rede opera com um _serviço não orientado para conexão_. Isso significa que cada pacote procura o seu próprio caminho durante o envio, sem reservar rotas antecipadamente, garantindo flexibilidade caso alguma estrada digital fique congestionada.

**O que há dentro de um roteador?** 

- O roteador atua como um grande centro de triagem. A informação chega pelas _portas de entrada_ e cruza a máquina através do _elemento de comutação_. Caso a velocidade de chegada seja maior que a velocidade da travessia interna, os dados aguardam nas _filas_ temporárias de memória. Após a travessia, eles seguem para as _portas de saída_. Se as _filas_ encherem completamente, os novos pacotes são simplesmente descartados.

**Formato do datagrama e Endereçamento IPv4** 

- Todo _datagrama_ possui um cabeçalho de controle, que funciona como a parte frontal de um envelope postal. O dado mais importante contido ali é o _endereço IP_. Ele atua como uma sequência numérica (no caso do _IPv4_, com tamanho de 32 bits) que identifica unicamente o dispositivo remetente e o destinatário na rede global.

**IPv6** 

- Com a explosão de celulares e dispositivos conectados, os endereços do _IPv4_ se esgotaram. A solução de engenharia foi adotar o _IPv6_, que utiliza endereços com um espaço imenso de 128 bits. Essa atualização garante que a internet continue crescendo sem limitações numéricas.

**Algoritmos de roteamento e Roteamento na Internet** 

- Para o roteador saber o melhor caminho, ele utiliza os _algoritmos de roteamento_, que são fórmulas matemáticas focadas em calcular a rota mais eficiente. A internet mundial é dividida em blocos administrativos de diferentes empresas, chamados de _Sistemas Autônomos_. O roteamento interno de cada empresa é feito por protocolos locais, enquanto a troca de informações global entre provedores diferentes é gerenciada pelo protocolo _BGP_.

### **Módulo 4: Camada de Enlace e Redes Sem Fio**

**Introdução à camada de enlace** 

- Enquanto a camada de rede cuida de toda a viagem de ponta a ponta, a camada de enlace cuida apenas do pequeno salto entre dois equipamentos conectados pelo mesmo cabo ou sinal de rádio. Para fazer esse salto local, o pacote de dados recebe uma nova embalagem externa e passa a ser chamado de _quadro_.

**Protocolos de acesso aleatório** 

- Quando vários computadores dividem o mesmo cabo de rede, se dois equipamentos tentarem enviar dados ao mesmo tempo, ocorre uma colisão elétrica e a informação é destruída. Para evitar isso, utilizam-se regras para compartilhar o canal. Os equipamentos sempre escutam o cabo antes de falar para garantir o silêncio e minimizar problemas.

**Endereçamento na camada de enlace e ARP** 

- Para o salto local funcionar, o número IP não é suficiente. As placas de rede se comunicam pelo _endereço MAC_, um identificador físico gravado de fábrica na peça de hardware. Para que um computador descubra o _endereço MAC_ de um equipamento vizinho possuindo apenas o número IP dele em mãos, o sistema dispara o _ARP_, um protocolo rápido de tradução.

**Ethernet e Comutadores da camada de enlace** 

- A tecnologia _Ethernet_ é o padrão hegemônico para redes cabeadas locais. Nessas redes corporativas e residenciais, o equipamento central unificador é o _switch_ (comutador). O _switch_ atua de forma inteligente memorizando os _endereços MAC_ de cada máquina conectada e repassando o _quadro_ diretamente para a porta correta, isolando o tráfego e eliminando colisões.

**A arquitetura 802.11 e o protocolo MAC 802.11** 

- Essa é a nomenclatura técnica que define as populares redes Wi-Fi. Ao contrário de um cabo de cobre isolado, o ar é um meio de transmissão muito hostil e cheio de interferências. Como os equipamentos sem fio não conseguem transmitir energia e escutar o canal com clareza simultaneamente, eles utilizam um protocolo robusto chamado _CSMA/CA_, desenhado exclusivamente para prever e evitar ao máximo as colisões invisíveis pelo ar antes de arriscar o envio dos dados.
