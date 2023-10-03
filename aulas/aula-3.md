# Modelo Conceitual - Diagrama Entidade-Relacionamento (notação Chen)

[VOLTAR](/readme.md)

O Modelo Entidade-Relacionamento (MER) foi desenvolvido por Peter Pin-Shan Chen em 1976 e se concentra na representação de entidades e relacionamentos do mundo real por meio de um Diagrama de Entidades e Relacionamentos (DER). Essa abordagem é orientada para a criação de um modelo conceitual, descrevendo a estrutura de dados de forma independente de detalhes de implementação física. O objetivo principal da modelagem de dados é definir o contexto dos dados que os sistemas utilizam, mantendo-se o mais próximo possível do mundo real.

## Elementos de um MER

- Um modelo de dados ER consiste em três classes de objetos: entidades, relacionamentos e atributos.

- Procedimentos não são o foco principal.

- Nossa principal preocupação é representar as informações do negócio.

- O objetivo central é compreender o negócio para projetar um sistema com base em seus dados.

- Reconhecer os objetos que compõem o negócio, sem se preocupar com procedimentos, programas ou formas de tratamento das informações.

## Entidades

- Entidades representam objetos do mundo real para os quais desejamos armazenar informações.

- No Modelo Entidade-Relacionamento (MER), as entidades são simbolizadas por retângulos com seus nomes no centro, geralmente em singular (um substantivo).

- Cada entidade pode abranger várias instâncias do mesmo tipo.

- Por exemplo, a entidade "aluno" representa todos os alunos de uma escola, não apenas um deles.

- Uma entidade é qualquer objeto, concreto ou abstrato, com existência própria no contexto de um negócio.

- Entidades são coisas sobre as quais desejamos arquivar informações.

- Quando algo no ambiente de negócios nos leva a desejar armazenar dados sobre isso, isso o classifica como uma entidade de negócios.

<!-- IMAGEM -->

## Relacionamentos

- Relacionamentos representam associações entre entidades do mundo real.

- No mundo real, as entidades raramente existem de forma isolada; frequentemente, há associações entre diferentes entidades.

- Em um Diagrama Entidade-Relacionamento (DER), os relacionamentos são mostrados como linhas que conectam as entidades envolvidas.

- Cada linha de relacionamento possui um losango com um nome (geralmente um verbo flexionado) no centro.

- Esse nome reflete um fato ou associação entre as entidades.

- Um relacionamento pode ter dois nomes, um para explicar a associação no sentido da Entidade A para a Entidade B e outro no sentido inverso.

- A leitura de um relacionamento não é unidirecional, não tendo um lado específico para iniciar a interpretação.

<!-- IMAGEM -->

## Atributos

- Atributos são características que detalham uma entidade.

- Uma ocorrência específica de um atributo em uma entidade ou relacionamento é chamado de "valor do atributo."

- Atributos representam propriedades fundamentais de uma entidade ou relacionamento.

- Cada atributo está vinculado a um domínio específico, que é um conjunto de valores válidos para o atributo.

- A notação visual representa um atributo como uma elipse com o nome do atributo dentro dela.

- A elipse é conectada à entidade à qual pertence.

- Existem dois tipos de atributos: identificadores e descritores.

- Um identificador (chave) é usado exclusivamente para identificar uma ocorrência de uma entidade, correspondendo à chave primária em nosso ambiente relacional.

- Os atributos descritores (não chaves) são utilizados para descrever características não únicas de uma ocorrência específica da entidade.

<!-- IMAGEM -->

## Conectividade de um relacionamento (Cardinalidade Máxima)

A conectividade em modelagem ER descreve como as ocorrências de entidades em um relacionamento se associam. Os valores de conectividade podem ser "um" ou "muitos" em um dos lados do relacionamento, indicando que uma ocorrência de uma entidade pode se conectar a uma ocorrência de outra entidade ou a várias ocorrências dessa entidade.

A cardinalidade máxima pode ser 1 ou muitos (n) para cada lado do relacionamento.

### Relacionamento um-para-um (1:1)

- Em um relacionamento um-para-um, temos uma conexão entre duas entidades.

- Cada ocorrência da entidade A se relaciona exclusivamente com uma ocorrência da entidade B.

- Da mesma forma, cada ocorrência da entidade B se relaciona apenas com uma ocorrência da entidade A.

![Diagrama entidade-relacionamento](/imagens/aula-1-2-1.png)

#### DER

![Diagrama entidade-relacionamento](/imagens/4.png)

#### Tabela em um banco de dados relacional

<details>
  <summary>SPOILER!</summary>

  ![Diagrama entidade-relacionamento](/imagens/5.png)
</details>

### Relacionamento um-para-muitos (1:n)

- O relacionamento um-para-muitos é o tipo de conexão mais comum em situações do mundo real e no ambiente de negócios.
Este tipo de relacionamento é amplamente utilizado na modelagem de dados.

