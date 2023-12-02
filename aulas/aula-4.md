# Modelo Físico

[VOLTAR](/readme.md)

O modelo físico é criado com base no modelo lógico e descreve as estruturas físicas de armazenamento de dados, incluindo tipos e tamanhos de campos, índices, restrições de preenchimento e outras especificações. Esta fase final do projeto de banco de dados envolve o uso da linguagem de definição de dados do SGBD, como o SQL.

## Exemplo de código SQL para a implementação do banco de dados utilizando o SGBD (sistema de gerenciamento de banco de dados) MySQL

```sql
CREATE DATABASE streaming_de_filmes;

USE streaming_de_filmes;

CREATE TABLE filmes
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  titulo VARCHAR(80),
  data_lancamento DATE,
  sinopse VARCHAR(255),
  duracao INT,

  -- indexes
  PRIMARY KEY (id),
  INDEX (titulo),
  INDEX (data_lancamento)
);

CREATE TABLE categorias
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  nome VARCHAR(60),
  descricao VARCHAR(255),

  -- indexes
  PRIMARY KEY (id),
  UNIQUE INDEX (nome)
);

CREATE TABLE filmes_categorias
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  filme_id INT,
  categoria_id INT,

  -- indexes
  PRIMARY KEY (id),
  UNIQUE INDEX (filme_id, categoria_id),

  -- foreign keys
  FOREIGN KEY (filme_id) REFERENCES filmes (id) ON DELETE RESTRICT ON UPDATE RESTRICT,

  FOREIGN KEY (categoria_id) REFERENCES categorias (id) ON DELETE RESTRICT ON UPDATE RESTRICT
);

CREATE TABLE usuarios
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  nome VARCHAR(80),
  email VARCHAR(40),
  cpf VARCHAR(11),

  -- indexes
  PRIMARY KEY (id),
  INDEX (nome),
  UNIQUE INDEX (cpf),
  UNIQUE INDEX (email)
); 

CREATE TABLE filmes_usuarios
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  usuario_id INT,
  filme_id INT,
  tempo_assistido INT,

  -- indexes
  PRIMARY KEY (id),
  UNIQUE INDEX (usuario_id, filme_id),

  -- foreign keys
  FOREIGN KEY (usuario_id) REFERENCES usuarios (id) ON DELETE RESTRICT ON UPDATE RESTRICT,

  FOREIGN KEY (filme_id) REFERENCES filmes (id) ON DELETE RESTRICT ON UPDATE RESTRICT
); 

CREATE TABLE avaliacoes
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  usuario_id INT,
  filme_id INT,
  nota INT,
  comentario VARCHAR(255),

  -- indexes
  PRIMARY KEY (id),

  -- foreign keys
  FOREIGN KEY (usuario_id) REFERENCES usuarios (id) ON DELETE RESTRICT ON UPDATE RESTRICT,

  FOREIGN KEY (filme_id) REFERENCES filmes (id) ON DELETE RESTRICT ON UPDATE RESTRICT
); 

CREATE TABLE atores
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  nome VARCHAR(80),
  data_nascimento DATE,

  -- indexes
  PRIMARY KEY (id),
  INDEX (nome),
  INDEX (data_nascimento)
);

CREATE TABLE filmes_atores
(
  -- columns
  id INT NOT NULL AUTO_INCREMENT,
  filme_id INT,
  ator_id INT,
  nome_personagem VARCHAR(80),

  -- indexes
  PRIMARY KEY (id),

  -- foreign keys
  FOREIGN KEY (filme_id) REFERENCES filmes (id) ON DELETE RESTRICT ON UPDATE RESTRICT,

  FOREIGN KEY (ator_id) REFERENCES atores (id) ON DELETE RESTRICT ON UPDATE RESTRICT
);
```

## Populando as tabelas criadas anteriormente

