
---

>[!quote] **Link:** [Add a Liby in project Part I ](https://www.udemy.com/course/complete-game-development-series-04-making-a-game-with-c/learn/lecture/40905886#content)

>[!quote] **Link:** [Add a Liby in project Part II ](https://www.udemy.com/course/complete-game-development-series-04-making-a-game-with-c/learn/lecture/40905888#content)

```

NomeDaBiblioteca -> Propriedades -> Geral -> Tipo de configuração -> Biblioteca Estática

```

```

Projeto -> Propriedades -> C/C++ -> Geral -> Diretório de inclusão Adicionais

$(SolutionDir)nomedabiblioteca

```

```

Projeto -> Propriedades -> Linker -> Entrada -> Dependências Adicionais

$(SolutionDir)$(Platform)\$(Configuration)\nomedabiblioteca.lib

```

```

Projeto -> Propriedades -> Linker (mudar a plataforma para win32) -> Entrada -> Dependências Adicionais

$(SolutionDir)\$(Configuration)\nomedabiblioteca.lib

```

```

Solução -> Propriedades -> Dependências da solução -> Marcar a dependência

```

---

>[!quote] **Link:** [Build a DLL Library](https://www.udemy.com/course/complete-game-development-series-04-making-a-game-with-c/learn/lecture/40905892#content)

