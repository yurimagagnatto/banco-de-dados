# Modelo Lógico - Diagrama Entidade-Relacionamento (pé de galinha/Martin/engenharia da informação)

[VOLTAR](/readme.md)

- James Martin introduziu melhorias no Diagrama Entidade-Relacionamento (DER).

- O modelo lógico define a estrutura lógica dos relacionamentos entre os dados, que foram inicialmente conceituados em um modelo mais abstrato. O modelo ER lógico fornece maior detalhamento em comparação ao modelo ER conceitual.

- No modelo lógico, já selecionamos a abordagem tecnológica a ser usada, que, neste caso, é o modelo relacional. Isso significa que definimos como os dados serão armazenados em tabelas e relacionados.

- Uma das etapas cruciais na criação do modelo lógico é a definição das chaves primárias (identificadores únicos) e chaves estrangeiras (responsáveis pela relação entre as tabelas).

- Os relacionamentos no modelo lógico são representados por linhas, e a cardinalidade (ou seja, o número de instâncias relacionadas) pode ser representada por símbolos ou números.

- No modelo lógico, as entidades conceituais são substituídas por tabelas do banco de dados relacional. Cada tabela representa uma entidade conceitual e contém os atributos associados a essa entidade.

- Quando ocorrem relações de muitos-para-muitos (N:N), elas são transformadas em duas relações de um-para-muitos (1:N) através da criação de uma tabela associativa. Esta tabela associativa contém chaves estrangeiras que fazem referência às chaves primárias das tabelas envolvidas, permitindo assim a representação eficaz de tais relacionamentos complexos.

Dica: Em relações 1:N (um-para-muitos), a tabela que representa o lado "muitos" contém a chave estrangeira, que faz referência à chave primária da tabela que representa o lado "um". Isso estabelece a ligação entre os registros nas duas tabelas.

## Modelo Conceitual

### Diagrama Entidade-Relacionamento (notação Chen)

![Modelo conceitual](/imagens/modelo-conceitual.png)

## Modelo Lógico

### Diagrama Entidade-Relacionamento (notação engenharia da informação)

![Modelo lógico](/imagens/modelo-logico.png)

### Exemplo das tabelas com registros em um banco de dados relacional

#### filmes

| id | titulo | data_lancamento | sinopse | duracao |
| --- | --- | --- | --- | --- |
| 1 | Matrix | 1999-03-31 | Um hacker descobre a verdade... | 136 |
| 2 | Titanic | 1997-12-19 | Um romance épico a bordo do... | 195 |
| 3 | O Senhor dos Anéis: A Sociedade do Anel | 2001-12-19 | Uma jornada épica... | 178 |
| 4 | Pantera Negra | 2018-02-13 | T'Challa retorna a Wakanda... | 134 |
| 5 | Pulp Fiction | 1994-10-14 | Uma história interligada... | 154 |

#### categorias

| id | nome | descricao |
| --- | --- | --- |
| 1 | Ação | Filmes de ação |
| 2 | Romance | Filmes de romance |
| 3 | Fantasia | Filmes de fantasia |
| 4 | Drama | Filmes dramáticos |
| 5 | Comédia | Filmes de comédia |

#### filmes_categorias

| id | filme_id | categoria_id |
| --- | --- | --- |
| 1 | 1 | 1 |
| 2 | 2 | 2 |
| 3 | 3 | 3 |
| 4 | 4 | 1 |
| 5 | 5 | 5 |

#### usuarios

| id | nome | email | cpf |
| --- | --- | --- | --- |
| 1 | João da Silva | <joao@email.com> | 123.456.789-00 |
| 2 | Maria Santos | <maria@email.com> | 987.654.321-00 |
| 3 | Pedro Lima | <pedro@email.com> | 555.555.555-55 |
| 4 | Ana Pereira | <ana@email.com> | 777.777.777-77 |
| 5 | Carlos Sá | <carlos@email.com> | 999.999.999-99 |

#### filmes_usuarios

| id | usuario_id | filme_id | tempo_assistido |
| --- | --- | --- | --- |
| 1 | 1 | 1 | 90 |
| 2 | 1 | 2 | 120 |
| 3 | 2 | 1 | 75 |
| 4 | 3 | 4 | 60 |
| 5 | 4 | 5 | 100 |

#### avaliacoes

| id | usuario_id | filme_id | nota | comentario |
| --- | --- | --- | --- | --- |
| 1 | 1 | 1 | 4 | Gostei muito deste filme! |
| 2 | 1 | 2 | 5 | Uma história emocionante. |
| 3 | 2 | 1 | 4 | Recomendo a todos. |
| 4 | 3 | 4 | 3 | Pantera Negra é bom. |
| 5 | 4 | 5 | 5 | Pulp Fiction é um clássico. |

#### atores

| id | nome | data_nascimento |
| --- | --- | --- |
| 1 | Keanu Reeves | 1964-09-02 |
| 2 | Leonardo DiCaprio | 1974-11-11 |
| 3 | Elijah Wood | 1981-01-28 |
| 4 | Chadwick Boseman | 1976-11-29 |
| 5 | Samuel L. Jackson | 1948-12-21 |

#### filmes_atores

| id | filme_id | ator_id |
| --- | --- | --- |
| 1 | 1 | 1 |
| 2 | 2 | 2 |
| 3 | 3 | 3 |
| 4 | 4 | 4 |
| 5 | 5 | 5 |

## Referências

- MACHADO, F. N. R. BANCO DE DADOS  PROJETO E IMPLEMENTAÇÃO. [s.l.] Saraiva Educação S.A., 2020.

- [Entity–relationship model - Wikipedia](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model)

- [Criar um diagrama com a notação da base de dados de pés de galinha - Suporte da Microsoft](https://support.microsoft.com/pt-pt/office/criar-um-diagrama-com-a-nota%C3%A7%C3%A3o-da-base-de-dados-de-p%C3%A9s-de-galinha-1ec22af9-3bd3-4354-b2b5-ed5752af6769)

- [O que é um diagrama entidade relacionamento? | Lucidchart](https://www.lucidchart.com/pages/pt/o-que-e-diagrama-entidade-relacionamento)

- [brModeloWeb](https://app.brmodeloweb.com/)
