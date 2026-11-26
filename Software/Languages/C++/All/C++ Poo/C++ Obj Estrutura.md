
---
#### **Estrutura de uma Classe em C++**

>[!quote] **Def**
>Uma classe em C++ é um modelo ou "blueprint" para criar objetos. Define um tipo de dado abstrato que combina dados (atributos ou membros de dados) e funções (métodos ou funções membro) que operam nesses dados. A estrutura básica de uma classe em C++ é a seguinte:
###### ***Exemplo:***

```cpp

// // .hpp da Classe // //

class NomeDaClasse {
public: // Especificador de acesso público
    // Construtores
    NomeDaClasse(); // Construtor padrão
    NomeDaClasse(parametros); // Construtor parametrizado

    // Métodos Públicos (Interface da classe)
    tipoRetorno metodoPublico1(parametros);
    tipoRetorno metodoPublico2(parametros);
    // ...

    // Getters (Métodos de acesso para atributos privados)
    tipoAtributo getAtributo1() const; // Const significa que não modifica o objeto
    tipoAtributo getAtributo2() const;
    // ...

    // Setters (Métodos de modificação para atributos privados)
    void setAtributo1(tipoAtributo valor);
    void setAtributo2(tipoAtributo valor);
    // ...


private: // Especificador de acesso privado
    // Atributos (Dados) da classe
    tipoAtributo atributo1;
    tipoAtributo atributo2;
    // ...

    // Métodos Privados (Implementação interna da classe)
    tipoRetorno metodoPrivado1(parametros);
    tipoRetorno metodoPrivado2(parametros);
    // ...


public: // Novamente público (opcional, pode omitir se não tiver mais membros públicos após os privados)
    // Destrutor
    ~NomeDaClasse();
};
```

---
#### **Construtor**

>[!quote] **Def**
>**Definição e Propósito:** 
>- Um construtor é um método especial que tem o mesmo nome da classe. Ele é automaticamente invocado quando um objeto da classe é criado. A principal função de um construtor é inicializar o estado do objeto, ou seja, atribuir valores iniciais aos seus atributos.

>[!quote] **Vault:** [[C++ Plus Construtor]]
##### ***Características:***

>[!quote] **Def**
>
>**Nome:** 
>- Tem o mesmo nome da classe.

>[!quote] **Def**
>
>**Sem tipo de retorno:** 
>- Não tem tipo de retorno, nem mesmo `void`.
>  

>[!quote] **Def**
>  
>**Pode ser sobrecarregado (Overload)** 
>- Uma classe pode ter múltiplos construtores com listas de parâmetros diferentes (sobrecarga de construtores). Isso permite criar objetos de maneiras diferentes, dependendo das informações disponíveis no momento da criação.
>  

>[!quote] **Def**
>  
>**Construtor Padrão (Default Constructor):** 
>  - Se você não definir nenhum construtor na classe, o compilador C++ fornecerá um construtor padrão implícito que não faz nada (além da inicialização padrão dos membros). Se você define _qualquer_ construtor, o construtor padrão implícito não é mais fornecido.
###### ***Exemplo:***

```cpp
// .cpp
class Retangulo {
public:
    double largura;
    double altura;

    // Construtor Padrão (sem parâmetros)
    Retangulo() {
        largura = 0.0;
        altura = 0.0;
        std::cout << "Construtor padrão Retangulo chamado." << std::endl;
    }

    // Construtor Parametrizado (com parâmetros para inicializar largura e altura)
    Retangulo(double larg, double alt) {
        largura = larg;
        altura = alt;
        std::cout << "Construtor parametrizado Retangulo chamado." << std::endl;
    }
};

// Implementação //
int main() {
    Retangulo ret1; // Usa o construtor padrão
    Retangulo ret2(5.0, 10.0); // Usa o construtor parametrizado

    std::cout << "Retangulo 1: Largura = " << ret1.largura << ", Altura = " << ret1.altura << std::endl; // Retangulo 1: Largura = 0, Altura = 0
    std::cout << "Retangulo 2: Largura = " << ret2.largura << ", Altura = " << ret2.altura << std::endl; // Retangulo 2: Largura = 5, Altura = 10

    return 0;
}
```

---
#### **Destrutor (`~Destrutor`)**

