# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/bddfeefe-4fdd-4fc5-a00b-f58925490e17/original)](https://ampli-images.s3.amazonaws.com/production/bddfeefe-4fdd-4fc5-a00b-f58925490e17/original)

### **Qual é o foco da aula?**

Nesta aula, você irá aprender sobre o armazenamento em banco de dados.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer o uso de banco de dados;
- aplicar dados _MySQL_ com linguagem PHP na web;
- localizar dados inseridos por usuários.

**Situação-problema**

O que uma rede social, um _e-commerce_ e um site de notícias têm em comum? Uma grande quantidade de dados, que são exibidos rapidamente a cada vez que algum usuário acessa o site. Nos casos em que temos um grande volume de dados, o simples armazenamento de deles em arquivos não é satisfatório, pois ficaria muito lento, desestruturado e inseguro. Pense, por exemplo, em um site de _e-commerce_: a cada acesso devem ser disponibilizadas diversas informações a respeito dos produtos disponíveis, incluindo a descrição, código de referência, preço, informações técnicas, saldo de estoque disponível, volume para cálculo de frete, fotos e outras.

Além disso, os produtos devem ser classificados em categorias e o site deve permitir que o usuário faça pesquisa filtrando os produtos que deseja. São muitas informações, e é fundamental que elas estejam armazenadas e organizadas em um banco de dados. Nesta aula estudaremos a utilização do banco de dados MySQL com a linguagem de programação para web PHP.

Para colocarmos em prática os conhecimentos a serem obtidos, vamos analisar a seguinte situação-problema: na _startup_ em que você trabalha, solicitaram o desenvolvimento de uma página capaz de auxiliar o usuário a decidir qual o melhor combustível para seu uso, considerando o preço do litro da gasolina e do etanol. Essa página também deve efetuar cálculos levando em conta o consumo do veículo (9 km/litro de etanol e 11 km/litro de gasolina) e a distância a ser percorrida.

Além disso, foi solicitado que você mantivesse salvos os dados inseridos pelos usuários, de maneira que fosse possível gerar posteriormente um relatório contendo a data, o valor da gasolina e o valor do etanol que os usuários digitaram. Esses dados estavam sendo salvos em arquivo, porém essa não é a melhor estratégia. Portanto, visando ao melhor desempenho do site, sua startup deverá desenvolver funcionalidades que permitam que os dados inseridos pelo usuário sejam salvos e posteriormente exibidos no relatório com base em manipulação e consultas no banco de dados MySQL.

Com a utilização de banco de dados, as suas aplicações web ficarão ainda mais robustas e profissionais. Bons estudos!

# **Conceito-Chave**

