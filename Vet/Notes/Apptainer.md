
---

token:

https://npad.ufrn.br/tutorials/advanced/singularity/?h=singularity

https://ai.google.dev/gemma/docs/core?hl=pt-br

---

/mnt/beegfs/scratch/asgmoreira/gemma4-31b-weights

---
### A Mecânica do Apptainer

O Apptainer é um sistema de conteinerização desenhado estritamente para a arquitetura de computação de alto desempenho (_HPC_). O seu funcionamento difere de motores tradicionais como o Docker por não exigir um _daemon_ em segundo plano operando com privilégios de superusuário.

Ele adota uma arquitetura de segurança _rootless_. Quando o artefato é acionado, o processo interno herda exatamente a mesma identidade de usuário (_UID_) e permissões do ambiente host. Isso elimina riscos de escalonamento de privilégios em supercomputadores compartilhados. O isolamento das dependências, pacotes do sistema operacional nativo e bibliotecas dinâmicas ocorre em tempo de execução via _namespaces_ do kernel do Linux, garantindo a execução isolada do ambiente original.

### Estrutura de Diretórios Padrão

A organização a seguir reflete a separação obrigatória entre o código da infraestrutura (imagem), o código da aplicação (scripts) e os dados pesados em um pipeline de _HPC_.

Plaintext

```
projeto-hpc/
├── ambiente/
│   ├── build.def
│   └── runtime.sif
├── scripts/
│   ├── orquestrador.slurm
│   └── inferencia.py
├── dados_entrada/
│   └── pesos_modelo/
└── saidas/
    └── logs_execucao/
```

### Anatomia dos Arquivos

### O Arquivo .def (Definition File)

Este arquivo é o código-fonte declarativo da sua infraestrutura. Trata-se de um manifesto em texto plano que instrui o compilador sobre como construir o ambiente do zero. Ele contém diretivas de qual sistema base importar (ex: Ubuntu, Alpine), quais gerenciadores de pacote invocar no bloco _%post_ (ex: _apt_, _pip_) e quais variáveis de ambiente definir no bloco _%environment_. É a garantia técnica de que o ambiente é reprodutível em qualquer máquina.

### O Arquivo .sif (Singularity Image Format)

É o bloco monolítico gerado após a compilação do arquivo de definição. Este formato empacota o sistema de arquivos inteiro do container em um único arquivo binário comprimido e de leitura bloqueada (_read-only_). A imutabilidade do formato _.sif_ impede que falhas lógicas nos seus scripts corrompam as bibliotecas do sistema. É este artefato que transita entre o seu ambiente de desenvolvimento e o nó de processamento do supercomputador.

### O Formato Sandbox (Diretório)

Não representado na árvore acima por ser efêmero, o _sandbox_ é o modo de desenvolvimento do Apptainer. Em vez de gerar um arquivo binário fechado, o comando de _build_ descompacta o sistema em uma pasta comum. Sua única utilidade é permitir que você acesse o container interativamente com permissões de gravação para testar comandos temporários antes de selar o ambiente no arquivo definitivo.

### Diretórios de Bind Mount (Dados e Saídas)

As pastas `dados_entrada` e `saidas` na árvore acima não pertencem ao container. Injetar gigabytes de modelos diretamente no arquivo de imagem é uma falha estrutural gravíssima de arquitetura. O Apptainer utiliza _bind mounts_ dinâmicos para criar links simbólicos temporários que conectam o sistema de arquivos do supercomputador ao interior do arquivo _.sif_ no momento da execução. Isso permite que a rede neural consuma os pesos no disco e grave os resultados de volta na máquina host.

---

````ad-quote
title:
##### **01 ) -** Instalação

```ad-quote
title:

<p align="justify">Para instalaer o Apptainer é necessário desligar o ambiente conda e instalar todos os pacotes abaixo para um bom funcionamento.</p>

```

```bash
conda deactivate
sudo apt update && sudo apt install -y apptainer uidmap build-essential
```


````

````ad-quote
title:
##### **A ) -** Via PPA

```ad-quote
title:

<p align="justify">O PPA é um repositório hospedado no Launchpad, criado especificamente para distribuições baseadas em Ubuntu como o Zorin OS. Ele funciona como uma "extensão" da loja oficial de aplicativos.</p>

```

```bash
sudo add-apt-repository ppa:apptainer/ppa
sudo apt update
sudo apt install apptainer
```

````

````ad-quote
title:
##### **B ) -** Via github

