
---

```ad-done
title:
#### **Fase 1 ) - Airflow**
```

---

````ad-quote
title:

##### **01 )** - Descrição

```ad-quote
title:
<p align="justify">Configuração e instalação do Apache Airflow em ambiente isolado Conda no Zorin OS, utilizando Python 3.11 para orquestração de pipelines de dados.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Criando e configurando o ambiente_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Criação do ambiente isolado*
```

```Bash

conda create -n Airflow python=3.11 -y
conda activate Airflow

```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Configuração no arquivo de inicialização*
```

```ad-quote
title:
<p align="justify">Para que o Airflow reconheça onde guardar configurações e bancos de dados sem precisar redigitar o caminho toda vez que abrir um terminal novo, adicione a variável diretamente ao arquivo de inicialização do sistema.</p>
```

```Bash

echo 'export AIRFLOW_HOME=~/airflow' >> ~/.bashrc
source ~/.bashrc

# É necessário executar o comando abaixo para verificar se deu certo
echo $AIRFLOW_HOME

```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _Instalação do Airflow_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Instalação*
```

```Bash

# Basta apenas copiar e colar os comandos abaixo no terminal

AIRFLOW_VERSION=2.10.0
PYTHON_VERSION="$(python -c 'import sys; print(f"{sys.version_info.major}.{sys.version_info.minor}")')"
CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"

# Comando para verificar se a instalação deu certo

airflow version
```

````

````ad-quote
title:

```ad-quote
title:
###### B ) *Execução*
```

```ad-quote
title:
<p align="justify">O comando standalone configura o banco de dados interno SQLite, cria o usuário inicial e sobe os serviços principais em um único processo. O sistema vai mostrar o usuário admin e uma senha temporária gerada para o primeiro acesso. Mantenha essa janela do terminal aberta enquanto estiver utilizando o Airflow.</p>
```

```Bash

airflow standalone

http://localhost:8080

```

````

---

```ad-done
title:
#### **Fase 1 ) - Airflow**
```

---

O Airflow é um orquestrador de fluxo de dados

- DAG
- Operators
- Tasks
- Comunicação entre tasks

https://www.youtube.com/watch?v=4DGRqMoyrPk

O que é um dag?
- Em sua essência, um DAG é uma coleção de tarefas organizadas de forma a refletir seus relacionamentos e dependências. É como um mapa do seu fluxo de trabalho, mostrando como cada tarefa se conecta às outras.

Arquivo de definição DAG
- Considere o script Python do Airflow como um arquivo de configuração que define a estrutura do seu DAG em código. As tarefas reais que você define aqui são executadas em um ambiente diferente, o que significa que este script não se destina ao processamento de dados. Sua principal função é definir o objeto DAG e precisa ser avaliado rapidamente, pois o Processador de Arquivos DAG o verifica regularmente em busca de alterações.


```python
from datetime import datetime, timedelta
from airflow import DAG
from airflow.operators.empty import EmptyOperator

argumentos_padrao = {
    "retries": 1,
    "retry_delay": timedelta(minutes=5),
    # "depends_on_past": False,
    # "execution_timeout": timedelta(minutes=30),
    # "on_failure_callback": funcao_alerta,
    # "on_success_callback": funcao_sucesso,
    # "pool": "nome_do_pool",
}

with DAG(
    dag_id="minha_pipeline_essencial",
    default_args=argumentos_padrao,
    start_date=datetime(2026, 1, 1),
    schedule=timedelta(minutes=1),
    catchup=False,
    # description="Descricao do fluxo",
    # tags=["dados", "producao"],
    # max_active_runs=1,
    # max_active_tasks=5,
    # dagrun_timeout=timedelta(hours=2),
    # on_failure_callback=alerta_geral,
    # doc_md="""Documentacao da DAG""",
) as dag:

    tarefa_exemplo = EmptyOperator(
        task_id="tarefa_inicial"
    )

    tarefa_exemplo
```

**Parâmetros de Identificação e Documentação** Configurações que dão nome, contexto e organização visual para a pipeline na interface gráfica.

- dag_id: define o identificador único da rotina dentro de todo o ambiente do Airflow.
    
- description: texto curto que resume a função da pipeline, exibido logo abaixo do nome na lista de DAGs.
    
- tags: lista de marcadores em texto usados para filtrar e agrupar pipelines relacionadas no painel web.
    
- doc_md: documentação detalhada escrita em formato Markdown, exibida na aba de documentação da interface para orientar quem opera o sistema.
    

**Parâmetros de Linha do Tempo e Agendamento** Controles que ditam o relógio de execução, o ritmo e o comportamento retroativo da rotina.

- start_date: data histórica fixa que serve como o marco zero a partir do qual o agendador calcula os intervalos.
    
