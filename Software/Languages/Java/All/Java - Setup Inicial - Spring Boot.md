---
banner: "![[Pasted image 20250928150046.png]]"
---

---

````ad-quote
title:

##### **Intro )** - Contextualização da Estrutura

```ad-quote
title:
<p align="justify">No SPRING BOOT, a estrutura muda um pouco porque o framework assume o controle do fluxo (Inversão de Controle). Em vez de pastas como "operacoes" ou "factory", usamos camadas arquiteturais: CONTROLLER, SERVICE e REPOSITORY.</p>
```

```ad-quote
title:
<p align="justify">Aqui está o passo a passo para criar o QuickVote no VS CODE, adaptando aquela estrutura para o padrão profissional do SPRING.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - Gerar o Projeto - Spring Initializr

```ad-quote
title:
<p align="justify">Com o EXTENSION PACK instalado, não precisamos baixar ZIP do site. Faremos tudo internamente.</p>
```

```ad-quote
title:
###### **Execução no VS Code**
```

```ad-quote
title:
<p align="justify">Abra a Paleta de Comandos: CTRL + SHIFT + P. Digite e selecione: SPRING INITIALIZR: CREATE A MAVEN PROJECT. Siga as opções abaixo:</p>
```

```ad-quote
title:

| Configuração | Valor / Instrução |
| :--- | :--- |
| Spring Boot Version | Escolha a mais recente ESTÁVEL (sem SNAPSHOT/M1), ex: 3.3.x. |
| Language | Java. |
| Group Id | com.quickvote (Isso define a pasta base). |
| Artifact Id | api (Nome do projeto). |
| Packaging | Jar. |
| Java Version | 17. |
| Dependencies | Selecione Spring Web, Spring Boot DevTools e Lombok (já que você instalou a extensão dele). |
```

```ad-quote
title:
<p align="justify">Por fim, escolha uma pasta no seu computador para salvar o projeto.</p>
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - A Estrutura de Diretórios (Adaptação)

```ad-quote
title:
<p align="justify">O SPRING BOOT segue uma convenção rígida. Ao contrário da imagem onde SRC está na raiz, no SPRING (Maven) os códigos ficam em SRC/MAIN/JAVA.</p>
```

```ad-quote
title:
###### **Diagrama da Nova Estrutura**
```

```plaintext
QUICKVOTE-API
├── .vscode/                
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── quickvote
│   │   │           └── api
│   │   │               ├── ApiApplication.java  
│   │   │               │
│   │   │               ├── controller           
│   │   │               │   └── EnqueteController.java
│   │   │               │
│   │   │               ├── service              
│   │   │               │   └── VotacaoService.java
│   │   │               │
│   │   │               ├── model                
│   │   │               │   ├── Enquete.java
│   │   │               │   └── OpcaoVoto.java
│   │   │               │
│   │   │               └── repository          
│   │   │                   └── CsvRepository.java
│   │   │
│   │   └── resources
│   │       ├── application.properties           
│   │       └── dados
│   │           └── enquetes.csv                 
│   │
│   └── test                                    
├── pom.xml                                      
└── .gitignore                                   
```

```ad-quote
title:
###### **Justificativa da Mudança**
```

```ad-quote
title:

| Componente | Descrição |
| :--- | :--- |
| CONTROLLER | Onde definimos as rotas (GET, POST). Substitui a interface de console. |
| SERVICE | Onde fica a regra de negócio (validar se o usuário já votou, impedir duplicidade). |
| REPOSITORY | Onde fica a lógica SUJA de abrir arquivo, ler CSV e salvar CSV. |
| MODEL | Apenas a representação dos dados (os objetos puros). |
```

````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Criando os Pacotes no VS Code

```ad-quote
title:
<p align="justify">No VS CODE, dentro da aba EXPLORER (lado esquerdo), navegue até: src > main > java > com > quickvote > api. Clique com o botão direito na pasta API e selecione NEW FOLDER (ou NEW PACKAGE se a extensão Java estiver ativa visualmente). Crie as pastas uma por uma:</p>
```

```plaintext
controller
model
service
repository
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **04 )** - Configuração Inicial - Properties

```ad-quote
title:
<p align="justify">Vá até SRC/MAIN/RESOURCES/APPLICATION.PROPERTIES. Este arquivo define como sua API se comporta. Adicione estas linhas para começar:</p>
```

```properties
# Nome da Aplicação
spring.application.name=NomeDoProjeto

# Porta do Servidor (Padrão é 8080, mas vamos garantir)
server.port=8080

