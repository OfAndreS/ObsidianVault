---
banner: "![[Pasted image 20251201181229.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Guia Definitivo


```ad-quote
title:
###### A Analogia do Relógio - O Ciclo Modular
```

![[Pasted image 20251130163821.png]]

```ad-quote
title:
<p align="justify">Diferente da aritmética tradicional, que opera em uma reta numérica infinita, a aritmética modular opera em um círculo fechado. O diagrama ao lado representa o universo do <strong>Módulo 6</strong>.</p>
```

```ad-quote
title:
###### A ) O Universo Finito
```

```ad-quote
title:
No módulo $m=6$, existem apenas 6 posições possíveis para o "ponteiro": de <strong>0 a 5</strong>. Qualquer número inteiro, por maior que seja, cairá em uma dessas 6 casas dependendo do resto de sua divisão por 6.
```

```ad-quote
title:
###### B ) O Ponto de Reset
```

```ad-quote
title:
O círculo visualiza a regra fundamental: <strong>$5 + 1 \equiv 0$</strong>. Ao completar o ciclo (chegar no valor do módulo), o sistema "zera" e o processo recomeça. Não existe o número 6 no mostrador, pois $6 \equiv 0 \pmod 6$.
```

```ad-quote
title:
###### C ) As Classes de Equivalência
```

```ad-quote
title:
Cada número no relógio é um "representante" de uma família infinita. A posição <strong>"2"</strong>, por exemplo, é a casa onde moram o 2, o 8, o 14, o 20, e também o -4.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - A Anatomia da Equação

```ad-quote
title:
<p align="justify">Uma equação de congruência descreve uma relação cíclica entre números inteiros.</p>
```

```ad-quote
title:
###### A Estrutura Base
```

```ad-quote
title:
$$ax \equiv b \pmod m$$
```



```ad-quote
title:
###### Os Componentes
```

```ad-quote
title:
- a (Coeficiente): O número que multiplica a incógnita.
- x (Incógnita): O valor que se deseja descobrir.
- b (Resto Alvo): O ponto de chegada.
- m (Módulo): O tamanho do ciclo (divisor).
```

```ad-quote
title:
<p align="justify">"Eu preciso encontrar um número inteiro x tal que, se eu multiplicar ele por a, o resultado vai cair exatamente na mesma posição do relógio que o número b (considerando um relógio de tamanho m)."</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Lógica Estrutural das Congruências

```ad-quote
title:
<p align="justify">Entender a lógica por trás das resoluções diferencia quem apenas segue receitas de quem domina a matemática. Tudo em congruência linear gira em torno do conflito entre duas variáveis fundamentais:</p>
```

```ad-quote
title:
O tamanho do passo 

1. $$a$$
   
   
O tamanho do ciclo 

2. $$m$$
```
````

---

```ad-done
title:
##### **Fase 02 ) -** Cálculos de Congruência
```

---

````ad-quote
title:

##### **02 )** - As 3 Estruturas Básicas - Definidas pelo MDC

```ad-quote
title:
<p align="justify">A relação entre o passo e o ciclo define a solubilidade da equação.</p>
```

````

> [!done] **_New_**

````ad-quote
title:
```ad-quote
title:
###### **A - Solução Única**
```

```ad-quote
title:
<p align="justify">Ocorre quando o passo e o ciclo não possuem divisores em comum, resultando em um comportamento desincronizado.</p>
```

```ad-quote
title:
Identidade:
- $$mdc(a, m) = 1$$
```

```ad-quote
title:
###### Fórmula Geral
```

```ad-quote
title:
Truque da soma || Algoritmo de Euclides Estendido || Teorema de Fermat
```

```ad-quote
title:

Resolução padrão: 

1. $$ax \equiv b \pmod m$$

Trasnformar a equação para: 

2. $$\bar{a} \cdot a \equiv 1 \pmod m$$

Calcular 

3. $$\bar{a}$$

Realizar o cálculo final:

4. $$x \equiv \bar{a} \cdot b \pmod m$$

```
````

> [!done] **_New_**

````ad-quote
title:
```ad-quote
title:
###### **B - Múltiplas Soluções**
```

```ad-quote
title:
<p align="justify">Ocorre quando a redundância cíclica permite atingir o alvo múltiplas vezes dentro de uma volta.</p>
```

```ad-quote
title:
Identidade:

- $$mdc(a, m) = d > 1 \land d \mid b$$
```

```ad-quote
title:
###### Fórmula Geral
```

```ad-quote
title:
Algoritmo de Euclides Estendido Caminho Expandido
```

```ad-quote
title:

Resolução padrão:  

1. $$ax \equiv b \pmod m$$ 
  
Transformar a equação - Visando achar o coeficiente do MDC:  

2. $$a \cdot s \equiv d \pmod m$$ 
  
Calcular Variáveis Auxiliares: 

- Coeficiente de Bézout: 
  
3. $$s$$ 
  
- Fator de Escala: 
  
4. $$k = \frac{b}{d}$$  
  
- Passo: 
  
5. $$p = \frac{m}{d}$$
  
Realizar o cálculo final: 

6. $$x_0 = s \cdot k$$    
  
Montar o Conjunto Solução: 

7. $$S = \{x_0, x_0 + p, x_0 + 2p, \dots, x_0 + (d-1)p\}$$

```

