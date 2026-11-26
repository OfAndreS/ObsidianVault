
---

````ad-quote
title:

##### **Intro )** - O Pré Requisito

```ad-quote
title:
###### A Regra De Ouro
```

```ad-quote
title:
<p align="justify">Para aplicação de qualquer caso abaixo, existe uma condição inegociável: O Módulo p Precisa Ser Primo.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Redução De Expoentes

```ad-quote
title:
<p align="justify">Este é o uso mais frequente, focado no cálculo de restos para números com expoentes massivos onde a computação direta é inviável.</p>
```


```ad-quote
title:
###### O Conceito - Ciclo De Repetição
```

```ad-quote
title:
<p align="justify">Em aritmética modular com módulo p, as potências de uma base a entram em um ciclo. O tamanho desse ciclo é sempre p-1. Ao completar o ciclo, o valor reseta para 1.</p>
```

```ad-quote
title:
###### O Algoritmo De Resolução
```

```ad-quote
title:
Identificar O Ciclo:

1. $$Ciclo = p - 1$$

Dividir O Expoente:

2. $$\text{Dividir o expoente original pelo valor do Ciclo}$$

Focar No Resto:

3. $$\text{Obter o resto } r \text{ da divisão anterior}$$

Substituir:

4. $$a^N \equiv a^r \pmod p$$
```

```ad-quote
title:

|Conceito|Definição|
| --- | --- |
|$a$|A Base |
|$r$|O resto|
|$p$|O Módulo|
|$N$|O Expoente|

```

```ad-quote
title:
###### Fórmula Prática
```

```ad-quote
title:
Se 

- $p$ = É Primo
- $a$ = Não divide $p$

Então

- $$a^N \equiv a^r \pmod p$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Inverso Modular

```ad-quote
title:
<p align="justify">Focado na resolução de Equações Lineares. Como não existe divisão em aritmética modular, utilizamos a multiplicação pelo inverso.</p>
```

```ad-quote
title:
###### O Conceito - A Substituição Da Divisão
```

```ad-quote
title:
<p align="justify">O Teorema afirma que a elevado a p-1 resulta em 1. Logo, a multiplicado por a elevado a p-2 também resulta em 1. Portanto, a elevado a p-2 atua como o Inverso De a.</p>
```

```ad-quote
title:
###### O Algoritmo De Resolução
```

```ad-quote
title:
Equação Base:

1. $$ax \equiv b \pmod p$$

Calcular O Inverso:

2. $$Inverso = a^{p-2}$$

Multiplicar Ambos Os Lados:

3. $$x \equiv b \cdot (a^{p-2}) \pmod p$$
```

```ad-quote
title:
###### Fórmula Prática
```

```ad-quote
title:
A solução direta para x é:
$$x \equiv b \cdot a^{p-2} \pmod p$$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Provas De Divisibilidade

```ad-quote
title:
<p align="justify">Utilizado para demonstrações algébricas envolvendo variáveis inteiras n, provando que uma expressão é divisível por um primo p.</p>
```

```ad-quote
title:
###### O Conceito - A Forma Alternativa
```

```ad-quote
title:
<p align="justify">Diferente da forma clássica, esta variação vale para Qualquer Inteiro n. Ela implica que a diferença entre a potência e a base é múltipla do módulo.</p>
```

```ad-quote
title:
###### O Algoritmo De Resolução
```

```ad-quote
title:
Identificar O Formato:

1. $$\text{Procurar termos como } n^p \text{ onde o expoente iguala o divisor}$$

Aplicar A Substituição:

2. $$n^p \equiv n \pmod p$$

Simplificar:

3. $$\text{Substituir na expressão e observar o cancelamento dos termos}$$
```

```ad-quote
title:
###### Fórmula Prática
```

```ad-quote
title:
Para todo inteiro n e primo p:
$$n^p - n \equiv 0 \pmod p$$
```
````

---