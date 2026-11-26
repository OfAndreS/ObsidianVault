
---

```embed
title: "194 - Diagramas de Arquitetura de Software e Deployment | theWiseDev Modelling"
image: "https://i.ytimg.com/vi/v-taFyrNXJY/maxresdefault.jpg"
description: "Com o advento do desenvolvimento ágil muitos devs passaram a ter ojeriza de diagramas! De fato, aquela documentação toda em UML não fazia muito sentido.Por o..."
url: "https://www.youtube.com/watch?v=v-taFyrNXJY"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Arquitetura Monolítica Modular: Organização Modular de Pastas"
image: "https://miro.medium.com/v2/resize:fit:847/1*NXACGIAcmMyxtDvOBrp4bg.png"
description: "Quando você está a desenvolver uma Aplicação Empresarial que será utilizada apenas pela empresa e os seus funcionários. Você não está a…"
url: "https://medium.com/@abel.ncm/arquitetura-monol%C3%ADtica-modular-estrutura%C3%A7%C3%A3o-escal%C3%A1vel-do-projecto-8888ed51f53b"
favicon: ""
aspectRatio: "30.57851239669421"
```


#### Padrões de arquitetura

Tem como principal objetivo definir a organização do código-fonte, as camadas do sistema e os limites de implantação. Dessa forma, garantindo a manutenibilidade, separação de responsabilidades, escalabilidade interna e desacoplamento de módulos. Além disso, as arquiteturas determinam onde colocar regras de negócio, onde isolar acessos a banco de dados e como empacotar os serviços.

##### Padrões de organização interna

```shell
01 ) O que é
# É a regra de desenho que organiza o código-fonte dentro de um único programa executável. Ele estabelece a estrutura lógica de pastas, módulos e classes.


02 ) O que define na prática
# Define quem chama quem dentro da memória do computador. Estabelece a fronteira entre regras de negócio, interfaces de usuário e acessos a banco de dados.


03 ) Pergunta que ele responde
# "Onde eu coloco este arquivo no projeto e qual parte do código tem permissão para usá-lo?"


04 ) Exemplos clássicos
# Arquitetura em Camadas, Arquitetura Hexagonal, Clean Architecture e MVC.
```

##### Padrões de distribuição e implantação

```shell
01 ) O que é
# É o modelo que determina como o sistema se divide em processos de execução e servidores físicos ou virtuais. Ele estabelece as fronteiras de rede.


02 ) O que define na prática
# Define se o sistema roda como um único executável ou como dezenas de serviços separados. Estabelece quais dados trafegam pela rede e onde cada banco opera.


03 ) Pergunta que ele responde
# "Quantos programas independentes nós vamos compilar, implantar e conectar via rede para o sistema funcionar?"


04 ) Exemplos clássicos
# Monólito, Monólito Modular, Microsserviços e Arquitetura Orientada a Eventos.
```