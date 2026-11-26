
---
Essa é uma excelente pergunta de arquitetura. No mundo do desenvolvimento web, a verificação de unicidade de usuários é um espectro que vai desde "muito simples e falho" até "extremamente seguro e invasivo".

Como o seu projeto (QuickVote) tem um requisito de NÃO ter login (RNF-06), você precisa escolher uma estratégia que equilibre SEGURANÇA com CONVENIÊNCIA.

Aqui estão todas as abordagens principais, organizadas da mais simples para a mais complexa:

---

### 1. Verificação por IP (Endereço de Rede)

É a abordagem que discutimos anteriormente. O servidor olha para o remetente do pacote de dados.

- **Como funciona:** O backend (Spring) captura o IP da requisição (`request.getRemoteAddr()`) e o armazena. Se o mesmo IP tentar votar, é bloqueado.
    
- **Prós:** Não exige nenhuma ação do usuário (transparente) e é muito fácil de implementar no backend.
    
- **Contras:** Bloqueia usuários legítimos que compartilham a mesma rede (NAT, Wi-Fi de Universidade, Empresas). Falha se o usuário reiniciar o modem ou usar VPN.
    

### 2. Verificação por Cookies ou LocalStorage (Marcador no Cliente)

Esta é a abordagem mais comum para enquetes rápidas na internet (como enquetes de jornais).

- **Como funciona:** Quando o usuário entra na página, o seu Frontend gera um ID aleatório único (um UUID) e salva no navegador dele (nos Cookies ou no LocalStorage). Toda vez que ele votar, esse ID é enviado junto.
    
- **Prós:** Resolve o problema do NAT (várias pessoas no mesmo Wi-Fi podem votar, pois cada navegador tem seu cookie).
    
- **Contras:** Se o usuário abrir uma "Aba Anônima" ou limpar o histórico do navegador, ele pode votar novamente. É fácil de burlar por usuários com conhecimento técnico mínimo.
    

### 3. Browser Fingerprinting (Impressão Digital do Navegador)

Esta é uma técnica avançada e "forense". Ela tenta identificar o computador sem instalar nada nele.

- **Como funciona:** O sistema coleta uma série de dados passivos: Resolução da tela, versão do navegador, lista de fontes instaladas, modelo da placa de vídeo, fuso horário e nível de bateria. Ao juntar tudo isso, cria-se um "hash" quase único.
    
- **Prós:** Muito difícil de burlar (mesmo na aba anônima, a resolução da tela e a placa de vídeo continuam as mesmas). Não bloqueia IPs compartilhados.
    
- **Contras:** É tecnicamente complexo de implementar (exige bibliotecas JS externas como `FingerprintJS`). Pode ter problemas de privacidade (LGPD) se não for bem documentado.
    

### 4. Verificação Social / Terceiros (OAuth Light)

Embora você não queira login tradicional, você pode exigir uma validação externa.

- **Como funciona:** O usuário precisa clicar em um botão "Verificar com Google" ou "Verificar com Twitter" antes de votar. O sistema recebe o ID dele, mas não salva senha nem cria conta.
    
- **Prós:** Extremamente seguro. Garante 1 pessoa = 1 voto.
    
- **Contras:** Adiciona atrito (friction). O usuário pode ter preguiça de clicar e desistir de votar. Fere parcialmente o espírito do seu RNF-06 (sem autenticação).
    

### 5. CAPTCHA (Prova de Humanidade)

Isso não impede necessariamente o voto duplo, mas impede a automação massiva.

- **Como funciona:** O usuário resolve um desafio (clicar em semáforos ou apenas clicar em "Não sou um robô").
    
- **Prós:** Impede que alguém crie um script Python para dar 10.000 votos em 1 segundo.
    
- **Contras:** Um humano dedicado ainda pode votar várias vezes manualmente.
    

---

### Tabela Comparativa para o QuickVote

---

### Minha Recomendação para o seu Projeto

Considerando que é um projeto de **aprendizado** e você precisa entregar valor rápido sem violar os requisitos:

Use uma abordagem **HÍBRIDA (IP + LocalStorage)**.

No seu Backend (Java), a classe `Enquete` que criamos com `Set<String> usuariosQueVotaram` é agnóstica. Ela aceita qualquer String. Então, você pode fazer o seguinte:

1. **No Frontend:** Gere um UUID aleatório e salve no navegador (`localStorage`). Envie isso para o backend.
    
2. **No Backend:** Receba esse UUID.
    
3. **A Lógica de Segurança:** O identificador único do usuário será uma combinação do IP + UUID.
    

Ou, para simplificar drasticamente para o MVP: Escolha a Opção 2 (LocalStorage/Cookie).

O Frontend envia um ID. O Backend (Java) verifica se esse ID está na lista usuariosQueVotaram.

- **Por que?** Evita o problema da UFRN (bloquear o campus inteiro pelo IP) e cumpre o requisito de persistência e controle de concorrência no Java.
    

Quer que eu te ajude a implementar essa lógica de receber um identificador genérico no **Service** antes de passarmos para a criação do arquivo CSV?