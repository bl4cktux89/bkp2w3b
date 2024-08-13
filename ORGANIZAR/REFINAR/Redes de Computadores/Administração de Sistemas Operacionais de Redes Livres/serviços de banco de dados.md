### Introdução

Bancos de dados são fundamentais para o desenvolvimento da inteligência dos negócios. O desenvolvimento de sistemas evoluiu para esferas da inteligência artificial principalmente pela capacidade dos bancos de dados. Embora seja por ignorância, muitas empresas mantêm, no interior de seus departamentos, muita informação enclausurada em planilhas, textos, etc., mas, pelo conhecimento acumulado em análise de sistemas, tudo deveria estar em banco de dados. Mas primeiro precisamos conceituar banco de dados.

### Conceito de Banco de Dados

Os bancos de dados são a principal forma de armazenamento nos mundos on-line e offline. Os bancos de dados são usados para armazenar milhões de diferentes tipos/combinações de informações, incluindo detalhes do produto, funcionários, cadernos de endereços pessoais, notícias, etc. Antes de começar a usar um banco de dados, porém, você deve entender os conceitos e teorias subjacentes e como eles são criados. Vamos dar uma olhada no que é um banco de dados, o modelo de banco de dados relacional, metadados e índices, o DBMS e SQL [1].

Vou gastar um pouco do seu tempo com isto, mas analisando porque alguns analistas e programadores não fazem uso completo das ferramentas, fez-me perceber que não o fazem porque não entendem exatamente com o que estão lidando. Hoje a computação transformou-se num “Lego”, aquele brinquedo de montar. Claro, isto trouxe vantagens em termos de produtividade, mas, pode estar certo, perdeu-se muito em capacidade de construir sistemas criativos que utilizam tudo, ou quase tudo, que a ciência pode dar. Na verdade, não só os usuários de áreas diversas são usuários, os próprios desenvolvedores são usuários e, portanto, não usam a computação para alavancar os negócios com toda a potencialidade da computação. Há exceções!! Antes que alguém fique nervoso aqui.

### A origem

Primeiro precisamos saber como a comunidade de computação chegou nos bancos de dados. Claro que não vamos aqui fazer todo aquele caminho de fichários, hollerit, anotações, etc., isto seria por demais tedioso e não acrescentaria nada. Explicar quando e como passamos a chamar nossos arquivos de banco de dados é mais valioso para o próprio entendimento do assunto. Os primeiros arquivos com informações sobre as atividades das empresas como, vendas, estoque, controle de salários, etc., eram, na verdade, uma pilha de dados gravados sequencialmente em disco. Existiam várias maneiras de fazê-lo e dependiam mais da criatividade do programador do que da tecnologia. O que eu quero dizer com isto? Bem, de um lado as grandes empresas de computação como Digital Corporation, IBM, Fujitso, Burroughs, etc. produziam sistemas de arquivos cada vez mais sofisticados [1]. Os primeiros eram como falei, uma pilha de dados, depois vieram os índices para melhorar o acesso. Por um longo período as melhoras tinham haver com a rapidez de acesso, soluções para um tipo de fragmentação que ocorre com os arquivos e outras funções. Ao programador ficava a tarefa de tirar melhor proveito disto. Para ter uma ideia, imagine que um programador precisava guardar a informação de vendas com os seguintes dados: Código do Produto, Código do Cliente, Quantidade e Data. A primeira opção seria gravar sequencialmente (aliás, o nome do tipo deste arquivo era “**arquivo sequencial”**) e os registros ficariam algo como:

**L15AB**

**C153212**

**30**

**25061982**

**L20XX**

**C132132**

**15**

**26061982**

**…**

Aqui temos 8 registros que na verdade representam duas compras. Uma seria o produto L15AB, vendido para o cliente C153212, na quantidade de 30, na data 25 de junho de 1982. Outra venda seria o produto L20XX, vendido para o cliente C132132, na quantidade de 15, na data 26 de junho de 1982. Quando um programa de consulta precisasse consultar isto, o programador sabia que a cada 4 registros, mudava a venda, então ele lia o primeiro registro e atribuía a uma variável no programa chamada Produto_Vendido, lia o próximo registro e atribuía à variável Cliente_Vendido, e assim por diante.

