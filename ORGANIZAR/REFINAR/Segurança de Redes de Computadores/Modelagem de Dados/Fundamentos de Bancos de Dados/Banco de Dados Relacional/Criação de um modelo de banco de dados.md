[![](https://ampli-images.s3.amazonaws.com/production/2c4eabc7-a088-468a-accf-4936d4b8973c/original)](https://ampli-images.s3.amazonaws.com/production/2c4eabc7-a088-468a-accf-4936d4b8973c/original)

Criar um modelo de banco de dados é uma tarefa que, na maioria das vezes, não deve ser feita por uma única pessoa e de forma isolada com a sua própria experiência de vida. Se o projeto for pequeno, é provável que isso ocorra. Porém, suponha que você necessite fazer um banco de dados para uma clínica de estética, mas nunca sequer pisou em uma. Não pode simplesmente fazer algumas consultas na internet e supor o que é necessário para o sistema. O passo inicial, segundo Eslmari e Navathe (2005), é o levantamento e a análise dos requisitos, realizando entrevistas para entender e documentar as necessidades solicitadas pelos usuários. Cougo (1997) afirma que o processo de modelagem implica na existência de um objeto ou em um ambiente a ser observado.

Monteiro (2014) afirma que um requisito é uma condição ou uma capacidade que um software deverá possuir. Requisito é um levantamento e análises das necessidades que o sistema precisa atender. Para atingir esses objetivos serão necessárias reuniões com os clientes envolvidos e analistas de sistemas e que resultará em um documento de especificação com as funcionalidades que o banco de dados precisará possuir.

A fase inicial do projeto de banco de dados, segundo Korth, Silberschatz e Sudarshan (2003), é caracterizar completamente as necessidades de dados dos prováveis usuários do banco de dados. As etapas da modelagem possuem algumas funções que podem ser classificadas como:

- **Concepção**: é um entendimento da necessidade do cliente com relação ao software e é quando serão estabelecidos os objetivos principais da solução desejada.
- **Elicitação**: são as conversas com os usuários do software com o objetivo de colher mais informações sobre os procedimentos realizados e que deverão estar presentes no software.
- **Elaboração**: criação de modelos para a formalização dos requisitos (aqui entra a nossa disciplina). Com o modelo é possível encontrar falhas ou esquecimentos dos clientes ou do próprio analista de sistemas.
- **Negociação**: com o modelo apresentado, os clientes podem querer mais itens, é necessário verificar as viabilidades das sugestões.

A qualidade do banco de dados desenvolvido depende diretamente dos requisitos levantados, mas não para por aí. Ao projetarmos um banco de dados, precisamos nos antecipar às necessidades do cliente. Muitas vezes, criamos e programamos muito além do que foi solicitado, visando a qualidade final do software para este para futuros clientes (caso o sistema seja vendido para um outro cliente). Devemos realizar vários testes como forma de garantir que as relações criadas estejam corretas, antes de implantar o banco de dados. Usamos alguns exemplos (dados) típicos da empresa para determinar se algum ponto crucial da modelagem pode estar com problemas.

_______

**➕ Pesquise mais**

Saiba um pouco mais sobre os requisitos de software no artigo Definição de requisitos de software baseada numa arquitetura de modelagem de negócios.

AZEVEDO JUNIOR, D. P.; CAMPOS R. Definição de requisitos de software baseada numa arquitetura de modelagem de negócios. [**Produção**](https://pt.wikipedia.org/wiki/Produ%C3%A7%C3%A3o), São Paulo. Associação Brasileira de Engenharia de Produção, vol. 18, n. 1, 2008, p. 26-46.

_______

Um Sistema Gerenciador de Banco de Dados, de acordo com Korth, Silberschatz e Sudarshan (2012), é constituído por um conjunto de dados associados a um conjunto de programas para acesso a estes mesmos dados, proporcionando um ambiente perfeito para o armazenamento e a recuperação destes dados. Podemos classificar os elementos que compõem um banco de dados em: dados, hardware, software e usuários.

O SGBD foi projetado para trabalhar com um volume muito grande de dados. Esses dados armazenados nos bancos de dados serão compartilhados entre os diversos usuários dos sistemas. É em função deste armazenamento que algumas regras de modelagem deverão ser rigorosamente seguidas (elas serão vistas nas próximas unidades deste livro).

O hardware é um elemento importante, pois determina como e onde os dados serão processados e armazenados. Devemos orientar corretamente os nossos clientes quanto à necessidade de investimentos nesta área. De nada adianta uma modelagem perfeita se o banco de dados rodar em uma máquina obsoleta. Conforme visto na aula anterior, o armazenamento em nuvem está se destacando atualmente, é uma tendência, mas ainda existem muitas empresas que preferem ter seu próprio servidor e deixar a base de dados em sua propriedade física.

O software em questão como elemento essencial de um banco de dados é sem dúvida o Sistema Gerenciador de Banco de Dados. De acordo com Date (2003), o SGBD é de longe o software mais importante, por isolar o acesso dos dados pelos usuários leigos do acesso ao seu armazenamento no hardware. Existem, ainda, os softwares de aplicação, que são ambientes próprios do SGBD ou linguagens de programação que permitem criar uma _interface_ amigável entre o usuário e o SGBD.

Os usuários de banco de dados são os atores (as pessoas) que realizam operações de manipulação na base de dados e podem ser classificados, conforme Korth, Silberschatz e Sudarshan (2012), como:

- **Programadores de aplicação**: são os programadores do software que podem ou não criar a base de dados, podem simplesmente criar aplicações para acessar a base já existentes ou podem desenvolver o banco de dados e a aplicação que irá utilizar o banco;
- **Usuários sofisticados**: são usuários treinados para poder manipular a base de dados através de consultas ao banco de dados. Geralmente, são analistas de sistemas especializados em determinado software (ou base de dados);
- **Usuários especialistas**: são desenvolvedores que projetam aplicações em determinada base de dados específica e complexa, como dados gráficos ou cartográficos;
- **Usuários navegantes (comuns ou leigos)**: são os usuários comuns que fazem uso das informações do banco de dados. Algumas vezes, este tipo de usuário nem sabe que está acessando uma base de dados, procura as informações em um software (de aplicação) e a informação é apresentada na tela (vinda de um banco de dados).