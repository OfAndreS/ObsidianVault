---
tags:
  - deep-learning
  - rnn
---

# Redes Neurais Recorrentes (RNN)

## As duas equações fundamentais (Rede de Elman)

Em cada instante de tempo $t$ de uma sequência, a célula RNN faz dois passos:

1. **Atualiza a memória (estado oculto $h_t$):**
$$h_t = \tanh(W_{xh} \cdot x_t + W_{hh} \cdot h_{t-1} + b_h)$$

2. **Calcula a saída ($y_t$):**
$$y_t = \text{ativação}(W_{hy} \cdot h_t + b_y)$$

---

## 1. Anatomia interna da célula

![[assets/rnn-01-anatomia-celula.svg]]

- **Cores nos diagramas:** azul = entrada ($x_t$), roxo = memória ($h_t$), laranja = pesos e vieses ($W, b$), verde = saída ($y_t$).
- A **memória anterior** ($h_{t-1}$) e a **entrada atual** ($x_t$) são multiplicadas por $W_{hh}$ e $W_{xh}$, somadas ao viés $b_h$ e comprimidas pela $\tanh$.
- O novo estado $h_t$ **se bifurca**: uma cópia segue para o próximo passo ($t+1$) e a outra sobe para gerar a saída $y_t$.
- **Ativação da saída ($y_t$):** varia conforme o problema — *Softmax* (multiclasse / próxima palavra), *Sigmoid* (classificação binária) ou *Linear* (regressão).

---

## 2. Desenrolando no tempo (*Unrolling*)

![[assets/rnn-02-unrolling-tempo.svg]]

- O loop recorrente da forma dobrada equivale a aplicar **a mesma célula repetidamente** ao longo da sequência ($t = 1, 2, 3\dots$), partindo de um estado inicial $h_0$ (normalmente um vetor de zeros).
- **Compartilhamento de pesos (*Parameter Sharing*):** as matrizes $W_{xh}, W_{hh}, W_{hy}$ e vieses $b_h, b_y$ são **idênticos em todos os passos $t$**. O que muda a cada passo é apenas a entrada $x_t$ e a memória acumulada $h_t$.
- **Memória de curto prazo vs. aprendizado:** $h_t$ guarda apenas o contexto da sequência atual (zera em cada novo exemplo); o que a rede realmente aprende são os pesos $W$ e vieses $b$.

---

## 3. Papel da $\tanh$ e dimensões das matrizes

![[assets/rnn-03-tanh-e-dimensoes.svg]]

### Por que usar $\tanh$ na memória?
- **Controla a escala:** mantém $h_t \in (-1, +1)$ mesmo após dezenas de multiplicações por $W_{hh}$.
- **Centrada em zero:** permite valores positivos e negativos (reforçar ou inibir informações na memória).
- **Saturação (ponto de atenção):** nas pontas ($|z| > 2{,}5$), a derivada $\tanh'(z) = 1 - \tanh^2(z) \approx 0$, o que contribui para o *vanishing gradient* em sequências longas.

### Como ler os subscritos e dimensões
Regra prática: a dimensão de cada matriz é sempre $(\text{destino} \times \text{origem})$. No exemplo do diagrama ($\dim(x)=3,\ \dim(h)=4,\ \dim(y)=2$):
- **$W_{xh}$** ($4 \times 3$): projeta a entrada $x_t$ para o espaço da memória $h_t$.
- **$W_{hh}$** ($4 \times 4$): transforma a memória anterior $h_{t-1}$ no próximo estado.
- **$W_{hy}$** ($2 \times 4$): projeta a memória $h_t$ para o formato da saída $y_t$.

---

## 4. Exemplo numérico completo (passo a passo)

Vamos executar manualmente **2 passos de tempo** ($t=1$ e $t=2$) usando exatamente as duas equações da célula do tópico 1, com **Softmax** como função de ativação da saída.

### Configuração inicial
Dimensões: $\dim(x) = 2,\ \dim(h) = 2,\ \dim(y) = 2$.

