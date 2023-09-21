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
<!-- ____________________________________________________________________________ -->

## insert
## produtos


```sql

INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUES('ultrabook',
'Ultrabook Asus Intel Core i9'
6500.99
7,
1
);
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)VALUES(
'geladeira',
'FrostFree com acesso a internet'
8500.99,
10,
6 --Brastemp
);
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)VALUES(
'Tablet Android',
'Tablet 10 Polegadas com 256Gb de armazenamento'
4999,
3,
5 --samsung
);
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)VALUES(
'Iphone 14 pro max',
'processador bionic 15 com 512Gb de armazenamento'
4999,
3,
3 --Apple
);
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)VALUES(
'Ipad mini',
'Tablet com tela de retina 4k com 512Gb de armazenamento'
5000,
8,
3 --Apple
);


```


