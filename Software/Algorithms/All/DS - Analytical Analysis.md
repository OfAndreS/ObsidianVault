
---

---

```ad-done
title:  

#### **Fase 01 )** - Análise assintótica
```

---

https://www.youtube.com/watch?v=AveLzjfZbEs

````ad-quote
title:

##### **01 )** - O Protocolo HTTP

```ad-quote
title:
...
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _..._
```

````ad-quote
title:

```ad-quote
title:
###### A ) *...*
```

![[Pasted image 20260824225430.png]]

````

| Complexidade               | Crescimento            |
| -------------------------- | ---------------------- |
| $$O(1)$$                   | $$\text{Constante}$$   |
| $$O(log_{10}{n})$$         | $$\text{Logarítmica}$$ |
| $$O(n)$$                   | $$\text{Linear}$$      |
| $$O(n \cdot log_{10}{n})$$ | $$\text{Log linear}$$  |
| $$O(n^2)$$                 | $$\text{Quadrática}$$  |
| $$O(n^3)$$                 | $$\text{Cúbica}$$      |
| $$O(e^n)$$                 | $$\text{Exponencial}$$ |

| **Notação** | **Significado**                                   |
| ----------- | ------------------------------------------------- |
| $$O$$       | $$\text{assintótico superior}$$                   |
| $$\Omega$$  | $$\text{assintótico inferior}$$                   |
| $$\Theta$$  | $$\text{assintoticamente restrito}$$              |
| $$o$$       | $$\text{assintoticamente superior não restrito}$$ |
| $$\omega$$  | $$\text{assintoticamente inferior não restrito}$$ |

Copie e cole este bloco diretamente no seu arquivo para visualizar a tabela renderizada corretamente.

https://pt.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/big-big-theta-notation

Com certeza! Eu ajustei os textos utilizando o símbolo correto para representar a notação e adicionei a explicação detalhada sobre a nova função matemática.

  

### **Função f(n)**

- **Definição**: Função alvo. Representa o tempo de execução real do algoritmo, calculando a quantidade de trabalho para uma entrada de tamanho n. 

### **Função g(n)**

- **Definição**: Função de referência. Serve como uma régua de comparação para classificar ordens de grandeza. Pode ser qualquer função conhecida, sem necessidade de ter o mesmo ritmo de f(n).

### **Notação O: f(n) pertencente a O(g(n))**

- **Papel**: Limite assintótico superior ou teto.

- **Definição matemática**: $0 \le f(n) \le c \cdot g(n)$ para todo $n \ge n_0$.

- **Significado prático**: O tempo do algoritmo nunca ultrapassará essa curva para entradas grandes.  

- **Modelo mental**: A função de referência g(n) cresce no mesmo ritmo ou mais rápido que f(n).  

### **Notação Ômega: f(n) pertencente a Omega(g(n))**

- **Papel**: Limite assintótico inferior ou piso.  

- **Definição matemática**: $0 \le c \cdot g(n) \le f(n)$ para todo $n \ge n_0$.  

- **Significado prático**: O algoritmo exigirá no mínimo essa quantidade de trabalho para rodar.  

- **Modelo mental**: A função de referência g(n) cresce no mesmo ritmo ou mais devagar que f(n).  

### **Notação Teta: f(n) pertencente a Theta(g(n))**

- **Papel**: Limite firme ou limite assintoticamente restrito.  

- **Definição matemática**: $0 \le c_1 \cdot g(n) \le f(n) \le c_2 \cdot g(n)$ para todo $n \ge n_0$.  

- **Significado prático**: A função alvo fica presa entre um piso e um teto da mesma curva g(n), crescendo na mesma ordem de grandeza.  

- **Modelo mental**: Representa a interseção $(f(n) \in O(g(n))) \cap (f(n) \in \Omega(g(n)))$.

---

### **Funcionamento do Algoritmo**

O algoritmo recebe a função alvo f(n) e uma lista contendo funções de referência g(n). Ele percorre cada função dessa lista e avalia a velocidade de crescimento relativo entre f(n) e g(n) quando a entrada cresce indefinidamente. Essa checagem é feita por meio da razão entre as duas funções no infinito.

  

Em seguida, o programa aplica o operador relacional específico da notação assintótica solicitada. Se a condição for atendida, a função de referência é adicionada à lista de saída. O resultado final devolvido é a lista filtrada de funções clássicas que satisfazem a regra.

  