```ad-quote
title:

Ao contrário dos repositórios oficiais, que dependem do ciclo de atualização da distribuição, o GitHub do Apptainer oferece acesso imediato às versões mais recentes. Basta acessar a página de [release](https://github.com/apptainer/apptainer/releases) do projeto, baixar o pacote .deb compatível com sua arquitetura e realizar a instalação manual.

```

```bash

sudo apt install ./apptainer_versao_selecionada_amd64.deb

```
````

````ad-quote
title:
##### **Verificação**

```ad-quote
title:
Por fim, basta executar o comando abaixo para realizar a verificação final
```

```bash
apptainer --version

apptainer exec docker://alpine cat /etc/os-release
```
````

---
### 1. Preparo do Apptainer e Containerização

**Passo 1: Configuração das Variáveis de Ambiente no Host**

Execute a sequência abaixo no terminal para impedir o travamento do sistema por falta de espaço em disco. O erro clássico no uso do Apptainer é permitir que o diretório _home_ (geralmente limitado em partições de cluster) receba gigabytes de cache de _build_. A correção é apontar as variáveis para um volume de armazenamento secundário amplo antes de iniciar:

```Bash
echo 'export APPTAINER_CACHEDIR=/caminho/para/disco/maior/cache' >> ~/.bashrc
echo 'export APPTAINER_TMPDIR=/caminho/para/disco/maior/tmp' >> ~/.bashrc
source ~/.bashrc
```

**Passo 2: Preparação do Arquivo de Definição**

Descobrir quais são os drivers da Nvidia

```bash
srun --partition=gpu-4-a100 --gres=gpu:1 --time=00:10:00 nvidia-smi > diagnostico_driver.txt
```

Você deve criar um arquivo de texto plano chamado `Singularity.def` no seu diretório de trabalho atual. A estrutura correta para que o container vLLM incorpore as dependências e elimine arquivos residuais de instalação é esta:

```txt
Bootstrap: docker
From: vllm/vllm-openai:v0.6.3.post1

%post
    apt-get update && apt-get install -y python3-pip
    pip install pandas numpy matplotlib tqdm
    
    apt-get clean
    rm -rf /var/lib/apt/lists/
```

**Passo 3: Compilação do Container (Build)**

Rode o comando de compilação no terminal do seu computador de desenvolvimento. O parâmetro `--fakeroot` corrige a limitação estrutural de usuários comuns, simulando permissões de administrador (_root_) estritamente dentro do ambiente de isolamento do container para viabilizar as instalações do _apt_ e do _pip_:

```Bash
apptainer build --fakeroot vllm-custom.sif Singularity.def
```

**Passo 4: Sequência de Validação de Recursos**

Execute esta bateria de comandos em lote no terminal do seu supercomputador para inspecionar o tamanho físico da imagem e testar a comunicação direta do Python com o hardware gráfico:

Teste no pc

```Bash
# Exibir tamanho final do arquivo binário imutável
ls -lh vllm-custom.sif

# Confirmar a instalação correta das bibliotecas extras
singularity exec vllm-custom.sif pip show pandas tqdm

# Validar se o PyTorch do container enxerga a placa de vídeo do servidor
singularity exec --nv vllm-custom.sif python3 -c "import torch; print(torch.cuda.is_available())"
```

Teste no super

```bash
srun --partition=gpu-4-a100 --gres=gpu:1 --time=00:05:00 singularity exec --nv vllm-custom.sif python3 -c "import torch; print('\n[SUCESSO] CUDA:', torch.cuda.is_available()); print('[SUCESSO] GPU:', torch.cuda.get_device_name(0)); t = torch.zeros(1).cuda(); print('[SUCESSO] Tensor alocado na VRAM.\n')"
```

**Passo 5: Execução Interativa com Mapeamento de Volumes**

Use o comando a seguir para instanciar o container localmente. A flag `--nv` injeta as chamadas de driver da GPU do _host_ para dentro da aplicação virtualizada, enquanto a instrução `--bind` monta a pasta física de armazenamento de dados na raiz interna do _.sif_, permitindo leitura e escrita direta sem violar a imutabilidade do container:

```Bash
apptainer run --nv --bind /home/andre/dados:/mnt/dados vllm-custom.sif
```

---
### 2. Autenticação e Download de Pesos (Hugging Face)

_Credenciais_

Gere o token do tipo _Read_ nas configurações do seu perfil no Hugging Face e registre-o no nó de login do cluster:

Bash

```bash
huggingface-cli login
```

_Download via Terminal (CLI)_

O download via CLI estabelece validação de arquivos por _hash check_. A desativação de links simbólicos é fundamental para evitar falhas de montagem no Apptainer.

Bash

```bash
hf download google/gemma-3-270m-it --local-dir ./gemma3-weights --local-dir-use-symlinks False
```

