Em Sistemas Distribuídos, os nomes são uma cadeia de bits ou caracteres usados para referenciar uma entidade, para compartilhar recursos, fazer referência a localizações, entre outras funções.

Podemos citar como exemplo de entidades que costumam ser nomeadas: impressoras, arquivos, processos, usuários, caixas postais, mensagens, conexões de rede, páginas da Web . . .

Se considerarmos uma conexão de rede, veremos que ela pode fornecer operações para enviar e receber dados, ajustar parâmetros, requisitar estado, entre outras funções, por isso chamamos as entidades de ativas.

Para agir sobre uma entidade é necessário acessá-la, e para isso necessitamos de um ponto de acesso, que é outro tipo de entidade. Esse ponto de acesso é chamado de **endereço**, que nada mais é do que um tipo especial de nome.

Além dos endereços, outro tipo de nome merece atenção, como aqueles que servem para identificar uma entidade, ou seja, **os identificadores**.

Usando identificadores fica mais fácil referenciar uma entidade sem nenhuma ambiguidade, pois se dois processos referenciarem uma entidade por meio de um identificador, basta testar os dois identificadores, para saber se os processos estão tratando da mesma entidade.

Endereços e identificadores são dois tipos de nomes importantes, e cada um deles é usado para fins diferentes. Em sistemas de computação, endereços e identificadores são representados por cadeias de bits, que só podem ser lidos por máquinas.

A implementação de um sistema de nomeação costuma ser distribuída por várias máquinas e o modo como é realizada desempenha um papel fundamental na eficiência e escalabilidade do sistema de nomeação.

**NOMEAÇÃO SIMPLES**

Os nomes simples nos Sistemas Distribuídos são caracterizados por serem os nomes dados às entidades que não contém uma informação sobre o ponto de acesso da sua entidade associada, trás com ele apenas um identificador.

Como vimos, identificadores são convenientes para identificar entidades com exclusividade, sendo que estes são cadeias aleatórias de bits, que são nomes não estruturados ou nomes simples.

Uma propriedade importante que devemos ressaltar, é que um nome não contém nenhuma informação de como localizar o ponto de acesso de uma entidade associada.

Podemos utilizar duas soluções simples para realizar essa identificação, que são aplicáveis apenas em redes locais: **o Broadcasting e o Multicasting.**

**Broadcasting**

Vamos considerar um Sistema Distribuído que foi construído em uma rede de computadores que ofereça recursos de Broadcasting, onde todas as máquinas estejam conectadas a um único cabo. Localizar uma entidade nesse ambiente é mais fácil, pois uma mensagem que contenha o identificador da entidade é enviada por broadcast a cada uma das máquinas dessa rede, sendo que cada máquina verifica se tem a entidade relacionada. Somente as máquinas que oferecem um ponto de acesso à entidade, enviam uma mensagem de resposta com o endereço daquele ponto de acesso.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/1/297124/SEQUENCIA-Broadcasting--PSD.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/1/297124/SEQUENCIA-Broadcasting--PSD.gif)

Ilustração de um Broadcasting

Fonte:

Isso é tratado no protocolo ARP que é o Protocolo de Resolução de Endereços da Internet, que utiliza o endereço de enlace de uma máquina quando só existe um endereço IP.

Broadcasting se torna ineficiente quando a rede cresce, porque existe um desperdício da banda de rede por mensagem enviada e também, um grande número de hospedeiros pode ser interrompido caso as requisições não sejam respondidas.

**Multicasting**

Uma solução para esse problema é fazer uso de multicasting, onde somente um grupo restrito de hospedeiro recebe a requisição. Nas redes Ethernet, o multicasting é suportado em nível de enlace diretamente no hardware.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297086/Gif.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297086/Gif.gif)

Envio de mensagens por Multicasting.

As redes ponto-a-ponto suportam multicast para localizar entidades. Veja a Internet, que utiliza multicasting de nível de rede permitindo que hospedeiros se juntem a grupos multicast específicos, onde a rede fornece um serviço para entregar a mensagem a todos os membros do grupo.

**Ponteiros repassadores**

Outra abordagem para localização de entidades móveis é utilizar ponteiros repassadores. A questão é simples: quando uma entidade se move de **A** para **B** deixa para trás em **A**, uma referência a sua localização em **B**. A principal vantagem dessa abordagem é a simplicidade, pois tão logo uma entidade seja localizada, usando um serviço de nomeação, um cliente pode consultar o endereço corrente da entidade percorrendo uma cadeia de ponteiros repassadores.

Vamos considerar a utilização dos ponteiros repassadores em relação a objetos que podem ser acessados por meio de uma chamada de procedimento remoto.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314828/19613.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314828/19613.png)

