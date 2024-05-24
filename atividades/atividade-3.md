# Atividade 3

[VOLTAR](/readme.md)

## Modelo Conceitual

![Modelo Conceitual](/imagens/atividade-3-modelo-conceitual.png)

## Modelo Lógico

![Modelo Lógico](/imagens/atividade-3-modelo-logico.png)

## Modelo Físico

```sql

CREATE DATABASE `eventos`;

USE `eventos`;

CREATE TABLE `locais` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(80) NOT NULL,
  `cidade` varchar(50) NOT NULL,
  `uf` char(2) NOT NULL,
  `logradouro` varchar(80) NOT NULL,
  `cep` char(8) NOT NULL,
  `numero` varchar(15) NOT NULL,
  `bairro` varchar(40) NOT NULL,
  `capacidade_maxima` int NOT NULL,
  PRIMARY KEY (`id`),
  INDEX (`nome`)
);

CREATE TABLE `eventos` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(80) NOT NULL,
  `data_inicio` datetime DEFAULT NULL,
  `local_id` int DEFAULT NULL,
  PRIMARY KEY (`id`),
  FOREIGN KEY (`local_id`) REFERENCES `locais` (`id`)
);

CREATE TABLE `participantes` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(60) NOT NULL,
  `cpf` char(11) NOT NULL,
  `email` varchar(60) NOT NULL,
  `telefone` char(11) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE INDEX (`cpf`),
  INDEX (`nome`),
  INDEX (`email`)
);

CREATE TABLE `inscricoes` (
  `id` int NOT NULL AUTO_INCREMENT,
  `data_inscricao` datetime NOT NULL,
  `status` enum('CANCELADO','CONFIRMADO','PENDENTE') NOT NULL,
  `evento_id` int NOT NULL,
  `participante_id` int NOT NULL,
  PRIMARY KEY (`id`),
  INDEX (`status`),
  INDEX (`data_inscricao`),
  UNIQUE INDEX (`evento_id`,`participante_id`),
  FOREIGN KEY (`evento_id`) REFERENCES `eventos` (`id`),
  FOREIGN KEY (`participante_id`) REFERENCES `participantes` (`id`)
);

```