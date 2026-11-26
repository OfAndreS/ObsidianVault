
---

```embed
title: "Padrões de Commits e Estratégias de Branches · engvictor"
image: ""
description: "Como desenvolvedor de sistemas e graduando em um curso de Tecnologia, uma das questões que encontro entre os estudantes e entre alguns colegas de trabalho é sobre como manter o controle d..."
url: "https://www.tabnews.com.br/engvictor/padroes-de-commits-e-estrategias-de-branches"
favicon: ""
```

>[!quote] **Link:** [Conventional Commits Official](https://www.conventionalcommits.org/en/v1.0.0/)

>[!quote] **Link:** [GitHub Flow Documentation](https://docs.github.com/en/get-started/using-github/github-flow)

---

```ad-done
title:
#### **Fase 1 ) - Padrões de Commit (Conventional Commits)**
```

---

````ad-quote
title:

##### **01 )** - Conventional Commits

```ad-quote
title:
<p align="justify">Manter um histórico de projeto organizado não só facilita a compreensão das mudanças realizadas ao longo do tempo, mas também potencializa a colaboração entre desenvolvedores. O <i>Conventional Commits</i> é uma convenção estruturada e amplamente adotada que define regras simples para criar registros de alterações consistentes e legíveis.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Estrutura e Tipos de Commit_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Anatomia do Commit*
```

```ad-quote
title:
<p align="justify">Cada mensagem segue o formato padrão <b>tipo(escopo): descrição</b>. No exemplo abaixo, o prefixo <i>feat</i> sinaliza que uma nova funcionalidade foi adicionada, enquanto o escopo <i>login</i> esclarece exatamente o módulo afetado.</p>
```

```shell
# Exemplo de Conventional Commit:
feat(login): adiciona captcha à tela de login
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Tipos de Commit*
```

```shell
01 ) feat
# Indica a adição de uma nova funcionalidade ao projeto. Sinaliza crescimento e novos recursos para o usuário.


02 ) fix
# Usado para correções de bugs. Essencial para garantir estabilidade e resolução rápida de problemas identificados.


03 ) docs
# Refere-se exclusivamente a alterações na documentação (como arquivos README, manuais, guias e comentários).


04 ) style
# Modificações de formatação que não alteram a lógica do código (espaçamento, ponto e vírgula, indentação, etc.).


05 ) refactor
# Alteração no código que não corrige bug nem adiciona funcionalidade nova. Foca na melhoria da qualidade estrutural interna.


06 ) test
# Inclui adição ou correção de testes automatizados (unitários, integração ou end-to-end) em todo o projeto.


07 ) chore
# Manutenções de tarefas e arquivos de configuração que não modificam código-fonte de produção nem testes.


08 ) build
# Alterações que afetam o sistema de build ou ferramentas auxiliares (scripts de build, package.json, webpack, etc.).
```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _Escopo do Commit_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Aplicação do Escopo*
```

```ad-quote
title:
<p align="justify">O escopo é inserido entre parênteses logo após o tipo (como em <i>feat(login)</i>). Ele indica explicitamente qual área ou componente do sistema recebeu a modificação, tornando dispensável inspecionar o código linha a linha para entender o impacto. Embora seja opcional pelo padrão, seu uso é fortemente encorajado para refinar o rastreamento em equipe.</p>
```

```shell
# Exemplos com escopo bem definido:
feat(auth): implementa autenticação via token JWT
fix(checkout): resolve inconsistência no cálculo de frete
```

````

---

```ad-done
title:
#### **Fase 2 ) - Estratégias de Branches (GitHub Flow)**
```

---

````ad-quote
title:

##### **02 )** - Ciclo de Branches

```ad-quote
title:
<p align="justify">A separação do fluxo de trabalho em ramificações específicas garante que o código em produção permaneça continuamente estável, ao mesmo tempo em que permite desenvolvimento simultâneo e revisões de código isoladas.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Tipos de Branches_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Nomenclatura e Finalidades*
```

```shell
01 ) main
# Contém a versão atual do software em produção. Todo código aqui consolidado deve estar estável e pronto para os usuários.


02 ) dev / develop
# Concentra todos os desenvolvimentos e integrações em andamento que ainda não foram implantados no ambiente de produção.


03 ) hotfix
# Usada para correções críticas e emergenciais que não podem aguardar a próxima versão planejada (ex: hotfix/correcao-crash-login).


04 ) bugfix
# Usada para correções de bugs de menor urgência identificados durante o ciclo regular de desenvolvimento.


05 ) feature
# Criada a partir da develop para implementar uma funcionalidade específica e isolada (ex: feature/funcionalidade-y).
```

````

---

```ad-done
title:
#### **Fase 3 ) - Integração Contínua (Pull Requests & Issues)**
```

---

````ad-quote
title:

##### **03 )** - Ciclo Colaborativo

```ad-quote
title:
<p align="justify">O fluxo contínuo de colaboração articula o planejamento com o código final por meio de revisões sistemáticas em Pull Requests e vínculo direto a Issues rastreáveis.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Fluxo de Trabalho e Rastreamento_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Etapas do Ciclo de Integração*
```

```shell
01 ) Registro da Issue
# Cada funcionalidade ou correção nasce como uma Issue no GitHub, estabelecendo claramente o objetivo e escopo da tarefa.


02 ) Desenvolvimento da Feature
# O desenvolvedor cria a branch feature específica e realiza commits orientados pelo padrão Conventional Commits.


03 ) Abertura do Pull Request
# Após finalizar a feature, abre-se um Pull Request apontando para a branch develop, disparando a revisão por pares (Code Review).


04 ) Validação em Develop
# Todas as novas funcionalidades e correções aprovadas são testadas de forma integrada no ambiente de desenvolvimento.


05 ) Deploy em Produção (Main)
# Ao atingir maturidade, a develop é mesclada na main, passando pela validação final antes do lançamento definitivo aos usuários.
```

````

---