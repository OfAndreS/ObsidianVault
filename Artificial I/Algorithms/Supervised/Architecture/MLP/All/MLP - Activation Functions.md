
---

````ad-quote
title:

**Função Degrau - Step Function**
```ad-quote
title:
<p align="justify">Uma das mais simples. Se o input for maior que zero, a saída é 1, senão é 0. É raramente usada em redes modernas devido à sua natureza não-diferenciável.</p>

1. $$f(z) = \begin{cases} 1 & \text{se } z \ge 0 \\ 0 & \text{se } z < 0 \end{cases}$$
```

````

![[Pasted image 20250805115906.png]]

````ad-quote
title:

**Função Sigmoide - Sigmoid**
```ad-quote
title:
<p align="justify">Transforma qualquer valor real em um valor entre 0 e 1. Foi muito popular no passado, mas pode sofrer do problema da "saturação dos gradientes". É útil em camadas de saída para tarefas de classificação binária.</p>

1. $$f(z) = \sigma(z) = \frac{1}{1 + e^{-z}}$$
```
````

![[Pasted image 20250805120011.png]]

````ad-quote
title:

**Função Tangente Hiperbólica - Tanh**
```ad-quote
title:
<p align="justify">Similar à sigmoide, mas comprime os valores no intervalo de -1 a 1. Muitas vezes converge mais rápido que a sigmoide por ser centrada em zero.</p>

1. $$f(z) = \tanh(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}}$$
```
````

![[Pasted image 20250805120101.png]]

````ad-quote
title:

**Unidade Linear Retificada - ReLU**
```ad-quote
title:
<p align="justify">É a função de ativação mais utilizada atualmente em redes profundas. Para qualquer valor de entrada negativo, a saída é zero. Para qualquer valor positivo, a saída é o próprio valor. É computacionalmente muito eficiente.</p>

1. $$f(z) = \max(0, z)$$
```
````

![[Pasted image 20250805120151.png]]

````ad-quote
title:

**Leaky ReLU**
```ad-quote
title:
<p align="justify">Uma variação da ReLU que permite uma pequena inclinação para valores negativos, ajudando a mitigar o problema do "neurônio morto" (quando um neurônio ReLU fica preso em uma saída de zero).</p>

1. $$f(z) = \begin{cases} z & \text{se } z > 0 \\ \alpha z & \text{se } z \le 0 \end{cases} \quad (\text{onde } \alpha \text{ é um pequeno valor, como 0.01})$$
```
````

![[Pasted image 20250805120310.png]]