### **Parâmetros da Simulação**

- **Função alvo**: $f(n) = n^2$
    
      
    
- **Catálogo de referências**: $1$, $\log n$, $n$, $n^2$, $n^3$, $2^n$
    
      
    
      
    

### **Tabela Comparativa de Execução**

|**Notação**|**Operador Lógico**|**Regra de Seleção**|**Saída do Algoritmo**|
|---|---|---|---|
|**O(g(n))**|$\le$|Crescimento igual ou superior a f(n)|$n^2$, $n^3$, $2^n$|
|**Omega(g(n))**|$\ge$|Crescimento igual ou inferior a f(n)|$1$, $\log n$, $n$, $n^2$|
|**Theta(g(n))**|$=$|Interseção exata entre O e Ômega|$n^2$|
|**o(g(n))**|$<$|Crescimento estritamente superior a f(n)|$n^3$, $2^n$|
|**omega(g(n))**|$>$|Crescimento estritamente inferior a f(n)|$1$, $\log n$, $n$|

### **Detalhamento Passo a Passo**

- **Notação O**: O algoritmo aplica o teste menor ou igual. Ele inclui toda função que cresce no mesmo ritmo ou mais rápido que a função quadrática. O resultado final entrega $n^2$, $n^3$ e $2^n$.
    
      
    
- **Notação Ômega**: O algoritmo aplica o teste maior ou igual. Ele inclui toda função que cresce no mesmo ritmo ou mais devagar que a função quadrática. O resultado final entrega $1$, $\log n$, $n$ e $n^2$.
    
      
    
- **Notação Teta**: O algoritmo busca a interseção matemática dos conjuntos de O e de Ômega. Apenas o elemento comum aos dois conjuntos é aprovado. O resultado final isola exclusivamente $n^2$.
    
      
    
- **Notação o pequeno**: O algoritmo aplica o teste estritamente menor. A própria função quadrática é descartada por ter a mesma taxa de crescimento. O resultado final entrega apenas $n^3$ e $2^n$.
    
      
    
- **Notação ômega pequeno**: O algoritmo aplica o teste estritamente maior. A própria função quadrática é descartada por ter a mesma taxa de crescimento. O resultado final entrega apenas $1$, $\log n$ e $n$.

---
---

# Operações básicas

$$f(n) = O(f(n))$$
$$c \times O(f(n)) = O(f(n)) \quad c = \text{constante}$$
$$O(f(n)) + O(f(n)) = O(f(n))$$
$$O(O(f(n))) = O(f(n))$$
$$O(f(n)) + O(g(n)) = O(\max(f(n), g(n)))$$
$$O(f(n))O(g(n)) = O(f(n)g(n))$$
$$f(n)O(g(n)) = O(f(n)g(n))$$


---
---
# Comparação de funções

Muitas das propriedades relacionais de números reais também se aplicam a comparações assintóticas. No caso das propriedades seguintes, suponha $f(n)$ e $g(n)$ sejam assintoticamente positivas.

### Transitividade:

$$f(n) = \Theta(g(n)) \quad \text{e} \quad g(n) = \Theta(h(n)) \quad \text{implicam} \quad f(n) = \Theta(h(n)),$$
$$f(n) = O(g(n)) \quad \text{e} \quad g(n) = O(h(n)) \quad \text{implicam} \quad f(n) = O(h(n)),$$
$$f(n) = \Omega(g(n)) \quad \text{e} \quad g(n) = \Omega(h(n)) \quad \text{implicam} \quad f(n) = \Omega(h(n)),$$
$$f(n) = o(g(n)) \quad \text{e} \quad g(n) = o(h(n)) \quad \text{implicam} \quad f(n) = o(h(n)),$$
$$f(n) = \omega(g(n)) \quad \text{e} \quad g(n) = \omega(h(n)) \quad \text{implicam} \quad f(n) = \omega(h(n)).$$

### Reflexividade:

$$f(n) = \Theta(f(n))$$
$$f(n) = O(f(n))$$
$$f(n) = \Omega(f(n))$$

### Simetria:

$$f(n) = \Theta(g(n)) \quad \text{se e somente se} \quad g(n) = \Theta(f(n))$$

### Simetria de transposição:

$$f(n) = O(g(n)) \quad \text{se e somente se} \quad g(n) = \Omega(f(n))$$
$$f(n) = o(g(n)) \quad \text{se e somente se} \quad g(n) = \omega(f(n))$$
