---
banner: "![[Pasted image 20251201181229.png]]"
---

---

````ad-quote
title:

#### **Intro) -** Script 

```ad-quote
title:

Eu quero aprender com você de forma interativa esse assunto:

```

````

---

```ad-done
title:
#### **Seção 4.4 ) -** Resolvendo Congruências 
```

---

````ad-quote
title:
##### **01 ) -** Congruências Lineares 

>[!done] 75%

```ad-quote
title:

- $$ax \equiv b \pmod m$$

``` 

```ad-quote
title:
**Definição:** 
```

```ad-quote
title:
Entender o que é uma congruência linear (uma variável na primeira potência).
```

```ad-quote
title:
**Condição de Solução:** 
```

```ad-quote
title:
Aprender a usar o MDC para saber se a equação tem solução.
```

```ad-quote
title:

|Regra|
|-|
|Tem solução se, e somente se, $d = \text{mdc}(a, m)$ divide $b$.|

|Número de Soluções|
|-|
|Se houver solução, existem exatamente $d$ soluções incongruentes módulo $m$.|
```

>[!quote] **Vault:** [[FMC I - Congruências Lineares]]

````

````ad-quote
title:
##### **02 ) -** O Inverso Modular

>[!done] 75%

```ad-quote
title:

- $$a\bar{a} \equiv 1 \pmod m$$

```

```ad-quote
title:
**Definição:**
```

```ad-quote
title:
O inverso de a módulo m é um inteiro $\bar{a}$ que satisfaz a congruência acima.
```

```ad-quote
title:
**Existência:**
```

```ad-quote
title:
|Regra|
|-|
|Só existe se $a$ e $m$ forem primos entre si (Coprimos).|
|Identidade: $\text{mdc}(a, m) = 1$.|
```

```ad-quote
title:
**Como Calcular:**
```

```ad-quote
title:
Aprender a usar o Algoritmo De Euclides Estendido (Coeficientes De Bézout) para encontrar esse inverso. Isso é essencial para resolver $ax \equiv b \pmod m$ multiplicando ambos os lados por $\bar{a}$.
```

>[!quote] **Vault:** [[FMC I - Inverso Modular]]

````

````ad-quote
title:
##### **03 ) -** Teorema Chinês Do Resto (CRT)

>[!done] 50%

```ad-quote
title:

- $$\begin{cases} x \equiv a_1 \pmod{m_1} \\ x \equiv a_2 \pmod{m_2} \\ \vdots \\ x \equiv a_k \pmod{m_k} \end{cases}$$

```

```ad-quote
title:
**O Problema:**
```

```ad-quote
title:
Resolver sistemas de congruências com módulos diferentes.
```

```ad-quote
title:
**Condições e Teorema:**
```

```ad-quote
title:
|Requisito|
|-|
|Os módulos ($m_1, m_2, \dots$) devem ser Primos Entre Si Dois A Dois.|

|Garantia|
|-|
|Existe uma Solução Única módulo $M = m_1 \times m_2 \times \dots \times m_n$.|
```

```ad-quote
title:
**Algoritmo de Resolução:**
```

```ad-quote
title:
Aprender a construção da solução usando a fórmula:
$$x = \sum a_i M_i y_i$$
Onde $M_i = M/m_i$ e $y_i$ é o inverso de $M_i$ módulo $m_i$.
```

>[!quote] **Vault:** [[FMC I - Teorema Chinês]]

````

````ad-quote
title:
##### **04 ) -** Pequeno Teorema De Fermat

>[!done] 75%

```ad-quote
title:

- $$a^{p-1} \equiv 1 \pmod p$$

```

```ad-quote
title:
**Condição:**
```

```ad-quote
title:
Se p é primo e p não divide a.
```

```ad-quote
title:
**Corolário:**
```

```ad-quote
title:
$$a^p \equiv a \pmod p$$
(Válido para qualquer inteiro a).
```

```ad-quote
title:
**Aplicações Práticas:**
```

```ad-quote
title:
|Uso|Descrição|
|-|---|
|Cálculo Rápido|Encontrar inversos modulares rapidamente (se o módulo for primo).|
|Simplificação|Reduzir potências grandes. Ex: calcular $7^{222} \pmod{11}$.|
```

>[!quote] **Vault:** [[FMC I - Teoremas de Fermat]]

````

````ad-quote
title:
##### **05 ) -** Pseudoprimos

>[!done] 0%

```ad-quote
title:
**Conceito:**
```

```ad-quote
title:
Entender que o inverso do Teorema De Fermat não é sempre verdadeiro. Existem números compostos que fingem ser primos, satisfazendo a congruência de Fermat mesmo sem serem primos.
```

>[!quote] **Vault:** [[FMC I - Primalidade]]

````

---

```ad-done
title:
### **Seção 4.5: Aplicações de Congruências**
```

---

