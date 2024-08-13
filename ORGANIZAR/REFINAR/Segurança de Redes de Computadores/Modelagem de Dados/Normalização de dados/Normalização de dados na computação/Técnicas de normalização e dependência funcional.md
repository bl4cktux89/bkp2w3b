[![](https://ampli-images.s3.amazonaws.com/production/57fd4b79-3e95-4304-ab21-5710b7f4cabe/original)](https://ampli-images.s3.amazonaws.com/production/57fd4b79-3e95-4304-ab21-5710b7f4cabe/original)

Korth, Silberschatz e Sudarshan (2012) afirmam que as primeiras técnicas de normalização foram criadas em 1972 por Edgar Frank Codd. Após ter dado o primeiro passo, Codd propôs, junto de Raymond Boyce, um novo significado, que ficou conhecido como Forma Normal Boyce-Codd (ou FNBC). Todas elas se baseiam na dependência funcional entre os atributos de uma entidade do banco de dados e nas chaves primárias. Segundo Coronel e Rob (2011), as formas normais mais populares, são:

- A primeira forma normal ou 1FN.
- A segunda forma normal ou 2FN.
- A terceira forma normal ou 3FN.
- A quarta forma normal ou 4FN.

Heuser (2001) afirma que a forma normal é uma regra que deve ser satisfeita por uma entidade para que ela seja avaliada como uma tabela “projetada com exatidão”. São várias formas normais, com regras que vão se tornando mais rigorosas, com o objetivo de averiguar nas tabelas a existência de redundância ou dependências funcionais. No entanto, pelo menos quatro formas normais (como supracitadas) são consideradas essenciais para a construção de um bom projeto de banco de dados.

_______

**💭 Reflita**

Aplicando as formas normais em um projeto de banco de dados e respeitando suas regras, será possível ter um banco de dados mais coeso e com possibilidades de sucesso. Mas será que estará livre de erros? Quais erros podem ocorrer nas últimas fases de um projeto de banco de dados?

_______

Podemos descrever a normalização como um processo de organizar os dados em um modelo de banco de dados. Para realizar essas tarefas são criadas tabelas e estabelecidos relacionamentos entre tabelas de acordo com as regras empregadas para proteger os dados e para tornar o banco de dados mais maleável se adaptando para acabar com a redundância e a dependência inconsistente (campo errado na tabela errada) dos dados que serão armazenados no banco de dados.

_______

**🔁 Assimile**

A redundância de dados desperdiça espaço  de  armazenamento,  com informações duplicadas, e geralmente ocasiona problema de manutenção. Caso haja alteração e os dados estejam em várias tabelas, por exemplo, será necessário procurar esse dado e alterá-lo, gerando uma perda significativa de tempo na manutenção do banco de dados.

_______

Para compreender as formas normais, que serão apresentadas nas próximas aulas, precisamos primeiramente compreender o significado de dependência funcional, que nada mais é consistir em uma restrição entre dois ou mais conjuntos de atributos de uma mesma tabela ou relacionamento, conforme afirma Alves (2014).

Conforme Coronel e Rob (2011) podemos explicar a dependência funcional com o apoio na teoria de conjuntos, dados dois conjuntos de atributos X e Y de uma entidade pode-se afirmar que:

- Y é dependente funcional de X ou
- X determina Y ou
- Y depende de X, logo
- Podemos representar a dependência funcional como: _X_ ® _Y_

A dependência _X_ ® _Y_ ocorrerá se a cada valor de X estiver associado um e somente um valor de Y. Um exemplo de dependência funcional é a tabela _Aluno_. Nela temos a matrícula e o nome do aluno. O nome do aluno depende diretamente da matrícula do aluno. A Figura 4.5 demonstra o esquema de relacionamento de uma tabela. Observe que os três primeiros campos sublinhados: _MatriculaAluno_, _CodigoCurso_ e _CodigoDisciplina_ representam a chave primária da tabela (no caso, uma chave composta ou concatenada). Nesse exemplo, o conjunto dos três campos formam um índice único (formando a chave primária).

[![](https://ampli-images.s3.amazonaws.com/production/311993f1-b47d-4b25-bc63-9bc95a8de4f3/original)](https://ampli-images.s3.amazonaws.com/production/311993f1-b47d-4b25-bc63-9bc95a8de4f3/original)

Tabela exemplificando dependência funcional. Fonte: Alves (2014, p. 109).

A Figura acima apresenta a notação de dependências funcionais dos campos, observe:

- Campo MatriculaAluno: possui como dependência funcional os campos NomeAluno e DataMatricula.
- Campo CodigoCurso: possui como dependência funcional o campo NomeCurso.
- Campo CodigoDisciplina: possui como dependência funcional o campo NomeDisciplina.
- Campos MatriculaAluno, CodigoCurso, CodigoDisciplina: determinam o valor da NotaProva.

A dependência funcional pode ser classificada em: transitiva ou indireta, total ou parcial. A dependência funcional transitiva acontece quando um determinado campo da tabela, além de depender da chave primária da tabela, depende também de outro campo ou de outros campos que são integrantes da mesma tabela. A dependência transitiva ocorre quando Y  depende de  X e Z depende de Y; logo, Z também depende de X. Podemos representar esse tipo de dependência como: X ® Y ® Z .

No Quadro abaixo, observe a tabela _Aluno_ para um sistema de uma universidade. Temos a necessidade de guardar a escola de origem do aluno e o endereço dessa escola. O endereço da escola de origem é dependente da escola de origem, que depende da chave primária que é a matrícula do aluno. Esse é um exemplo de tabela que precisará sofrer um processo de normalização para resolver essa dependência entre os campos com esse tipo de dependência.

[![](https://ampli-images.s3.amazonaws.com/production/7857885e-0fe4-4512-b528-568248c18d34/original)](https://ampli-images.s3.amazonaws.com/production/7857885e-0fe4-4512-b528-568248c18d34/original)

Dependência funcional transitiva ou indireta. Fonte: elaborado pela autora.

A dependência funcional total ou completa (como também é conhecida) ocorre quando um atributo que não faz parte da chave primária depende diretamente de todos os outros atributos que fazem parte da chave primária. Sempre ocorre quando a tabela possui chaves concatenadas (mais de uma chave primária). No Quadro abaixo, há um exemplo em que os campos Cidade e o Bairro são chaves concatenadas e o campo Fiscal Responsável depende dos dois campos para “existir”. A dependência funcional total pode ser representada da seguinte forma: Cidade, Bairro Fiscal Responsável.

[![](https://ampli-images.s3.amazonaws.com/production/fa3b68c0-78a0-4ddb-8a34-f5ad4a7866b2/original)](https://ampli-images.s3.amazonaws.com/production/fa3b68c0-78a0-4ddb-8a34-f5ad4a7866b2/original)

Dependência Funcional Total. Fonte: elaborado pela autora.

A dependência funcional parcial ocorre quando um  campo ou atributo que não faz parte da chave primaria tem dependência funcional de apenas alguns dos atributos que fazem parte da chave primária. No Quadro abaixo, observe que a tabela _Medição da Temperatura_, possui três chaves primárias: UF, Cidade e Região. O campo _Temperatura_ possui uma dependência funcional  parcial apenas de parte das chaves primárias visto que se o campo _Região_ não existisse ou se fosse removido não afetaria o campo _Temperatura_.

[![](https://ampli-images.s3.amazonaws.com/production/d7a242f8-fc55-4c38-b90e-da41671994c6/original)](https://ampli-images.s3.amazonaws.com/production/d7a242f8-fc55-4c38-b90e-da41671994c6/original)

Dependência funcional parcial. Fonte: elaborado pela autora.

A normalização de tabelas é um conjunto  de  procedimentos que permitem encontrar erros em  um  projeto  de  banco  de  dados, encontrando inconsistências que podem ser informações duplicadas e dependências funcionais mal resolvidas ou mal elaboradas. Normalizar é converter uma tabela em tabelas de graus e cardinalidades menores até que quase não haja redundâncias e nem dependências funcionais. Você poderá perceber que o objetivo principal da normalização não é eliminar totalmente as inconsistências, mas controlá-las. Identificar as dependências funcionais nas tabelas é o primeiro passo para saber que precisamos normalizar as tabelas em um banco de dados.