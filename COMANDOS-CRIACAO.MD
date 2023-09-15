# comandos SQL - Referência
 <!--___________________________________________________________________________  -->
## Modelagem físicas 

### Criar banco de dados 

```sql

CREATE DATABASE vendas CHARACTER SET  utf8mb4;

```

<!-- ____________________________________________________________________________ -->

### Criar a tabela fabricantes

```sql
CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
)


```
<!-- ____________________________________________________________________________ -->

### Criar a tabela produtos

```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT (1000)NOT NULL,
    preco DECIMAL(6,2) NOT NULL,
    quantidade TINYINT(4) NOT NULL,
)



```
<!-- ____________________________________________________________________________ -->

### Adicionar campo/coluna em uma tabela

```sql

ALTER TABLE produtos ADD fabricante_id INT NOT NULL
AFTER quantidade

```
<!-- ____________________________________________________________________________ -->

### Adicionar campo/coluna em uma tabela

```sql

ALTER TABLE produtos
# CONSTRAINT é uma restrição definida no relacionamento
ADD CONSTRAINT fk_produtos_fabricantes

# A chave estrangeira deve fazer referência a chave primeira 
FOREING KEY(quantidade) REFERENCES fabricantes(id)

```
