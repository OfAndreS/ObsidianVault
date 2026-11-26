
---

```ad-quote
title: **Def**

O **"S" do SOLID** representa o princípio da **Responsabilidade Única (Single Responsibility Principle - SRP)**, que é um dos cinco princípios de design de software orientado a objetos que compõem o acrônimo SOLID.
```

---
#### **Definição do SRP:**

```ad-quote
title: **Def**

> *"Uma classe deve ter apenas um motivo para mudar, ou seja, deve ter apenas uma responsabilidade."*  

Isso significa que uma classe deve ser especializada em um único aspecto do sistema e não assumir múltiplas responsabilidades.
```

---
#### **📌 Quando o SRP é Violado?**

```ad-quote
title: **Def**

- Se uma classe tem **muitos métodos não relacionados**.
- Se uma mudança em uma regra exige alterar a classe em vários lugares.
- Se é difícil testar a classe isoladamente.
```

---
#### **Objetivo do SRP:**

```ad-quote
title: **Def**

**Reduzir o acoplamento:** 
- Entre classes.

**Aumentar a coesão:**
- Garantindo que cada classe faça apenas uma coisa bem feita.

**Facilitar a manutenção:**
- Pois mudanças em uma funcionalidade afetam apenas a classe responsável por ela.
```

---

```ad-error
#### **Exemplo Completo**
```

---
#### **📦 Sistema de Pedidos (Exemplo Completo com SRP)**

```ad-quote
title: **Def**

###### **Requisitos:**
**1 )** Registrar um pedido com itens.

**2 )** Calcular o total do pedido.

**3 )** Salvar o pedido no banco de dados.

**4 )** Enviar um e-mail de confirmação ao cliente.

**5 )** Gerar um log das operações.

```

---
#### **⚠️ Versão Violando o SRP / Problema**

```java
class Pedido {
    public void adicionarItem(Item item) { /* ... */ }
    public void calcularTotal() { /* ... */ }
    public void salvarNoBanco() { /* ... */ }
    public void enviarEmailConfirmacao() { /* ... */ }
    public void gerarLog() { /* ... */ }
}
```

```ad-quote
title: **Def**

###### **Problemas:**
- A classe `Pedido` faz **tudo** (regras de negócio, banco de dados, e-mail, logs).
- Se qualquer uma dessas funcionalidades mudar, a classe precisará ser alterada.
- Dificulta testes e manutenção.
```

---

>[!tip] ##### **Versão Aplicando o SRP / Solução**

---

```ad-quote
title: **Def**

Vamos dividir as responsabilidades em classes especializadas:
```

---
#### **✔️Benefícios da Solução (SRP Aplicado)**

```ad-quote
title: **Def**

1 ) **Cada classe tem uma única responsabilidade**:
   - `Pedido`: Gerencia itens e cálculo.
   - `PedidoRepository`: Cuida do banco de dados.
   - `EmailService`: Lida com envio de e-mails.
   - `Logger`: Registra logs.
   - `PedidoFacade` (opcional): Orquestra o processo.

2 ) **Fácil manutenção**:
   - Se a forma de salvar no banco mudar, só `PedidoRepository` é afetado.
   - Se o formato do e-mail mudar, só `EmailService` precisa ser alterado.

3 ) **Testabilidade**:
   - Cada classe pode ser testada isoladamente (ex.: mockar `EmailService` para testes).

4 ) **Baixo acoplamento**:
   - As classes não dependem diretamente umas das outras (exceto `PedidoFacade`).
```

---
#### *1 ) `Pedido` / Responsabilidade: Representar o pedido e suas regras*

```java
class Pedido {
    private List<Item> itens;
    
    public void adicionarItem(Item item) {
        itens.add(item);
    }
    
    public double calcularTotal() {
        return itens.stream().mapToDouble(Item::getPreco).sum();
    }
}
```

---
#### *2 ) `PedidoRepository` / Responsabilidade: Persistência no banco de dados*

```java
class PedidoRepository {
    public void salvar(Pedido pedido) {
        System.out.println("Salvando pedido no banco de dados...");
        // Lógica de INSERT no BD
    }
}
```

---
#### *3 ) `EmailService` / Responsabilidade: Enviar e-mails*

```java
class EmailService {
    public void enviarConfirmacao(Pedido pedido) {
        System.out.println("Enviando e-mail de confirmação...");
        // Lógica de envio de e-mail
    }
}
```

---
#### *4 ) `Logger` / Responsabilidade: Registrar logs*

```java
class Logger {
    public void log(String mensagem) {
        System.out.println("[LOG] " + mensagem);
    }
}
```

---
#### *5 ) `PedidoFacade` / Opcional: Coordena as operações*

```java
class PedidoFacade {
    private PedidoRepository repository;
    private EmailService emailService;
    private Logger logger;
    
    public PedidoFacade() {
        this.repository = new PedidoRepository();
        this.emailService = new EmailService();
        this.logger = new Logger();
    }
    
    public void finalizarPedido(Pedido pedido) {
        double total = pedido.calcularTotal();
        repository.salvar(pedido);
        emailService.enviarConfirmacao(pedido);
        logger.log("Pedido finalizado: R$" + total);
    }
}
```

---
#### **📌 Como Usar / Exemplo de Cliente**

```java
public class Main {
    public static void main(String[] args) {
        Pedido pedido = new Pedido();
        pedido.adicionarItem(new Item("Livro", 50.0));
        pedido.adicionarItem(new Item("Caneta", 5.0));
        
        PedidoFacade facade = new PedidoFacade();
        facade.finalizarPedido(pedido);
    }
}
```
###### **Saída:**

```
Salvando pedido no banco de dados...
Enviando e-mail de confirmação...
[LOG] Pedido finalizado: R$55.0
```

---