````ad-quote
title:
##### **06 ) -** Funções Hash (Hashing)

>[!done] 0%

```ad-quote
title:

- $$h(k) = k \pmod m$$

```

```ad-quote
title:
**Objetivo:**
```

```ad-quote
title:
Mapear um universo grande de chaves $k$ (como CPFs ou Matrículas) para um conjunto pequeno de índices $m$ em uma tabela de memória. O foco é a EFICIÊNCIA na busca de dados ($O(1)$ no caso médio).
```

```ad-quote
title:
**Método da Divisão:**
```

```ad-quote
title:
É a aplicação direta da ARITMÉTICA MODULAR que você estudou.
A função de hash é definida pelo resto da divisão:
$$h(k) = k \bmod m$$
Onde $m$ é o tamanho da tabela hash.
```

```ad-quote
title:
**Colisões:**
```

```ad-quote
title:
|Definição|
|-|
|Ocorre quando duas chaves diferentes resultam no mesmo índice: $h(k_1) = h(k_2)$.|

|Consequência|
|-|
|Duas informações tentam ocupar o mesmo espaço na memória. Isso EXIGE tratamento (como Encadeamento ou Endereçamento Aberto).|
```

```ad-quote
title:
**A Importância do Módulo Primo:**
```

```ad-quote
title:
Para minimizar colisões, o tamanho da tabela ($m$) deve ser, preferencialmente, um NÚMERO PRIMO e não muito próximo de uma potência de 2.
Isso ajuda a DISTRIBUIR uniformemente as chaves, quebrando padrões aritméticos que possam existir nos dados de entrada.
```

>[!quote] **Vault:** [[FMC I - Hashing e Colisões]]
````

---
1. **Geradores de Números Pseudoaleatórios (PRNGs)**
    
    - **Método da Congruência Linear:** A fórmula padrão para gerar números aleatórios em computadores.
        
        - $x_{n+1} = (ax_n + c) \bmod m$
            
    - **Parâmetros:** Saber o papel da semente ($x_0$), multiplicador ($a$), incremento ($c$) e módulo ($m$).
        
    - **Conceito:** Entender que não são aleatórios de verdade, pois a sequência é previsível se você souber os parâmetros.
        
2. **Dígitos Verificadores (Check Digits)**
    
    - **Conceito:** Usar congruências para detectar erros de digitação.
        
    - **ISBN-10:** Usa módulo 11. A condição é $\sum_{i=1}^{10} i x_i \equiv 0 \pmod{11}$.
        
    - **UPC (Códigos de Barra):** Usa módulo 10 com pesos alternados (3 e 1).
        
    - **Tarefa:** Você deve saber verificar se um código é válido e encontrar um dígito faltando (o "check digit") fazendo a conta modular.
        

---

### **Seção 4.6: Criptografia**

A aplicação mais nobre da aritmética modular: proteger segredos.

1. **Cifras Clássicas (Criptografia Simétrica)**
    
    - **Cifra de Deslocamento (Shift Cipher / César):**
        
        - Cifrar: $C = (P + k) \bmod 26$.
            
        - Decifrar: $P = (C - k) \bmod 26$.
            
    - **Cifra Afim (Affine Cipher):**
        
        - Cifrar: $C = (aP + b) \bmod 26$.
            
        - Decifrar: $P = \bar{a}(C - b) \bmod 26$.
            
        - _Nota:_ Aqui você precisa verificar se $a$ tem inverso (mdc com 26 deve ser 1) e calcular esse inverso $\bar{a}$ para conseguir decifrar.
            
2. **Criptografia de Chave Pública (Assimétrica)**
    
    - **Conceito:** Entender a diferença entre ter uma chave para fechar (pública) e outra para abrir (privada). Isso elimina o problema de trocar chaves secretas.
        
3. **O Algoritmo RSA (O Grande Final)**
    
    - Você deve dominar todo o ciclo de vida do RSA:
        
        1. **Geração de Chaves:**
            
            - Escolher dois primos grandes $p$ e $q$.
                
            - Calcular o módulo $n = p \cdot q$.
                
            - Calcular a função totiente $\phi(n) = (p-1)(q-1)$.
                
            - Escolher um expoente $e$ coprimo com $\phi(n)$.
                
            - Calcular $d$ (o inverso de $e$ módulo $\phi(n)$).
                
        2. **Cifrar (Encryption):** $C = M^e \bmod n$.
            
        3. **Decifrar (Decryption):** $M = C^d \bmod n$.
            
    - **Segurança:** Entender que a segurança do RSA depende do fato de que fatorar $n$ para descobrir $p$ e $q$ é computacionalmente inviável para números grandes.
        

### **Resumo da "Caixa de Ferramentas" Necessária**

Para sobreviver a essas seções, certifique-se de que você sabe fazer estas 4 coisas mecanicamente:

1. Calcular **MDC** (Euclides).
    
