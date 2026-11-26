---
banner: "![[Pasted image 20260215205950.png]]"
---
---

````ad-quote
title:

##### **01 ) -** Os Pilares do Tidy Data

```ad-quote
title:
<p align="justify">Para entender Tidy Data (ou dados arrumados), o segredo não é apenas olhar para a tabela, mas entender a relação entre variáveis, observações e valores. O conceito, popularizado por Hadley Wickham, dita que um dataset está arrumado quando facilita a análise e a visualização.</p>
```

![[Pasted image 20260324131005.png]]

```ad-quote
title:
Para que um dado seja considerado tidy, ele deve seguir regras rígidas para sua estrutura. Cada variável deve possuir sua própria coluna. Cada observação (ou caso) deve possuir sua própria linha. Cada valor deve possuir sua própria célula.
```

````

---

> [!done] _New_

---

````ad-quote
title:

##### **02 ) -** Exemplo Prático: Formato Wide vs Long

```ad-quote
title:
<p align="justify">Vamos imaginar que estamos monitorando o crescimento de três plantas sob condições diferentes. Abaixo, veremos como os dados podem ser estruturados de forma espalhada e como reorganizá-los corretamente.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) O Formato Bagunçado - Wide Format
```

```ad-quote
title:
Este formato é muito comum em planilhas porque é fácil para humanos lerem, mas é péssimo para algoritmos de busca e gráficos. Os nomes das colunas (Adubo_A e Adubo_B) são, na verdade, valores da variável Tipo de Adubo. As alturas estão espalhadas em duas colunas diferentes, quando deveriam ser uma única variável Altura.
```

```Plaintext
  ID_Planta  Adubo_A (cm)  Adubo_B (cm)
        101          15.5          18.2
        102          14.8          17.5
        103          16.0          19.1
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) O Formato Arrumado - Long Format
```

```ad-quote
title:
Aplicamos uma transformação para reorganizar os dados seguindo os três pilares. A primeira coluna é o identificador da planta, a segunda é a variável independente e a terceira é a variável dependente. Desta forma, criar um gráfico comparando a média de altura por adubo se torna direto, bastando informar aos eixos quais colunas utilizar.
```

```Plaintext
  ID_Planta  Tipo_Adubo  Altura_cm
        101     Adubo_A       15.5
        102     Adubo_A       14.8
        103     Adubo_A       16.0
        101     Adubo_B       18.2
        102     Adubo_B       17.5
        103     Adubo_B       19.1
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **03 ) -** Métodos de Transformação

```ad-quote
title:
<p align="justify">Para demonstrar a versatilidade das ferramentas de manipulação de dados, vamos utilizar um conjunto sintético. O objetivo é transformar a estrutura onde os tipos de adubo são colunas para uma estrutura tidy, onde o adubo é uma variável em uma única coluna.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) O Método melt()
```

```ad-quote
title:
É a forma mais explícita. Você define a coluna de identificação que fica parada (ID_Planta) e quais colunas vão derreter (Adubo_A e Adubo_B).
```

```python
import pandas as pd

dados_baguncados = pd.DataFrame({
    'ID_Planta': [101, 102, 103],
    'Adubo_A': [15.5, 14.8, 16.0],
    'Adubo_B': [18.2, 17.5, 19.1]
})

df_melt = dados_baguncados.melt(
    id_vars=['ID_Planta'],
    var_name='Adubo',
    value_name='Altura'
)
print(df_melt)
```

```ad-quote
title:
###### Output esperado:
```

```Plaintext
  ID_Planta    Adubo  Altura
0       101  Adubo_A    15.5
1       102  Adubo_A    14.8
2       103  Adubo_A    16.0
3       101  Adubo_B    18.2
4       102  Adubo_B    17.5
5       103  Adubo_B    19.1
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) O Método stack()
```

```ad-quote
title:
O stack foca no índice. Para que a coluna de identificação não seja esmagada junto com as outras, nós a transformamos em índice antes da operação.
```

```python
# Transformamos o ID em índice e empilhamos o resto
df_stack = dados_baguncados.set_index('ID_Planta').stack().reset_index()

# Renomeamos as colunas que são geradas automaticamente
df_stack.columns = ['ID_Planta', 'Adubo', 'Altura']
```
````

````ad-quote
title:

```ad-quote
title:
##### C ) O Método wide_to_long()
```

```ad-quote
title:
Este método é excelente quando as colunas seguem o padrão Prefixo_Sufixo. No caso exemplificado, o prefixo é Adubo e o sufixo é a letra indicativa. Ele precisa de um separador claro para identificar a raiz da coluna.
```

```python
# Identifica 'Adubo' como o tronco (stub) da coluna
df_wtl = pd.wide_to_long(
    dados_baguncados,
    stubnames='Adubo',
    i='ID_Planta',
    j='Tipo',
    sep='_',
    suffix='\w+'
).reset_index()
```
````

````ad-quote
title:

```ad-quote
title:
##### D ) O Método explode()
```

```ad-quote
title:
Para usar o explode, os dados precisariam estar agrupados em uma lista dentro da célula. O método expande a lista para que cada valor ganhe sua própria linha.
```

```python
# Criando uma versão onde os adubos estão em uma lista
df_lista = pd.DataFrame({
    'ID_Planta': [101, 102, 103],
    'Alturas': [[15.5, 18.2], [14.8, 17.5], [16.0, 19.1]]
})

# Explodimos a lista para separação em linhas
df_exploded = df_lista.explode('Alturas')
```
````

---

> [!done] _New_

---

````ad-quote
title:

##### **04 ) -** Oposto Estrutural: pivot() vs melt()

```ad-quote
title:
<p align="justify">Para entender a diferença, pense neles como ações inversas. O melt estica a tabela para baixo, enquanto o pivot alarga a tabela para os lados.</p>
```
````

````ad-quote
title:

```ad-quote
title:
##### A ) O Ponto de Partida e o melt()
```

```ad-quote
title:
Imagine que você tem os batimentos cardíacos de dois atletas registrados em colunas de Manhã e Noite. O formato é largo e comum, mas não é tidy. O melt pega os cabeçalhos das colunas de período e os transforma em uma única coluna de categorias, empilhando os batimentos numéricos.
```

```Plaintext
  Atleta  Período  BPM
   André    Manhã   70
    João    Manhã   72
   André    Noite   85
    João    Noite   90
```
````

````ad-quote
title:

```ad-quote
title:
##### B ) O Retorno com o pivot()
```

```ad-quote
title:
O pivot faz exatamente o contrário. Ele pega os nomes que estão dentro de uma coluna e os transforma em novos cabeçalhos, preenchendo as células com os valores correspondentes. Este formato é excelente para comparação visual rápida ou cálculos de subtração direta.
```

```Plaintext
  Atleta  Manhã  Noite
   André     70     85
    João     72     90
```
````

````ad-quote
title:

```ad-quote
title:
##### C ) Erros Comuns e Agregações
```

```ad-quote
title:
Se você tentar usar o pivot em uma tabela que tem duas medições para o mesmo período do mesmo atleta, ocorrerá um erro, pois o algoritmo não saberá qual valor manter na célula. Nesses casos, a solução é o pivot_table, que calcula a média ou a soma desses valores automaticamente.
```
````

---