A computação para cálculos de física e engenharia foi sempre avançada em relação aos assuntos de negócios, afinal os computadores foram inventados para cálculos. Portanto já existiam vetores e matrizes, então aquela primeira venda seria toda indexada às variáveis com um índice de vetor, como: Produto_Vendido(1), Cliente_Vendido(1), e assim por diante. O próximo grupo de 4 registro (a outra venda) seria: Produto_Vendido(2), Cliente_Vendido(2), etc.

Outro programador, mais esperto, pensou: Como os cálculos e as ações computacionais em memória primária (aquela memória hoje chamada RAM) são mais rápidas do que em memória secundária (discos são mais lentos porque precisam de ações mecânicas para leitura e gravação), vou trazer as tarefas de separar os campos para o processamento interno e criou os seguintes registros:

**L15AB C153212 30 25061982**

**L20XX C132132 15 26061982**

**…**

Pronto, agora cada registro de arquivo que eu ler, já pego todas as informações de cada venda, apenas lembrando que a cada espaço em branco estarei lendo um campo diferente. Você provavelmente nunca viu nada assim, mas, acredite, na época, pequenas mudanças como esta representavam várias horas a menos de tempo computacional.

Não demorou para que os melhores programadores percebessem que, em caso de grandes volumes de arquivos, eu poderia criar mais um arquivo só com o código do produto e a indicação de em qual/quais ordem sequencial ele estava no arquivo de vendas, o nome disto era **índice**.  Então um arquivo de vendas como este podia ter um índice por produto, por cliente, por data. Eram arquivos menores e a leitura deles era mais rápida do que passar venda por venda para descobrir o que era consultado.

Não demorou muito para grandes empresas de computação criarem seu próprios métodos e juntarem aqueles vetores e matrizes com sistemas sofisticados de arquivos (**ISAM** - _**Indexed Sequential Access Method**_ e **VSAM** - _**Virtual Storage Access Method**_  eram o máximo que se podia fazer em termos de tecnologia de arquivos sequenciais, ambos da IBM) criando assim, programas cuja especialidade era organizar os dados de forma a uma mistura entre dados físicos no arquivo e dados lógicos nos vetores ficarem transparentes para o programador. Ele (o programador) só precisava saber o nome dos campos e o nome das “bases de dados” e o resto ficava por conta de programas gerenciadores de base. Basicamente, e muito grosseiramente, esta é a história do nascimento dos bancos de dados [1].

### Bancos de Dados

Conhecer o que são bancos de dados, e as várias variedades de projetos de banco de dados são o que esta seção pretende introduzir. Você não encontrará aqui uma teoria de banco de dados avançada. A ideia e saber o que você terá num ambiente Linux e o que pode fazer com isto.

Graças à internet, bancos de dados de todos os tipos têm sido o centro das atenções na tecnologia emergente como um meio bastante eficaz para armazenar e gerenciar dados. Os desenvolvedores de banco de dados possuem um domínio único e específico de habilidades que não são comuns à maioria dos profissionais de computação. Devido a isso, os salários para os administradores de banco de dados (especialmente aqueles que oferecem habilidades específicas como Oracle) são muito bons. Um conhecimento aprofundado dos sistemas de banco de dados e do projeto é essencial para o futuro da tecnologia e o surgimento contínuo de aplicativos de processamento de dados.Em primeiro lugar, já vimos porque os bancos de dados foram criados. Os bancos de dados acompanham e organizam dados. Os dados são a essência de qualquer negócio ou organização. O processamento de dados mantém as empresas competindo nos negócios em uma taxa cada vez mais rápida. Um banco de dados às vezes é referido como um "**DBMS** - Database Management System", ou SGBD - Sistema de Gerenciamento de Banco de Dados. O Microsoft Access, por exemplo, é um DBMS, juntamente com o Microsoft SQL Server, MySQL e Oracle. DBMS, no entanto, não desfrutaram de uma existência impecável. De fato, há muitos anos, algumas bases de dados eram simplesmente inviáveis.Bancos de dados usam **queries**. As **queries** interagem com o banco de dados para extrair, inserir e excluir registros ou trabalhar com os dados do banco de dados. Como acontece com qualquer processo que o computador deve concluir, é preciso alguns recursos de processamento. Bases de dados, no entanto, têm muito mais recursos que uma aplicação típica, como **queries** podem se tornar bastante grandes. Computadores de há 20 anos não eram simplesmente suficientemente poderosos para lidar com o processamento de dados, especialmente o modelo de banco de dados relacional (que vamos explorar em breve). À medida que os computadores começaram a avançar, as bases de dados começaram o efeito de bola de neve que vemos agora. Estamos apenas começando a perceber o poder absoluto de sistemas de banco de dados em profundidade e o poder de que esses sistemas podem implementar.Além disso, a base de dados é um campo único, que requer um conjunto único de habilidades, antes os programadores das aplicações comerciais faziam suas bases. Outra razão pela qual bases de dados eram inviáveis era simplesmente a falta de administradores qualificados para instalar e mantê-los funcionando eficientemente.

