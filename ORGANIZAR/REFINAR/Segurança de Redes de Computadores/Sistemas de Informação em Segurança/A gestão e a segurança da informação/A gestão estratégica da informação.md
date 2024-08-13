# **Introdução da Unidade**

[![](https://ampli-images.s3.amazonaws.com/production/fc1a977d-5ad3-403e-8ab7-aff018390e01/original)](https://ampli-images.s3.amazonaws.com/production/fc1a977d-5ad3-403e-8ab7-aff018390e01/original)

### **Objetivos da Unidade**

Ao longo desta Unidade, você irá:

- esclarecer o ciclo de vida da informação;
- discutir o modelo PDCA aplicado aos processos do SGSI;
- analisar os conceitos de cibersegurança e ciberespaço.

Estudante, na unidade anterior vimos como os sistemas de informação e as tecnologias da informação e comunicação transformaram o mundo moderno. Vimos também a importância da informação e seus impactos nas organizações e na segurança pública e privada. Neste momento, prosseguiremos no nosso aprendizado, buscando conhecimentos sobre a gestão desses sistemas de informação, que processam o bem mais valioso das organizações atualmente, ou seja, a informação. Além disso, discutiremos sobre como é relevante que a informação que tramita nesses sistemas e tecnologias seja protegida contra a ação indevida de agentes maliciosos, porque a segurança da informação deve ser encarada como uma necessidade vital para as pessoas, organizações públicas e privadas e, principalmente, para os órgãos de segurança pública e as empresas e os agentes da segurança privada.

Dentro da ideia de contextualizar nossa aprendizagem, vamos pensar na situação a seguir que começa pela frase: “Futuro conectado compromete segurança na rede”. Foi a chamada que Fernando Bezerra leu na coluna Link, do Jornal “O Estado de São Paulo”

Fernando trabalha na Secretaria de Segurança do Governo do Estado de Minas Gerais - SSPMG, cuja função é analisar os riscos da rede e dos sistemas de segurança pública, que, atualmente, disponibilizam o acesso a diversos dados aos cidadãos e órgãos pela internet. Fernando Bezerra não ficou muito surpreso com a notícia que leu no site deste jornal de grande circulação, porque tem bastante conhecimento do assunto. Ele sabe das dificuldades e tem a exata noção de que a Rede Internacional de Computadores traz vários benefícios, mas carrega consigo riscos ilimitados aos usuários, às organizações e às corporações. Sua missão, como especialista em segurança de redes, é analisar todos os sistemas da SSPMG, a maioria destes voltados para a segurança pública, e levantar os acessos indevidos, às tentativas de invadir a privacidade dos agentes públicos, as invasões para obtenção dos dados diversos dos cidadãos e, ainda, as ações deliberadas aos servidores (grandes computadores) para provocar a queda e a inoperância dos sistemas.

Fernando Bezerra lida com vários sistemas alimentados pelas ocorrências dos órgãos policiais civil e militar, com os dados advindos dos Conselhos Comunitários de Segurança – CONSEG e com as informações oriundas dos órgãos de inteligência diversos, como a Rede Nacional de Integração de Informações de Segurança Pública, Justiça e Fiscalização – Rede INFOSEG. Seu desafio, o de gerenciar o fluxo da informação e evitar os acessos não autorizados, é grande.

Pelo visto, a missão de Fernando não é fácil. E realmente não é simples trabalhar diretamente com a informação, seja fazendo a gestão dela ou sua segurança. Mas será que esta é uma missão impossível? Qual será a forma correta de se administrar a informação? Como conseguir manter uma informação segura nessa era da internet? E como fica o papel da segurança pública e privada nesse contexto?

Para cada questão que possa ser levantada sobre este assunto, existirá uma resposta adequada e, nesta unidade, tentaremos buscar um pouco das nossas respostas, estudando a Gestão Estratégica da Informação; a Segurança da Informação; e a Segurança na Era da Internet. Sem sombra de dúvidas, vamos cursar um conteúdo instigante e muito atrativo, por isso, precisamos começar com firmeza e determinação.

Boa jornada e bom estudo!

# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/b422d5e2-a7f9-4a65-9819-0a9fc89063f1/original)](https://ampli-images.s3.amazonaws.com/production/b422d5e2-a7f9-4a65-9819-0a9fc89063f1/original)

### **Qual é o foco da aula?**

Na primeira aula desta unidade, abordaremos a importância da era digital, gestão da informação e SIG.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- identificar o ciclo de vida da informação;
- compreender os sistemas de informação nas organizações;
- interpretar o funcionamento típico de um SIG.

### **Situação-problema**

Dentro do nosso contexto de aprendizagem – Fernando, que trabalha na Secretaria de Segurança do Governo do Estado de Minas Gerais, cuja função é analisar os riscos da rede e dos sistemas de segurança pública utilizados em Minas Gerais – imagine agora que o Cabo Abreu, que trabalha há mais de vinte anos em um dos Pelotões de Polícia do 62º BPM da cidade de Caratinga – MG estava indignado logo em uma segunda-feira, porque sua mesa estava cheia de fichas de ocorrências dos plantões policiais do final de semana, as quais deveriam ser conferidas e lançadas no livro de ocorrência para que pudessem se transformar em boletins de ocorrência. A experiência do Cabo Abreu diz que ele deve ser criterioso com o registro oficial das ocorrências, pois caso insira um fato, uma pessoa envolvida ou o nome incorreto do policial que atendeu à ocorrência, podem acontecer desdobramentos diversos e, até mesmo, inviabilizar a ocorrência formal. Quando iniciou seus trabalhos na PM, Caratinga era uma cidade menor, mas com o crescimento da população veio a evolução dos crimes e, consequentemente, das ocorrências.

O Cabo Abreu já não estava muito satisfeito com aquela papelada que não acabava mais e, justo na segunda-feira, veio uma moça solicitando o boletim de ocorrência policial de um acidente envolvendo veículos e vítimas com lesões corporais, para dar entrada na solicitação do seguro. Aquele foi o estopim. Ele ficou pensando, será que não existe um sistema que possa agilizar a inserção dos dados diversos? Seria bom se a SSPMG se lembrasse das pessoas de Caratinga. Mas como seria este sistema em uma cidadezinha do interior? É possível que não chegue até nós. O melhor seria se eu lançasse a identidade e o CPF e já puxasse os dados do cidadão, dessa forma ajudaria muito a reduzir a papelada. Auxiliaria até mesmo os policiais no atendimento das ocorrências. Mas isso parece que é muito difícil!

Para ajudar a resolver os problemas do Cabo Abreu, você deverá elaborar um relatório contendo respostas para os seguintes questionamentos: o que seria necessário a SSPMG implementar em termos de sistemas? E como garantir a segurança de um sistema de ocorrências e registro de dados? É possível a Secretaria de Segurança Pública disponibilizar, integrar e proteger um sistema de ocorrências policiais em um local remoto?

Para ajudar o Cabo Abreu, precisaremos compreender o que é o mundo digital, onde as coisas acontecem on-line, facilitando a vida de todo mundo, e também saber como é feito o gerenciamento da informação que circula nesses sistemas, além de entender um pouco mais sobre esses próprios sistemas de informações gerenciais e de negócio.

Não podemos perder tempo, vamos ao conhecimento!

# **Era da Informação ou Era Digital**

[![](https://ampli-images.s3.amazonaws.com/production/ced077dd-19ec-4cb7-be0c-48967a317628/original)](https://ampli-images.s3.amazonaws.com/production/ced077dd-19ec-4cb7-be0c-48967a317628/original)

Estudante, vamos dar início a mais uma aula de estudo buscando conhecer os Sistemas de Informação em Segurança e, desta vez, abordaremos a Gestão Estratégica da Informação. Para tanto, começaremos com a identificação da Era da Informação para prosseguirmos com a aprendizagem de como pode ser feita a gestão da informação, além de nos aprofundarmos um pouco mais nos Sistemas de Informações Gerenciais (SIG) e nos Sistemas de Inteligência Empresarial (BI).

Vamos lá!

A Era da Informação ou Era Digital, também conhecida como Era Pós-Industrial, é o novo ciclo que a humanidade está vivendo desde o final do século passado, com o término da Revolução Industrial. Esta nova era pode ser caracterizada pelo papel transformador assumido pela informação na vida das pessoas, na sociedade, nas organizações. Neste meio tempo, o grande avanço da informática, da computação e das telecomunicações, originando o espaço cibernético, acelerou sobremaneira essa transição, acentuando ainda mais a projeção da informação como mola propulsora dessa revolução. Dessa forma, a Era da Informação passou a ser mais uma etapa na evolução da vida humana.

Nessa nova fase, os sistemas de informação ganharam popularidade e assumiram papéis desempenhados privativamente pelo homem, por causa da sua capacidade de raciocínio. A tecnologia tomar o lugar do homem não é novidade, pois isso já havia acontecido quando a automação industrial substituiu o operário no chão de fábrica, só que agora o computador está substituindo a capacidade do homem de processar informações e isso é muito impactante.  É claro que o homem ainda ficou com o papel de detentor do conhecimento e da sabedoria (e estes conceitos você já aprendeu na aula 1, da Unidade 1), através da sua criatividade e imaginação; detalhes que o computador ainda não é capaz de fazer. Por esse motivo, vem crescendo a importância do estudo e da qualificação profissional na vida do ser humano.

A tecnologia assumiu o controle da informação porque cresceu muito a capacidade da TI em gerar, armazenar, manipular e difundir informação de forma automática. Essa evolução transcendeu a capacidade humana, pois a informação passou a ser gerada, processada e transmitida de forma muito rápida e em grandes volumes, e essa velocidade e quantidade foram crescendo exponencialmente, sendo humanamente impossível realizar essa tarefa. Atualmente, por causa dessa velocidade da informação, tudo está mais rápido. O que era novidade em um momento, vira passado no instante seguinte. Foi o que aconteceu do pager ao smartphone, do disco de vinil ao stream de áudio e da televisão de tubo a smart TV, ou seja, as transformações são diversas e muito rápidas, sendo difícil de acompanhá-las.

_______

**📝 Exemplificando**

Para ilustrar essa aceleração e transformação promovida pela informação nos produtos e serviços comercializados pelas empresas, vamos tomar como exemplo dois modelos de automóveis muito conhecidos por todos: o Fusca e o Gol. O Fusquinha, um dos carros mais populares já comercializados pela indústria automobilística, reinou isolado no Brasil por mais de 25 anos, desde seu lançamento em 1959, até sair de linha em 1986. Detalhe, com o mesmo modelo! Em seguida, veio o substituto do Fusca, o também muito popular e conhecido Gol, lançado em 1980, sendo o primeiro modelo denominado pela Volkswagen (VW) como Geração 1 (G1), e durou até 1994. Portanto, 14 anos no mercado, quando foi lançado o Gol G2, em 1994, conhecido como “bola”, que durou apenas cinco anos, até ser substituído pelo Gol G3, em 1999. Este teve o mesmo tempo de vida do Gol G2, ou seja, 5, quando deu lugar para o Gol G4, em 2004. E agora estamos no Gol G5, desde 2007, isto é, o Gol G4 durou apenas 3 anos (MOTOR1.COM, 2015). Embora o Gol G5 ainda esteja em atividade passados mais de 10 anos, pode ser justificado porque a partir daí as maiores mudanças foram feitas no embarque de tecnologias nos automóveis, ou seja, o diferencial deixou de ser o modelo em si, mas sim a tecnologia à disposição do condutor, como conectividade, informação e entretenimento.

_______

Essa informação toda é propulsora da integração mundial que se vive atualmente, porque as notícias correm o mundo em segundos e os acontecimentos são narrados, às vezes, em tempo real, como se a história fosse contada dia a dia, além de permitir uma troca muito intensa de conhecimento provocando a rápida evolução de diversos setores da sociedade, como educação, cultura, lazer, economia, política e outros. Graças à integração promovida pela comunicação, as distâncias diminuíram, a sociedade ficou mais coesa e surgiu a globalização, um movimento de integração da sociedade mundial em torno da economia e da cultura, com o intercâmbio de produtos e de conhecimento. Na direção oposta desta integração mundial está o isolamento social do indivíduo, um fenômeno do mundo moderno que atinge um grande número de pessoas. Motivadas pelo fácil acesso à informação através das redes sociais e dos aplicativos, muitas pessoas vivem escondidas atrás de sua timidez e, apesar de estarem isoladas socialmente, interagem vigorosamente com a internet, ora com outras pessoas, ora com elementos virtuais e até mesmo trabalhando, e isto tudo sem nenhum contato físico com outra pessoa. Este é um sério problema da Era Digital.

_______

**💭 Reflita**

Imagine um profissional de segurança que passa seus dias a fio olhando para monitores de computador que exibem imagens sobre aquilo que se deseja manter seguro. Será que ele está mais propício ao isolamento social? Como evitar essa tendência? Você já se preocupou com isso? Essas questões também afligem os profissionais de segurança e não somente os adolescentes nerds e as pessoas introvertidas.

_______

Prosseguindo, podemos dizer que este momento da civilização também trouxe uma democratização da informação, porque praticamente todo mundo pode divulgar informações na internet e muitas delas ganham notoriedade rapidamente, são as conhecidas “**viralizadas**”, isto é, informações que ganham o mundo em poucos minutos na internet. Essa facilidade também tem seus reveses, porque existe muita informação não confiável, tendenciosa e fraudulenta circulando pela rede, tendo cada um saber selecionar o conteúdo adequado. Note que somente os meios de comunicação convencionais, como a televisão, o rádio, o jornal, as revistas e outros, tinham o poder de selecionar as informações que se tornariam públicas, e agora isso não ocorre mais. Por um lado, é bom porque fica mais difícil de se manipular a opinião pública apresentando conteúdos pré-selecionados, por outro, surgem muitas informações desqualificadas e improcedentes para processarmos. O fato é que a internet trouxe à tona um aglomerado incontrolável de informações onde se pode achar de tudo, desde a receita de um bolo até o manual de bombas caseiras, e da mais divina evangelização até a apologia ao nazismo e à violência.

Ainda sobre essa nova era, temos também o surgimento do conceito de cibernética como sendo uma ciência baseada nos sistemas de processamento das informações e que estuda a comunicação e o controle dentro da abordagem sistêmica da informação, onde a comunicação integra os sistemas de informação e o controle governa o desempenho destes no processamento e na transformação da informação (CHIAVENATO, 2004). Como desdobramento deste conceito, surgiram novas concepções e dimensões no ambiente de vida humana, como o espaço cibernético ou ciberespaço, que é justamente este universo de sistemas integrados pela comunicação em rede, que ninguém consegue ver ou pegar, mas onde ocorrem diversos fatos que geram impactos concretos e muito significativos na vida real. É a chamada Era Virtual, na qual o meio físico não existe mais, e tudo acontece de forma intangível e on-line, contudo, gerando consequências verdadeiras e efetivas.

Finalizando, esta é a nova era da civilização, na qual a comunicação passou a ser a essência da atividade humana, surgindo um novo tipo de sociedade, a conectada ou em rede, com novos universos, comportamentos, oportunidades, adversidades e desafios.

# **Gestão da informação**

[![](https://ampli-images.s3.amazonaws.com/production/d25e5e84-8098-4cfc-b2da-c70fd07fe11d/original)](https://ampli-images.s3.amazonaws.com/production/d25e5e84-8098-4cfc-b2da-c70fd07fe11d/original)

Compreender a complexa Era da Informação, na qual a informação é o bem mais valioso da sociedade, constituída pelas pessoas e organizações, é claro que esse bem deve receber um tratamento específico para manter sua utilidade e, principalmente, seu valor. Esse tratamento é conhecido como Gestão da Informação, que podemos conceituar como sendo a capacidade que uma organização deve ter para administrar ou gerenciar a informação durante todo o ciclo de vida dela. O ciclo de vida da informação é descrito de várias maneiras por diversos autores, porém, podemos considerar que compreende sua produção, obtenção ou coleta; sua classificação e seu armazenamento; seu processamento ou manipulação; sua transmissão, distribuição ou transporte; sua utilização; e, por fim, seu descarte ou destruição (Figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/bcda58e9-a1e8-4b27-af35-4752d3b455dc/original)](https://ampli-images.s3.amazonaws.com/production/bcda58e9-a1e8-4b27-af35-4752d3b455dc/original)

Ciclo de vida da informação. Fonte: elaborada pelo autor.

**🔁 Assimile**

Vamos entender o que significa cada conceito apresentado na Figura acima?

- **Produção ou busca**: gerar informação ou adquiri-la de alguma fonte, atendendo aos requisitos de necessidade da informação.
- **Classificação e armazenamento**: conservar a informação de forma estruturada em bancos de dados, categorizadas por características e critérios, principalmente, determinando que usuários terão acesso à informação.
- **Processamento**: transformação feita na informação para agregar significado e formatar sua apresentação.
- **Distribuição**: disponibilização da informação para os usuários autorizados.
- **Utilização**: empregar a informação de forma que produza os resultados desejados.
- **Descarte**: deixar de guardar a informação ou destruí-la.

_______

Geralmente, as organizações fazem gestão da informação com o objetivo de permitir que a informação permaneça segura e esteja disponível no momento certo para ser utilizada com oportunidade pelos usuários que necessitem da informação e estejam credenciados a acessá-la.

Vimos que a informação é a mola propulsora da atividade humana atualmente, por isso, as pessoas e as organizações precisam das informações em suas tarefas e processos, principalmente, aquelas que envolvam algum tipo de decisão. Fruto dessa necessidade de informação, surge a exigência de se administrar ou gerir este tão valioso ativo da sociedade digital.

As organizações que fazem gestão da informação buscam também:

- Produzir informação sobre seus processos internos.
- Coletar informações externas que de alguma forma influenciam ou interferem na sua atividade.
- Manipular suas informações através de sistemas de processamento de informações, buscando obter vantagem competitiva. Sistemas como o SIG que já conhecemos e veremos mais detalhadamente adiante.
- Promover uma comunicação ágil e segura para troca de informações entre suas repartições internas e com seus participantes externos.
- Utilizar informação nos seus processos de tomada de decisão, na arquitetura de novos produtos e no relacionamento com o cliente.
- Configurar cenários prospectivos do mercado e da economia, visando valer-se de decisões estratégicas e proativas que podem definir a sobrevivência da empresa.

A gestão da informação em uma empresa ou organização perpassa pelos sistemas de informação que a empresa utiliza, simplesmente porque estes participam diretamente da existência da informação, desde sua produção ou coleta; passando por seu armazenamento e processamento; e chegando à sua utilização e descarte (Figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/500135e6-a79d-4f44-92f0-77ca9567b20c/original)](https://ampli-images.s3.amazonaws.com/production/500135e6-a79d-4f44-92f0-77ca9567b20c/original)

Sistemas de informação nas organizações. Fonte: elaborada pelo autor.

Vendo por esta perspectiva, logo se nota que fazer gestão da informação não é uma tarefa simples nem pode ser desenvolvida ou executada por um profissional sem a devida habilitação técnica para levar a efeito esta delicada atividade dentro de uma empresa ou organização. Na verdade, esta é uma tarefa para um profissional específico, o Gestor da Informação. Esta profissão envolve a realização de todas as atividades que acabamos de aprender, além de participar de outras que envolvam informação dentro da empresa, tais como realizar pesquisa de informações estratégicas para os negócios da empresa, compor times de análise de cenários de mercado, estudar e otimizar fluxos de informação e gerenciar os bancos de dados internos e as fontes de dados externos. Em virtude do emprego de tecnologias da informação e comunicação na sua atividade, este profissional atua intimamente ligado com a área de TI da empresa, fazendo todas as interfaces necessárias para que sua missão obtenha sucesso.

# **SIG e BI**

[![](https://ampli-images.s3.amazonaws.com/production/83a5c606-fe37-4d49-8379-0234b30e4290/original)](https://ampli-images.s3.amazonaws.com/production/83a5c606-fe37-4d49-8379-0234b30e4290/original)

Vimos, portanto, como fazer a gestão da informação em uma organização e que, além de ser uma atividade vital para o negócio da empresa, está longe de ser uma tarefa fácil, principalmente porque envolve grande parte dos sistemas de informação empregados na organização, e somente promover essa integração já é motivo de bastante trabalho. Particularmente dois sistemas utilizados pelas empresas, em geral, são muito importantes para a gestão estratégica da informação, são eles: os Sistemas de Informações Gerenciais (SIG) e os Sistemas de Inteligência de Negócio (BI). Passaremos, então, a estudar detalhadamente cada um deles.

Começaremos pelos Sistemas de Informações Gerenciais (SIG), os quais já sabemos que recebem essa classificação porque atuam no nível tático ou gerencial dentro da estrutura da empresa e que reportam as operações básicas dela, através de relatórios e estatísticas sobre o desempenho da organização, permitindo o acompanhamento e o controle dos meios de produção, da produção propriamente dita e dos produtos e serviços gerados. Na verdade, um SIG é um sistema que envolve diversas tarefas reunidas em torno de um objetivo comum, ou seja, fornecer as informações necessárias para que os gerentes possam acompanhar e controlar o andamento do negócio da empresa, possibilitando intervenções e ajustes, quando necessário, visando a consecução dos objetivos do negócio e promovendo vantagem competitiva para a organização (LAUDON; LAUDON, 2007).

A operação básica de um SIG compreende o processamento de dados para a produção de informações que serão empregadas no sistema decisório de nível gerencial da empresa (FRANCO; RODRIGUES; CASELA, 2013). Esse processo se inicia com a coleta de dados pelos SPTs que resultam na manutenção de bancos de dados operacionais, geralmente, contendo dados sobre a produção, o volume de vendas, a contabilidade e outros. Os SPTs, por sua vez, se interligam com o SIG, fornecendo dados para os bancos de dados gerenciais. Dessa forma, o SIG pode realizar consultas estruturadas e processamentos nestes dados, buscando agregar significado a eles, isto é, transformando-os em informações, regularmente apresentadas em formato de relatórios que serão utilizados pela gerência (Figura abaixo). Os relatórios podem se apresentar de diversas formas, a critério da gerência e dentro das possibilidades de customização do sistema, podendo ser programados (semanal, mensal, anual); eventuais, sob demanda dos gerentes, em um momento de necessidade ou imposição; de indicadores, resumem índices de atingimento de metas; de adversidades ou exceções, quando ocorre algum evento ou comportamento anormal em alguma rotina; e outros (a Tabela abaixo mostra um exemplo fictício de relatório de um SIG).

[![](https://ampli-images.s3.amazonaws.com/production/f6baea0c-ef07-477d-9b3c-13a6a589a3cd/original)](https://ampli-images.s3.amazonaws.com/production/f6baea0c-ef07-477d-9b3c-13a6a589a3cd/original)

Funcionamento típico de um SIG. Fonte: adaptada de Laudon e Laudon (2007).

Um sistema tipicamente SIG deve apresentar algumas peculiaridades que o caracteriza discriminatoriamente de outros. Vejamos algumas delas (STAIR; REYNOLDS, 2015):

- Baseiam-se geralmente em dados internos da empresa.
- Executam operações e processamentos relativamente simples do ponto de vista matemático e estatístico.
- Processam dados históricos e atuais da atividade da organização, mas usualmente não projetam informações futuras.
- Servem exclusivamente para o ambiente interno da empresa, mais precisamente no que diz respeito à rotina interna da organização.
- Usualmente emitem relatórios padronizados.

[![](https://ampli-images.s3.amazonaws.com/production/0ac82931-86d4-4a76-a209-91d8a227caa6/original)](https://ampli-images.s3.amazonaws.com/production/0ac82931-86d4-4a76-a209-91d8a227caa6/original)

Exemplo de relatório gerado pelo SIG. Fonte: elaborada pelo autor.

Outro importante sistema, dentro do contexto de gestão estratégica da informação, é o Sistema de Inteligência de Negócio (BI), que também já estudamos e conhecemos como sendo resultado da integração dos sistemas da empresa com foco no processo decisório, primordialmente, no nível estratégico da organização. É exatamente isso, um sistema de BI também tem a finalidade de dar suporte ao processo decisório de uma empresa, assim como o SIG, porém voltado para o nível estratégico da organização. Por se tratar do nível estratégico, as informações a serem analisadas e os cenários a serem elaborados são muito mais complexos, por isso, em um sistema de BI são processados enormes volumes de dados, coletados de diversas fontes internas e externas a empresa, e são produzidas informações capazes de permitir uma clara interpretação do significado desses dados pela gerência estratégica da empresa.

Um sistema de BI é capaz de (i) extrair dados de múltiplos bancos de dados simultaneamente (Figura Sistemas de informação nas organizações), por meio de ferramentas específicas, como OLAP (_On-line Analytical Processing_ ou processamento analítico on-line), EIS (_Executive Information System_ ou sistema de informação do executivo), Data Mining (Mineração de Dados) e outros; (ii) processar toda essa massa de dados, considerando um contexto de análise, buscando estabelecer relações entre os dados e projetando hipóteses e tendências futuras neste contexto; e (iii) emitir relatórios, gráficos e composição de cenários de negócio. Tudo isso para permitir à empresa tomar medidas proativas para manutenção de suas estratégias de negócio, como prever tendências do mercado consumidor, antevendo o lançamento de produtos e até mesmo antecipando estratégias dos concorrentes (BROGNOLI, 2010).

_______

**➕ Pesquise mais**

Para ampliar seus conhecimentos sobre Sistemas de BI, leia o [artigo](https://alvarobrg.blogspot.com/search?q=Sistemas+de+BI) de Alvaro Brognoli, especialista em Gestão Estratégica Empresarial.

_______

Chegamos ao final de mais uma aula dos nossos estudos, espero que tenhamos conseguido aprender um pouco mais sobre os sistemas de informação e a gestão estratégica da informação. Dessa forma, poderemos prosseguir na resolução da nossa situação-problema.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/3df9b0ac-e463-4a26-b010-9211b0691d58/original)](https://ampli-images.s3.amazonaws.com/production/3df9b0ac-e463-4a26-b010-9211b0691d58/original)

Estudante, vamos a solução da nossa situação-problema. Você se lembra das reclamações do Cabo Abreu sobre o sistema de registro de ocorrências?

Para ajudar o nosso amigo, a SSPMG poderia implementar um sistema de informações de registro de ocorrências, disponibilizando acesso pela internet, podendo assim viabilizar o acesso para as mais remotas unidades de polícia do Estado de Minas Gerais, aproveitando o espaço cibernético de nossa Era Digital. Este sistema teria a finalidade de preencher bancos de dados de ocorrências, possibilitando o armazenamento destes, sua transmissão pela grande rede, sua utilização por agentes públicos de segurança e outros órgãos de interesse, mediante credenciamento de acesso, além do processamento dos dados por outros sistemas que possibilitem ações policiais mais eficazes contra o crime, advindas de sistemas de informações gerenciais da SSPMG.

Mas claro que nem tudo seria fácil assim, para garantir a eficiência do sistema e a segurança dos dados ali presentes, torna-se necessário a implantação de uma rotina de gestão das informações circulantes no sistema, desde sua produção, passando pelo seu armazenamento e transmissão, até sua utilização e descarte. Tudo isso pode, tranquilamente, ser integrado com outros sistemas da Secretaria de Segurança Pública, como citado anteriormente, para que seja feita uma análise e um cruzamento dos dados do sistemas de registro de ocorrências com os dados de outros sistemas, visando o levantamento de informações que seriam usadas nos processos decisórios dos órgãos de segurança pública – dentro da ideia dos SIG e BI –, permitindo um combate mais eficaz contra a criminalidade e até mesmo antecipando as ações criminosas, provendo uma segurança de melhor qualidade para a população. E, antes que esqueçamos, facilitando, é claro, o trabalho do Cabo Abreu, em Caratinga – MG, que não precisaria mais daquela papelada interminável e ineficiente.

O que você achou da nossa solução? Tenho certeza de que ficou bem parecida com a sua.