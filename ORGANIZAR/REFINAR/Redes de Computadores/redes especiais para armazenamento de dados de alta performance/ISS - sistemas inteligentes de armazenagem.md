### Introdução

A armazenagem de dados é uma das principais preocupações de gestores e do custodiante da informação, assim como dos cientistas de dados que organizam, classificam e utilizam os dados na gestão estratégica das organizações.

O sistemas de armazenamento inteligente é um recurso de processamento de I/O (Input e output) entrada e saida, capazes de suportar a combinação de HD (Hard Disks) e SSD.

Precisamos entender bem o funcionamento dos dispositivos de armazenamento, suas vantagens e desvantagens, a fim de fazer a melhor escolha ou a melhor combinação dessas tecnologias. Por exemplo, um SSD é mais rápido que um HD, entretanto mais caro. Mas quais aspectos técnicos influenciam nisso? O objetivo desse tópico é apresentar os sistemas de armazenagem inteligente que possuem dois componentes principais: controladora e armazenamento, que auxiliam na gestão eficiente dos dados.

Os sistemas inteligentes de armazenamento funcionam de maneira automática por meio de políticas pré-estabelecidas, essas políticas servem para automatizar o gerenciamento de dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258599/11947.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258599/11947.jpg)

Referência a Armazenamento.

### Mecanismo de funcionamento do HDD - (Hard Drive Disk)

Um HD, ou HDD (_**Hard Drive Disk**_) funciona com pratos (_**Platters**_), que são discos revestidos de material magnético que armazenam os dados. Os dados são recuperados e gravados conforme o prato gira, e a cabeça de leitura e gravação passa por cima da região do prato em que os dados se encontram, esses dados são enviados para a placa controladora, a placa controladora é um circuito, com um processador integrado que controla todas operações de E/S ou I/O. Todo esse movimento é feito por um braço atuador ( que controla a cabeça de leitura/gravação), e um _**spindle**_ (eixo que prende os pratos e é ligado ao motor).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/9/315990/20813.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/5/9/315990/20813.png)

Organização das Trilhas e Setores no HD com as cabeças de Leitura/Gravação.

Os dados são organizados em trilhas, que são anéis ao redor do _**spindle**_, e cada uma recebe um número identificador começando do 0, de acordo com a Dell Corporation (2015) a quantia de trilhas é medida por TPI(_**Trails per inch**_ ou trilhas por polegada). As trilhas são divididas em pedaços menores, chamados de setores, os setores geralmente tem 512 bytes. Dessa forma a controladora já consegue achar em qual parte do disco está, mas também é preciso saber em qual cilindro está, o que aumenta o tempo de procura. Todo esse mapeamento lógico é feito pela controladora, que basicamente associa os endereços lógicos(LBA) e os converte em endereços físicos (_**cilindro, cabeça e setor ou CHS**_).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/1/5/311563/20812.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/1/5/311563/20812.png)

Organização das Trilhas e Setores no HD.

Sobre o desempenho do HD, devemos levar em consideração alguns fatores de fábrica e suas limitações. Vamos começar com os fatores de fábrica:

Temos 3 especificações que nos ajudam ter uma ideia do desempenho do dispositivo, que são : Tempo de busca,Latência rotacional, Taxa de transferência de dados;

Agora vamos detalhar cada especificação:

- Tempo de busca = É o tempo que o HD demora para mover suas cabeças de leitura e gravação. Cada fabricante especifica de uma maneira diferente, porém as mais comuns são: Full stroke (da primeira à última trilha), Média (de uma trilha aleatória para outra), Trilha para trilha (de uma trilha para a próxima). Essa informação é medida em ms (Milissegundos).
- Latência rotacional = Para calcular a LR usamos a seguinte fórmula: 30000/rpm (Rotações por minuto). Temos diversas velocidades de RPM disponíveis no mercado, se fizermos o cálculo com o RPM de 15000, a LR será de 2ms.
- Taxa de transferência de dados = Pode ser de entrada ou saída, de saída(externo) seria o tempo que o drive pode entregar os dados ao barramento, e de entrada (interno), é a velocidade de leitura do disco para o buffer interno do drive.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/0/8/850876/36711.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/0/8/850876/36711.jpg)

Hardware

