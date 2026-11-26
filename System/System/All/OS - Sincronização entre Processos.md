---
banner: "![[Pasted image 20251008190141.png]]"
---

---

> [!quote] **YouTube: ** [Sistemas Operacionais - Aula 08 - Sincronização entre Processos](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3DiCwMQJnKk2c%26list%3DPL-wATfeyAMNqIee7cH3q1bh4QJFAaeNv02)

> [!quote] **YouTube: ** [Sistemas Operacionais - Aula 09 - Sincronização entre Processos (parte 2)](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3DiCwMQJnKk2c%26list%3DPL-wATfeyAMNqIee7cH3q1bh4QJFAaeNv03)


---

```
Problema: 
- Uma CPU tem uma quantidade limitada de núcleos. Portanto, se faz necessário criar uma ferramenta para gerênciar os processos de forma que todos consigam se utilizar dos recurssos da CPU de forma justa.

Seção Crítica:
- Para garantir uma concorrência eficiente, precisamos eliminar a "Condição de corrida", ou seja, se assegurar que o dois processos diferentes não alterem o mesmo arquivo simutâneamente. Visando corrigir esse problema, se criou o conceito da condição de corrida.

```