
---

>[!quote] **Link:** [Learn to Build a Neural Network From Scratch](https://medium.com/@waadlingaadil/learn-to-build-a-neural-network-from-scratch-yes-really-cac4ca457efc)

---

````ad-quote
title:

##### **01 )** - A Arquitetura da Rede: O Projeto de um Cérebro Simples

```ad-quote
title:
<p align="justify">Para construir nossa rede neural, primeiro definimos sua <b>arquitetura</b>, que é como o projeto de um pequeno cérebro digital. Essa estrutura é organizada em camadas, onde cada camada tem uma função específica.</p>
```

```ad-quote
title:

###### **Os Componentes do Projeto**

**Camada de Entrada:** 
- É a porta da frente da rede. No nosso caso, possui um único neurônio (`I_1`) que recebe o dado inicial.

**Camada Oculta:** 
- É o centro de processamento. Esta é uma camada intermediária com dois neurônios (`O1_1`, `O1_2`) que recebem a informação da entrada e começam a transformá-la.

**Camada de Saída:** 
- É onde a decisão final é tomada. Ela contém um único neurônio (`O2_1`) que produz o resultado final da previsão.

**Pesos e Conexões:** 
- As conexões entre os neurônios são como caminhos neurais, e cada uma tem um "peso" associado (`w1_1`, `w1_2`, `w2_1`, `w2_2`). Esses pesos são os parâmetros mais importantes, pois controlam a força do sinal entre os neurônios e é exatamente isso que a rede ajusta para aprender.

```
````

![[Pasted image 20250810235917.png]]

-----

> [!example] ***New***

-----

````ad-quote
title:

##### **02 )** - Propagação Direta: O Fluxo do Pensamento

```ad-quote
title:
<p align="justify">Uma vez que a arquitetura está definida, a rede precisa de um processo para "pensar". Esse processo é a <b>Propagação Direta (Forward Propagation)</b>, onde a informação flui para a frente, da entrada até a saída.</p>
```

```ad-quote
title:

**Da Entrada para a Camada Oculta:** 
- O dado de entrada (`I_1`) é enviado para a camada oculta. Cada neurônio oculto multiplica o dado pelo seu peso de conexão (`w1_1`, `w1_2`) e soma um valor de *bias* (viés).

**Da Camada Oculta para a Saída:** 
- As saídas da camada oculta são então enviadas para a camada de saída. O neurônio de saída faz a mesma coisa: multiplica as informações recebidas pelos seus pesos (`w2_1`, `w2_2`), soma tudo e adiciona seu próprio bias.

<p align="justify">Em cada etapa, após a soma, o resultado passa por uma <b>Função de Ativação Sigmoide</b>. Pense nela como um "filtro" que decide a importância daquela informação, convertendo o resultado em um valor entre 0 e 1 antes de passá-lo adiante.</p>
```
````

![[Pasted image 20250810235805.png]]

-----

> [!example] ***New***

-----

````ad-quote
title:

##### **03 )** - Função de Custo: Medindo o Tamanho do Erro

```ad-quote
title:
Após a rede fazer sua previsão, precisamos de uma forma de avaliar o quão correta ela foi. Para isso, usamos uma <b>Função de Custo</b>. Ela compara a previsão da rede (`O2_1`) com a resposta correta (`OP_1`) e calcula uma "nota de erro".
```

```ad-quote
title:

###### **Usando o Erro Quadrático**

<p align="justify">Neste modelo, usamos a <b>Função do Erro Quadrático</b>.</p>
<p align="justify"><b>Intuição:</b> A fórmula calcula a diferença entre a previsão e o valor real e eleva o resultado ao quadrado. Isso tem um efeito importante: erros grandes são penalizados muito mais do que erros pequenos. É como um professor que dá uma penalidade muito maior por um erro grave, forçando a rede a evitar previsões muito distantes da realidade. O objetivo de todo o treinamento é ajustar os pesos para que essa nota de erro seja a menor possível.</p>
```
````

-----

>[!example] ***New***

-----

````ad-quote
title:

##### **04 )** - Backpropagation: Aprendendo com os Erros

```ad-quote
title:
<p align="justify">Ok, a função de custo nos deu uma nota de erro. E agora? A rede precisa saber como melhorar. O Backpropagation é o algoritmo que permite esse aprendizado.</p>
<p align="justify">Imagine a rede como uma equipe, onde cada neurônio contribuiu para o resultado final. O Backpropagation age como um gerente que, de trás para frente, investiga a contribuição de cada um para o erro.</p>
```

```ad-quote
title:

**1 ) - Calcular o Erro:** 
- Primeiro, o erro total na saída é calculado.


**2 ) - Propagar o Erro para Trás:** 
- O algoritmo começa na última camada e volta, distribuindo a "culpa" pelo erro total. Ele usa derivadas (a regra da cadeia) para calcular o quanto cada neurônio na camada anterior contribuiu para o erro.

**3 ) - Descobrir a Contribuição de Cada Peso:** 
- Ao fazer isso, o algoritmo descobre o <b>Gradiente</b> para cada peso. O gradiente é um valor que diz exatamente como ajustar aquele peso (se deve aumentar ou diminuir) para reduzir o erro geral.

<p align="justify">Ao final, temos um mapa que nos diz como ajustar cada "botão" (peso) da rede para melhorar o resultado.</p>
```
````

![[Pasted image 20250810235004.png]]

-----

> [!example] ***New***

-----

````ad-quote
title:

##### **05 )** - O Ciclo de Treinamento: A Prática Leva à Perfeição

```ad-quote
title:
<p align="justify">O treinamento de uma rede neural é um ciclo que une todos esses conceitos, repetido várias vezes para refinar o conhecimento da rede.</p>
```

```ad-quote
title:


**1) - Prever e Avaliar o Erro:**

- Primeiro, a rede recebe um dado e realiza uma previsão (processo conhecido como **Forward Pass**). Em seguida, o erro total dessa previsão é calculado por uma função de custo, que mede a sua imprecisão.
    

**2) - Propagar o Erro para Trás (Backpropagation):**

- O algoritmo investiga a "culpa" pelo erro, começando da última camada e retrocedendo. Ele utiliza derivadas para calcular o quanto cada peso na rede contribuiu para o erro total.
    

**3) - Descobrir a Contribuição e Ajustar os Pesos:**

- Ao fazer isso, o algoritmo descobre o **Gradiente** para cada peso. O gradiente é um valor que indica exatamente como ajustar o peso (se deve aumentar ou diminuir) para reduzir o erro. Com base nesse gradiente, os pesos são atualizados, usando uma **Taxa de Aprendizagem** (definida como 0.1) para controlar o tamanho desse ajuste.
    

Este ciclo se repete por várias **épocas**, permitindo que a rede melhore gradualmente até que o erro médio seja minimizado.
```
````

-----

```python
import numpy as np

class RedeNeuralSimples:
    """
    Uma implementação da rede neural simples descrita na imagem.
    - 1 neurônio de entrada
    - 1 camada oculta com 2 neurônios
    - 1 neurônio de saída
    """
    def __init__(self):
        # Inicializa os pesos com valores aleatórios pequenos
        # Camada 1 (entrada -> oculta)
        self.w1_1 = np.random.randn()
        self.w1_2 = np.random.randn()
        # Camada 2 (oculta -> saída)
        self.w2_1 = np.random.randn()
        self.w2_2 = np.random.randn()

        # Inicializa os biases (um para cada neurônio) com zero
        self.b1 = 0
        self.b2 = 0
        self.b_out = 0

    def _sigmoide(self, x):
        """Função de ativação sigmoide"""
        return 1 / (1 + np.exp(-x))

    def _derivada_sigmoide(self, x):
        """Derivada da função sigmoide"""
        return x * (1 - x)

    def forward(self, I_1):
        """Executa a Forward Propagation"""
        # Camada oculta
        # Nota: Guardamos os resultados (z e ativações) para usar no backpropagation
        self.z1 = (self.w1_1 * I_1) + self.b1
        self.a1 = self._sigmoide(self.z1) # Ativação do neurônio 1

        self.z2 = (self.w1_2 * I_1) + self.b2
        self.a2 = self._sigmoide(self.z2) # Ativação do neurônio 2

        # Camada de saída
        self.z_out = (self.a1 * self.w2_1) + (self.a2 * self.w2_2) + self.b_out
        self.y_previsto = self._sigmoide(self.z_out)

        return self.y_previsto

    def treinar(self, dados_treino, y_verdadeiros, epocas, taxa_aprendizado):
        """
        Executa o treinamento da rede usando forward propagation e backpropagation.
        """
        print(f"Iniciando treinamento por {epocas} épocas...")
        
        for epoca in range(epocas):
            # Para cada época, passamos por todos os dados de treino
            for I_1, y_verdadeiro in zip(dados_treino, y_verdadeiros):
                
                # --- 1. Forward Pass ---
                self.forward(I_1)
                
                # --- 2. Cálculo do Erro e Gradientes (Backpropagation) ---
                
                # Erro total
                erro = self.y_previsto - y_verdadeiro
                
                # Gradientes da camada de saída
                d_y_previsto = erro * self._derivada_sigmoide(self.y_previsto)
                
                grad_w2_1 = d_y_previsto * self.a1
                grad_w2_2 = d_y_previsto * self.a2
                grad_b_out = d_y_previsto
                
                # Propagar erro para a camada oculta
                erro_oculto_1 = d_y_previsto * self.w2_1
                erro_oculto_2 = d_y_previsto * self.w2_2
                
                # Gradientes da camada oculta
                d_a1 = erro_oculto_1 * self._derivada_sigmoide(self.a1)
                d_a2 = erro_oculto_2 * self._derivada_sigmoide(self.a2)
                
                grad_w1_1 = d_a1 * I_1
                grad_w1_2 = d_a2 * I_1
                grad_b1 = d_a1
                grad_b2 = d_a2

                # --- 3. Atualização dos Pesos e Biases ---
                self.w2_1 -= taxa_aprendizado * grad_w2_1
                self.w2_2 -= taxa_aprendizado * grad_w2_2
                self.b_out -= taxa_aprendizado * grad_b_out
                
                self.w1_1 -= taxa_aprendizado * grad_w1_1
                self.w1_2 -= taxa_aprendizado * grad_w1_2
                self.b1 -= taxa_aprendizado * grad_b1
                self.b2 -= taxa_aprendizado * grad_b2
            
            # Imprime o erro a cada 1000 épocas para acompanharmos o progresso
            if (epoca + 1) % 5000 == 0:
                erro_medio = np.mean(np.square(y_verdadeiros - self.prever(dados_treino)))
                print(f"Época {epoca + 1}/{epocas}, Erro Médio Quadrático: {erro_medio:.6f}")

    def prever(self, entradas):
        """Faz previsões para um conjunto de entradas."""
        previsoes = []
        for entrada in entradas:
            previsoes.append(self.forward(entrada))
        return np.array(previsoes)


# --- Exemplo de Uso ---

if __name__ == '__main__':
    # Criamos a instância da nossa rede
    minha_rede = RedeNeuralSimples()

    # Criamos um conjunto de dados simples.
    # A rede deve aprender a função "NÃO" (NOT gate):
    # Se a entrada for 0, a saída deve ser 1.
    # Se a entrada for 1, a saída deve ser 0.
    dados_treino = np.array([0, 1])
    y_verdadeiros = np.array([1, 0])

    # Treinamos a rede
    minha_rede.treinar(dados_treino=dados_treino, 
                       y_verdadeiros=y_verdadeiros, 
                       epocas=100000, 
                       taxa_aprendizado=0.1)

    # Testamos a rede com os dados de treino para ver se ela aprendeu
    print("\n--- Testando a rede após o treinamento ---")
    previsoes_finais = minha_rede.prever(dados_treino)

    for dado, previsao, real in zip(dados_treino, previsoes_finais, y_verdadeiros):
        print(f"Entrada: {dado}, Saída Prevista: {previsao:.4f}, Saída Real: {real}")
```

---