Se somarmos, o tempo de busca, a latência rotacional, e a taxa de transferência de dados, vamos obter o tempo de atividade (serviço) no disco. o prato é um círculo, que por sua vez possui um Raio, quanto mais perto do centro (o spindle), menor será o raio, e logo menor o tempo de leitura e gravação. Porém quanto mais longe do centro, maior o raio, e maior o tempo, pois a cabeça demora mais tempo para dar uma volta maior, em decorrência de seu diâmetro. Por isso, é comum uma técnica que se chama subutilização do HD, que consiste em usar por exemplo, apenas 60% da capacidade total, de forma que o tempo de resposta seja menor, de acordo com a Dell Corporation (2015).

Sobre as limitações, temos que entender que o HD vai ter um limite de velocidade de rotação, e mesmo essa rotação sendo alta, o tempo de deslocamento de um prato para outro, ou até de um setor para outro demanda  tempo. O que de certa forma nos limita em termos de velocidade.

### Cluster de Discos

Um Cluster de disco é formado por um conjunto de discos, que tem a função de armazenar dados e criar uma entidade lógica unica.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/3/267333/15035.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/3/267333/15035.jpg)

Cluster de Discos

### SSD - Solid State Drive

Os SSD (Solid State Drive) são dispositivos de armazenamento bem mais rápidos que o HD, pois diferente deles, ele não usa braços, motor, e cabeça de leitura e gravação. No SSD os dados são armazenados em memória flash não volátil, que é uma memória muito eficiente. Sem contar a velocidade significativamente mais alta, eles também gastam menos energia.

Os principais componentes de um SSD são: o armazenamento em massa (_**chips**_ de memória _**flash**_), controladora, e interface de ENTRADA/SAÍDA. Alguns SSDs já oferecem recursos como criptografia inclusos por padrão.

Os SSDs não tem trilhas e setores, eles funcionam dividindo os dados em pequenas partes chamadas de páginas, e eles depois são agrupados em blocos, um bloco geralmente tem 32 KB. Essas informações são mapeadas e armazenadas nos chips de memória flash, para poder recuperar rapidamente esses dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/7/4/7/2774764/42097.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/7/4/7/2774764/42097.png)

### Arquitetura de Dimensionamento

Temos duas arquiteturas de dimensionamento possíveis, elas que vão ditar como esse armazenamento deve se expandir, temos o dimensionamento vertical, onde usamos uma controladora para vários armazenamentos, enquanto na scale-out usamos uma controladora para cada armazenamento, ou conjunto deles. Imagine a abordagem vertical como um prédio, onde depois de ter uma base sólida, é só construir os andares, e a scale-out como uma rua, onde para construir cada casa, é preciso uma base diferente.

A arquitetura de dimensionamento vertical nos permite criar algo mais escalável, uma vez que não é preciso adicionar uma controladora cada vez que quiser aumentar seu storage.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267922/11817.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267922/11817.png)

Desempenho de Disco

O armazenamento baseado em software nos traz vários benefícios, como pode-se imaginar, sai muito caro usar soluções específicas de hardware, e o maior problema disso é que cria-se os famosos silos de Tecnologia da Infomação. Um silo é aquele compartimento fechado para armazenar grãos e outras coisas assim. Quando dizemos um silo de TI, significa criar uma infraestrutura não escalável, e muitas vezes usando hardware e software proprietário, o que acaba sendo uma limitação, já que ficamos presos à um fabricante ou modelo. o armazenamento baseado em software soluciona esse problema para nós, com um controle feito por software, podemos usar hardwares normais, e não tão caros, e apenas aplicar o SDS por cima do hardware.

A Infraestrutura baseada em software cria um pool de recursos diferentes, e os aloca conforme tiver necessidade. Facilita o gerenciamento de maneira global automatizada por políticas, e dá suporte a outros vários tipos de armazenamento(block, file, object).

Seu principal componente é o control plane, suas principais funções são descritas a seguir, sua interface pode ser CLI(interface de linha de comandos) ou GUI(interface gráfica do usuário), o termo tenants significa inquilinos em inglês, que seriam como se fossem containers para um sistema virtual em um ambiente físico, e o control plane é o software que gerencia essas instâncias virtualizadas.

