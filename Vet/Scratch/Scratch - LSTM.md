---
tags:
  - deep-learning
  - rnn
  - lstm
---

# LSTM (*Long Short-Term Memory*)

A **LSTM** é uma evolução direta da [[Scratch - RNN|RNN simples]] criada para resolver o problema de **memória curta (*Vanishing Gradient*)** em sequências longas.

Tudo o que você viu em [[Scratch - RNN|RNN]] sobre *unrolling*, arquiteturas (*Many-to-One*, *Many-to-Many*, *Seq2Seq*) e *BPTT* continua valendo exatamente igual — o que muda é **o que acontece dentro da célula**.

---

## 1. A ideia central: duas memórias + portões ($\sigma$)

Em vez de apenas um estado oculto $h_t$, a LSTM mantém **dois caminhos paralelos**:
- **Cell State ($c_t$ — memória de longo prazo):** funciona como uma **via expressa** no topo da célula, carregando informações importantes por dezenas ou centenas de passos com mínimas alterações.
- **Hidden State ($h_t$ — memória de curto prazo / saída):** é uma versão filtrada de $c_t$ usada no passo atual (e para gerar $y_t$).

Para decidir o que apagar, guardar ou expor, a LSTM usa **3 portões (*gates*)** com função **sigmoide** $\sigma(z) \in (0, 1)$:
- $\sigma \approx 0$ $\rightarrow$ **fecha o portão** (bloqueia / apaga aquela informação);
- $\sigma \approx 1$ $\rightarrow$ **abre o portão** (deixa a informação passar integralmente).

---

## 2. Anatomia interna e equações da célula LSTM

![[assets/lstm-01-celula.svg]]

- **Cores:** ciano = *Cell State* ($c_t$), roxo = *Hidden State* ($h_t$), azul = entrada ($x_t$), laranja = portões ($\sigma$), escuro = $\tanh$.
- **Notação $[h_{t-1}, x_t]$:** representa a concatenação dos dois vetores; matematicamente, $W \cdot [h_{t-1}, x_t] + b$ é equivalente a $W_{hh} \cdot h_{t-1} + W_{xh} \cdot x_t + b$.

### Os 4 passos dentro da célula no instante $t$:

1. **Portão de Esquecimento (*Forget Gate* — $f_t$):** decide o que **apagar** da memória antiga $c_{t-1}$:
$$f_t = \sigma\left(W_f \cdot [h_{t-1}, x_t] + b_f\right)$$

2. **Portão de Entrada (*Input Gate* — $i_t$) + Candidato ($\tilde{c}_t$):** decide **quanta** informação nova entra e **qual** conteúdo novo será proposto:
$$i_t = \sigma\left(W_i \cdot [h_{t-1}, x_t] + b_i\right)$$
$$\tilde{c}_t = \tanh\left(W_c \cdot [h_{t-1}, x_t] + b_c\right)$$

3. **Atualização da memória de longo prazo (*Cell State* — $c_t$):** esquece parte do passado e **soma** a informação nova ($\odot$ = multiplicação elemento a elemento):
$$c_t = f_t \odot c_{t-1} + i_t \odot \tilde{c}_t$$

4. **Portão de Saída (*Output Gate* — $o_t$) e novo estado oculto ($h_t$):** filtra $c_t$ (comprimido por $\tanh$) para produzir $h_t$:
$$o_t = \sigma\left(W_o \cdot [h_{t-1}, x_t] + b_o\right)$$
$$h_t = o_t \odot \tanh(c_t)$$

*(Quando a tarefa precisa de predição no passo $t$, calcula-se $y_t = \text{ativação}(W_{hy} \cdot h_t + b_y)$ exatamente como na [[Scratch - RNN|RNN]].)*

---

## 3. Por que a LSTM resolve o *Vanishing Gradient*?

![[assets/lstm-02-via-expressa-gradiente.svg]]

- Na **RNN simples**, o gradiente precisa atravessar repetidamente $W_{hh}^T$ e $\tanh'$ a cada passo $t$, encolhendo rapidamente.
- Na **LSTM**, a atualização de $c_t$ é **aditiva** ($c_t = f_t \odot c_{t-1} + i_t \odot \tilde{c}_t$). No BPTT, a derivada direta ao longo do *Cell State* é simplesmente:
$$\frac{\partial c_t}{\partial c_{t-1}} = f_t$$
- Quando a rede aprende a manter o *Forget Gate* aberto ($f_t \approx 1$) para uma informação importante, o gradiente atravessa dezenas de passos **praticamente intacto**, sem multiplicar por $W_{hh}$ nem saturar em $\tanh$.

---

## 4. Limitações da LSTM (e próximos passos)

- **Custo computacional:** possui **4 blocos de matrizes** ($W_f, W_i, W_c, W_o$) — cerca de **4× mais parâmetros** que uma RNN simples do mesmo tamanho $\rightarrow$ versão mais leve em [[Scratch - GRU|GRU]].
- **Ainda é sequencial no tempo:** como $c_t$ e $h_t$ dependem do passo $t-1$, continua difícil paralelizar na GPU em sequências muito longas $\rightarrow$ superado por [[Transformers]].
