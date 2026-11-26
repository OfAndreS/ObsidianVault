
---

>[!quote] **Def**
>Para trabalhar com arquivos, inclua a biblioteca `<fstream>`. Se precisar de entrada/saída padrão (como `std::cout`), inclua também `<iostream>`.

```
#include <fstream>  // Para manipulação de arquivos
#include <iostream> // Para entrada/saída padrão (opcional)
```

---
#### **Boas Práticas**

>[!quote] **Def**
>
>01 )
>- Sempre verifique se o arquivo foi aberto com sucesso usando `is_open()`.
>  
>---
>
>02 )
>- Feche o arquivo após o uso com `close()`.
>  
>---  
>03 )
>- Use exceções para lidar com erros de forma robusta.
>  
>---
>
>04 )  
>- Use `std::getline()` para ler linhas inteiras de texto.

---
#### **Classes Principais**

>[!quote] **Def**
>
>01 ) `std::ofstream`
>- Usada para **escrever** em arquivos (output file stream).
>  
>---
>
>02 ) `std::ifstream`
>- Usada para **ler** de arquivos (input file stream).
>  
>---  
>03 ) `std::fstream`
>- Usada para **leitura e escrita** (file stream).
>  

---

>[!tip] ### **Manipulando Arquivos**

---
#### **Modos de Abertura**

>[!quote] **Def**
>
>01 ) `std::ios::in`
>- Abre para leitura (padrão para `ifstream`).
>  
>---
>
>02 ) `std::ios::out`
>- Abre para escrita (padrão para `ofstream`).
>  
>---  
>03 ) `std::ios::app`
>- Adiciona ao final do arquivo (append).
>  
>---  
>
>04 ) `std::ios::ate`
>- Abre e posiciona o cursor no final do arquivo.
>  
>---
>
>05 ) `std::ios::trunc`
>- Trunca o arquivo (apaga o conteúdo existente).
>  
>---  
>06 ) `std::ios::binary`
>- Abre o arquivo em modo binário.

```cpp
#include <fstream>

int main() { // Exemplo com ios:app
    // Abre o arquivo "exemplo.txt" para escrita no final (append)
    std::ofstream arquivoSaida("exemplo.txt", std::ios::app);

    if (arquivoSaida.is_open()) {
        arquivoSaida << "Adicionando uma nova linha.\n"; // Escreve no final do arquivo
        arquivoSaida.close();
    } else {
        std::cerr << "Erro ao abrir o arquivo!\n";
    }

    return 0;
}
```

---
#### **Abrindo um Arquivo**

>[!quote] **Def**
>Para abrir um arquivo, você pode usar o método `open()` ou passar o nome do arquivo diretamente no construtor da classe.

```cpp
#include <fstream>

int main() {
    // Abre o arquivo "exemplo.txt" para escrita
    std::ofstream arquivoSaida("exemplo.txt");

    // Verifica se o arquivo foi aberto com sucesso
    if (arquivoSaida.is_open()) {
        arquivoSaida << "Olá, mundo!\n"; // Escreve no arquivo
        arquivoSaida.close(); // Fecha o arquivo
    } else {
        std::cerr << "Erro ao abrir o arquivo para escrita!\n";
    }

    return 0;
}
```

---
#### **Leitura e Escrita de Dados**

>[!quote] **Def**
>Você pode usar os operadores `<<` e `>>` para escrever e ler dados, respectivamente. Além disso, a função `std::getline()` é útil para ler linhas inteiras.

```cpp
#include <fstream>
#include <iostream>

int main() {
    // Escrevendo no arquivo
    std::ofstream arquivoSaida("dados.txt");
    if (arquivoSaida.is_open()) {
        arquivoSaida << "Nome: João\nIdade: 25\n"; // Escreve dados no arquivo
        arquivoSaida.close();
    } else {
        std::cerr << "Erro ao abrir o arquivo para escrita!\n";
    }

    // Lendo do arquivo
    std::ifstream arquivoEntrada("dados.txt");
    if (arquivoEntrada.is_open()) {
        std::string linha;
        while (std::getline(arquivoEntrada, linha)) { // Lê linha por linha
            std::cout << linha << '\n'; // Exibe no console
        }
        arquivoEntrada.close();
    } else {
        std::cerr << "Erro ao abrir o arquivo para leitura!\n";
    }

    return 0;
}
```
##### *Abrindo um arquivo para Escrita e Leitura de dados*

