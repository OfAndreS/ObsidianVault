---
banner: "![[Pasted image 20250913205332.png]]"
---

---

![[🔍 Search.base#Math - FMC I]]

---

````ad-quote
title:
##### **Intro ) - Fundamentos da Matemática Computacional I **

```ad-quote
title:

"A matemática é a única linguagem que temos em comum com a natureza"
- Albert Einstein
```
````

>[!quote] **Draw** [[FMC.excalidraw]]

>[!quote] **Roteiro:** [[FMC I - Roteiro P I]] 

>[!quote] **YouTube:** [FMC I - PlayList - Pt 1 & Pt 2](https://www.youtube.com/watch?v=QE6ruiq632o&list=PLrOyM49ctTx-HWypJVvn_zMO1o7oOAfVx&index=1)

>[!quote] **YouTube:** [FMC I - Playlist - Pt 3 & Pt 4](https://youtu.be/bhfhmre-QxU?si=lLQUoMkOdY8DPu1D)

---

```ad-example

#### **Fase 1 ) - Fundamentos**
```

---
#### **00 )** - Sistemas de numeração

```ad-quote
title: **Def**
**Summary:**
- A estruturação do pensamento matemático pode ser feita por meio de diversas bases numéricas, sendo que cada uma possui particularidades e benefícios distintos. Neste _vault_, são expostos o conceito e a representação das bases mais notáveis.
```

>[!quote] **Vault:** [[FMC I - Sistemas de Numeração]]

---
#### **01 )** - Proposições e Conectivos Lógicos

```ad-quote
title: **Def**
**Summary:**
- O objetivo é introduzir o conceito de proposição como uma sentença que pode ser classificada como verdadeira ou falsa, e apresentar os conectivos lógicos (conjunção, disjunção, condicional, etc.) e as tabelas-verdade usadas para combinar e avaliar essas proposições.
```

> [!quote] **Vault:** [[FMC I - Proposições e Valor Verdade]]

---

> [!example] _New_

---
#### **02 )** - Fórmulas, Tautologias e Contradições

```ad-quote
title: **Def**
**Summary:**
- Foco em como construir expressões lógicas complexas, chamadas Fórmulas Bem-Formuladas (fbf), seguindo regras de sintaxe e precedência. Além disso, definir os conceitos de tautologia, uma fórmula sempre verdadeira, e contradição, uma fórmula sempre falsa.
```

> [!quote] **Vault:** [[FMC I - Fórmulas Bem-Formuladas (fbf)]]

> [!quote] **Vault:** [[FMC I - Tautologias e Contradições]]

---

> [!example] _New_

---
#### **03 )** - Equivalências Lógicas e Aplicações

```ad-quote
title: **Def**
**Summary:**
- O foco é apresentar o conceito de equivalência entre fbfs, destacando equivalências fundamentais como as Leis de De Morgan, e mostrar como esses princípios são aplicados para simplificar expressões em contextos práticos, como programação e algoritmos de teste.
```

> [!quote] **Vault:** [[FMC I - Equivalências Tautológicas]]

---

```ad-example

#### **Fase 2 ) - Lógica Proposicional e Argumentação**
```

---
#### **04 )** - Argumentos Válidos

```ad-quote
title: **Def**
**Summary:**
- Neste tópico, você aprenderá a definir formalmente um argumento como um conjunto de hipóteses que levam a uma conclusão. O critério para um argumento ser considerado válido é que a fbf que o representa seja uma tautologia.
```

> [!quote] **Vault:** [[FMC I - Estrutura de Argumentos Válidos]]

---

> [!example] _New_

---
#### **05 )** - Regras de Dedução e Demonstrações Formais

```ad-quote
title: **Def**
**Summary:**
- O objetivo é introduzir o sistema formal para provar a validade de argumentos através de uma "sequência de demonstração", utilizando regras de equivalência e regras de inferência como Modus Ponens e Modus Tollens para derivar a conclusão a partir das hipóteses.
```

> [!quote] **Vault:** [[FMC I - Regras de Dedução e Inferência]]

> [!quote] **Vault:** [[FMC I - Demonstrações Formais]]

---

> [!example] _New_

---
#### **06 )** - Análise de Argumentos Verbais

```ad-quote
title: **Def**
**Summary:**
- Aprender a aplicar a lógica proposicional para analisar a validade de argumentos expressos em linguagem natural. O processo envolve traduzir o argumento para a notação simbólica e, em seguida, construir uma prova formal para verificar sua validade.
```

> [!quote] **Vault:** [[Lógica - Análise de Argumentos Verbais]]

---

```ad-example

#### **Fase 3 ) - Métodos e Estratégias de Demonstração**
```

---
#### **07 ) -** Técnicas de demonstração

```ad-quote
title: **Def**
**Summary:**
- A lógica proposicional é insuficiente para analisar a validade de argumentos cuja estrutura interna depende de quantificadores e relações entre objetos. Para suprir essa necessidade, foi desenvolvida a Lógica de Predicados. Dentro desses sistemas lógicos (tanto o proposicional quanto o de predicados), utilizamos diversas Técnicas de Demonstração para construir provas rigorosas e verificar a veracidade das afirmações.
  
```

>[!quote] **Vault:** [[FMC I - Tecnicas de Demonstracao]]

---

> [!example] _New_

---
#### **08 ) -** Demonstração Direta e por Contraposição

```ad-quote
title: **Def**
**Summary:**
- Introduzir duas das principais técnicas de prova. A Prova Direta assume a veracidade das premissas para chegar à conclusão. A Prova por Contraposição, por sua vez, prova a equivalência `¬Q → ¬P` ao assumir que a conclusão é falsa para demonstrar que a premissa também deve ser falsa.
```

> [!quote] **Vault:** [[FMC I - Demonstração Direta]]

> [!quote] **Vault:** [[FMC I - Demonstração por Contraposição]]

---

> [!example] _New_

---
#### **09 )** - Demonstração por Contradição (Redução ao Absurdo)

```ad-quote
title: **Def**
**Summary:**
- Aprender a poderosa técnica da Redução ao Absurdo. O método consiste em assumir que a afirmação a ser provada é falsa e, a partir daí, derivar uma contradição lógica (um resultado impossível). Isso força a conclusão de que a suposição inicial era incorreta e, portanto, a afirmação original é verdadeira.
```

> [!quote] **Vault:** [[FMC I - Demonstração por Contradição]]

---

> [!example] _New_

---
#### **10 )** - Demonstração por Casos e Indução Matemática

```ad-quote
title: **Def**
**Summary:**
- Este tópico aborda duas técnicas essenciais. A Prova por Casos divide o problema em subconjuntos e prova a afirmação para cada um deles. A Prova por Indução (Forte e Fraca) é usada para provar que uma propriedade é válida para todos os inteiros a partir de um ponto inicial, através de um passo base e um passo indutivo.
```

> [!quote] **Vault:** [[FMC I - Demonstração por Casos]]

>[!quote] **Vault:** [[FMC I - Princípio de Indução Matemática]]

---

```ad-example

#### **Fase 4 ) - Relações de Recorrência**
```

---

>[!quote] **Vault:** [Material](https://docs.google.com/document/d/1k1JC7u2X8kyrAhelXU7Hkr1SEW-ITXCB8Fx5TUDpqMs/edit?tab=t.0)

>[!quote] **Vault:** [[FMC I - Relações de Recorrência]] 

---
#### **11 )** - Fundamentos das Relações de Recorrência

```ad-quote
title: **Def**
**Summary:**
- O objetivo é entender como sequências podem ser definidas recursivamente. Você aprenderá a definir uma relação de recorrência com suas condições iniciais, a classificar as relações quanto à _ordem_, _linearidade_ e _homogeneidade_, e a dominar o método de resolução para relações lineares de 1º grau com coeficiente constante.
```

> [!quote] **Vault:** [[Mat Discreta - Relações de Recorrência de 1º Grau]]

---

> [!example] _New_

---
#### **12 )** - Relações de Recorrência de 2ª Ordem

```ad-quote
title: **Def**
**Summary:**
- Foco em resolver relações lineares homogêneas de 2º grau com coeficientes constantes. O tópico central é a _equação característica_ derivada da relação, e como encontrar a solução geral para os três casos possíveis de suas raízes: duas raízes reais distintas, duas raízes reais iguais ou duas raízes complexas conjugadas.
```

> [!quote] **Vault:** [[Mat Discreta - Relações de Recorrência de 2º Grau]]

---

> [!example] _New_

---
#### **13 )** - Generalização e Exercícios

```ad-quote
title: **Def**
**Summary:**
- Este tópico busca generalizar o método da equação característica para resolver relações de recorrência lineares homogêneas de grau _k_. O objetivo secundário é consolidar todo o conhecimento do módulo através da resolução de uma variedade de problemas, misturando diferentes ordens e tipos de relações.
```

> [!quote] **Vault:** [[Mat Discreta - Relações de Recorrência de Ordem k]]

---

```ad-example

#### **Fase 5 ) - Fundamentos de Teoria dos Números**
```

---
#### **14 )** - O Conceito de Divisibilidade

```ad-quote
title: **Def**
**Summary:**
- Introduzir a base da teoria dos números: a divisibilidade. O foco é entender a definição formal de que um inteiro _a_ divide um inteiro _b_, estudar e demonstrar as propriedades fundamentais dessa relação, e conectar o conceito matemático com suas aplicações práticas em computação.
```

> [!quote] **Vault:** [[FMC I - Divisibilidade e Propriedades]]

---

> [!example] _New_

---
#### **15 )** - O Algoritmo da Divisão

```ad-quote
title: **Def**
**Summary:**
- Estudar o _Teorema da Divisão_, que garante a existência e unicidade do quociente e do resto para a divisão de dois inteiros. O objetivo é relacionar este teorema fundamental com as operações computacionais de divisão inteira (_div_) e módulo (_mod_), aplicando-o em problemas práticos, inclusive com números negativos.
```

> [!quote] **Vault:** [[FMC I - Teoria dos Números Teorema da Divisão]]

---

> [!example] _New_

---
#### **16 )** - Números Inteiros, Computação e Divisão

```ad-quote
title: **Def**
**Summary:**
- Explorar a implementação computacional do TEOREMA DA DIVISÃO (Tópico 15), focando em como o CONJUNTO ℤ (negativos) cria ambiguidades. O objetivo é contrastar as duas soluções para o quociente (q): TRUNCAMENTO (C/Java) versus PISO (Python, Tópico 17). A meta é demonstrar por que a abordagem de PISO é a implementação matematicamente correta, pois é a única que satisfaz a regra do resto (0 ≤ r < |b|).
```

> [!quote] **Vault:** [[FMC I - Números Inteiros e Divisão]]

---

> [!example] _New_

---
#### **17 )** - Ferramentas de Análise Inteira

```ad-quote
title: **Def**
**Summary:**
- Apresentar duas funções essenciais para trabalhar com números inteiros. O objetivo é definir formalmente a _função piso_ (maior inteiro menor ou igual a x) e a _função teto_ (menor inteiro maior ou igual a x), e compreender suas principais propriedades e identidades.
```

> [!quote] **Vault:** [[FMC I - Função Piso e Teto]]

---

> [!example] _New_

---
#### **18 )** - Primalidade e Teorema Fundamental da Aritmética

```ad-quote
title: **Def**
**Summary:**
- Definir números primos e números compostos. O objetivo principal é compreender, enunciar e aplicar o _Teorema Fundamental da Aritmética_ (TFA), que garante que todo inteiro maior que 1 pode ser decomposto de forma única (a menos da ordem) como um produto de fatores primos.
```

> [!quote] **Vault:** [[FMC I - Primalidade e Teorema Fundamental da Aritmética]]

---

> [!example] _New_

---
#### **19 )** - Propriedades dos Números Primos

```ad-quote
title: **Def**
**Summary:**
- Explorar as propriedades avançadas dos números primos, como sua infinitude (demonstração de Euclides) e sua distribuição (Teorema dos Números Primos). O objetivo é aplicar esses conceitos em exercícios e discutir problemas em aberto famosos, como a Hipótese de Riemann e a Conjectura de Goldbach.
```

> [!quote] **Vault:** [[FMC I - Propriedades dos Primos e Problemas em Aberto]]

---

> [!example] _New_

---
#### **20 )** - Critérios de Divisibilidade

```ad-quote
title: **Def**
**Summary:**
- Estudar e demonstrar os critérios de divisibilidade mais comuns (por 2, 3, 4, 5, 6, 8, 9, 10, 11). O objetivo é entender a lógica por trás dessas "regras", baseando-se na aritmética modular e no sistema decimal, para verificar rapidamente a divisibilidade sem realizar a divisão completa.
```

> [!quote] **Vault:** [[FMC I - Critérios de Divisibilidade]]

---

> [!example] _New_

---
#### **21 )** - Algoritmo Estendido de Euclides

```ad-quote
title: **Def**
**Summary:**
- Introduzir o Algoritmo Estendido de Euclides como um método para encontrar o MDC de dois números, *a* e *b*, e também para encontrar coeficientes inteiros *x* e *y* que satisfazem a identidade de Bézout: *ax + by = mdc(a, b)*. O foco é entender sua aplicação na resolução de equações diofantinas lineares e no cálculo de inversos modulares.
```

> [!quote] **Vault:** [[FMC I - Algoritmo Estendido de Euclides]]

---

>[!quote] **Vault:** [[FMC I - Roteiro Final]]

>[!quote] **Vault:** [[FMC I - Congruência na Criptografia ]]

>[!quote] **Vault:** [[FMC I - Congruências Lineares]]

>[!quote] **Vault:** [[FMC I - Inverso Modular]]

>[!quote] **Vault:** [[FMC I - Teorema Chinês]]

>[!quote] **Vault:** [[FMC I - Teoremas de Fermat]]

>[!quote] [!quote] **Vault:** [[FMC I - Criptografia Classica]]

>[!quote] [!quote] **Vault:** [[FMC I - Criptografia RSA]]