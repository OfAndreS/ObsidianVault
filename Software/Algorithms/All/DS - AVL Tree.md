
---

>[!quote] **Link:** [Árvore AVL (YouTube)](https://youtu.be/HNTvsHRZuqY)

---

```ad-done
title:
#### **Fase 1 ) - Fator de Balanceamento**
```

---

````ad-quote
title:

##### **01 )** - Fator de Balanceamento (FB)

```ad-quote
title:
<p align="justify">O fator de balanceamento é um coeficiente que serve como referência para verificar se a AVL está balanceada. Esse fator é calculado em cada nó e é dado pela altura da sub-árvore da esquerda hsae(T) menos a altura da sub-árvore da direita hsad(T).</p>
```

```ad-quote
title:
1. $$fb(T) = hsae(T) - hsad(T)$$
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Interpretação dos Valores_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Valores Balanceados*
```

```ad-quote
title:
<p align="justify">Uma árvore AVL aceita apenas três valores inteiros para manter o equilíbrio estrutural em cada nó.</p>
```

```shell
0 )
# As duas subárvores possuem a mesma altura exata.
# O nó está equilibrado.

+1 )
# A subárvore esquerda é mais alta que a subárvore direita por um nível.
# O nó está equilibrado.

-1 )
# A subárvore direita é mais alta que a subárvore esquerda por um nível.
# O nó está equilibrado.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Valores Desbalanceados*
```

```ad-quote
title:
<p align="justify">Valores fora do intervalo aceitável exigem rotações para restaurar o equilíbrio da árvore.</p>
```

```bash
+2 )
# A subárvore esquerda está muito mais alta que a subárvore direita.
# O nó está desbalanceado para a esquerda.

# A estrutura exige rotação simples à direita ou rotação dupla à direita.


-2 )
# A subárvore direita está muito mais alta que a subárvore esquerda.
# O nó está desbalanceado para a direita.

# A estrutura exige rotação simples à esquerda ou rotação dupla à esquerda.
```
````

---

```ad-done
title:
#### **Fase 2 ) - Auto-balanceamento**
```

---

````ad-quote
title:

##### **02 )** - Mecanismos de Rotação

```ad-quote
title:
<p align="justify">Existem quatro tipos básicos de rotações para corrigir desvios no fator de balanceamento e restaurar a estabilidade da árvore AVL.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Rotações Simples_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Simples à Direita (LL)*
```

```ad-quote
title:
<p align="justify">Acontece quando inserimos elementos menores sucessivamente, criando uma linha inclinada para a esquerda.</p>
```

```shell

# Desbalanceado no nó 30:

      30
     /
    20
   /
  10

# Aplicando a rotação à direita sobre o nó 30, o nó 20 sobe e se torna a raiz.


    20
   /  \
  10  30

```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Simples à Esquerda (RR)*
```

```ad-quote
title:
<p align="justify">Ocorre no cenário oposto, quando valores maiores são inseridos em sequência pelo lado direito.</p>
```

```shell

# Desbalanceado no nó 10:

  10
    \
     20
       \
        30

# Ao rotacionar o nó 10 para a esquerda, o nó 20 sobe para a raiz:

    20
   /  \
  10  30

```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.2 ) - _Rotações Duplas_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Dupla à Direita (LR)*
```

```ad-quote
title:
<p align="justify">Surge quando o elemento entra no lado esquerdo do nó principal, mas depois vira para a direita, formando um zig-zag.</p>
```

```shell

# Estado inicial com zig-zag:

      30
     /
    10
     \
      20

# Primeiro passo: rotação simples à esquerda no nó 10 para alinhar a coluna:

      30
     /
    20
   /
  10

# Segundo passo: rotação simples à direita no nó 30 para equilibrar:

    20
   /  \
  10  30

```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Dupla à Esquerda (RL)*
```

```ad-quote
title:
<p align="justify">Acontece quando a inserção vai para a direita e em seguida dobra para a esquerda.</p>
```

```shell

# Estado inicial com zig-zag:

  10
    \
     30
    /
   20

# Primeiro passo: rotação simples à direita no nó 30 para alinhar os elementos

  10
    \
     20
       \
        30

# Segundo passo: rotação simples à esquerda no nó 10

    20
   /  \
  10  30

```
````

---

```ad-done
title:
#### **Fase 3 ) - Operações na AVL**
```

---

````ad-quote
title:

##### **03 )** - Operações Fundamentais

```ad-quote
title:
<p align="justify">As operações na árvore AVL preservam a lógica clássica da árvore binária de busca, com a adição de inspeção recursiva do fator de balanceamento e rebalanceamento automático imediato.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.1 ) - _Busca de Chave_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Mecânica e Complexidade*
```

```ad-quote
title:
<p align="justify">O código de busca na árvore AVL é exatamente igual ao código da árvore binária de busca padrão [[DS - BST Tree |{ X }]]. Dessa forma, a operação de leitura apenas percorre os ponteiros existentes. A busca nunca altera as chaves ou o fator de balanceamento dos nós. A diferença ocorre apenas na complexidade de tempo no pior caso. Entretanto, a árvore AVL garante busca em tempo logarítmico O(log n) porque mantém a estrutura sempre equilibrada.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.2 ) - _Inserção de Elementos_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Fluxo de Inserção*
```

```shell
01 )
# O algoritmo desce pela árvore usando a regra padrão de busca e insere o novo nó como uma folha.

