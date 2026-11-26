
---
### **Criar novas tarefas**

Você precisa de uma rota para receber informações e salvar no banco de dados. O usuário envia o título e o corpo do texto. A sua aplicação processa isso e devolve a tarefa recém criada. Na comunicação entre sistemas, chamamos essa ação de método POST.



### **Atualizar tarefas existentes**

As pessoas vão precisar editar o título ou corrigir o texto de uma tarefa. Você vai precisar de uma rota que receba a identificação da tarefa e os novos dados. Na programação, usamos o método PUT para substituir a tarefa inteira por uma nova versão. Usamos o método PATCH quando queremos mudar apenas um pequeno detalhe.

  

### **Apagar tarefas**

Você deve permitir que o usuário remova tarefas que não importam mais. Essa rota precisa apenas receber a identificação exata da tarefa e removê-la do banco de dados. Chamamos essa ação de método DELETE.

  

### **Filtrar resultados**

Quando o número de tarefas crescer, listar todas de uma vez vai ficar confuso. Você pode adicionar regras na sua rota de listagem. Isso permite buscar apenas as tarefas concluídas ou apenas as tarefas pendentes.

  

### **Dividir em páginas**

Se o usuário tiver milhares de tarefas, enviar todas de uma vez pode deixar o aplicativo lento. A paginação resolve esse problema. Ela divide as tarefas em pequenos grupos, entregando dez ou vinte resultados de cada vez.