```cpp
#include <iostream>
#include <fstream>
#include <string>

int main() {
    std::fstream arquivo;
    
    // Abre o arquivo para leitura e escrita
    arquivo.open("exemplo.txt", std::ios::in | std::ios::out);
    
    if (!arquivo.is_open()) {
        std::cerr << "Erro ao abrir o arquivo!" << std::endl;
        return 1;
    }
    
    // Operações de leitura e escrita...
    
    arquivo.close();
    return 0;
}
```

---
#### **Tratamento de Exceções**

>[!quote] **Def**
>Você pode configurar os fluxos para lançar exceções em caso de erros usando o método `exceptions()`.

```cpp
#include <fstream>
#include <iostream>

int main() {
    std::ifstream arquivoEntrada;
    arquivoEntrada.exceptions(std::ifstream::failbit | std::ifstream::badbit);

    try {
        arquivoEntrada.open("arquivo_inexistente.txt");
        std::string linha;
        while (std::getline(arquivoEntrada, linha)) {
            std::cout << linha << '\n';
        }
        arquivoEntrada.close();
    } catch (const std::ifstream::failure& e) {
        std::cerr << "Erro ao abrir ou ler o arquivo: " << e.what() << '\n';
    }

    return 0;
}
```

---

>[!tip] #### **Tools**

---
#### **Código em C++ para contar linhas de um arquivo .txt**

```ad-quote
title: **Def**


**Como funciona:**

1. O programa pede ao usuário o nome do arquivo .txt
    
2. Abre o arquivo usando `ifstream`
    
3. Lê o arquivo linha por linha usando `getline()`
    
4. Incrementa um contador para cada linha lida
    
5. Retorna o total de linhas ou -1 se houve erro ao abrir o arquivo
```

```cpp
#include <iostream>
#include <fstream>
#include <string>

int contarLinhas(const std::string& nomeArquivo) {
    std::ifstream arquivo(nomeArquivo);
    int contador = 0;
    std::string linha;

    if (!arquivo.is_open()) {
        std::cerr << "Erro ao abrir o arquivo: " << nomeArquivo << std::endl;
        return -1;
    }

    while (std::getline(arquivo, linha)) {
        contador++;
    }

    arquivo.close();
    return contador;
}

int main() {
    std::string nomeArquivo;
    std::cout << "Digite o nome do arquivo .txt: ";
    std::cin >> nomeArquivo;

    int totalLinhas = contarLinhas(nomeArquivo);

    if (totalLinhas >= 0) {
        std::cout << "O arquivo possui " << totalLinhas << " linhas." << std::endl;
    }

    return 0;
}
```

---

>[!tip] #### **Trabalhando com Modo Binário**

---

>[!quote] **Def**
>Você pode configurar os fluxos para lançar exceções em caso de erros usando o método `exceptions()`.

```cpp
#include <fstream>
#include <iostream>

struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    // Escrevendo dados binários
    Pessoa p = {"João", 25};
    std::ofstream arquivoSaida("dados.bin", std::ios::binary);
    if (arquivoSaida.is_open()) {
        arquivoSaida.write(reinterpret_cast<char*>(&p), sizeof(p)); // Escreve a estrutura no arquivo
        arquivoSaida.close();
    } else {
        std::cerr << "Erro ao abrir o arquivo para escrita!\n";
    }

    // Lendo dados binários
    Pessoa p2;
    std::ifstream arquivoEntrada("dados.bin", std::ios::binary);
    if (arquivoEntrada.is_open()) {
        arquivoEntrada.read(reinterpret_cast<char*>(&p2), sizeof(p2)); // Lê a estrutura do arquivo
        arquivoEntrada.close();
        std::cout << "Nome: " << p2.nome << ", Idade: " << p2.idade << '\n'; // Exibe os dados
    } else {
        std::cerr << "Erro ao abrir o arquivo para leitura!\n";
    }

    return 0;
}
```

---
