# SQL (Structured Query Language)

[VOLTAR](/readme.md)

SQL (Structured Query Language) é uma linguagem de programação usada para gerenciar sistemas de gerenciamento de banco de dados relacionais (SGBD). Ela é usada para criar, modificar e consultar bancos de dados. Existem quatro categorias principais de comandos SQL:

## DDL (Data Definition Language)

A Linguagem de Definição de Dados (DDL) é usada para definir a estrutura do banco de dados, como tabelas, índices, restrições e outros objetos de esquema. Alguns dos comandos DDL mais comuns incluem:

CREATE TABLE: Usado para criar uma nova tabela no banco de dados.

ALTER TABLE: Usado para modificar a estrutura de uma tabela existente.

DROP TABLE: Usado para excluir uma tabela do banco de dados.

CREATE INDEX: Usado para criar índices em colunas de tabelas para melhorar o desempenho de consultas.

## DML (Data Manipulation Language)

A Linguagem de Manipulação de Dados (DML) é usada para inserir, atualizar e excluir dados em uma tabela. Alguns dos comandos DML mais comuns incluem:

INSERT: Usado para adicionar novos registros a uma tabela.

UPDATE: Usado para modificar os dados em registros existentes.

DELETE: Usado para excluir registros de uma tabela.

## DQL (Data Query Language)

A Linguagem de Consulta de Dados (DQL) é usada para recuperar informações de um banco de dados. O principal comando DQL é o SELECT, que permite extrair dados de uma ou mais tabelas. O SQL SELECT permite filtrar, ordenar e agrupar dados de acordo com critérios específicos. Por exemplo:

```sql
SELECT * FROM tabela WHERE condição;
SELECT coluna1, coluna2 FROM tabela ORDER BY coluna1;
```

Essas três categorias de comandos SQL são fundamentais para gerenciar eficazmente um banco de dados relacional, desde a definição da estrutura do banco de dados até a manipulação e recuperação de dados.
