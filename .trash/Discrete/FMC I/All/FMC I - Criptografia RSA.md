---
banner: "![[Pasted image 20251201181229.png]]"
---

---

````ad-quote
title:

##### **Intro )** - O Guia Definitivo RSA

```ad-quote
title:
###### Visão Geral
```

![[Pasted image 20251202220613.png]]

```ad-quote
title:
<p align="justify">Este guia separa a teoria rigorosa do exemplo prático. A segurança do RSA fundamenta-se na assimetria computacional: é Trivial multiplicar dois números primos grandes, mas Computacionalmente Inviável fatorar o resultado de volta aos primos originais.</p>
```


````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Geração de Chaves (Key Generation)

```ad-quote
title:
<p align="justify">Etapa única onde se define o par de chaves. O objetivo é criar a fechadura (pública) e a chave mestra (privada).</p>
```

```ad-quote
title:
###### Passo 1: Seleção dos Primos
```

```ad-quote
title:
Escolha de dois números primos distintos e grandes, $p$ e $q$.
Nota: Estes valores são Segredos Supremos e devem ser destruídos após o cálculo.
```

```ad-quote
title:
###### Passo 2: O Módulo (n)
```

```ad-quote
title:
<p align="justify">Define a base do relógio para ambas as chaves.</p>
```
```ad-quote
title:
Fórmula:

2. $$n = p \times q$$
   
```

```ad-quote
title:
###### Passo 3: A Função Totiente ($\phi(n)$)
```

```ad-quote
title:
<p align="justify">Calcula-se quantos números menores que n são coprimos com n. Essencial para determinar o ciclo matemático.</p>
```
```ad-quote
title:
Fórmula:

3. $$\phi(n) = (p - 1) \times (q - 1)$$
   
```

```ad-quote
title:
###### Passo 4: O Expoente Público (e)
```

```ad-quote
title:
<p align="justify">Deve ser escolhido um inteiro e que obedeça a duas regras de coprimalidade.</p>
```
```ad-quote
title:
Regras:

- $$1 < e < \phi(n)$$
- $$\text{mdc}(e, \phi(n)) = 1$$
   
```

```ad-quote
title:
###### Passo 5: O Expoente Privado (d)
```

```ad-quote
title:
<p align="justify">Determina-se d como o inverso multiplicativo de e em relação ao totiente.</p>
```
```ad-quote
title:
Congruência Linear:
$$e \cdot d \equiv 1 \pmod{\phi(n)}$$
```

```ad-quote
title:
###### Resumo das Chaves
```
```ad-quote
title:
- Chave Pública: $(n, e)$
- Chave Privada: $(n, d)$
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - Mecânica de Transmissão

```ad-quote
title:
<p align="justify">O processo de comunicação segura entre Alice (Remetente) e Bob (Destinatário).</p>
```

```ad-quote
title:
###### I. Encriptação - O Cadeado
```

```ad-quote
title:
<p align="justify">Alice converte a mensagem em um número M (onde M é menor que n) e usa a Chave Pública de Bob.</p>
```

```ad-quote
title:
Fórmula:

1. $$C \equiv M^e \pmod n$$

Onde C é o Texto Cifrado.
```

```ad-quote
title:
###### II. Descriptação - A Chave
```

```ad-quote
title:
<p align="justify">Bob recebe C e utiliza sua Chave Privada para recuperar a informação.</p>
```

```ad-quote
title:
Fórmula:

1. $$M \equiv C^d \pmod n$$

Garantido pelo Teorema de Euler.
```

```ad-quote
title:
###### III. Aplicando a resolução de dois casos 
```

```ad-quote
title:

- Descobrir quem são $p$ e $q$
- Criar os dois casos de resolução:
  1. Lado P: $C^{d} \pmod p$
  2. Lado Q: $C^{d} \pmod q$
- Achar o passo de Fermat para cada lado:
  - $f_p = (p - 1)$
  - $f_q = (q - 1)$
- Dividir o expoente $d$ pelo $f$ correspondente ($f_p$ ou $f_q$) e usar os restos
- Calcular as potências reduzidas separadamente
- Comparar os restos finais
```

````

---