À medida que as bases de dados avançavam, os padrões eram comuns. O processo de atualização de informações em um banco de dados preenchido com dados repetidos gasta quantidades enormes de tempo. Considere o seguinte exemplo. Temos um banco de dados de vendas. Junto com o nome do produto, vamos listar o cliente que fez a compra e seu endereço de e-mail, a quantidade e a data da compra. Veja como que a tabela pode parecer:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/6/822660/36739.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/6/822660/36739.png)

Observe que para fazermos consultas, emitir relatórios e mesmo fazer cálculos e prever tendências de vendas, análise de estoque, etc., vou ler repetidas vezes vários nomes várias vezes, e-mails, etc. Isto não parece muito legal.

O modelo de banco de dados relacional nos dá uma alternativa, criando um link entre mais que umas tabelas diferentes. Podemos ler as informações dos produtos e colocá-los em uma tabela separada e relacioná-lo com a tabela de vendas e a mesma coisa com os dados de produto. A tabela mostrada acima funcionaria muito melhor se fosse projetada como estas abaixo:

Para o cadastro de Clientes:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822738/36741.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822738/36741.png)

Para o Cadastro de Produtos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822806/36742.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822806/36742.png)

E para o movimento de vendas:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/0/823075/36743.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/3/0/823075/36743.png)

Isso nos permite relacionar as duas tabelas entre si por uma chave primária; neste caso, é o campo Con_Cli da primeira tabela e Cod_Prod da segunda tabela. Uma chave primária é simplesmente um campo que é usado para definir uma referência relacional única para qualquer registro em uma tabela. Uma vez que a terceira tabela também tem campos que correspondem à chave primária de outras duas tabelas, nós nos referimos a eles como chaves estrangeiras.Você observou que os produtos e clientes na segunda e primeira tabelas se relacionam com as compras que eles fizeram na terceira tabela através da chave primária, Cod_Cli e Cod_Prod? Agora, nós poderíamos desenvolver uma aplicação que unisse as três tabelas juntas que nos dê os mesmos resultados que nós teríamos recebidos do primeiro modelo **não-relacional** (Base de Vendas) do exemplo. O que isso também nos permite fazer é atualizar e-mails, endereços (se houvessem) de cada cliente em um lugar e um único lugar, exigindo muito menos processamento do sistema. Em uma escala corporativa muito maior, você pode ver como esse tipo de banco de dados economizaria recursos de processamento.Bom, este é um olhar muito básico em bases de dados relacionais. Para os propósitos deste estudo de serviços de base de dados no Linux, você deve apenas lembrar que bancos de dados relacionais permitem que mais de uma tabela esteja relacionada (ou conectada) uma à outra para uma organização e eficácia muito superior em consultas e manutenção da base de dados.

### Banco de Dados no Linux

Primeiro vamos ver o que há no mercado em termos comerciais, livres e quais são os tipos de base disponíveis.

**1. Comerciais**

**1.1 Por tipo de acesso e tecnologia:**

**1.1.1Tipo SQL:**

**Oracle**: Atualmente, o Oracle faz com que seus produtos de software de servidor de banco de dados e suporte estejam totalmente disponíveis no Linux. A última tendência é apoiar a computação blade no Linux. A Oracle suporta uma extensão de procedimento SQL chamada PL / SQL, que acrescenta capacidade e vantagens quando usada com acionadores e scripts de banco de dados. A Oracle também tem um conjunto completo de ferramentas de desenvolvimento, bem como ferramentas de administração de acesso remoto. (**Atenção: Download gratuito de teste**)

**Banco de dados universal do IBM DB2 para Linux:** é o banco de dados principal da IBM usado em grandes data centers corporativos. (**Atenção: Download gratuito de teste**)

