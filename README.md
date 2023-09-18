# Aula Banco de Dados

- [link teste](aulas/aula-1.md)

- [link teste 2](/aulas/aula-1.md)

## Banco de Dados

### O que é Banco de Dados

### Tipos de Banco de Dados

### Banco de Dados Relacional

### Sistema de Gerenciamento de Banco de Dados (SGBD)

### MySQL

### SQL

#### DDL

#### DML

#### DQL

### Modelagem de Dados

#### Abstração

#### Minimundo

#### Modelo conceitual

#### Modelo Lógico

#### Modelo Físico

#### Imagem

## Teoria Relacional

Criada por Edgar Frank Codd em 1970.

A abordagem da teoria relacional de banco de dados se concentra em melhorar a compreensão dos dados pelos usuários, apresentando o banco de dados como um conjunto de tabelas de duas dimensões organizadas em linhas e colunas.

### Premissas que definem uma tabela de dados

- Cada tabela é chamada de relação.

- Uma linha junto com suas colunas é chamada de tupla.

- Cada coluna da tabela tem um nome, representando um domínio da tabela.

- A ordem das linhas não importa.

- Não existem duas linhas idênticas.

- Usamos nomes para referenciar as colunas.

- A ordem das colunas também não importa.

- Cada tabela tem um nome único e distinto das demais no banco de dados.

### Principais características de uma relação (tabela)

- Todos os atributos (colunas) de uma relação devem ser atômicos, ou seja, não podem ser divididos em valores ou componentes menores.

- Não é permitida a ocorrência de valores múltiplos (multivaloração) em nenhum dos atributos (colunas).

- É importante entender que cada linha de uma tabela representa um objeto ou um assunto.

- Esse objeto é descrito pelos valores em cada uma das colunas.

### Domínio

- Domínio refere-se ao conjunto de valores indivisíveis que uma coluna em uma relação (tabela) pode aceitar.

- Cada domínio é associado a um tipo de dados ou formato específico.

- Geralmente, os domínios são definidos usando tipos primitivos de dados, como integer, float, char, date, time, money, entre outros.

### Chave primária

Em todas as tabelas de um banco de dados relacional, há sempre uma coluna ou um grupo de colunas cujos valores são exclusivos na tabela, ou seja, esses valores nunca se repetem em nenhuma outra linha da mesma tabela.

### Valores nulos

- Um valor nulo representa a ausência de um valor conhecido ou desconhecido.

- Nesse contexto, a chave primária não pode, sob nenhuma circunstância, ser nula ou desconhecida.

- Além disso, nenhuma das colunas que compõem a chave primária pode ter um valor nulo.

### o que faltou

## Modelo Entidade-Relacionamento

O Modelo Entidade-Relacionamento (MER) foi desenvolvido por Peter Pin-Shan Chen em 1976 e se concentra na representação de entidades e relacionamentos do mundo real por meio de um Diagrama de Entidades e Relacionamentos (DER). Essa abordagem é orientada para a criação de um modelo conceitual, descrevendo a estrutura de dados de forma independente de detalhes de implementação física. O objetivo principal da modelagem de dados é definir o contexto dos dados que os sistemas utilizam, mantendo-se o mais próximo possível do mundo real.

### Elementos de um MER

- Um modelo de dados ER consiste em três classes de objetos: entidades, relacionamentos e atributos.

- Procedimentos não são o foco principal.

- Nossa principal preocupação é representar as informações do negócio.

- O objetivo central é compreender o negócio para projetar um sistema com base em seus dados.

- Reconhecer os objetos que compõem o negócio, sem se preocupar com procedimentos, programas ou formas de tratamento das informações.

### Entidades

- Entidades representam objetos do mundo real para os quais desejamos armazenar informações.

- No Modelo Entidade-Relacionamento (MER), as entidades são simbolizadas por retângulos com seus nomes no centro, geralmente em singular (um substantivo).

- Cada entidade pode abranger várias instâncias do mesmo tipo.

- Por exemplo, a entidade "aluno" representa todos os alunos de uma escola, não apenas um deles.

- Uma entidade é qualquer objeto, concreto ou abstrato, com existência própria no contexto de um negócio.

- Entidades são coisas sobre as quais desejamos arquivar informações.

- Quando algo no ambiente de negócios nos leva a desejar armazenar dados sobre isso, isso o classifica como uma entidade de negócios.

### Relacionamentos

- Relacionamentos representam associações entre entidades do mundo real.

- No mundo real, as entidades raramente existem de forma isolada; frequentemente, há associações entre diferentes entidades.

- Em um Diagrama Entidade-Relacionamento (DER), os relacionamentos são mostrados como linhas que conectam as entidades envolvidas.

