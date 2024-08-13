[![](https://ampli-images.s3.amazonaws.com/production/ff27b094-12c0-4281-9340-815ed1f15309/original)](https://ampli-images.s3.amazonaws.com/production/ff27b094-12c0-4281-9340-815ed1f15309/original)

A modelagem de dados, de acordo com Coronel e Rob (2011), é um processo que irá se repetir de forma progressiva, começando com uma compreensão simples de um determinado problema e, logo que haja um melhor entendimento do problema a ser modelado, o nível de detalhes do modelo também irá se ampliar. Uma das fases mais cruciais no desenvolvimento de um _software_ é justamente a elaboração de um projeto de banco de dados. Criar um banco de dados sem um estudo e de forma apressada pode causar vários problemas, tais como desempenho abaixo do esperado, consultas complicadas e, ainda, resultados equivocados, o que impacta de forma negativa a performance do _software_.

Cougo (1997) descreve que um modelo de dados é um detalhamento dos tipos de informações que serão guardadas em um banco de dados. Para a construção de modelos de dados, usa-se uma linguagem de modelagem de dados, essas linguagens são qualificadas conforme a forma de apresentar modelos, podendo ser: a linguagem textual ou linguagem gráfica. Esta forma de representação de um modelo de dados, por meio de uma linguagem de modelagem de dados, é conhecida como: esquema de banco de dados (KORTH; SILBERSCHATZ; SUDARSHAN, 2012).

Um modelo de dados, de acordo com Coronel e Rob (2011), é uma reprodução gráfica de estruturas de dados de situações reais. Um modelo pode representar uma abstração de alguma coisa real ou de algum objeto. Utilizar um modelo tem como finalidade auxiliar na compreensão das situações reais. Em um sistema que utiliza banco de dados, o modelo irá representar as estruturas das tabelas, os dados e seus relacionamentos.

Utilizamos os modelos de forma gráfica para conseguirmos simplificar a comunicação com o usuário. Na Figura abaixo, podemos observar uma representação gráfica que, mesmo sem muita noção sobre banco de dados ou qualquer área da computação, pode ser facilmente compreendida: uma receita de bolo possui diversos ingredientes e, com um pouco de analogia iria perceber que os ingredientes podem ou não ser usados nas receitas de bolo. Os modelos gráficos como forma de comunicação com os usuários são uma excelente ferramenta. Com poucas explicações, os usuários já se tornam aptos a darem suas opiniões.

[![](https://ampli-images.s3.amazonaws.com/production/c78f6e20-3474-45ad-a65b-5a6ca7ecdfb2/original)](https://ampli-images.s3.amazonaws.com/production/c78f6e20-3474-45ad-a65b-5a6ca7ecdfb2/original)

Exemplo de representação gráfica. Fonte: elaborada pela autora.

**📝 Exemplificando**

Objetos ou eventos do mundo real podem ser modelados e transformados em entidades (tabelas). São exemplos de objetos do mundo real que podem ser modelados: clientes, empresas, funcionários, produtos etc. Eventos reais são ações que geram atributos e que devem ser preservados, tais como: reservas, atendimentos, locação, dentre outros.

_______

Abreu e Machado (2004) afirmam que o projeto de um sistema de informações é uma atividade complexa, que inclui planejamentos, especificações e desenvolvimento de vários componentes. É necessário estabelecer uma sequência de atividades para guiar o processo de modelagem do banco de dados, sendo elas:

- **Análise dos requisitos**: levantamento das necessidades do cliente.
- **Modelo conceitual**: não contém detalhes sobre como será representado em meio físico; representa as informações no nível da realidade do que será modelado.
- **Modelo lógico**: descreve as estruturas que estarão contidas no banco de dados, de acordo com a abordagem da modelagem a ser utilizada.
- **Modelo físico**: descreve o detalhamento ao nível do SGBD; nível físico de criação dos componentes do banco de dados.

Segundo Coronel e Rob (2011), o projeto de banco de dados focaliza em como a estrutura do banco será utilizada para armazenar e gerenciar todos os dados do sistema do usuário final. Na Figura abaixo, podemos observar a sequência do processo de modelagem de um banco de dados.

[![](https://ampli-images.s3.amazonaws.com/production/10b1a132-8367-4f1e-9555-1a2fcc0c6cf6/original)](https://ampli-images.s3.amazonaws.com/production/10b1a132-8367-4f1e-9555-1a2fcc0c6cf6/original)

Processo de modelagem de dados. Fonte: elaborada pela autora.

O processo de inicialização de um banco de dados de sucesso começa no procedimento de levantamento e de análise de requisitos (CORONEL; ROB, 2011). Devemos estudar o domínio do problema que o banco de dados deverá solucionar. Por meio dos requisitos, é realizado um levantamento das necessidades que o software deverá possuir. Diversas reuniões com o cliente deverão ser realizadas para que o analista possa detectar as reais necessidades do cliente e também para conhecer as rotinas de trabalho da empresa. Desta forma, a chance de haver problemas na modelagem por causa de um requisito esquecido será reduzida.

Cougo (1997) destaca alguns pontos importantes que devem ser considerados, na análise de requisitos:

- **Abrangência**: determinar o escopo do projeto para poder determinar o que será realizado e qual processo terá a necessidade de ser observado (na empresa) para realizar a modelagem do banco de dados.
- **Nível de detalhamento**: definir qual o nível de detalhamento que o projeto deverá possuir.
- **Tempo para a produção do modelo**: é necessário estabelecer um tempo para realizar a modelagem. Nesta fase, muitos problemas podem ser encontrados e rapidamente solucionados.
- **Recursos disponíveis**: estabelecer a quantidade de mão de obra para desenvolver o software solicitado.

Korth, Silberschatz e Sudarshan (2012) relatam que, em geral, nenhum usuário entende todas as necessidades de uma aplicação. O analista de sistemas precisa interagir com os usuários a fim de identificar e criar as regras de negócio, pois, caso essa parte seja mal executada, corremos o risco de ter que refazer a modelagem. Como resultado da análise dos requisitos, são produzidos diversos documentos de especificação do projeto que deverão ser validados com o cliente, mas não nos aprofundaremos sobre tal documentação, nos atendo ao foco desta disciplina, o processo de modelagem.

_______

**📝 Exemplificando**

Um requisito se refere às funcionalidades que o software deverá possuir, a regra de negócio determina como o software deverá se comportar e quais restrições deverá possuir. Tanto o requisito quanto a regra de negócio possuem um foco diferente. São exemplos de requisito e de regra de negócio, respectivamente: matricular o aluno na disciplina de estágio; o aluno somente será matriculado na disciplina de estágio caso não haja dependência no primeiro e no segundo semestre do curso.

_______

Assim que os requisitos do software forem levantados, o próximo passo é a modelagem conceitual. Navathe e Ramez (2005) afirmam que a modelagem conceitual é uma descrição concisa das informações que o software deverá possuir, de acordo com seus requisitos. É uma representação do que precisa ser realizado (não é a solução do problema). Após o levantamento dos requisitos é gerado um esquema conceitual ou uma visão mais abrangente e geral do banco de dados.

Podemos utilizar as linguagens textuais ou linguagens gráficas, sem nos preocuparmos com as regras de modelagem de dados, que serão demonstradas mais adiante. A linguagem textual é menos utilizada por ser mais complexa, caso haja muitas informações. Na Figura abaixo, podemos observar, em linguagem textual, as entidades Ator e Filme, com alguns campos que caracterizam cada uma.

[![](https://ampli-images.s3.amazonaws.com/production/8da5c327-bad6-45d3-85fc-a929319b394d/original)](https://ampli-images.s3.amazonaws.com/production/8da5c327-bad6-45d3-85fc-a929319b394d/original)

Linguagem textual. Fonte: elaborada pela autora.

As entidades representadas na Figura acima possuem poucos atributos, mas é comum uma entidade ter muitos deles, o que dificulta a visualização por parte do usuário. Na figura abaixo, a linguagem gráfica é demonstrada de forma simplificada.

[![](https://ampli-images.s3.amazonaws.com/production/193d0623-9b24-4152-a502-555be52b92c8/original)](https://ampli-images.s3.amazonaws.com/production/193d0623-9b24-4152-a502-555be52b92c8/original)

Linguagem gráfica simplificada. Fonte: elaborada pela autora.

Utilizamos os modelos de entidade de relacionamento para descrever esses esquemas e assim apresentar aos usuários para sanar eventuais dúvidas de entendimento do software. Por exemplo, estamos realizando uma modelagem para um sistema de uma universidade e é nesta hora que definimos algumas situações:

- O aluno poderá se matricular em mais de um curso?
- Um professor pode lecionar em vários cursos?
- Uma turma pode ser composta por alunos de cursos diferentes?

As perguntas anteriores não podem ser respondidas pelo analista de sistemas, mas sim pelo cliente, que irá determinar essas situações. Nessa fase de modelagem conceitual, não é levado em conta como essas informações serão armazenadas no Sistema Gerenciador de Banco de Dados (SGBD).

Segundo Coronel e Rob (2011), o modelo conceitual traz algumas vantagens importantes: fornece a visão de nível macro, de forma simplificada e independente de hardware e de software, não sendo necessária a realização de adaptações em função de determinado SGBD ou equipamento que serão adotados posteriormente.

_______

**🔁 Assimile**

O alvo do modelo conceitual é a definição do problema e não a sua solução. Mostra o que precisará existir no banco de dados de uma forma geral, sem se preocupar de que forma isso será realizado no SGBD.