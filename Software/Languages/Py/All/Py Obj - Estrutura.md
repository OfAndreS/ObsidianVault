---
banner: "![[Pasted image 20251215191705.png]]"
banner-x: 50
banner-y: 40
---

---

```ad-example

#### **Classes e Objetos**
```

---
#### **01 )** - Definição de Classes

```ad-quote
title: **Def**

Uma **classe** é um **blueprint** ou um modelo para criar objetos. Ela define a estrutura: 
- (quais atributos o objeto terá) e o comportamento (quais métodos o objeto poderá executar) 
  
Que todos os objetos criados a partir dela possuirão. Pense em uma classe como a planta de uma casa: ela descreve todos os cômodos, portas e janelas, mas não é a casa em si.
```

---
#### **02 )** - Instanciação de Objetos

```ad-quote
title: **Def**

A **instanciação** de um objeto é o processo de criar uma instância concreta (um objeto real) a partir de uma classe. Usando a analogia da casa, instanciar um objeto seria construir a casa real a partir da planta. Cada objeto criado terá seus próprios valores para os atributos definidos na classe.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Carro: # Definição da classe Carro
    def __init__(self, marca, modelo, cor):
        self.marca = marca      # Atributo de instância
        self.modelo = modelo    # Atributo de instância
        self.cor = cor          # Atributo de instância

    def ligar(self): # Método de instância
        return f"O {self.marca} {self.modelo} está ligado."

# Instanciação de objetos
carro1 = Carro("Toyota", "Corolla", "Prata")
carro2 = Carro("Honda", "Civic", "Preto")

print(f"Carro 1: {carro1.marca} {carro1.modelo}, Cor: {carro1.cor}")
print(f"Carro 2: {carro2.marca} {carro2.modelo}, Cor: {carro2.cor}")

print(carro1.ligar())
```

---

```ad-example

#### **Atributos**
```

---

```ad-quote
title: **Def**

Atributos são as características ou dados que um objeto possui.
```

---
#### **01 )** - Atributos de Instância

```ad-quote
title: **Def**

**Atributos de instância** são dados **únicos para cada objeto** criado a partir de uma classe. Cada objeto terá sua própria cópia desses atributos, e as modificações feitas em um objeto não afetarão os atributos de outros objetos da mesma classe. Por exemplo, em uma classe `Carro`, `cor` e `modelo` seriam atributos de instância.
```

---
#### **02 )** - Atributos de Classe

```ad-quote
title: **Def**

**Atributos de classe** (ou atributos estáticos) são dados **compartilhados por todos os objetos da classe**. Eles pertencem à classe em si, e não a uma instância específica. Se o valor de um atributo de classe for alterado, essa alteração será visível para todos os objetos da classe. Um exemplo seria um `contadorDeCarros` em uma classe `Carro`, que registra quantos carros foram criados.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Veiculo:
    # Atributo de classe: compartilhado por todas as instâncias
    numero_rodas_padrao = 4
    total_veiculos_criados = 0

    def __init__(self, tipo, cor):
        self.tipo = tipo # Atributo de instância
        self.cor = cor   # Atributo de instância
        Veiculo.total_veiculos_criados += 1 # Incrementa o contador de classe

# Acessando atributo de classe diretamente pela classe
print(f"Número de rodas padrão (antes da criação): {Veiculo.numero_rodas_padrao}")
print(f"Total de veículos criados (antes da criação): {Veiculo.total_veiculos_criados}")

# Instanciando objetos
carro = Veiculo("Carro", "Azul")
moto = Veiculo("Moto", "Vermelha")

# Acessando atributo de instância
print(f"\nCarro: {carro.tipo}, Cor: {carro.cor}")
print(f"Moto: {moto.tipo}, Cor: {moto.cor}")

# Acessando atributo de classe via instância (mas o valor é o mesmo para todos)
print(f"Número de rodas do carro: {carro.numero_rodas_padrao}")
print(f"Número de rodas da moto: {moto.numero_rodas_padrao}")

# Modificando atributo de classe (afeta todas as instâncias e a própria classe)
Veiculo.numero_rodas_padrao = 2

print(f"\nNovo número de rodas padrão: {Veiculo.numero_rodas_padrao}")
print(f"Número de rodas do carro (após mudança): {carro.numero_rodas_padrao}") # Reflete a mudança
print(f"Total de veículos criados: {Veiculo.total_veiculos_criados}") # Reflete o total de instâncias
```