- Ele ocorre quando uma ocorrência da entidade A está associada a várias ocorrências da entidade B.

- Ao mesmo tempo, cada ocorrência da entidade B está vinculada a apenas uma ocorrência da entidade A.

![Diagrama entidade-relacionamento](/imagens/aula-1-2-2.png)

#### DER

![Diagrama entidade-relacionamento](/imagens/3.png)

#### Tabela em um banco de dados relacional

<details>
  <summary>SPOILER!</summary>

  ![Diagrama entidade-relacionamento](/imagens/6.png)
</details>

### Relacionamento muitos-para-muitos

- O relacionamento muitos-para-muitos ocorre quando, em ambos os lados da relação, há conectividade de um-para-muitos.

- Esse tipo de relacionamento representa eventos ou fatos comuns nos negócios do mundo real.

![Diagrama entidade-relacionamento](/imagens/aula-1-2-3.png)

#### DER

![Diagrama entidade-relacionamento](/imagens/exercicio-1-1.png)

## Atributos em um relacionamento muitos-para-muitos

No nível conceitual, relacionamentos muitos-para-muitos geralmente têm atributos.

<!-- IMAGEM -->

Observação: Em relacionamentos um-para-um ou um-para-muitos, qualquer atributo necessário para descrever o relacionamento deve ser atribuído às entidades em vez de ao relacionamento em si. Isso ocorre porque nesses tipos de relacionamentos, sempre há um lado com apenas um elemento relacionado.

## Opcionalidade de relacionamento (Cardinalidade Mínima)

A opcionalidade de relacionamento (cardinalidade mínima) indica se a ocorrência do relacionamento é obrigatória (1) ou opcional (0).

A cardinalidade mínima pode ser representada numericamente, com 0 ou 1, antes da cardinalidade máxima, separando-os por uma vírgula.

<!-- IMAGEM -->

## Leitura de um relacionamento entre duas entidades

Exemplo da leitura de um relacionamento entre as entidades Aluno e Disciplinas em ambos os sentidos da relação:

<!-- IMAGEM -->

- Um aluno pode estar matriculado em zero (0) ou mais (n) disciplinas.

<!-- IMAGEM -->

- Uma disciplina pode ter zero (0) ou mais (n) alunos matriculados.

Isso significa que essa relação é muitos-para-muitos (n:n).

![Diagrama entidade-relacionamento](/imagens/exercicio-1-1.png)

Simplificando, o aluno pode se matricular em várias disciplinas, ou não se matricular em nenhuma, e uma disciplina pode ter vários alunos matriculados, ou nenhum.

<!-- ## Condicionalidade de um relacionamento

Um relacionamento pode ser condicional ou ter restrições, ou seja, podemos ter um modelo em que uma entidade se relacione com outras duas, porém com cada uma exclusivamente.

A entidade A se relaciona com a entidade B ou com a entidade C. -->

## Relacionamentos reflexivos

- São relacionamentos que ocorrem entre as ocorrências da mesma entidade.

- Geralmente, representam algum tipo de hierarquia interna.

- Relacionamentos reflexivos podem ter as três possibilidades de conectividade: um-para-um, um-para-muitos e muitos-para-muitos.

<!-- IMAGEM -->

## Resolução de relacionamentos muitos-para-muitos

- Relacionamentos muitos-para-muitos podem ser tratados como entidades associativas.

- Essas entidades representam um fato ou um relacionamento complexo.

- Um relacionamento muitos-para-muitos pode ser dividido em dois relacionamentos 1:n, criando assim uma nova entidade que se relaciona com as duas entidades originais.

![Diagrama entidade-relacionamento](/imagens/aula-1-2-4.png)

### DER

#### representação n:n

![Diagrama entidade-relacionamento](/imagens/exercicio-1-1.png)

#### agora representado por duas relações 1:n

![Diagrama entidade-relacionamento](/imagens/exercicio-1-2.png)

### Tabela em um banco de dados relacional

<details>
  <summary>SPOILER!</summary>

  ![Diagrama entidade-relacionamento](/imagens/7.png)

  Relacionamentos muitos-para-muitos (2 tabelas) são representados por dois relacionamentos 1:n em um banco de dados relacional. Isso envolve o uso de uma terceira tabela, conhecida como tabela associativa, para relacionar as duas tabelas que têm o relacionamento n:n.
</details>

## Atributos ou entidade?

- Algo que não requeira pelo menos dois atributos para ser descrito provavelmente não é uma entidade, mas sim um atributo de outra entidade.

- Atributos multivalorados também podem ser tratados como outra entidade.

## Entidade fraca ou dependente

É uma entidade que não possui existência própria independente no ambiente e depende da existência de uma entidade forte à qual está relacionada.

## Referências

- MACHADO, F. N. R. BANCO DE DADOS  PROJETO E IMPLEMENTAÇÃO. [s.l.] Saraiva Educação S.A., 2020.