- **Pesos e vieses compartilhados** (iguais em $t=1$ e $t=2$):
$$
W_{xh} = \begin{bmatrix} 0{,}5 & -0{,}4 \\ 0{,}8 & 0{,}6 \end{bmatrix}, \quad
W_{hh} = \begin{bmatrix} 0{,}3 & -0{,}2 \\ 0{,}4 & 0{,}5 \end{bmatrix}, \quad
b_h = \begin{bmatrix} 0{,}1 \\ -0{,}1 \end{bmatrix}
$$
$$
W_{hy} = \begin{bmatrix} 0{,}6 & -0{,}5 \\ -0{,}3 & 0{,}8 \end{bmatrix}, \quad
b_y = \begin{bmatrix} 0{,}0 \\ 0{,}2 \end{bmatrix}
$$

- **Memória inicial e sequência de entrada:**
$$
h_0 = \begin{bmatrix} 0 \\ 0 \end{bmatrix}, \quad
x_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, \quad
x_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}
$$

---

### Passo $t = 1$

1. **Atualização da memória ($h_1$):**
$$
W_{xh} \cdot x_1 = \begin{bmatrix} 0{,}5 & -0{,}4 \\ 0{,}8 & 0{,}6 \end{bmatrix} \begin{bmatrix} 1 \\ 0 \end{bmatrix} = \begin{bmatrix} 0{,}5 \\ 0{,}8 \end{bmatrix}, \qquad
W_{hh} \cdot h_0 = \begin{bmatrix} 0{,}3 & -0{,}2 \\ 0{,}4 & 0{,}5 \end{bmatrix} \begin{bmatrix} 0 \\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}
$$
$$
z_1 = W_{xh} \cdot x_1 + W_{hh} \cdot h_0 + b_h = \begin{bmatrix} 0{,}5 \\ 0{,}8 \end{bmatrix} + \begin{bmatrix} 0 \\ 0 \end{bmatrix} + \begin{bmatrix} 0{,}1 \\ -0{,}1 \end{bmatrix} = \begin{bmatrix} 0{,}6 \\ 0{,}7 \end{bmatrix}
$$
$$
h_1 = \tanh(z_1) = \begin{bmatrix} \tanh(0{,}6) \\ \tanh(0{,}7) \end{bmatrix} \approx \begin{bmatrix} 0{,}5370 \\ 0{,}6044 \end{bmatrix}
$$

2. **Cálculo da saída ($y_1$):**
$$
o_1 = W_{hy} \cdot h_1 + b_y = \begin{bmatrix} 0{,}6 & -0{,}5 \\ -0{,}3 & 0{,}8 \end{bmatrix} \begin{bmatrix} 0{,}5370 \\ 0{,}6044 \end{bmatrix} + \begin{bmatrix} 0{,}0 \\ 0{,}2 \end{bmatrix}
= \begin{bmatrix} 0{,}3222 - 0{,}3022 \\ -0{,}1611 + 0{,}4835 \end{bmatrix} + \begin{bmatrix} 0{,}0 \\ 0{,}2 \end{bmatrix}
= \begin{bmatrix} 0{,}0200 \\ 0{,}5224 \end{bmatrix}
$$
$$
y_1 = \text{softmax}(o_1) = \frac{1}{e^{0{,}0200} + e^{0{,}5224}} \begin{bmatrix} e^{0{,}0200} \\ e^{0{,}5224} \end{bmatrix}
\approx \frac{1}{1{,}0202 + 1{,}6861} \begin{bmatrix} 1{,}0202 \\ 1{,}6861 \end{bmatrix}
\approx \begin{bmatrix} 0{,}3770 \\ 0{,}6230 \end{bmatrix}
$$

---

### Passo $t = 2$ (agora com a memória $h_1$ ativa!)

