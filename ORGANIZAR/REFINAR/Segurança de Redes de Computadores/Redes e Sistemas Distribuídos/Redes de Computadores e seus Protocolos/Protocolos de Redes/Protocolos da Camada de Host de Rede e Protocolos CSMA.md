[![](https://ampli-images.s3.amazonaws.com/production/e685b9a9-ea81-49d2-bfb0-157232c0f90c/original)](https://ampli-images.s3.amazonaws.com/production/e685b9a9-ea81-49d2-bfb0-157232c0f90c/original)

A camada host de rede ou _network access layer_, como no modelo OSI, é a camada em que se localizam os dispositivos físicos da rede com as funções de enlace para acesso aos dispositivos físicos da rede. Entre suas atribuições, estão o monitoramento de tráfego de rede, a detecção e a correção de erros e o endereçamento, em nível físico, de dispositivos de rede para a transmissão de dados.

Aqui, destacam-se os protocolos de acesso múltiplo ao meio _Carrier Sense Multiple Access_ (CSMA) implementados com especificações de detecção de colisão ou de colisão evitada nos padrões, também chamados de protocolos dos dispositivos físicos de rede, sendo os mais utilizados: IEEE 802.3, IEEE 802.11 e IEEE 802.16, em que IEEE representa uma instituição internacional que organiza, regulamenta e padroniza sistemas de comunicação de rede em nível de _hardware_. A seguir, serão apresentados dois protocolos de acesso múltiplo ao meio.

_**CARRIER SENSE MULTIPLE ACCESS WITH COLLISION DETECTION**_ **(CSMA/CD)**

O protocolo CSMA utiliza um único meio de transmissão (cabo de rede, por exemplo) para suportar a transmissão de todos os hosts da rede. Seu funcionamento ocorre por meio de acesso múltiplo com detecção de onda portadora, chamada de CSMA/CD, independentemente da topologia da rede. A transmissão é feita quando o cabo está livre, e existe controle de colisão quando mais de um host transmite dados ao mesmo tempo, implementado por meio de um algoritmo com mecanismo de gestão de colisão e transmissão.

Conforme Forouzan (2010), nesse método, a estação monitora continuamente o meio de transmissão após transmitir um frame para: verificar se a transmissão foi bem sucedida, finalizar a transmissão ou, se houver colisão na transmissão, providenciar a retransmissão. O algoritmo detecta a colisão do sinal transmitido e controla sua retransmissão com a definição de um tempo aleatório para transmitir e retransmitir os dados conforme a disponibilidade do meio (cabo), por meio de protocolos de revezamento. Esse padrão é implementado nas redes padrão Ethernet, normatizadas pela IEEE 802.3.

_**CARRIER SENSE MULTIPLE ACCESS WITH COLLISION AVOIDANCE**_ **(CSMA/CA)**

Protocolo que define o formato de utilização de um meio de comunicação compartilhado por meio de prevenção de colisão de onda portadora. Seu funcionamento é realizado a partir da análise do meio pelo qual o sinal será transmitido, e ao se verificar que o canal está livre, a transmissão é iniciada. Como apresentam Kurose e Ross (2013), durante a transmissão em uma rede de computadores, cada host verifica o canal antes de transmitir e abstém-se de transmitir quando percebe que o canal está ocupado. Esse é um padrão utilizado pelas redes sem fio (_wireless_) e normatizado pela IEEE 802.11.

Essa camada é composta também por outros protocolos que regem a comunicação em redes de telecomunicações e redes convergentes no contexto de integração entre redes de telecomunicações e redes de computadores.

______

**➕****Saiba mais**

Protocolos de redes de computadores são os padrões desenvolvidos via programação que regem o funcionamento dos serviços em redes de computadores. Além das aplicações dos protocolos de redes de computadores e suas funções, existe uma preocupação quanto a questões de segurança em redes, que transcendem a funcionalidade de cada protocolo e é suportada por protocolos adicionais, que operam em camadas ou mesmo em subcamadas. Segundo Stallings (2015), o SSH é um protocolo para comunicações seguras de rede projetado para que sua implementação seja relativamente simples. Aplicações SSH cliente e servidor são encontradas na maioria dos sistemas operacionais e utilizadas para login remoto e tunelamento (termo utilizado nas VPN – _Virtual Private Network_).