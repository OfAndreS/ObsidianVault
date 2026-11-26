
---

Batch Normalization Paper:- [https://arxiv.org/abs/1502.03167](https://www.youtube.com/redirect?event=video_description&redir_token=QUZZTVljRmNZUHhZdFViRlphS2ZJNEhPWmdQYXxBTl9pYzRlTTVoLTNTZ2FaTVYtMzJkbXhFMVRQbklLa3V3YXUzRVhfT0NjLTRQQjhuSUp6T3h3a0tJYVNOZ3FTU0xua09VLU9tSmFqcVUyUFhtajZDdHVQbGVOZk1HRXlaZ3hh&q=https%3A%2F%2Farxiv.org%2Fabs%2F1502.03167&v=PaIKIXb3v9Q) How Does Batch 

Normalization Help Optimization?:- [https://arxiv.org/abs/1805.11604](https://www.youtube.com/redirect?event=video_description&redir_token=QUZZTVljRTBKUEgxT0xIOHdTUGxfdmFuUXE5T3xBTl9pYzRkWmhCZU9iRGNUeXJHeEgtMkk0QkJDRjFCV2hUWE5kTTh6bDlfaUlLQVB4Zk50NUtOTHYza29rSTdmN3lUR1lxT3lOQmdQMnBVcGsxSWxqSEZ6OGFTTkdQa1pPVFE0&q=https%3A%2F%2Farxiv.org%2Fabs%2F1805.11604&v=PaIKIXb3v9Q)

Treinar uma rede neural profunda sem normalização é como descer uma montanha cheia de penhascos e vales pontiagudos, onde um passo grande pode arremessar você longe do objetivo. A normalização atua como um trator que aplana esse terreno, transformando buracos íngremes em encostas suaves. Isso permite usar taxas de aprendizado muito maiores sem que o modelo divirja.

Além da suavização do terreno de otimização, a técnica introduz um leve efeito regularizador por conta do ruído inerente ao cálculo das estatísticas em lotes menores, o que também reduz a dependência de técnicas como o dropout.

![[Pasted image 20261005182837.png]]



  

$$x = B = \{x_1, x_2, \dots, x_m\}$$

  

$$\mu_B = \frac{1}{m} \sum_{i=1}^{m} x_i$$

  

$$\sigma_B^2 = \frac{1}{m} \sum_{i=1}^{m} (x_i - \mu_B)^2$$

  

$$\hat{x}_i = \frac{x_i - \mu_B}{\sqrt{\sigma_B^2 + \varepsilon}}$$

  

$$y_i = \textcolor{green}{\gamma} \hat{x}_i + \textcolor{red}{\beta}$$

  


![[Pasted image 20261005183252.png]]

![[Pasted image 20261005184433.png]]