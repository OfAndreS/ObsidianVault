
---

>[!quote] **Link:** [How to Fix Error: GCC/G++ No Such File Or Directory](https://www.youtube.com/watch?v=pcaByFmyP-s)

---
#### **1 ) Compilação Básica**

```ad-quote
title: **Def**

Para compilar um arquivo `.cpp` e gerar um executável:

- Substitua `arquivo.cpp` pelo nome do seu código-fonte.

- O argumento `-o` define o nome do executável (opcional; se omitido, o padrão é `a.out`).
```

```cpp
g++ arquivo.cpp -o nome_do_executavel
```
###### **Exemplo:**

```cpp
g++ main.cpp -o programa
```

---
#### **2 ) Executando o Programa**

```ad-quote
title: **Def**  

Após a compilação, execute o programa gerado:  

- Use `./` antes do nome do executável no Linux/Mac.  
```

```cpp
./nome_do_executavel  
```
###### **Exemplo:**

```cpp
./programa  
```

---
#### **3 ) Compilação com Avisos e Otimização**

```ad-quote
title: **Def**  

Habilite avisos e otimizações para melhor desempenho e detecção de erros:  

- `-Wall`: Ativa avisos comuns.  
- `-Wextra`: Avisos extras.  
- `-O2`: Otimização de velocidade (pode usar `-O1`, `-O3` ou `-Os`).   
```

```cpp
g++ -Wall -Wextra -O2 arquivo.cpp -o executavel  
```
###### **Exemplo:**

```cpp
g++ -Wall -Wextra -O2 main.cpp -o programa_otimizado  
```

---
#### **4 ) Especificando o Padrão do C++**

```ad-quote
title: **Def**  

Use flags como `-std=c++11`, `-std=c++17` ou `-std=c++20` para garantir compatibilidade:  

- Essencial para recursos modernos do C++.   
```

```cpp
g++ -std=c++17 arquivo.cpp -o executavel  
```
###### **Exemplo:**

```cpp
g++ -std=c++20 main.cpp -o programa_moderno    
```

---
#### **5 ) Compilação Separada (Projetos Grandes)**

```ad-quote
title: **Def**  

Para projetos com múltiplos arquivos, compile separadamente e depois linke:  

- `-c`: Gera arquivos objeto (`.o`) sem linkar.  
```

```cpp
g++ -c arquivo1.cpp        # Gera arquivo1.o  
g++ -c arquivo2.cpp        # Gera arquivo2.o  
g++ arquivo1.o arquivo2.o -o programa_final  
```
###### **Exemplo:**

```cpp
g++ -c utils.cpp  
g++ -c main.cpp  
g++ utils.o main.o -o app    
```

---
#### **6 ) Depuração com GDB**

```ad-quote
title: **Def**  

Compile com símbolos de depuração (`-g`) para usar o **GDB**:  

- Permite analisar erros com mais detalhes.  
```

```cpp
g++ -g arquivo.cpp -o programa_debug  
gdb ./programa_debug  
```
###### **Exemplo:**

```cpp
g++ -g main.cpp -o debug  
gdb ./debug    
```

---
#### **Exemplo Completo**

```ad-quote
title: **Def**  

Compilação com avisos, otimização e C++17:  

- Combina flags essenciais para um projeto bem configurado.
```

```cpp
g++ -Wall -Wextra -O2 -std=c++17 main.cpp -o meu_programa  
./meu_programa  
```

---