- schedule: define a periodicidade com que a rotina deve rodar, aceitando atalhos predefinidos, intervalos de tempo ou expressões cron.
    
- catchup: valor booleano que determina se o Airflow deve rodar retroativamente todos os intervalos passados que ficaram pendentes desde o início da linha do tempo.
    

**Parâmetros de Infraestrutura e Concorrência** Travas de proteção que gerenciam a carga no computador, no banco de dados e na fila de processamento.

- max_active_runs: limita quantas instâncias completas dessa mesma DAG podem rodar ao mesmo tempo, impedindo sobreposição em caso de lentidão.
    
- max_active_tasks: determina a quantidade máxima de tarefas individuais que podem executar simultaneamente dentro dessa pipeline.
    
- dagrun_timeout: tempo limite total para o fluxo terminar; caso seja ultrapassado, a execução inteira é abortada com falha.
    
- default_args: dicionário que armazena configurações padronizadas que são repassadas automaticamente para todas as tarefas pertencentes ao fluxo.
    

**Parâmetros das Tarefas (usados em default_args ou direto na Task)** Diretrizes que dizem respeito ao comportamento e à resiliência de cada passo isolado de processamento.

- retries: número de tentativas adicionais que o sistema realiza caso aquela tarefa específica encontre um erro.
    
- retry_delay: período de pausa que o sistema espera antes de tentar executar novamente a tarefa após uma falha.
    
- execution_timeout: tempo máximo tolerado para a execução de uma única tarefa antes de forçar sua interrupção.
    
- depends_on_past: trava que impede uma tarefa de rodar hoje se a mesma tarefa na execução do dia anterior terminou com falha.
    
- pool: associa a tarefa a uma reserva limitada de recursos ou conexões, evitando sobrecarga em bancos ou serviços externos.
    

**Parâmetros de Monitoramento e Notificação (Callbacks)** Gatilhos de aviso que disparam ações automáticas de acordo com o desfecho das execuções.

- on_failure_callback: função que é disparada automaticamente quando a tarefa ou a rotina inteira falha, útil para enviar mensagens em canais de equipe.
    
- on_success_callback: função executada assim que a tarefa ou a rotina termina com sucesso, utilizada para confirmações e relatórios.

---
---

O Operator direciona a tecnologia que será utilizada para constuir a task

**1. Operadores de Ação** Executam comandos concretos ou disparam funções em ambientes específicos.

- PythonOperator: roda funções Python nativas no mesmo ambiente onde o Airflow está instalado.
    
- BashOperator: envia linhas de comando diretamente para o terminal do sistema operacional.
    
- EmailOperator: envia mensagens de correio eletrônico com relatórios ou avisos.
    

**2. Operadores de Transferência e Integração** Fazem a ponte entre dois sistemas ou acionam serviços externos em nuvem.

- PostgresOperator / MySqlOperator: autenticam e rodam consultas SQL diretamente em bancos de dados.
    
- S3FileTransformOperator / GCSToBigQueryOperator: pegam arquivos de um repositório em nuvem e enviam para outro destino sem carregar o dado pesado no Airflow.
    

**3. Sensores (Sensors)** Operadores passivos cuja única função é pausar o fluxo e ficar aguardando uma condição se tornar verdadeira.

- FileSensor: espera um arquivo específico surgir em uma pasta do disco.
    
- ExternalTaskSensor: aguarda uma tarefa de outra DAG diferente terminar antes de liberar o fluxo atual.
    

**4. Operadores de Controle de Fluxo** Gerenciam a rota e as condições das tarefas dentro do gráfico.

- BranchPythonOperator: avalia uma condição lógica e escolhe qual caminho seguir, pulando os outros ramos.
    
- EmptyOperator: não executa nada, servindo apenas como ponto de união visual ou início e fim de etapas complexas.

---
---

No Apache Airflow, cada tarefa executa em um processo isolado. Isso significa que duas tarefas nunca compartilham a mesma memória de execução, mesmo que estejam no mesmo computador.

Para que uma tarefa consiga enviar dados para outra, o sistema utiliza uma ponte de comunicação chamada XCom, uma abreviação para comunicação cruzada.

**O papel do XCom**

O XCom funciona como uma caixa postal central. Essa caixa fica guardada diretamente no banco de dados de metadados do Airflow, que é o local onde o sistema registra tudo o que acontece na plataforma.

O processo de envio e recebimento funciona em duas etapas muito diretas:

- Envio da informação: quando uma tarefa termina de processar, ela deposita um dado nessa caixa postal. Em tarefas normais de Python, qualquer valor devolvido no comando de retorno da função é gravado automaticamente nessa área de mensagens.
    
