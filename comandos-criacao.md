# Comandos SQL - Referencia
<!-- _________________________________________________________________ -->
## Modelagem fisica

### Criar banco de dados 
```sql
CREATE DATABASE vendas CHARACTER SET utf8mb4;
```

<!-- _________________________________________________________________ -->

### Criar a tabela fabricantes
```sql
CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
)

```
<!-- _________________________________________________________________ -->

### Criar a tabela produtos
```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    preco DECIMAL(6,2) NOT NULL,
    quantidade TINYINT(4) NOT NULL
)

```
<!-- _________________________________________________________________ -->

### Adicionar campo/coluna em uma tabela

```sql

ALTER TABLE produtos ADD fabricantes_id INT NOT NULL
AFTER quantidade;

```
<!-- _________________________________________________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)

```sql

ALTER TABLE produtos
    # CONSTRAINT é uma restrição definida no relacionamento
    ADD CONSTRAINT fk_produtos_fabricantes

    # A chave estrangeira deve fazer referencia a chave primaria
FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id)

```