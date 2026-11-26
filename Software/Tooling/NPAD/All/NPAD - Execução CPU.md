---
banner: "![[Pasted image 20251115123940.png]]"
---
---

````ad-quote
title:

##### **Intro )** - Execução 

```ad-quote
title:
<p align="justify"></p>
```

````

---

```ad-done
title:  

#### **Fase 1 ) - Ordem de Comandos**

```

---

````ad-quote
title:

```ad-quote
title:
###### A ) Conexão e Desconexão do Servidor
```

```bash
# Iniciando a conexão
ssh -p4422 asgmoreira@sc2.npad.ufrn.br  # Comando completo
ssh super-pc                            # Atalho de Teclado

# Desligando a conexão
exit                                    # Comando completo
Ctrl + D                                # Atalho de Teclado
```

````

````ad-quote
title:

```ad-quote
title:
######  B ) - Transferência de Arquivos - [[NPAD - Sincronização de Arquivos|{X}]]
```

```bash
# Comando para garantir que você está no local correto:
cd ~/Documents/Sync

# Enviando Arquivos:
rsync -avz -e "ssh -p 4422" --exclude-from=".rsync-ignore" . super-pc:~/Sync/

# Enviando Arquivos:
rsync -avP -e "ssh -p 4422" --exclude-from=".rsync-ignore" . super-pc:~/Sync/

# Baixando Arquivos
rsync -avz -e "ssh -p 4422" super-pc:~/Sync/ .
```

````

````ad-quote
title:

```ad-quote
title:
######  C ) - Pipeline de Execução 
```

```bash

# Cria os diretórios de output
mkdir -p results erros

# Criar ou executar o arquivo .sh 
nano sExecute.sh

# Submeta o job para a fila de execução
sbatch sExecute.sh

# Verifique o status dos seus jobs (opcional)
squeue -u asgmoreira

# 3. Analise os resultados após a conclusão do job
cat resultados/resultado_1.out
```

````

---

```ad-done
title:  

#### **Fase 2 ) - Requisitos**

```

---

````ad-quote
title:

##### **02 )** - Criação do Script de Submissão - Slurm - [[NPAD - Slurm|{X}]]


```bash
#!/bin/bash
#SBATCH --job-name=EmotionsPatterns # Nome do job para fácil identificação
#SBATCH --partition=amd-512 # Partição correta
#SBATCH --ntasks=1 # Número de tarefas
#SBATCH --cpus-per-task=4 # Aumentado para 4 CPUs
#SBATCH --mem=16G # Aumentado para 16GB de RAM (aumento significativo)
#SBATCH --time=0-01:00:00 # Aumentado para 1 hora

# Salvando Output
#SBATCH --output=results/r%j.out
#SBATCH --error=erros/e%j.err
  
#====================================================================#

echo "|  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  * |"
echo "|  Job iniciado em: $(date)                                    "
echo "|  Executando no no: $(hostname)                               "

# Navegue para o diretório do seu projeto
cd ~/Sync/YourDir

# Inicialize o Conda
source ~/miniconda3/etc/profile.d/conda.sh

# Ative o ambiente
conda activate YourEnv

# Execute o script Python
echo "|  Iniciando execucao do app.py...                             "
echo "|  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  * |"

python -m src.

echo "|  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  * |"
echo "|  Job finalizado em: $(date)                                  "
echo "|  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  * |"

```
````

---

