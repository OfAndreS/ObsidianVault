
---

>[!example] #### **Introdução: A Camada Fundamental de Software**

---

```ad-quote
title: **Def**

Em sua essência, um sistema operacional é a camada de software fundamental que reside entre o hardware do computador e os aplicativos do usuário. 

Sua principal função é: 
- Gerenciar os recursos de hardware de maneira eficiente e fornecer uma interface abstrata para que os aplicativos possam ser executados sem se preocuparem com as complexidades do hardware subjacente. 
  
  
Sem um SO, a interação com o hardware seria extremamente complexa e ineficiente.
```

---

>[!tip] **1 ) Abstração e Gerenciamento de Recursos de Hardware**

---

```ad-quote
title: **Def**

O SO atua como um **gerente de recursos**, orquestrando o uso dos componentes físicos do computador. Essa gestão envolve:
```

---
##### **Gerenciamento da CPU**

```ad-quote
title: **Def**

O SO implementa algoritmos de **Escalonamento de Processos** 
- (e.g., _First-Come, First-Served_, _Round Robin_, _Priority Scheduling_) 
  
Determinando qual processo terá acesso ao processador em um dado momento. O objetivo é maximizar o _throughput_ (taxa de conclusão de tarefas), minimizar a _latência_ (tempo de resposta) e garantir a _justiça_ na alocação do tempo de processamento.
```

```ad-quote
title: **Def**

Em sistemas _multicore_, o SO também gerencia a distribuição de processos entre os diferentes núcleos para paralelizar a execução e aumentar o desempenho.
```

---
##### **Gerenciamento da Memória Principal RAM**

```ad-quote
title: **Def**


O SO é responsável pela: 
- **Alocação** e **Desalocação** de blocos de memória para os processos. 
  
Técnicas como **Paginação** e **Segmentação** são utilizadas para dividir a memória em unidades menores e facilitar a alocação.
```

```ad-quote
title: **Def**

O conceito de **Memória Virtual** permite que os processos utilizem mais memória do que a fisicamente disponível, através da troca de partes da memória para o disco rígido 
- (arquivo de _swap_)
  
Isso aumenta a capacidade de executar múltiplos programas simultaneamente.
```

---
##### **Gerenciamento de Dispositivos de Entrada/Saída (I/O):**

```ad-quote
title: **Def**

O SO fornece uma interface uniforme para que os aplicativos interajam com uma variedade de dispositivos (teclado, mouse, disco, rede, etc.). Isso é feito através de 
- **Drivers de dispositivo** 
  
que são softwares específicos para cada tipo de hardware.
```

```ad-quote
title: **Def**

O SO lida com as interrupções geradas pelos dispositivos de E/S, sinalizando a conclusão de operações ou a ocorrência de eventos. Técnicas como 
- **Acesso Direto à Memória (DMA)** 
  
permitem que dispositivos transfiram dados diretamente para a memória sem a intervenção constante da CPU, melhorando a eficiência.
```

---
##### **Gerenciamento de Armazenamento Secundário (Disco Rígido, SSD):**

```ad-quote
title: **Def**

O SO implementa um **Sistema de arquivos** 
- (e.g., FAT32, NTFS, ext4) Que organiza os dados em arquivos e diretórios. 
  
Ele gerencia o espaço em disco, controla o acesso aos arquivos e mantém a integridade dos dados através de metadados (informações sobre os arquivos).
```

```ad-quote
title: **Def**

 Operações como criar, ler, escrever, excluir e renomear arquivos são abstraídas pelo SO, fornecendo uma interface lógica para os aplicativos.
```

---

>[!tip] **2 ) Interface entre Usuário e Hardware**

---

```ad-quote
title: **Def**

O SO oferece um **paradigma de interface de usuário** para facilitar a interação entre o ser humano e o computador. As duas formas principais são:
```

---
##### **Interface Gráfica do Usuário (GUI):** 

```ad-quote
title: **Def**

Utiliza elementos visuais como janelas, ícones e menus para permitir a interação através de um ponteiro (mouse, _touchscreen_). O SO é responsável por gerenciar o ambiente gráfico, incluindo o sistema de janelas e o _desktop environment_.
```
##### **Interface de Linha de Comando (CLI):** 

```ad-quote
title: **Def**

Permite a interação através da digitação de comandos de texto. Embora menos intuitiva para usuários iniciantes, a CLI oferece grande poder e flexibilidade para tarefas automatizadas e administração do sistema.
```

---

>[!tip] **3 ) Gerenciamento de Processos e Aplicações:**

---

```ad-quote
title: **Def**

O SO é o responsável por gerenciar o ciclo de vida dos **processos**, que são instâncias em execução de um programa.
```

---
##### **Criação e Destruição de Processos:** 

```ad-quote
title: **Def**

- O SO permite a criação de novos processos (e.g., quando um aplicativo é iniciado) e a sua terminação (normalmente ou forçadamente).
```
##### **Estados do Processo:** 

```ad-quote
title: **Def**

- O SO permite a criação de novos processos (e.g., quando um aplicativo é iniciado) e a sua terminação (normalmente ou forçadamente).
```
##### **Comunicação entre Processos (IPC):** 

```ad-quote
title: **Def**

- O SO permite a criação de novos processos (e.g., quando um aplicativo é iniciado) e a sua terminação (normalmente ou forçadamente).
```
##### **Gerenciamento de Threads:** 

```ad-quote
title: **Def**

- O SO permite a criação de novos processos (e.g., quando um aplicativo é iniciado) e a sua terminação (normalmente ou forçadamente).
```

---

>[!tip] **4 ) Serviços Essenciais e Chamadas de Sistema**

---

```ad-quote
title: **Def**

O SO fornece uma série de **serviços essenciais** que são utilizados pelos aplicativos. Esses serviços são acessados através de 
- **chamadas de sistema** (_system calls_) 
  
Que são solicitações feitas por um programa ao kernel do SO para executar uma tarefa privilegiada (que envolve acesso direto ao hardware ou a recursos protegidos). Exemplos de chamadas de sistema incluem:

- Criação e manipulação de arquivos (`open`, `read`, `write`, `close`).
- Criação e controle de processos (`fork`, `exec`, `wait`).
- Alocação e liberação de memória (`malloc`, `free`).
- Comunicação em rede (`socket`, `connect`, `send`, `receive`).
```

---

> [!tip] **5 ) Segurança e Proteção**

---

```ad-quote
title: **Def**

O SO implementa mecanismos de segurança para proteger o sistema contra acesso não autorizado, erros de programação e softwares maliciosos. Isso inclui:

**Gerenciamento de Usuários e Permissões:** 
- O SO gerencia contas de usuário e atribui permissões para controlar o acesso a arquivos e recursos do sistema.
  
  
**Controle de Acesso:** 
- Mecanismos como listas de controle de acesso (ACLs) definem quais usuários ou grupos têm permissão para executar determinadas ações em arquivos e diretórios.


**Proteção de Memória:** 
- O SO impede que um processo acesse a área de memória de outro processo, evitando interferências e falhas.


**Mecanismos de Defesa:** 
- Alguns SOs incluem firewalls e outros mecanismos para proteger o sistema contra ameaças externas.
```

---
