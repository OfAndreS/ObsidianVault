
---

````ad-quote
title:
##### 01 ) - Fórmula recursiva

```ad-quote
title:
<p align="justify">Para construir essa lógica passo a passo, vamos adotar a sequência 5, 13, 29, 61, 125 como o nosso objeto de estudo. Usaremos esse mesmo conjunto de números para testar cada uma das etapas do nosso método de investigação estruturada.</p>
```
````

````ad-quote
title:

##### 1.1 ) - _Definindo elementos_
````

````ad-quote
title:

```ad-quote
title:
###### A ) *Definindo $a_1$*
```

```ad-quote
title:
O caso base $a_1$ sempre será o primeiro elemento de uma sequência. Logo, para o exemplo acima
```

```ad-quote
title:
- $$a_1 = 5$$
```
````

````ad-quote
title:
```ad-quote
title:
###### B ) *Definindo o para n >= k*
```

```ad-quote
title:
A lógica recursiva exige olhar para o termo anterior. Como o nosso $a_1$ já está dado e não possui um antecessor, a regra de formação algébrica não consegue calculá-lo, sendo útil exclusivamente para processar do segundo termo em diante (como o 13, o 29, etc.). Por isso, você deve sempre restringir a validade da sua fórmula para evitar um erro de domínio, anotando obrigatoriamente a condição $n \ge 2$.
```
````

````ad-quote
title:

##### 1.2 ) - _Estratégias de resolução_
````

````ad-quote
title:

```ad-quote
title:
###### A ) *Estratégia da subtração*
```

```ad-quote
title:
Para testar uma progressão aritmética, nós subtraímos o termo anterior do termo atual na nossa sequência de teste
```

```ad-quote
title:
- $13 - 5 = 8$
- $29 - 13 = 16$
```

```ad-quote
title:
Como o resultado não se manteve constante, a estratégia da subtração falhou. Com isso, sabemos com exatidão que a regra de formação não obedece ao formato elementar.
```

```ad-quote
title:
- $$a_n = a_{n-1} + d$$
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Estratégia da divisão*
```

```ad-quote
title:
Para testar uma progressão geométrica, nós dividimos o termo atual pelo seu antecessor na nossa sequência de teste.
```

```ad-quote
title:
- $13 / 5 = 2.6$
- $29 / 13 \approx 2.23$
```

```ad-quote
title:
Como o resultado não se manteve constante, a estratégia da divisão falhou. Com isso, sabemos com exatidão que a regra de formação não obedece ao formato puramente multiplicativo.
```

```ad-quote
title:
- $$a_n = a_{n-1} \cdot r$$
```
````

````ad-quote
title:

```ad-quote
title:
###### C ) *Padrão composto*
```

```ad-quote
title:
Quando as duas abordagens isoladas falham, estamos diante de um padrão composto. A forma composta exige multiplicar o termo anterior por uma constante e, logo em seguida, somar um resíduo fixo. O esquema algébrico dessa relação assume a forma 
```

```ad-quote
title:
- $$a_n = c \cdot a_{n-1} + k$$
```

```ad-quote
title:
<span style="opacity: 0.5;">*Para descobrir as variáveis, nós injetamos os primeiros números do nosso exemplo nesse esqueleto para montar um sistema*<span>

- $13 = c \cdot 5 + k$
    
- $29 = c \cdot 13 + k$
    

<span style="opacity: 0.5;">*Subtraindo a primeira equação da segunda, anulamos o resíduo $k$*<span>

- $29 - 13 = (13c + k) - (5c + k)$
    
- $16 = 8c$
    
- $c = 2$
    

<span style="opacity: 0.5;">*Sabendo que o multiplicador é 2, voltamos à primeira equação para isolar o resíduo e descobrir a taxa de adição:*<span>

- $13 = 2 \cdot 5 + k$
    
- $13 = 10 + k$
    
- $k = 3$

```
````

````ad-quote
title:

###### C ) *Formato ideal de resposta*

