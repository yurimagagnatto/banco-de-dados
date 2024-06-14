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

1. Crie 5 registros na tabela livros
2. Crie 5 registros na tabela autores
3. Crie 5 registros na tabela membros
4. Crie 5 registros na tabela empréstimos
5. Crie 5 registros na tabela livros_autores
6. Atualize o ano de publicação do livro com id igual a 2 para 1885.
7. Atualize o nome do autor com id igual a 1 para "Joaquim Maria Machado de Assis".
8. Delete o membro com id igual a 1 da tabela membros.
9. Delete o empréstimo com id igual a 2 da tabela empréstimos.
10. Delete a associação entre o livro com id igual a 3 e o autor com id igual a 1 da tabela livros_autores.
11. Selecionar todos os livros.
12. Selecionar os livros com editora "Editora A".
13. Selecionar todos os autores.
14. Selecionar membros cujo nome começa com "João".
15. Selecionar livros cujo título contém a palavra "Casmurro".
16. Selecionar autores cujo nome termina com "Assis".
17. Selecionar livros cujo título começa com a letra "O".
18. Selecionar membros cujo endereço contém a palavra "Rua".
19. Selecionar todos os membros ordenados por nome.
20. Selecionar todos os dados da tabela autores ordenados por nome.
21. Contar o número de membros na tabela membros.
22. Selecionar os primeiros 5 membros na tabela membros.
23. Selecionar o título e ano de publicação dos livros.
24. Selecionar os membros que nasceram antes de 1990.
25. Selecionar os membros que nasceram entre 1980 e 1990.
26. Selecionar o nome dos livros e dos autores.
27. Contar o número total de livros.
28. Contar quantos livros foram publicados depois de 2000.
29. Selecionar os livros publicados depois de 1900.
30. Selecionar o título do livro e o nome do autor do livro com id=1.
31. Selecionar o título do livro e a quantidade de empréstimos que cada livro teve (group).
32. Selecionar todos os empréstimos ainda não devolvidos e os nomes dos membros.
33. Selecionar o título do livro e o nome do autor dos livros em ordem decrescente de ano de publicação.
