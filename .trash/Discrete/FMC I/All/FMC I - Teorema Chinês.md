---
banner: "![[Pasted image 20251201181229.png]]"
---

---

````ad-quote
title:

##### **Intro ) -** Formalização do Teorema

```ad-quote
title:
<p align="justify">Método para resolver sistemas de congruências lineares, garantindo uma solução única dentro do módulo global, desde que os módulos sejam PRIMOS ENTRE SI dois a dois.</p>
```

```ad-quote
title:
Identidade:

- $$\text{mdc}(m_i, m_j) = 1, \forall i \neq j$$
```

```ad-quote
title:
###### Fórmula Geral
```

```ad-quote
title:
Algoritmo Construtivo (Soma Ponderada)
```

```ad-quote
title:

Definição do Sistema:

1. $$\begin{cases} x \equiv a_1 \pmod{m_1} \\ x \equiv a_2 \pmod{m_2} \\ \vdots \\ x \equiv a_k \pmod{m_k} \end{cases}$$

Calcular Variáveis Auxiliares:

- Módulo Global ($M$):

2. $$M = m_1 \cdot m_2 \cdot \dots \cdot m_k$$

- Módulos Parciais ($M_i$):

3. $$M_i = \frac{M}{m_i}$$

- Inversos Modulares ($y_i$) - Deve-se encontrar $y_i$ tal que:

4. $$M_i \cdot y_i \equiv 1 \pmod{m_i}$$

Realizar o cálculo final - Soma Ponderada:

5. $$x = \sum_{i=1}^{k} (a_i \cdot M_i \cdot y_i) = \text{Resultado}$$

Solução Geral - Normalização:

6. $$x \equiv \text{Resultado} \pmod M$$

```
````

---

```ad-done
title:

##### **Fase 02 ) -** Resolução de Exercícios

```

---

````ad-quote
title:

##### **02 )** - Exemplo de Resolução

```ad-quote
title:
<p align="justify">Vamos resolver um sistema de congruências lineares utilizando o Teorema Chinês do Resto. O objetivo é encontrar o menor número inteiro positivo x que satisfaça simultaneamente as três condições abaixo.</p>
```

```ad-quote
title:
###### O Sistema Proposto
```

```ad-quote
title:
1. $$x \equiv 1 \pmod 3$$
2. $$x \equiv 2 \pmod 4$$
3. $$x \equiv 3 \pmod 5$$
```
````

> [!done] **_New_**

````ad-quote
title:

##### **A** - Verificação de Existência - Condição de Coprimalidade

```ad-quote
title:
<p align="justify">Para garantir uma solução única módulo M, os divisores (módulos) devem ser primos entre si par a par. Verifica-se o Máximo Divisor Comum (MDC) entre as combinações dos módulos 3, 4 e 5.</p>
```

```ad-quote
title:
###### Análise
- $\text{mdc}(3, 4) = 1$ (Verdadeiro)
- $\text{mdc}(3, 5) = 1$ (Verdadeiro)
- $\text{mdc}(4, 5) = 1$ (Verdadeiro)
```

```ad-quote
title:
<p align="justify">Conclusão: A condição é satisfeita. O sistema possui solução.</p>
```
````

> [!done] **_New_**

````ad-quote
title:

##### **B** - Cálculo dos Módulos Parciais

```ad-quote
title:
<p align="justify">Nesta etapa, calculamos o Módulão (produto total) e os pesos de cada equação (Módulos Parciais).</p>
```

```ad-quote
title:
###### Produto Total (M)
```
```ad-quote
title:
$$M = 3 \times 4 \times 5 = 60$$
```

```ad-quote
title:
###### Os Módulos Parciais ($M_i$)
```
```ad-quote
title:
Para a linha 1 ($m=3$):
$$M_1 = \frac{60}{3} = 20$$
```
```ad-quote
title:
Para a linha 2 ($m=4$):
$$M_2 = \frac{60}{4} = 15$$
```
```ad-quote
title:
Para a linha 3 ($m=5$):
$$M_3 = \frac{60}{5} = 12$$
```
````

