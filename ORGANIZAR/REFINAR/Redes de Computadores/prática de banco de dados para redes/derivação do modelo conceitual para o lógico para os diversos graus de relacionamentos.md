**Introdução**

Antes de apresentar como deve ser feita a derivação dos modelos conceituais para os lógicos (relacionais), vamos revisar alguns conceitos sobre as chaves utilizadas em bancos de dados relacionais.

- **Chave Primária (PK – Primary Key)**

Atributo por meio do qual é possível identificar determinado registro. O conjunto de valores que constituem a chave primária deve ser único dentro de uma tabela.

- **Chave estrangeira (FK – Foreign Key)**

Utilizada quando queremos que o valor de um atributo seja validado a partir do valor de atributo de outra tabela. Criamos assim uma relação de dependência (um relacionamento) entre as tabelas.

- **Chave única (unique)**

Utilizada quando determinado campo não deve ser repetido e não é chave primária. Aumenta a consistência do banco de dados.

Há ainda outro tipo de restrição muito utilizado em bancos de dados relacionais: **NOT NULL** (não nulo), utilizado quando todos os valores relacionados a determinado atributo são obrigatórios, ou seja, não nulos ou não "vazios".

A partir da compreensão desses conceitos, podemos agora apresentar como deve ser feita a derivação entre os modelos (lógico e relacional).

**Nota**: Consulte a **aula** **5** para uma revisão dos graus de relacionamento.

Utilizamos as seguintes abreviações na representação dos modelos conceituais e lógicos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121871/a10i00_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121871/a10i00_md80_100.jpg)

Portanto, A, B e C podem representar qualquer conjunto de entidades presentes em um relacionamento, por exemplo, cliente, pedido, produto etc.

**Nota:** Abaixo das entidades relacionadas são apresentadas as respectivas tabelas que devem ser geradas a partir do processo de derivação entre os modelos.

**Relacionamentos binários 1:1**

As soluções são diversas para os relacionamentos 1:1, por exemplo, quando a cardinalidade máxima for 1,1 nos dois sentidos, a solução mais comum é unir as duas entidades em uma única tabela.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121873/a10i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121873/a10i01_md80_100.jpg)

**Relacionamentos binários 1:N**

Observe que nos relacionamentos 1:N a chave primária sempre ficará do lado em que a cardinalidade for N.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121874/a10i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121874/a10i02_md80_100.jpg)

**Relacionamentos binários N:N**

Quando efetuamos o mapeamento para o modelo lógico de relacionamentos N:N, devemos construir uma tabela associativa composta pelas chaves primárias das duas tabelas (A e B). Os dois atributos (X e Y) formarão a chave primária (composta) da nova tabela (AB).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121875/a10i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121875/a10i03_md80_100.jpg)

**Relacionamento com atributo identificador**

A solução é semelhante à anterior, porém o atributo identificador do relacionamento (Z, no exemplo a seguir) também fará parte da chave primária na tabela associativa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121876/a10i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121876/a10i04_md80_100.jpg)

**Relacionamentos ternários**

Os relacionamentos entre três entidades requerem a construção de uma quarta tabela que deverá conter as chaves primárias das três tabelas (A, B e C). Os três atributos (X, Y e Z) formarão a chave primária composta da nova tabela (ABC).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121878/a10i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121878/a10i05_md80_100.jpg)

**Autorrelacionamentos 1:1**

Neste tipo de autorrelacionamento, a chave estrangeira ficará na mesma tabela com uma restrição do tipo unique (chave única) para garantir a cardinalidade 1:1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121877/a10i06_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121877/a10i06_md80_100.jpg)

**Autorrelacionamentos 1:N**

Neste outro tipo de autorrelacionamento, a chave estrangeira também ficará na mesma tabela, porém não terá a restrição unique (chave única).

O diagrama apresentado a seguir demonstra que um funcionário supervisor pode ter vários supervisionados, porém, cada funcionário supervisionado tem apenas um supervisor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121879/a10i07_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121879/a10i07_md80_100.jpg)

**Autorrelacionamentos N:N**

Os autorrelacionamentos com grau de cardinalidade N:N requerem uma segunda tabela na qual teremos uma chave primária composta.

O modelo conceitual a seguir apresenta uma entidade DISCIPLINA e por meio do relacionamento PRE_REQUISITO procura-se demonstrar que algumas disciplinas são _**pré-requisito**_ para cursar outras, por exemplo: para cursar Cálculo 2 há como     pré-requisito cursar Cálculo 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121882/a10i08_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/8/121882/a10i08_md80_100.jpg)