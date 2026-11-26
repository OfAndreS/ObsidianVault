
---
### **Melhores Casos de Uso**

- **Prototipagem de Aplicações de IA e LLMs**
    
    Construção acelerada de interfaces de chat e painéis de iteração para modelos locais ou requisições de API. A arquitetura se beneficia dos elementos de conversação nativos e da manipulação direta do _Session State_ para reter o contexto histórico.
    
- **Dashboards Interativos de Data Science**
    
    Renderização de análises exploratórias, visualizações dinâmicas e métricas de desempenho. Elimina a fricção de construir e manter um _frontend_ isolado, permitindo injeção direta de dados processados.
    
- **Ferramentas Internas e Sistemas de Backoffice**
    
    Desenvolvimento pragmático de painéis administrativos, painéis de auditoria ou formulários complexos para equipes operacionais. O foco recai puramente sobre a funcionalidade e o trânsito seguro de dados, onde a estética padronizada do _framework_ é suficiente.
    
- **Demonstração de Modelos Preditivos**
    
    Implementação de interfaces para que usuários finais testem modelos de _Machine Learning_ em tempo real. Permite o carregamento de arquivos ou o ajuste de tensores via controles deslizantes para observação imediata do _output_.
    
- **Simuladores e Projetores de Cenários**
    
    Estruturação de ferramentas financeiras ou matemáticas que demandam recálculo constante mediante a alteração de múltiplas variáveis de entrada, capitalizando o fluxo linear de execução _top-down_ inerente à ferramenta.
    

### **Casos de Uso Não Recomendados**

- **Aplicações B2C de Alta Escala**
    
    O modelo de estado mantido no servidor e o tráfego contínuo via _websocket_ tornam a sustentação de milhares de usuários simultâneos inviável e financeiramente ineficiente. Escalar esse modelo para o consumidor final é um erro arquitetural estrutural.
    
- **Interfaces com UI e UX Altamente Customizadas**
    
    Projetos que exigem _pixel-perfect design_, animações complexas ou fluxos de tela não lineares são incompatíveis. Tentar forçar o _design_ usando injeções massivas de CSS e HTML destrói a principal vantagem da plataforma, que é a velocidade de desenvolvimento. A correção aqui é adotar _React_ ou _Vue_ desde o início.
    
- **Sistemas de Baixa Latência e Tempo Real**
    
    Ferramentas de _trading_ de alta frequência, jogos ou plataformas de edição colaborativa simultânea falham estruturalmente nessa plataforma. A arquitetura de _rerun_ do _script_ a cada interação do usuário insere uma latência de rede perceptível e inaceitável.
    
- **Plataformas Dependentes de SEO**
    
    A renderização é feita no cliente via _JavaScript_ após o estabelecimento da conexão _websocket_. Isso impede que os motores de busca tradicionais indexem o conteúdo da página, inviabilizando aplicações que dependem de tráfego orgânico e ranqueamento web.
    
- **Aplicações Mobile-First Complexas**
    
    Embora exista responsividade nativa básica, o controle sobre a usabilidade em dispositivos móveis é raso. A ausência de acesso nativo direto a sensores do dispositivo, navegação por gestos ou manipulação avançada do _layout_ em telas pequenas resulta em uma experiência de usuário severamente degradada no celular.