- Detecção de ativos: Faz a detecção de recursos de rede, armazenamento, clusters, SANs, soluções de segurança e proteção a dados por meio da controladora.
- Abstração e pooling de recursos: Cria uma camada de abstração entre nós e os recursos de maneira mais simples, “escondendo” os volumes físicos por meio de mascaramento de LUN, e mostrando apenas a capacidade total como um volume unificado, ao invés de mostrar vários volumes físicos, e ter que os gerenciar separadamente. Dessa forma ele gerencia os volumes físicos, cuidando de todos os detalhes quando fazemos alguma mudança no pool virtual. Os principais tipo de pools para armazenamento são o block, file, e object. A parte da abstração também é responsável pelos multi-tenants(Ou múltiplos inquilinos), que como comentado anteriormente, é a técnica de rodar mais de um aplicativo no mesmo ambiente separados em containers virtuais distintos.
- Prover serviços e recursos: Para expor os tenants, depois da configuração inicial, cria-se um catálogo de serviços. Os serviços podem ser block, file ou object. Esse catálogo serve para criar um autoatendimento sob demanda, para os usuários fazerem solicitações é usado um programa de cliente. Essas solicitações podem ser monitoradas em tempo real pelo administrador do sistema.

### Provisionamento

Provisionamento vem da palavra prover, onde indica a capacidade de implementar, modificar ou acessar serviços de telecomunicações.

A seguir vamos citar os principais serviços dos tipos de provisionamento:

- Block: Principais serviços envolvendo volumes block são: criar e excluir, vincular e desvincular, montar e desmontar, e expandir um volume existente.
- File: Permite compartilhamento de arquivos NFS, SMB, CIFS, seus principais serviços de compartilhamento envolvem criar, excluir e expandir.
- Object: O container que armazena os objetos se chamam buckets(baldes), esses buckets podem receber um namespace único para os separar, e dessa forma evitar que um acesse informações do outro. Suas principais funções sobre os buckets de objetos são: criar, editar, excluir, incluir compartilhamento a um bucket existente.
- Proteção de dados: A controladora deve oferecer proteção aos dados caso aconteça algo inesperado. Para isso cada tipo de implementação como visto anteriormente têm suas funções, no block, temos snapshots(uma imagem, no sentido de “tirar uma foto e conservar”), proteção de failover(tolerância a falhas), proteção contínua. Enquanto no file temos apenas snapshot e o file system, e no object já temos a replicação sem necessidade de RAID e codificação de eliminação.

### API - Application Programming Interface

API ou Application Programming Interface que significa "Interface de Programação de Aplicativos", é um software com um conjunto de rotinas, geralmente por alguma empresa para facilitar algumas tarefas, criando uma camada de abstração entre o núcleo do sistema e o que o usuário têm acesso, e podem seguir duas arquiteturas principais, SOAP ou REST(RESTful). As APIs permitem acessibilidade aos aplicativos por meio da rede. SOAP é uma abordagem nova para objetos descentralizados, de forma assíncrona, uma linguagem de programação que têm sido muito usada para desenvolvimento de APIs é o node.js. E o REST trabalha com url e a sua codificação para enviar e receber parâmetros por meio de métodos do protocolo http, os principais são POST, GET, PUT, PATCH e DELETE.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/7/4/7/2774720/42098.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/7/4/7/2774720/42098.jpg)

### Resumo

Para se entender o funcionamento de sistemas inteligentes de armazenamento é preciso entender todos seus componentes, não só físico(hardware), mas também os componentes de sistemas(software), e como tudo se junta. A virtualização exerce um papel importantíssimo quando se trata de sistemas de armazenagem inteligentes, pois soluções baseadas em software oferecem um controle mais fácil, de maneira centralizada.

Sempre que for montar uma rede de armazenamento é importante pensar em como a infraestrutura como um todo vai ficar, dessa maneira pode-se planejar cuidadosamente quais hardwares e softwares se usar, e como seu sistema vai funcionar. Claro que isso depende de vários fatores, espaço físico, dispositivos de hardware, entre outros.

Como foi visto neste capítulo, os sistemas inteligentes são combinações feitas entre hardware e software para evitar perda de dados. Neste capítulo também foi visto os tipos de provisionamento, por file, block, e object, e como as API’s funcionam de maneira a fornecer acesso rápido aos dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/8/1/0/7/2810750/-comp-final.gif)](https://img.uninove.br/static/0/0/0/0/0/0/2/8/1/0/7/2810750/-comp-final.gif)

Fonte: https://animagraffs.com/hard-disk-drive/