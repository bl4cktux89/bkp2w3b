### Introdução

Quando falamos de previsão ou prognósticos, nos submetemos ao estudo de uma ciência capaz de prever eventos futuros. É utilizada em diversas áreas como a de previsões climáticas e a de mercados financeiros. Devemos utilizar com bastante ênfase essas técnicas também no planejamento de serviços na web para que se possa prever a quantidade de usuários que se conectarão nos serviços e os dados que serão transportados.

Atualmente, a maioria das empresas baseia seu funcionamento em um banco de dados, onde suas transações são efetuadas e depositam todo o seu lado informatizado. Com a internet, iniciou-se uma verdadeira corrida contra o tempo, que resultou no desenvolvimento de sites web, puramente estáticos e de necessária manutenção, nos quais as organizações passaram a disponibilizar suas informações essenciais aos clientes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/1/7/221772/4605.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/1/7/221772/4605.png)

Ambiente cliente/servidor

### Arquitetura de servidores web

Hoje, a web é um dos meios mais poderosos de comunicação, que tem provocado grandes impactos em qualquer área de atuação profissional.

Com o passar dos anos, grandes corporações começaram a colocar algumas de suas aplicações críticas na web e tornou-se crucial administrar os problemas que o desenvolvimento nesta plataforma pode ocasionar. A internet impôs um novo modelo de desenvolvimento de aplicações, o de sistemas/aplicações web. A partir disso, a grande maioria das empresas está colocando seus sistemas na web pela praticidade e globalização dos meios envolvidos, principalmente os servidores web (MENASCE; ALMEIDA, 2002).

Com o advento desses servidores e aplicações, esse novo modelo de desenvolvimento possibilita a criação e a distribuição de aplicações cada vez mais complexas. Alguns fatores foram importantes para que o uso deles se tornasse uma unanimidade nos dias de hoje, vejamos:

Na maioria das empresas existe uma programação totalmente organizada no que se refere às funcionalidades citadas, a qual possibilita uma divisão bem clara dessas partes no projeto de um software.

A evolução no projeto de interação entre o usuário e os computadores, ou seja, a evolução da arquitetura cliente/servidor:

Arquitetura de duas camadas.

Arquitetura de três camadas.

O amadurecimento da internet, permitindo uma rápida transmissão de mensagens entre computadores de qualquer parte do mundo e, consequentemente, o rápido crescimento de utilização da web.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/8/2/348276/24861.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/8/2/348276/24861.png)

Servidores e clientes

### Entendendo as aplicações web

Antigamente os processos eram feitos diretamente no computador cliente. Toda regra de negócio era realizada localmente e apenas os dados ficavam no servidor. Com a utilização de servidores web tudo ficou mais fácil tanto do lado do cliente como do lado do servidor.

A arquitetura cliente/servidor na web ficou mais enxuta e simples de se entender. Primeiro vamos ver o lado do cliente.

**O cliente web**

O computador cliente utiliza o protocolo TCP/IP e um browser para mostrar os dados e interagir com o usuário e o servidor.

**Modelo tradicional cliente/servidor**

Ao executar aplicações, uma máquina-cliente do modelo cliente/servidor tradicional roda um software que é armazenado localmente, parte da lógica da aplicação. Alguma aplicação pode ter outra parte armazenada e executada em um servidor, mas a maioria está no cliente. O servidor fornece os dados para a aplicação. Nenhum software adicional é necessário, além do sistema operacional e o da própria aplicação (KUROSE, 2006; TANENBAUM, 2003).

**O servidor web**

No lado do servidor temos uma tecnologia mais complexa, conforme descreve Kurose (2006) falando sobre a camada de aplicação. O protocolo TCP/IP mantém a comunicação, o servidor web interage com o browser do usuário no lado-cliente e um novo software é adicionado – o servidor de aplicações interage com o banco de dados e com arquivos HTML. Um servidor web provê e retorna arquivos HTML estáticos. O servidor de aplicação combina modelos, dados oriundos de um banco e outros elementos para criar arquivos HTML, dinamicamente. Para que o servidor web faça o download, ele não deve saber que está capturando nada além de texto com base em um arquivo HTML.

**Servidores de aplicação web**

São softwares que agem como intermediários entre um servidor web e uma base de dados.

Consequentemente, de uma forma lógica, entre um browser (no cliente) e uma base de dados (no lado servidor) que tem a informação desejada. Um servidor de aplicações é responsável por manter uma lista de serviços que podem ser obtidos e prover um canal de comunicação entre esses serviços e os clientes.

Os servidores de aplicações web geram o processo de ligação dos utilizadores de informação aos dados em que estão armazenados, envolvem tecnologia orientada a objetos na forma de objetos tradicionais e componentes de software. O mundo dos servidores de aplicações baseia-se na estrutura e nas interfaces bem definidas dos objetos e dos componentes. São partes de uma infraestrutura que deve permitir aos programadores web a construção de aplicações que trabalhem com uma grande variedade de hardware e softwares cliente e que possuam funcionalidades para serem integrados aos recursos existentes. Contém ainda a lógica da aplicação e situa-se entre o servidor web e o banco de dados. Esta arquitetura rigorosa permite a interoperabilidade entre os produtos de vários fornecedores. Provêm a infraestrutura de run time e serviços necessários para implementar aplicações ou componentes em uma arquitetura de várias camadas que suportam a web e outras interfaces com o cliente (KUROSE, 2006).

O servidor de aplicação web contém a lógica da aplicação e situa-se entre o servidor web e o banco de dados e controla a conexão com o banco de dados em função das requisições do browser. A web é stateless, ou seja, o servidor web não segura a primeira interação com o banco de dados, mesmo se cliente retornar apenas alguns segundos depois. Cada um dos componentes desta arquitetura (servidor web, servidor de aplicações e banco de dados) pode comunicar-se com outros elementos. A comunicação com esses outros elementos não é, geralmente, baseada em padrões abertos (KUROSE, 2006).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/5/347536/26755.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/5/347536/26755.png)

