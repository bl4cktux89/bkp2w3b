O modelo de arquitetura de um Sistema Distribuído consiste na distribuição ou repartição dos componentes, que acontecem através de uma rede de computadores, e do relacionamento entre esses componentes: o Software e o Hardware.

Um componente é uma unidade modular com interfaces requeridas, que são fornecidas bem definidas e que são substituíveis dentro do seu ambiente.

Nos Sistemas Distribuídos esses componentes estão espalhados por várias máquinas e tratam de complexas peças de Software que para serem controladas se faz necessário serem organizadas adequadamente.

A organização lógica dos Sistemas Distribuídos trata dos componentes de Software que constituem o sistema.

Essas arquiteturas determinam como os vários componentes de Software devem ser organizados e como devem interagir.

Usando componentes e conectores, chegasse a avarias configurações classificadas em estilos arquitetônicos, sendo os mais importantes para os Sistemas Distribuídos, os que seguem:

- Arquiteturas em Camadas;
- Arquiteturas baseadas em Objetos;
- Arquiteturas centradas em dados;
- Arquiteturas baseadas em eventos.

**ARQUITETURA EM CAMADAS**

O estilo dessa arquitetura é simples, uma vez que organiza seus componentes **em camadas**, sendo que uma determinada camada tem permissão de chamar componentes na camada subjacente, mas não ocorre o contrário.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293074/18561.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293074/18561.png)

Arquitetura em Camadas - Sistema Distribuído.

Fonte: Figura 2.1 (a) - pag.21 - Livro Sistemas Distribuídos - Princípios e Paradigmas.

Em geral, o controle flui de camada em camada, onde as requisições descem pela hierarquia ao passo que os resultados fluem para cima.

É um modelo muito utilizado por profissionais de redes.

**ARQUITETURA BASEADA EM OBJETOS**

Uma organização mais solta acontece nesta Arquitetura onde cada objeto corresponde a um componente que é conectado através de uma chamada de procedimento remota.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293146/18562.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293146/18562.png)

Arquitetura Baseada em Objetos - Sistema Distribuído

Fonte: Figura 2.1 (b) - pag.21 - Livro Sistemas Distribuídos - Princípios e Paradigmas.

A arquitetura baseada em objetos se ajusta em arquiteturas do tipo cliente-servidor, e em conjunto com a arquitetura em camadas fazem os estilos mais importantes para sistemas de grande porte.

**ARQUITETURA CENTRADA EM DADOS**

Nesta Arquitetura, os processos se comunicam por meio de um repositório comum (passivo ou ativo), sendo que para os Sistemas Distribuídos esse tipo de arquitetura é tão importante quanto às duas anteriores.

Foi desenvolvida uma grande quantidade de aplicações em rede que dependem de um sistema distribuído de arquivos compartilhados no qual toda a comunicação ocorre por meio de arquivos.

Um exemplo dessa arquitetura são os Sistemas Distribuídos baseados na Web, onde os processos se comunicam por meio da utilização de serviços centrados em dados.

**ARQUITETURA BASEADA EM EVENTOS**

Na arquitetura baseada em eventos processos se comunicam por meio da propagação de eventos que, também transportam dados.

A ideia básica é que processos publiquem eventos após os quais o Middleware assegura que somente os processos que se subscreveram para esses eventos os receberão.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293155/18563.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293155/18563.png)

Arquitetura Baseada em Eventos - Sistema Distribuído

Fonte: Figura 2.2 (a) - pag.21 - Livro Sistemas Distribuídos - Princípios e Paradigmas.

A principal vantagem de sistemas baseados em eventos é que os processos são fracamente acoplados, e sendo assim, eles não precisam se referir explicitamente uns aos outros. São também conhecidos como desacoplados.

Se combinarmos as arquiteturas Centradas em Dados com a Baseada em Eventos, teremos a Arquitetura de **Espaços Compartilhados de Dados**, onde os processos estão desacoplados no tempo e não precisam estar ambos ativos quando ocorrer a comunicação.

As Arquiteturas de Software são importantes para os Sistemas Distribuídos, uma vez que, todas elas visam obter transparência de distribuição em um nível razoável, o que requer compromisso entre desempenho, tolerância a falhas, facilidade de programação, entre outros.

**MODELOS FUNDAMENTAIS**

Os Sistemas Distribuídos tem por objetivo proporcionar uma computação de alto desempenho e são divididos em **Computação em Cluster** e **Computação em Grade.**

