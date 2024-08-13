[![](https://ampli-images.s3.amazonaws.com/production/120829b7-8aa7-4efc-b8ed-abf7645d40ba/original)](https://ampli-images.s3.amazonaws.com/production/120829b7-8aa7-4efc-b8ed-abf7645d40ba/original)

A modelagem de dados tem como sua essência mais pura o refinamento de processos. Isso significa que sempre podemos melhorar o que já foi realizado. Uma vez criado o Diagrama Entidade-Relacionamento   (DER) já podemos implementá- lo em um Sistema Gerenciador de Banco de Dados? Não. O correto é revisar, procurar imperfeições e melhorar, prevendo possíveis problemas. Em um  banco de  dados o  maior problema é a redundância, pois ela pode causar danos enormes e pode acontecer disso ser notado somente quando o banco de dados já estiver sendo usado pela empresa. Os danos que a redundância pode causar e que geram mais problemas é a repetição da mesma informação em várias tabelas, ocasionando, além de duplicidade, possíveis erros em relatórios.

_______

**📝 Exemplificando**

Na Figura abaixo podemos observar três tabelas: a do cliente, a do fornecedor e a do funcionário. Repare que todas possuem um campo  em  comum: cidade.

Se deixarmos do jeito que está, a mesma cidade pode ser cadastrada três vezes e em tabelas diferentes.

[![](https://ampli-images.s3.amazonaws.com/production/1ced3811-19d1-448d-ad73-7693f3baf207/original)](https://ampli-images.s3.amazonaws.com/production/1ced3811-19d1-448d-ad73-7693f3baf207/original)

Exemplo de redundância. Fonte: elaborada pela autora.

E o que poderia ser pior que a repetição vista na Figura acima? O problema de inconsistência no banco de dados, que nada mais é  do que a mesma informação sendo cadastrada de forma errônea, por exemplo, a cidade de Joinville pode ser cadastrada como: “Joinville”, “Joinvile” ou ainda “Jlle”. São três formas de cadastros que darão problemas quando  precisarmos  consultar,  no  banco  de dados, informações como: “mostrar todos os funcionários da cidade de Joinville”. Caso a cidade tenha sido cadastrado de forma errada, esses funcionários ficarão fora do relatório gerado.

Quando o usuário cadastra uma informação em uma tabela não podemos, por exemplo, prever que ele irá inserir o seu nome errado no banco de dados. Mas, no caso da cidade é mais simples: criamos uma tabela chamada _Cidade_, relacionando as tabelas que precisam dessa informação, observe a Figura abaixo que ilustra o correto relacionamento entre a tabela _Cidade_ e as demais que a utilizam.

[![](https://ampli-images.s3.amazonaws.com/production/dda8894a-786d-47ac-b847-61fdef079125/original)](https://ampli-images.s3.amazonaws.com/production/dda8894a-786d-47ac-b847-61fdef079125/original)

Resolvendo a redundância e a inconsistência entre as tabelas. Fonte: elaborada pela autora.

Às vezes é interessante manter uma informação redundante no banco de dados. Por questões de desempenho de alguma pesquisa ou software a redundância pode ocorrer, fato esse que é chamado de **redundância controlada** e é recomendado quando o campo recebe uma grande quantidade de consultas e poucas alterações. Um exemplo é uma tabela de nota fiscal, o campo “valor_total_ da_nota”, que poderia ser obtido automaticamente, como o resultado da soma de todos os itens vendidos e multiplicados pelo seu preço. Entretanto, é comum criarmos manualmente o campo “valor_total_da_nota” para evitar que, caso haja alteração do preço do produto vendido, o valor da nota não seja alterado (causando problemas contábeis). É uma redundância que sabemos que existe, mas é necessária.

O Quadro abaixo apresenta um outro exemplo de redundância controlada. Observe, na tabela _Funcionário_ há o código do departamento (_CodDepartamento_) e o nome do departamento _(NomeDepartamento_), causando a redundância e que pode ser ideal para um determinado software, mas para outro software pode ser uma péssima ideia. É nessa hora que o projetista do banco de dados ou o analista de sistemas deverá decidir se realmente será benéfico deixar a redundância acontecer.

[![](https://ampli-images.s3.amazonaws.com/production/a45aee33-adba-4891-aec8-ad167c869422/original)](https://ampli-images.s3.amazonaws.com/production/a45aee33-adba-4891-aec8-ad167c869422/original)

Exemplo tabela com redundância controlada. Fonte: elaborado pela autora.

Segundo Coronel e Rob (2011), a normalização é uma técnica para avaliar e corrigir estruturas e tabelas ao modo de tornar mínimas as redundâncias de dados, reduzindo assim as chances de haver problemas. Normalizar um banco de dados é aplicar regras para todas as suas tabelas, com os objetivos, além de reduzir a redundância e eliminar campos que não dizem respeito à tabela. Um bom exemplo disso é uma tabela que armazena informações sobre a cidade. De forma alguma poderemos armazenar informações sobre um funcionário dentro da tabela.

Podemos listar alguns objetivos e vantagens da normalização de um esquema de banco de dados:

- Diminuição de dados repetitivos deixando o banco de dados mais compacto.
- Aumento da performance no Sistema Gerenciador de Banco de Dados.
- Armazenamento dos dados de forma lógica.
- Facilidade na criação de consultas.
- Permite a concatenação de índices (chaves) de acordo com a quantidade de tabelas envolvidas.
- Facilidade na manutenção do banco de dados.

Normalização de dados é um processo rígido e formal que deve ser seguido passo a passo examinando os campos de uma tabela, a fim de evitar irregularidades observadas na inclusão, exclusão e alteração de registros. Observe o Quadro abaixo que demonstra a tabela _Produto_ não normalizada, observe que nos campos _TipoProduto_ e no _Fornecedor_ a mesma informação foi inserida erroneamente, entre os registros.

[![](https://ampli-images.s3.amazonaws.com/production/39566c02-c0dc-41b7-be48-f4fc5d316d42/original)](https://ampli-images.s3.amazonaws.com/production/39566c02-c0dc-41b7-be48-f4fc5d316d42/original)

Exemplo tabela Produto não normalizada. Fonte: elaborado pela autora.

Uma das regras básicas da normalização é verificar se determinado campo realmente pertence à tabela. No caso do Quadro acima, há os campos:

- _TipoProduto_: podemos criar uma tabela para armazenar os tipos de produtos.
- _CodForn_ e _Fornecedor_: devemos criar uma tabela chamada fornecedor.

Na sequência de Quadros abaixo, é mostrado como devem ser as tabelas normalizadas. O Quadro abaixo mostra que foram retirados da tabela _Produto_ alguns campos, para que ela fique normalizada. As informações que permaneceram e que agora fazem parte de outra tabela ficaram como chaves estrangeiras das tabelas: _TipoProduto_ e _Fornecedor_, observe:

[![](https://ampli-images.s3.amazonaws.com/production/9c5aa9d6-e46b-426b-b8b7-54417765afa1/original)](https://ampli-images.s3.amazonaws.com/production/9c5aa9d6-e46b-426b-b8b7-54417765afa1/original)

Exemplo tabela Produto normalizada. Fonte: elaborado pela autora.

No Quadro abaixo, a tabela _TipoProduto_ foi criada e será nesta tabela que todos os tipos de produtos deverão ser criados, para depois serem escolhidos na tabela _Produto_ (via chave estrangeira).

[![](https://ampli-images.s3.amazonaws.com/production/251afad3-0434-4c84-81c4-f39a0357ac51/original)](https://ampli-images.s3.amazonaws.com/production/251afad3-0434-4c84-81c4-f39a0357ac51/original)

Exemplo tabela TipoProduto normalizada. Fonte: elaborado pela autora.

No Quadro abaixo, a tabela fornecedor foi criada para receber as informações dos fornecedores e, por meio da chave estrangeira na tabela _Produto_, vinculamos o Fornecedor ao Produto, evitando que o nome do mesmo fornecedor seja cadastrado de forma errada.

[![](https://ampli-images.s3.amazonaws.com/production/931e465b-51d8-48fb-92d9-3d465615dbe0/original)](https://ampli-images.s3.amazonaws.com/production/931e465b-51d8-48fb-92d9-3d465615dbe0/original)

Exemplo tabela Fornecedor normalizada. Fonte: elaborado pela autora.

Geralmente os analistas de sistemas já criam as tabelas _TipoProduto_ e _Fornecedor_ automaticamente num modelo de banco de dados. Mostramos as tabelas dos quadros supracitados para dar ênfase à necessidade da normalização, principalmente quando estamos começando na modelagem de banco de dados.

Na Figura abaixo você poderá observar o Diagrama de Entidade-Relacionamento entre as três tabelas: _Produto_ – _Fornecedor_ e _TipoProduto_. No diagrama você pode observar, que um produto é classificado a um determinado tipo de produto, mas um determinado tipo de produto poderá estar relacionado com muitos produtos. Para esse exemplo um produto possui somente um fornecedor e o fornecedor poderá fornecer muitos produtos.

[![](https://ampli-images.s3.amazonaws.com/production/a12afcc1-0c22-4caf-90b2-fc68bab0ef87/original)](https://ampli-images.s3.amazonaws.com/production/a12afcc1-0c22-4caf-90b2-fc68bab0ef87/original)

DER Produto – TipoProduto - Fornecedor. Fonte: elaborada pela autora.