Partes do Modelo Web

### Entendendo a carga de trabalho

Em serviços na web, é importante prever a quantidade de requisições que chegarão a um servidor, isso é essencial para garantir o QoS (Qualidade de Serviço) da aplicação, pois é de suma importância (CAVANAUGH; ODOM, 2004).

Vejamos o seguinte cenário:

O site da Receita Federal do Ministério da Fazenda recebe todo ano a demanda das declarações de imposto de renda de pessoas físicas e jurídicas, porém com muita frequência as declarações tendem a ser entregues nos últimos dias. Sendo assim, esse serviço degradará no que diz respeito ao tempo de resposta e velocidade, à medida que os contribuintes enviam suas declarações. Esse cenário indesejável dá ênfase à importância do bom prognóstico e planejamento para os serviços da web.

O desempenho dos sistemas web, que possuam muitos usuários conectados a servidores e redes, depende bastante da carga de trabalho que será demandada. Consideremos um servidor web que, durante 15 minutos, teve 80.000 pedidos efetuados. A carga de trabalho do servidor web durante esse período de 15 minutos será os 80.000 pedidos efetuados. As características da carga de trabalho são representadas por um conjunto de informações, por exemplo, tempo de chegada e de conclusão dos pedidos, tempo de CPU, tempo de rede, tamanho do objeto solicitado para cada um dos 80.000 pedidos feitos pela web.

Existe um conjunto considerável de trabalhos sobre caracterização da carga de trabalho do tráfego da web como mostra Allspaw (2008) e Subraya (2006). Algumas das características consideradas tratam das distribuições de tamanho de arquivo, da popularidade do arquivo, e de itens comuns no tráfego da web.

Devemos saber também que outras propriedades básicas são encontradas na análise do tráfego real da web, uma delas é a tendência de se observar o tráfego que passa na rede. Um monitoramento visual do número de pedidos que chegam a um servidor web em diferentes escalas de tempo, ou seja, em intervalos de tempo de tamanho variável, pode mostrar esse tráfego da rede e a alta variabilidade do processo de chegada. Esse tipo de processo de chegada, pode degradar o desempenho do serviço se não for levado em consideração.

Os benchmarks utilizados para medir o desempenho de servidores web normalmente empregam uma carga de trabalho padrão (STAPENHURST, 2009), que inclui páginas HTML geradas estática e dinamicamente. As características de cada conjunto de páginas, ou seja, tamanhos de arquivo e frequências de acesso, podem ser modeladas por meio de parâmetros de entrada.As características da carga de trabalho do SPECweb, benchmark projetado para medir capacidade de um sistema de atuar como servidor web, por exemplo, foram coletadas de registros (logs) de vários servidores populares da internet e alguns sites web menores. Assim, a carga do SPECweb tenta imitar padrões de acesso aos documentos de um servidor Web típico, em que 70 dos pedidos de páginas estáticas e 50% dos arquivos requisitados são de tamanho até 10KB.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/6/363611/29047.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/6/363611/29047.png)

Distribuição de carga de trabalho

### Previsão de carga de trabalho

A utilização de uma técnica de previsão em uma atividade qualquer está ligada à existência de uma diferença de tempo entre a expectativa e o acontecimento de um determinado evento, isto é, o tempo que um determinado evento demora para ocorrer a partir de um certo instante (MENASCÉ et al., 2004). Quando essa diferença de tempo é significativa para um processo em questão, a execução de um planejamento ou até mesmo de uma previsão torna-se aplicável (MENASCE; ALMEIDA, 2002).

O termo previsão trata da utilização de uma função ou modelo matemático que, com base em dados ocorridos no passado, fornece uma avaliação para um instante futuro.

Efetuar a previsão da demanda requer um conjunto de hipóteses e suposições. O tempo desempenha um papel importante no processo de previsão. Quanto maior o tempo de amostragem, menos exato será o prognóstico.

**Variações das cargas de trabalho**

As cargas de trabalho numa rede de dados, segundo Kurose (2006) podem mudar por diversos aspectos. Abaixo citamos os mais relevantes:

- **A variação do número de usuários.**
- **O número de mensagens por usuário.**
- **O tamanho das mensagens.**
- **Variação dos recursos oferecidos pelo sistema**

Esses aspectos variam em sua quantidade, o que dificulta ainda mais a previsão da carga.

Pensando nas cargas de trabalho da Web, segundo Cavanaugh e Odom (2004) as empresas precisam atender as expectativas dos clientes e garantir o QoS, sendo assim os problemas de desempenho em um ambiente on-line devem ser antecipados. Sabemos também que um correto dimensionamento da carga de trabalho aumenta o QoS.

### Estratégias de Previsão

Para Menascé e Almeida (2002) uma estratégia de previsão de carga normalmente combina as técnicas qualitativas com as quantitativas.

- Quantitativa: Analisa os dados históricos para estimativa dos valores futuros para parâmetros de carga de trabalho.
- Qualitativa: Se baseado em intuição, opiniões especializadas, critérios, dados comerciais e outras informações relevantes.

**Atividades de previsão de carga**

- Objetivos da Previsão;
- Previsão Qualitativa;
- Dados Históricos;
- Processo de Previsão;
- Validação da Previsão.

**Definir a finalidade da previsão e as decisões a serem tomadas.**

- Como a previsão deve ser utilizada?
- Qual é o risco das decisões?
- Qual o tempo destinada para realizar esta previsão?

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/6/363604/29064.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/6/363604/29064.png)