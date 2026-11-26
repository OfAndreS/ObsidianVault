
---

````ad-quote
title:
```ad-quote
title:
A princípio, topologias de redes definem as disposições físicas (*layouts* efetivos dos fios ou meios físicos) ou lógicas (definem como os meios físicos são acessados pelos *hosts* para o envio de dados) de como os dispositivos estão conectados e comunicam-se entre si.
```
```ad-quote
title: **Fluxo de Dados**
- **Simplex:** Os dados seguem em um único sentido (TV, rádio, etc.).
<br>
- **Half-Duplex:** Os dados seguem em um único sentido de cada ves (rádio da polícia, *walkie-talkies*, entre outros).
<br>
- **Full-Duplex:** Os dados seguem em ambos os sentidos simultaneamente (telefone).
```
```ad-quote
title: **Critérios de Classificação**
- **Ponto-a-Ponto (*Peer-to-Peer* | P2P):** A rede consiste  em um conjunto de conexões em pares de máquinas individuais. Nesse sentido, fornece um link dedicado entre dois dispositivos (receptor e transmissor). Exemplo: controle remoto infravermelho.
<br>
- **Multiponto (*Multidrop*):** Um ponto central envia informações para vários pontos, utilizando um mesmo meio. Nesse contexto, mais de dois dispositivos compartilham um único link. Logo, a capacidade do canal é compartilhada, seja de forma espacial ou temporal:
	- **Espacial:** Diversos dispositivos usam o link simultaneamente.
	- **Temporal:** Usuários devem revesar entre si.
```
```ad-quote
title: **Tipos de Topologias Físicas**
- **Barramento:** Todos os computadores são ligados em um mesmo barramento físico de dados (Multiponto). Assim, apenas uma máquina pode "escrever" no barramento num dado momento. Diante disso, quando um computador estiver transmitindo um sinal, toda a rede fica ocupada.
	- **Vantagens:** Uso de cabo é econômico; simples e relativamente confiável e fácil a inserção de um novo computador na rede.
	- **Desvantagens:** A rede pode ficar extremamente lenta com tráfego pesado, problemas são difíceis de isolar e falhas no cabo principal paralisa a rede inteira.

<img alt="center" src="topologia_barramento.png">
<br>

- **Estrela:** Utiliza cabos de par trançado e um computador como ponto central de rede (Ponto-a-Ponto). Desse modo, o concentrador (*hub*) se encarregaa de retransmitir todos os dados para todas as estações.
	- **Vantagens:** Mais fácil a localização dos problemas (são vários pares, e não apenas um único canal principal), a adição de novos computadores é simples e robustez.
	- **Desvantagens:** Uma falha no dispositivo central paralisa a rede inteira.

<img alt="center" src="topologia_estrela.png">
<br>

- **Anel:** Presença de um cabo coaxial (ou fibra óptica) fechado sobre si próprio (anel), ao qual se ligam os vários computadores da rede. Dessa maneira, sinais ou mensagens circulam dentro do anel, passando sequencialmente (Ponto-a-Ponto) de ligação em ligação até chegar ao destinatário.
	- **Vantagens:** Ideal para uso de fibra óptica por cada ponto pode estar diretamente ligado ao outro.
	- **Desvantagens:** Necessidade de hardware adequado (*transceivers*) para a ligação dos computadors às redes, todos os computaores precisam estar ligados para funcionar e a avaria de um computador pode invalidar a rede e não é fácil identificar o posto avariado.

<img alt="center" src="topologia_anel.png">
<br>

- **Malha:** Dispositivos de interligação (*routers*) se encarregam do encaminhamento das mensagens mediante os vários nós da malha constituída (Ponto-a-Ponto). Isto posto, o número de links é determinado da seguinte maneira: (número de nós * (número de nós - 1)) / 2.
	- **Vantagens:** Vários caminhos possíveis e privacidade.
	- **Desvantagens:** Maior complexidade da rede e elevado preço do equipamento de interligação de nós (dispositivos I/O).

<img alt="center" src="topologia_malha.png">
```
````