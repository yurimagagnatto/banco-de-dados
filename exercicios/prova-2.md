# Prova 2 - SQL (MySQL)

[VOLTAR](/readme.md)

Considere o diagrama entidade-relacionamento apresentado abaixo, representando o banco de dados de um sistema de gerenciamento de uma empresa de eventos.

## Diagrama entidade-relacionamento

![Diagrama entidade-relacionamento](/diagrama.png)

## Relações

### Relação 1:n entre Locais e Eventos

Um local pode hospedar vários eventos, mas cada evento ocorre em um único local.

### Relação n:n entre Eventos e Participantes (via tabela Inscrições)

Um evento pode ter vários participantes, e um participante pode se inscrever em vários eventos. Essa relação é gerenciada pela tabela Inscrições.

## Observações Adicionais

A tabela Inscrições não só facilita a relação muitos-para-muitos, mas também armazena informações específicas sobre cada inscrição, como a data de inscrição e o status.

As chaves estrangeiras garantem a integridade referencial entre as tabelas.

## Exercícios

Com base no modelo lógico fornecido acima, responda aos exercícios a seguir, utilizando os comandos SQL necessários para executar cada ação solicitada. Cada questão tem o mesmo peso (0.5 ponto).

1. Crie o banco de dados `empresa_eventos`.
    ```sql
    CREATE DATABASE empresa_eventos;
    ```

2. Execute o comando para começar a utilizar o banco de dados `empresa_eventos`.
    ```sql
    USE empresa_eventos;
    ```

3. Crie a tabela `locais`.
    ```sql
    CREATE TABLE locais
    (
    -- columns
    id INT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(80) NOT NULL,
    capacidade INT NOT NULL,
    endereco VARCHAR(255) NOT NULL,

    -- indexes
    PRIMARY KEY (id)
    );
    ```

4. Crie a tabela `eventos`.
    ```sql
    CREATE TABLE eventos
    (
    -- columns
    id INT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(80) NOT NULL,
    descricao TEXT NULL,
    data_inicio DATETIME NOT NULL,
    local_id INT NOT NULL,

    -- indexes
    PRIMARY KEY (id),

    -- foreign keys
    FOREIGN KEY (local_id) REFERENCES locais (id)
    );
    ```

5. Crie a tabela `participantes`.
    ```sql
    CREATE TABLE participantes
    (
    -- columns
    id INT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(80) NOT NULL,
    celular CHAR(11) NOT NULL,
    email VARCHAR(60) NULL,
    cpf CHAR(11) NOT NULL,
    data_nascimento DATE NOT NULL,
    empresa VARCHAR(80) NULL,

    -- indexes
    PRIMARY KEY (id)
    );
    ```

6. Crie a tabela `inscrições`.
    ```sql
    CREATE TABLE inscricoes
    (
    -- columns
    id INT NOT NULL AUTO_INCREMENT,
    evento_id INT NOT NULL,
    participante_id INT NOT NULL,
    data_inscricao DATETIME NOT NULL,
    status ENUM('PENDENTE', 'CANCELADO', 'CONFIRMADO') NOT NULL DEFAULT 'PENDENTE',

    -- indexes
    PRIMARY KEY (id),

    -- foreign keys
    FOREIGN KEY (evento_id) REFERENCES eventos (id),
    FOREIGN KEY (participante_id) REFERENCES participantes (id)
    );
    ```

7. Insira pelo menos 5 registros na tabela `locais`.
    ```sql
    INSERT INTO locais (nome, capacidade, endereco) VALUES
    ('Local A', 200, 'Endereco A'),
    ('Local B', 150, 'Endereco B'),
    ('Local C', 300, 'Endereco C'),
    ('Local D', 180, 'Endereco D'),
    ('Local E', 250, 'Endereco E');
    ```

8. Insira pelo menos 5 registros na tabela `eventos`.
    ```sql
    INSERT INTO eventos (nome, descricao, data_inicio, local_id) VALUES
    ('Evento 1', 'Descrição do Evento 1', '2023-01-01 10:00:00', 1),
    ('Evento 2', 'Descrição do Evento 2', '2023-02-15 15:30:00', 2),
    ('Evento 3', 'Descrição do Evento 3', '2023-03-20 18:45:00', 3),
    ('Evento 4', 'Descrição do Evento 4', '2023-04-05 14:00:00', 4),
    ('Evento 5', 'Descrição do Evento 5', '2023-05-10 12:00:00', 5);
    ```

9. Insira pelo menos 5 registros na tabela `participantes`.
    ```sql
    INSERT INTO participantes (nome, celular, email, cpf, data_nascimento, empresa) VALUES
    ('Participante 1', '11111111111', 'participante1@email.com', '12345678901', '1990-03-15', 'Empresa A'),
    ('Participante 2', '22222222222', 'participante2@email.com', '23456789012', '1991-05-20', 'Empresa B'),
    ('Participante 3', '33333333333', 'participante3@email.com', '34567890123', '1992-08-10', 'Empresa C'),
    ('Participante 4', '44444444444', 'participante4@email.com', '45678901234', '1993-11-25', 'Empresa D'),
    ('Participante 5', '55555555555', 'participante5@email.com', '56789012345', '1994-04-03', 'Empresa E');
    ```

10. Insira pelo menos 5 registros na tabela `inscrições`.
    ```sql
    INSERT INTO inscricoes (evento_id, participante_id, data_inscricao, status) VALUES
    (1, 1, '2023-01-01 08:30:00', 'CONFIRMADO'),
    (2, 2, '2023-02-10 14:20:00', 'PENDENTE'),
    (3, 3, '2023-03-18 17:45:00', 'CONFIRMADO'),
    (4, 4, '2023-04-02 10:10:00', 'CANCELADO'),
    (5, 5, '2023-05-05 11:30:00', 'CONFIRMADO');
    ```

11. Edite o telefone de um participante através do seu `id`.
    ```sql
    UPDATE participantes SET celular = '99999999999' WHERE id = 1;
    ```

12. Exclua uma inscrição específica.
    ```sql
    DELETE FROM inscricoes WHERE id = 2;
    ```

13. Selecione as colunas nome, data de nascimento e telefone da tabela `participantes`.
    ```sql
    SELECT nome, data_nascimento, celular FROM participantes;
    ```

14. Selecione todos os eventos ordenados por data de início (do mais recente para o mais antigo).
    ```sql
    SELECT * FROM eventos ORDER BY data_inicio DESC;
    ```

15. Conte quantas inscrições com status confirmado houve em um evento específico (através do id do evento).
    ```sql
    SELECT COUNT(*) FROM inscricoes WHERE evento_id = 1 AND status = 'CONFIRMADO';
    ```

16. Liste todos os participantes que nasceram em 1991.
    ```sql
    SELECT * FROM participantes WHERE YEAR(data_nascimento) = 1991;
    ```

17. Selecione todos os eventos que ainda não aconteceram (data de início maior que a data atual).
    ```sql
    SELECT * FROM eventos WHERE data_inicio > NOW();
    ```

18. Selecione todos os participantes que têm `Silva` no nome e ordene em ordem alfabética.
    ```sql
    SELECT * FROM participantes WHERE nome LIKE '%Silva%' ORDER BY nome;
    ```

19. Selecione todos os eventos e o nome e endereço do local de cada evento (join).
    ```sql
    SELECT eventos.*, locais.nome AS nome_local, locais.endereco AS endereco_local
    FROM eventos
    JOIN locais ON eventos.local_id = locais.id;
    ```

20. Exclua o banco de dados `empresa_eventos`.
    ```sql
    DROP DATABASE empresa_eventos;
    ```
