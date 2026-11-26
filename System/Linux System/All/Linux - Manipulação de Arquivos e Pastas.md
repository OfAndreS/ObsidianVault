
---

````ad-quote
title: 

##### **01 ) -** Syntax - ls

```ad-quote
title: 

Lista o conteúdo do diretório
```

```shell
ls [options] [directory_or_path]

ls -la /var/log
```

```ad-quote
title: 

###### Common options
```

```ad-quote
title: 
- `-a` → show hidden files
- `-l` → use a long listing format
```
````

````ad-quote
title: 

##### **02 ) -** Syntax - pwd

```ad-quote
title: 

Verifica o caminho de um diretório
```

```shell
pwd [options]

pwd -P
```

```ad-quote
title: 

###### Common options
```

```ad-quote
title: 
- `-L` → print the logical current working directory
- `-P` → print the physical current working directory
```
````

````ad-quote
title: 

##### **03 ) -** Syntax - cd

```ad-quote
title: 

Muda de diretório
```

```shell
cd [directory]

cd /home/user/Documents
```

```ad-quote
title: 

###### Common options
```

```ad-quote
title: 
- `..` → move one directory up
- `-` → return to the previous directory
```
````

````ad-quote
title: 

##### **04 ) -** Syntax - locate

```ad-quote
title: 

Pesquisa por um arquivo e seu caminho
```

```shell
locate [options] pattern

locate -i filename.txt
```

```ad-quote
title: 

###### Common options
```

```ad-quote
title: 
- `-i` → ignore case distinctions
- `-c` → print only a count of matching entries
```
````

Snippet de código

````
title: 

##### **05 ) -** Syntax - find

```ad-quote
title: 

Encontra um arquivo dentro do diretório atual
```

```shell
find [path] [expression]

find . -name "*.txt"
```

```ad-quote
title: 

###### Common options
```

```ad-quote
title: 
- `-name` → base of file name matches pattern
- `-type f` → search only for regular files
```
````

---

O visual com as caixas unidas ficou muito bom para copiar e colar direto no _Obsidian_! Gostaria que eu preparasse mais alguns comandos do Zorin OS ou do _Linux_ em geral usando essa exata mesma estrutura para você adicionar às suas anotações?