**COMPUTAÇÃO EM CLUSTER**

Neste modelo, o hardware consiste em um conjunto de estações de trabalho semelhantes, conectados por meio de uma rede local de alta velocidade, onde cada nó executa o mesmo Sistema Operacional.

A computação em Cluster é usualmente utilizada para programação paralela quando um único programa, intensivo em computação, é executado em paralelo em várias máquinas. Um exemplo típico desta aplicação é a renderização de imagens em filmes de animação.

Outro modelo de Computação em Cluster é formado pelos “Clusters Beowulf”, baseados em Linux, onde cada cluster consiste em um conjunto de nós, formados por computadores comuns, controlados e acessados por um único nó, denominado “mestre”. As tarefas do mestre é manipular a alocação de nós a um programa específico, manter uma fila de tarefas e proporcionar a interface com os usuários do sistema.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293053/18564.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293053/18564.jpg)

Exemplo de um Sistema de Computação em Cluster.

Fonte: Figura 1.4 - pag.10 - Livro Sistemas Distribuídos - Princípios e Paradigmas.

A origem do Beowulf está associada ao trabalho realizado por Donald Becker e Thomas Sterling, em 1993, que projetavam um sistema de cluster com intenção de obter uma alternativa de custo/benefício aos supercomputadores.

O sucesso do Beowulf foi imediato e sua ideia de usar computadores comuns ociosos, se espalhou rapidamente pela NASA (que deu suporte ao projeto), pelo mundo acadêmico e por comunidades de pesquisa. Em sua configuração usual, um cluster beowulf possui uma configuração onde um nó assume o papel de mestre e executa o gerenciamento do cluster.

**COMPUTAÇÃO EM GRADE**

Um sistema de computação em grade é uma rede de grupos de computadores geograficamente dispersos organizados para realizarem uma tarefa em conjunto. Nenhuma premissa é adotada em relação aos componentes do sistema (hardware, sistema operacional, rede, etc...) fazendo a computação em grade envolver alto grau de heterogeneidade e descentralização.

Enquanto os clusters são conjuntos de computadores unidos como um único sistema, a computação em grade consiste de múltiplos sistemas que trabalham juntos, mas mantém sua identidade distinta.

Uma questão fundamental nesse tipo de sistema é que recursos de diferentes organizações são reunidos para permitir a colaboração de um grupo de pessoas ou instituições, sendo realizada sob a forma de uma organização virtual.

Um software para realizar uma computação em grade deve prover acesso a recursos de diferentes domínios administrativos, atendendo a usuários e aplicações que pertençam a uma organização virtual específica.

Foster et al. (2001) propôs uma arquitetura baseada em quatro camadas, projetada para permitir compartilhamento de recursos dentro da organização virtual.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293054/18565.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293054/18565.jpg)

Arquitetura em Camadas para Sistema de Computação em Grade.

Fonte: Figura 1.5 - pag. 11 - do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Na camada mais baixa denominada de _**camada base**_, é fornecido acesso às interfaces para recursos locais em um determinado site, bem como funções para consultar o estado e as capacidades de um recurso, em conjunto com funções de gerenciamento desses recursos.

A _**camada de conectividade**_ oferece protocolos de comunicação que suportam transações da grade envolvendo a utilização de diversos recursos. Os protocolos são necessários para o acesso ou transferência de dados entre os recursos. Nessa camada teremos ainda, os protocolos de segurança para autenticar usuários e recursos.

A _**camada de recursos**_ é responsável pelo gerenciamento de um único recurso. Utiliza as funções da camada de conectividade e chama as interfaxes disponibilizadas pela camada base.

A próxima é a _**camada coletiva**_ responsável por manipular o acesso a múltiplos recursos, alocação e escalonamento de tarefas para múltiplos recursos e a replicação de dados.

A última é a _**camada de aplicação**_ que oferece aplicações que funcionam na organização virtual e fazem uso do ambiente de computação em grade.

Em conjunto, essas camadas dão acesso e gerenciam recursos que estão dispersos por diversos sites.

**ARQUITETURA PEER-TO-PEER (PROCESSOS PARES)**

Os processos que constituem um sistema Peer-to-Peer são todos iguais, o que significa que as funções que serão realizadas são representadas por todo processo que constitui o Sistema Distribuído.

Dessa forma, grande parte da interação entre processos é simétrica, ou seja, cada processo agirá como um cliente e um servidor ao mesmo tempo.

