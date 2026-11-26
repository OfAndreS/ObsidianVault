---
banner: "![[Pasted image 20251002114003.png]]"
---

---

https://www.youtube.com/watch?v=EuBBz3bI-aA

https://www.ibm.com/br-pt/think/topics/bias-variance-tradeoff

---
### Bias

O viés representa o erro introduzido por aproximar um problema complexo do mundo real utilizando um modelo matemático simplificado. Ele mede o quão longe as previsões médias do seu modelo estão do valor real que você está tentando prever.

- **Baixo Viés**: O modelo é flexível o suficiente para capturar as relações e os padrões verdadeiros presentes nos dados de treinamento.

- **Alto Viés**: O modelo assume premissas rígidas ou simplórias sobre os dados. Ele não consegue captar a tendência real do problema (fenômeno conhecido como _underfitting_ ou subajuste) e apresenta erros de forma sistemática.


### Variance

A variância mede a sensibilidade do seu modelo às flutuações e aos ruídos presentes especificamente nos dados de treinamento. Ela indica o quanto as previsões do modelo mudariam caso você o treinasse com um conjunto de dados diferente.

- **Baixa Variância**: O modelo produz previsões consistentes e estáveis, independentemente das pequenas variações no conjunto de dados utilizado para treiná-lo.

- **Alta Variância**: O modelo é complexo demais e tenta se adaptar a cada mínimo detalhe dos dados de treino, incluindo os ruídos aleatórios (fenômeno conhecido como _overfitting_ ou sobreajuste). Ele "decora" os dados de treino perfeitamente, mas falha de forma considerável ao receber informações novas.