**IBM / Informix** - Informix introduziu muitas das mais recentes tecnologias de banco de dados e foi considerado o mais avançado. A Informix demonstrou um marketing pobre e foi finalmente adquirida pela IBM para salvar-se de ir a falência. A Informix também pode salvar a IBM de ficar muito para trás. O Informix para Linux está agora disponível na IBM.

**Borland Interbase - FireBird** (agora open source e chamado FireBird)

**Empress**: Embedded Database

**Adabas** (da Alemanha)

**MIMER SQL DBMS** - Padrão ISO PSM usado para store procedures.

**Clustrix** - altamente paralelo, distribuído, escalável e tolerante a falhas. Banco de dados SQL para grandes aplicações de dados.

**Pervasive** - base de dados de servidor SQL 2000 e SDK. Suporta JDBC, ODBC

**ScaleDB**: mecanismo de armazenamento plugável para o **MySQL**. Recuperação automática de nós com falha. Escalável, alta disponibilidade. Plugin comercial para um banco de dados de código aberto.

**DBshards** - consulta distribuída, escalonamento para o **MySQL**. Inclui drivers para Java, PHP, Python, Ruby.

**Raima** para Linux - banco de dados distribuído com espelhamento, replicação, particionamento. SQL, C / C ++ de baixo nível e APIs Labview.

**Sybase** para Linux

**1.1.2 Tipo Analítico:**

Os armazenamentos analíticos são bancos de dados (geralmente SQL) para grandes conjuntos de dados usados para relatórios e análises, onde a otimização e a compactação em colunas são importantes.

**HP Vertica** - banco de dados analítico orientado por coluna para consultas rápidas contra um grande wharehouse de dados. Nada de arquitetura compartilhada para escalabilidade. Executa em uma grade distribuída de servidores.

**Teradata Aster**: SQL / mapa reduzir dados grandes banco de dados analítico. Dados estruturados e não estruturados.

**IBM Netezza** - Dispositivo de banco de dados com uma arquitetura de processamento paralelo massivamente paralela usando FPGAs para suportar computação.

**XtremeData** - Banco de dados SQL distribuído em grande escala.

**Teradata** - arquitetura compartilhada distribuída nada para armazéns de dados maciços.

**1.1.3 Tipo não-SQL:**

Não apenas bancos de dados SQL. Não está restrito a um esquema de tabela fixa. Distribuído e escalável.

**FairCom**: C-Tree, servidor de banco de dados e servidor SDK - gerenciamento de arquivos, ISAM, ODBC multi-threaded API. Código fonte completo.

**Pick Systems**: D3 - Servidor de banco de dados. Também FlashConnect, FlashBASIC

**Solid** (da Finlândia)

**Cache** - Eles vangloriam-se sobre a velocidade e seu uso generalizado em saúde.

**Oracle: Berkeley Db** - pequeno apertado e muitas vezes usado em sistemas embarcados.

**HDFgroup.org**: formato de dados hierárquico (HDF) - armazenamento de dados baseado em arquivos grandes para coleções de dados complexas. Usado pela NASA para organizar, armazenar, descobrir, acessar, analisar, compartilhar e preservar dados de observação da Terra.

**DBMaker**: banco de dados SQL. Suporta ODBC, XML, COBOL, C ++, Visual Basic, Delphi, Perl e PHP. Usado para adicionar funcionalidade de banco de dados ao software.

**Gemfire**: armazenamento de dados elástico. VMware em memória

**1.1.4 Outros Tipos:**

**Software OpenLink: Virtuoso** - SQL, XML, WebDAV, SOAP, WSDL, ODBC, serviços web JDBC, produtos de middleware

**2. Uso Livre (Open Source).**

**2.1 SQL**:

**MySQL** -  Base adquirida pela Oracle, mas mantém compromisso com open source. **InfiniDB** - mecanismo de banco de dados escalável para data warehousing e armazenamento analítico. Colunas orientada DBMS plugin para MySQL. Projetado para consultas rápidas contra grandes armazenamentos de dados. Edições comerciais e comunitárias.

**InfoBright** - banco de dados relacional orientado a coluna baseado em MySQL focado em dados gerados por computador (logs da web, logs de rede, dados de sensores). Vendido como um pacote de hardware / software. Alta disponibilidade, auto-ajuste, backup / restauração.