---

```ad-example

#### **Métodos**
```

---

```ad-quote
title: **Def**

Métodos são as ações que um objeto pode realizar.
```

---
#### **01 )** - Métodos de Instância

```ad-quote
title: **Def**

**Métodos de instância** 

São funções que operam sobre os dados (atributos) de um objeto específico. Eles acessam e manipulam os atributos de instância. 
- Por exemplo, em uma classe `Carro`, um método `ligarMotor()` operaria sobre o estado de um carro específico.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Livro:
    def __init__(self, titulo, autor, paginas):
        self.titulo = titulo
        self.autor = autor
        self.paginas = paginas
        self.lido = False # Atributo de instância

    # Método de instância: opera sobre os atributos do objeto
    def marcar_como_lido(self):
        self.lido = True
        return f"O livro '{self.titulo}' foi marcado como lido."

    def get_info(self):
        status = "lido" if self.lido else "não lido"
        return f"Título: {self.titulo}, Autor: {self.autor}, Páginas: {self.paginas}, Status: {status}"

livro1 = Livro("O Pequeno Príncipe", "Antoine de Saint-Exupéry", 96)
livro2 = Livro("1984", "George Orwell", 328)

print(livro1.get_info())
print(livro2.get_info())

print(livro1.marcar_como_lido())
print(livro1.get_info())
print(livro2.get_info())
```

---
#### **02 )** - Métodos de Classe - `@classmethod`

```ad-quote
title: **Def**

**Métodos de classe** 

são funções que: 
- Operam sobre a classe em vez da instância. 
- Geralmente chamado `cls` em Python
  
Eles recebem a própria classe como primeiro argumento. São úteis para operações que afetam a classe como um todo, como criar uma nova instância de uma maneira específica (métodos de fábrica) ou acessar atributos de classe.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Ponto:
    unidade_medida = "metros" # Atributo de classe

    def __init__(self, x, y):
        self.x = x
        self.y = y

    def get_coordenadas(self):
        return f"({self.x}, {self.y}) {self.unidade_medida}"

    @classmethod
    def mudar_unidade(cls, nova_unidade):
        """Método de classe para mudar a unidade de medida para todos os pontos."""
        cls.unidade_medida = nova_unidade
        print(f"Unidade de medida alterada para: {cls.unidade_medida}")

    @classmethod
    def from_string(cls, coord_string):
        """Método de classe para criar um Ponto a partir de uma string."""
        x_str, y_str = coord_string.strip("()").split(",")
        return cls(int(x_str), int(y_str))

ponto1 = Ponto(10, 20)
print(ponto1.get_coordenadas())

# Acessando e chamando o método de classe via classe
Ponto.mudar_unidade("centímetros")
print(ponto1.get_coordenadas())

ponto2 = Ponto.from_string("(5,15)") # Criando um Ponto usando o método de classe
print(ponto2.get_coordenadas())
```

---
#### **03 )** - Métodos Estáticos - `@staticmethod`

```ad-quote
title: **Def**

**Métodos estáticos** 

são funções utilitárias que: 
- **Pertencem à classe, mas não operam sobre a instância nem a classe**. 
  
Eles não recebem nem a instância (`self`) nem a classe (`cls`) como primeiro argumento. São como funções regulares que foram agrupadas dentro de uma classe por conveniência lógica, sem depender de qualquer estado da instância ou da classe.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
import math

class Geometria:
    @staticmethod
    def area_circulo(raio):
        """Método estático para calcular a área de um círculo."""
        if raio < 0:
            raise ValueError("O raio não pode ser negativo.")
        return math.pi * raio**2

    @staticmethod
    def perimetro_retangulo(largura, altura):
        """Método estático para calcular o perímetro de um retângulo."""
        if largura < 0 or altura < 0:
            raise ValueError("Largura e altura não podem ser negativas.")
        return 2 * (largura + altura)

# Chamando métodos estáticos diretamente pela classe
print(f"Área do círculo com raio 5: {Geometria.area_circulo(5):.2f}")
print(f"Perímetro do retângulo 3x4: {Geometria.perimetro_retangulo(3, 4)}")
```

