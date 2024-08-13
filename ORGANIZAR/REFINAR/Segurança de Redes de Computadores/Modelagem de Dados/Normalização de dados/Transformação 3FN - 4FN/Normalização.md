[![](https://ampli-images.s3.amazonaws.com/production/e2dbb333-5c34-4ff0-9ac8-d9bce9760891/original)](https://ampli-images.s3.amazonaws.com/production/e2dbb333-5c34-4ff0-9ac8-d9bce9760891/original)

A normalização é um processo que visa diminuir a redundância no banco de dados. A ideia central é identificar e reduzir de forma gradual as anomalias que podem aparecer em tabelas ou nos relacionamentos. De forma geral, precisamos retirar um ou mais campos de uma tabela e criar novas tabelas para receber esses campos retirados. Conforme afirmam Navathe e Ramez (2005), o procedimento de normalização proporciona a quem for modelar um banco de dados, as seguintes ações:

- Uma estrutura formal para a análise dos relacionamentos entre as tabelas, com base em suas chaves (primárias e estrangeiras) e das dependências funcionais entre os campos da tabela.
- Um conjunto de testes de Formas Normais para ser realizado em cada esquema de relação, de forma que o modelo de banco de dados seja normalizado no grau desejado, aplicando as Formas Normais até o limite que for mais conivente para a modelagem do banco de dados.

_______

**🔁 Assimile**

O método de normalização envolve a aplicação de um conjunto de regras, chamadas de Formas Normais. Ao avaliarmos um banco de dados e examinarmos que ele respeita as regras da Primeira Forma Normal, podemos, dessa forma, afirmar que o banco está na 1FN (Primeira Forma Normal).

_______

Na medida que o analista de sistemas, programador ou o projetista de banco de dados ganha experiência na modelagem de dados, erros comuns que são encontrados na Primeira Forma Normal e na Segunda Forma Normal são evitados antes mesmo de serem criados. Um exemplo que já foi citado na seção anterior é a tabela Cidade. Quem faz a modelagem de dados de tabelas já sabe de antemão que jamais deverá inserir um campo chamado Cidade nas tabelas. A regra é simples: se em uma tabela aparecer o campo Cidade, devemos criar uma tabela Cidade.

Mas qual a vantagem de aplicar a normalização? A primeira é a redução do trabalho na manutenção do banco de dados. Usando o exemplo do campo Cidade, imagine se uma cidade trocar de nome, para atualizar o banco de dados e se ele não for normalizado, será necessário:

- Localizar o campo Cidade em todas as tabelas.
- Realizar um procedimento de manutenção para a troca do nome.

Se o banco de dados for normalizado, a cidade estará em uma tabela. Basta alterar o nome nessa tabela e todas as outras que estiverem relacionadas com a tabela Cidade automaticamente ficarão atualizadas. Um banco de dados dentro das regras de normalização diminui o trabalho de manutenção e ajuda a evitar o desperdício do espaço de armazenamento.

_______

**📝 Exemplificando**

Uma tabela está na 1FN quando todos os campos contêm apenas um valor correspondente, singular e não existem grupos de atributos repetidos, isso quer dizer que não haverá repetições ou campos que tenham mais que um valor. O primeiro passo é identificar a chave primária da tabela. Após, é necessário reconhecer os campos repetitivos e removê-los da tabela. Em seguida, criamos uma nova tabela para receber os campos que estão repetindo na tabela que está sendo modelada.

_______

Uma tabela está na Segunda Forma Normal se ela atender os requisitos da Primeira Forma Normal e se os campos que estão na tabela, que não sejam chaves, dependam da chave primária em sua totalidade e não em parte dela, causando irregularidades e prevenindo a redundância. Para solucionar, devemos identificar esses campos que dependem parcialmente da chave primária e criar uma nova tabela para eles, criando um relacionamento entre as duas tabelas. No Quadro abaixo é demonstrado a tabela Cliente, a tabela está na 1FN e precisa que a 2FN seja aplicada.

[![](https://ampli-images.s3.amazonaws.com/production/fa423d8f-880b-4edb-b371-6881f3354132/original)](https://ampli-images.s3.amazonaws.com/production/fa423d8f-880b-4edb-b371-6881f3354132/original)

Tabela Cliente não normalizada na 2FN. Fonte: elaborado pela autora.

**📝 Exemplificando**

Quando a tabela Cliente foi normalizada para a 2FN constatou-se que a Nota Fiscal pode ser uma nova tabela, observe o Quadro abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/4f5d94d6-8ff1-45a5-83a3-48ceb05165a8/original)](https://ampli-images.s3.amazonaws.com/production/4f5d94d6-8ff1-45a5-83a3-48ceb05165a8/original)

Tabela Nota Fiscal. Fonte: elaborado pela autora.

Na tabela Cliente é necessário criar uma chave estrangeira, fazendo a referência à tabela Nota Fiscal, observe o Quadro abaixo. Lembre-se de que a nota fiscal só pode pertencer a um único cliente e um cliente poderá possuir várias notas fiscais, observe a tabela Cliente com a chave estrangeira da tabela Nota Fiscal.

[![](https://ampli-images.s3.amazonaws.com/production/52c4ab27-8b0e-4251-8ba0-a136bab90091/original)](https://ampli-images.s3.amazonaws.com/production/52c4ab27-8b0e-4251-8ba0-a136bab90091/original)

Tabela Cliente normalizada. Fonte: elaborado pela autora.

Uma tabela estará na Terceira Forma Normal somente se estiver na Segunda Forma Normal e todos os campos forem independentes, isso quer dizer que não poderá haver dependências funcionais entre os campos e todos os campos dependem da chave primária da tabela. Os campos da tabela precisam depender unicamente da chave primária da tabela. Para aplicar a Terceira Forma Normal é necessário:

- Reconhecer os campos que são funcionalmente dependentes das outras colunas não chaves.
- Eliminar as colunas dependentes.

Conforme Coronel e Rob (2011) para deixar uma tabela na Terceira Forma Normal é necessário eliminar todas as dependências transitivas, ou seja, eliminar todos os campos dependentes de outras tabelas. O Quadro abaixo demonstra a tabela Funcionário, observe que um dos campos é a Descrição, mas é descrição do que? É a descrição do cargo que o funcionário ocupa e, nesse caso, será necessário aplicar a 3FN na tabela.

[![](https://ampli-images.s3.amazonaws.com/production/248719e4-4f74-4598-a13f-e6331b2110f6/original)](https://ampli-images.s3.amazonaws.com/production/248719e4-4f74-4598-a13f-e6331b2110f6/original)

Tabela Funcionário. Fonte: elaborado pela autora.

**🔁 Assimile**

Uma dependência funcional transitiva ocorre quando o valor de uma coluna é dependente de outra que não compõe a chave primária, dependendo indiretamente de outra chave primária. No Quadro acima o campo Descrição depende do Cargo (que é outra tabela) e nesse caso há uma dependência funcional transitiva.