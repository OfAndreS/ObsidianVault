
---

https://www.youtube.com/watch?v=tvd715tZrtQ&list=PLD80i8An1OEEgxMpH-SOdBCjWpT5Io5rJ&index=3


---
---

wandb agent ofandres-ufrn/mlops-lab2-wine-quality/lo3r32iy

---
---

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

---
---

  O pipeline completo de comandos a ser executado em ordem no terminal é o seguinte:
  ──────
  ### 1. Criar o Sweep no W&B
  
  Registra a configuração da MLP e o método Bayesiano no servidor do W&B:
  
    wandb sweep sweep.yaml
  
  │ Saída esperada: Uma mensagem informando o comando do agente, por exemplo:
  │ wandb: Run sweep agent with: wandb agent ofandres-ufrn/mlops-lab2-wine-quality/<SWEEP_ID>
  ──────
  ### 2. Executar o Agente de Treinamento
  
  Inicia as iterações de treino do modelo com busca bayesiana (ex.: 25 iterações):
  
    wandb agent ofandres-ufrn/mlops-lab2-wine-quality/<SWEEP_ID> --count 25
  
  │ (Substitua <SWEEP_ID> pelo ID que apareceu no passo anterior)
  │ Dica: Você pode abrir 2 abas no terminal rodando esse mesmo comando simultaneamente para executar os runs em paralelo.  
  ──────
  ### 3. Marcar o Melhor Modelo com o Alias best
  
  Após o agente terminar todos os 25 runs, execute o script de pós-processamento:
  
    python set_best_alias.py <SWEEP_ID>
  
  │ Saída esperada: O terminal exibirá o ID do melhor run, seus hiperparâmetros, os scores (cv_f1_macro_mean, test_f1_macro)
  │ e confirmará que o alias best foi aplicado ao artifact no W&B.
  ──────
  ### 4. Montar o W&B Report (Interface Web)
  
  Com os dados coletados e o melhor modelo marcado, abra o navegador em:
  https://wandb.ai/ofandres-ufrn/mlops-lab2-wine-quality
  e clique em Create Report para adicionar os gráficos e os links dos artifacts.