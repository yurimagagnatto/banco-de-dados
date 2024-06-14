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

Crie 5 registros na tabela livros

Crie 5 registros na tabela autores

Crie 5 registros na tabela membros

Crie 5 registros na tabela emprestimos

Crie 5 registros na tabela livros_autores

Atualize o ano de publicação do livro com id igual a 2 para 1885.

Atualize o nome do autor com id igual a 1 para "Joaquim Maria Machado de Assis".

Delete o membro com id igual a 1 da tabela membros.

Delete o empréstimo com id igual a 2 da tabela emprestimos.

Delete a associação entre o livro com id igual a 3 e o autor com id igual a 1 da tabela livros_autores.

Selecionar todos os livros

Selecionar os livros com editora "Editora A"

Selecionar todos os autores

Selecionar membros cujo nome começa com "João"

Selecionar livros cujo título contém a palavra "Casmurro"

Selecionar autores cujo nome termina com "Assis"

Selecionar livros cujo título começa com a letra "O"

Selecionar membros cujo endereço contém a palavra "Rua"

Selecionar todos os membros ordenados por nome

Selecionar todos os dados da tabela autores ordenados por nome

Contar o número de membros na tabela membros

Selecionar os primeiros 5 membros na tabela membros

Selecionar o título e ano de publicação dos livros

Selecionar os membros que nasceram antes de 1990

Selecionar os membros que nasceram entre 1980 e 1990

Selecionar o nome dos livros e dos autores

Contar o número total de livros

Contar quantos livros foram publicados depois de 2000

Selecionar os livros publicados depois de 1900

Selecionar o título do livro e o nome do autor do livro com id=1

Selecionar o título do livro e a quantidade de empréstimos que cada livro teve (group)

Selecionar todos os empréstimos ainda não devolvidos e os nomes dos membros

Selecionar o título do livro e o nome do autor dos livros em ordem decrescente de ano de publicação
