

---

\documentclass{article}

% --- PREÂMBULO ---
\usepackage[utf8]{inputenc}
\usepackage[brazil]{babel}
\usepackage{amsmath} % Para ambientes de matriz como pmatrix
\usepackage{geometry}
\geometry{a4paper, margin=1in}

\title{Exemplo Detalhado de uma Operação de Convolução}
\author{Gemini}
\date{\today}

% --- INÍCIO DO DOCUMENTO ---
\begin{document}

\maketitle

O objetivo da convolução é aplicar um \textbf{filtro (Kernel)} sobre uma \textbf{imagem de entrada} para criar um \textbf{mapa de características (Saída)}. Este mapa de saída realça certas características da imagem, dependendo do que o kernel foi projetado para detectar.

Neste exemplo, usaremos um kernel que detecta \textbf{bordas verticais}.

\section*{Passo 1: Os Componentes}

Temos nossa imagem de entrada (uma matriz 5x5 de pixels em escala de cinza) e nosso kernel (uma matriz 3x3).

\subsection*{Imagem de Entrada (5x5)}
$$
\text{Imagem} = 
\begin{pmatrix}
 8 & 8 & 8 & 1 & 1 \\
 8 & 8 & 8 & 1 & 1 \\
 8 & 8 & 8 & 1 & 1 \\
 8 & 8 & 8 & 1 & 1 \\
 8 & 8 & 8 & 1 & 1
\end{pmatrix}
$$

\subsection*{Kernel (Filtro de Borda Vertical 3x3)}
Este kernel tem valores positivos na primeira coluna e negativos na última. Isso fará com que ele gere um valor alto quando encontrar uma transição de um pixel claro para um escuro.
$$
\text{Kernel} = 
\begin{pmatrix}
 1 & 0 & -1 \\
 1 & 0 & -1 \\
 1 & 0 & -1
\end{pmatrix}
$$

\section*{Passo 2: O Processo (Cálculo da Primeira Posição)}

Primeiro, posicionamos o kernel no canto superior esquerdo da imagem. Em seguida, realizamos a multiplicação elemento a elemento e somamos todos os resultados.

$$
\text{Região da Imagem} =
\begin{pmatrix}
 8 & 8 & 8 \\
 8 & 8 & 8 \\
 8 & 8 & 8
\end{pmatrix}
\quad \quad
\text{Kernel} =
\begin{pmatrix}
 1 & 0 & -1 \\
 1 & 0 & -1 \\
 1 & 0 & -1
\end{pmatrix}
$$

\textbf{Cálculo:}
\begin{align*}
\text{Soma} &= (8 \times 1) + (8 \times 0) + (8 \times -1) \\
           &+ (8 \times 1) + (8 \times 0) + (8 \times -1) \\
           &+ (8 \times 1) + (8 \times 0) + (8 \times -1) \\
           &= (0) + (0) + (0) = 0
\end{align*}

Este é o primeiro valor da nossa matriz de saída.

$$
\text{Saída} =
\begin{pmatrix}
 \mathbf{0} & ? & ? \\
 ? & ? & ? \\
 ? & ? & ?
\end{pmatrix}
$$

\section*{Passo 3: Deslizando o Kernel}

Agora, deslizamos o kernel uma posição para a direita (stride de 1) e repetimos o processo.

$$
\text{Nova Região da Imagem} =
\begin{pmatrix}
 8 & 8 & 1 \\
 8 & 8 & 1 \\
 8 & 8 & 1
\end{pmatrix}
\quad \quad
\text{Kernel} =
\begin{pmatrix}
 1 & 0 & -1 \\
 1 & 0 & -1 \\
 1 & 0 & -1
\end{pmatrix}
$$

\textbf{Cálculo:}
\begin{align*}
\text{Soma} &= (8 \times 1) + (8 \times 0) + (1 \times -1) \\
           &+ (8 \times 1) + (8 \times 0) + (1 \times -1) \\
           &+ (8 \times 1) + (8 \times 0) + (1 \times -1) \\
           &= (7) + (7) + (7) = 21
\end{align*}

Este é o segundo valor da nossa matriz de saída.
$$
\text{Saída} =
\begin{pmatrix}
 0 & \mathbf{21} & ? \\
 ? & ? & ? \\
 ? & ? & ?
\end{pmatrix}
$$

\section*{Passo 4: O Resultado Final}

Repetimos esse processo para todas as posições possíveis. A matriz de saída final, ou \textbf{Mapa de Características}, será:
$$
\text{Saída Final} =
\begin{pmatrix}
 0 & 21 & 21 \\
 0 & 21 & 21 \\
 0 & 21 & 21
\end{pmatrix}
$$

\section*{Interpretação}

A primeira coluna da saída é \textbf{0}, indicando que não há borda vertical naquela região da imagem original. A segunda e a terceira colunas têm o valor alto \textbf{21}, mostrando que o kernel detectou com sucesso a forte borda vertical que existia na imagem de entrada. Este é o princípio fundamental da convolução em CNNs.

\end{document}