> [!done] **_New_**

````ad-quote
title:

##### **C** - O Cálculo dos Inversos Modulares ($y_i$)

```ad-quote
title:
Esta é a etapa crítica. Devemos encontrar o inverso multiplicativo de cada Módulo Parcial em relação ao seu módulo original. Resolvemos a equação: $M_i \cdot y_i \equiv 1 \pmod{m_i}$.
```

```ad-quote
title:
###### Inverso 1 - Referente ao módulo 3
```
```ad-quote
title:
Equação:
$$20 \cdot y_1 \equiv 1 \pmod 3$$

Simplificação (20 dividido por 3 deixa resto 2):
$$2 \cdot y_1 \equiv 1 \pmod 3$$

Resolução:
Testando múltiplos de 3 somados a 1: (1+3)=4.
$$4 \div 2 = 2$$
$$y_1 = 2$$
```

```ad-quote
title:
###### Inverso 2 - Referente ao módulo 4
```
```ad-quote
title:
Equação:
$$15 \cdot y_2 \equiv 1 \pmod 4$$

Simplificação (15 dividido por 4 deixa resto 3):
$$3 \cdot y_2 \equiv 1 \pmod 4$$

Resolução:
Testando múltiplos de 4 somados a 1: (1+4)=5 (não); (1+8)=9.
$$9 \div 3 = 3$$
$$y_2 = 3$$
```

```ad-quote
title:
###### Inverso 3 - Referente ao módulo 5
```
```ad-quote
title:
Equação:
$$12 \cdot y_3 \equiv 1 \pmod 5$$

Simplificação (12 dividido por 5 deixa resto 2):
$$2 \cdot y_3 \equiv 1 \pmod 5$$

Resolução:
Testando múltiplos de 5 somados a 1: (1+5)=6.
$$6 \div 2 = 3$$
$$y_3 = 3$$
```
````

> [!done] **_New_**

````ad-quote
title:

##### **D )** - A Montagem da Solução (Soma Ponderada)

```ad-quote
title:
<p align="justify">Reunimos todos os componentes na fórmula do Teorema Chinês do Resto. A estrutura é: Soma de (Resto Original × Módulo Parcial × Inverso).</p>
```

```ad-quote
title:
###### Tabela de Componentes
```

| Linha | Resto ($a_i$) | Módulo Parcial ($M_i$) | Inverso ($y_i$) |
| :--- | :---: | :---: | :---: |
| **1** | 1 | 20 | 2 |
| **2** | 2 | 15 | 3 |
| **3** | 3 | 12 | 3 |

```ad-quote
title:
###### Cálculo da Soma Bruta
```

```ad-quote
title:
$$x = (1 \cdot 20 \cdot 2) + (2 \cdot 15 \cdot 3) + (3 \cdot 12 \cdot 3)$$
$$x = (40) + (90) + (108)$$
$$x = 238$$
```
````

> [!done] **_New_**

````ad-quote
title:

##### **E** - O Resultado Final

```ad-quote
title:
<p align="justify">O valor 238 é uma solução válida, mas buscamos a solução mínima canônica. Para isso, aplicamos a congruência módulo M (60).</p>
```

```ad-quote
title:
###### Redução Modular
```

```ad-quote
title:
$$x \equiv 238 \pmod{60}$$
```

```ad-quote
title:
Divisão Euclidiana:
$$238 = 60 \cdot 3 + 58$$
```

```ad-quote
title:
###### Solução
```

```ad-quote
title:
$$x \equiv 58 \pmod{60}$$
```

```ad-quote
title:
###### Prova Real
- $58 \div 3$ ? Resto 1 (Ok, pois $19 \cdot 3 + 1 = 58$)
- $58 \div 4$ ? Resto 2 (Ok, pois $14 \cdot 4 + 2 = 58$)
- $58 \div 5$ ? Resto 3 (Ok, pois $11 \cdot 5 + 3 = 58$)
```
````

---
