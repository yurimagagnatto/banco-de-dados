# Prova 1

[VOLTAR](/readme.md)

## Enunciado

### Estudo de Caso: Sistema de Gerenciamento de Biblioteca

Uma biblioteca deseja criar um sistema de gerenciamento de biblioteca para rastrear informações sobre seus livros, autores, empréstimos e membros. Cada livro tem um título, um ISBN (International Standard Book Number), uma data de publicação e pode ser escrito por um ou mais autores. Cada autor tem um nome e uma data de nascimento. Cada membro da biblioteca possui um número de membro, um nome e um endereço. Um membro pode emprestar um ou mais livros da biblioteca. Um empréstimo é registrado com uma data de empréstimo e uma data de devolução prevista. Cada empréstimo é associado a um único membro e um ou mais livros.
 
### Instruções:
 
1. Crie um diagrama ER Modelo Conceitual (BRModelo) que represente as principais entidades, relacionamentos e atributos do sistema de gerenciamento de biblioteca.

2. Crie um diagrama ER Modelo Lógico (BRModelo) que detalhe como as entidades, relacionamentos e atributos do Modelo Conceitual serão implementados em tabelas de banco de dados. Certifique-se de incluir chaves primárias e estrangeiras, se necessário.

### Observações:

- Para cada entidade no Modelo Conceitual, liste os principais atributos que devem ser armazenados.

- Para cada relacionamento no Modelo Conceitual, descreva as cardinalidades mínimas e máximas.

- Nomeie todas as entidades, relacionamentos e atributos de forma clara e significativa.

## Resolução

Diagrama ER Modelo Conceitual e Diagrama ER Modelo Lógico para o sistema de gerenciamento de biblioteca.

### Modelo Conceitual

![Modelo lógico](/imagens/prova-1-1.png)

Entidades, relacionamentos e atributos do Modelo Conceitual.

#### Entidades:

1.  `Livro`

    -   Atributos:
        -   Título (string)
        -   ISBN (string)
        -   Data de Publicação (data)
2.  `Autor`

    -   Atributos:
        -   Nome (string)
        -   Data de Nascimento (data)
3.  `Membro da Biblioteca`

    -   Atributos:
        -   Número de Membro (string)
        -   Nome (string)
        -   Endereço (string)
4.  `Empréstimo`

    -   Atributos:
        -   Data de Empréstimo (data)
        -   Data de Devolução Prevista (data)

#### Relacionamentos:

1.  Um livro é escrito por um ou mais autores e um autor escreve um ou mais livros.

    -   Cardinalidade do relacionamento: Muitos para muitos (N:N).

2.  Um membro da biblioteca pode fazer nenhum ou vários empréstimos e um empréstimo está associado a um único membro.

    -   Cardinalidade do relacionamento: Um para muitos (1:N).

3.  Um empréstimo está associado a um ou mais livros e um livro pode ter sido emprestado várias vezes.

    -   Cardinalidade do relacionamento: Muitos para muitos (N:N).

### Modelo Lógico

Modelo Lógico com as chaves primárias e estrangeiras.

![Modelo lógico](/imagens/prova-1-2.png)

#### Tabelas:

1.  `Livro`

    -   Colunas:
        -   ID (Chave Primária)
        -   Título (string)
        -   ISBN (string)
        -   Data de Publicação (data)

2.  `Autor`

    -   Colunas:
        -   ID (Chave Primária)
        -   Nome (string)
        -   Data de Nascimento (data)

3.  `Membro da Biblioteca`

    -   Colunas:
        -   ID (Chave Primária)
        -   Número de Membro (string)
        -   Nome (string)
        -   Endereço (string)
        
4.  `Empréstimo`

    -   Colunas:
        -   ID (Chave Primária)
        -   Data de Empréstimo (data)
        -   Data de Devolução Prevista (data)
        -   Membro ID (Chave Estrangeira referenciando a tabela `Membro da Biblioteca`)

5.  `Livro Autor` (Tabela Associativa para o relacionamento entre as tabelas `Livro` e `Autor`)

    -   Colunas:
        -   ID (Chave Primária)
        -   Livro ID (Chave Estrangeira referenciando a tabela `Livro`)
        -   Autor ID (Chave Estrangeira referenciando a tabela `Autor`)

6.  `Empréstimo Livro` (Tabela Associativa para o relacionamento entre as tabelas `Empréstimo` e `Livro`)

    -   Colunas:
        -   ID (Chave Primária)
        -   Empréstimo ID (Chave Estrangeira referenciando a tabela `Empréstimo`)
        -   Livro ID (Chave Estrangeira referenciando a tabela `Livro`)

Neste Modelo Lógico, as chaves primárias estão indicadas com (Chave Primária) e as chaves estrangeiras estão indicadas com (Chave Estrangeira). Isso permite que as tabelas se relacionem e mantenham a integridade referencial entre os dados.

## Exemplo das tabelas do banco de dados com registros

Tabela `Livro`:

| ID | Título | ISBN | Data de Publicação |
| --- | --- | --- | --- |
| 1 | Dom Casmurro | 978-123456789 | 1899-01-01 |
| 2 | A Moreninha | 978-987654321 | 1844-05-15 |
| 3 | Harry Potter e a Pedra Filosofal | 978-555555555 | 1997-06-26 |
| 4 | O Senhor dos Anéis | 978-333333333 | 1954-07-29 |
| 5 | O Pequeno Príncipe | 978-111111111 | 1943-04-06 |

Tabela `Autor`:

| ID | Nome | Data de Nascimento |
| --- | --- | --- |
| 1 | Machado de Assis | 1839-06-21 |
| 2 | Joaquim Manuel de Macedo | 1820-06-24 |
| 3 | Antoine de Saint-Exupéry | 1900-06-29 |
| 4 | J.K. Rowling | 1965-07-31 |
| 5 | J.R.R. Tolkien | 1892-01-03 |

Tabela `Empréstimo`:

| ID | Data de Empréstimo | Data de Devolução Prevista | Membro ID |
| --- | --- | --- | --- |
| 1 | 2023-10-10 | 2023-10-17 | 1 |
| 2 | 2023-10-15 | 2023-10-22 | 3 |
| 3 | 2023-10-20 | 2023-10-27 | 4 |

Tabela `Livro Autor`:

| ID | Livro ID | Autor ID |
| --- | --- | --- |
| 1 | 1 | 1 |
| 2 | 2 | 2 |
| 3 | 3 | 4 |
| 4 | 4 | 5 |
| 5 | 5 | 3 |

Tabela `Empréstimo Livro`:

| ID | Empréstimo ID | Livro ID |
| --- | --- | --- |
| 1 | 1 | 3 |
| 2 | 1 | 4 |
| 3 | 2 | 1 |
| 4 | 3 | 4 |
| 5 | 3 | 2 |
| 6 | 3 | 5 |

Tabela `Membro da Biblioteca`:

| ID | Número de Membro | Nome | Endereço |
| --- | --- | --- | --- |
| 1 | MB-001 | João Silva | Rua Principal, 123 |
| 2 | MB-002 | Maria Santos | Avenida Central, 456 |
| 3 | MB-003 | Pedro Lima | Travessa da Paz, 789 |
| 4 | MB-004 | Ana Pereira | Praça da Liberdade, 1010 |