Princípio de ponteiros repassadores que se utilizam de pares.

Fonte: Figura 5.1 - Pag. 111 - do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Seguindo a abordagem em cadeias, cada ponteiro repassador é implementado através de pares.  Assim, sempre que um objeto se move de **A** para **B**, deixa para trás um apêndice de servidor que referencia aquele apêndice em **B**, fazendo com que uma requisição de cliente seja repassada ao longo da cadeia até o objeto propriamente dito.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314829/19614.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314829/19614.png)

Redirecionamento de ponteiro repassador utilizando atalho.

Fonte: Figura 5.2 - Pag. 111 - do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Para tomar um atalho em uma cadeia de pares uma invocação de objeto transporta a identificação (endereço) do apêndice de cliente onde foi iniciada. Essa localização caminha junto com a resposta e o apêndice do cliente ajusta seu apêndice de servidor para a localização corrente do objeto.

**NOMEAÇÃO ESTRUTURADA**

A estrutura de nomeação simples é interessante para as máquinas, mas inconvenientes para a utilização dos humanos.

A nomeação estruturada é utilizada para definir nomes compreensíveis por humanos, que são utilizados em arquivos, nome de máquinas e em nomes de sites, na Internet.

Esses nomes estruturados são armazenados dando nomes às entidades e são chamados de **espaço de nomes** (names space). Podem ser representados por dois tipos de nós: **nó-folha** e o **nó de diretório.**

O **nó-folha** representa uma entidade e tem a propriedade de não ter ramos de saída e armazenam informações sobre a entidade que está representando, sendo assim acessível por um cliente.

Já o **nó de diretório** tem vários ramos de saída, sendo cada um rotulado com um nome e cada nó é considerado como outra entidade de um Sistema Distribuído e tem um identificador associado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314835/19616.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314835/19616.PNG)

Gráfico de nomeação com um único nó-raiz.

Fonte: Figura 5.9 - Pag. 111 - do Livro Sistemas Distribuídos - Princípios e Paradigmas

Um nó de diretório armazena uma tabela na qual um ramo de saída é representado por um par. No gráfico acima temos apenas ramos de saída e nenhum de entrada, ou seja, existe apenas um nó (nó-raiz), e embora seja possível ter vários nós, muitos sistema de nomeação trabalham com somente um.

É importante saber que nomes são sempre organizados em um espaço de nomes e são sempre definidos em relação a apenas um nó de diretório.

**ESPAÇOS DE NOMES**

Os espaços de nomes em um Sistema Distribuído é o conjunto de todos os nomes válidos reconhecidos por um serviço. Costuma ser organizado de forma hierárquica e para implementa-lo é conveniente reparti-lo em três camadas: a global, a administrativa e a gerencial.

**CAMADA GLOBAL**

Formada por nós de nível mais alto, contendo o nó-raiz e outros nós de diretórios próximos ao raiz. Os nós nessa camada costumam ser caracterizados por sua estabilidade, uma vez que suas tabelas de diretório raramente mudam. Podemos representar nesses nós os grupos de organizações, cujos nomes estão armazenados no espaço de nomes, tais como: .com; .edu; .org; .net, entre outros.

**CAMADA ADMINISTRATIVA**

Nesta camada, encontraremos os nós de diretórios que são gerenciados por uma única organização, ou seja, representam grupos de entidades que pertencem à mesma organização e que são controlados por elas, mas que podem ocorrer mudanças com o decorrer do tempo. Por exemplo: .org que tem na sua camada administrativa o IEEE, acm ...(considerando o exemplo do gráfico abaixo) e que podem ter alteradas ou incluídas novas entidades.

**CAMADA GERENCIAL**

Na camada gerencial temos os nós que sofrem mudança periódica, são nós que representam arquivos compartilhados, diretórios e/ou arquivos definidos pelos usuários.

Os elementos dessa camada são mantidos e gerenciados por administradores de sistemas e também por usuários que se utilizam de um Sistema Distribuído.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314830/19618.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/8/314830/19618.png)

Exemplo de espaço de nomes usados no DNS, incluindo as três camadas.

Fonte: Figura 5.13 - Pag. 123 - do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Vemos na figura acima, um exemplo da repartição de parte do espaço de nomes do DNS, incluindo os nomes de arquivos que estão dentro de uma organização e que podem ser acessados pela Internet.

Vale lembrar que, o DNS (Domain Name System – Sistema de Nomes de Domínio) é, hoje em dia, um dos maiores serviços distribuídos de nomeação, que trabalha com a Internet, sendo usado para consultar nomes de sites convertendo-o em endereços IP (Internet Protocol).