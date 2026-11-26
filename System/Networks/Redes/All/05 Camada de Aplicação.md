
---

````ad-quote
title:
```ad-quote
title:
A princípio, ela é responsável pelas funcionalidades de rede (comunicação) das aplicações do **usuário** e de alguns protocolos auxiliares de uso geral. Nesse sentido, usa serviços de comunicação da camada de transporte e é a camada **mais próxima do usuário**.
```
```ad-quote
title: **Modelo TCP/IP**
No modelo TCP/IP, a camada de aplicação engloba as funcionalidades das camadas de **sessão**, **apresentação** e **aplicação** do modelo **OSI**. Nessa camada, são definidos o tipo das mensagens de **requisição** e **resposta**, sintaxe das mensagens, determinando os campos usados nas mensagens e como são organizados, semântica (significado) das informações contidas nos campos dos protocolos e regras para definir como e quando as aplicações **enviam** e **respondem** as **mensagens**.
- **Camada de Aplicação (OSI):** Responsável pela comunicação em rede entre programas em execução (processos) em diferentes *hosts*, enviando e recebendo os dados entre os processos e fazendo a interação com o usuário (pessoa ou sistema). Exemplo: jogo FPS online enviando para o servidor as ações do usuário e recebendo do servidor a situação dos demais participantes.
<br>
- **Camada de Apresentação (OSI):** Apresenta os dados em um formato independente da arquitetura dos sistemas participantes da comunicação, realizando a manutenção da semântica das informações transmitidas. Exemplos: criptografia e compressão.
<br>
- **Camada de Sessão (OSI):** Estabelece a comunicação entre processos em máquinas diferentes, criando e mantendo os diálogos entre as aplicações de origem e de destino e controlando as sessões de comunicação (mantém em atividade, pausa ou reinicia, se necessário). Exemplo: RPC.
```
```ad-quote
title: **Arquiteturas**
- **Arquitetura Cliente-Servidor:**
	- **Cliente:** Inicia a comunicação com o servidor e não se comunica diretamente com outros clientes. Exemplo: navegador web.
	- **Servidor:** Responde às requisições dos clientes, mantendo o *host* e os serviços sempre ativos. Nesse sentido, apresenta endereço IP permanente e/ou resolvido por meio do DNS. Exemplo: servidor web.
<br>
- **Arquitetura *Peer-to-Peer*:** Comunicação direta entre pares de *hosts* (*peers*). Os pares alternam entre si as funções de servidor e de cliente, o que aumenta muito a escalabilidade. Exemplos: Gnutella, Kazaa e BitTorrent.
<br>
- **Arquitetura  Híbrida:** Provê o gerenciamento e controle centralizados presentes no modelo servidor com a escalabilidade e tolerância à falhas da arquitetura *Peer-to-Peer* (o melhor dos dois mundos).
	- **Cliente-Servidor:** Autenticação, autorização, controle de presença, localização de *peers* e recursos compartilhados.
	- **P2P**: Troca de mensagens (*instant messenger*), áudio, videoconferência e transferência de arquivos entre pares. Exemplos: Napster, Skype e Spotify (até 2014).
```
```ad-quote
title: **Comunicação entre Processos**
Duas aplicações em *hosts* distintos se comunicam através do **envio de mensagens na rede**. No entanto, um *host* pode executar diversos processos que utilizam a rede simultaneamente.
```
```ad-quote
title:
Nesse contexto, mediante a **API (*Application Programming Interface*)** de rede do sistema operacional, as aplicações solicitam a criação de *sockets* de comunicação para permitir o envio e recepção de dados. Logo, cada *socket* está vinculado a um único processo, fazendo com que a comunicação destinada a ele seja encaminhada sem equívoco à aplicação correspondente.
```
```ad-quote
title:
Os sockets são definidos a partir do **endereço IP do *host*** e de um **número de porta** de um dos protocolos da camada de transporte (TCP ou UDP). Exemplo: 10.1.1.1:**80** (servidor web em execução no *host* com IP 10.1.1.1).

<img alt="center" src="comunicacao_processos.png">
```
```ad-quote
title: **Protocolos**
- **HTTP/HTTPS** (80/443 - TCP/UDP), **DNS** (53 - TCP/UDP), **DHCP** (67/68 - UDP), **SMTP** (25 - TCP), **SSH** (22 - TCP), **FTP** (20/21 - TCP), entre outros.
```
````