---

```ad-example

#### **Construtor - `__init__`**
```

---

```ad-quote
title: **Def**

**Construtor** 

É um método especial que é automaticamente chamado quando um novo objeto é criado. Seu principal papel é **inicializar o estado do objeto**, atribuindo valores iniciais aos seus atributos. Em Python, o construtor é o método `__init__`.
```

---
#### **01 )** - Passando Argumentos para o Construtor

```ad-quote
title: **Def**

É comum **passar argumentos para o construtor** 

- para fornecer os valores iniciais dos atributos do objeto no momento de sua criação. Isso garante que o objeto seja criado em um estado válido e consistente.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Pessoa:
    def __init__(self, nome, idade): # O construtor __init__
        self.nome = nome # Atributo inicializado com o argumento 'nome'
        self.idade = idade # Atributo inicializado com o argumento 'idade'
        print(f"Objeto Pessoa '{self.nome}' criado com sucesso!")

    def apresentar(self):
        return f"Olá, meu nome é {self.nome} e eu tenho {self.idade} anos."

# Criando objetos e passando argumentos para o construtor
pessoa1 = Pessoa("Alice", 30)
pessoa2 = Pessoa("Bob", 25)

print(pessoa1.apresentar())
print(pessoa2.apresentar())
```

---

```ad-example

#### **Encapsulamento**
```

---

```ad-quote
title: **Def**
**Encapsulamento** 

- **Proteger a integridade dos dados** de um objeto
  
Restringindo o acesso direto a eles. Ele garante que os dados de um objeto só possam ser acessados ou modificados de maneiras controladas, geralmente por meio de métodos públicos.
```

---
#### **01 )** - Modificadores de Acesso (Convenções em Python)

```ad-quote
title: **Def**

Em linguagens como C++, existem modificadores de acesso explícitos (`public`, `private`, `protected`). Em Python, o encapsulamento é mais baseado em **convenções**:
```
##### *Atributos e métodos "privados" - Usando `_`:*

```ad-quote
title: **Def**

Um único underscore (`_nome_atributo`) indica que o atributo ou método é "protegido" e deve ser tratado como interno à classe. Embora ainda seja tecnicamente acessível, é uma convenção para os desenvolvedores não o acessarem diretamente de fora.
```
##### *Atributos e métodos "muito privados" - Usando `__`:*

```ad-quote
title: **Def**

Dois underscores (`__nome_atributo`) acionam a "name mangling" em Python, o que dificulta o acesso direto de fora da classe. Isso é geralmente usado para evitar conflitos de nomes em herança e para tornar a intenção de privacidade ainda mais explícita.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class ContaBancaria:
    def __init__(self, saldo_inicial):
        self.__saldo = saldo_inicial # Atributo "muito privado" (name mangling)
        self._limite = 1000 # Atributo "protegido" (convenção)

    def depositar(self, valor):
        if valor > 0:
            self.__saldo += valor
            print(f"Depósito de R${valor:.2f} realizado. Novo saldo: R${self.__saldo:.2f}")
        else:
            print("Valor de depósito inválido.")

    def sacar(self, valor):
        if valor > 0 and self.__saldo - valor >= -self._limite:
            self.__saldo -= valor
            print(f"Saque de R${valor:.2f} realizado. Novo saldo: R${self.__saldo:.2f}")
        else:
            print("Saque inválido: Saldo insuficiente ou valor negativo.")

    def exibir_saldo(self):
        print(f"Saldo atual: R${self.__saldo:.2f}")

conta = ContaBancaria(500)
conta.exibir_saldo()

conta.depositar(200)
conta.sacar(300)
conta.sacar(1500)

# Tentando acessar atributos "privados" (desencorajado, mas possível em Python)
# print(conta.__saldo) # Isso resultaria em um AttributeError (name mangling)
# print(conta._limite) # Isso funcionaria, mas viola a convenção de privacidade
```

