---
banner: "- FILES/Attachments/Pasted image 20261012210111.png"
banner-fade: 100
---

---

````ad-quote
title:

```ad-quote
title:
###### ... ) *Definições*
```

```bash
01 )
# Uma árvore rubro-negra é uma árvore binária de busca.

02 )
# Todo nó pertencente à árvore é vermelho ou negro.

03 )
# O nó raiz é negro.

04 )
# Se um nó é vermelho, então os seus filhos são negros.

05 )
# Se um nó é vermelho, então o seu pai é negro.

06 )
# Para todo nó, todos os caminhos até as folhas descendentes contêm a mesma quantidade de nós negros.
```

````

> [!done] **_New_**

#### Graduação de uma árvore

A graduação serve para verificar se uma árvore qualquer é de fato uma rubro-negra.

````ad-quote
title:

```ad-quote
title:
###### ... ) *Definições*
```

```ad-quote
title:
$T$ é graduada quando, para todo nó $v$ pertencente a $T$, o valor $posto(v)$ satisfaz as seguintes condições:
```

```bash
01 )
# Se v é externo, posto(v) = 0.

02 )
# Se v é pai de um nó externo, posto(v) = 1.

03 )
# Se v é filho de w, (posto(w) = posto(v)) ou (posto(w) = posto(v) + 1).

04 )
# Se v é neto de w, posto(w) > posto(v).
```

````

Existem árvores que devido a sua estrutura impossibilitam a graduação. Tome como exemplo a árvore abaixo.

```shell

         ( )
        /   \
      ( )   [ ]
      /   \
    [ ]   ( )
          / \
        [ ] [ ]

```

Ao substituir os símbulos abstratos pelos valores de postulação da graduação fica evidente o descumprimento da regra 4. Dessa forma, impossibilitanto essa árvore ser uma rubro-negra.

```shell

         (1)
        /   \
      (1)   [ ]
      /   \
    [ ]   (1)
          / \
        [ ] [ ]

```

Seja T uma árvore graduada:

❑  Percorra T de cima para baixo, colorindo seus nós da seguinte forma:

```shell
    se v é a raiz de T
        então cor(v) <- negra
    senão
        seja w o pai de v
        se posto(v) = posto(w)
            então cor(v) <- rubra
            senão cor(v) <- negra
```

---
---

O algoritmo de busca é o mesmo da AVL e da ABB.

---
---

Aqui está a transcrição completa do texto, do código e a representação visual em ASCII do conteúdo da imagem:

## Caso 1

O novo nó N está na raiz da árvore.

- Neste caso, este nó muda para negro e satisfaz a propriedade.
- Como esta ação adiciona um nó negro em todos os caminhos da árvore de uma só vez, as propriedades não são violadas.

## Código em C

```c
void insercao_caso1(struct node *n){
    if(n -> pai == NULL)
        n->cor = NEGRO;
    else
        insercao_caso2(n);
}
```

## Representação Visual (Árvores)

```text
    ( )               ( )
   /   \     ───►    /   \
 [ ]   [ ]         [ ]   [ ]
(Rubro)            (Negro)
```

---
---

Aqui está a transcrição completa do texto, do código em C e a representação em arte ASCII do conteúdo da imagem:

## Caso 2

O pai do novo nó é negro.

- Neste caso as Propriedades claramente não são invalidadas;
- As Propriedades não são ameaçada;
- Neste caso, a árvore continua válida após a inserção, não sendo necessária mais alterações.

## Código em C

```c
void insercao_caso2(struct node *n){
    if(n->pai->cor == NEGRO)
        return;
    else
        insercao_caso3(n);
}
```

## Representação Visual (Árvore)

_Legenda utilizada para as cores conforme solicitado:_ `(N)` para nós Negros e `(R)` para nós Rubros (o novo nó N inserido).

```text
         (N) G
        /     \
    P (N)     (N) U
      / \     / \
  N (R) [ ]  [ ] [ ]
    / \
  [ ] [ ]
```

---
---

Aqui está a transcrição completa do texto, do código em C e a representação em arte ASCII das duas árvores da imagem:

## Caso 3

Quando ambos o pai P e o tio U são vermelhos, então ambos podem ser trocados para negro e o avô G torna-se rubro.

- Agora, o novo nó vermelho N tem um pai negro. Dado que todos os caminhos que passam pelo pai ou tio de N devem passar pelo seu avô, o número de nós negros nestes caminhos não foi alterado. Porém, o avô G pode estar violando agora uma Propriedade. Para consertar isso, uma "chamada recursiva" do procedimento de insercao_caso1 é iniciada passando G como parâmetro.

## Código em C

