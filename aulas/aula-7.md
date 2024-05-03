# DDL (Data Definition Language)

[VOLTAR](/readme.md)

## Criar um banco de dados

```sql
CREATE DATABASE `nome_do_banco_de_dados`;
```

## Deletar um banco de dados

```sql
DROP DATABASE `nome_do_banco_de_dados`;
```

## Setar um banco de dados para ser usado

```sql
USE `nome_do_banco_de_dados`;
```

## Criar uma tabela

Criando uma tabela com várias colunas (de tipos diferentes) e com uma chave primária auto incrementável.

```sql
CREATE TABLE `nome_do_banco_de_dados`.`nome_da_tabela` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `coluna_2` CHAR(2) NOT NULL,
  `coluna_3` VARCHAR(80) NOT NULL,
  `coluna_4` TEXT,
  `coluna_5` DATE,
  `coluna_6` TIME,
  `coluna_7` DATETIME,
  `coluna_8` FLOAT NOT NULL,

  PRIMARY KEY (`id`)
);
```

## Deletar uma tabela

```sql
DROP TABLE `nome_do_banco_de_dados`;
```

## Exemplo de como criar uma tabela com chave estrangeira

A segunda tabela tem uma coluna "chave estrangeira" que faz referência para a chave primária da primeira tabela.

```sql
CREATE TABLE `nome_do_banco_de_dados`.`tabela_1` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `coluna_2` VARCHAR(80) NOT NULL,

  PRIMARY KEY (`id`)
);

CREATE TABLE `nome_do_banco_de_dados`.`tabela_2` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `tabela_1_id` INT,

  PRIMARY KEY (`id`),

  FOREIGN KEY (`tabela_1_id`) REFERENCES `tabela_1` (`id`) ON DELETE RESTRICT ON UPDATE RESTRICT
);
```

## Criando uma coluna com índice

```sql
CREATE TABLE `nome_do_banco_de_dados`.`tabela` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `titulo` VARCHAR(80) NOT NULL,

  PRIMARY KEY (`id`),

  INDEX (`titulo`)
);
```

## Criando uma coluna que armazena registros únicos

```sql
CREATE TABLE IF NOT EXISTS `nome_do_banco_de_dados`.`tabela` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `nome` VARCHAR(80) NOT NULL,
  `cpf` VARCHAR(11) NOT NULL,

  PRIMARY KEY (`id`),

  UNIQUE (`cpf`)
);
```

## Deletar uma coluna de uma tabela

```sql
ALTER TABLE `nome_do_banco_de_dados`.`tabela`
DROP COLUMN `coluna`;
```

## Adicionar uma coluna a uma tabela existente

```sql
ALTER TABLE `nome_do_banco_de_dados`.`tabela`
ADD `coluna` INT;
```

## Modificar uma coluna de uma tabela existente

```sql
ALTER TABLE `nome_do_banco_de_dados`.`tabela`
MODIFY COLUMN `coluna` VARCHAR(80);
```

## Adicionar uma chave estrangeira a uma tabela existente

`nome_da_chave_estrangeira` é opcional, caso não seja passado será gerado um nome automáticamente.

```sql
ALTER TABLE `nome_do_banco_de_dados`.`tabela_2`
ADD FOREIGN KEY `nome_da_chave_estrangeira` (`tabela_1_id`) REFERENCES `tabela_1` (`id`) ON DELETE RESTRICT ON UPDATE RESTRICT
```

## Deletar uma chave estrangeira

```sql
ALTER TABLE `nome_do_banco_de_dados`.`tabela`
DROP FOREIGN KEY `nome_da_chave_estrangeira`;
```

## Criar índice

```sql
CREATE INDEX `nome_do_indice`
ON `nome_do_banco_de_dados`.`tabela` (`coluna`);
```

## Criar índice único

```sql
CREATE UNIQUE INDEX `nome_do_indice`
ON `nome_do_banco_de_dados`.`tabela` (`coluna`);
```

## Deletar um índice

```sql
ALTER TABLE `nome_do_banco_de_dados`.`tabela`
DROP INDEX `nome_do_indice`;
```

## Criar um índice composto (um mesmo índice para mais de uma coluna)

```sql
CREATE INDEX `nome_do_indice`
ON `nome_do_banco_de_dados`.`tabela` (`coluna_1`,`coluna_2`);
```
