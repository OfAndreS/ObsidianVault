
---

````ad-quote
title:
##### **1 ) -** Seleção e Filtragem - Busca

```ad-quote
title:
O objetivo aqui é extrair fatias específicas dos dados para análise ou visualização sem comprometer a integridade do dataset original.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Indexadores loc e iloc:** 
```

>[!done]

```ad-quote
title:
Dominar a diferença entre a seleção por rótulos através do _loc_ e a seleção por coordenadas inteiras com o _iloc_. Para acesso ultra-rápido a valores escalares únicos, utilize os métodos _at_ e _iat_, que possuem menor sobrecarga computacional.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Filtragem Condicional e Query:**
```

>[!done]

```ad-quote
title:
Criar máscaras booleanas para filtrar linhas que atendem a critérios lógicos. O método _query_ permite escrever essas condições de forma mais elegante e legível, utilizando uma sintaxe baseada em strings que facilita a manutenção do código.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **2 ) -** Manipulação de Estrutura - CRUD

```ad-quote
title:
Operações fundamentais para alterar a "carcaça" do seu DataFrame, permitindo a evolução do esquema de dados conforme a necessidade do projeto.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Gestão de Colunas e Linhas:**
```

>[!missing]

```ad-quote
title:
Utilizar a atribuição direta para criar novas colunas ou o método _insert_ para posicioná-las especificamente. Para a remoção de dados redundantes, o método _drop_ é essencial, enquanto o _pop_ permite extrair uma coluna e removê-la simultaneamente.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Renomeação e Atualização:**
```

>[!missing]

```ad-quote
title:
Aplicar o método _rename_ para ajustar os nomes de eixos, garantindo que as colunas sigam padrões de nomenclatura profissionais. As atualizações de valores podem ser feitas de forma pontual ou em lote através de fatiamento e atribuição.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **3 ) -** Aplicação de Funções e Transformação

```ad-quote
title:
A capacidade de aplicar lógica personalizada sobre grandes volumes de dados de maneira vetorizada ou iterativa.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Família Apply e Map:**
```

>[!missing]

```ad-quote
title:
Usar o _apply_ para lógicas complexas que dependem de colunas inteiras e o _map_ para substituições rápidas em _Series_ baseadas em dicionários. Para operações que devem atingir cada célula individual de um DataFrame, o _applymap_ é a ferramenta adequada.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Encadeamento com Pipe:**
```

>[!missing]

```ad-quote
title:
Implementar o método _pipe_ para organizar sequências de transformações. Isso evita a criação de variáveis intermediárias desnecessárias e torna o fluxo de processamento de dados muito mais próximo da leitura de um texto estruturado.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **4 ) -** Agrupamento e Agregação

```ad-quote
title:
O motor principal para gerar inteligência e resumos estatísticos a partir de dados brutos e volumosos.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Ciclo GroupBy:**
```

>[!missing]

```ad-quote
title:
Dominar o processo de _Split-Apply-Combine_. Dividir o dataset em grupos lógicos para aplicar funções estatísticas independentes, permitindo comparar métricas entre diferentes categorias de dados de forma automática.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Agregação e Transformação de Grupo:**
```

>[!missing]

```ad-quote
title:
Utilizar o método _agg_ para rodar múltiplas estatísticas simultaneamente. O método _transform_ é vital para normalizar dados dentro de grupos, mantendo a dimensionalidade original do DataFrame para facilitar operações subsequentes.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **5 ) -** Combinação de Datasets

```ad-quote
title:
Integrar múltiplas fontes de informação, simulando o comportamento de bancos de dados relacionais dentro do ambiente Python.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Merge e Join Relacional:**
```

>[!missing]

```ad-quote
title:
Executar junções de tabelas com _merge_ utilizando chaves comuns, suportando tipos como _inner_, _outer_, _left_ e _right_. O método _join_ oferece uma alternativa otimizada quando o objetivo é combinar dados através dos seus índices.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Concatenação e Empilhamento:**
```

