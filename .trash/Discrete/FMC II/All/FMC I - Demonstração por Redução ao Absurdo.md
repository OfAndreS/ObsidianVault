---
banner: "![[Pasted image 20260311140138.png]]"
---

---

````ad-quote
title:

##### **intro )** - Demonstração por Redução ao Absurdo

```ad-quote
title:
<p align="justify">A Demonstração por Redução ao Absurdo, também conhecida como _reductio ad absurdum_, é um método de prova que estabelece a validade de uma proposição ao demonstrar que a sua negação conduz inevitavelmente a uma contradição lógica. No contexto de Fundamentos de Matemática para a Computação (FMC I), essa técnica é essencial para provar a inexistência de certos objetos matemáticos ou a veracidade de afirmações onde o caminho direto é excessivamente complexo.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - A Estrutura Lógica do Absurdo

```ad-quote
title:
O raciocínio por trás desse método fundamenta-se na Lei do Terceiro Excluído. Para provar uma afirmação P, inicia-se assumindo que P é falsa (ou seja, que _não P_ é verdadeira). A partir dessa premissa, desenvolve-se uma argumentação lógica rigorosa até que se alcance um _absurdo_: uma conclusão que contradiz a própria premissa inicial, uma definição aceita ou um fato matemático previamente estabelecido (como $0=1$). Uma vez que a lógica matemática não admite contradições, a suposição inicial de que _não P_ era verdadeira deve estar errada, o que força P a ser necessariamente verdadeira.
```
````

---

```ad-done
title:

#### Exemplos ) - Provas por Redução ao Absurdo

```

---

````ad-quote
title:

##### **Ex 01 )** - A Irracionalidade de Raiz de 2

```ad-quote
title:
_Proposição:_ 
- $\sqrt{2}$ é um número irracional.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Suposição e Contradição**
```

```ad-quote
title:
_Suposição Inicial_ (negação da tese): 
- $\sqrt{2}$ é um número racional.

_Objetivo:_ 
- Demonstrar que isso contradiz a definição de fração irredutível.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Demonstração**
```

```ad-quote
title:

_Assumir a negação:_ 
- Suponha que $\sqrt{2}$ seja racional. Então, existem inteiros p e q, com $q \neq 0$, tais que $\sqrt{2} = p/q$. Assumimos que a fração $p/q$ é _irredutível_ (p e q não possuem divisores comuns além de 1).

_Desenvolver a dedução:_ 

1. $$\sqrt{2} = \frac{p}{q} \Rightarrow 2 = \frac{p^2}{q^2}$$
2. $$p^2 = 2q^2$$

_Análise de Paridade:_ 
- Como $p^2$ é o dobro de um inteiro, $p^2$ é par, o que implica que _p também é par_. Logo, $p = 2k$ para algum inteiro k.
- Substituindo: $(2k)^2 = 2q^2 \Rightarrow 4k^2 = 2q^2 \Rightarrow 2k^2 = q^2$.
- Isso mostra que $q^2$ é par, logo _q também é par_.

_Conclusão do Absurdo:_ 
- Se p e q são ambos pares, eles podem ser divididos por 2. Isso contradiz a suposição de que a fração $p/q$ era _irredutível_. Portanto, a suposição de que $\sqrt{2}$ é racional é falsa, e ele deve ser irracional.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **Ex 02 )** - Inexistência de um Maior Número Inteiro

```ad-quote
title:
_Proposição:_ 
- Não existe um número inteiro que seja maior do que todos os outros.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Suposição e Contradição**
```

```ad-quote
title:
_Suposição Inicial_ (negação da tese): 
- Existe um número inteiro N que é o maior de todos.
```
````

````ad-quote
title:
```ad-quote
title:
###### **Demonstração**
```

```ad-quote
title:

_Assumir a negação:_ 
- Suponha que exista um número inteiro N tal que, para qualquer inteiro x, $N \geq x$.

_Desenvolver a dedução:_ 
- Considere o número $M = N + 1$.
- Como N é um inteiro e 1 é um inteiro, a soma de dois inteiros resulta em um inteiro. Logo, M é um número inteiro.

_Concluir o absurdo:_ 
- Por definição, $N + 1 > N$. Portanto, encontramos um inteiro M que é _maior_ que N.
- Isso contradiz a hipótese de que N era o maior número inteiro possível. Logo, a existência de um "maior inteiro" é um absurdo, provando que o conjunto dos inteiros é ilimitado superiormente.
```
````

---
