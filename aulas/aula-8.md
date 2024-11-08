# DML (Data Manipulation Language)

[VOLTAR](/readme.md)

## Inserir um registro em uma tabela

```sql
INSERT INTO `nome_da_tabela` (`coluna_1`, `coluna_2`, `coluna_3`)
VALUES ('valor 1', 'valor 2', 'valor 3');
```

## Inserir vários registros em uma tabela de uma só vez

```sql
INSERT INTO `nome_da_tabela` (`coluna_1`, `coluna_2`, `coluna_3`)
VALUES ('valor 1', 'valor 2', 'valor 3'),
('valor 1', 'valor 2', 'valor 3'),
('valor 1', 'valor 2', 'valor 3');
```

## Editar um registro ou vários registros

```sql
UPDATE `nome_da_tabela`
SET `coluna_1` = 'valor 1', `coluna_2` = 'valor 2'
WHERE `id` = 1;
```

Caso a condição (WHERE) não seja passada, todos os registros serão alterados!

## Deletar um ou vários registros

```sql
DELETE FROM `nome_da_tabela`
WHERE `id` = 1;
```

## Truncate

O comando TRUNCATE no SQL é usado para remover rapidamente todos os registros de uma tabela, redefinindo-a ao estado vazio sem afetar sua estrutura.

```sql
TRUNCATE TABLE nome_da_tabela;
```