2. Calcular **Inverso Modular** (Euclides Estendido ou Fermat).
    
3. Fazer **Exponenciação Modular** (calcular $a^b \bmod m$ eficientemente).
    
4. Resolver a equação $ax \equiv b \pmod m$.

---
Com base no livro _Discrete Mathematics and Its Applications_ (8ª edição), aqui está um log detalhado dos tipos de questões e tópicos abordados nos capítulos 4.4, 4.5 e 4.6.

### **Capítulo 4.4: Solving Congruences (Resolvendo Congruências)**

Este capítulo foca na matemática necessária para resolver equações que envolvem restos de divisões. Os tipos de questões cobradas incluem11:

- **Inversas Modulares:**
    
    - Encontrar o inverso de um número $a$ módulo $m$.
        
    - Uso do Algoritmo de Euclides Estendido para encontrar coeficientes de Bézout e inversas.
        
- **Congruências Lineares:**
    
    - Resolver equações do tipo $ax \equiv b \pmod m$.
        
    - Determinar se uma congruência linear tem solução e quantas soluções incongruentes existem.
        
- **Teorema Chinês do Resto (Chinese Remainder Theorem):**
    
    - Resolver sistemas de congruências lineares (ex: $x \equiv 2 \pmod 3$, $x \equiv 3 \pmod 5$, etc.).
        
    - Aplicações práticas envolvendo grandes números utilizando aritmética modular com módulos primos entre si.
        
    - Uso do método de "back substitution" (substituição regressiva) para resolver sistemas.
        
- **Pequeno Teorema de Fermat:**
    
    - Calcular restos de potências grandes (ex: $7^{222} \pmod{11}$) usando o teorema.
        
    - Demonstrar propriedades de divisibilidade usando o teorema.
        
- **Pseudoprimos e Números de Carmichael:**
    
    - Verificar se um número composto passa no teste de primalidade base $b$ (pseudoprimo).
        
    - Identificar números de Carmichael (compostos que se comportam como primos para todos os testes de Fermat).
        
- **Raízes Primitivas e Logaritmos Discretos:**
    
    - Verificar se um número é uma raiz primitiva de um primo $p$.
        
    - Calcular logaritmos discretos de um número base $r$ módulo $p$.
        

---

### **Capítulo 4.5: Applications of Congruences (Aplicações de Congruências)**

Este capítulo aplica a aritmética modular em problemas práticos de computação e identificação. As questões envolvem2222:

- **Funções de Hashing (Espelhamento):**
    
    - Calcular a localização de memória de um arquivo dado uma chave $k$ usando funções como $h(k) = k \pmod m$.
        
    - Resolver problemas de colisão (quando dois arquivos são designados para o mesmo local).
        
- **Números Pseudoaleatórios:**
    
    - Gerar sequências de números usando o método da congruência linear: $x_{n+1} = (ax_n + c) \pmod m$.
        
    - Questões sobre a previsão de números futuros na sequência ou propriedades da sequência gerada.
        
- **Dígitos Verificadores (Check Digits):**
    
    - Calcular dígitos de verificação para códigos como ISBN (livros) e UPC (produtos).
        
    - Verificar se um código dado é válido (ex: Validar um número de cartão de crédito ou ISBN).
        
    - Identificar tipos de erros que um código pode detectar (como erro em um único dígito ou transposição de dígitos adjacentes).
        

---

### **Capítulo 4.6: Cryptography (Criptografia)**

Este capítulo introduz métodos clássicos e modernos de criptografia. Os exercícios focam em3333:

- **Cifras Clássicas:**
    
    - **Cifra de César e Cifras de Deslocamento (Shift Ciphers):** Criptografar e descriptografar mensagens deslocando letras do alfabeto (ex: $f(p) = (p + k) \pmod{26}$).
        
    - **Cifras Afins (Affine Ciphers):** Usar funções lineares do tipo $f(p) = (ap + b) \pmod{26}$.
        
    - **Cifra de Vigenère:** Usar chaves compostas por strings para cifrar blocos de texto.
        
    - **Cifras de Transposição:** Reordenar letras baseando-se em permutações.
        
- **Criptoanálise:**
    
    - Quebrar códigos simples usando análise de frequência (ex: identificar que a letra mais comum no texto cifrado provavelmente corresponde à letra 'E').
        
- **Criptografia de Chave Pública (RSA):**
    
    - Criptografar mensagens numéricas usando chaves públicas $(n, e)$.
        
    - Descriptografar mensagens usando chaves privadas $d$ (onde $d$ é o inverso de $e$ módulo $(p-1)(q-1)$).
        
    - Entender a mecânica matemática por trás da segurança do RSA (fatoração de grandes primos).
        
- **Protocolos Criptográficos:**
    
    - Troca de chaves de Diffie-Hellman (computar chaves compartilhadas usando aritmética modular).
        
    - Assinaturas digitais (garantir autenticidade de mensagens).