>[!quote] **Def**
>**Definição e Propósito:** 
>- Um destrutor é um método especial com o mesmo nome da classe precedido por um til (`~`). Ele é automaticamente invocado quando um objeto da classe está prestes a ser destruído (por exemplo, quando sai do escopo, ou quando é explicitamente deletado usando `delete` para objetos alocados dinamicamente). A principal função de um destrutor é liberar recursos que foram alocados pelo objeto durante seu tempo de vida, como memória alocada dinamicamente, fechar arquivos abertos, etc.

>[!quote] **Def**
>**Importância:** 
>- Essencial para a gestão de recursos, especialmente em C++ onde a gestão de memória é manual (em grande parte). Se você aloca memória dinamicamente dentro de um objeto (por exemplo, usando `new`), é crucial liberá-la no destrutor usando `delete` para evitar vazamentos de memória.
##### ***Características:***

>[!quote] **Def**
>
>**Nome:** 
>- Tem o mesmo nome da classe precedido por `~`.

>[!quote] **Def**
>
>**Sem parâmetros:** 
>- Não aceita parâmetros.
>  

>[!quote] **Def**
>  
>**Sem tipo de retorno:** 
>- Não tem tipo de retorno, nem mesmo `void`.
>  

>[!quote] **Def**
>  
>**Apenas um destrutor:** 
>  - Uma classe pode ter apenas um destrutor.
###### ***Exemplo:***

```cpp
// .cpp
class ExemploDestrutor {
public:
    int *ponteiroParaDados;

// Construtor que aloca memória dinamicamente
    ExemploDestrutor(int tamanho) {
        ponteiroParaDados = new int[tamanho];
        std::cout << "Construtor ExemploDestrutor: Memória alocada." << std::endl;
    }

// Destrutor que libera a memória alocada
    ~ExemploDestrutor() {
        delete[] ponteiroParaDados; // Libera a memória alocada
        std::cout << "Destrutor ExemploDestrutor: Memória liberada." << std::endl;
    }
};

int main() {
    { // Início de um escopo
        ExemploDestrutor obj1(10); // Construtor chamado, memória alocada.
        // ... usar obj1 ...
    } // Fim do escopo, obj1 sai do escopo, destrutor de obj1 é chamado automaticamente, memória liberada.

    return 0;
}
```

---
#### **Métodos**

>[!quote] **Def**
>**Definição e Propósito:** 
>- Métodos são funções que são definidas dentro de uma classe e operam nos dados (atributos) dos objetos dessa classe. Eles definem o comportamento que os objetos podem ter.
##### ***Tipos de Métodos:***

>[!quote] **Def**
>
>**Métodos Públicos:** 
>- Declarados na seção `public:` da classe. São acessíveis de _fora_ da classe (através dos objetos da classe) e de _dentro_ da classe. Eles formam a interface pública da classe, ou seja, como os usuários da classe podem interagir com os objetos.

>[!quote] **Def**
>
>**Métodos Privados:** 
>- Declarados na seção `private:` da classe. São acessíveis _apenas_ de dentro da própria classe (por outros métodos da mesma classe). Eles são usados para implementar detalhes internos da classe que não devem ser acessíveis ou modificados diretamente de fora. Isso ajuda a encapsular a implementação e proteger a integridade dos dados.
>  

>[!quote] **Def**
>  
>**Métodos Públicos: protected** 
>- Em C++, métodos **protected** são membros de uma classe que podem ser acessados apenas pela própria classe, por classes derivadas (herança) e por funções amigas (`friend`). Eles são úteis para encapsular funcionalidades que devem ser compartilhadas com classes derivadas, mas não expostas publicamente. Isso permite um controle mais granular sobre o acesso aos membros da classe.
>  
###### ***Exemplo:***

