[![](https://ampli-images.s3.amazonaws.com/production/0881c0d5-1e37-45ff-8a0b-3dcd74dda0a9/original)](https://ampli-images.s3.amazonaws.com/production/0881c0d5-1e37-45ff-8a0b-3dcd74dda0a9/original)

O modelo TCP/IP foi uma evolução dos primeiros protocolos desenvolvidos para a ARPANet e reúne um conjunto de protocolos padronizados para a utilização de sistemas de rede juntamente à internet. Assim, o modelo TCP/IP foi incorporado nas organizações para padronização dos sistemas de rede. Nesse modelo, existe a classificação dos protocolos em quatro camadas: aplicação, transporte, inter-rede e _host_ de Rede ou camada física. A figura a seguir apresenta um esquema dos protocolos TCP/IP e as atribuições em camadas a exemplo do modelo OSI.

______

**⚠️****Atenção**

De acordo com Kurose e Ross (2013), o TCP/IP foi uma evolução dos primeiros protocolos desenvolvidos para a ARPANet e abrange diversos outros protocolos. Tanenbaum direciona o TCP/IP como um modelo, de fato; já Kurose e Ross (2013) fazem referência ao TCP/IP como arquitetura em camadas e Forouzan (2010) como conjunto de protocolos.

A arquitetura TCP/IP representa uma arquitetura de um conjunto de protocolos de rede que não se limita apenas aos protocolos de transporte TCP e de rede IP. Outros protocolos fazem parte desse conjunto de protocolos e compõem o conjunto de protocolos utilizados, na atualidade, nos sistemas de redes de computadores. O TCP é considerado o principal protocolo de camada de transporte por ser orientado à conexão e garantir a entrega dos pacotes; já o IP é considerado o principal protocolo de endereçamento e roteamento de camada de Rede e possui duas versões atuais, o IPv4 e o IPv6.

[![](https://ampli-images.s3.amazonaws.com/production/e6f24409-962c-4234-8914-c4e5b8319870/original)](https://ampli-images.s3.amazonaws.com/production/e6f24409-962c-4234-8914-c4e5b8319870/original)

Modelo TCP/IP. Fonte: elaborada pelo autor.

A arquitetura ou conjunto de protocolos TCP/IP é, na realidade, um nome dado a um conjunto de protocolos de rede organizados em uma estrutura dividida em quatro camadas. As suas quatro camadas e suas funcionalidades serão descritas a seguir:

- **Camada de aplicação**: ou _application layer_ é uma camada composta por protocolos de rede de nível de aplicação que são responsáveis pela operacionalização de sistemas e aplicações finais para o usuário. Nessa camada, são definidos como os programas vão se comunicar com as aplicações de rede e como se dará o gerenciamento da interface e o que o usuário vai utilizar para executar a aplicação. Normalmente, mas não exclusivamente, as aplicações são executadas em um _browser_ (navegador) de internet. Alguns dos principais protocolos de camada de aplicação são: HTTP, _Simple Mail Transfer Protocol_ (SMTP), _Domain Name System_ (DNS), _Simple Mail Transfer Protocol_ (SNMP) e _File Transfer Protocol_ (FTP).
- **Camada de transport**e: ou _Transport Layer_ é uma camada composta por protocolos de transporte de dados em rede que fornecem, à camada de aplicação, serviços de empacotamento e comunicação de duas formas, sendo uma delas via serviços orientados à conexão e a outra via serviços não orientados à conexão. Ela tem como função realizar e gerenciar conexões ponto a ponto para garantir a integridade dos dados por meio de sequenciamento de pacotes segmentados no envio e recebimento de mensagens. Seus dois principais protocolos são o TCP e o UDP.
- **Camada de inter-rede**: ou _Internet Layer_ ou, ainda, camada de Rede é responsável pela definição do endereçamento de um _host_ de rede por meio do endereço de rede e também de roteamento dos pacotes de dados pelos dispositivos de rede. O principal protocolo dessa camada é o IP, responsável pelos endereçamentos de _hosts_ na rede. Outros protocolos de camada de _Inter-rede_ são: _Internet Control Message Protocol_ (ICMP)_, Address Resolution Protocol_ (ARP) e _Reverse Address Resolution Protocol_ (RARP).

______

**📝****Exemplificando**

A arquitetura TCP/IP, como conjunto de protocolos de rede, apresenta, em sua camada de Inter-rede, protocolos que são utilizados na prática para a configuração de _hosts_ de rede. O Protocolo IP (_Internet Protocol_) deve ser atribuído de forma única em cada host de rede, ou seja, em cada dispositivo que venha a fazer parte de uma rede. Por exemplo, para que um _notebook_ seja ativo dentro da rede local de uma empresa, ele precisa receber um endereço IP válido, como 192.168.0.15 ou 172.16.0.18 ou, ainda, 10.0.0.125, em conformidade com a política de endereçamento da empresa. O mesmo ocorre para qualquer outro dispositivo de rede, como impressoras e _smartphones_, por exemplo. Se for um endereço para um host em rede pública, uma organização de atribuição de endereços na internet, como a IANA (_Internet Assigned Number Authority_) e seus representantes locais, deverá atribuir o endereço.

______

- **Camada host de rede**: ou _network access layer_, como no modelo OSI, é a camada em que se localizam os dispositivos físicos da rede e as funções de enlace para acesso aos dispositivos físicos da rede. Entre suas atribuições, estão o monitoramento de tráfego de rede e o endereçamento em nível físico de dispositivos de rede para se realizar a transmissão de dados. São exemplos de protocolos de camada de host de rede: IEEE 802.3, IEEE 802.11 e IEEE 802.16, em que IEEE representa uma instituição internacional que organiza, regulamenta e padroniza sistemas de comunicação de rede em nível de _hardware_.

Com o objetivo de organizar alguns dos principais protocolos de comunicação de rede de computadores com as camadas do modelo TCP/IP, a próxima figura ilustra exemplos de protocolos.

[![](https://ampli-images.s3.amazonaws.com/production/cb9344a2-00bd-44b3-84dd-8ee14068226c/original)](https://ampli-images.s3.amazonaws.com/production/cb9344a2-00bd-44b3-84dd-8ee14068226c/original)

Exemplos de protocolos das camadas do modelo TCP/IP. Fonte: elaborada pelo autor.