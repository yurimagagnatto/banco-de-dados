# Teoria Relacional

[VOLTAR](/readme.md)

Criada por Edgar Frank Codd em 1970.

A abordagem da teoria relacional de banco de dados se concentra em melhorar a compreensão dos dados pelos usuários, apresentando o banco de dados como um conjunto de tabelas de duas dimensões organizadas em linhas e colunas.

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

! aqui

Em toda a tabelas de um banco de dados relacional, há sempre uma coluna ou um grupo de colunas cujos valores são exclusivos na tabela, ou seja, esses valores nunca se repetem em nenhuma outra linha da mesma tabela.

## Valores nulos

- Um valor nulo representa a ausência de um valor conhecido ou desconhecido.

- Nesse contexto, a chave primária não pode, sob nenhuma circunstância, ser nula ou desconhecida.

- Além disso, nenhuma das colunas que compõem a chave primária pode ter um valor nulo.

## o que faltou
