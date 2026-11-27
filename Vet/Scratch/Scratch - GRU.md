---
tags:
  - deep-learning
  - rnn
  - gru
---

# GRU (*Gated Recurrent Unit*)

A **GRU** é uma simplificação da [[Scratch - LSTM|LSTM]] (proposta em 2014) que resolve o *vanishing gradient* da [[Scratch - RNN|RNN simples]] com **menos portões e menos parâmetros**, mantendo desempenho muito parecido na prática.

---

## 1. O que muda em relação à LSTM?

- **Unifica a memória:** elimina o *Cell State* ($c_t$) separado — tudo fica em um **único estado $h_t$**.
- **Apenas 2 portões** (em vez de 3):
  - **Portão de Atualização (*Update Gate* — $z_t$):** faz o papel combinado do *Forget* e do *Input Gate* da LSTM. Ele decide a proporção entre **manter o passado** $(1 - z_t)$ e **aceitar o novo** $(z_t)$.
  - **Portão de Reset (*Reset Gate* — $r_t$):** decide quanto da memória anterior $h_{t-1}$ deve ser **ignorado** ao propor o novo estado candidato $\tilde{h}_t$.

---

## 2. Anatomia interna e equações da célula GRU

![[assets/gru-01-celula.svg]]

- **Cores:** roxo = memória ($h_t$), azul = entrada ($x_t$), laranja = portões ($\sigma$), escuro = $\tanh$.

### Os 4 passos dentro da célula no instante $t$:

1. **Portão de Atualização (*Update Gate* — $z_t$):**
$$z_t = \sigma\left(W_z \cdot [h_{t-1}, x_t] + b_z\right)$$

2. **Portão de Reset (*Reset Gate* — $r_t$):**
$$r_t = \sigma\left(W_r \cdot [h_{t-1}, x_t] + b_r\right)$$

3. **Estado candidato ($\tilde{h}_t$):** usa $r_t$ para filtrar o quanto do passado $h_{t-1}$ influencia a nova proposta:
$$\tilde{h}_t = \tanh\left(W_h \cdot [r_t \odot h_{t-1}, x_t] + b_h\right)$$

4. **Atualização final da memória ($h_t$):** interpolação direta entre o passado e o candidato:
$$h_t = (1 - z_t) \odot h_{t-1} + z_t \odot \tilde{h}_t$$

> [!tip] Intuição rápida da equação final
> - Se $z_t \approx 0 \implies h_t \approx h_{t-1}$ (copia a memória anterior intacta — via expressa do gradiente!).
> - Se $z_t \approx 1 \implies h_t \approx \tilde{h}_t$ (substitui pela informação nova).

*(A saída $y_t$, quando usada no passo $t$, continua sendo $y_t = \text{ativação}(W_{hy} \cdot h_t + b_y)$.)*

---

## 3. Comparativo: RNN vs. LSTM vs. GRU

| Característica | [[Scratch - RNN\|RNN (Elman)]] | [[Scratch - LSTM\|LSTM]] | GRU |
| :--- | :---: | :---: | :---: |
| **Estados internos** | 1 ($h_t$) | 2 ($h_t$ e $c_t$) | 1 ($h_t$) |
| **Número de portões ($\sigma$)** | 0 | 3 ($f_t, i_t, o_t$) | 2 ($z_t, r_t$) |
| **Parâmetros relativos** | $1\times$ | $\approx 4\times$ | $\approx 3\times$ |
| **Memória de longo prazo** | Fraca (*vanishing gradient*) | Forte | Forte |
| **Velocidade de treino** | Mais rápida | Mais lenta | Intermediária (~25% mais leve que LSTM) |
| **Quando escolher** | Didática / sequências bem curtas | Sequências longas e datasets grandes | Ótimo padrão inicial; datasets menores ou quando precisa de velocidade |