A simetria característica dos sistemas Peer-to-Peer se desenvolvem em torno da questão de como organizar os processos em uma rede de sobreposição, onde um processo não pode se comunicar diretamente com outro processo arbitrariamente, mas deve enviar mensagens por meio dos canais de comunicação disponíveis.

Em uma arquitetura Peer-to-Peer estruturada, a rede de sobreposição é construída com a utilização de um procedimento determinístico, que organiza os processos por meio de uma tabela chamada **DHT** (Distributed Hash Table – Tabela de Hash Distribuída).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293085/18566.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293085/18566.jpg)

Exemplo de uma Tabela DHT baseada em um sistema Chord

Fonte: Figura 5.4 - pag. 114 - Livro Sistemas Distribuídos - Princípios e Paradigmas.

**MODELO DE INTERAÇÃO: SISTEMAS DISTRIBUÍDOS SÍNCRONOS E ASSÍNCRONOS**

As arquiteturas dos Sistemas Distribuídos são compostas por muitos processos que interagem de maneira complexa. Vários servidores podem cooperar entre si para fornecer um serviço, como por exemplo, o DNS (Domain Name Service) que divide e replica seus dados em diferentes servidores na Internet, outros podem tratar de um conjunto de processos peer-to-peer para cooperar entre si e atingir um objetivo comum, como em um sistema de teleconferência.

Em um Sistema Distribuído, as atividades são realizadas por processos que interagem entre si, sendo que cada processo tem o seu próprio estado, que consiste no conjunto de dados que ele pode acessar e atualizar, sendo muito difícil estabelecer limites para o tempo que leva a execução dos processos, para a troca de mensagens.

Duas variantes do modelo de interação fornecem modelos simples, que são os Sistemas Distribuídos Síncronos e Assíncronos, onde o primeiro é baseado na ideia de tempo, e o segundo não.

**SISTEMA DISTRIBUÍDO SÍNCRONO**

HADZILACOS E TOUEG (1994) definem um **Sistema Distribuído Síncrono** como aquele no qual é definido o tempo para executar cada etapa de um processo, com limites inferior e superior conhecidos; onde cada mensagem transmitida em um canal é recebida em um tempo limite e, onde cada processo tem um relógio local cuja taxa de desvio do tempo real tem um valor máximo conhecido.

Assim, nos sistemas Síncronos é possível estimar possíveis limites superior e inferior para o tempo de execução de um processo, para o atraso das mensagens e para as taxas de desvio do relógio, entretanto, sem que se garanta que esses valores sejam extremamente reais.

Os Sistemas Distribuídos Síncronos podem ser construídos desde que se garanta que os processos sejam executados de forma a respeitar as restrições de tempo impostas, sendo que para isso se faz necessário alocar os recursos necessários, tais como: tempo de processamento e capacidade de rede, e limitar o desvio do relógio.

**SISTEMA DISTRIBUÍDO ASSÍNCRONO**

Um Sistema Distribuído Assíncrono é aquele em que não existem considerações sobre as velocidades de execução dos processos, nem sobre o atraso na transmissão das mensagens e, tão pouco preocupação com as taxas de desvio do relógio.

Um exemplo deste modelo é o caso da Internet, onde não há nenhum limite interno definido sobre a carga no servidor ou na rede, nem quanto tempo demora para ser transferido um arquivo usando, por exemplo, FTP (File Transfer Protocol).

Normalmente, os Sistemas Distribuídos são assíncronos devido à necessidade dos processos de compartilhar tempo de processamento, canais de comunicação e acesso à rede.

Assim, se vários processos com características desconhecidas compartilharem um processador, o desempenho resultante de cada um deles não poderá ser garantido.

**MODELO DE FALHAS**

Em um Sistema Distribuído, tanto os processos como os canais de comunicação podem falhar, pois não é possível conceber componentes sem falhas, apenas se pode diminuir a probabilidade de as mesmas ocorrerem.

O modelo de falha consiste na definição dos mecanismos no qual as falhas podem ocorrer, de modo a se compreender o efeito e consequências que elas podem causar. Abrange ainda a indicação rigorosa do comportamento global do sistema na presença dos diferentes tipos de falhas.

Nos Sistemas Distribuídos tanto os processos como os canais de comunicação podem falhar, pois não é possível conceber componentes sem falhas, apenas se pode diminuir a probabilidade de as mesmas ocorrerem.

**ALGUNS TIPOS DE FALHA**

