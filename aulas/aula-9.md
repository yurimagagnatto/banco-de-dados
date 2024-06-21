# DQL (Data Query Language) - Linguagem de Consulta de Dados em MySQL

[VOLTAR](/readme.md)

A Linguagem de Consulta de Dados (DQL) em MySQL, por meio de instruções SELECT, permite recuperar e manipular dados de tabelas. Abaixo estão algumas operações e conceitos fundamentais:

## SELECT Statement

A instrução SELECT é utilizada para recuperar dados de uma ou mais tabelas. Pode-se especificar colunas específicas ou selecionar todas usando o caractere "*".

```sql
-- Seleciona todas as colunas da tabela
SELECT * FROM nome_da_tabela;

-- Seleciona colunas específicas da tabela
SELECT nome_da_coluna_1, nome_da_coluna_2 FROM nome_da_tabela;
```

## DISTINCT

A cláusula DISTINCT é usada para selecionar valores distintos de uma coluna.

```sql
-- Seleciona valores distintos da coluna
SELECT DISTINCT nome_da_coluna FROM nome_da_tabela;
```

## ALIASES

Aliases permitem atribuir nomes temporários a colunas ou tabelas para tornar as consultas mais legíveis.

```sql
-- Alias para colunas
SELECT nome_da_coluna_1 AS nome_personalizado_1, nome_da_coluna_2 AS nome_personalizado_2 FROM nome_da_tabela;

-- Alias para tabela
SELECT * FROM nome_da_tabela AS nome_personalizado_da_tabela;
```

## FUNCTIONS

Funções agregadas realizam cálculos em conjuntos de dados. Exemplos incluem COUNT(), MAX(), MIN(), SUM() e AVG().

```sql
-- Contagem de registros
SELECT COUNT(nome_da_coluna) FROM nome_da_tabela;

-- Maior valor
SELECT MAX(nome_da_coluna) FROM nome_da_tabela;

-- Soma dos valores
SELECT SUM(nome_da_coluna) FROM nome_da_tabela;

-- Média dos valores
SELECT AVG(nome_da_coluna) FROM nome_da_tabela;
```

## WHERE Clause

A cláusula WHERE é usada para filtrar registros com base em condições específicas.

```sql
-- Igualdade
SELECT * FROM tabela WHERE coluna = 1;

-- Maior que
SELECT * FROM tabela WHERE coluna > 1;

-- Menor que
SELECT * FROM tabela WHERE coluna < 1;

-- Diferente de
SELECT * FROM tabela WHERE coluna <> 1;

-- Intervalo
SELECT * FROM tabela WHERE coluna BETWEEN 1 AND 2;

-- Padrão específico
SELECT * FROM tabela WHERE coluna LIKE "_palavra%";

-- Verificar se é NULL
SELECT * FROM tabela WHERE coluna IS NULL;

-- Verificar se não é NULL
SELECT * FROM tabela WHERE coluna IS NOT NULL;
```

## IN, AND, OR, NOT

Operadores lógicos e de comparação ampliam as capacidades de filtragem.

```sql
-- IN
SELECT * FROM tabela WHERE coluna IN (valor_1, valor_2);

-- OR
SELECT * FROM tabela WHERE coluna_1 = 1 OR coluna_2 = 2;

-- AND
SELECT * FROM tabela WHERE coluna_1 = 1 AND coluna_2 = 2;

-- NOT
SELECT * FROM tabela WHERE NOT coluna = 1;
```

## ORDER BY Clause

A cláusula ORDER BY classifica os resultados em ordem crescente (ASC) ou decrescente (DESC) com base em uma coluna.

```sql
-- Ordem crescente
SELECT * FROM tabela ORDER BY coluna_2 ASC;

-- Ordem decrescente
SELECT * FROM tabela ORDER BY coluna_2 DESC;
```

## LIMIT Clause

A cláusula LIMIT restringe o número de registros retornados.

```sql
-- Limita a 2 registros
SELECT * FROM tabela LIMIT 2;

-- Limita a 2 registros a partir do registro 0
SELECT * FROM tabela LIMIT 0, 2;
```

## JOIN Clause

A cláusula JOIN combina registros de tabelas diferentes com base em relações.

```sql
-- INNER JOIN
SELECT * FROM tabela_1 INNER JOIN tabela_2 ON tabela_1.coluna_x = tabela_2.coluna_y;

-- LEFT JOIN
SELECT * FROM tabela_1 LEFT JOIN tabela_2 ON tabela_1.coluna_x = tabela_2.coluna_y;

-- RIGHT JOIN
SELECT * FROM tabela_1 RIGHT JOIN tabela_2 ON tabela_1.coluna_x = tabela_2.coluna_y;
```

## GROUP BY e HAVING

As cláusulas GROUP BY e HAVING são usadas para agrupar registros com base em valores de coluna.

```sql
-- Agrupamento por coluna
SELECT COUNT(coluna) FROM tabela GROUP BY coluna;

-- Agrupamento com condição
SELECT COUNT(coluna) FROM tabela GROUP BY coluna HAVING COUNT(coluna) > 2;
```

## VIEW

Views são tabelas virtuais baseadas em consultas predefinidas.

```sql
-- Criar uma view
CREATE VIEW nome_da_view AS SELECT * FROM tabela WHERE coluna < 100 LIMIT 5;

-- Selecionar dados da view
SELECT * FROM nome_da_view;
```
