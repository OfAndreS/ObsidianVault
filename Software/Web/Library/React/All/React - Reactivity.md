---
banner: "- FILES/Attachments/Pasted image 20260923211852.png"
banner-fade: 100
banner-x: 50
banner-y: 50
---
---
#### **Intro )** - useState - useEffect - Hooks

O State (estado) representa variáveis internas que guardam informações sobre o componente. Quando um estado é modificado através de sua função atualizadora, o componente ao qual ele pertence é re-renderizado automaticamente, atualizando a interface visual do usuário.

---

### 📋 Checklist de Estudos - Tópicos a Cobrir

- [x] **01 )** - Fundamentos de Reatividade e Estado Local com `useState`
- [ ] **02 )** - Regra da Imutabilidade e Atualização de Objetos e Arrays no Estado (`spread operator`)
- [ ] **03 )** - Atualizações Funcionais / Baseadas no Estado Anterior (`setState(prev => prev + 1)`)
- [ ] **04 )** - As Regras dos Hooks (Rules of Hooks: chamada no topo e escopo de funções)
- [ ] **05 )** - Levantamento de Estado (Lifting State Up e comunicação Filho -> Pai via callbacks)
- [ ] **06 )** - Efeitos Colaterais com `useEffect` (Fases de Montagem, Atualização e Desmontagem)
- [ ] **07 )** - Otimização de Efeitos e Array de Dependências (`[]` vs `[deps]`)
- [ ] **08 )** - Função de Limpeza (Cleanup Function no `useEffect` para cancelar timers/listeners)
- [ ] **09 )** - Persistência de Dados e Acesso ao DOM com `useRef`
- [ ] **10 )** - Introdução à Memoização de Performance (`useMemo` para cálculos e `useCallback` para funções)

---

```ad-done
title:
#### **Fase 1 ) - Estado Local (useState)**
```

---

````ad-quote
title:

##### **01 )** - Descrição

```ad-quote
title:
<p align="justify">O hook useState permite declarar variáveis de estado dentro de componentes funcionais, sendo amplamente utilizado para responder dinamicamente a interações e ações do usuário.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 1.1 ) - _Declaração e Atualização de Estado_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Exemplo Prático com useState*
```

```jsx

import * as React from "react";
import { useState } from "react";

function App() {
  // Definição do useState e da primeira mensagem
  const [message, setMessage] = useState("Welcome");

  return (
    <div>
      <h1>{message}</h1>
      {/* Definição do botão e alteração do estado via clique */}
      <button
        onClick={() => {
          setMessage("Welcome!!!");
        }}
      >
        Clicar
      </button>
    </div>
  );
}

export default App;

```

````

---

```ad-done
title:
#### **Fase 2 ) - Levantamento de Estado (Lifting State Up)**
```

---

````ad-quote
title:

##### **02 )** - Descrição

```ad-quote
title:
<p align="justify">Padrão para atualizar o estado de um componente pai a partir de uma ação disparada dentro de um componente filho, passando funções de callback via props.</p>
```
````

> [!done] **_New_**

```ad-quote
title:

##### 2.1 ) - _Atualização a partir de Componente Filho_
```

````ad-quote
title:

```ad-quote
title:
###### A ) *Comunicação Filho para Pai*
```

```ad-quote
title:
<p align="justify"></p>
```

````

---
