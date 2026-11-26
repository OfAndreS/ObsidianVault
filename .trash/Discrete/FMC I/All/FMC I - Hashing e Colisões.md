---
banner: "![[Pasted image 20251201181229.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Conceito e Motivação

```ad-quote
title:
###### O Problema da Busca Linear
```

```ad-quote
title:
Estruturas tradicionais, como vetores não ordenados ou listas ligadas, exigem uma Busca Linear ($O(n)$). Se houver 1 milhão de usuários, no Pior Caso, o computador verificará 1 milhão de posições.
```

```ad-quote
title:
###### A Mudança de Paradigma
```



```ad-quote
title:
As Tabelas Hash não "procuram"; nós Calculamos o endereço. O objetivo é a complexidade de tempo $O(1)$ (tempo constante).
```

```ad-quote
title:
<p align="justify">O tempo de acesso permanece o mesmo, independentemente de o banco de dados conter 10 ou 10 milhões de itens.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - A Matemática: O Método da Divisão

```ad-quote
title:
<p align="justify">A função de hash é o motor da estrutura. A implementação mais robusta para chaves inteiras baseia-se na Aritmética Modular.</p>
```

```ad-quote
title:
###### A Fórmula Fundamental
```

```ad-quote
title:
$$h(k) = k \pmod m$$
```

```ad-quote
title:
###### Os Componentes
```

```ad-quote
title:
- k (Chave): O dado único (Ex: CPF, Matrícula).
- m (Módulo): O tamanho total do vetor de memória.
- h(k) (Hash): O índice resultante de gravação.
```

```ad-quote
title:
###### O Papel Crítico dos Números Primos
```

```ad-quote
title:
Se $m$ for par ou potência de 2, ele cria padrões com dados de entrada. Para garantir uma Distribuição Uniforme e minimizar conflitos, $m$ deve ser um Número Primo distante de potências de 2. Isso "espalha" os dados de forma caótica e eficiente.
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Fenômeno da Colisão

```ad-quote
title:
<p align="justify">Ao mapear um universo potencialmente infinito de chaves para um espaço finito de memória, o Princípio Da Casa Dos Pombos entra em ação.</p>
```

![[Pasted image 20251201185829.png]]

```ad-quote
title:
###### Definição Matemática
```

```ad-quote
title:
$$k_1 \neq k_2 \quad \text{mas} \quad h(k_1) = h(k_2)$$
```

```ad-quote
title:
###### O Conflito Físico
```

```ad-quote
title:
<p align="justify">Dois dados diferentes competem pelo Mesmo Endereço Físico. Como o computador não pode sobrepor dados sem perder informação, é necessário um algoritmo de resolução.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Solução A: Encadeamento (Chaining)

```ad-quote
title:
<p align="justify">Esta é a abordagem de Memória Estendida. A tabela hash não guarda o dado, mas sim uma referência.</p>
```



```ad-quote
title:
###### Estrutura e Funcionamento
```

```plaintext
TABELA HASH                    ÁREA DE DADOS (LISTAS LIGADAS)
    (Vetor de Ponteiros)        (Memória Dinâmica Dispersa)
    +-------------------+
  0 |       NULL        |
    +-------------------+         +------+    +------+
  1 |     PONTEIRO      | ------> |  08  | -> |  15  | -> NULL
    +-------------------+         +------+    +------+
  2 |     PONTEIRO      | ------> +------+
    +-------------------+         |  23  | -> NULL
  3 |       NULL        |         +------+
    +-------------------+
  4 |       NULL        |
    +-------------------+
  5 |       NULL        |
    +-------------------+
  6 |       NULL        |
    +-------------------+
