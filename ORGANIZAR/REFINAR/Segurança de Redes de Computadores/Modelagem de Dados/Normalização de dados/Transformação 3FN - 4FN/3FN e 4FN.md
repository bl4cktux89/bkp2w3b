[![](https://ampli-images.s3.amazonaws.com/production/04d06951-ddba-4378-b94c-6fa0dd9134cf/original)](https://ampli-images.s3.amazonaws.com/production/04d06951-ddba-4378-b94c-6fa0dd9134cf/original)

Ao aplicar a 3FN na tabela Funcionário, retiramos o campo Descrição, afinal esse é um campo que detalha o cargo e deve estar em uma tabela apropriada e que no caso será a tabela Cargo. O Quadro abaixo demonstra a tabela Funcionário após aplicarmos a 3FN.

[![](https://ampli-images.s3.amazonaws.com/production/b8e65b97-3159-431f-bdec-db34ea672ee6/original)](https://ampli-images.s3.amazonaws.com/production/b8e65b97-3159-431f-bdec-db34ea672ee6/original)

Tabela Funcionário normalizada. Fonte: elaborado pela autora.

A tabela Cargo, Quadro abaixo, agora possui a descrição do cargo do funcionário. O relacionamento entre as duas tabelas (Funcionário e Cargo) é 1 para N. Observe que na tabela Funcionário há um campo com o sinal &, isso indica que o campo é uma chave estrangeira e a tabela está relacionada com a tabela Cargo.

[![](https://ampli-images.s3.amazonaws.com/production/f467beb6-540d-488d-b418-413d420f8a70/original)](https://ampli-images.s3.amazonaws.com/production/f467beb6-540d-488d-b418-413d420f8a70/original)

Tabela Cargo. Fonte: elaborado pela autora.

Observe a tabela **Ordem_de_Compra** na forma textual:

Ordem_de_Compra(**\#idOrdem**, dtOrdem, &codProduto, Quantidade, Valor_Unitário, ValorTotal). Para aplicar a 3FN, qual campo não deveria estar na tabela? Um dos campos é resultado de um cálculo, consegue identificar qual é o campo?

_______

Para realizar a normalização de uma tabela na Quarta Forma Normal (ou 4FN) é necessário que a tabela esteja na Terceira Forma Normal. A tabela somente estará na 4FN se não existir dependência multivalorada. Mas o que isso quer dizer? Dependência multivalorada é quando as informações inseridas nas tabelas podem ficar se repetindo e, claro, produzir redundâncias na tabela. Para evitar esse tipo de problema é melhor dividir a tabela evitando assim esse tipo de dependência. De acordo com Navathe e Ramez (2005), em uma tabela na 4FN, além de estar na 3FN, todo campo precisa ser atômico (não pode ser dividido em vários campos).

Os procedimentos para deixar uma tabela na 4FN são:

- Primeiro identificar os campos multivalorados (que causam repetições).
- Criar uma tabela para cada grupo multivalorado.
- Criar uma chave primária para a nova tabela.
- Inserir a chave estrangeira na tabela que está sendo normalizada (na 4FN) para criar o relacionamento entre as tabelas.

Para uma empresa é necessário armazenar as informações sobre os dependentes de todos os seus funcionários. Esse armazenamento se faz necessário por causa do imposto de renda, plano de saúde, etc. No Quadro abaixo a tabela Funcionário possui dois campos: Dependente e Parentesco.

[![](https://ampli-images.s3.amazonaws.com/production/15d27bd2-c96d-402d-afe1-11028a7db609/original)](https://ampli-images.s3.amazonaws.com/production/15d27bd2-c96d-402d-afe1-11028a7db609/original)

Tabela Funcionário com campo multivalorado. Fonte: elaborado pela autora.

Algumas perguntas sobre a tabela Funcionário, mostrada no Quadro abaixo precisam de respostas:

- Caso um funcionário tenha mais de um filho, como será o cadastro?
- Vamos cadastrar o funcionário duas vezes?
- E se o funcionário tiver cinco filhos?

A redundância na tabela Funcionário aparecerá com certeza. Para resolver esse problema, será necessário dividir a tabela Funcionário em duas tabelas: Funcionário e Dependentes. No Quadro abaixo foi retirado totalmente os campos Dependente e Parentesco.

[![](https://ampli-images.s3.amazonaws.com/production/8ff2993e-9032-40ea-855b-909817271fb0/original)](https://ampli-images.s3.amazonaws.com/production/8ff2993e-9032-40ea-855b-909817271fb0/original)

Tabela Funcionário normalizada. Fonte: elaborado pela autora.

O Quadro abaixo apresenta a tabela Dependente que foi criada para evitar os campos multivalorados na tabela Funcionário.

[![](https://ampli-images.s3.amazonaws.com/production/b1c0c557-b9e6-46ee-9628-ded308b3270a/original)](https://ampli-images.s3.amazonaws.com/production/b1c0c557-b9e6-46ee-9628-ded308b3270a/original)

Tabela Dependente. Fonte: elaborado pela autora.

Refletindo um pouco sobre as tabelas Funcionário e Dependente: seria possível que, em uma empresa, o mesmo dependente pudesse ser dependente de mais de um funcionário? E um funcionário poderia ter mais de um dependente? As respostas são todas afirmativas. Uma sugestão de modelagem dessas tabelas aparece na Figura abaixo. Foi criado mais uma tabela para relacionar os funcionários que possuem mais de um dependente e os dependentes que estão relacionados com mais de um funcionário (gerando assim um relacionamento N para N).

[![](https://ampli-images.s3.amazonaws.com/production/201a587d-8434-4da0-b420-ac938f486984/original)](https://ampli-images.s3.amazonaws.com/production/201a587d-8434-4da0-b420-ac938f486984/original)

DER das tabelas normalizadas. Fonte: elaborada pela autora.

Korth, Silberschatz e Sudarshan (2012) afirmam que a Quarta Forma Normal não é a última instância da modelagem de um esquema de banco de dados. Os refinamentos podem continuar evoluindo, juntamente com o banco de dados. Alguns autores afirmam que um banco de dados normalizado até a Terceira Forma Normal já está num nível aceitável. Com a grande demanda de informações da nossa era, é importante pensar nos perigos que o excesso de redundância pode ocasionar ao banco de dados, afinal, guardar essas informações requer espaço em equipamentos e isso gera custos.

Chegamos ao final do nosso conteúdo! Você aprendeu sobre a modelagem de dados de uma forma mais prática, aplicada para projetos de médio porte. A experiência fará com que os conceitos das aulas sejam diversas vezes aplicados no dia a dia do desenvolvimento de softwares. O nível de refinamento de suas modelagens irá refletir com a prática que você irá adquirir. Por isso, mãos à obra. Coloque em prática seus projetos, comece pelo banco de dados e realize a modelagem dos dados.