```cpp
class Calculadora {
private:
    int resultado; // Atributo privado para armazenar o resultado

    // Método privado para validar se um número é positivo (implementação interna)
    bool ehPositivo(int num) {
        return num >= 0;
    }

public:
    // Construtor
    Calculadora() : resultado(0) {}

    // Método público para somar dois números
    void somar(int num1, int num2) {
        if (ehPositivo(num1) && ehPositivo(num2)) { // Usando método privado internamente
            resultado = num1 + num2;
            std::cout << "Soma realizada com sucesso." << std::endl;
        } else {
            std::cout << "Erro: Apenas números positivos são permitidos." << std::endl;
            resultado = 0; // Resetando o resultado em caso de erro
        }
    }

    // Método público para obter o resultado
    int obterResultado() const { // Método getter público
        return resultado;
    }
};

int main() {
    Calculadora calc;
    calc.somar(5, 3); // Chamando método público para somar
    std::cout << "Resultado: " << calc.obterResultado() << std::endl; // Chamando getter público para obter o resultado

    // calc.ehPositivo(10); // Erro! ehPositivo é privado, não pode ser acessado diretamente de fora.

    return 0;
}
```

---
#### **Getters / Métodos de Acesso**

>[!quote] **Def**
>**Definição e Propósito:** 
>- Getters são métodos públicos que fornecem acesso de leitura aos atributos privados de uma classe. Eles permitem que o código de fora da classe obtenha o valor de um atributo privado, mas _sem_ permitir que o atributo seja modificado diretamente. Isso é importante para manter o encapsulamento e o controle sobre como os dados são acessados.

>[!quote] **Def**
>**Convenção de Nomenclatura:**
>- Geralmente, o nome de um getter começa com `get` seguido do nome do atributo que ele acessa (por exemplo, `getNome()`, `getValor()`). É comum usar `const` no final da declaração do getter para indicar que o método não modifica o estado do objeto.
###### ***Exemplo:***

```cpp
class Pessoa {
private:
    std::string nome;
    int idade;

public:
    Pessoa(std::string n, int i) : nome(n), idade(i) {}

    // Getter para o atributo 'nome'
    std::string getNome() const {
        return nome;
    }

    // Getter para o atributo 'idade'
    int getIdade() const {
        return idade;
    }
};

int main() {
    Pessoa pessoa1("Alice", 30);

    std::cout << "Nome: " << pessoa1.getNome() << std::endl; // Acessando o nome usando o getter
    std::cout << "Idade: " << pessoa1.getIdade() << std::endl; // Acessando a idade usando o getter

    // pessoa1.nome = "Novo Nome"; // Erro! 'nome' é privado e não acessível diretamente de fora
    return 0;
}
```

---
#### **Setters / Métodos de Modificação**

>[!quote] **Def**
>**Definição e Propósito:** 
>- Setters são métodos públicos que permitem modificar o valor de atributos privados de uma classe. Eles fornecem um ponto de controle para alterar os dados de um objeto. Ao contrário do acesso direto, os setters podem incluir lógica de validação ou regras de negócio para garantir que os novos valores sejam válidos e consistentes com o estado do objeto.

>[!quote] **Def**
>**Convenção de Nomenclatura:** 
>- Geralmente, o nome de um setter começa com `set` seguido do nome do atributo que ele modifica (por exemplo, `setNome()`, `setValor()`).
###### ***Exemplo:***

```cpp
class Produto {
private:
    std::string nome;
    double preco;

public:
    Produto(std::string n, double p) : nome(n), preco(p) {}

    // Getter para 'nome' (já vimos getters)
    std::string getNome() const { return nome; }
    double getPreco() const { return preco; }

    // Setter para 'preco' com validação
    void setPreco(double novoPreco) {
        if (novoPreco >= 0) { // Validação: Preço não pode ser negativo
            preco = novoPreco;
            std::cout << "Preço atualizado com sucesso." << std::endl;
        } else {
            std::cout << "Erro: Preço inválido. O preço deve ser não negativo." << std::endl;
        }
    }
};

int main() {
    Produto produto1("Livro", 25.0);
    std::cout << "Preço inicial: " << produto1.getPreco() << std::endl; // Preço inicial: 25

    produto1.setPreco(30.0); // Usando setter para modificar o preço (válido)
    std::cout << "Novo preço: " << produto1.getPreco() << std::endl; // Novo preço: 30

    produto1.setPreco(-5.0); // Usando setter para tentar definir um preço inválido (negativo)
    std::cout << "Preço após tentativa inválida: " << produto1.getPreco() << std::endl; // Preço após tentativa inválida: 30 (o preço não mudou devido à validação no setter)

    return 0;
}
```

---