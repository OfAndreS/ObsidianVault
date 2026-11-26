---
banner: "![[Threrd IMG.png]]"
banner-fade: 100
---
---

`````ad-quote
title:
```ad-quote
title:

###### **Focus )** - _"Qual é a intenção do autor com essa informação?"_
```

```ad-quote
title:

###### **Focus )** - _"O que está ocupando o seu espaço atencional?"_
```

```ad-quote
title:

###### **Focus )** - _"Qual é o seu objetivo final com essa tarefa?"_
```

````ad-quote
title:

```contributionGraph
title: 
graphType: month-track
dateRangeValue: 160
dateRangeType: LATEST_DAYS
startOfWeek: 0
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 15px
  fontWeight: normal
dataSource:
  type: PAGE
  value: ""
  dateField:
    type: FILE_MTIME
  filters: []
fillTheScreen: false
enableMainContainerShadow: false
cellStyleRules: []

```
`````

````ad-quote
title:

```ad-quote
title:
###### **Task Buffer**
```

```bash

# Alternar para o monitor principal (DP-2)
tablet-tela1
  
# Alternar para o monitor vertical (HDMI-0) 
tablet-tela2 
  
# Ver status dos monitores e dispositivos detectados
tablet-config.py --status
```

````

---

>[!done] ***New***

---

````ad-quote
title:
```ad-quote
title:
###### **Copy Vault**
```


```bash

# **Restrições Estritas:**

# 1. Nunca use **negrito** dentro do texto. O negrito só é permitido nos tópicos.
# 2. Não coloque o texto dentro de caixas de código ou formatação de terminal (`code blocks`).
# 3. Retorne um arquivo MD.

# Refatore o texto 1 para a notação do texto 2:

# Texto 1: 



# Texto 2:

```
````

````ad-quote
title:
```ad-quote
title:
###### **Copy Image**
```

```bash 
# Analise cuidadosamente a imagem de referência fornecida para capturar seu estilo artístico distintivo, paleta de cores, tipo de pincelada/textura, iluminação e atmosfera geral.

# Com base nesta análise, crie uma nova imagem de:
```
````

````ad-quote
title:

```ad-quote
title:

###### **Copy Prompt**

```

```python

# "Faça com a notação padrão do gemini. Não utilize o 'ad-quote'."

# "Vamos usar o método socrático para entender [tópico]."  

# "Eu gostaria de solicitar a recapitulação parcial"

# "Quero aprender sobre [tópico] socraticamente."

# "Vou te enviar um texto em inglês. Por favor, não o corrija apenas. Liste os 3 erros mais graves que cometi, explique o porquê e sugira duas formas mais naturais (nativas) de reescrever o parágrafo X. Aqui está o texto: [Seu Texto]"
```

````

---

>[!done] ***New***

---

<div style="border: 1px solid #555; padding: 15px; border-radius: 8px; text-align: justify; line-height: 1.6; box-sizing: border-box; margin: 2px; display: block;">
	<h2>01 ) - Título Primário</h2>
	<div style="border: 1px solid #555; padding: 15px; border-radius: 8px; text-align: justify; line-height: 1.6; box-sizing: border-box; margin: 2px; display: block;">
	
	A Regressão Linear é a Base Fundamental para qualquer aspirante a Cientista De Dados. Por ser um Modelo Interpretável E Poderoso, ela serve como Porta De Entrada para conceitos mais complexos de Aprendizado De Máquina.
	
	</div>
	<br>
	<div style="border: 1px solid #555; padding: 15px; border-radius: 8px; text-align: justify; line-height: 1.6; box-sizing: border-box; margin: 2px; display: block;">
	
	No entanto, entendo perfeitamente que o ambiente corporativo exige ferramentas compartilhadas. Minha organização é adaptável, portanto, a transição para plataformas colaborativas como o Notion ou Jira não será um problema. Além disso, conheço bem as metodologias ágeis especificamente o Scrum.
	
	</div>
</div>

---

>[!done] ***New***

---

CONFIGURAÇÕES DE COMO DEVE SER TODAS AS RESPOSTA

- Evite ganchos, metáforas exageradas, listas longas e conclusões genéricas. Melhore a coesão textural retire vício de linguagem e hipérboles
- O seu texto está desnecessariamente formal. Utilize termos mais normais de forma que ainda tenha um rigor acadêmico e retire todas as hipérboles!


---

>[!done] ***New***

---
### **Casos de Uso do Usuário Comum**

- **Criação de tarefa:** Eu como usuário quero criar uma nova tarefa com título e descrição para não esquecer o que preciso fazer ao longo do dia.

- **Listagem de tarefas:** Eu como usuário quero ver todas as minhas tarefas pendentes para conseguir organizar o meu tempo de forma mais eficiente.

- **Atualização de status:** Eu como usuário quero marcar uma tarefa como concluída para conseguir acompanhar o meu progresso visualmente.

- **Edição de texto:** Eu como usuário quero alterar a descrição de uma tarefa já criada para corrigir erros de digitação ou adicionar mais detalhes.

- **Exclusão de tarefa:** Eu como usuário quero apagar uma tarefa da minha lista para manter a tela limpa e organizada.


### **Casos de Uso do Administrador**

- **Visão geral do sistema:** Eu como administrador quero ver a lista de todos os usuários cadastrados para entender quantas pessoas utilizam o aplicativo.

- **Monitoramento de uso:** Eu como administrador quero ver o número total de tarefas criadas no sistema para analisar o engajamento geral da plataforma.

- **Moderação de contas:** Eu como administrador quero excluir a conta de usuários inativos para liberar espaço no banco de dados e reduzir custos.

As tarefas devem ser salvas em JSON's.

As tarefas devem ter os seguintes atributos:
- str titulo
- str descricao
- bool finalizada

Criar o método PUT /tarefa/{id}
- Para atualizar uma tefa já existente

---

Always split the item label and its descriptive body into separate lines. Never place descriptive text on the same line as the colon (- Label: Text). Break the line immediately after the colon and indent the description by 4 to 6 spaces. Mandatory layout format: Item Label: Indented descriptive content placed on the next line. Apply bold text strictly to headings, section titles, and item labels. Never use bold, italics, underlines, or em dashes inside body paragraphs. Keep running prose completely free of inline markdown emphasis. Use explicit headings for distinct sections. Insert an empty line between sequential items to guarantee clear visual separation. Use numbered lists for sequential steps and bullet points (-) for non-sequential items.