```c
void insercao_caso3 (struct node *n){
    struct node *u = tio(n), *g;
    if ((u != NULL) && (u->cor == RUBRO)){
        n->pai->cor = NEGRO;
        u->cor = NEGRO;
        g = avo(n);
        g->cor = RUBRO;
        insercao_caso1(g);
    } else {
        insercao_caso4(n);
    }
}
```

## Representação Visual (Antes e Depois)

_Legenda para as cores:_ `(N)` para nós Negros e `(R)` para nós Rubros.

```text
       Antes da Alteração                        Depois da Alteração
       
             (N) G                                     (R) G
            /     \                                   /     \
        P (R)     (R) U                           P (N)     (N) U
          / \     / \                               / \     / \
      N (R) [ ]  [ ] [ ]                        N (R) [ ]  [ ] [ ]
        / \                                       / \
      [ ] [ ]                                   [ ] [ ]
```


---
---

Aqui está a transcrição completa do texto, do código em C e a representação em arte ASCII das duas árvores do Caso 4:

## Caso 4

O pai P é vermelho mas o tio U é negro; além disso, o novo nó N é o filho a direita de P, e P o filho a esquerda do seu pai G.

- Neste caso, uma rotação a esquerda que troca os papéis do novo nó N e de seu pai P deve ser realizada.
- Quando isso acontecer o antigo nó-pai P precisa ser tratado usando o Caso 5 (renomeando N e P), isso porque uma Propriedade ainda está sendo violada.

## Código em C

```c
void insercao_caso4(struct node *n){
    struct node *g = avo(n);
    if((n == n->pai->direita) && (n->pai == g->esquerda)){
        rotacionar_esquerda(n->pai);
        n = n->esquerda;
    } else if ((n == n->pai->esquerda) && (n->pai == g->direita)){
        rotacionar_direita(n->pai);
        n = n->direita;
    }
    insercao_caso5(n);
}
```

## Representação Visual (Antes e Depois da Rotação)

_Legenda para as cores:_ `(N)` para nós Negros e `(R)` para nós Rubros. Os triângulos representam subárvores.

```text
       Antes da Rotação                         Depois da Rotação
       
             (N) G                                    (N) G
            /     \                                  /     \
        P (R)     (N) U                          N (R)     (N) U
        /   \     /   \                          /   \     /   \
       ▲   (R) N ▲     ▲                        (R) P ▲   ▲     ▲
                 / \                            / \
                ▲   ▲                          ▲   ▲
```

Você gostaria que eu transcrevesse também o próximo passo, que seria o Caso 5, para completar o ciclo de inserção na Árvore Rubro-Negra?

---
---

Aqui está a transcrição completa do texto, do código em C e a representação em arte ASCII das duas árvores do Caso 5:

## Caso 5

O pai P é rubro mas o tio U é negro, o novo nó N é o filho esquerdo de seu pai P, e P é o filho esquerdo de seu pai, G.

- Neste caso, uma rotação a direita no pai de P é realizada. O resultado é uma árvore onde o antigo pai P é agora pai tanto do novo nó N quanto do avô de N, G. É sabido que G é negro, já que seu antigo filho P não poderia ser rubro. Então as cores de P e G são trocadas, e a árvore resultante satisfaz as propriedades (ambos os filhos de cada nó rubro são negros).

## Código em C

_(Nota: Corrigido o pequeno erro de digitação contido na imagem no trecho `n->pai_cor` para `n->pai->cor` para garantir a validade sintática)._

```c
void insercao_caso5(struct node *n){
    struct node *g = avo(n);
    n->pai->cor = NEGRO;
    g->cor = RUBRO;
    if((n == n->pai->esquerda) && (n->pai == g->esquerda)){
        rotacionar_direita(g);
    } else {
        /*Aqui, (n == n->pai->direita) && n->pai == g->direita.*/
        rotacionar_esquerda(g);
    }
}
```

## Representação Visual (Antes e Depois da Alteração)

_Legenda para as cores:_ `(N)` para nós Negros e `(R)` para nós Rubros. Os triângulos representam subárvores.

```text
       Antes da Alteração                        Depois da Alteração
       
             (N) G                                     (N) P
            /     \                                   /     \
        P (R)     (N) U                           N (R)     (R) G
        /   \     /   \                           /   \     /   \
    N (R)    ▲   ▲     ▲                         ▲     ▲   ▲     (N) U
    /   \                                                        /   \
   ▲     ▲                                                      ▲     ▲
```

Com isso terminamos de transcrever os 5 casos de inserção da Árvore Rubro-Negra. Você gostaria de ajuda para criar um arquivo `.c` completo unificando todas as funções de inserção que analisamos?