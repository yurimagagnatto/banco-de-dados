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

Uma tabela pode ter um conjunto de atributos que contêm valores com o mesmo domínio de um conjunto de atributos que formam a chave primária de outra tabela. Esse conjunto se chama chave estrangeira.

Isso ajuda a eliminar ou diminuir erros de entrada de dados nos sistemas, e a manter a consistência do banco de dados.

Sempre que uma coluna de uma determinada tabela A for uma chave primária em uma tabela B, essa coluna na tabela A é uma chave estrangeira em relação à mesma coluna na tabela B.

IMAGEM

Esse conceito estabelece uma regra em bancos de dados relacionais denominada integridade referencial.

## Integridade referencial

uma tabela contém uma chave estrangeira, então, o valor dessa chave só pode ser:

▶Nulo – nesse caso pode, pois representa a inexistência de referência para uma linha da tabela.

▶Igual ao valor de alguma chave primária na tabela referenciada.

O que não pode haver é um valor de chave estrangeira que não exista como chave primária de nenhuma linha da tabela referenciada

## Restrições

as restrições aqui