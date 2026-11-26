---

---

---

````ad-quote
title:
```ad-quote
title:
A princípio, modularizar significa decompor um projeto em componentes em que cada um terá uma responsabilidade específica, o que possibilita uma evolução gradual e em paralelo do sistema. Nesse sentido, cada módulo deve ter uma interface duradoura.
```
```ad-quote
title:
Por natureza, redes são modularizadas. Porém, como fazer isso? **Modelo em Camadas (*Layering*)** e implementados seguindo o **Princípio Fim-a-Fim (*End-to-End*)**. 
```
```ad-quote
title: **Modelo em Camadas (TCP/IP)**
Inspiração para esse modelo: o CEO A escreve uma carta para o CEO B, o CEO A entrega a carta ao Secretário A (o qual vai adicionar o nome completo do CEO B e colocar a carta em um envelope), o Secretário A entrega o envelope aos Correios (que adiciona o nome e o endereço da empresa do CEO B e coloca o envelope em um envelope maior), e, por fim, ocorre um processo inverso (dos Correios até o CEO B) e o CEO B recebe a carta.

<img alt="center" src="inspiracao_layering.png">
```
```ad-quote
title:
Funcionalidades separadas em **camadas**. Camada *N* faz interface somente com a camada *N-1* e *N+1*.

Comunicação entre mesmas camadas em diferentes sistemas é definida pelos **protocolos**.
```
```ad-quote
title: O que é um protocolo?
Um **acordo** entre as partes que irão se comunicar. Dessa forma, eles definem uma **sintaxe** de comunicação (formato de cabeçalho) e uma **semântica** ("primeiro um cumprimento, depois uma requisição"). Logo, um protocolo é o **formato** e a **ordem** das mensagens trocadas entre **duas** ou **mais entidades comunicantes**, controlando o **envio** e o **recebimento** de informações.
```
```ad-quote
title:
**L7 | Camada de Aplicação:**
Protocolos: SMTP, HTTP(S), DNS. NTP.

Mensagem/Dados.

**L4 | Camada de Transporte:**
Protocolos: TCP, UDP.

Segmento (TCP) ou datagrama (UDP).

**L3 | Camada de Rede:**
Protocolos: IP (unificador).

Pacote (*packet*).

**L2 | Camada de Enlace:**
Protocolos: Ethernet, FDDI, PPP.

Quadro (*frame*).

**L1 | Camada Física**
Protocolos: Óptico, Cobre, Rádio, PSTN.

*Bits*.

<img alt="center" src="hosts_e_roteadores.png">
```
````