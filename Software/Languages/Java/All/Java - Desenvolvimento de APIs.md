---
banner: "![[Pasted image 20250928150046.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O Modelo Cliente-Servidor

```ad-quote
title:
<p align="justify">No desenvolvimento de APIS (Application Programming Interfaces), o software é dividido em duas partes distintas que conversam através da rede. A linguagem universal dessa conversa é o HTTP (protocolo de transporte) e o JSON (formato dos dados).</p>
```

```ad-quote
title:
###### **Os Atores**
```

```ad-quote
title:
<p align="justify">O CLIENTE (FRONTEND/CONSUMER): Pode ser um navegador web, um aplicativo móvel ou outro servidor. Ele não sabe COMO a tarefa é feita, apenas solicita dados.</p>
```

```ad-quote
title:
<p align="justify">O SERVIDOR (BACKEND/API): É onde roda o código JAVA SPRING BOOT. Ele recebe pedidos, processa regras e devolve respostas. Ele é STATELESS (não guarda estado de tela do usuário) e passivo (só trabalha quando chamado).</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - A Arquitetura em Camadas

```ad-quote
title:
<p align="justify">No SPRING BOOT, organizamos o código em camadas horizontais, onde cada camada tem uma responsabilidade única e só pode conversar com a camada imediatamente abaixo.</p>
```

```ad-quote
title:

| Camada | Função Principal | Anotações Chave |
| :--- | :--- | :--- |
| **Controller** | Porta de entrada. Sabe o que é HTTP/JSON. Recebe requisições e valida formatos. | `@RestController`, `@PostMapping` |
| **Service** | O CÉREBRO. Contém a lógica de negócio e transações atômicas. É agnóstico de onde vêm os dados. | `@Service` |
| **Repository** | O BIBLIOTECÁRIO. Único que fala com o armazenamento (CSV/SQL). Faz o CRUD. | `@Repository` |
| **Model** | Classes de dados puros. Transportam informações entre camadas. | (Nenhuma específica) |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Ciclo de Vida de uma Requisição

```ad-quote
title:
<p align="justify">Quando um usuário clica em VOTAR no Frontend, eis o processo milimétrico dentro do Spring Boot:</p>
```

```ad-quote
title:

| Fase | Descrição |
| :--- | :--- |
| 1 - CHEGADA | O Servidor TOMCAT recebe o pacote HTTP na porta 8080. |
| 2 - ROTEAMENTO | O Spring olha a URL e procura qual método no CONTROLLER é responsável. |
| 3 - DESERIALIZAÇÃO | O Spring converte o JSON recebido para um OBJETO JAVA automaticamente (via Jackson). |
| 4 - PROCESSAMENTO | O Controller chama o SERVICE. O Service aplica regras e chama o REPOSITORY. |
| 5 - PERSISTÊNCIA | O Repository grava o dado no arquivo ou banco. |
| 6 - RETORNO | O caminho se inverte. O Controller recebe o OK, serializa a resposta em JSON e envia o status 200 OK. |

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Conceitos Avançados do Spring

```ad-quote
title:
<p align="justify">Para que tudo funcione magicamente, o Spring utiliza dois padrões fundamentais.</p>
```

```ad-quote
title:
###### **Inversão de Controle (IoC)**
```

```ad-quote
title:
<p align="justify">Em vez de você dar NEW nos objetos, quem cria e gerencia tudo é o CONTAINER DO SPRING. Ao iniciar, ele cria uma instância única (SINGLETON) de cada classe marcada.</p>
```

```ad-quote
title:
###### **Injeção de Dependência (DI)**
```

```ad-quote
title:
<p align="justify">Nós pedimos ao Spring para INJETAR o objeto pronto via construtor, garantindo acoplamento fraco.</p>
```

```java
@RestController
public class EnqueteController {
    
    private final VotacaoService service;

    // O Spring injeta o Service já criado aqui
    public EnqueteController(VotacaoService service) {
        this.service = service;
    }
}
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - O Protocolo HTTP na Prática

```ad-quote
title:
<p align="justify">Desenvolver uma API significa respeitar a semântica do protocolo HTTP. Retornamos intenções e estados, não apenas dados.</p>
```

```ad-quote
title:

| Tipo | Elemento | Significado |
| :--- | :--- | :--- |
| **Verbo** | GET | Quero LER dados. Nunca altera nada. |
| **Verbo** | POST | Quero CRIAR algo novo (Votar). |
| **Verbo** | PUT/PATCH | Quero ALTERAR algo existente. |
| **Verbo** | DELETE | Quero REMOVER algo. |
| **Status** | 2xx | Sucesso (200 OK, 201 Created). |
| **Status** | 4xx | Erro do Cliente (400 Bad Request, 404 Not Found). |
| **Status** | 5xx | Erro do Servidor (500 Internal Server Error). |

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Resumo

```ad-quote
title:
<p align="justify">Desenvolver uma API com SPRING BOOT é configurar e orquestrar componentes. Você define os MODELOS, isola as regras em SERVIÇOS e expõe tudo via ROTAS HTTP, deixando o Framework cuidar da rede e da memória.</p>
```
````

---