**PostgresSQL** - incluído no Redhat distro

**Drizzle** - MySQL simplificado com recursos despojados (sem viewers, sem triggers, sem store procedures, sem ACL, ...) para suportar simultaneidade maciça

**SQLite**: Incorporar um mecanismo SQL em seu aplicativo. Domínio público.

**VoltDB**: Na memória, de alta velocidade, alta taxa de transferência de banco de dados SQL. Usa store procedures Java pré-compilados. Comunidade GPL e edições comerciais.

**SapDb** - SAP lançou banco de dados de código aberto

**Actian**: Banco de dados de código aberto Ingres

**GigaBASE**: Para bancos de dados de arquivos grandes (Tbyte). API C ++. Herda a maioria dos recursos do FastDB.

**FastDB**: Integração apertada com C ++.

**2.2 Bancos de Dados baseados em Java:**

**Apache Derby**: banco de dados relacional de código aberto implementado inteiramente em Java. O Derby é pequeno o suficiente para ser incorporado em aplicativos Java ou pode ser acessado no modo cliente / servidor usando o JDBC.

[**HSQL Database engine**](http://hsqldb.sourceforge.net/)**:** pequeno. Pode ser incorporado em um aplicativo.

[**MckoiDDB Distributed SQL Database**](http://www.mckoi.com/):: Suporta transações, triggers. GPL open source.

**2.3 Outros tipos:**

**GNU: gdbm** - hash extensível (clone de UNIX dbm)

**2.4 NoSQL:**

**Cassandra**: armazenamento de dados multi-master de alta velocidade paralelo e tolerante a falhas. Pode abrir fonte pelo Facebook.

**Apache HBase**: Base de dados distribuída tolerante a falhas usada no framework Hadoop. Utiliza HDFS (Hadoop Distributed Filesystem). Java

**Apache Hadoop**: Estrutura Hadoop baseada no Sistema de Arquivos Distribuídos Hadoop (HDFS) e no Mapa - Reduz o processamento paralelo distribuído no armazenamento de dados. Framework inclui "Zookeeper" para suportar alta disponibilidade através de serviços redundantes.

**Estes abaixo são front-ends do Hadoop**

- **Presto** (lançado pelo Facebook, rápido, ANSI SQL)
- **Hive** - Simula SQL
- **Hortonworks Stinger** (uma versão mais rápida do Hive)
- **Cloudera Impala**

**Kai**: clone de código aberto do armazenamento em nuvem **Dynamo NoSQ**L da Amazon.

**Kademlia**: tabela de hash distribuída para clusters.

**Hypertable**: modelado a partir do banco de dados "Bigtable" do Google.

[**High Performance Computing Cluster (HPCC)**](http://hpccsystems.com/)**::** LexisNexis map-reduced paralelo para  armazenamento de dados. C ++.

### Implementando um Serviço de Base de Dados no Linux

Basicamente, vamos fazer o nosso experimento com um único sistema de base de dados. Escolhi o SQL Server por ser bastante genérico e quase que um padrão para Windows, criando um leque maior de possíveis clientes para seu serviço de base de dados.

A versão chamada SQL Server vNext CTP1, está atualmente disponível para Ubuntu, Red Hat Enterprise e outras distribuições via Docker containers. Muitas opções para os usuários do Linux. Desde que eu estou executando o Linux Ubuntu no meu computador, os exemplos nesta revisão pertencerão ao Ubuntu [2].

### Instalação

Como muitas aplicações, a pré-visualização do SQL Server para Linux deve ser instalada a partir da linha de comando.

Abra o terminalPegue as chaves GPG públicas para criptografar suas sessões digitando a seguinte linha: (**não esqueça de ser um superusuário**)**\#curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -**

Registre o repositório Ubuntu do Microsoft SQL Server digitando a seguinte linha:

**\#curl https://packages.microsoft.com/config/ubuntu/16.04/mssql-server.list | sudo tee /etc/apt/sources.list.d/mssql-server.list**

**CUIDADO COM ESPAÇOS E MANTENHA O ?SUDO? APÓS O PIPE MESMO SE VOCÊ FOR SUPERUSUÁRIO. ALIÁS, COPIE E COLE O COMANDO...**

Fica algo assim:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822782/36744.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822782/36744.png)

Finalmente, instale um SQL Server atualizado para Linux digitando os seguintes comandos:**#****apt-get update****\#apt-get install -y mssql-server**

Ao terminar, você verá o print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822783/36745.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822783/36745.png)

Observe que a instalação ocorreu bem. O tempo maior foi do download de aproximadamente 169 MB do programa principal. O próprio instalador avisa para executar o setup (entre duas linhas tracejadas).

A partir daqui vou mostrando as telas do setup:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822794/36746.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822794/36746.png)