---
#### **02 )** - Getters e Setters - `@property`

```ad-quote
title: **Def**

Embora o encapsulamento em Python seja por convenção, é comum usar **getters e setters** para controlar o acesso e a modificação de atributos. 
```

```ad-quote
title: **Def**

A forma mais elegante de fazer isso é usando o decorador `@property`, que permite definir métodos para acessar e modificar atributos como se fossem atributos normais, sem a necessidade de chamar funções explicitamente: `get_nome()` ou `set_nome()`
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Produto:
    def __init__(self, nome, preco):
        self._nome = nome  # Atributo protegido (convenção)
        self._preco = 0.0
        self.preco = preco # Usa o setter para validar o preço inicial

    @property # Getter para 'nome'
    def nome(self):
        return self._nome

    @property # Getter para 'preco'
    def preco(self):
        return self._preco

    @preco.setter # Setter para 'preco'
    def preco(self, novo_preco):
        if novo_preco >= 0:
            self._preco = novo_preco
        else:
            print("Erro: O preço não pode ser negativo. Preço não alterado.")

    def exibir_detalhes(self):
        return f"Produto: {self.nome}, Preço: R${self.preco:.2f}"

item = Produto("Notebook", 3500.00)
print(item.exibir_detalhes())

# Acessando o preço como se fosse um atributo (internamente, chama o getter)
print(f"Preço do notebook: R${item.preco:.2f}")

# Tentando alterar o preço (internamente, chama o setter)
item.preco = 3200.00
print(item.exibir_detalhes())

item.preco = -100.00
print(item.exibir_detalhes())
```

---

```ad-example

#### **Herança**
```

---

```ad-quote
title: **Def**

A **herança** é um mecanismo que permite que uma nova classe herde atributos e métodos de uma classe existente. Isso promove a reutilização de código e estabelece uma relação "é um tipo de" entre as classes. 
- Por exemplo, uma classe `CarroEsportivo` pode herdar de uma classe `Carro`.
```

---
#### **01 )** - Sobrescrita de Métodos

```ad-quote
title: **Def**

ocorre quando uma subclasse fornece sua própria implementação para um método que já existe na sua superclasse. Isso permite que a subclasse personalize o comportamento herdado sem alterar o código da classe pai.
```

---
#### **02 )** - Função - `super()`

```ad-quote
title: **Def**

A função `super()` em Python é usada para **chamar métodos da classe pai** a partir de uma subclasse. Isso é particularmente útil quando você deseja estender o comportamento de um método herdado, adicionando funcionalidades específicas na subclasse, mas ainda mantendo o comportamento original da superclasse.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Animal: # Superclasse
    def __init__(self, nome):
        self.nome = nome

    def fazer_som(self):
        return "Fazendo algum som..."

class Cachorro(Animal): # Subclasse que herda de Animal
    def __init__(self, nome, raca):
        super().__init__(nome) # Chama o construtor da classe pai
        self.raca = raca

    # Sobrescrita do método fazer_som
    def fazer_som(self):
        return "Au au!"

    def abanar_rabo(self):
        return f"{self.nome} está abanando o rabo."

class Gato(Animal): # Outra subclasse que herda de Animal
    def __init__(self, nome, cor):
        super().__init__(nome)
        self.cor = cor

    # Sobrescrita do método fazer_som
    def fazer_som(self):
        return "Miau!"

# Criando instâncias das classes
animal_generico = Animal("Desconhecido")
cachorro = Cachorro("Buddy", "Golden Retriever")
gato = Gato("Mia", "Branco")

print(animal_generico.fazer_som())
print(cachorro.fazer_som())
print(cachorro.abanar_rabo())
print(gato.fazer_som())
```

---
#### **03 )** - Herança Múltipla

```ad-quote
title: **Def**

**Herança múltipla** é a capacidade de uma classe herdar de múltiplas classes pai. Embora poderosa, ela pode introduzir desafios como o "problema do diamante" (ambiguidade sobre qual método chamar quando o mesmo método é herdado de várias superclasses). Em Python, a **MRO (Method Resolution Order)** define a ordem em que as classes base são pesquisadas para encontrar um método, resolvendo essas ambiguidades.
```

