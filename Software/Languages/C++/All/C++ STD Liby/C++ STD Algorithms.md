
---

> [!quote] **`std::sort(begin, end)`**: Ordena os elementos no intervalo `[begin, end)` em ordem crescente.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {4, 2, 5, 3, 1};
    std::sort(vec.begin(), vec.end());
    for (int i : vec) {
        std::cout << i << " ";
    }
    return 0;
}
```

---

>[!quote] **`std::find(begin, end, value)`**: Procura o primeiro elemento igual a `value` no intervalo `[begin, end)`.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    auto it = std::find(vec.begin(), vec.end(), 3);
    if (it != vec.end()) {
        std::cout << "Elemento encontrado: " << *it << std::endl;
    } else {
        std::cout << "Elemento não encontrado" << std::endl;
    }
    return 0;
}
```

---

>[!quote] **`std::accumulate(begin, end, initial_value)`**: Soma os elementos no intervalo `[begin, end)` a partir de `initial_value`.

```cpp
#include <numeric>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    int sum = std::accumulate(vec.begin(), vec.end(), 0);
    std::cout << "Soma: " << sum << std::endl;
    return 0;
}
```

---

>[!quote] **`std::transform(begin, end, result, unary_op)`**: Aplica a função `unary_op` a cada elemento no intervalo `[begin, end)` e armazena o resultado em `result`.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int square(int x) {
    return x * x;
}

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    std::vector<int> result(vec.size());
    std::transform(vec.begin(), vec.end(), result.begin(), square);
    for (int i : result) {
        std::cout << i << " ";
    }
    return 0;
}
```

---

>[!quote] **`std::count(begin, end, value)`**: Conta o número de ocorrências de `value` no intervalo `[begin, end)`.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {1, 2, 3, 2, 4, 2, 5};
    int count = std::count(vec.begin(), vec.end(), 2);
    std::cout << "Número de ocorrências de 2: " << count << std::endl;
    return 0;
}
```

---

>[!quote] **`std::reverse(begin, end)`**: Inverte a ordem dos elementos no intervalo `[begin, end)`.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    std::reverse(vec.begin(), vec.end());
    for (int i : vec) {
        std::cout << i << " ";
    }
    return 0;
}
```

---

>[!quote] **`std::max_element(begin, end)`**: Retorna um iterador para o maior elemento no intervalo `[begin, end)`.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    auto it = std::max_element(vec.begin(), vec.end());
    std::cout << "Maior elemento: " << *it << std::endl;
    return 0;
}
```

---

>[!quote] **`std::min_element(begin, end)`**: Retorna um iterador para o menor elemento no intervalo `[begin, end)`.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    auto it = std::min_element(vec.begin(), vec.end());
    std::cout << "Menor elemento: " << *it << std::endl;
    return 0;
}
```

---

>[!quote] **`std::unique(begin, end)`**: Remove elementos duplicados consecutivos no intervalo `[begin, end)`.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {1, 2, 2, 3, 3, 3, 4, 5, 5};
    auto last = std::unique(vec.begin(), vec.end());
    vec.erase(last, vec.end());
    for (int i : vec) {
        std::cout << i << " ";
    }
    return 0;
}
```

---
