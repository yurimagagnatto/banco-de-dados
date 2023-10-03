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

## Referências

- MACHADO, F. N. R. BANCO DE DADOS  PROJETO E IMPLEMENTAÇÃO. [s.l.] Saraiva Educação S.A., 2020.

- https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model

- https://support.microsoft.com/pt-pt/office/criar-um-diagrama-com-a-nota%C3%A7%C3%A3o-da-base-de-dados-de-p%C3%A9s-de-galinha-1ec22af9-3bd3-4354-b2b5-ed5752af6769

- https://www.lucidchart.com/pages/pt/o-que-e-diagrama-entidade-relacionamento
