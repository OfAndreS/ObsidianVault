
---

>[!quote] **Problema dos caracteres especiais**

>[!quote] **Link:** [Caracteres Especiais em C++](https://www.youtube.com/watch?v=5ogRNBvRAQk)

```cpp
#include <locale>

locale::global(locale("pt_BR.utf8"));

setlocale(LC_ALL, "Portuguese");

```

---

>[!quote] **Função de cabeçalho**

```cpp
#include <iostream>

using namespace std; // Evita a necessidade de escrever std::

void head() { 

    cout << "\n\n*  *  *  *  *  *  *  *  *  *  *  *  *  *  *\n\n" << endl;

}

int main(){ setlocale(LC_ALL, "Portuguese");

}
```

---

>[!quote] **Entrada padrão de dados**

```cpp
template <typename T>

            void input_iSync(T& userInput)

            {

                std::string linha;

                while (true)

                {

                    std::getline(std::cin, linha);

  

                    std::stringstream ss(linha);

                    if ((ss >> userInput) && (ss.eof())) {

                        break;

                    }

  

                    std::cout << "| Entrada inválida! Por favor, tente novamente.\n";

                }

            }
```

---