02 )
# O recálculo da altura e do fator de balanceamento ocorre no retorno das chamadas recursivas. A verificação sobe do novo nó inserido em direção à raiz da árvore.

03 )
# O algoritmo verifica se o módulo do fator de balanceamento de cada nó ancestral é maior que 1. Quando o valor atinge 2 ou menos 2, a função executa a rotação adequada naquele ponto.

04 )
# Na operação de inserção, uma única rotação simples ou dupla restaura a altura original da subárvore. Os nós ancestrais acima do ponto rotacionado não sofrem mais alterações de altura.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Exemplo de Inserção*
```

```shell

# Considere a árvore balanceada abaixo antes da operação:

          ( 30 | +1 )
          /         \
    ( 10 | -1 )   ( 40 | 0 )
          \
      ( 20 | 0 )


# Ao inserir a chave 25, o algoritmo posiciona o novo nó à direita do nó 20 e atualiza os fatores no retorno da recursão:

          ( 30 | +2 )
          /         \
    ( 10 | -2 )   ( 40 | 0 )
          \
      ( 20 | -1 )
            \
          ( 25 | 0 )


# O nó 10 é o ancestral mais próximo com desequilíbrio e configura o Caso LR, aplicando uma rotação simples à esquerda no filho 20:

            ( 30 | +2 )
            /         \
      ( 20 | +1 )   ( 40 | 0 )
      /         \
( 10 | 0 )   ( 25 | 0 )


# Em seguida, o algoritmo aplica uma rotação simples à direita no nó 10 e restaura o equilíbrio de toda a árvore:

            ( 30 | +1 )
            /         \
      ( 20 | 0 )    ( 40 | 0 )
      /        \
( 10 | 0 )  ( 25 | 0 )

```
````

> [!done] **_New_**

```ad-quote
title:

##### 3.3 ) - _Remoção de Elementos_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Fluxo de Remoção*
```

```shell
01 )
# O algoritmo localiza o nó alvo e executa a exclusão usando as três regras padrão de uma árvore binária de busca.

02 )
# O recálculo da altura e do fator de balanceamento ocorre no retorno das chamadas recursivas. A verificação sobe do ponto da remoção física em direção à raiz da árvore.

03 )
# O algoritmo avalia o fator de balanceamento de cada ancestral. Quando o valor atinge 2 ou menos 2, a função analisa o sinal do filho do lado mais alto e executa a rotação.

04 )
# Na remoção, uma rotação pode diminuir a altura total da subárvore. O algoritmo deve continuar verificando todos os ancestrais até a raiz, podendo realizar múltiplas rotações.
```
````

````ad-quote
title:

```ad-quote
title:
###### B ) *Exemplo de Remoção*
```

```shell

# Considere a árvore balanceada abaixo antes da operação:

          ( 20 | -1 )
          /         \
    ( 10 | 0 )    ( 40 | +1 )
                   /         \
             ( 30 | -1 )   ( 50 | 0 )
                   \
               ( 35 | 0 )


# Ao remover a chave 10, o lado esquerdo da raiz perde altura e o algoritmo atualiza o fator de balanceamento no retorno da recursão:

          ( 20 | -2 )
                    \
                  ( 40 | +1 )
                  /         \
            ( 30 | -1 )   ( 50 | 0 )
                  \
              ( 35 | 0 )


# O nó 20 possui fator negativo dois e seu filho direito 40 possui fator positivo um, configurando o Caso RL, que aplica uma rotação simples à direita no filho 40:

          ( 20 | -2 )
                    \
                  ( 30 | -2 )
                            \
                          ( 40 | 0 )
                          /        \
                    ( 35 | 0 )  ( 50 | 0 )


# Em seguida, o algoritmo aplica uma rotação simples à esquerda no nó 20 e restaura o equilíbrio completo da árvore:

                ( 30 | -1 )
                /         \
          ( 20 | 0 )    ( 40 | 0 )
                        /        \
                  ( 35 | 0 )  ( 50 | 0 )

```
````

---