[![](https://ampli-images.s3.amazonaws.com/production/ce2d6782-7670-43ab-9e0f-044adf4658cf/original)](https://ampli-images.s3.amazonaws.com/production/ce2d6782-7670-43ab-9e0f-044adf4658cf/original)

Estudante, as diversas mídias dizem que estamos atualmente na Era da Informação, e que o bem mais precioso é a informação. Portanto, sempre que você desenvolver uma aplicação web é importante armazenar e disponibilizar informações aos seus usuários, incluindo dados sobre o produto que ele visitou no _e-commerce_, recorrência de acesso e quais cliques o usuário deu dentro do site. Considere a quantidade de informações armazenadas em um _e-commerce_: os dados cadastrais dos clientes, dados sobre os produtos, preços, estoque, carrinhos de compra, pagamentos e outros.

São tantas informações que seria inviável desenvolver um sistema desse tipo sem um banco de dados. Sempre que precisamos fazer persistência de dados, ou seja, armazenar e recuperar dados, uma estratégia muito utilizada é utilizar um Sistema Gerenciador de Banco de Dados (SGBD). Um SGBD é um _software_ responsável pelo gerenciamento dos dados, controlando os acessos, a consistência e a integridade desses dados. Alguns exemplos de SGBDs são o MySQL, MariaDB, _Postgre_SQL, _Oracle_ e Microsoft SQL _Server_.

# **Sistema gerenciador de banco de dados MYSQL**

[![](https://ampli-images.s3.amazonaws.com/production/445f48f3-f4fc-4df6-ae8f-41c9cc5751f1/original)](https://ampli-images.s3.amazonaws.com/production/445f48f3-f4fc-4df6-ae8f-41c9cc5751f1/original)

O MySQL é um SGBD relacional cuja primeira versão foi lançada em 1994. Em 2008 foi adquirido pela empresa _Sun Microsystems_ e, em 2010 a gigante _Oracle_, que tem um SGBD de mesmo nome, comprou a Sun Microsystems. Assim, atualmente o MySQL é de propriedade da _Oracle_, que mantém a distribuição do MySQL com código aberto (_open source_) sob a licença GPL (_General Public License_), permitindo o uso gratuito do MySQL, dispondo, também, de uma versão paga que pode ser incorporada a sistemas comerciais.

______

**💭 Reflita**

A licença do MySQL costuma ser um assunto que confunde muitas pessoas. Pesquise a respeito das condições de uso do MySQL e reflita sobre elas. Veja, ainda, as condições de uso do MariaBD e quais as diferenças desse SGBD com o MySQL.

______

Quando falamos de banco de dados relacional, dizemos que os dados são organizados em uma estrutura que relaciona e organiza os dados por meio dos seguintes elementos: tabelas (entidades), colunas (atributos) e registros (tuplas).

Para se comunicar com o banco de dados MySQL é utilizada a linguagem SQL (_Structured Query Language_), ou Linguagem de Consulta Estruturada. A linguagem SQL é adotada por praticamente todos os sistemas gerenciadores de banco de dados relacionais, sofrendo apenas pequenas mudanças quanto a sua sintaxe. Dessa forma, antes de aprendermos como se conecta ao banco de dados MySQL com PHP, vamos estudar um pouco a linguagem SQL, que permite a manipulação dos dados com as seguintes operações:

**Inserção**: para inserir um registro em uma tabela utiliza-se o seguinte comando:

[![](https://ampli-images.s3.amazonaws.com/production/e24f57cf-12b0-4b10-a832-6c04a800109e/original)](https://ampli-images.s3.amazonaws.com/production/e24f57cf-12b0-4b10-a832-6c04a800109e/original)

Observe que há um parêntese em que são adicionados os atributos da tabela que se deseja fazer a inserção separados por vírgula. No segundo parêntese são adicionados os valores desses mesmos atributos, seguindo a mesma ordem em que foram adicionados no primeiro parêntese. Caso o valor for algum texto ou data, deve-se colocar os valores entre aspas simples.

- **Alteração**: para alterar um registro de uma tabela é importante que se tenha o valor da chave primária (atributo que identifica unicamente uma tupla) do registro que se deseja alterar. A alteração é realizada pelo seguinte comando:

[![](https://ampli-images.s3.amazonaws.com/production/55c422a5-1ca1-40a3-aa00-8fcd66f1c438/original)](https://ampli-images.s3.amazonaws.com/production/55c422a5-1ca1-40a3-aa00-8fcd66f1c438/original)

A cláusula _WHERE_ serve para indicar qual é o registro a ser alterado.

- **Exclusão**: para excluir um registro de uma tabela é necessário que se tenha o valor da chave primária do registro que se deseja excluir, passando-o na cláusula _WHERE_, semelhante ao que acontece no comando para alteração:

[![](https://ampli-images.s3.amazonaws.com/production/bbdea274-9639-408c-8528-700b3535e511/original)](https://ampli-images.s3.amazonaws.com/production/bbdea274-9639-408c-8528-700b3535e511/original)

Entre os comandos da linguagem SQL, o mais versátil é o comando para consultar dados. Neste momento veremos apenas sua sintaxe básica, mas vale a pena você estudar mais a fundo esse importante comando. Para consultar todas as colunas de todos os registros de uma tabela basta utilizar o seguinte comando:

[![](https://ampli-images.s3.amazonaws.com/production/6f53bd74-aae4-4260-94ff-dd678f1073fa/original)](https://ampli-images.s3.amazonaws.com/production/6f53bd74-aae4-4260-94ff-dd678f1073fa/original)

O símbolo asterisco indica que serão consultados todos os atributos da tabela, mas muitas vezes desejamos consultar apenas alguns, o que deixa a consulta mais rápida. Para especificar as colunas que se deseja consultar, pode-se substituir o asterisco pelo nome das colunas separados por vírgula, conforme este exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/96f357db-9fb3-43ee-83c2-5e00b705a46d/original)](https://ampli-images.s3.amazonaws.com/production/96f357db-9fb3-43ee-83c2-5e00b705a46d/original)

É possível ainda adicionar filtros para que sejam mostrados apenas os registros que atendem a esse critério com a cláusula _WHERE_. Também é possível ordenar os dados utilizando a cláusula _ORDER BY_, conforme mostrado neste código:

[![](https://ampli-images.s3.amazonaws.com/production/55d6674a-a9b9-426d-a7c9-eb2aff946b9d/original)](https://ampli-images.s3.amazonaws.com/production/55d6674a-a9b9-426d-a7c9-eb2aff946b9d/original)

# **Criando o banco de dados**

[![](https://ampli-images.s3.amazonaws.com/production/dbb2fc22-5c0a-4b83-ae35-3a3ba1973683/original)](https://ampli-images.s3.amazonaws.com/production/dbb2fc22-5c0a-4b83-ae35-3a3ba1973683/original)

Para criar as tabelas do seu banco de dados você pode utilizar ferramentas auxiliares, como o MySQL _Workbank_ ou o PHP_MyAdmin_. É possível utilizar, por exemplo, a PHP_MyAdmin_ dentro do ambiente _PaizaCloud_ e assim não há necessidade de instalar algo mais no seu computador. Para isso, crie ambiente no _PaizaCloud_ (PAIZA INC, c2014), marcando as opções PHP, MySQL e php_MyAdmin_, conforme mostrado na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/40c544cd-5a9e-473d-9593-ac47ae863e49/original)](https://ampli-images.s3.amazonaws.com/production/40c544cd-5a9e-473d-9593-ac47ae863e49/original)

Criação do servidor PaizaCloud. Fonte: elaborada pelo autor.

Depois de criar o servidor, abra o navegador existente dentro do PaizaCloud e acesse o endereço: [https://localhost/phpmyadmin/](https://localhost/phpmyadmin/) .

Dentro desse endereço clique no menu “Banco de Dados” e crie um banco de dados, conforme exemplificado na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/6eec0e6f-e381-4f76-886c-10ee2a502885/original)](https://ampli-images.s3.amazonaws.com/production/6eec0e6f-e381-4f76-886c-10ee2a502885/original)

Criação do banco de dados. Fonte: elaborada pelo autor.

### **Criando tabelas**

Depois que criar o banco de dados deve-se elaborar as tabelas que receberão os dados a serem armazenados. Na figura abaixo está sendo criada uma tabela chamada “pessoa”, com os atributos de idpessoa, nome, cpf e telefone. O atributo “idpessoa” é uma chave primária (identificador único de cada registro), portanto, foi selecionada a opção _PRIMARY KEY_. Marcamos também a opção A.I., que significa “autoincremento”, ou seja, esse campo terá o seu valor atribuído automaticamente por meio de uma sequência numérica única.

[![](https://ampli-images.s3.amazonaws.com/production/f85c8c55-12ef-48da-8de0-64f181d9c3ce/original)](https://ampli-images.s3.amazonaws.com/production/f85c8c55-12ef-48da-8de0-64f181d9c3ce/original)

Criação da tabela. Fonte: elaborada pelo autor.

**💭 Reflita**

A plataforma de desenvolvimento _on-line PaizaCloud_ quando usada na licença gratuita, permite a criação de servidores temporários, ou seja, depois de 4 horas você perde todos os arquivos e o banco de dados criado. Será que podemos usar essa plataforma para projetos profissionais? Vale a pena configurar todo o ambiente de desenvolvimento localmente no seu computador?

______

### **Conectando ao banco de dados**

Agora que temos um banco de dados e uma tabela criados, podemos fazer a conexão utilizando a linguagem PHP, que disponibiliza algumas bibliotecas para conectar-se em diversos SGBDs disponíveis no mercado. No caso das conexões com o MySQL, usaremos a biblioteca **MySQLi**. Essa biblioteca disponibiliza diversas funções, com destaque para as seguintes:

- **Abrir conexão**: antes de executar qualquer comando no banco de dados, é necessário abrir uma conexão com a função _**mysqli_connect**_, passando como parâmetros o endereço do servidor, o nome do usuário, a senha e o nome do banco de dados. É necessário salvar o retorno dessa função em uma variável, que será utilizada nas funções seguintes para apontar para a conexão com o banco de dados, conforme este exemplo: _$con = mysqli_connect($server, $username, $password, $database);_
- **Executar comando SQL**: para executar um comando SQL (para inserção, alteração, exclusão ou consulta), podemos utilizar a função _**mysqli_query**_, passando por parâmetro uma variável que indica a conexão com o banco de dados e a _string_ contendo o comando SQL que se deseja executar. Nos casos em que o comando sql é de consulta de dados, é necessário salvar o retorno da variável para que possa ser utilizado na recuperação dos dados, conforme este exemplo: _$res = mysqli_query($con, $sql);_
- **Ler dados da consulta**: o comando _**mysqli_fetch_array**_ é capaz de ler um registro da consulta que foi realizada no banco de dados. Como parâmetro, deve-se passar uma variável contendo o resultado da consulta e o seu retorno é um vetor contendo as colunas e valores do registro. Caso queira fazer a leitura de todos os registros de uma consulta, é necessário combinar esse comando com uma estrutura de repetição, conforme mostrado neste exemplo:

_while ($row = mysqli_fetch_array($res)) {_

_echo $row_[“coluna”];

}

- **Fechar conexão**: os SGBDs têm um limite permitido para realização de conexões, logo é importante, ao concluir as operações com o banco de dados, fechar a conexão pelo comando _mysqli_close_, conforme mostrado a seguir: _mysqli_close($con)_;
- **Exibir erro**: quando estamos trabalhando com banco de dados, enviamos para ele comandos SQL, que serão interpretados pelo SGBD. Como esses comandos dependem da interpretação do MySQL, é possível que haja algum tipo de falha. Nesses casos pode-se exibir o erro na execução do comando sql por meio do comando _mysqli_error_, passando como parâmetro a variável que identifica a conexão: _mysqli_error($con)_;

______

**📝 Exemplificando**

A linguagem PHP permite que executemos comandos SQL no banco de dados MySQL. Mas como podemos utilizar todos esses comandos na prática? Considere o banco de dados chamado “meubd”, que contém uma tabela chamada “pessoa” com os atributos de “nome”, “telefone” e “cpf”. A seguir podemos ver um exemplo de código PHP capaz de inserir um registro nessa tabela e logo em seguida consultar todos os dados contidos na tabela. Cada linha do código está comentada com a função sua função.

[![](https://ampli-images.s3.amazonaws.com/production/c79032ed-820e-4f6c-a4d1-31d2f56d4fc5/original)](https://ampli-images.s3.amazonaws.com/production/c79032ed-820e-4f6c-a4d1-31d2f56d4fc5/original)

[![](https://ampli-images.s3.amazonaws.com/production/81625ed5-cb0f-4d29-8908-3568254f7fc8/original)](https://ampli-images.s3.amazonaws.com/production/81625ed5-cb0f-4d29-8908-3568254f7fc8/original)

[![](https://ampli-images.s3.amazonaws.com/production/01b8c28f-c20c-4520-9c62-11eb90e1ce09/original)](https://ampli-images.s3.amazonaws.com/production/01b8c28f-c20c-4520-9c62-11eb90e1ce09/original)

Inserção e consulta de registro de registro utilizando SQL. Fonte: elaborada pelo autor.

# **Autenticação de usuário, sessões e cookies**

[![](https://ampli-images.s3.amazonaws.com/production/185267fd-5ec8-448f-b17a-f4dac9ac1bb8/original)](https://ampli-images.s3.amazonaws.com/production/185267fd-5ec8-448f-b17a-f4dac9ac1bb8/original)

Estudante, agora que você já pode realizar a manipulação e consultas de dados no banco de dados, abordaremos a autenticação de usuário. Em uma rede social, por exemplo, quando você clica para ver seus amigos é mostrada uma lista contendo apenas os seus amigos, enquanto outro usuário que clica no mesmo link enxerga a lista dos amigos dele. Ou seja, para cada usuário é exibida uma informação diferente. Isso acontece também em sites de _e-commerce_, quando são sugeridos produtos direcionados para o usuário que está acessando a página.

A visualização ocorre dessa maneira porque cada usuário fez o seu login de acesso e tem sua identificação definida em todas as páginas que ele acessa na aplicação. Uma forma muito comum de se identificar o usuário é por meio da sessão, que em PHP é identificada pelo vetor (_array_) chamado $__SESSION_. Nesse vetor podem ser armazenados dados exclusivos para aquele usuário, de modo que ele tenha uma identificação única e diferente da dos demais usuários.

Quando o usuário fecha o navegador essa sessão é excluída automaticamente, garantindo a segurança do acesso daquele usuário. Para se utilizar a sessão de usuário em uma página PHP, é obrigatório que na primeira linha da página seja feita a inicialização da sessão pela função _session_start()_.

Um complemento ao uso da sessão é a utilização do banco de dados para validar o login do usuário; caso ele tenha digitado usuário e senha válidos, pode-se guardar o seu nome no vetor da sessão. Assim, qualquer página a que ele tiver acesso posteriormente, seu nome poderá ser resgatado para identificação ou para filtrar dados que serão exibidos para este usuário.

Considere que você tem um banco de dados com a tabela chamada “usuario” contendo os atributos de “idusuario”, “nome”, “email” e “senha”. Faremos, portanto, um formulário HTML em que o usuário poderá digitar o seu e-mail e senha. Caso ele digite um usuário ou senha válidos, seu nome será armazenado na sua sessão, então ele poderá navegar em todas as páginas da aplicação tendo seu nome exibido no topo das páginas. Acompanhe o exemplo a seguir, que ilustra um sistema de autenticação de usuário. A página _index.html_ disponibiliza um formulário em que o usuário poderá digitar o seu e-mail e senha:

[![](https://ampli-images.s3.amazonaws.com/production/d729f07c-a45e-4c18-b62f-59a20eb2555c/original)](https://ampli-images.s3.amazonaws.com/production/d729f07c-a45e-4c18-b62f-59a20eb2555c/original)

index.html – formulário de autenticação. Fonte: elaborada pelo autor.

Quando o usuário clicar no botão “_**submit**_” ele será redirecionado para a página “_login_.php”, a qual receberá os dados digitados pelo usuário no vetor $_POST. Note que a primeira linha do arquivo “_login_.php” é justamente a abertura do código PHP com a inicialização da sessão do usuário. Depois disso é realizada uma consulta no banco de dados para saber se o e-mail existe no cadastro de usuários e se a senha está correta. Caso o usuário e a senha sejam válidos, o nome do usuário é salvo no vetor de sessão e é disponibilizado um _link_ para o usuário navegar até a página de menu:

[![](https://ampli-images.s3.amazonaws.com/production/dcc1562f-16c0-411e-8568-d839a89b1dea/original)](https://ampli-images.s3.amazonaws.com/production/dcc1562f-16c0-411e-8568-d839a89b1dea/original)

[![](https://ampli-images.s3.amazonaws.com/production/76b7e823-caae-4ebe-8385-e70db0e6d632/original)](https://ampli-images.s3.amazonaws.com/production/76b7e823-caae-4ebe-8385-e70db0e6d632/original)

[![](https://ampli-images.s3.amazonaws.com/production/836621ee-d9f2-48d2-baaf-a86c10ed3903/original)](https://ampli-images.s3.amazonaws.com/production/836621ee-d9f2-48d2-baaf-a86c10ed3903/original)

[![](https://ampli-images.s3.amazonaws.com/production/ce920ca3-5384-4db7-bc17-ce7766564a8e/original)](https://ampli-images.s3.amazonaws.com/production/ce920ca3-5384-4db7-bc17-ce7766564a8e/original)

Quando o usuário clicar no _link_ para abrir a página de menu ou qualquer outra página que ele acessar a partir de então, basta iniciar a sessão com a função _**session_start()**_ e buscar o nome do usuário que está logado por meio do vetor $__SESSION_:

[![](https://ampli-images.s3.amazonaws.com/production/ef45847c-e30f-41e9-8238-600426d2558a/original)](https://ampli-images.s3.amazonaws.com/production/ef45847c-e30f-41e9-8238-600426d2558a/original)

Função session_start() para inicializar a sessão do usuário. Fonte: elaborado pelo autor.

O nome do usuário pode ser usado para muito mais do que simplesmente mostrar quem está logado. Pode-se, por exemplo, utilizar o nome do usuário para filtrar os produtos relacionados a ele em um site de _e-commerce_ ou as notícias com os assuntos que o usuário costuma ler, ou, ainda, uma lista de seus amigos em uma rede social. Essas consultas podem ser facilmente realizadas pelo banco de dados.

Existem casos em que não há área no site para se fazer autenticação do usuário por meio de _login_ e senha, mas, mesmo assim, deseja-se manter alguma informação salva sobre ele. A sessão de usuário então não é útil, pois quando o navegador é fechado os valores da sessão se perdem. Quando há a necessidade de se armazenar alguma informação especificamente daquele usuário é possível utilizar _cookies_, que basicamente são pequenas informações salvas no navegador do usuário.

Toda vez que o usuário voltar a acessar o seu site, você poderá ler os _cookies_ que foram salvar no navegador de quem está acessando. É importante notar que nos _cookies_ devem ser salvas realmente poucas informações, pois geralmente há um limite de no máximo 4Kb apenas para guardar informações desse tipo no navegador. Para salvar um dado no _cookie_ do usuário utilize a função do PHP _**setcookie**_, passando por parâmetro um nome identificador do valor e o valor que se deseja salvar. Também é possível enviar a data de expiração para esse valor, somando a uma função _**time()**_ a quantidade de segundos que você quer deixar esse dado disponível.

É obrigatório que a chamada da função _**setcookie**_ venha antes de qualquer código html ou impressão de dados com php, semelhante ao que ocorre com a função _**session_start**_, a qual colocamos logo no início do arquivo. Para recuperar algum dado armazenado no _cookie_ de usuário basta acessar o vetor $__COOKIE_, conforme mostrado no exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/1e7ad004-8e6c-498e-a4df-3c07f531fd34/original)](https://ampli-images.s3.amazonaws.com/production/1e7ad004-8e6c-498e-a4df-3c07f531fd34/original)

Função setcookie para salvar um dado no cookie do usuário. Fonte: elaborado pelo autor.

Infelizmente os _cookies_ não podem ser utilizados dentro do ambiente do _PaizaCloud_ ou do _Paiza.io_, pois são salvos no navegador do usuário (_Chrome, Firefox, Edge_) e ambas as plataformas de desenvolvimento on-line não utilizam navegadores reais, mas simuladores _on-line_. Portanto, para testar os _cookies_ é recomendável que você instale e configure o PHP no seu próprio computador para ter acesso a todos os recursos da linguagem PHP sem limitação.

Você pode então instalar o _software WAMPServer_ ([s. d.]), além de um editor de código como o _Microsoft Visual Studio Code_ (2021). A figura a seguir apresenta como a página PHP que grava _cookie_ pode ser executada utilizando _WAMPServer_:

[![](https://ampli-images.s3.amazonaws.com/production/ba0c217d-b84b-4b7b-b7e0-9445b88f694a/original)](https://ampli-images.s3.amazonaws.com/production/ba0c217d-b84b-4b7b-b7e0-9445b88f694a/original)

Execução da página com WAMPServer. Fonte: elaborado pelo autor.

🔁 **Assimile**

Uma informação importante para saber se o seu site está tendo sucesso ou não é a **taxa de recorrência** de seus usuários, ou seja, a quantidade de vezes que um usuário volta ao seu site. Nos casos em que não há interface para o usuário fazer _login_, é possível analisar essa taxa com um contador de acessos que utiliza _cookies_. Esse contador de acesso é único por usuário, pois o seu valor é salvo no navegador do próprio usuário. Assim, cada vez que um novo usuário acessa sua página, o contador inicia a contagem novamente, e você saberá que é um novo usuário entrando na sua página. A seguir, podemos observar um código que faz esse contador:

[![](https://ampli-images.s3.amazonaws.com/production/5593f219-5791-4396-a091-2191296ba026/original)](https://ampli-images.s3.amazonaws.com/production/5593f219-5791-4396-a091-2191296ba026/original)

Contador de acesso de usuários. Fonte: elaborado pelo autor.

**➕ Pesquise mais**

Um dos recursos mais relevantes do PHP é a capacidade de gerar conteúdo HTML dinâmico. Quando se usa um banco de dados, essa funcionalidade fica ainda mais interessante, pois podemos permitir que nossa página mude de conteúdo à medida que o banco de dados é alimentado. Acompanhe o exemplo a seguir, que mostra a realização de uma consulta em uma tabela de estudantes e suas notas. Note que de acordo com a nota do estudante a linha da tabela muda de cor: ficará em vermelho quando o estudante for reprovado ou em azul, quando for aprovado:

[![](https://ampli-images.s3.amazonaws.com/production/07a65d72-48b5-47a0-a4ab-57dac9821876/original)](https://ampli-images.s3.amazonaws.com/production/07a65d72-48b5-47a0-a4ab-57dac9821876/original)

Lista de Alunos. Fonte: elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/ad9987ea-9fef-4199-964e-a1056b21b1e8/original)](https://ampli-images.s3.amazonaws.com/production/ad9987ea-9fef-4199-964e-a1056b21b1e8/original)

[![](https://ampli-images.s3.amazonaws.com/production/0e6501a7-ed2d-4928-bb83-d6e0677671fb/original)](https://ampli-images.s3.amazonaws.com/production/0e6501a7-ed2d-4928-bb83-d6e0677671fb/original)

[![](https://ampli-images.s3.amazonaws.com/production/973dff12-ffae-4980-81c7-fd47238ba9b3/original)](https://ampli-images.s3.amazonaws.com/production/973dff12-ffae-4980-81c7-fd47238ba9b3/original)

[![](https://ampli-images.s3.amazonaws.com/production/5e21dbcc-de67-4cf8-86ef-51bd8931321e/original)](https://ampli-images.s3.amazonaws.com/production/5e21dbcc-de67-4cf8-86ef-51bd8931321e/original)

**➕ Pesquise mais**

Para aprender mais acerca da utilização de banco de dados com PHP, recomendamos a leitura das páginas 71 a 88 do material indicado a seguir.

BOECHAT, G. C. **Apostila de Linguagem de Programação I e II PHP**. Guarulhos, SP: Instituto Federal de Educação, Ciência e Tecnologia de São Paulo, 2014.

______

É incrível a quantidade de funções e recursos que a linguagem PHP nos disponibiliza. Vimos, nesta aula, o acesso ao banco de dados por meio de uma linguagem de programação, um recurso extremamente importante que permite desenvolver aplicações web complexas. Aplique os conceitos apresentados neste material e crie seus próprios portais para internet.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)

A fim de ampliar sua visão a respeito das possibilidades de aplicação dos conhecimentos obtidos até o momento, vamos propor uma resolução para a situação-problema apresentada no início desta aula. De acordo com ela, deve-se continuar a aplicação web em que o usuário deverá digitar a distância a ser percorrida, o preço da gasolina e o preço do etanol. Logo depois deverá ser calculado e exibido o valor gasto com cada um dos combustíveis, considerando um consumo de 9 km/litro de etanol e 11 km/litro de gasolina, além de mostrar ao usuário qual combustível gera menos custo.

Nesta aula vimos como adicionar o requisito de armazenar os dados digitados pelo usuário em uma tabela no banco de dados, criando, depois, um relatório que exibisse esses dados. A parte de código em que o usuário fará a entrada de dados _(index_.php) não sofrerá alteração alguma com a versão anterior, mantendo-se da seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/8b9a3556-31ab-49c8-a670-69deaf45d8d4/original)](https://ampli-images.s3.amazonaws.com/production/8b9a3556-31ab-49c8-a670-69deaf45d8d4/original)

Formulário para cálculo do preço do combustível. Fonte: elaborado pelo autor.

A página “resposta.php” sofrerá alterações para que os dados possam ser salvos no banco de dados, ficando de seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/d9bb612e-e529-4403-afe1-b3c0392a2459/original)](https://ampli-images.s3.amazonaws.com/production/d9bb612e-e529-4403-afe1-b3c0392a2459/original)

[![](https://ampli-images.s3.amazonaws.com/production/359c3ff8-ef34-44a2-a980-a72c927d426a/original)](https://ampli-images.s3.amazonaws.com/production/359c3ff8-ef34-44a2-a980-a72c927d426a/original)

[![](https://ampli-images.s3.amazonaws.com/production/dd8c193c-d466-468e-9488-7daecff50ced/original)](https://ampli-images.s3.amazonaws.com/production/dd8c193c-d466-468e-9488-7daecff50ced/original)

[![](https://ampli-images.s3.amazonaws.com/production/effea5a0-d2f3-46d0-8fc7-86a7c8f44aea/original)](https://ampli-images.s3.amazonaws.com/production/effea5a0-d2f3-46d0-8fc7-86a7c8f44aea/original)

Relatório de preços de combustível. Fonte: elaborado pelo autor.

Por fim, deve-se alterar a página de relatório para ela que seja capaz de exibir os dados que foram armazenados no banco de dados, conforme exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/91cb96ed-8794-4d5d-88de-492adfc0c9b9/original)](https://ampli-images.s3.amazonaws.com/production/91cb96ed-8794-4d5d-88de-492adfc0c9b9/original)

[![](https://ampli-images.s3.amazonaws.com/production/a622aa5a-fb74-4f0f-9592-f1a9e1a78d81/original)](https://ampli-images.s3.amazonaws.com/production/a622aa5a-fb74-4f0f-9592-f1a9e1a78d81/original)

[![](https://ampli-images.s3.amazonaws.com/production/eba4b13c-6a03-45db-98f7-59c0686f4fa5/original)](https://ampli-images.s3.amazonaws.com/production/eba4b13c-6a03-45db-98f7-59c0686f4fa5/original)

Relatório de preços de combustível. Fonte: elaborado pelo autor.

**➕ Pesquise mais**

Nesta aula aprendemos os comandos básicos dos comandos SQL, porém existem diversos recursos a serem explorados, especialmente na sintaxe da instrução de consulta de dados. Na atividade proposta com foco no mercado foi solicitado que você fizesse um relatório listando todos os dados inseridos pelo usuário a respeito do preço da gasolina e do etanol. Mas, e se em vez de listar todos os dados quiséssemos um resumo, informando qual é a média de preço de cada um desses combustíveis, qual o preço mais alto e qual o preço mais baixo? Para isso, podemos utilizar as funções agregadas que a linguagem SQL nos disponibiliza. Essas funções são capazes de agrupar dados mostrando o resultado da operação a qual ela foi designada, que pode ser dos seguintes tipos:

- **SUM**: calcula a soma dos valores.
- **AVG**: calcula a média dos valores.
- **MAX**: retorna o maior valor.
- **MIN**: retorna o menor valor.
- **COUNT**: conta a quantidade de valores.

Assim, podemos fazer um relatório sintético dos preços de combustível, conforme o exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/b8fda3df-29d3-4ecb-a6e6-f6bb459c9cf8/original)](https://ampli-images.s3.amazonaws.com/production/b8fda3df-29d3-4ecb-a6e6-f6bb459c9cf8/original)

[![](https://ampli-images.s3.amazonaws.com/production/1a586573-7f8b-4b49-a3fd-a350aa11d235/original)](https://ampli-images.s3.amazonaws.com/production/1a586573-7f8b-4b49-a3fd-a350aa11d235/original)

[![](https://ampli-images.s3.amazonaws.com/production/14cf5136-3ed1-4d9a-b0b2-b49dafeaf887/original)](https://ampli-images.s3.amazonaws.com/production/14cf5136-3ed1-4d9a-b0b2-b49dafeaf887/original)

Funções para agrupar dados. Fonte: elaborado pelo autor.

# **Referências**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

000WEBHOST. **Página inicial**. 000webhost, 2021. Disponível em: <https://br.000webhost.com/>. Acesso em: 1 ago. 2021.

AWS. **Comece a criar com a AWS ainda hoje**. Amazon, 2021. Disponível em: <https://aws.amazon.com/>. Acesso em: 1 ago. 2021.

BABIN, L. **Ajax com PHP: do iniciante ao profissional: crie poderosos aplicativos web interativos utilizando a força de Ajax e PHP**. Rio de Janeiro: Alta Books, 2007. 208 p. ISBN 9788576081463.

BITNAMI. WAMP. **Bitnami, 2021**. Disponível em: <https://bitnami.com/stack/wamp>. Acesso em: 1 ago. 2021.

BOECHAT, G. C. **Apostila de Linguagem de Programação I e II PHP.** Guarulhos, SP: Instituto Federal de Educação, Ciência e Tecnologia de São Paulo, 2014. Disponível em: <https://onbus.com.br/leeia.com.br/pdf/ApostilaPHP_2014.pdf>. Acesso em: 1 ago. 2021.

GOOGLE CLOUD. **Página inicial**. Google Cloud, 2021. Disponível em: <https://cloud.google.com/>. Acesso em: 1 ago. 2021.

HOSTINGER. **Página inicial**. Hostinger, 2021. Disponível em: <https://www.hostinger.pt/>. Acesso em: 1 ago. 2021.

KISIELEWICZ, L. A. **Um jogo eletrônico como ferramenta complementar no ensino de PHP**. 2012. 91 f. Dissertação (Mestrado em Ensino de Ciência e Tecnologia) - Universidade Tecnológica Federal do Paraná, Ponta Grossa, 2012.

MICROSOFT AZURE. **Página inicial**. Microsoft, 2021. Disponível em: <https://bit.ly/2Oo6ZpA>. Acesso em: 1 ago. 2021.

MILANI, A. **Construindo aplicações web com PHP e MySQL**. São Paulo: Novatec, 2010. 336 p. ISBN 9788575222195.

PAIZA CLOUD. **Página inicial**. Paiza Inc, c2014. Disponível em: <https://paiza.cloud/>. Acesso em: 1 ago. 2021.

ROTERMEL, F.; SOMMARIVA, L. W. **Inovações advindas na nova versão da linguagem de programação web PHP 7.0.** Revista Interdisciplinar Científica Aplicada, v. 10, n. 4, p. 1-20, 2016.

THE PHP GROUP. **História do PHP**. PHP, 2020. Disponível em: <https://bit.ly/38vUxLA>. Acesso em: 1 ago. 2021.

THE PHP GROUP. **História do PHP**. PHP, 2020. Disponível em: <https://bit.ly/3eE27HX>. Acesso em: 1 ago. 2021.

THE PHP GROUP. **História do PHP**. PHP, 2020. Disponível em: <https://www.php.net/manual/pt_BR/history.php.php>. Acesso em: 1 ago. 2021.

VISUAL STUDIO CODE. **Página inicial**. Seattle: Microsoft, 2021. Disponível em: <https://code.visualstudio.com/>. Acesso em: 1 ago. 2021.

ZERVAAS, Q.; LIMA, E. C.; KINOSHITA, L. **Aplicações práticas de web 2.0 com PHP**. Rio de Janeiro: Alta Books, 2009. 521 p. ISBN 9788576083269.