```sql
-- Inserts para a tabela filmes
INSERT INTO filmes (titulo, data_lancamento, sinopse, duracao)
VALUES
('O Poderoso Chefão', '1972-03-24', 'Um chefão do crime tenta transferir o controle de seu império para seu filho relutante.', 175),
('Interestelar', '2014-11-07', 'Um grupo de exploradores espaciais viaja através de um buraco de minhoca em busca de um novo lar para a humanidade.', 169),
('Gladiador', '2000-05-05', 'Um ex-general romano busca vingança contra o corrupto imperador que assassinou sua família e enviou-o para a escravidão.', 155),
('O Senhor dos Anéis: A Sociedade do Anel', '2001-12-19', 'Um hobbit relutante é encarregado de destruir um anel mágico que ameaça o mundo.', 178),
('Forrest Gump', '1994-07-06', 'A vida de um homem simples, mas notável, que testemunha e influencia vários eventos históricos nos Estados Unidos.', 142),
('Matrix', '1999-03-24', 'Um hacker descobre a verdadeira natureza da realidade e lidera um grupo de rebeldes contra máquinas que controlam o mundo.', 136),
('A Origem', '2010-07-16', 'Um ladrão especializado em invadir os sonhos das pessoas é contratado para realizar uma tarefa quase impossível.', 148),
('O Resgate do Soldado Ryan', '1998-07-24', 'Um grupo de soldados é enviado para resgatar um paraquedista cujos irmãos foram mortos em combate durante a Segunda Guerra Mundial.', 169),
('Cidade de Deus', '2002-08-30', 'Dois jovens crescem em favelas violentas do Rio de Janeiro e escolhem caminhos diferentes em suas vidas.', 130),
('A Lista de Schindler', '1993-12-15', 'Um empresário alemão salva a vida de mais de mil judeus durante o Holocausto.', 195),
('A Origem dos Guardiões', '2012-11-30', 'Os Guardiões, incluindo o Papai Noel e o Coelhinho da Páscoa, se unem para combater um vilão que ameaça o mundo.', 97),
('O Labirinto do Fauno', '2006-05-27', 'Durante a Guerra Civil Espanhola, uma jovem encontra um mundo mágico e perigoso em um labirinto.', 118),
('O Tigre e o Dragão', '2000-12-08', 'Em uma China antiga, guerreiros buscam uma espada lendária enquanto enfrentam desafios e traições.', 120),
('A Viagem de Chihiro', '2001-07-20', 'Uma menina é transportada para um mundo mágico habitado por espíritos e criaturas fantásticas.', 125),
('A Vida é Bela', '1997-12-20', 'Durante o Holocausto, um pai usa sua imaginação para proteger seu filho da terrível realidade de um campo de concentração.', 116),
('O Discurso do Rei', '2010-09-06', 'Um rei britânico com gagueira improvável contrata um terapeuta para ajudá-lo a superar suas limitações.', 118),
('La La Land: Cantando Estações', '2016-12-09', 'Um músico e uma aspirante a atriz se apaixonam enquanto buscam sucesso em Los Angeles.', 128),
('Pantera Negra', '2018-02-13', 'Após a morte de seu pai, o príncipe T''Challa retorna a Wakanda para assumir o trono e proteger seu povo como o Pantera Negra.', 134),
('O Cavaleiro das Trevas', '2008-07-18', 'Batman enfrenta o Coringa, um criminoso psicótico que busca criar o caos em Gotham City.', 152),
('Os Incríveis', '2004-11-05', 'Uma família de super-heróis aposentados é chamada de volta à ação para enfrentar uma ameaça insidiosa.', 115);

-- Inserts para a tabela atores
INSERT INTO atores (nome, data_nascimento)
VALUES
('Marlon Brando', '1924-04-03'),
('Matthew McConaughey', '1969-11-04'),
('Russell Crowe', '1964-04-07'),
('Elijah Wood', '1981-01-28'),
('Tom Hanks', '1956-07-09'),
('Keanu Reeves', '1964-09-02'),
('Leonardo DiCaprio', '1974-11-11'),
('Tom Hanks', '1956-07-09'),
('Denzel Washington', '1954-12-28'),
('Liam Neeson', '1952-06-07'),
('Hugh Jackman', '1968-10-12'),
('Wagner Moura', '1976-06-27'),
('Chin Han', '1969-11-27'),
('Doug Jones', '1960-05-24'),
('Ralph Fiennes', '1962-12-22'),
('Robin Williams', '1951-07-21'),
('Colin Firth', '1960-09-10'),
('Ryan Gosling', '1980-11-12'),
('Chadwick Boseman', '1976-11-29'),
('Heath Ledger', '1979-04-04'),
('Brad Pitt', '1963-12-18'),
('Ed Harris', '1950-11-28'),
('Keira Knightley', '1985-03-26'),
('Andy Serkis', '1964-04-20'),
('Gael García Bernal', '1978-11-30'),
('Michelle Yeoh', '1962-08-06'),
('Ralph Fiennes', '1962-12-22'),
('Daveigh Chase', '1990-07-24'),
('Roberto Benigni', '1952-10-27'),
('Colin Firth', '1960-09-10'),
('Ryan Gosling', '1980-11-12'),
('Emma Stone', '1988-11-06'),
('Chadwick Boseman', '1976-11-29'),
('Christian Bale', '1974-01-30'),
('Holly Hunter', '1958-03-20'),
('Daniel Kaluuya', '1989-05-24'),
('Michael B. Jordan', '1987-02-09'),
('Will Smith', '1968-09-25'),
('Angelina Jolie', '1975-06-04');

-- Inserts para a tabela filmes_atores
INSERT INTO filmes_atores (filme_id, ator_id, nome_personagem)
VALUES
(1, 1, 'Vito Corleone'),
(2, 2, 'Cooper'),
(3, 3, 'Maximus'),
(4, 4, 'Frodo Baggins'),
(5, 5, 'Forrest Gump'),
(6, 6, 'Neo'),
(7, 7, 'Dom Cobb'),
(8, 8, 'Capitão John Miller'),
(9, 9, 'Zé Pequeno'),
(10, 10, 'Oskar Schindler'),
(11, 11, 'Jack Frost'),
(12, 12, 'Capitão Nascimento'),
(13, 13, 'Seng'),
(14, 14, 'Abe Sapien'),
(15, 15, 'Amon Goeth'),
(16, 16, 'Sean Maguire'),
(17, 17, 'Rei George VI'),
(18, 18, 'Sebastian'),
(19, 19, 'T''Challa / Pantera Negra'),
(20, 20, 'Coringa'),
(5, 21, 'Síndrome'),
(7, 22, 'Fauno'),
(3, 23, 'Li Mu Bai'),
(11, 24, 'Chihiro'),
(16, 25, 'Guido'),
(7, 26, 'Lionel Logue'),
(11, 27, 'Sebastian Wilder'),
(19, 28, 'T''Chaka'),
(20, 29, 'Batman'),
(11, 30, 'Frozone'),
(4, 31, 'Aragorn'),
(12, 32, 'Elastigirl'),
(18, 33, 'Padre René'),
(14, 34, 'Rei Ferdinand'),
(17, 35, 'Mark Hoffman'),
(18, 36, 'Will Munson'),
(19, 37, 'Chris Washington'),
(18, 38, 'Killmonger'),
(20, 39, 'O Coringa');

-- Inserts para a tabela categorias
INSERT INTO categorias (nome, descricao)
VALUES
('Drama', 'Filmes que exploram temas emocionais e narrativas intensas.'),
('Ficção Científica', 'Filmes que exploram conceitos científicos e tecnológicos.'),
('Ação', 'Filmes com sequências de ação e aventuras emocionantes.'),
('Fantasia', 'Filmes que envolvem elementos mágicos e mundos imaginários.'),
('Comédia', 'Filmes que visam entreter e provocar o riso.'),
('Aventura', 'Filmes cheios de emoção, exploração e desafios.'),
('Animação', 'Filmes feitos através da animação de personagens.'),
('Guerra', 'Filmes ambientados em períodos de guerra e conflito.'),
('Biografia', 'Filmes que contam a história de pessoas reais.'),
('Crime', 'Filmes centrados em atividades criminosas.'),
('Mistério', 'Filmes que envolvem elementos de suspense e investigação.'),
('História', 'Filmes que exploram eventos históricos.'),
('Família', 'Filmes voltados para o público familiar.');

-- Inserts para a tabela filmes_categorias
INSERT INTO filmes_categorias (filme_id, categoria_id)
VALUES
(1, 1), -- Drama
(1, 6), -- Aventura
(1, 9), -- Biografia
(2, 3), -- Ação
(2, 12), -- Mistério
(3, 3), -- Ação
(3, 9), -- Biografia
(4, 4), -- Fantasia
(4, 7), -- Animação
(5, 1), -- Drama
(5, 5), -- Comédia
(6, 2), -- Ficção Científica
(6, 8), -- Animação
(7, 2), -- Ficção Científica
(7, 13), -- História
(8, 1), -- Drama
(9, 10), -- Crime
(10, 8), -- Animação
(11, 11), -- Crime
(12, 1), -- Drama
(13, 3), -- Ação
(14, 2), -- Ficção Científica
(14, 3), -- Ação
(15, 1), -- Drama
(15, 5), -- Comédia
(16, 1), -- Drama
(16, 4), -- Fantasia
(17, 5), -- Comédia
(17, 1), -- Drama
(18, 11), -- Crime
(19, 7), -- Animação
(20, 3), -- Ação
(20, 7); -- Animação

-- Inserts para a tabela usuarios
INSERT INTO usuarios (nome, email, cpf)
VALUES
('João Silva', 'joao.silva@email.com', '12345678901'),
('Maria Oliveira', 'maria.oliveira@email.com', '98765432101'),
('Carlos Santos', 'carlos.santos@email.com', '45678901234'),
('Ana Pereira', 'ana.pereira@email.com', '56789012345'),
('Lucas Costa', 'lucas.costa@email.com', '67890123456'),
('Laura Lima', 'laura.lima@email.com', '78901234567'),
('Rodrigo Almeida', 'rodrigo.almeida@email.com', '89012345678'),
('Juliana Souza', 'juliana.souza@email.com', '90123456789'),
('Fernanda Santos', 'fernanda.santos@email.com', '01234567890'),
('Pedro Oliveira', 'pedro.oliveira@email.com', '23456789012');

-- Inserts para a tabela filmes_usuarios
INSERT INTO filmes_usuarios (usuario_id, filme_id, tempo_assistido)
VALUES
(1, 1, 120),
(1, 3, 90),
(1, 5, 150),
(2, 2, 100),
(2, 4, 80),
(2, 6, 120),
(3, 7, 130),
(3, 9, 110),
(3, 11, 140),
(4, 8, 95),
(4, 10, 125),
(4, 12, 100),
(5, 13, 110),
(5, 15, 80),
(5, 17, 130),
(6, 14, 105),
(6, 16, 120),
(6, 18, 90),
(7, 19, 100),
(7, 20, 110),
(8, 1, 90),
(8, 3, 110),
(8, 5, 140),
(9, 2, 120),
(9, 4, 95),
(9, 6, 110),
(10, 7, 130),
(10, 9, 100),
(10, 11, 120);

-- Inserts para a tabela avaliacoes
INSERT INTO avaliacoes (usuario_id, filme_id, nota, comentario)
VALUES
(1, 1, 5, 'Um clássico que nunca envelhece.'),
(2, 2, 4, 'Adorei as cenas de ação, mas a história poderia ser mais desenvolvida.'),
(3, 3, 5, 'Uma obra-prima! Russell Crowe entrega uma atuação incrível.'),
(4, 4, 4, 'A jornada de Frodo é emocionante, mas o filme poderia ser mais curto.'),
(5, 5, 5, 'Tom Hanks é brilhante como sempre. Uma história incrível.'),
(6, 6, 4, 'A ideia da Matrix é fascinante, mas algumas cenas são confusas.'),
(7, 7, 5, 'A mente humana é um enigma intrigante!'),
(8, 8, 4, 'Um filme de guerra emocionante com atuações impressionantes.'),
(9, 9, 5, 'Cidade de Deus é impactante e visceral.'),
(10, 10, 4, 'Schindler é um herói real. Uma história poderosa.');
```