````

> [!done] **_New_**

````ad-quote
title:
```ad-quote
title:
###### **C - Sem Solução**
```

```ad-quote
title:
<p align="justify">Ocorre quando há um divisor comum que atua como um filtro, impedindo o acesso a certos números.</p>
```

```ad-quote
title:
Identidade:
$$mdc(a, m) = d > 1 \land d \nmid b$$
```

```ad-quote
title:
###### A Lógica - O Porquê:
```

```ad-quote
title:
<p align="justify">Imagine um relógio de tamanho 12 onde m é igual a 12 e só é possível andar de 2 em 2 onde a é igual a 2. O MDC aqui é 2. Não importa quantos passos sejam dados, sempre se cairá em números pares. Se o alvo b for um número ímpar, é fisicamente impossível alcançá-lo. A equação só alcança múltiplos desse MDC.</p>
```
````

---

```ad-done
title:
##### **Fase 03 ) -** Otimizações
```

---

````ad-quote
title:

##### **03 )** - Variações de Apresentação

```ad-quote
title:
<p align="justify">Nestes casos, a estrutura matemática é saudável, mas a equação apresenta-se de forma não simplificada.</p>
```

```ad-quote
title:
###### O Caso dos Negativos
```

```ad-quote
title:
<p align="justify">O relógio modular é um círculo. Se você está no zero e anda 3 passos para trás, representado por -3, você para na mesma posição que se tivesse andado m subtraído de 3 passos para frente. Matematicamente, eles pertencem à mesma classe de equivalência.</p>
```

```ad-quote
title:
<p align="justify">Solução: Soma-se o módulo m ao número negativo até que ele se torne positivo.</p>

1. $$-2x \equiv -3 \pmod 5$$
   
Somando do lado Direito

2. $$-2x \equiv (-3 + 5) \pmod 5$$
3. $$-2x \equiv 2 \pmod 5$$
   
Somando do lado Esquerdo

4. $$(-2 + 5)x \equiv 2 \pmod 5$$
   
Resultado
   
5. $$3x \equiv 2 \pmod 5$$




```

```ad-quote
title:
###### O Caso dos Gigantes
```

```ad-quote
title:
<p align="justify">Em aritmética modular, apenas o resto importa. Um número como 100 em módulo 6 significa dar 16 voltas completas e andar mais 4 casas. As voltas completas são irrelevantes para a posição final.</p>
```

```ad-quote
title:
Solução:
<p align="justify">Substitui-se qualquer número maior que m pelo seu resto na divisão por m.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Resumo Visual e Operacional

```ad-quote
title:
<p align="justify">Síntese do comportamento do passo a em relação ao alvo b e ao ciclo.</p>
```

```ad-quote
title:
###### Cenário: MDC = 1
```
```ad-quote
title:
- Bastidores: O passo visita todas as casas.
- Ação: Acha Inverso e resolve.
```

```ad-quote
title:
###### Cenário: MDC > 1 - Não divide b
```
```ad-quote
title:
- Bastidores: O passo só pisa em alguns lugares; o alvo está num Buraco inacessível.
- Ação: Declara impossível.
```

```ad-quote
title:
###### Cenário: MDC > 1 - Divide b
```
```ad-quote
title:
- Bastidores: Ritmo repetitivo gera vários acertos.
- Ação: Simplifica dividindo tudo e expande.
```

```ad-quote
title:
###### Cenário: Negativos
```
```ad-quote
title:
- Bastidores: Andando para trás no círculo.
- Ação: Soma o módulo para andar para frente.
```

```ad-quote
title:
###### Cenário: Números Grandes
```
```ad-quote
title:
- Bastidores: Voltas inúteis no círculo.
- Ação: Pega só o resto e ignora as voltas.
```
````

---
### **1. A Afirmação (Statement)**

$$a \equiv b \pmod m$$

- **Sua definição:** "Qual é o número $a$ que dividido por $m$ dá resto $b$?" (Correto, mas incompleto).
    
- Tradução para Código: Isso é uma VERIFICAÇÃO BOOLEANA.
    
    É como um assert ou um if.
    
    Python
    
    ```
    if (a % m) == b:
        return True
    ```
    
    Você não está "procurando" nada, está apenas afirmando que os dois lados são equivalentes.

### **2. A Equação Linear (Equation)**

$$ax \equiv b \pmod m$$

- **Sua definição:** "Eu preciso encontrar um número inteiro $x$..." (PERFEITO).
    
- Tradução para Código: Isso é uma BUSCA (SOLVER).
    
    O $x$ está "preso" numa multiplicação. Você não sabe quem ele é. Você precisa de um algoritmo (como o Inverso Modular) para isolá-lo.
    
    Python
    
    ```
    # Precisamos descobrir x
    def solve_linear_congruence(a, b, m):
        # Lógica complexa aqui (inverso modular, etc)
        return x
    ```