# Formatação bonita do JSON na resposta
spring.jackson.serialization.indent-output=true
```

```ad-quote
title:

**Configurando o Pom.xml**

```

```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
<modelVersion>4.0.0</modelVersion>
<parent>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-parent</artifactId>
<version>3.3.5</version>
<relativePath/>
</parent>
<groupId>com.todospring</groupId>
<artifactId>tds</artifactId>
<version>0.0.1-SNAPSHOT</version>
<name>tds</name>
<description>Demo project for Spring Boot</description>

  
<properties>
<java.version>17</java.version>
</properties>

  
<dependencies>
<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-web</artifactId>
</dependency>

  
<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>

  
<dependency>
<groupId>org.postgresql</groupId>
<artifactId>postgresql</artifactId>
<scope>runtime</scope>
</dependency>

  
<dependency>
<groupId>org.projectlombok</groupId>
<artifactId>lombok</artifactId>
<optional>true</optional>
</dependency>

  
<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-devtools</artifactId>
<scope>runtime</scope>
<optional>true</optional>
</dependency>

  
<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-test</artifactId>
<scope>test</scope>
</dependency>
</dependencies>

  
<build>
<plugins>
<plugin>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-maven-plugin</artifactId>
<configuration>
<excludes>
<exclude>
<groupId>org.projectlombok</groupId>
<artifactId>lombok</artifactId>
</exclude>
</excludes>
</configuration>
</plugin>
</plugins>
</build>

  
</project>
```


````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **05 )** - Verificando se funcionou - "Hello World"

```ad-quote
title:
<p align="justify">Para garantir que seu ambiente VS CODE + JAVA 17 + SPRING está perfeito, vamos criar um teste rápido. Na pasta CONTROLLER, crie um arquivo STATUSCONTROLLER.JAVA e cole este código:</p>
```

```java
package com.quickvote.api.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class StatusController {

    @GetMapping("/status")
    public String verificarStatus() {
        return "QuickVote API está rodando com sucesso!";
    }
}
```

```ad-quote
title:
###### **PARA RODAR**
```

```ad-quote
title:
<p align="justify">Procure no menu lateral esquerdo o ícone do SPRING BOOT DASHBOARD (logo verde do Spring ou um ícone de folha). Em APPS, você verá quickvote-api. Clique no botão de PLAY (Start) e aguarde o terminal carregar.</p>
```

```ad-quote
title:
###### **PARA TESTAR**
```

```ad-quote
title:
<p align="justify">Abra a extensão THUNDER CLIENT (ícone de raio à esquerda). Clique em NEW REQUEST. Digite a URL abaixo e clique em SEND.</p>
```

```plaintext
http://localhost:8080/status
```

```ad-quote
title:
<p align="justify">Se retornar a mensagem QuickVote API está rodando com sucesso!, parabéns! Sua estrutura está profissional, modularizada e pronta para iniciar o desenvolvimento.</p>
```

````

---

>[!done] **_New_**

---

````ad-quote
title:
##### **06 ) -** Git Ignore

```bash
# -------------------
# Compilados Java
# -------------------
*.class
*.log
*.ctxt

# Pacotes e executáveis
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar

# -------------------
# Visual Studio Code
# -------------------
.vscode/*
# !.vscode/settings.json    # Descomente se quiser impor configurações de projeto (ex: formatação) a todos
!.vscode/tasks.json       # Tarefas de build compartilhadas
!.vscode/launch.json      # Configurações de Debug compartilhadas
!.vscode/extensions.json  # Recomendações de extensões (muito importante para seu setup)
*.code-workspace

# Histórico local (Plugin Local History)
.history/

# -------------------
# Java Tooling (VS Code usa Eclipse por baixo dos panos)
# -------------------
.classpath
.project
.settings/
bin/

# -------------------
# Maven
# -------------------
target/
pom.xml.tag
pom.xml.releaseBackup
pom.xml.versionsBackup
pom.xml.next
release.properties
dependency-reduced-pom.xml
buildNumber.properties
.mvn/timing.properties
.mvn/wrapper/maven-wrapper.properties

# -------------------
# Gradle
# -------------------
.gradle/
build/
!gradle/wrapper/gradle-wrapper.jar
.gradletasknamecache

# -------------------
# IntelliJ IDEA (Caso alguém da equipe use)
# -------------------
.idea/
*.iml
*.iws
*.ipr
out/

# -------------------
# Arquivos de Sistema
# -------------------
.DS_Store
Thumbs.db
ehthumbs.db
Desktop.ini

# -------------------
# Variáveis de Ambiente e Segredos
# -------------------
.env
.env.local
```

````

---