1. **Atualização da memória ($h_2$):**
$$
W_{xh} \cdot x_2 = \begin{bmatrix} 0{,}5 & -0{,}4 \\ 0{,}8 & 0{,}6 \end{bmatrix} \begin{bmatrix} 0 \\ 1 \end{bmatrix} = \begin{bmatrix} -0{,}4 \\ 0{,}6 \end{bmatrix}
$$
$$
W_{hh} \cdot h_1 = \begin{bmatrix} 0{,}3 & -0{,}2 \\ 0{,}4 & 0{,}5 \end{bmatrix} \begin{bmatrix} 0{,}5370 \\ 0{,}6044 \end{bmatrix}
= \begin{bmatrix} 0{,}1611 - 0{,}1209 \\ 0{,}2148 + 0{,}3022 \end{bmatrix}
= \begin{bmatrix} 0{,}0402 \\ 0{,}5170 \end{bmatrix}
$$
$$
z_2 = W_{xh} \cdot x_2 + W_{hh} \cdot h_1 + b_h
= \begin{bmatrix} -0{,}4 \\ 0{,}6 \end{bmatrix} + \begin{bmatrix} 0{,}0402 \\ 0{,}5170 \end{bmatrix} + \begin{bmatrix} 0{,}1 \\ -0{,}1 \end{bmatrix}
= \begin{bmatrix} -0{,}2598 \\ 1{,}0170 \end{bmatrix}
$$
$$
h_2 = \tanh(z_2) = \begin{bmatrix} \tanh(-0{,}2598) \\ \tanh(1{,}0170) \end{bmatrix} \approx \begin{bmatrix} -0{,}2541 \\ 0{,}7686 \end{bmatrix}
$$

2. **Cálculo da saída ($y_2$):**
$$
o_2 = W_{hy} \cdot h_2 + b_y = \begin{bmatrix} 0{,}6 & -0{,}5 \\ -0{,}3 & 0{,}8 \end{bmatrix} \begin{bmatrix} -0{,}2541 \\ 0{,}7686 \end{bmatrix} + \begin{bmatrix} 0{,}0 \\ 0{,}2 \end{bmatrix}
= \begin{bmatrix} -0{,}1525 - 0{,}3843 \\ 0{,}0762 + 0{,}6149 \end{bmatrix} + \begin{bmatrix} 0{,}0 \\ 0{,}2 \end{bmatrix}
= \begin{bmatrix} -0{,}5368 \\ 0{,}8911 \end{bmatrix}
$$
$$
y_2 = \text{softmax}(o_2) = \frac{1}{e^{-0{,}5368} + e^{0{,}8911}} \begin{bmatrix} e^{-0{,}5368} \\ e^{0{,}8911} \end{bmatrix}
\approx \frac{1}{0{,}5846 + 2{,}4378} \begin{bmatrix} 0{,}5846 \\ 2{,}4378 \end{bmatrix}
\approx \begin{bmatrix} 0{,}1934 \\ 0{,}8066 \end{bmatrix}
$$

---

### Cálculo da Loss (*Cross-Entropy*)

Suponha um treino **Many-to-One** cujo gabarito ao final da sequência ($t=2$) seja a classe 2, $\hat{y}_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$:

$$
L = -\sum_{i=1}^{2} \hat{y}_{2,i}\,\ln(y_{2,i}) = -\ln(0{,}8066) \approx 0{,}2150
$$

*(No caso **Many-to-Many**, basta calcular uma Loss em cada passo e somar: $L = L_1 + L_2$.)*

---

### Atualização dos pesos via BPTT (visão simplificada)

1. **Erro na saída ($t = 2$):** para *Softmax + Cross-Entropy*, o erro inicial é simplesmente a diferença entre predição e gabarito:
$$
\text{erro} = y_2 - \hat{y}_2 = \begin{bmatrix} 0{,}1934 \\ 0{,}8066 \end{bmatrix} - \begin{bmatrix} 0 \\ 1 \end{bmatrix} = \begin{bmatrix} +0{,}1934 \\ -0{,}1934 \end{bmatrix}
$$
*(Sinal positivo na classe 1 indica "reduzir essa pontuação"; negativo na classe 2 indica "aumentar essa pontuação".)*

2. **Regra de atualização (BPTT):** esse erro volta no tempo ($t=2 \to t=1$), calcula o ajuste sugerido em cada passo e **soma** as contribuições para atualizar cada matriz compartilhada com taxa de aprendizado $\eta = 0{,}1$:
$$
W_{\text{novo}} = W - \eta \sum_{t=1}^{2} \left.\frac{\partial L}{\partial W}\right|_t
$$

3. **Exemplo em uma matriz ($W_{hy}$) e resultado:**
$$
W_{hy} = \begin{bmatrix} 0{,}6000 & -0{,}5000 \\ -0{,}3000 & 0{,}8000 \end{bmatrix}
\quad \xrightarrow{\text{BPTT } (\eta=0{,}1)} \quad
W_{hy}^{\text{novo}} = \begin{bmatrix} 0{,}6049 & -0{,}5149 \\ -0{,}3049 & 0{,}8149 \end{bmatrix}
$$

