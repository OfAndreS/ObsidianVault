
---

````ad-quote
title:
##### **01 ) -** Garantia de um Par

```ad-quote
title:
Sobreposição de elementos em uma categoria
```

```ad-quote
title:
- $$P=C+1$$ 
```
```ad-quote
title:
|Descrição|
|-|
|$P$ Limite de elementos retirados / Pombos|
|$C$ Categorias no domínio / Casas|
```
````

````ad-quote
title:

##### Exemplo 01 )

```ad-quote
title:
Em um grupo de pessoas, qual é o número mínimo de indivíduos necessários para garantir que pelo menos dois façam aniversário no mesmo mês? 
```

```ad-quote
title:
O limite de categorias (meses) é $C=12$. Logo, é necessário agrupar $P=12+1=13$ indivíduos.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **02 ) -** Repetição de k Elementos

```ad-quote
title:
Sobreposição de k elementos em uma classe
```

```ad-quote
title:
- $$N=C\times(k-1)+1$$
```
```ad-quote
title:
|Descrição|
|-|
|$N$ total de extrações|
|$C$ número de partições disponíveis|
|$k$ cota exigida por classe|
```
````

````ad-quote
title:
##### Exemplo 02 )

```ad-quote
title:
Um baralho padrão possui 52 cartas divididas em 4 naipes de 13 cartas cada. Qual é o número mínimo de cartas que devem ser sacadas para garantir que 5 delas sejam do mesmo naipe?
```

```ad-quote
title:
Existem $C=4$ partições (naipes) e a exigência é $k=5$. O número de saques é $N=4\times(5-1)+1=17$ cartas.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:
##### **03 ) -** Um de Cada Classe

```ad-quote
title:
Obtenção de um elemento de cada classe
```

```ad-quote
title:
- $$N=\left(\sum_{i=1}^{C-1}X_{i}\right)+1$$
```
```ad-quote
title:
|Descrição|
|-|
|$N$ total de extrações|
|$C$ número total de categorias|
|$X_i$ capacidade da i-ésima categoria mais abundante, ordenadas decrescentemente|
```
````

````ad-quote
title:
##### Exemplo 03 )

```ad-quote
title:
Uma urna contém 10 bolas azuis, 8 bolas vermelhas e 5 bolas verdes. Qual é o número mínimo de bolas que devem ser retiradas para garantir que haja ao menos uma de cada cor?
```

```ad-quote
title:
Soma-se o volume total das duas maiores categorias, esgotando o limite de falhas ($10+8=18$). A próxima extração forçará o acerto. O número é $N=18+1=19$ bolas.
```
````

---
