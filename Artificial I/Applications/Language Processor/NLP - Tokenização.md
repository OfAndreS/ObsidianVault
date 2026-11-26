
---

- Existe mais de uma forma de tokenizar um texto ou frase.
    
- O conceito de token é amplo. Um token pode ser uma palavra, um sinal de pontuação, um emoji ou até um símbolo matemático. Ele representa qualquer pacote de informação que o seu sistema precisa ler.
    
- A forma mais simples de tokenizar uma frase é com a função split do Python. Ela quebra o texto usando os espaços em branco, mas tem a desvantagem de deixar a pontuação grudada nas palavras.
    
- As expressões regulares também podem ser utilizadas para criar tokens. Elas conseguem isolar a pontuação corretamente e são executadas de forma muito rápida pelo computador.
    
- O spaCy é uma das melhores e mais completas ferramentas de tokenização, pois entende regras gramaticais e contexto.
    
- A precisão do spaCy pode tornar o processamento lento a depender da tarefa. Portanto, é interessante saber quais módulos da ferramenta podem ser desligados visando uma resposta mais rápida.
    
- A criação de um vocabulário exige organização. Converter todas as letras para minúsculas antes da contagem evita que a máquina trate a mesma palavra como dois tokens diferentes.
    
- O método de tokenização escolhido vai impactar o resto do seu sistema. O importante é garantir que qualquer informação removida durante esse processo não fará falta para o objetivo final da sua aplicação.

