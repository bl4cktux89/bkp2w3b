[![](https://ampli-images.s3.amazonaws.com/production/8e11b00b-840c-482e-b575-3c9112d2996c/original)](https://ampli-images.s3.amazonaws.com/production/8e11b00b-840c-482e-b575-3c9112d2996c/original)

Os bancos de dados se tornaram essenciais para o sucesso de grandes corporações. Analisar informações de consumo de clientes pode trazer mais lucratividade para as empresas. Desta forma, atualmente, os bancos de dados se tornaram essenciais no desenvolvimento de softwares. De acordo com Guimarães (2003), ao se projetar um banco de dados, deve-se ter em mente um conjunto de aplicações que deverão utilizar estes dados. Os bancos de dados podem ser simples ou extremamente complexos. O analista de sistemas deverá propor soluções, levando em consideração o volume de informações que deverá ser armazenado.

Podemos afirmar que banco de dados é um conjunto de dados ou informações relacionadas entre si. Conforme Heuser (2009), banco de dados são coleções inter-relacionados de arquivos e que visam auxiliar vários. Exemplificando esse conceito, suponha que você vá fazer a matrícula numa faculdade. Primeiramente, você irá até a secretaria e lá passará os seus dados pessoais, informações acadêmicas, entre muitas outras informações, que deverão ser cadastradas em um banco de dados. Para gerar boletos de pagamento, você não precisará informar seus dados novamente, pois o departamento financeiro já possui suas informações no banco de dados (com as que foram fornecidas no ato da matrícula). São dois sistemas diferentes usando o mesmo banco de dados ou também, podemos dizer, usando a mesma base de dados.

Conforme afirma Date (2003), um banco de dados é uma coletânea de dados duráveis e acessíveis a vários softwares da empresa. O termo persistente faz referência ao armazenamento dos dados que só podem ser apagados do banco de dados através de alguma função específica e, claro, por alguém que tenha a permissão de excluí-los do banco de dados.

_______

**🔁 Assimile**

Um SGBD é um software cuja finalidade é gerenciar as informações de um banco de dados (também chamada de base de dados) segundo Navathe e Ramez (2005), e que também devem organizar, acessar, controlar e proteger as informações contidas no banco de dados. O SGBD tem por objetivo facilitar a vida do programador ou analista, deixando livre para pensar na modelagem e não ficar pensando em questões técnicas de armazenamento de dados (sendo esta uma das funções do SGBD).

_______

Quando nos referenciamos ao termo aplicação, estamos mencionando os softwares que estarão se beneficiando dos dados inseridos em um banco de dados. Por exemplo, como citado anteriormente, o sistema do setor financeiro de uma faculdade utiliza as informações arquivadas no banco de dados do sistema de controle acadêmico da secretaria da faculdade, ou seja, podemos dizer que existe um banco de dados único e centralizado para diversas aplicações utilizarem, conforme a Figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/a6de5ef3-9894-43f0-b434-7fde232302a2/original)](https://ampli-images.s3.amazonaws.com/production/a6de5ef3-9894-43f0-b434-7fde232302a2/original)

Aplicações em um banco de dados. Fonte: elaborada pela autora.

Na Figura acima podemos observar uma imagem central: o banco de dados. O acesso ao banco de dados por diversas aplicações necessita de regras específicas para garantir tanto a segurança quanto a integridade das informações inseridas. São diversos programas que executam essas garantias, conhecidos como SGBD ou Sistema Gerenciador de Banco de Dados. Observe na Figura abaixo como é o esquema do SGBD em relação às aplicações e ao banco de dados.

[![](https://ampli-images.s3.amazonaws.com/production/fa97f08c-8edc-41d8-934e-783ca9fb14f2/original)](https://ampli-images.s3.amazonaws.com/production/fa97f08c-8edc-41d8-934e-783ca9fb14f2/original)

SGBD em um banco de dados. Fonte: elaborada pela autora

Segundo Korth, Silberschatz e Sudarshan (2012, p. 19), um Sistema Gerenciador de Banco de Dados é constituído por um conjunto de dados associados a um conjunto de programas para acesso a esses dados. O SGBD é projetado para gerenciar grandes volumes de informações, chegando a 1.152.921.504.606.846.976 bytes ou exabyte. O SGBD tem como finalidade a garantia de que as informações que foram inseridas no banco de dados estejam seguras, protegendo de ataques indevidos quanto ao seu acesso ou problemas ocasionados por erros de software ou hardware.

O SGBD pode ser distribuído por diversos computadores, no mesmo local ou até em locais diferentes (espaços, cidades, países). Caso o SGBD esteja em locais físicos diferentes, cada um passa a receber o nome de nó, e uma operação realizada no banco de dados pode ser executada em um ou em mais nós. Os computadores e seus SGBDs se comunicam através de diversos protocolos de comunicação, de acordo com Navathe e Ramez (2005).

_______

**📝 Exemplificando**

A integridade é a garantia de que a informação armazenada no banco de dados esteja correta. Precisamos, na medida do possível, prevenir erros de integridade no banco de dados. Por exemplo: é necessário que o usuário informe a sua cidade de nascimento. A cidade que deveria ser informada é São Paulo, mas o usuário digita San Paolo. Caso seja feita uma pesquisa para informar os nascidos em São Paulo, esse usuário ficará fora do resultado. A forma de evitar que isso aconteça é solicitar o estado de nascimento e, a partir dessa informação, apresentar somente as cidades do estado que o usuário informou.

_______

O objetivo geral de um banco de dados é centralizar as informações em determinado computador (servidor ou servidores), permitindo o compartilhamento dos dados entre os mais diversos sistemas, conforme a primeira Figura apresentada. Com muitos usuários acessando os dados, podem ocorrer acessos concomitantes à mesma informação, por exemplo, no banco de dados de uma loja de eletrodomésticos, há disponível a última geladeira de uma determinada marca no estoque. Dois vendedores acessam simultaneamente o registro e vendem a geladeira para seus clientes. Com certeza, um cliente ficaria sem a geladeira, gerando muitos conflitos tanto para o cliente, quanto para a loja. Para este tipo de evento damos o nome de controle de concorrência, uma das finalidades essenciais de um SGBD e que, segundo Korth, Silberschatz e Sudarshan (2012), são técnicas utilizadas para garantir a propriedade de isolamento de transações que estão sendo executadas ao mesmo tempo.

Navathe e Ramez (2005) afirmam que um SGBD possui as funções de permitir aos seus usuários a pesquisa em um banco de dados para recuperar uma determinada informação, alterar e gerar relatórios das informações. Outras funções que podemos destacar do SGBD são a proteção e a recuperação dos dados quando houver problemas de hardware ou software, a segurança a acessos indevidamente autorizados, a possibilidade de compartilhar dados, a administração da redundância e a restrição de integridade dos componentes do banco. Conforme Guimarães (2003), o conjunto de requisitos de um SGBD recebe o nome de ACID dos termos em inglês **A**_tomicity_, **C**_onsistency_, **I**_solation_, **D**_urability_ ou, respectivamente, **A**tomicidade, **C**onsistência, **I**solamento e **D**urabilidade. O SGBD escolhido pela empresa deve possuir os fatores ACID para garantir que uma transação no banco de dados seja realizada com sucesso. Antes de vermos cada uma das quatro características de um SGBD, precisamos compreender o real significado de uma transação. O SGBD deve garantir várias propriedades durante uma transação.

Segundo Navathe e Ramez (2005), uma transação é um processo ou um determinado programa que pode incluir vários bancos de dados ou somente uma parte do banco de dados, realizando atividades como consultas, alterações e até exclusão de informações da base de dados. Para Korth, Silberschatz e Sudarshan (2012, p. 393), uma transação é uma consequência da efetivação de um programa (ou uma rotina) que acessa e possivelmente atualiza vários itens de dados. A transação é o resultado da execução de um programa de usuário escrito em uma linguagem de manipulação de alto nível ou em uma linguagem de programação, como Java, C# ou SQL, entre outras.

_______

**🔁 Assimile**

O que é um log de transação? O SGBD, para recuperar-se de uma transação com falhas, possui um log para registrar todas as operações realizadas em dados. Funciona como um histórico das modificações. Caso haja erro, através do log, haverá a recuperação dos dados para que eles voltem ao estado inicial.

_______

Agora que sabemos o que é uma transação, vamos entender os requisitos de um SGDB:

- A **atomicidade** garante que nenhuma ou a totalidade das operações da transação sejam realizadas com sucesso. Suponha que estamos aumentando os salários dos funcionários (este aumento é uma alteração em uma tabela e, neste caso, é uma transação) e que durante a atualização faltou luz. Somente uma parte dos funcionários receberá o aumento no salário, caso não haja a verificação de atomicidade. Conforme Korth, Silberschatz e Sudarshan (2012), a ideia por trás da garantia de atomicidade é que o sistema de banco de dados mantenha um registro (em disco) dos antigos valores de quaisquer dados a serem alterados. Caso haja algum problema durante a realização da transação, o SGBD restabelece os dados antigos, como se nunca tivessem sido modificados.
- A **consistência** preserva as regras impostas no banco de dados. Assim que a transação for finalizada, todos os dados devem estar íntegros. Um exemplo seria a soma de dois valores. Após uma transação, os valores iniciais não podem ser alterados, mas, é claro, se esta for a regra determinada no banco de dados. A consistência é a garantia de manter os dados íntegros durante e com a finalização da transação realizada no banco de dados.
- O **isolamento** é a segurança de que uma transação não interfira no trabalho de outra. Somente após o término de uma transação, ela estará liberada para receber outras. Korth, Silberschatz e Sudarshan (2012) afirma que, mesmo asseguradas as propriedades de atomicidade e consistência para cada transação, a intercalação das operações de várias transações concorrentes pode resultar em inconsistências (erros nos resultados e/ou nos dados). Alterações feitas por transações simultâneas precisam ser isoladas das alterações feitas por qualquer outra transação simultânea.

Atualmente, é difícil criar um projeto de banco de dados para uma única aplicação. Por mais que isso ocorra, cabe ao analista de sistema pensar e deixar o banco de dados modelado para futuras mudanças e adaptações. As principais características do uso de um banco de dados, conforme Navathe e Ramez (2005), são as seguintes:

- Natureza autodescritiva do SGBD.
- Isolamento entre os programas, os dados e a abstração dos dados.
- Suporte a diversas visões dos dados inseridos no banco de dados.
- Transações para diversos usuários do banco e a possibilidade de compartilhar os dados da base de dados.

Uma característica essencial de um SGBD é possuir uma ampla gama de possibilidades para definir a estrutura da base de dados e poder aplicar restrições no banco. Os programas de aplicação que irão acessar a base de dados devem ser criados independentemente da estrutura do banco. De acordo com Navathe e Ramez (2005), um SGBD oferece aos usuários uma representação conceitual de dados, omitindo vários detalhes, por exemplo, como os dados realmente são guardados ou como as transações são realizadas no banco de dados. Essa representação de modelo de dados é informalmente conhecida como abstração de dados.

_______

**📝 Exemplificando**

Uma visão (ou _view_) pode ser uma parte de uma base de dados, podendo ser resultantes de pesquisas que retornam parte das informações armazenadas. Um SGBD com suporte a múltiplas visões deve proporcionar facilidades para a definição de diversas visões. O controle de concorrência é o fator primordial para que o compartilhamento de dados e as transações sejam realizados com sucesso para todos aqueles que utilizam o banco de dados. Ao criar visões, podemos criar filtros protegendo certas colunas e tornando o código mais simplificado.