>[!missing]

```ad-quote
title:
Usar o _concat_ para unir múltiplos objetos pandas ao longo de um eixo específico. Esta operação é ideal para consolidar logs diários ou arquivos de áudio processados em um único conjunto de dados mestre.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **6 ) -** Reestruturação e Modelagem (Reshaping)

```ad-quote
title:
Alterar a orientação espacial dos dados para se adequar a requisitos de visualização ou algoritmos de machine learning.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Pivot e Melt:**
```

>[!missing]

```ad-quote
title:
Girar tabelas com o _pivot_ para criar matrizes de comparação ou usar o _melt_ para "despivorar" os dados, transformando colunas em linhas. Este processo é fundamental para deixar os dados no formato _tidy_, facilitando o uso de bibliotecas de plotagem.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Hierarquia e Explosão:**
```

>[!missing]

```ad-quote
title:
Trabalhar com índices multinível através de _stack_ e _unstack_. O método _explode_ é particularmente útil para lidar com colunas que contêm listas, transformando cada elemento da lista em uma linha individual.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **7 ) -** Limpeza e Tratamento de Dados

```ad-quote
title:
Garantir a qualidade do dado antes de sua utilização em modelos preditivos ou relatórios científicos.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Gestão de Valores Ausentes:**
```

>[!missing]

```ad-quote
title:
Implementar estratégias de preenchimento com _fillna_ ou remoção com _dropna_. Em séries temporais de áudio ou sinais, o uso de _interpolate_ pode ser vital para estimar valores perdidos com base na tendência dos dados vizinhos.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Duplicatas e Conversão de Tipos:**
```

>[!missing]

```ad-quote
title:
Identificar e eliminar registros repetidos com _drop_duplicates_. Utilizar o método _astype_ para converter tipos de dados, garantindo que valores numéricos não sejam tratados como strings, o que economiza memória e evita erros de cálculo.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **8 ) -** Acessores Especializados

```ad-quote
title:
Ferramentas de nicho que permitem manipular tipos específicos de dados com a mesma facilidade de uma linguagem de manipulação de strings ou datas.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Strings, Datas e Categorias:**
```

>[!missing]

```ad-quote
title:
Dominar o acessor _str_ para operações de texto complexas e o _dt_ para extrair componentes temporais. O acessor _cat_ permite lidar com dados categóricos, otimizando o armazenamento e permitindo ordenações lógicas não alfabéticas.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **9 ) -** Janelas Móveis e Séries Temporais

```ad-quote
title:
Essencial para o processamento de sinais e dados que possuem uma dependência temporal intrínseca.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Rolling e Expanding:**
```

>[!missing]

```ad-quote
title:
Calcular estatísticas em janelas deslizantes com o _rolling_, útil para suavizar ruídos em sinais de áudio. O método _expanding_ permite observar o comportamento acumulado dos dados desde o início da série histórica.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Frequência e Resampling:**
```

>[!missing]

```ad-quote
title:
Utilizar o _resample_ para mudar a granularidade temporal dos dados, agregando informações de milissegundos para segundos ou minutos, facilitando a análise de padrões de longo prazo.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **10 ) -** Estatística e I/O

```ad-quote
title:
A porta de entrada e saída para os dados, além das ferramentas para uma primeira análise exploratória rápida.
```
````

````ad-quote
title:
```ad-quote
title:
###### A ) - **Estatística Descritiva:**
```

>[!missing]

```ad-quote
title:
Extrair um panorama completo do dataset com o método _describe_. Calcular correlações com o _corr_ para entender as relações entre diferentes variáveis independentes e o alvo da sua pesquisa.
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) - **Interface de Arquivos:**
```

>[!missing]

```ad-quote
title:
Dominar os métodos de leitura e escrita para formatos modernos como _Parquet_ e _HDF5_, que são muito mais eficientes que o CSV para grandes volumes de dados científicos, preservando a tipagem das colunas.
```
````

---
