# Atividade 4

[VOLTAR](/readme.md)

## Contexto: Sistema de Gerenciamento de Biblioteca

### Tabelas

- **livros**: Armazena informações sobre os livros disponíveis na biblioteca.

- **autores**: Armazena informações sobre os autores dos livros.

- **membros**: Armazena informações sobre os membros da biblioteca.

- **emprestimos**: Armazena informações sobre os empréstimos de livros realizados pelos membros.

- **livros_autores**: Tabela associativa para modelar a relação muitos-para-muitos entre livros e autores.

### Relacionamentos

- Um livro pode ter vários autores (relação muitos-para-muitos entre livros e autores, através da tabela livros_autores).

- Um membro pode emprestar vários livros, e um livro pode ser emprestado por vários membros ao longo do tempo (relação muitos-para-muitos entre livros e membros, através da tabela emprestimos).

## Modelo de Banco de Dados

### Tabela: livros

- **id** (Primary Key)

- titulo

- ano_publicacao

- editora

### Tabela: autores

- **id** (Primary Key)

- nome

- data_nascimento

### Tabela: membros

- **id** (Primary Key)

- nome

- data_nascimento

- endereco

### Tabela: emprestimos

- **id** (Primary Key)

- livro_id (Foreign Key)

- membro_id (Foreign Key)

- data_emprestimo

- data_devolucao

### Tabela: livros_autores

- **id** (Primary Key)

- livro_id (Foreign Key)

- autor_id (Foreign Key)

## Relacionamentos

- livros_autores: Tabela associativa para modelar a relação muitos-para-muitos entre livros e autores.

  - **id** (Primary Key)

  - livro_id (Foreign Key)

  - autor_id (Foreign Key)

- **emprestimos**: Tabela que modela a relação muitos-para-muitos entre livros e membros, com colunas adicionais para armazenar as datas de empréstimo e devolução.

  - **id** (Primary Key)

  - livro_id (Foreign Key)

  - membro_id (Foreign Key)

  - data_emprestimo

  - data_devolucao

## Exercícios

1. Crie o banco de dados "Biblioteca".
2. Crie a tabela "livros".
3. Crie a tabela "autores".
4. Crie a tabela "membros".
5. Crie a tabela "empréstimos".
6. Crie a tabela "livros_autores".
7. Crie 5 registros na tabela livros.
8. Crie 5 registros na tabela autores.
9. Crie 5 registros na tabela membros.
10. Crie 5 registros na tabela empréstimos.
11. Crie 5 registros na tabela livros_autores.
12. Atualize o ano de publicação do livro com id igual a 2 para 1885.
13. Atualize o nome do autor com id igual a 1 para "Joaquim Maria Machado de Assis".
14. Delete o membro com id igual a 1 da tabela membros.
15. Delete o empréstimo com id igual a 2 da tabela empréstimos.
16. Delete a associação entre o livro com id igual a 3 e o autor com id igual a 1 da tabela livros_autores.
17. Selecionar todos os livros.
18. Selecionar os livros com editora "Editora A".
19. Selecionar todos os autores.
20. Selecionar membros cujo nome começa com "João".
21. Selecionar livros cujo título contém a palavra "Casmurro".
22. Selecionar autores cujo nome termina com "Assis".
23. Selecionar livros cujo título começa com a letra "O".
24. Selecionar membros cujo endereço contém a palavra "Rua".
25. Selecionar todos os membros ordenados por nome.
26. Selecionar todos os dados da tabela autores ordenados por nome.
27. Contar o número de membros na tabela membros.
28. Selecionar os primeiros 5 membros na tabela membros.
29. Selecionar o título e ano de publicação dos livros.
30. Selecionar os membros que nasceram antes de 1990.
31. Selecionar os membros que nasceram entre 1980 e 1990.
32. Selecionar o nome dos livros e dos autores.
33. Contar o número total de livros.
34. Contar quantos livros foram publicados depois de 2000.
35. Selecionar os livros publicados depois de 1900.
36. Selecionar o título do livro e o nome do autor do livro com id=1.
37. Selecionar o título do livro e a quantidade de empréstimos que cada livro teve (group).
38. Selecionar todos os empréstimos ainda não devolvidos e os nomes dos membros.
39. Selecionar o título do livro e o nome do autor dos livros em ordem decrescente de ano de publicação.
40. Selecionar os autores que têm mais de 2 livros na tabela (group e having).