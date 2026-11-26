
---

```ad-quote
title: **Def**

**CMake** é uma ferramenta de **compilação automatizada** (_build system_) que ajuda a gerenciar o processo de compilação de software de forma independente de plataforma. Ele é amplamente utilizado em projetos de código aberto e comerciais, especialmente em C e C++, mas também suporta outras linguagens.
```

---
#### **Principais características do CMake:**

```ad-quote
title: **Def**

**Multiplataforma**
    
- Funciona em Windows, Linux, macOS e outros sistemas.
        
- Gera arquivos de compilação para diferentes sistemas (Makefiles, projetos do Visual Studio, Xcode, etc.).
```

```ad-quote
title: **Def**

**Linguagem de Script Própria**
    
- Usa arquivos de configuração chamados `CMakeLists.txt` para definir como o projeto deve ser compilado.
```

```ad-quote
title: **Def**

**Gerenciamento de Dependências**
    
- Pode encontrar bibliotecas instaladas no sistema (`find_package`).
        
- Suporta integração com ferramentas como `git submodule`, `Conan`, `vcpkg` e `FetchContent`.
```

```ad-quote
title: **Def**

**Builds Direcionados**
    
- Permite compilar diferentes versões (Debug, Release, etc.).
        
- Suporta compilação cruzada (_cross-compiling_).
```

```ad-quote
title: **Def**

**Integração com IDEs**
    
- Compatível com Visual Studio, CLion, Qt Creator, VS Code (com extensões), entre outros.
```

---
#### **Como o CMake funciona?**

```ad-quote
title: **Def**

**1 )** 
- Você escreve um arquivo `CMakeLists.txt` definindo como o projeto deve ser compilado.

---

**2 )** 
- O CMake gera arquivos de build específicos para o seu sistema (ex: `Makefile` no Linux ou `.sln` no Visual Studio).
  
---

**3 )** 
- Você usa um compilador (como `gcc`, `clang` ou `MSVC`) para construir o projeto a partir desses arquivos.
```

---
#### **Exemplo Básico de `CMakeLists.txt`**

```cmake
cmake_minimum_required(VERSION 3.10)  # Versão mínima do CMake
project(MeuProjeto)                   # Nome do projeto

add_executable(meu_programa main.cpp) # Define um executável
```

---

```ad-example

#### **Estrutura de projeto completa**
```

---

```ad-quote
title: **Def**

Template completo de `CMakeLists.txt` para sua estrutura de projeto:
```

>[!quote] **Link:**  [OfAndreS/CmakeTemplate](https://github.com/OfAndreS/CmakeTemplate)

```cmake
/cMakeTest 
├── CMakeLists.txt
├── include/
│   └── meu_arquivo.h
├── src/
│   └── main.cpp
├── resources/
└── thirdParty/
```

---
#### **`CMakeLists.txt` (no diretório raiz)**

```cmake
cmake_minimum_required(VERSION 3.13)

project(cMakeTest)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Adiciona diretórios de include (para encontrar arquivos .h)
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/include")

# Gera lista de arquivos .cpp automaticamente
file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp")

# Cria o executável com os arquivos encontrados
add_executable(${PROJECT_NAME} ${SOURCES})

# Define macro com o caminho para recursos (ajuda no desenvolvimento)
target_compile_definitions(${PROJECT_NAME} PUBLIC 
    RESOURCES_PATH="${CMAKE_CURRENT_SOURCE_DIR}/resources/"
)

# Exemplo: adicionar bibliotecas de terceiros no futuro
# add_subdirectory(thirdParty/minhaLib)
# target_link_libraries(${PROJECT_NAME} PRIVATE minhaLib)

# Opcional: para runtime estático no MSVC (Windows)
if(MSVC)
    set_property(TARGET ${PROJECT_NAME} PROPERTY
        MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>$<$<CONFIG:Release>:Release>"
    )
endif()

```

---
#### **Comandos para execução**

>[!quote] **1 ) Abrir o terminal no diretório do projeto**

```bash
cd /caminho/para/cMakeTest
```

>[!quote] **2 ) Abrir o terminal no diretório do projeto**

```bash
mkdir build
cd build
```

>[!quote] **3 ) Gerar os arquivos de build com o CMake**

```bash
Para o Visual Studio:
cmake ..

Para o Visual Studio Code:
Ctrl+Shift+P → `CMake: Configure`
```

>[!quote] **4 ) Compilar o Projeto**

```bash
cmake --build .
```

>[!quote] **5 ) Compilar o Projeto**

```bash
./cMakeTest
```
###### ***📝 Dica extra:** recompilar automaticamente ao mudar arquivos*

>[!quote] **Extra ) Compilar o Projeto**

```bash
cmake --build . --parallel
```

---
#### **.gitignore**

```bash 
# Diretórios de build
/build/
/cmake-build-*/

# Arquivos gerados pelo CMake
CMakeCache.txt
CMakeFiles/
Makefile
cmake_install.cmake
install_manifest.txt

# Executáveis gerados
/cMakeTest
/cMakeTest.exe
*.out
*.obj
*.o
*.a
*.lib
*.dll
*.so
*.dylib

# Arquivos temporários e de backup
*.log
*.tmp
*.swp
*.swo
*~

# Arquivos da IDE (opcional)
.vscode/
.idea/
*.user
*.code-workspace

# Arquivos de sistema
.DS_Store
Thumbs.db

```

---
