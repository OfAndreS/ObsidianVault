
---
#### **Básico Of Memory**

>[!quote] **Definição** 
>Um **byte** é composto por 8 bits e representa uma unidade básica de armazenamento.
>Processadores e sistemas operam em diferentes arquiteturas de bits ***8, 16, 32, 64 bits***
>- influenciando a quantidade de dados que podem ser processados ou endereçados de uma só vez.
##### *O que é um **Bit**?*

>[!quote] **Definição**
> Um **bit** (abreviação de **"binary digit"** ou dígito binário) é a menor unidade de dados em um computador. Ele pode assumir um de dois valores: **0** ou **1**. 
>- Os bits são os blocos de construção fundamentais da computação, e todas as operações e dados no computador são representados por combinações de bits.

>[!quote] **Definição**
> No sistema binário, esses dois valores representam dois estados, que podem ser interpretados de várias formas, como:
>- **0** = Desligado, Falso, Não
>- **1** = Ligado, Verdadeiro, Sim 
##### *O que é um **Byte**?*

>[!quote] **Definição**
>Um **byte** é um conjunto de **8 bits**. 
>
>

>[!quote] **Definição**
>Ele é usado para representar um único caractere (como uma letra, número ou símbolo) em muitos sistemas de codificação, como o **ASCII**. 
>- A razão de usar 8 bits para formar um byte está relacionada à capacidade de armazenar **256 combinações diferentes** (2^8 = 256), o que é suficiente para representar um grande número de caracteres e outros tipos de dados.
##### *Significado de*  ***8, 16, 32 e 64 Bits***

>[!quote] **Definição**
>Esses números referem-se à quantidade de bits que um processador, sistema operacional ou outra tecnologia pode processar simultaneamente ou que uma unidade de dados 

>[!quote] **8 bits**
>**8 bits**: É o tamanho de um byte. Com 8 bits, você pode representar **256 valores diferentes** 
>- (0 a 255 no sistema decimal).

>[!quote] **16 bits**
>**16 bits**: Pode representar **65.536 valores diferentes** (2^16). 
>- Muitas máquinas antigas de 16 bits trabalhavam com unidades de 2 bytes.

>[!quote] **32 bits**
>**32 bits**: Pode representar **4.294.967.296 valores** (2^32). 
>- A arquitetura de computadores de 32 bits foi muito usada nos anos 1990 e 2000. Ela permite que os computadores enderecem até 4 GB de memória.

>[!quote] **64 bits**
>**64 bits**: Pode representar um valor extremamente grande, **18,4 quintilhões de valores** (2^64). 
>  - A arquitetura de 64 bits permite acesso a uma quantidade massiva de memória e é o padrão atual em computadores modernos.

---
#### **Ponto flutuante**

>[!quote] **Definição**
>O **ponto flutuante** é uma forma de representar números reais (que possuem parte fracionária, como 3.14 ou -0.001) em computadores. A aritmética de ponto flutuante permite a representação de números muito grandes ou muito pequenos ao usar uma aproximação.

>[!quote] **Em ponto flutuante, um número é geralmente representado na forma**
>
>$$N=\mathrm{sign}\times mantissa\times2^\text{exponent}$$
>
>- **Sign (sinal)**: Representa se o número é positivo ou negativo.
>- **Mantissa**: É a parte significativa do número.
>- **Exponent (expoente)**: Define a magnitude, ou a posição da "vírgula".

>[!quote] **Como funciona o ponto flutuante?**
>Os números em ponto flutuante são armazenados em três partes: o bit de sinal, o expoente, e a mantissa. Por exemplo, em um número de 32 bits no padrão IEEE 754 (usado para representar números **float**):
>- **1 bit para o sinal**: Se o bit é 0, o número é positivo; se for 1, o número é negativo.
>- **8 bits para o expoente**: Define a escala ou magnitude do número.
>- **23 bits para a mantissa**: A parte significativa do número.
>  
>Os números em ponto flutuante podem sofrer de **imprecisão** devido à forma como são armazenados. Como a quantidade de bits é limitada, nem todos os números podem ser representados exatamente, o que pode levar a **erros de arredondamento**.
##### *Tipo Float*

>[!quote] **Definição**
>**Float (32 bits)**
>
>- Ocupa 4 bytes de memória.
>- Possui precisão de cerca de 7 dígitos decimais.
>
>**No padrão IEEE 754, é dividido em:**
>- **1 bit** para o sinal 
>- **8 bits** para o expoente 
>- **23 bits** para a mantissa.
##### *Tipo Double*

>[!quote] **Definição**
>**Double (64 bits)**
>- Ocupa 8 bytes de memória.
>- Possui precisão de cerca de 15 dígitos decimais.
>  
>**No padrão IEEE 754, é dividido em:**
>- **1 bit** para o sinal.
>- **11 bits** para o expoente.
>- **52 bits** para a mantissa.
##### *Diferença entre*  **Float** e **Double**

 >[!quote] **Definição**
 >**Float** 
 >- Utiliza 32 bits, tem menor precisão e é mais rápido em cálculos.
 >  
 >**Double** 
 >- Utiliza 64 bits, tem maior precisão e é mais adequado para cálculos científicos que exigem alta exatidão.
 
>[!error] **Exemplo**
>**Armazenamento de um número "1.5" em float**
>- Mantissa: 1.1 (em binário, 1.5 é 1 + 0.5 = 1.11.1 1.1)
>- Expoente: 0 (pois não precisa mudar a posição da vírgula)
>- Sinal: 0 (número positivo)
>  
>**Problemas com precisão**
>A representação de números como $\frac{1}{3}=(0.3333...)$ não pode ser exata em ponto flutuante, o que causa pequenos erros de arredondamento.  

---