```

```ad-quote
title:
Cada índice do vetor ($0$ a $m-1$) contém um Ponteiro para o início de uma Lista Ligada. Se o índice 5 estiver ocupado, o novo elemento é simplesmente Adicionado à lista que reside naquele índice.
```

```ad-quote
title:
###### Análise de Engenharia
```

```ad-quote
title:
|Fator|Descrição|
|-|---|
|Custo|Consome Mais Memória (armazena dados + ponteiros).|
|Performance|Estável. A performance degrada suavemente mesmo com a tabela cheia.|
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Solução B: Endereçamento Aberto

```ad-quote
title:
<p align="justify">Esta é a abordagem de Memória Fixa. Todos os dados devem caber obrigatoriamente dentro da tabela principal.</p>
```



```ad-quote
title:
###### Sondagem Linear (Linear Probing)
```

```plaintext
TABELA HASH
      (Vetor de Dados)
    +-------------------+
  0 |      (vazio)      |
    +-------------------+
  1 |        08         | <--- COLISÃO AQUI! (15 queria entrar)
    +-------------------+      |
  2 |        23         | <--- Ocupado também! (Sondagem +1)
    +-------------------+      |
  3 |        15         | <--- LIVRE! (15 inserido aqui)
    +-------------------+
  4 |      (vazio)      |
    +-------------------+
  5 |      (vazio)      |
    +-------------------+
  6 |      (vazio)      |
    +-------------------+
```

```ad-quote
title:
Se a posição $h(k)$ está ocupada, o algoritmo tenta $h(k) + 1$, depois $h(k) + 2$, e assim por diante, tratando o vetor como um Buffer Circular.
```

```ad-quote
title:
###### O Problema do Agrupamento Primário
```

```ad-quote
title:
<p align="justify">O deslocamento cria Blocos Sólidos de dados ocupados (clusters). Quando um cluster cresce, o tempo de inserção e busca aumenta drasticamente, pois é necessário percorrer todo o bloco para achar uma vaga.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Resumo Comparativo para Engenharia

```ad-quote
title:
<p align="justify">A escolha da arquitetura depende estritamente das restrições do sistema.</p>
```

```ad-quote
title:
###### Use Encadeamento (Chaining) Quando:
```

```ad-quote
title:
1. Você não sabe quantos dados vão entrar (inserções > tamanho da tabela).
2. A remoção de dados é frequente (listas ligadas facilitam remoção).
3. Existe memória disponível para gastar com ponteiros.
```

```ad-quote
title:
###### Use Endereçamento Aberto Quando:
```

```ad-quote
title:
1. O tamanho dos dados é Conhecido e Fixo.
2. A memória é escassa (sistemas embarcados), evitando ponteiros extras.
3. O foco é Cache Do Processador (vetores contíguos são mais rápidos para a CPU).
```
````

```python
class TabelaHashDidatica:
    def __init__(self, tamanho_m):
        self.m = tamanho_m
        self.tabela = [None] * self.m

    def hash_function(self, k):
        """Calcula o índice usando aritmética modular."""
        return k % self.m

    def inserir_linear_probing(self, k, valor):
        """
        Simula o Endereçamento Aberto com Sondagem Linear.
        Mostra o problema dos 'Clusters' no terminal.
        """
        indice_inicial = self.hash_function(k)
        indice = indice_inicial
        
        # Tenta encontrar vaga (Loop Circular)
        while self.tabela[indice] is not None:
            print(f"Colisão em {indice}! Tentando próximo...")
            indice = (indice + 1) % self.m
            
            # Se deu a volta completa, tabela cheia
            if indice == indice_inicial:
                print("Erro: Tabela Cheia.")
                return

        self.tabela[indice] = (k, valor)
        print(f"Inserido chave {k} no índice {indice}")

if __name__ == "__main__":
    # Exemplo com m=7 (Primo)
    hash_map = TabelaHashDidatica(7)
    
    # Criação de Colisão Proposital
    # 10 % 7 = 3
    # 17 % 7 = 3 (Colisão)
    hash_map.inserir_linear_probing(10, "Dados A")
    hash_map.inserir_linear_probing(17, "Dados B") 
```

---