
---
#### **Melhores Casos de Uso**

>[!quote] **Def**
>**Legibilidade e Manutenção do Código:**
  >  
>- Enums são ideais para representar um conjunto fixo de valores relacionados, como dias da semana, estados de um processo, ou opções de menu. Isso torna o código mais legível e fácil de manter.

>[!quote] **Def**
>**Segurança de Tipos:**
  >  
>- `enum class` é particularmente útil para evitar conversões implícitas para inteiros, o que pode prevenir erros sutis no código.

>[!quote] **Def**
>**Documentação do Código:**
  >  
>- Enums servem como uma forma de documentação, indicando claramente quais valores são válidos para uma determinada variável.

>[!quote] **Def**
>**Facilidade de Iteração:**
  >  
>- Embora enums não sejam diretamente iteráveis, você pode usar técnicas como arrays associados para iterar sobre os valores de um enum.

---

>[!tip] ### **Enum Types**

---
#### **Definição Básica de Enum**

>[!quote] **Def**
>Um `enum` é definido usando a palavra-chave `enum`, seguida pelo nome do tipo enumerado e uma lista de identificadores entre chaves. Cada identificador representa um valor inteiro constante, começando por padrão em 0 e incrementando em 1 para cada item subsequente.

```cpp
enum Cor {
    Vermelho,   // 0
    Verde,      // 1
    Azul        // 2
};
```

>[!quote] Neste exemplo, `Vermelho` é equivalente a 0, `Verde` a 1, e `Azul` a 2.

---
#### **Enumeração Não Escopada (Unscoped Enum)**

>[!quote] **Def**
>Este é o tipo de enumeração tradicional, como no exemplo acima. Os identificadores são colocados no mesmo escopo onde o enum é definido, o que pode levar a conflitos de nomes.

```cpp
enum DiaDaSemana {
    Segunda,   // 0
    Terca,     // 1
    Quarta,    // 2
    Quinta,    // 3
    Sexta,     // 4
    Sabado,    // 5
    Domingo    // 6
};
```

>[!quote] Para acessar os valores de um `Unscoped Enum`: Basta especificar a variável acessada

```cpp
int main() {

DiaDaSemana segunda = Segunda;

}
```

---
#### **Enumeração Escopada (Scoped Enum) - `enum class`**

>[!quote] **Def**
>Introduzido no C++11, o `enum class` (ou `enum struct`) resolve o problema de conflitos de nomes, pois os identificadores são escopados dentro do enum. Além disso, eles não são implicitamente convertidos para inteiros, o que aumenta a segurança do tipo.

```cpp
enum class Mes {
    Janeiro,   // 0
    Fevereiro, // 1
    Marco,     // 2
    Abril,     // 3
    Maio,      // 4
    Junho,     // 5
    Julho,     // 6
    Agosto,    // 7
    Setembro,  // 8
    Outubro,   // 9
    Novembro,  // 10
    Dezembro   // 11
};
```

>[!quote] Para acessar os valores de um `enum class`, você deve usar o operador de escopo (`::`)

```cpp
int main() {

Mes mes = Mes::Janeiro;

}
```

---

>[!tip] ### **Específicos**

---

>[!quote] **Def**
>**Escolha entre `enum` e `enum class`:**
>
>**01 )**
>- Use `enum` tradicional quando você precisa de uma enumeração simples e não se preocupa com conflitos de nomes ou conversões implícitas.
>---
>
>**02 )**
>
>- Prefira `enum class` quando você quer maior segurança de tipos e evitar conflitos de nomes.

---
#### **Valores Personalizados:**

```cpp
enum class Status {
    Sucesso = 0,
    Falha = 1,
    Pendente = 2
};
```

>[!quote] Você pode atribuir valores específicos aos identificadores de um enum, se necessário:

---
#### **Conversão para Inteiro:**

```cpp
enum class Status {
    Sucesso = 0,
    Falha = 1,
    Pendente = 2
};

int valor = static_cast<int>(Status::Sucesso);
```

>[!quote] Para `enum class`, você pode converter explicitamente para inteiro usando `static_cast`:

---
#### **Exemplo de Uso**

```cpp
#include <iostream>

enum class EstadoProcesso {
    Iniciado,
    Executando,
    Pausado,
    Finalizado
};

void atualizarEstado(EstadoProcesso estado) {
    switch (estado) {
        case EstadoProcesso::Iniciado:
            std::cout << "Processo Iniciado\n";
            break;
        case EstadoProcesso::Executando:
            std::cout << "Processo Executando\n";
            break;
        case EstadoProcesso::Pausado:
            std::cout << "Processo Pausado\n";
            break;
        case EstadoProcesso::Finalizado:
            std::cout << "Processo Finalizado\n";
            break;
    }
}

int main() {
    EstadoProcesso estado = EstadoProcesso::Iniciado;
    atualizarEstado(estado);
    estado = EstadoProcesso::Executando;
    atualizarEstado(estado);
    return 0;
}
```

---
