# Prova 3 - SQL (MySQL) - SUB

Considere o diagrama entidade-relacionamento apresentado abaixo, representando o banco de dados de um sistema de gestão de cursos online.

## Diagrama entidade-relacionamento

![Diagrama entidade-relacionamento](/imagens/diagrama-prova-3.png)

## Tabelas

### categorias

- id (Chave primária, tipo INT, não nulo, autoincremento)
- nome (Tipo VARCHAR(80), não nulo)
- descricao (Tipo TEXT, permitindo valores nulos)

### cursos

- id (Chave primária, tipo INT, não nulo, autoincremento)
- nome (Tipo VARCHAR(80), não nulo)
- descricao (Tipo TEXT, permitindo valores nulos)
- categoria_id (Chave estrangeira, não nulo)

### estudantes

- id (Chave primária, tipo INT, não nulo, autoincremento)
- nome (Tipo VARCHAR(80), não nulo)
- email (Tipo VARCHAR(60), não nulo)
- cpf (Tipo CHAR(11), não nulo)
- celular (Tipo CHAR(11), permitindo valores nulos)
- data_nascimento (Tipo DATE, não nulo)

### matriculas

- id (Chave primária, tipo INT, não nulo, autoincremento)
- curso_id (Chave estrangeira, não nulo)
- estudante_id (Chave estrangeira, não nulo)
- data_matricula (Tipo DATETIME, não nulo)
- data_conclusao (Tipo DATETIME, permitindo valores nulos)
- nota_final (Tipo FLOAT, permitindo valores nulos)

## Exercícios

Com base no modelo lógico fornecido acima, responda aos exercícios a seguir, utilizando os comandos SQL necessários para executar cada ação solicitada.

1. Crie o banco de dados `escola_cursos_online`.

2. Execute o comando para começar a utilizar o banco de dados `empresa_eventos`.

3. Crie a tabela `categorias`.

    Explique cada coluna e seus tipos de dados.

4. Crie a tabela `cursos`.

    Explique cada coluna e seus tipos de dados.

    Essa tabela possui uma chave estrangeira. Explique o porquê de ela ser criada e qual o tipo de relação com a tabela `categorias`.

5. Crie a tabela `estudantes`.

    Explique cada coluna e seus tipos de dados.

6. Crie a tabela `matriculas`.

    Explique cada coluna e seus tipos de dados.

    Essa tabela é uma tabela associativa. Ela possui duas chaves estrangeiras. Explique o porquê de ela existir e qual o tipo de relação que ela torna possível entre `estudantes` e `cursos`.

7. Insira pelo menos 5 registros na tabela `categorias`. Explique o que representa cada coluna da tabela ao inserir um registro.

8. Insira pelo menos 5 registros na tabela `cursos`. Explique o que representa cada coluna da tabela ao inserir um registro.

9. Insira pelo menos 5 registros na tabela `estudantes`. Explique o que representa cada coluna da tabela ao inserir um registro.

10. Insira pelo menos 5 registros na tabela `matriculas`. Explique o que representa cada coluna da tabela ao inserir um registro.

11. Edite o telefone de um estudante através do seu `id`.

12. Exclua um estudante através do seu `id`.

13. Selecione todas as colunas da tabela `estudantes`.

14. Selecione as colunas nome, data de nascimento e telefone da tabela `estudantes`. Ordene pela data de nascimento, do mais novo para o mais velho.

15. Selecione todos os estudantes cujo nome começa com João. Ordene pelo nome em ordem alfabética.

16. Conte quantos estudantes existem na base de dados.

17. Selecione todas as matrículas iniciadas em novembro deste ano.

18. Selecione todas as matrículas que foram concluídas em dezembro deste ano, onde a nota foi igual ou superior a 9.

19. Selecione todas as matrículas junto (join) com o nome do estudante e o nome do curso (aqui são 2 joins, um com a tabela estudantes e outro com a tabela cursos).

20. Exclua o banco de dados `escola_cursos_online`.

Todas as questões devem estar corretas. Pode consultar qualquer tipo de material, Chat GPT, ajuda de outros alunos, etc.

Deve ser anexado junto à atividade um vídeo (não precisa gravar rosto, apenas a tela do computador e a voz) explicando `TODO` SQL de cada resposta (todas as 20 respostas devem ser explicadas no vídeo).

O vídeo deve ter no máximo 30 minutos.