---

>[!example]  **_Exemplo Python:_**

---

```python
class Voador:
    def voar(self):
        return "Eu posso voar!"

class Nadador:
    def nadar(self):
        return "Eu posso nadar!"

class Pato(Voador, Nadador): # Herança múltipla
    def quack(self):
        return "Quack!"

    def fazer_som(self): # Método próprio do Pato
        return "Quack quack!"

pato = Pato()
print(pato.voar())
print(pato.nadar())
print(pato.quack())
print(pato.fazer_som())

# MRO (Method Resolution Order) para ver a ordem de busca de métodos
print(Pato.__mro__)
```

---

```ad-example

#### **Polimorfismo**
```

---

```ad-quote
title: **Def**

É a capacidade de objetos de diferentes classes serem tratados de forma uniforme, desde que compartilhem uma interface comum. Ele permite que o mesmo código opere em diferentes tipos de objetos.
```

---
#### **01 )** - Polimorfismo por Herança

```ad-quote
title: **Def**

É quando objetos de diferentes classes que compartilham uma superclasse comum podem ser tratados como objetos dessa superclasse. Isso permite que você escreva código mais genérico que pode interagir com uma variedade de objetos relacionados. Por exemplo, uma função que recebe um objeto do tipo `Animal` pode aceitar tanto um `Cachorro` quanto um `Gato`, já que ambos são `Animal`.
```


---

>[!example]  **_Exemplo Python:_**

---

```python
class Animal:
    def fazer_som(self):
        pass # Método a ser sobrescrito pelas subclasses

class Cachorro(Animal):
    def fazer_som(self):
        return "Au au!"

class Gato(Animal):
    def fazer_som(self):
        return "Miau!"

class Pato(Animal):
    def fazer_som(self):
        return "Quack!"

# Função polimórfica: aceita qualquer objeto que seja um Animal (ou herde de Animal)
def emitir_som_animal(animal):
    print(f"O animal faz: {animal.fazer_som()}")

# Criando instâncias de diferentes tipos de animais
c = Cachorro()
g = Gato()
p = Pato()

# Chamando a função polimórfica com diferentes objetos
emitir_som_animal(c)
emitir_som_animal(g)
emitir_som_animal(p)
```

---
#### **02 )** -  Polimorfismo por Duck Typing

```ad-quote
title: **Def**

É um conceito popular em linguagens dinâmicas como Python. Onde o que importa é o comportamento, e não a herança formal. A ideia é: "Se parece com um pato, anda como um pato e quacka como um pato, então é um pato!". Isso significa que, se um objeto possui os métodos ou atributos necessários para uma determinada operação, ele pode ser usado nessa operação, independentemente de sua classe ou de qualquer hierarquia de herança.
```


---

>[!example]  **_Exemplo Python:_**

---

```python
class PatoReal:
    def quack(self):
        return "Quack, quack!"
    def andar(self):
        return "Andando como um pato."

class BonecoPato:
    def quack(self):
        return "Quack simulado!"
    def andar(self):
        return "Roleando como um boneco pato."

class Pessoa:
    def quack(self):
        return "Pessoa imitando um pato: Quack!"
    def andar(self):
        return "Andando como uma pessoa."

# Função polimórfica por Duck Typing
def fazer_barulho_e_andar(objeto):
    print(f"Barulho: {objeto.quack()}")
    print(f"Movimento: {objeto.andar()}")

print("--- Pato Real ---")
pato_real = PatoReal()
fazer_barulho_e_andar(pato_real)

print("\n--- Boneco Pato ---")
boneco_pato = BonecoPato()
fazer_barulho_e_andar(boneco_pato)

print("\n--- Pessoa ---")
pessoa = Pessoa()
fazer_barulho_e_andar(pessoa)

# Nota: A classe Pessoa não herda de PatoReal ou BonecoPato,
# mas como possui os métodos 'quack' e 'andar',
# ela se comporta como um "pato" para a função fazer_barulho_e_andar.
```

---
