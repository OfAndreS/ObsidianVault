
---

````ad-quote
title:
```ad-quote
title:
Inicialmente, ela é responsável por permitir que as aplicações utilizem os **serviços da camada de rede**, sendo a primeira camada onde ocorre a comunicação fim-a-fim. Outrossim, vale ressaltar que ela utiliza **portas** para permitir a **multiplexação dos dados**, possibilitando que múltiplas aplicações utilizem a rede simultaneamente.
```
```ad-quote
title: **Faixas de Numeração de Portas**
As portas da camada de transporte no modelo TCP/IP possuem 16 *bits* e são organizadas em faixas de numeração, definidas na RFC 6335:
- **0-1023:** Portas de sistema, também chamadas de portas bem-conhecidas (atribuídas pela IANA).
- **1024-49151:** Portas de usuário, também conhecidas como portas registradas (atribuídas pela IANA).
- **49152-65535:** Portas dinâmicas, também denominadas de portas privadas ou efêmeras.
```
```ad-quote
title: **Orientação à Conexão**
- **Serviço Orientado à Conexão:** Provê a entrega confiável da informação após estabelecer um acordo prévio entre as partes, definindo os parâmetros da comunicação. Além disso, também apresenta mecanismos de controle de fluxo, confirmação de recebimento e reenvio. Exemplos: TCP (RFC 793) e telefonia.
<br>
- **Serviço Não-Orientado à Conexão:** Não provê essa confiança na entrega, e a informação é enviada sem garantia de entrega (*best-effort*) ou acordo prévio. Todavia, apresenta um *checksum* no cabeçalho UDP usado para verificar se os bits do segmento foram alterados durante a transmissão. Exemplos: IP (RFC 791), UDP (RFC 768) e Correios.
```
````