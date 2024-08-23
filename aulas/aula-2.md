# Teoria Relacional

[VOLTAR](/readme.md)

Criada por Edgar Frank Codd em 1970.

A abordagem da teoria relacional de banco de dados se concentra em melhorar a compreensão dos dados pelos usuários, apresentando o banco de dados como um conjunto de tabelas de duas dimensões organizadas em linhas e colunas.

Uma tabela relacional é uma estruturação dos dados por assunto, organizada em tabelas com linhas e colunas, e cada linha é a representação de uma ocorrência de um objeto, um assunto, descrita por valores em cada coluna.

## Premissas que definem uma tabela de dados

- Cada tabela é chamada de relação.

- Uma linha junto com suas colunas é chamada de tupla.

- Cada coluna da tabela tem um nome, representando um domínio da tabela.

- A ordem das linhas não importa.

- Não existem duas linhas idênticas.

- Usamos nomes para referenciar as colunas.

- A ordem das colunas também não importa.

- Cada tabela tem um nome único e distinto das demais no banco de dados.

## Principais características de uma relação (tabela)

- Todos os atributos (colunas) de uma relação devem ser atômicos, ou seja, não podem ser divididos em valores ou componentes menores.

- Não é permitida a ocorrência de valores múltiplos (multivaloração) em nenhum dos atributos (colunas).

- É importante entender que cada linha de uma tabela representa um objeto ou um assunto.

- Esse objeto é descrito pelos valores em cada uma das colunas.

## Domínio

- Domínio refere-se ao conjunto de valores indivisíveis que uma coluna em uma relação (tabela) pode aceitar.

- Cada domínio é associado a um tipo de dados ou formato específico.

- Geralmente, os domínios são definidos usando tipos primitivos de dados, como integer, float, char, date, time, money, entre outros.

## Chave primária

Em toda tabela existente em um banco de dados relacional, haverá sempre uma coluna ou um conjunto de colunas concatenadas, cujos valores são únicos na tabela, isto é, nunca se repete aquele valor em nenhuma outra linha da tabela.

Em geral, uma tabela pode ter mais de uma chave que possua a capacidade de identificação única das linhas da tabela. Nesse caso, cada uma dessas chaves da tabela é chamada de CHAVE CANDIDATA.

Uma das chaves é definida como primária e as outras ficam como chaves alternativas à chave primária.

## Valores nulos

- Um valor nulo representa a ausência de um valor conhecido ou desconhecido.

- Nesse contexto, a chave primária não pode, sob nenhuma circunstância, ser nula ou desconhecida.

- Além disso, nenhuma das colunas que compõem a chave primária pode ter um valor nulo.

## Chave estrangeira

Uma tabela pode incluir um conjunto de atributos cujos valores pertencem ao mesmo domínio de um conjunto de atributos que formam a chave primária de outra tabela. Isso é conhecido como "chave estrangeira."

- O uso de chaves estrangeiras ajuda a reduzir ou eliminar erros de entrada de dados nos sistemas.

- Mantém a consistência do banco de dados, assegurando que as relações entre as tabelas sejam adequadas e respeitadas.

Quando uma coluna em uma tabela (por exemplo, tabela A) é uma chave primária em outra tabela (por exemplo, tabela B), essa coluna na tabela A é considerada uma "chave estrangeira" em relação à mesma coluna na tabela B.

Esse conceito estabelece uma regra fundamental em bancos de dados relacionais denominada "integridade referencial."

## Integridade referencial

Quando uma tabela possui uma chave estrangeira, os valores dessa chave só podem ser:

- Nulo: Isso é permitido, pois representa a ausência de referência para uma linha na tabela relacionada.

- Igual ao Valor de Alguma Chave Primária: Os valores da chave estrangeira devem corresponder a algum valor da chave primária na tabela referenciada.

Importante ressaltar que não é permitido ter um valor na chave estrangeira que não corresponda a nenhuma chave primária na tabela referenciada.

## Restrições para garantir a integridade referencial

### Tabela Pai

A tabela pai é a tabela com a chave primária da relação, que é referenciada pelas chaves estrangeiras das tabelas filhas.

### Tabelas Filhas

As tabelas filhas são as tabelas com chaves estrangeiras que se relacionam com a chave primária da tabela pai.

#### DELETE

Ao excluir um registro da tabela pai, quando há tabelas filhas relacionadas:

- RESTRICT: A exclusão é impedida caso haja registros relacionados nas tabelas filhas.

- CASCADE: Exclui todos os registros nas tabelas filhas em cascata junto com o registro da tabela pai.

- SET DEFAULT: Define os registros nas tabelas filhas com uma referência padrão para a tabela pai.

- SET NULL: Define as referências nas tabelas filhas como nulas, sem conexão com a tabela pai.

#### INSERT

Ao inserir um registro na tabela filha:

- RESTRICT: Verifica se o valor da chave estrangeira está relacionado a um registro da tabela pai; caso contrário, a operação é impedida.

#### UPDATE

Ao atualizar a chave estrangeira de um registro na tabela filha:

- RESTRICT: Verifica se o novo valor da chave estrangeira está associado a um registro válido na tabela pai; se não estiver, a operação é cancelada.

Essas restrições garantem a integridade referencial entre tabelas relacionadas, assegurando que os dados sejam consistentes e que as operações de inserção, atualização e exclusão sejam controladas de acordo com as regras definidas.

## Referências

- MACHADO, F. N. R. BANCO DE DADOS  PROJETO E IMPLEMENTAÇÃO. [s.l.] Saraiva Educação S.A., 2020.