**FAULT TOLERANCE - TOLERÂNCIA A FALHAS**

Propriedade de um sistema distribuído que lhe permite recuperar da existência de falhas sem introduzir comportamentos incorretos. Um sistema deste tipo pode mascarar as falhas e continuar a operar, ou parar e voltar a operar mais tarde, de forma coerente, após reparação da falha.

**AVAILABILITY – DISPONIBILIDADE.**

Mede a fração de tempo em que um serviço está a operar corretamente, isto é, de acordo com a sua especificação. Para um sistema ser altamente disponível (highly available) deve combinar um reduzido número de falhas com um curto período de recuperação das falhas, durante o qual não está disponível.

**RELIABILITY – CONFIABILIDADE.**

Mede o tempo desde um instante inicial até à primeira falha, ou seja, o tempo que um sistema funciona corretamente sem falhas. Um sistema que falha com grande frequência e se recupera rapidamente tem baixa fiabilidade, mas alta disponibilidade.

FALHAS POR OMISSÃO E ARBITRÁRIAS

**Alguns processos podem detectar esse tipo de falha pelo fato de um processo deixar de responder às mensagens de invocação, faz isso utilizando um tempo limite chamado de “timeout”, que é o tempo para que uma determinada ação ocorra.**

**As falhas podem ser classificadas de acordo com sua gravidade, sendo que nos sistemas distribuídos a maioria delas é tida como benignas e incluem as falas por omissão, por sincronização e as falhas de desempenho.**

**A falha arbitrária, conhecida também como “bizantina”, descreve a pior situação de falha possível onde qualquer tipo de erro pode ocorrer.**

**Nesse tipo de falha o processo omite os passos do processamento ou realiza um processamento indesejado.**

**Outro ponto desse tipo de falha pode ocorrer nos canais de comunicação, onde o conteúdo de uma mensagem pode estar corrompido, ou mensagens inexistentes podem ser enviadas, ou ainda, algumas mensagens podem ser entregues mais de uma vez.**

**Nos canais de comunicação esse tipo de falha é facilmente detectado, pois se uma mensagem estiver corrompida o software de comunicação é capaz de reconhecer e rejeitar a mensagem com problema.**

**MODELO DE SEGURANÇA**

**O compartilhamento dos recursos é um dos fatores motivadores para os Sistemas Distribuídos e foi descrita posteriormente a arquitetura dos seus sistemas em termos de processos encapsulando objetos e fornecendo acessos a eles através de interações com outros processos.**

**Esse modelo de arquitetura providencia as bases para o modelo de segurança:**

**“A segurança de um Sistema Distribuído pode ser obtida to****r****nando seguro os processos e os canais usados por suas interações e protegendo contra acesso não autorizado os objetos que encapsulam”.**

**COULOURIS (2008)**

()

**A proteção é descrita em temos de objetos, embora os conceitos se apliquem igualmente a recursos de todos os tipos.**

**Essa proteção dá-se por meio do gerenciamento de um conjunto de objetos para alguns usuários. Estes usuários podem executar programas clientes que enviam invocações (requisições) ao servidor para realizar operações nos objetos. O servidor executa a operação especificada em cada invocação e envia a resposta ao cliente.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293094/18572.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293094/18572.jpg)

Exemplo de um cliente realizando uma invocação.

Fonte: Figura 2.12 - pag. 63 - Livro Sistemas Distribuídos - Conceitos e Projetos. Coulouris - 2008

**Os objetos podem ser usados de diferentes formas, por diferentes usuários. Sendo que, alguns objetos podem conter dados privados do utilizador, como password e, outros objetos podem conter dados compartilhados como as páginas da Web.**

**Para suportar isto, os privilégios de acesso especificam a quem é permitido realizar operações num objeto, como por exemplo, ler, gravar e alterar o estado do objeto.**

**Por esse motivo, é que se incluem os usuários neste modelo como os beneficiários dos privilégios de acesso. Isso é feito associando cada requisição e cada resultado à respectiva autoridade, sendo esta chamada de “principal”, que pode ser um usuário ou um processo.**

**Assim, o servidor fica responsável por verificar a identidade de um principal, em cada requisição e verificar se ele detém privilégios suficientes para realizar a operação pretendida num determinado objeto, recusando se não os tiver.**

**Os processos interagem pelo envio de mensagens. As mensagens são expostas a ataque porque o acesso à rede e ao serviço de comunicação é livre, o que permite que os dois processos interajam.**