_Download em Background para Modelos Densos_

Para cargas massivas que ultrapassam o tempo limite da sessão ativa do usuário:

```bash
nohup huggingface-cli download google/gemma-2-27b-it --local-dir ./gemma27b-weights --local-dir-use-symlinks False > download.log 2>&1 &
```

### 3. Scripts de Orquestração SLURM

_Job 1: Download Automatizado_

```bash
#!/bin/bash
#SBATCH --job-name=dl_gemma4
#SBATCH --partition=intel-128         
#SBATCH --nodes=1
#SBATCH --ntasks=1
#SBATCH --cpus-per-task=4             
#SBATCH --mem=16G                     
#SBATCH --time=06:00:00               
#SBATCH --output=log_download_%j.txt  

echo "--- Iniciando o download do Gemma 4 31B ---"
date

# Ativação do ambiente conda no nó de processamento
source ~/miniconda3/etc/profile.d/conda.sh
conda activate nlp

# Injeção da credencial de autenticação
export HF_TOKEN="seu_token_aqui"

# Execução do download nativo via API Python
python -c "from huggingface_hub import snapshot_download; import os; snapshot_download(repo_id='google/gemma-4-31B-it-qat-w4a16-ct', local_dir='./gemma4-31b-weights', token=os.environ.get('HF_TOKEN'))"

echo "--- Download finalizado ---"
date
```

_Job 2: Execução de Inferência (A100)_

Rodando para o modelo com os pesos no diretório .

```bash
#!/bin/bash
#SBATCH --job-name=gemma3_a100
#SBATCH --partition=gpu-4-a100        
#SBATCH --gres=gpu:1                  
#SBATCH --nodes=1
#SBATCH --cpus-per-task=16            
#SBATCH --mem=100G                    
#SBATCH --time=00:30:00
#SBATCH --output=resultado_a100.log

module load singularity
module load compilers/nvidia/cuda/12.6

singularity exec --nv \
    --bind ./gemma3-weights:/mnt/modelo \
    vllm-custom.sif \
    python3 -u teste_h100.py
```

Rodando para o modelo com os pesos no Scratch

```bash
#!/bin/bash
#SBATCH --job-name=gemma-4-31b-qat
#SBATCH --partition=gpu-4-a100        
#SBATCH --gres=gpu:1
#SBATCH --nodes=1
#SBATCH --cpus-per-task=16            
#SBATCH --mem=100G                    
#SBATCH --time=04:00:00
#SBATCH --output=output.out
#SBATCH --error=error.err

module load singularity

export VLLM_LOGGING_LEVEL=ERROR
export SINGULARITYENV_VLLM_WORKER_MULTIPROC_METHOD=spawn

singularity exec --nv \
    --bind /scratch/global/asgmoreira/gemma4-31b-w4a16:/mnt/modelo \
    vllm-custom_ofc.sif \
    python3 -u test_gpu.py
```

### 4. Lógica de Inferência Python (vLLM)

Código a ser salvo como `teste_h100.py`.

```python
import os
import multiprocessing as mp

if __name__ == "__main__":
    try:
        mp.set_start_method('spawn', force=True)
    except RuntimeError:
        pass

    from vllm import LLM, SamplingParams

    MODEL_PATH = "/mnt/modelo"

    def main():
        print("--- Iniciando Script de Teste no HPC ---")
        
        if not os.path.exists(MODEL_PATH):
            print(f"ERRO: O diretório {MODEL_PATH} não foi encontrado.")
            return

        print(f"Carregando o modelo a partir de: {MODEL_PATH}...")
        
        try:
            llm = LLM(
                model=MODEL_PATH,
                dtype="bfloat16",
                quantization="compressed-tensors",
                trust_remote_code=True,
                disable_log_stats=True,
                max_model_len=8192,
                gpu_memory_utilization=0.90
            )
        except Exception as e:
            print(f"\n[FALHA] Erro ao inicializar o motor vLLM: {e}")
            return

        sampling_params = SamplingParams(
            temperature=0.0, 
            max_tokens=8192
        )

        messages = [
            {"role": "user", "content": "Generate 50 variables in credit context!"}
        ]
        print("\nEnviando requisição via Chat Template...")
        
        try:
            outputs = llm.chat(messages, sampling_params)
            for output in outputs:
                print("\n" + "="*50)
                print(f"RESPOSTA: {output.outputs[0].text.strip()}")
                print("="*50 + "\n")
        except Exception as e:
            print(f"Erro na geração: {e}")

        print("--- Teste Finalizado ---")

    main()
```
