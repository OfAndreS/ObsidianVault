
---

````ad-quote
title:

##### **Intro )** - Metadados e Comportamento

```ad-quote
title:
<p align="justify">Dominar as Annotations é dominar a linguagem do Spring. Encare as anotações não como código mas como Metadados que configuram o comportamento do framework em Tempo De Execução.</p>
```

```ad-quote
title:
###### **A Lógica dos Grupos:**
```

```ad-quote
title:
<p align="justify">O ecossistema divide-se em Injeção De Dependência, APIs Web e Persistência. Cada grupo atua em uma camada específica da arquitetura.</p>
```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **01 )** - O Núcleo: Container e Injeção

```ad-quote
title:
<p align="justify">Estas anotações controlam a criação e o ciclo de vida dos objetos Beans transformando classes comuns em componentes gerenciados.</p>
```

```ad-quote
title:
###### **Estereótipos e Wiring:**
```

```ad-quote
title:

|Anotação&nbsp; | Função Principal&nbsp; |
| :--- | :--- |
|**@Component**|A anotação Raiz. Indica que a classe é gerenciada pelo Spring.|
|**@Service**|Semanticamente indica Lógica De Negócio regras e validações.|
|**@Repository**|Acessa Dados e traduz exceções de banco para RuntimeExceptions do Spring.|
|**@RestController**|Fusão de Controller com ResponseBody. Serializa o retorno diretamente para JSON.|
|**@Autowired**|Realiza a Injeção De Dependência buscando um Bean compatível no contexto.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **02 )** - O Mundo Web: Spring MVC

```ad-quote
title:
<p align="justify">Mapeiam o protocolo HTTP para métodos Java definindo rotas e capturando dados de entrada.</p>
```

```ad-quote
title:
###### **Rotas e Inputs:**
```

```ad-quote
title:

|Recurso&nbsp; | Aplicação Prática&nbsp; |
| :--- | :--- |
|**@RestController**|Define que a classe é um Controlador e que o retorno dos métodos deve ser serializado (JSON), não uma página HTML.|

|Recurso&nbsp; | Aplicação Prática&nbsp; |
| :--- | :--- |
|**@GetMapping**|Atalho para requisições de Leitura.|
|**@PostMapping**|Atalho para requisições de Criação.|
|**@PutMapping**|Mapeia requisições para ATUALIZAÇÃO completa de um recurso.|
|**@DeleteMapping**|Mapeia requisições para a REMOÇÃO de um recurso.|
|**@PatchMapping**|Mapeia requisições para ATUALIZAÇÃO PARCIAL (modificar apenas um campo).|

|Recurso&nbsp; | Aplicação Prática&nbsp; |
| :--- | :--- |
|**@PathVariable**|Extrai valores diretamente da URL ex: ID em /usuarios/5.|
|**@RequestParam**|Extrai parâmetros de consulta da URL ex: ?termo=java.|

|Recurso&nbsp; | Aplicação Prática&nbsp; |
| :--- | :--- |
|**@Valid**|Ativa a validação automática dos campos (usado junto com o @RequestBody).|
|**@RequestBody**|Converte o JSON do corpo da requisição para um Objeto Java.|
```
````

```txt

Enquanto o @PathVariable compõe a estrutura da URL exigindo o dado explicitamente, o @RequestParam oferece maior flexibilidade através de Query Parameters. Ao utilizar @RequestParam(required = false), é possível omitir parâmetros na requisição, permitindo que um único endpoint sirva tanto para buscas abrangentes quanto para filtragens específicas.
  
```

---

> [!done] **_New_**

---

````ad-quote
title:

##### **03 )** - Persistência e Boot

```ad-quote
title:
<p align="justify">A união do padrão JPA para mapeamento de banco com a configuração automática do Spring Boot.</p>
```

```ad-quote
title:
###### **Dados e Configuração:**
```

```ad-quote
title:

|Anotação&nbsp; | Contexto&nbsp; |
| :--- | :--- |
|**@Entity**|Marca a classe como Tabela Do Banco no padrão JPA.|
|**@Transactional**|Crítica para integridade. Garante o Commit se tudo der certo ou Rollback automático em caso de erro.|
|**@SpringBootApplication**|A anotação Mãe. Habilita a autoconfiguração e o escaneamento de componentes.|
|**@Valid**|Ativa a validação de dados DTO impedindo a entrada de valores nulos ou inválidos.|

```
````

---

> [!done] **_New_**

---

````ad-quote
title:

##### **Conclusão )** - Fluxo Arquitetural

```ad-quote
title:
<p align="justify">As anotações orquestram o fluxo de dados desde a chegada da requisição até o banco de dados.</p>
```



```ad-quote
title:

|Camada&nbsp; | Fluxo de Execução&nbsp; |
| :--- | :--- |
|**Controller**|Recebe a requisição via @RestController e valida o input com @Valid.|
|**Service**|É injetado no Controller via @Autowired e executa a regra de negócio com @Transactional.|
|**Repository**|É chamado pelo Service e acessa a @Entity para persistir os dados.|

```
````

---