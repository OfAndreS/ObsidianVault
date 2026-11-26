---
banner: "![[Pasted image 20260421192206.png]]"
banner-x: 50
banner-y: 40
---

---

Sem usar a informação da variável categorizada, a variância calculada para a variável quantitativa para todos os dados mede a dispersão dos dados globalmente. 

Se a variância dentro de cada categoria for pequena e menor do que a global, significa que a variável qualitativa melhora a capacidade de previsão da quantitativa e portanto existe uma relação entre as duas variáveis.

---

A ANOVA, sigla para Análise de Variância, é um teste estatístico utilizado para comparar as médias de uma variável contínua entre dois ou mais grupos definidos por uma variável categórica.

O objetivo do teste é responder a uma pergunta direta: as diferenças observadas entre as médias dos grupos são reais ou decorrem apenas de flutuações normais da amostragem?

  

### A Ideia Central por Trás do Nome

Embora o foco seja comparar médias, o teste faz essa comparação analisando a dispersão dos dados.

  

Imagine uma situação prática em que você queira avaliar o salário médio de profissionais de três áreas de atuação distintas. A dispersão total dos salários pode ser decomposta em duas fontes principais:

  

- Variância entre grupos: reflete a distância entre a média de cada profissão e a média salarial geral de todas as pessoas reunidas.
    
      
    
- Variância dentro dos grupos: reflete a variação natural de salário que existe entre indivíduos que atuam dentro da mesma profissão.
    
      
    

Se a distância entre as médias das profissões for muito maior do que o ruído interno existente dentro de cada área, o teste conclui que o grupo de atuação realmente influencia o salário.

  

### A Estatística F

O motor matemático da ANOVA calcula uma proporção conhecida como Estatística F de Snedecor:

  

$$F = \frac{\text{Variância entre os grupos}}{\text{Variância dentro dos grupos}}$$

- Valor próximo de 1: a variação entre os grupos é do mesmo tamanho da variação esperada pelo acaso. Não há evidência de que os grupos sejam diferentes.
    
      
    
- Valor expressivamente maior que 1: as diferenças entre as médias são consideravelmente maiores que o ruído individual interno.
    
      
    

Esse valor de F é então associado a uma curva de distribuição teórica para gerar o p-valor. Um p-valor menor que 0,05 indica a rejeição da hipótese de médias iguais.

  

### Hipóteses do Teste

- Hipótese nula (H0): todas as médias populacionais dos grupos são perfeitamente iguais ($\mu_1 = \mu_2 = \dots = \mu_k$).
    
      
    
- Hipótese alternativa (H1): pelo menos uma das médias difere das demais.
    
      
    

A ANOVA não aponta qual grupo específico é diferente, apenas sinaliza que existe alguma diferença relevante no conjunto.

  

### Premissas Fundamentais

Para que os resultados da ANOVA sejam confiáveis, a base de dados precisa atender a três condições:

  

- Independência: os dados coletados de cada indivíduo não podem depender ou influenciar as respostas de outros participantes.
    
      
    
- Normalidade: a variável contínua deve apresentar distribuição aproximadamente normal dentro de cada categoria avaliada.
    
      
    
- Homocedasticidade: a variabilidade interna dos dados precisa ser equivalente em todos os grupos comparados (verificada por testes como o teste de Levene).
    
      
    

### Próximos Passos após o Teste

- Quando a ANOVA rejeita a hipótese nula com três ou mais grupos: aplica-se um teste complementar de comparações múltiplas (como o teste post-hoc de Tukey) para identificar exatamente quais pares de médias diferem entre si.
    
      
    
- Para medir o impacto prático: calcula-se o Eta-quadrado ($\eta^2$), que expressa a porcentagem da variação total da variável numérica que é explicada pela variável de grupo.