- Resgate da informação: quando a tarefa seguinte começa a rodar, ela faz uma busca nessa caixa postal informando o nome da tarefa de origem. O Airflow localiza o registro e entrega o conteúdo pronto para uso.
    

**A separação entre dados leves e dados pesados**

O banco de dados do Airflow foi feito para guardar configurações e estados de execução, não para armazenar grandes massas de informação. Por essa razão, a comunicação entre tarefas segue duas regras práticas fundamentais:

- Dados leves via XCom: números de contagem, datas de processamento, chaves de identificação, textos curtos e respostas de validação lógica devem viajar pelo XCom. Essas informações ocupam quase nada de espaço e não deixam o sistema lento.
    
- Dados volumosos via armazenamento externo: tabelas inteiras, arquivos compactados ou grandes relatórios nunca devem ser jogados no XCom. Fazer isso sobrecarrega o banco de metadados e pode paralisar o agendador de tarefas.
    

**Como transferir grandes volumes na prática**

Quando uma tarefa gera um volume alto de dados que precisa ser lido pela etapa seguinte, adota-se o padrão de armazenamento intermediário:

1. A primeira tarefa processa as informações e salva o arquivo completo em um local compartilhado, como uma pasta do disco local ou um serviço de armazenamento na nuvem.
    
2. A primeira tarefa envia pelo XCom apenas o caminho do arquivo, que é um texto curto com o endereço onde o material foi gravado.
    
3. A segunda tarefa busca esse endereço pelo XCom, abre o arquivo diretamente do local indicado e continua o trabalho.
    

Dessa forma, o Airflow cumpre o seu papel de orquestrador cuidando apenas dos avisos e das ordens de execução, enquanto as tarefas trocam o peso real dos dados por fora do banco central.

```python
from datetime import datetime, timedelta
from airflow import DAG
from airflow.operators.python import PythonOperator
import pandas as pd
import os

CAMINHO_ARQUIVO_TEMPORARIO = "/tmp/dados_processados.csv"


def extrair_e_salvar_dados():
    dados = {
        "produto": ["Notebook", "Mouse", "Teclado"],
        "preco": [3500, 150, 200],
    }
    df = pd.DataFrame(dados)
    df.to_csv(CAMINHO_ARQUIVO_TEMPORARIO, index=False)

    # O retorno vira automaticamente um XCom com o caminho do arquivo
    return CAMINHO_ARQUIVO_TEMPORARIO


def calcular_total(ti):
    # Puxa o caminho do arquivo gerado pela tarefa anterior via XCom
    caminho_recebido = ti.xcom_pull(task_ids="tarefa_extracao")

    df = pd.read_csv(caminho_recebido)
    valor_total = float(df["preco"].sum())

    # Retorna o valor calculado (dado leve) para outro XCom
    return valor_total


def exibir_relatorio(ti):
    # Puxa o valor numérico calculado na tarefa anterior
    total = ti.xcom_pull(task_ids="tarefa_calculo")
    print(f"Relatorio concluido. O valor total calculado foi: R$ {total}")

    # Remove o arquivo temporário do disco após o uso
    if os.path.exists(CAMINHO_ARQUIVO_TEMPORARIO):
        os.remove(CAMINHO_ARQUIVO_TEMPORARIO)


argumentos_padrao = {
    "retries": 1,
    "retry_delay": timedelta(minutes=2),
}

with DAG(
    dag_id="exemplo_comunicacao_tasks",
    default_args=argumentos_padrao,
    start_date=datetime(2026, 1, 1),
    schedule=None,
    catchup=False,
) as dag:

    tarefa_extracao = PythonOperator(
        task_id="tarefa_extracao",
        python_callable=extrair_e_salvar_dados,
    )

    tarefa_calculo = PythonOperator(
        task_id="tarefa_calculo",
        python_callable=calcular_total,
    )

    tarefa_relatorio = PythonOperator(
        task_id="tarefa_relatorio",
        python_callable=exibir_relatorio,
    )

    tarefa_extracao >> tarefa_calculo >> tarefa_relatorio
```

---
---

**1. Monitor e Alerta de Preços ou Câmbio**

- Ideia: coletar dados de uma API pública financeira (como a AwesomeAPI para cotações de moedas ou moedas digitais) de hora em hora.
    
- O que pratica: uso de PythonOperator com requisições HTTP, armazenamento do histórico em um arquivo local (CSV ou SQLite) e lógica de branching.
    
- Fluxo das tarefas:
    
    - Baixar a cotação atual.
        
    - Comparar a cotação com a média dos últimos dias via XCom.
        
    - Se o valor oscilar acima de uma porcentagem estipulada, acionar um ramo que envia uma notificação (pode ser via Telegram, Discord ou um simples BashOperator de log destacado); se a oscilação for normal, seguir para o ramo neutro.