- Cada linha de relacionamento possui um losango com um nome (geralmente um verbo flexionado) no centro.

- Esse nome reflete um fato ou associação entre as entidades.

- Um relacionamento pode ter dois nomes, um para explicar a associação no sentido da Entidade A para a Entidade B e outro no sentido inverso.

- A leitura de um relacionamento não é unidirecional, não tendo um lado específico para iniciar a interpretação.

### Atributos

- Atributos são características que detalham uma entidade.

- Uma ocorrência específica de um atributo em uma entidade ou relacionamento é chamado de "valor do atributo."

- Atributos representam propriedades fundamentais de uma entidade ou relacionamento.

- Cada atributo está vinculado a um domínio específico, que é um conjunto de valores válidos para o atributo.

- A notação visual representa um atributo como uma elipse com o nome do atributo dentro dela.

- A elipse é conectada à entidade à qual pertence.

- Existem dois tipos de atributos: identificadores e descritores.

- Um identificador (chave) é usado exclusivamente para identificar uma ocorrência de uma entidade, correspondendo à chave primária em nosso ambiente relacional.

- Os atributos descritores (não chaves) são utilizados para descrever características não únicas de uma ocorrência específica da entidade.

### Conectividade de um relacionamento (Cardinalidade Máxima)

A conectividade em modelagem ER descreve como as ocorrências de entidades em um relacionamento se associam. Os valores de conectividade podem ser "um" ou "muitos" em um dos lados do relacionamento, indicando que uma ocorrência de uma entidade pode se conectar a uma ocorrência de outra entidade ou a várias ocorrências dessa entidade.

#### Um-para-um (1:1)

Quando, entre duas entidades, temos um relacionamento em que cada ocorrência da entidade A se associa ou relaciona com uma e somente uma ocorrência da entidade B e cada ocorrência da entidade B se relaciona com uma e somente uma ocorrência da entidade A, temos um relacionamento com conectividade um-para-um (1:1).

#### Um-para-muitos (1:n)

É a conectividade mais comum no mundo real e no mundo dos negócios, além de ser a mais utilizada na solução de modelo de dados. Ela acontece quando uma ocorrência da entidade A se associa ou conecta a mais de uma ocorrência da entidade B, visto que a ocorrência da entidade B está conectada a uma e somente uma ocorrência da entidade A.

#### Muitos-para-muitos

Quando encontramos nos dois sentidos de leitura a conectividade de um-para-muitos, temos, então, o que se denomina de conectividade muitos-para-muitos. Um relacionamento com essa conectividade é normalmente um fato, acontecimento de negócios no mundo real.

### Atributos em um relacionamento

Como estamos atuando no nível conceitual, temos a obrigação de observar que, nesse tipo de relacionamento de muitos-para-muitos, normalmente ocorre a presença de atributos.

Atributos são normalmente assinalados em relacionamentos muitos-para-muitos. Nunca assinalamos atributos em relacionamentos um-para-um e em relacionamentos um-para-muitos porque, no sentido de leitura de um relacionamento desse tipo, sempre temos um lado que tem somente um elemento relacionado, e seria ambíguo colocarmos o atributo no relacionamento em vez de colocarmos na entidade.

Sempre que temos relacionamentos de um-para-um ou um-para-muitos, os atributos que possam existir em decorrência do fato são elementos de descrição de uma das duas entidades.

### Opcionalidade de relacionamento (Cardinalidade Mínima)

Como representar essa opcionalidade? Essa situação indica que a conectividade mínima é igual a 0 (zero). Um pequeno círculo no lado que existe a opcionalidade faz essa representação:

### Condicionalidade de um relacionamento

Um relacionamento pode ser condicional ou ter restrições, ou seja, podemos ter um modelo em que uma entidade se relacione com outras duas, porém com cada uma exclusivamente.

A entidade A se relaciona com a entidade B ou com a entidade C.

### Relacionamentos reflexivos

São os relacionamentos que acontecem entre as ocorrências de uma mesma entidade. Normalmente, esses relacionamentos representam algum sentido de hierarquia.

Os relacionamentos reflexivos podem ter qualquer uma das três possibilidades de conectividade: um-para-um, um-para-muitos e muitos-para-muitos.

formato de diagramação para representar os papéis, o que deixa um pouco mais clara essa definição do modelo.



### Resolução de relacionamentos muitos-para-muitos

Todo relacionamento muitos-para-muitos pode ser entendido como uma entidade. Essas entidades denominam-se associativas, pois elas representam um fato, um relacionamento muitos-para-muitos.

algo que não requeira pelo menos dois atributos para o descrever provavelmente não caracterizará uma entidade e, sim, um atributo de alguma outra entidade,


