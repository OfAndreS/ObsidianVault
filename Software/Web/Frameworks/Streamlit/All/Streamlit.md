
---
#### **Intro )** - Premissa e Objetivo

> [!quote] **Def**
> 
> **Summary:**
> 
> - Como a documentação oficial do Streamlit é excelente e amplamente indexada, o foco desta estrutura abandona a sintaxe básica e prioriza _modelos mentais_, _soluções de problemas estruturais_ e _snippets de código escaláveis_ para compor um índice pragmático.
>     

> [!quote] **Vault:** [[ST - Use cases]]

> [!quote] **Link:** [Streamlit Docs](https://docs.streamlit.io/)

> [!quote] **Link:** [Streamlit Extras](https://extras.streamlit.app/)

---

> [!done] _New_

---
#### **01 ) -** Paradigmas de Execução e Performance

> [!quote] **Def**
> 
> **Summary:**
> 
> - 
>     

> [!quote] **Vault:** [[ST - Execução e Performance]]

---

> [!done] _New_

---
#### **02 ) -** Gerenciamento Avançado de Estado

> [!quote] **Def**
> 
> **Summary:**
> 
> - Manipulação de _Session State_: padrões para não perder dados durante o _rerun_.
>     
> - Controle de fluxo via _Callbacks_ (_on_change_, _on_click_).
>     
> - Sincronização de estado entre _multipage apps_ (métricas globais vs locais).
>     

> [!quote] **Vault:** [[Streamlit MOC - Gerenciamento de Estado]]

---

> [!done] _New_

---
#### **03 ) -** Navegação Entre Páginas

> [!quote] **Def**
> 
> **Summary:**
> 
> - 

> [!quote] **Vault:** [[Streamlit MOC - Design de Componentes]]

---

> [!done] _New_

---
#### **04 ) -** Persistência e Pipeline de Dados

> [!quote] **Def**
> 
> **Summary:**
> 
> - Conectividade eficiente com _st.connection_ versus abordagens legadas de banco de dados.
>     
> - Manipulação de sessões assíncronas (_Async_ no Streamlit) para chamadas pesadas de API.
>     
> - Estratégias de paginação para carregamento de grandes volumes de dados.
>     

> [!quote] **Vault:** [[Streamlit MOC - Persistência de Dados]]

---

> [!done] _New_

---
#### **05 ) -** Infraestrutura, Segurança e Deploy

> [!quote] **Def**
> 
> **Summary:**
> 
> - _Dockerização_ otimizada: templates de _Dockerfile_ e _docker-compose.yml_ ajustados para produção.
>     
> - Gestão segura de credenciais (_Secrets_) em ambientes locais e conteinerizados.
>     
> - Limitações do _Community Cloud_ e roteiro de migração para instâncias dedicadas (_AWS_, _GCP_).
>     

> [!quote] **Vault:** [[Streamlit MOC - Infraestrutura e Deploy]]

---

> [!done] _New_

---
#### **06 ) -** Repositório de Padrões e Resolução de Erros

> [!quote] **Def**
> 
> **Summary:**
> 
> - _Boilerplates_ padronizados para _Dashboards_, ferramentas de IA e _CRUDs_.
>     
> - _Troubleshooting_ de erros comuns de paralelismo estrutural (conflitos de porta, travamento de _threads_).
>     

> [!quote] **Vault:** [[Streamlit MOC - Padrões e Resolução]]

----

> [!done] _New_

---
#### **07 ) -** Protocolos para Manutenção das Notas

> [!quote] **Def**
> 
> **Summary:**
> 
> - Foco no porquê e em como estruturar, negligenciando a sintaxe básica presente na documentação oficial.
>     
> - Isolamento de _snippets_ autocontidos para garantir o reuso imediato em novos projetos.
>     
> - Indexação estrita por _tags_ visuais (ex: _#streamlit/estado_, _#snippet/ui_) para facilitar buscas horizontais.
>     

> [!quote] **Vault:** [[Streamlit - Protocolos de Manutenção]]