> [!info] Efeito após 1 passo de atualização
> Aplicando a mesma ideia às demais matrizes ($W_{hh}, W_{xh}, b_h, b_y$) e rodando novamente a sequência $(x_1, x_2)$:
> - A confiança na classe correta sobe de **$80{,}66\% \to 82{,}52\%$**;
> - A Loss cai de **$0{,}2150 \to 0{,}1921$**.

---

## 5. Principais arquiteturas de RNN

### 5.1 One-to-Many ($1 \to N$)
*Exemplos: gerar legenda de imagem, geração de música ou texto a partir de uma entrada inicial.*

![[assets/rnn-04a-one-to-many.svg]]

- **Atualização da memória:**
  - No passo inicial ($t = 1$):
    $$h_1 = \tanh(W_{xh} \cdot x_1 + W_{hh} \cdot h_0 + b_h)$$
  - Nos passos seguintes ($t = 2, \dots, T$), sem retroalimentação de saída:
    $$h_t = \tanh(W_{hh} \cdot h_{t-1} + b_h)$$
  - Ou na forma **autoregressiva** (setas pontilhadas no diagrama, onde $y_{t-1}$ vira a entrada seguinte):
    $$h_t = \tanh(W_{xh} \cdot y_{t-1} + W_{hh} \cdot h_{t-1} + b_h)$$
- **Ativação / Saída** (em todos os passos $t = 1, \dots, T$):
  $$y_t = \text{ativação}(W_{hy} \cdot h_t + b_y)$$
- **Loss e BPTT:** a Loss é a soma de todas as saídas ($L = \sum_{t=1}^{T} L_t$). No BPTT, os erros voltam por toda a sequência somando gradientes em $W_{hy}$ e $W_{hh}$, e convergem até $t=1$ para atualizar $W_{xh}$ (onde entrou $x_1$).

---

### 5.2 Many-to-One ($N \to 1$)
*Exemplos: análise de sentimento, detecção de spam, classificação de séries temporais.*

![[assets/rnn-04b-many-to-one.svg]]

- **Atualização da memória** (em todos os passos $t = 1, \dots, T$):
  $$h_t = \tanh(W_{xh} \cdot x_t + W_{hh} \cdot h_{t-1} + b_h)$$
- **Ativação / Saída** (calculada **apenas** no último passo $t = T$):
  $$y_T = \text{ativação}(W_{hy} \cdot h_T + b_y)$$
- **Loss e BPTT:** existe uma **única Loss no final** ($L = L_T$). No BPTT, $W_{hy}$ recebe gradiente só de $t=T$, e uma única corrente de erro volta de $h_T \to \dots \to h_1$ para ajustar $W_{hh}$ e $W_{xh}$ (por isso sofre mais com *vanishing gradient* no início da sequência).

---

### 5.3 Many-to-Many Sincronizado ($N \to N$)
*Exemplos: classificação palavra por palavra (POS tagging / NER), previsão da próxima palavra a cada passo.*

![[assets/rnn-04c-many-to-many-sync.svg]]

- **Atualização da memória** (em todos os passos $t = 1, \dots, T$):
  $$h_t = \tanh(W_{xh} \cdot x_t + W_{hh} \cdot h_{t-1} + b_h)$$
- **Ativação / Saída** (em todos os passos $t = 1, \dots, T$):
  $$y_t = \text{ativação}(W_{hy} \cdot h_t + b_y)$$
- **Loss e BPTT:** a Loss total é a soma de todos os passos ($L = \sum_{t=1}^{T} L_t$). No BPTT, $W_{hy}$ soma gradientes de todo $t$, e cada célula $h_t$ recebe a **soma do erro local ($L_t$) + o erro que voltou do futuro ($h_{t+1}$)**.

---

### 5.4 Many-to-Many Seq2Seq / Encoder–Decoder ($N \to M$)
*Exemplos: tradução automática, resumo de texto (entrada e saída com tamanhos diferentes $T_x \neq T_y$).*

![[assets/rnn-04d-seq2seq.svg]]

