
---

**1. Expandir, Conjecturar e Verificar** Esse também é chamado de método de substituição. Você precisa expandir a expressão original repetidas vezes até alcançar o caso base. Essa repetição visual ajuda a adivinhar o formato da solução final. Por fim você utiliza uma prova matemática por indução para verificar se o seu palpite inicial estava realmente correto.

**2. Árvore de Recorrência** Essa é a opção mais visual e intuitiva. O processo consiste em desenhar uma estrutura de árvore na qual os nós indicam o tamanho dos problemas em cada nível de profundidade. Para encontrar a complexidade de tempo total do algoritmo você deve somar todos os passos executados em todos os níveis dessa árvore.

---

```ad-done
title:
#### **Fase ... ) - ...**
```

---

````ad-quote
title:

##### **01 )** - Teorema Mestre

```ad-quote
title:
<p aling="justify">Esse método atua como uma receita prática para resolver equações que possuem um formato bem específico. A regra possui três cenários diferentes de aplicação. O teorema cobre grande parte dos problemas comuns e entrega a resposta de forma muito direta quando a equação obedece aos seus critérios.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Cenários_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Definição*
```

```ad-quote
title:
O método mestre resolve equações de recorrência com o formato matemático $T(n) = aT(n/b) + f(n)$. Nessa estrutura base os valores numéricos de $a$ e $b$ são constantes. A regra exige sempre que $a \ge 1$ e $b > 1$.
```
```ad-quote
title:
$$\begin{array}{\|l\|l\|l\|} \hline \text{Cenário} & \text{Condição (Se)} & \text{Resultado Final (Então)} \\ \hline \text{Caso 1} & f(n) < n^{\log_b a} & T(n) = \Theta(n^{\log_b a}) \\ \hline \text{Caso 2} & f(n) = n^{\log_b a} & T(n) = \Theta(n^{\log_b a} \log n) \\ \hline \text{Caso 3} & f(n) > n^{\log_b a} & T(n) = \Theta(f(n)) \\ \hline \end{array}$$
```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Caso 01_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Implicação*
```

```ad-quote
title:
- Se $f(n) = O(n^{\log_b a - \epsilon})$ para alguma constante $\epsilon > 0$, então $T(n) = \Theta(n^{\log_b a})$.
```
```ad-quote
title:
1. $$f(n) < n^{\log_b a}$$
2. $$T(n) = \Theta(n^{\log_b a})$$
```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.2 ) - _Caso 02_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Implicação*
```

```ad-quote
title:
- Se $f(n) = \Theta(n^{\log_b a})$, então $T(n) = \Theta(n^{\log_b a} \log n)$.
```
```ad-quote
title:
1. $$f(n) = n^{\log_b a}$$
2. $$T(n) = \Theta(n^{\log_b a} \log n)$$
```

````

> [!done] **_New_**

```ad-quote
title:

##### 1.3 ) - _Caso 03_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Implicação*
```

```ad-quote
title:
- Se $f(n) = \Omega(n^{\log_b a + \epsilon})$ para alguma constante $\epsilon > 0$ e a restrição extra for verdadeira, então $T(n) = \Theta(f(n))$. E $a f(n/b) \le c f(n)$ para alguma constante $c < 1$.
```
```ad-quote
title:
1. $$f(n) > n^{\log_b a}$$
2. $$T(n) = \Theta(f(n))$$
```

````


---
---

### **Caso 3**

```embed
title: "Aula 11 - Teorema Mestre (Parte 01)"
image: "https://i.ytimg.com/vi/XWAkJsN_MuY/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AHUBoAC4AOKAgwIABABGGQgZShUMA8=&rs=AOn4CLBJ4oW6Fcd9DL7Rdo0A9HxLAEAyTg"
description: "Aula 11 - Teorema Mestre (Parte 01)"
url: "https://www.youtube.com/watch?v=XWAkJsN_MuY"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "AULA 04 - Projeto e Análise de Algoritmos - Recursivos - Relação de Recorrência - Teorema Mestre"
image: "https://i.ytimg.com/vi/DdNCO6A-JjI/maxresdefault.jpg"
description: "Disciplina: Projeto e Análise de AlgoritmosAULA 04: Análise de Algoritmos Recursivos - Relação de Recorrência e Teorema MestreProfessor: Danilo Medeiros Eler..."
url: "https://www.youtube.com/watch?v=DdNCO6A-JjI"
favicon: ""
aspectRatio: "56.25"
```




Tipos de questão do teorema do mestre:
- Dado uma equação no formato padrão, descubra qual é a sua complexidade.
- Dado um algoritmo, coloque no formato padrão.
- Dado um $n = c$, sendo $c$ uma constante, descubra a solução na equação no formato padrão 