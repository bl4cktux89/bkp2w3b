[![](https://ampli-images.s3.amazonaws.com/production/e9f6bb1e-3dca-47a0-88ff-06f17469227d/original)](https://ampli-images.s3.amazonaws.com/production/e9f6bb1e-3dca-47a0-88ff-06f17469227d/original)

Esta aula trouxe novas ferramentas para aperfeiçoar o desenvolvimento das modelagens de banco de dados de sua empresa: os dicionários de dados poderão auxiliar na organização, na apresentação e no controle de cada campo em uma tabela.  Será possível adotar uma estratégia de modelagem que melhor se enquadre nos padrões de desenvolvimento de sua empresa.

Agora com um novo cliente, você contará com ajuda de estagiários, que vão auxiliar na modelagem do banco de dados. Novamente, é necessário organização e controle nessas atividades.

Seu novo cliente, o salão de beleza da Dona Áurea, deseja informatizar o atendimento e o controle dos clientes e dos funcionários. Os requisitos da modelagem são os seguintes:

- O cliente deve ser cadastrado e ter seus serviços principais também armazenados, pois futuramente o salão pretende criar um cartão de fidelidade.
- O salão possui diversos fornecedores, de quem são comprados os produtos, e que podem ser também profissionais que prestam serviços como afiação de instrumentos, eletricidade, etc. Desta forma, precisamos classificar os tipos de fornecedores.

Deverá ser criado o modelo de entidade-relacionamentos e a documentação das tabelas criadas no modelo lógico. Com os requisitos apontados, duas perguntas precisarão ser respondidas: qual serviço um determinado funcionário realizou e como controlar o agendamento de horários dos clientes? Como resposta à primeira pergunta, deveremos criar três tabelas (atendimento, serviços e funcionários) e a relação entre elas. Em relação ao segundo questionamento, é necessário criar a tabela agenda, devendo conter o cliente, o serviço que a pessoa deseja realizar e o funcionário requisitado.

Na solução da situação-problema, vamos elencar as tabelas que apareceram nos questionamentos e nos requisitos: cliente, serviço, funcionário, agenda, atendimento, fornecedores e produtos.

Com as tabelas listadas, agora é com você, faça o DER da seguinte maneira:

- Encontre o relacionamento entre as tabelas.
- Indique as cardinalidades entre as tabelas.
- Encontre campos para as tabelas.
- Identifique as chaves primárias para cada tabela.
- Verifique os relacionamentos e insira as chaves estrangeiras nas tabelas que possuam a cardinalidade N.

Após a elaboração do DER, deverá ser realizado o mapeamento das entidades na forma textual, juntamente com a documentação completa das tabelas, neste caso, um dicionário de dados.

Pesquise uma ferramenta gráfica que permita a criação do modelo gráfico de forma mais prática e, então, crie um slide de apresentação para seu cliente, contendo o modelo lógico gráfico, o modelo textual e o dicionário de dados de todas as tabelas.