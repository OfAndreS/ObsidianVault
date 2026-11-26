---
banner: "- FILES/Attachments/Pasted image 20261012205745.png"
banner-x: 50
banner-y: 35
banner-fade: 100
---

---
#### **Intro )** - Persistência e Banco de Dados no FastAPI 

```ad-quote
title: **Def**
**Summary:**
- ...
```

---
#### Configuração de sessão 
##### Arquivo .env

##### Arquivo database.py

#### CRUD básico




---
#### 📋 Checklist de Estudos - Tópicos a Cobrir

---

- [ ] **01 )** - Diferença conceitual entre Pydantic Schemas (validação de dados na borda da API) e SQLAlchemy Models (tabelas no banco)

---

- [ ] **02 )** - Criação da URL de conexão com o banco (`DATABASE_URL = "sqlite:///./sql_app.db"` ou PostgreSQL)

---

- [ ] **03 )** - Instanciação do `create_engine()` e configuração do `sessionmaker(autocommit=False, autoflush=False)`

---

- [ ] **04 )** - Declaração da classe base declarativa moderna com `class Base(DeclarativeBase)`

---

- [ ] **05 )** - Definição de modelos com tipos tipados do SQLAlchemy 2.0 (`Mapped[int] = mapped_column(primary_key=True)`)

---

- [ ] **06 )** - Modelagem de relacionamentos (1 para N e N para N) com `relationship()` e `ForeignKey()`

---

- [ ] **07 )** - Padrão de Injeção de Dependências da sessão com generator: função `get_db()` usando `yield` e bloco `finally: db.close()`

---

- [ ] **08 )** - Criação de registros com `db.add(item)` e confirmação atômica com `db.commit()` e `db.refresh(item)`

---

- [ ] **09 )** - Consultas no SQLAlchemy 2.0 com `db.execute(select(Model).where(...)).scalars().all()`

---

- [ ] **10 )** - Atualizações de registros e tratamento seguro de rollback com blocos `try/except`

---

- [ ] **11 )** - Exclusão de registros com `db.delete(item)` e `db.commit()`

---

- [ ] **12 )** - Introdução ao versionamento de esquemas de banco com migrações gerenciadas pelo **Alembic**

---