Ao final, pergunta se você aceita os termos da licença e pede uma senha para o administrador.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822796/36747.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822796/36747.png)

Para verificar se está tudo ok, digite o comando abaixo:

**\#systemctl status mssql-server**

Resultará no print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822799/36748.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/7/822799/36748.png)

**Tudo Ok! O SQL Server já está pronto e “ouvindo” a porta padrão 1433.**

**Esta licença lhe dará 171 dias de testes.**

### Ferramentas para SQL Server

A pré-visualização do SQL Server para Linux é um aplicativo de linha de comando, então você vai precisar das ferramentas certas para se trabalhar nesse ambiente. A Microsoft oferece algumas ferramentas muito úteis para esse trabalho, incluindo **sqlcmd**. O utilitário **sqlcmd** foi projetado para otimizar consultas SQL e simplificar um número de tarefas da administração de banco de dados. Por exemplo, é ótimo para processamento em lote e outros processos repetitivos, bem como para simular a carga de bancos de dados de teste.

**Bcp** é outra ferramenta interessante disponível para testes do **SQL Server vNext CTP1**. Um programa para facilitar cópias de grandes volumes, o **bcp** é um utilitário de linha de comando que permite copiar trabalhos gerados por grandes consultas para um arquivo de dados e vice-versa, mais rápido do que a média dos bancos de dados. Um exemplo simples seria a importação de dados de empregados existentes em uma tabela que você criou com o SQL Server. O BCP é tão flexível que pode lidar com o todas as suas necessidades de importação e exportação.

As ferramentas de linha de comando não estão incluídas na instalação, portanto teremos que instalar os utilitários **sqlcmd** e **bcp** separadamente. Felizmente é tudo muito simples e direto. Vamos começar repetindo as três primeiras etapas do processo de instalação. Mas, em vez de instalar o SQL Server novamente, instalaremos as ferramentas atualizadas inserindo os seguintes comandos:

**\#curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -**

**curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list | sudo tee /etc/apt/sources.list.d/msprod.list**

**\#apt-get update**

**\#apt-get install mssql-tools**

Aparecerá a seguinte tela: Siga os passos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822802/36749.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822802/36749.png)

Depois:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822805/36750.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822805/36750.png)

E a tela final do terminal Linux, terminará assim:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822811/36752.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822811/36752.png)

### Conectando-se ao SQL Server

Outra função crítica que **sqlcmd** executa é conectar-se ao próprio servidor de banco de dados, que é necessário para criar os bancos de dados, importar dados, criar tabelas  e assim por diante. Podemos criar uma conexão segura com o SQL Server simplesmente abrindo o terminal e executando **sqlcmd** com parâmetros para nosso nome de usuário e a senha que criamos anteriormente. Seu comando será parecido com o seguinte: **#/opt/mssql-tools/bin/sqlcmd -S localhost -U SA**

Nota: Você pode digitar 'localhost' no lugar do nome de usuário e omitir a senha para ser solicitado na próxima linha, como ilustrado no comando acima. Acho que comandos mais curtos são mais fáceis de executar e não fazer besteira.

Aqui é onde as coisas ficam complicadas. Por alguma razão, o Linux não dá nenhuma indicação de que fizemos uma conexão bem-sucedida com o servidor. Calma! Se o terminal não mostrar quaisquer erros, é mais provável que todos os sistemas funcionam. Você saberá com certeza se está tudo certo se você vir uma saída semelhante à seguinte captura de tela:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822813/36768.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/8/822813/36768.png)

Bem, se você chegou aqui, está tudo ok.

### Conclusão

Parabéns, você tem um **Serviço de Banco de Dados** disponível!! Você tem um **Servidor de Banco de Dados.** O escopo deste tópico não permite que avancemos em direção a criar bancos de dados e tabelas com seus campos. A obrigação do administrador de redes seria deixar operacional um servidor de banco de dados e aqui está!