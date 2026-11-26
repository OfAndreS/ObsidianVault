
---
#### **1 ) Atribuição de um PID (Process Identifier)**

```ad-quote
title: **Def**

- Cada processo recebe um **identificador único (PID)**.
    
- O SO mantém uma **tabela de processos** (ex.: `task_struct` no Linux) com:
    
    - `PID` → Número único.
        
    - `PPID` → PID do processo pai.
        
    - `UID/GID` → Dono do processo.
        
    - `Estado` → _Running_, _Ready_, _Blocked_, etc.
```
###### 📌 **Exemplo (Linux):**

```bash
ps -aux | grep firefox  # Mostra PID, estado e recursos do Firefox.
```

---
#### **2 ) Carregamento do Programa na Memória**

```ad-quote
title: **Def**

O SO precisa mapear o executável do disco para a memória RAM:

- **Formato do executável** (ex.: ELF no Linux, PE no Windows) define a estrutura.
    
- **Seções carregadas:**
    
    - `.text` → Código do programa (instruções).
        
    - `.data` → Variáveis globais inicializadas.
        
    - `.bss` → Variáveis globais não inicializadas.
        
    - `Heap` → Alocação dinâmica (`malloc`, `new`).
        
    - `Stack` → Chamadas de função e variáveis locais.
```
###### 📌 **Exemplo (Linux):**

```bash
readelf -a /bin/ls  # Exibe a estrutura ELF do executável "ls".
```

---
#### **3 ) Alocação de Recursos**

```ad-quote
title: **Def**

**Memória**
- Divide em páginas (4KB no x86) e gerencia via MMU (Memory Management Unit).
  
**Registradores**
- Define valores iniciais (PC = entry point, SP = topo da stack).
  
**Arquivos**
- Mantém uma tabela de descritores (stdin, stdout, stderr, arquivos abertos).
  
**Dispositivos**
- Aloca acesso controlado a hardware (GPU, rede, etc.).
```
###### 📌 **Exemplo (Linux):**

```bash
pmap <PID>  # Mostra o mapa de memória do processo.
```

---
#### **4 ) Inicialização da Execução**

```ad-quote
title: **Def**

O SO configura o ambiente de execução:

**Define o Program Counter (PC)** 
- → Aponta para a primeira instrução (`_start` → `main`).

**Ajusta a Stack Pointer (SP)** 
- → Pilha vazia no início.

**Modo de Execução** 
- → Processos rodam em **user mode** (restrito), enquanto o SO opera em **kernel mode**.
```
###### 📌 **Exemplo (GDB):**

```bash
gdb ./programa
break main  # Pausa no início do programa.
info registers  # Mostra registradores (PC, SP, etc.).
```

---
#### **5 ) Gerenciamento Durante a Execução**

```ad-quote
title: **Def**

O SO monitora e controla o processo:

- **Escalonamento (Scheduling)**
    
    - Alterna entre estados:
        
        - **Running** (executando na CPU).
            
        - **Ready** (aguardando vez).
            
        - **Blocked** (esperando E/S).
            
    - Usa políticas como **Round-Robin**, **Prioridades**, etc.

---
   
- **Chamadas de Sistema (Syscalls)**
    
    - Quando o processo precisa de um recurso (ex.: `read()`, `write()`), faz uma **syscall** (troca para modo kernel).
```
###### 📌 **Exemplo (Linux):**

```bash
strace ./programa  # Mostra todas as syscalls usadas.
```

---
#### **6 ) Término do Processo**

```ad-quote
title: **Def**

Quando um processo termina (`exit()` ou sinal `SIGKILL`), o SO:

1. **Libera recursos**: Memória, descritores de arquivo, locks.
    
2. **Notifica o processo pai** → `SIGCHLD` no Linux.
    
3. **Remove da tabela de processos**.
```
###### 📌 **Exemplo (Linux):**

```bash
kill -9 <PID>  # Envia SIGKILL, terminando o processo.
```

---
