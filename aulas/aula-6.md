# DDL (Data Definition Language)

[VOLTAR](/readme.md)

```sql
CREATE DATABASE IF NOT EXISTS `netflix`;

USE `netflix`;

CREATE TABLE IF NOT EXISTS `netflix`.`atores` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `nome` VARCHAR(80) NOT NULL,
  `data_nascimento` DATE NOT NULL,

  PRIMARY KEY (`id`)
);

CREATE TABLE IF NOT EXISTS `netflix`.`filmes` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `titulo` VARCHAR(80) NOT NULL,
  `data_lancamento` DATE NOT NULL,
  `sinopse` VARCHAR(100) NULL DEFAULT NULL,
  `duracao_minutos` INT NOT NULL,

  PRIMARY KEY (`id`),

  INDEX (`titulo`)
);

CREATE TABLE IF NOT EXISTS `netflix`.`filmes_atores` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `filme_id` INT NOT NULL,
  `ator_id` INT NOT NULL,

  PRIMARY KEY (`id`),

  UNIQUE INDEX (`filme_id`, `ator_id`),
  
  FOREIGN KEY (`filme_id`) REFERENCES `filmes` (`id`) ON DELETE RESTRICT ON UPDATE RESTRICT,

  FOREIGN KEY (`ator_id`) REFERENCES `atores` (`id`) ON DELETE RESTRICT ON UPDATE RESTRICT
);
```
