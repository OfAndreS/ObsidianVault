
---

>[!quote] **Def**
>Um **stream** (fluxo) é um canal ou conexão que permite a transferência de dados entre o programa e uma fonte/destino, como o teclado, um arquivo ou a tela.
>
>- **Entrada (Input)**: Fluxo que lê dados, como teclado ou arquivos.
>- **Saída (Output)**: Fluxo que escreve dados, como na tela ou em arquivos.

>[!quote] **How to use:** [C reading files 🔎](https://www.youtube.com/watch?v=Hzg3kCHJcxI)

---
#### **2. FILE**

>[!quote] **Def**
>`FILE` é uma estrutura definida na biblioteca `<stdio.h>` que armazena informações sobre um arquivo ou fluxo de dados. Ela é usada em operações de leitura, escrita e manipulação de arquivos.
>
>- **Declaração**: `FILE *arquivo;`
>- **Abertura**: Usa `fopen` para abrir arquivos.
>- **Fechamento**: Usa `fclose` para liberar recursos.
```C

FILE *arquivo = fopen("exemplo.txt", "r"); // Abrindo em modo leitura
if (arquivo != NULL) {
    // Operações no arquivo
    fclose(arquivo); // Fechar o arquivo
}

```

---
#### **3. stdin / stdout / stderr**

>[!quote] **Def**
>São **streams padrão** usados para entrada e saída de dados:
>
>**stdin** (entrada padrão): 
>- Normalmente o teclado.
>
>---
>
>**stdout** (saída padrão): 
>- Normalmente a tela.
>  
>---
>
>**stderr** (saída de erro): 
>- Exclusivo para mensagens de erro.
```C

printf("Isso vai para stdout\n");
fprintf(stderr, "Isso vai para stderr\n");

```

---
#### **4. getchar / putchar / gets / puts**

>[!quote] **Def**
>**getchar()**
>- Lê um único caractere da entrada padrão.
```C

char c = getchar();

```

---

>[!quote] **Def**
>**putchar()**
>- Imprime um único caractere na saída padrão.
```C

putchar('A');

```

---

>[!quote] **Def**
>**gets()**
>- Lê uma string da entrada padrão (não recomendada, pois pode causar problemas de segurança).
```C

char str[50];
gets(str);

```

---

>[!quote] **Def**
>**puts()**
>- Imprime uma string na saída padrão.
```C

puts("Olá, mundo!");

```

---
#### **5. Input / Output e Fechamento de Arquivo**

>[!quote] **Def**
>**Operações comuns:**
>
>
>
>- **Abrir**: `fopen("arquivo.txt", "modo");`
>  
>---
>
>- **Ler**: `fscanf`, `fgets`, etc.
>  
>---
>
>- **Escrever**: `fprintf`, `fputs`, etc.
>  
>---
>
>- **Fechar**: `fclose(arquivo);`
```C

FILE *file = fopen("dados.txt", "w");
if (file) {
    fprintf(file, "Escrevendo no arquivo\n");
    fclose(file);
}

```

---
#### **6. perror**

>[!quote] **Def**
>Exibe uma mensagem de erro baseada na última função de biblioteca que falhou, usando `errno`.
```C

FILE *file = fopen("inexistente.txt", "r");
if (!file) {
    perror("Erro ao abrir o arquivo");
}

```

---
#### **7. Files**

>[!quote] **Def**
>Arquivos são usados para armazenar dados de forma persistente.
>
>---
>
>**Modos de abertura:**
>- `r`: Leitura.
>- `w`: Escrita (apaga o conteúdo existente).
>- `a`: Anexar (escreve no final do arquivo).
>- `r+`, `w+`, `a+`: Combinações de leitura e escrita.

---
#### **8. Directories**

>[!quote] **Def**
>Manipulação de diretórios não é nativa em C, mas pode ser feita com bibliotecas específicas, como `<dirent.h>` no Linux.
```C

#include <dirent.h>
DIR *d = opendir(".");
struct dirent *dir;
if (d) {
    while ((dir = readdir(d)) != NULL) {
        printf("%s\n", dir->d_name);
    }
    closedir(d);
}

```

---
#### **9. Streams**

>[!quote] **Def**
>Streams são abstrações para entrada e saída de dados. Em C, estão associados às funções como `fscanf`, `fprintf`, `fgets`, e `fputs`.

---
#### **10. Buffers**

>[!quote] **Def**
>Buffers armazenam temporariamente dados para otimizar a transferência entre a memória e os dispositivos de entrada/saída.
>
>- **Buffer de linha**: Usa `\n` para esvaziar o buffer.
>- **Buffer não-bufferizado**: Ex.: `stderr` (os dados são enviados diretamente).
```C

setbuf(stdout, NULL); // Desativa o buffer de stdout

```

---