```ad-quote
title:
- $$a_1 = 5$$

- $$a_n = (a_{n-1} \cdot 2) + 3, \text{ para } n \ge 2$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **Progressão Aritmética - PA**

```ad-quote
title:
$$a_n = a_{n-1} + c$$
```
```ad-quote
title:
$$a_n = a_1 + (n-1)c$$
```
```ad-quote
title:
- $a_n$ - Enésimo termo.
- $a_{n-1}$ - Termo anterior.
- $a_1$ - Primeiro termo.
- $n$ - Posição.
- $c$ - Constante. É a constante aditiva.
```
````

````ad-quote
title:
##### **Progressão Geométrica - PG**

```ad-quote
title:
$$a_n = a_{n-1} \cdot q$$
```
```ad-quote
title:
$$a_n = a_1 \cdot q^{n-1}$$
```
```ad-quote
title:
- $a_n$ - Enésimo termo.
- $a_{n-1}$ - Termo anterior.
- $a_1$ - Primeiro termo.
- $n$ - Posição do termo.
- $q$ - Razão. É a constante multiplicativa, o fator fixo pelo qual você multiplica cada termo para chegar ao próximo.
```
````

````ad-quote
title:
##### **Composta**

```ad-quote
title:
$$a_n = a_{n-1} \cdot q + c$$
```
```ad-quote
title:
$$a_n = a_1 \cdot q^{n-1} + c \cdot \frac{q^{n-1} - 1}{q - 1}$$
```
```ad-quote
title:
- $a_n$ - Enésimo termo.
- $a_{n-1}$ - Termo anterior.
- $a_1$- Primeiro termo.
- $n$ - Posição do termo.
- $q$ - Fator multiplicativo.
- $c$ - Constante aditiva. 
```
````

---
---

- _Passo Base_: 
Substituir $n$ por 1 na fórmula fechada e verificar se o resultado algébrico bate perfeitamente com a condição inicial $a_1$ da regra recursiva.

- _Hipótese de Indução (HI)_: 
Assumir provisoriamente que a fórmula fechada é verdadeira para uma posição genérica $k$. Reescrever a equação trocando a variável $n$ por $k$.

- _Passo Indutivo_: 
Iniciar escrevendo a regra recursiva para o termo $k+1$. Substituir o elemento $a_k$ dessa regra pela equação declarada na hipótese de indução. Manipular a álgebra até o resultado espelhar o formato exato da fórmula fechada para a posição $k+1$.

---
---

Vamos provar a validade da fórmula fechada da Sequência A que você resolveu anteriormente.

- _Relação Recursiva_: $a_1 = 7$ e $a_n = a_{n-1} + 4$.

- _Fórmula Fechada_: $a_n = 4n + 3$.

**Teorema:** Provar por indução que $a_n = 4n + 3$ para todo $n \ge 1$.

_Passo Base_: Para $n=1$.

Substituindo na fórmula fechada: $a_1 = 4(1) + 3 = 7$.

Como a definição recursiva exige que $a_1 = 7$, o passo base é verdadeiro.

_Hipótese de Indução_:

Suponha que a fórmula seja válida para algum inteiro $k \ge 1$.

$$a_k = 4k + 3$$

_Passo Indutivo_:

Para o passo indutivo, expandimos o termo $a_{k + 1}$ via recorrência.

$$a_{k+1} = a_k + 4$$

Substituímos o termo $a_k$ pela nossa _Hipótese de Indução_:

$$a_{k+1} = (4k + 3) + 4$$
$$a_{k+1} = 4k + 7$$
$$a_{k+1} = 4k + 4 + 3$$
$$a_{k+1} = 4(k+1) + 3$$

Como o resultado espelha exatamente a estrutura da fórmula fechada para a posição $k+1$, a demonstração está concluída. A proposição é verdadeira para todo $n \ge 1$.

### **Formato Ideal de Resposta**

A sua entrega técnica para uma prova de indução deve isolar visualmente cada uma das três etapas estruturais, apresentando as deduções linha por linha sem omitir os passos algébricos intermediários. O esqueleto lógico será:

1. _Passo Base_: (Demonstração do cálculo para $n=1$)
    
2. _Hipótese de Indução_: (Declaração da equação para $n=k$)
    
3. _Passo Indutivo_: (Dedução partindo da regra recursiva, passando pela substituição da hipótese, até o alcance do formato para $k+1$)
    

Você está pronto para redigir a demonstração formal por indução para a Sequência D, cuja fórmula fechada era $a_n = 5 \cdot 4^{n-1}$, seguindo esta exata arquitetura para que eu avalie o seu rigor sintático e encadeamento lógico?

---
---