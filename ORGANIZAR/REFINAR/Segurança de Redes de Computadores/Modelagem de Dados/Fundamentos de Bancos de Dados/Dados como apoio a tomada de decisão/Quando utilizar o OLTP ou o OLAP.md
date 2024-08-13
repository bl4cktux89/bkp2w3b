[![](https://ampli-images.s3.amazonaws.com/production/c7ddd7d9-b146-4167-9ddd-8bf3ffb10a20/original)](https://ampli-images.s3.amazonaws.com/production/c7ddd7d9-b146-4167-9ddd-8bf3ffb10a20/original)

Conforme afirmam Korth, Silberschatz e Sudarshan (2012, p. 120), “a maioria dos fornecedores de Sistemas Gerenciadores de Banco de Dados fornece ferramentas de OLAP como parte do SGBD ou como adicionais”. Existem empresas que desenvolvem softwares específicos para tomada de decisão e auxílio na gestão de informação da base de dados. Algumas companhias que desenvolvem OLAP são IBM, Microsoft, ORACLE, entre outras.

Uma pergunta que podemos fazer é: quando utilizar o OLTP ou o OLAP? É possível exemplificar com a seguinte situação: uma secretária faz a matrícula de um aluno no sistema de uma determinada faculdade, inserindo suas informações, então, neste caso, é usado o OLTP. Se o aluno se matricular em um curso, arrepender-se e quiser trocar, a secretária poderá modificar isso no sistema. Neste caso também é usado o OLTP, por se tratar de uma consulta de alteração. No final no bimestre, o diretor desta mesma faculdade precisa de um relatório com o perfil dos alunos dos últimos três anos, no qual será analisado: idade, curso, semestres cancelados e situação financeira. Este é um exemplo de OLAP, trazendo informações que servirão para oferta de novos cursos para o perfil de aluno desejado.

_______

**🔁 Assimile**

_Ad-hoc_ é uma consulta (ou transação) no banco de dados realizada pelo próprio usuário com parâmetros criados pela necessidade específica do consultante. A geração de consultas de acordo com as necessidades do negócio do cliente pode levar a resultados e descobertas casuais.

_______

O grande número de dados e a modelagem de um banco de dados podem levar a redundâncias, ocasionando futuros problemas. O controle da redundância (repetição) de um banco de dados é uma tarefa que deve ser realizada a partir da modelagem do banco de dados. Korth, Silberschatz e Sudarshan (2012, p. 158) afirmam que uma análise dos atributos das entidades deve ser realizada para evitar redundâncias, por exemplo o atributo cidade em entidades. Imagine que num banco de dados de uma universidade precisamos armazenar a cidade de nascimento do aluno. O atributo cidade precisa ser armazenado em outras entidades, como funcionários e fornecedores. É a mesma informação sendo armazenada em várias entidades diferentes, levando muitas vezes à inconsistência do banco de dados.

_______

**📝 Exemplificando**

A inconsistência em um banco de dados ocorre, principalmente, quando há redundâncias, por exemplo: o nome da cidade de São Paulo é digitado em três entidades diferentes. Na primeira está Sao Paulo (sem acento), na segunda está SP (abreviado) e na terceira está São Paul (com erro de digitação). Os dados são da mesma cidade, porém de formas bem diferentes. Esse tipo de situação pode ser contornado ao criarmos uma entidade chamada cidade.

_______

Segundo Navathe e Ramez (2005, p. 12), um SGBD deve permitir a redundância controlada. Em algumas situações específicas, até é permitida a repetição de algum atributo em uma entidade, mas isso deve ser feito de forma bem consciente pelo analista ou projetista do banco de dados, pois pode aumentar significativamente o espaço de armazenamento do banco de dados. Por causa do backup, existem várias cópias físicas do banco de dados, gerando redundância, cujo tipo de redundância, também é uma redundância controlada, visto que, as cópias são necessárias para manter a segurança do banco de dados. Em caso de falhas, a cópia backup do banco de dados é realizada.

Um SGBD deve prever facilidades para a recuperação após falhas, de acordo com Navathe e Ramez (2005, p. 13), porém, a empresa precisa se prevenir estabelecendo uma política de backup. Essa política é um conjunto de regras estabelecido pelo DBA (Administrador do Banco de Dados) junto com os gestores da empresa, que determinam as respostas dos seguintes itens:

- **Responsabilidades**: quem fará o backup? Quem terá acesso ao backup?
- **Meios**: de que forma será realizado o backup? Qual mídia ou nuvem usar? Qual software? Qual hardware?
- **Período**: qual o intervalo dos backups? Diariamente, semanalmente, mensalmente?
- **Retenção**: quanto tempo o backup deve ficar armazenado na mesma mídia?
- **Armazenamento**: onde serão armazenados os backups? Quais locais seguros deverão ser indicados?

_______

**💭 Reflita**

Um banco de dados é o bem mais precioso da empresa? Como uma companhia pode ter prejuízos por causa do banco de dados? Ela poderia ir à falência pela perda ou invasão de seu banco de dados?

_______

Segundo Date (2003), o bem mais valioso de uma empresa é a informação. Um SGBD permite que várias formas de segurança possam ser implementadas para proteger o banco de dados e preservar o seu conteúdo. Quando ocorrem falhas de segurança, nem sempre é um ato proposital. Por exemplo, um empregado do RH, de forma equivocada, pode apagar as informações contidas nas entidades dos empregados. Por que isso ocorreu? Aconteceu pelo fato de o funcionário ter permissão para apagar (neste caso, o comando DELETE) dados na entidade dos funcionários.

É fundamental estabelecer políticas de permissões e acessos às tabelas. Korth, Silberschatz e Sudarshan (2012) declaram que o primeiro ponto da segurança de um banco de dados é reforçar a autenticação do usuário e garantir que tenham permissão para acessar e executar somente os trabalhos com autorização prévia, conforme seu nível hierárquico dentro da empresa. Em um outro cenário, suponha que a companhia desenvolva projetos de peças mecânicas e está trabalhando em peças revolucionárias. Se não houver um controle de privilégios aos acessos destas informações, o projeto pode ser roubado (copiado por alguém) ou ser apagado por alguém que não deveria ter acesso e achou que não era algo importante. As consequências do acesso indevido são muitas e podem causar prejuízos muito altos. A empresa investe para desenvolver um projeto e, por causa de falhas em suas políticas, pode ter perdas significativas.

A segurança da informação ganhou notoriedade nestas últimas décadas. Riscos de ataques internos e externos podem afetar os dados e a própria administração da empresa, então é necessário criar regras que garantam a segurança aos seus dados, ou seja, a política de segurança da empresa. As regras são criadas conforme as necessidades de cada companhia, estabelecendo critérios de acesso físico e remoto ao banco de dados. Navathe e Ramez (2005, p. 525-527) citam que um dos itens mais importantes do SGBD são as senhas que controlam o acesso ao banco de dados. Uma política de segurança de um banco de dados deve possuir os seguintes itens:

- **Integridade**: garantia de que as informações serão mantidas de forma íntegra e sem modificações indevidas de pessoas não autorizadas.
- **Confiabilidade**: garantia de que as informações armazenadas no banco somente serão acessadas por pessoas autorizadas previamente. 50 U1 -Fundamentos de Bancos de Dados
- **Disponibilidade**: garantia de disponibilizar a informação somente às pessoas com permissão de acesso e modificação.

Korth, Silberschatz e Sudarshan (2012, p. 87) demonstram que podemos atribuir a um usuário várias formas de autorizações a um banco de dados:

- Somente de leitura dos dados.
- Para inserir novos dados.
- Para atualizar novos dados.
- Para excluir dados.

As autorizações dadas aos usuários são chamadas de privilégios e podemos estendê-los de um usuário para todos. Os privilégios também podem ser uma combinação de autorizações. É nesta hora que entra a política de segurança do banco de dados da empresa: quando um usuário realiza uma consulta ao banco de dados, primeiramente o SGBD verifica se o usuário possui a autorização necessária para realizar a ação que pretende, de acordo com Korth, Silberschatz e Sudarshan (2012, p. 88). A maior autoridade sobre o banco de dados é o DBA (Administrador do Banco de Dados), pois ele tem acesso tanto ao esquema do banco (diagramas) quanto aos dados armazenados, além de ser quem autoriza os acessos ao banco de dados, limitando e até criando novos usuários com permissões distintas.

_______

**➕ Pesquise mais**

O SQL Injection é uma das principais formas de ataques ao banco de dados. Conheça um pouco mais sobre essa tecnologia acessando o vídeo abaixo:

ROSA, Alex. [Entendendo o SQL Injection](https://www.youtube.com/watch?v=OmDCgJ9eQDw) – Vídeo 1.

_______

Chegamos ao fim da primeira parte teórica da unidade 1, na próxima aula será o momento de praticar seus conhecimentos. Conceitos essenciais foram apresentados sobre os SGBDs e suas tecnologias, além de subsídios para poder indicar uma ferramenta para um cliente, conforme a necessidade. Um analista de sistemas precisa estar ciente de que suas decisões podem afetar positiva ou negativamente o negócio das empresas. A confiança que o cliente deposita nos conselhos que recebe ao solicitar um software é muito grande. Na próxima unidade você aprenderá sobre os princípios da modelagem de dados, para que possam ser criados nos SGBDs vistos nesta unidade.