- **Encoder** (lê a entrada $t = 1, \dots, T_x$ sem gerar saída):
  $$h_t = \tanh\left(W_{xh}^{(\text{enc})} \cdot x_t + W_{hh}^{(\text{enc})} \cdot h_{t-1} + b_h^{(\text{enc})}\right)$$
- **Vetor de contexto** (conecta Encoder ao Decoder):
  $$c = h_{T_x} \implies s_0 = c$$
- **Decoder** (gera a saída $t' = 1, \dots, T_y$, partindo de $y_0 = \text{<BOS>}$):
  $$s_{t'} = \tanh\left(W_{ys}^{(\text{dec})} \cdot y_{t'-1} + W_{ss}^{(\text{dec})} \cdot s_{t'-1} + b_s^{(\text{dec})}\right)$$
  $$y_{t'} = \text{ativação}\left(W_{sy}^{(\text{dec})} \cdot s_{t'} + b_y^{(\text{dec})}\right)$$
- **Loss e BPTT:** a Loss é calculada **apenas nas saídas do Decoder** ($L = \sum_{t'=1}^{T_y} L_{t'}$). O BPTT volta primeiro pelo Decoder inteiro ($s_{T_y} \to \dots \to s_1$), atravessa o vetor de contexto $c$ e segue voltando pelo Encoder ($h_{T_x} \to \dots \to h_1$), ajustando os dois blocos juntos.

> [!note] Outras variações estruturais
> Sobre qualquer uma dessas 4 topologias, pode-se aplicar **RNN Bidirecional (Bi-RNN)** (lê nos dois sentidos), **RNN Profunda (*Stacked*)** (várias camadas empilhadas) ou trocar a célula de Elman por **LSTM / GRU**.

---

## 6. Backpropagation (BP) vs. Backpropagation Through Time (BPTT)

![[assets/rnn-05-bp-vs-bptt.svg]]

**BPTT** não é um algoritmo diferente do Backpropagation tradicional — é o **próprio Backpropagation aplicado à RNN desenrolada no tempo**, somando os gradientes dos pesos compartilhados:

$$W_{hh} \leftarrow W_{hh} - \eta \sum_{t=1}^{T} \left.\frac{\partial L}{\partial W_{hh}}\right|_t$$

| Aspecto | Backpropagation (BP — MLP) | BPTT (RNN) |
| :--- | :--- | :--- |
| **Direção da volta do erro** | Espacial (camada por camada) | Temporal ($t = T \to T-1 \to \dots \to 1$) |
| **Pesos** | Diferentes em cada camada ($W_1, W_2, W_3$) | **Compartilhados** em todos os passos ($W_{xh}, W_{hh}, W_{hy}$) |
| **Cálculo do gradiente** | Cada matriz recebe 1 gradiente próprio | **Soma** os gradientes de todos os passos $t$ antes de atualizar |
| **Profundidade efetiva** | Fixa (número de camadas da rede) | Dinâmica (igual ao tamanho $T$ da sequência) |
| **Principal desafio** | Mais estável (matrizes distintas + ReLU) | Multiplicar a *mesma* $W_{hh}$ $T$ vezes $\to$ **Vanishing / Exploding Gradient** |

> [!tip] Truques práticos no BPTT
> - **Truncated BPTT:** em sequências longas, o gradiente só volta uma janela fixa de $k$ passos no tempo para economizar memória.
> - **Gradient Clipping:** limita a norma máxima do gradiente para impedir explosão (*Exploding Gradient*).

---

## 7. Limitações da RNN simples (e o que veio depois)

- **Memória curta (*Vanishing / Exploding Gradient*):** em sequências longas, o gradiente enfraquece (ou explode) ao voltar no tempo por $W_{hh}$ e $\tanh'$, dificultando aprender dependências distantes $\rightarrow$ resolvido com portões em [[Scratch - LSTM|LSTM]] e [[Scratch - GRU|GRU]].
- **Gargalo do vetor de contexto ($c$):** em arquiteturas *Seq2Seq*, comprimir uma sequência longa inteira em um único vetor fixo $c = h_{T_x}$ faz perder detalhes do início $\rightarrow$ resolvido pelo mecanismo de [[Attention]].
- **Processamento estritamente sequencial:** como $h_t$ depende de $h_{t-1}$, não é possível processar todos os passos $t$ em paralelo na GPU durante o treino $\rightarrow$ superado pela arquitetura de [[Transformers]].
