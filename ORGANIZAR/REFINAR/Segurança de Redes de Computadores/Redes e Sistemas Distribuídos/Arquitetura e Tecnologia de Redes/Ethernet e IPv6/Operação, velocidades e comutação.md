[![](https://ampli-images.s3.amazonaws.com/production/4cf98b3f-a15f-4aa1-a7e0-ed65722ec3ce/original)](https://ampli-images.s3.amazonaws.com/production/4cf98b3f-a15f-4aa1-a7e0-ed65722ec3ce/original)

Conhecemos a tecnologia Ethernet e um pouco mais sobre o cabeamento metálico de par trançado. Agora, verificaremos sobre os meios de transmissão dentro desta tecnologia.

O protocolo Ethernet é um padrão de comunicação que compartilha um mesmo meio de comunicação (cabo) com todos os dispositivos de rede (_hosts_). Para transmissão, um dispositivo verifica a disponibilidade do canal e transmite. Caso haja outro dispositivo também transmitindo, ocorrerá uma colisão, a transmissão é interrompida e refeita em um tempo aleatório controlada pelo algoritmo do protocolo de acesso múltiplo ao meio compartilhado. Este protocolo é o CSMA (_Carrier Sense Multiple Access_), o qual, conforme Forouzan (2010), faz a transmissão em um meio compartilhado via três algoritmos:

1. CSMA não persistente: se o meio de transmissão estiver ocupado, o dispositivo aguarda um tempo para retransmitir.
2. CSMA 1 persistente: o dispositivo verifica a rede até que o meio fique livre para transmissão.
3. CSMA p-persistente: o algoritmo calcula a probabilidade de colisão e, quando livre e com baixa possibilidade de colisão, realiza a transmissão.

O CSMA/CD (_Carrier Sense Multiple Access with Collision Detection_) utilizado no padrão Ethernet tem um mecanismo de detecção de colisão, no qual os dispositivos da rede verificam colisões e controlam a retransmissão dos dados no canal compartilhado.

De acordo com Filippetti (2008), o padrão Ethernet com o CSMA/CD utiliza uma topologia em estrela e define uma rede comutada por um elemento central chamado de _switch_ (antes eram utilizados apenas hubs) ou roteadores. A apresentação de uma topologia de rede comutada no padrão Ethernet é apresentada na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/8961ad2d-0b90-483f-a081-70504eb4c545/original)](https://ampli-images.s3.amazonaws.com/production/8961ad2d-0b90-483f-a081-70504eb4c545/original)

Rede em topologia estrela com um comutador (switch). Fonte: elaborada pelo autor.

Em uma rede Ethernet, podem ocorrer colisões de duas formas, sendo uma pelo domínio de colisão e outra pelo domínio de _broadcast_.

No domínio de colisão, os pacotes da rede têm a possibilidade de efetuar colisão uns com os outros, o que leva à degradação da performance da rede, pois faz com que muitas retransmissões sejam necessárias. Esta situação se agrava ainda mais quando há equipamentos de comutação (_hubs_) em formato de cascata, ou seja, interligados, formando uma topologia híbrida de estrela e árvore para expansão do número de dispositivos na rede.

Já no domínio de broadcast é possível determinar o limite que o pacote pode chegar utilizando-se um dispositivo comutador de rede local que operacionalize a comunicação com outro dispositivo sem que seja utilizado um roteador.

Os dispositivos comutadores possuem, desta forma, um importante papel para a performance de uma rede de computadores em domínios de colisão e _broadcast_. Estes dispositivos podem ser:

- _Hub_: são dispositivos concentradores que fazem comutação em uma rede com a repetição das mensagens para todas as suas portas de conexão, formando um único domínio de colisão e _broadcast_. Estes dispositivos foram muito importantes no cenário das redes, mas encontram-se praticamente em desuso na implantação de novas redes pois, conforme Stallings (2016), estes equipamentos foram substituídos pelos switches de camada 2 e têm seu nome também atribuído de _switching hub_ ou ponte de rede multiporta.
- _Switch_: dispositivo capaz de formar um domínio de colisão em cada porta de comunicação e formar um único domínio de _broadcast_. Dispositivo fundamental na operação das redes de computadores na atualidade, os switches estão divididos em _switches_ de camada 2 e _switches_ de camada 3. Como sustenta Stallings (2016), um _switch_ de camada 2 tem maior desempenho e pode incorporar as funções de uma ponte, assim novas instalações tipicamente incluem _switches_ de camada 2 com funcionalidades de ponte em vez de pontes. Estes _switches_ de camada 2 são boas opções para utilização em redes, nas quais usuários utilizam 80% do tempo se comunicando com dispositivos no segmento local. Os _switches_ de camada 3 são definidos por Stallings (2016) como um roteador baseado em hardware. Eles têm a função de gerenciar melhor as redes, identificando os fluxos dos pacotes IP com a mesma origem e destino, segmentando em sub-redes e quebrando os domínios de _broadcast_. Importante salientar que apenas _switches_ de camada 3 podem desempenhar a função de gerenciamento.
- _Router_: ou roteador, é um dispositivo que opera na camada 3 (inter-rede) do conjunto de protocolos TCP/IP e quebram o domínio de _broadcast_, pois operacionalizam roteamento na rede. São dispositivos utilizados nas redes de computadores da atualidade.
- _Bridge_: ou ponte, são dispositivos que podem separar domínios de colisão, porém não separam os domínios de _broadcast_. Estes dispositivos podem ainda ser sua implementação realizada por _switches_.

A próxima figura traz um exemplo de uma rede um pouco mais complexa, na qual os dispositivos de rede são utilizados para implementar o modelo Ethernet para uma rede local com domínio de colisão. Verifique que o roteador separa os domínios de _broadcast_ em três domínios. No domínio de colisão à direita do roteador, a topologia é conectada por hubs, formando um único domínio de colisão e _broadcast_. À esquerda do roteador, há dois domínios de colisão, formados pelos _switches_, e abaixo do roteador há um domínio de colisão formado por um único _switch_.

[![](https://ampli-images.s3.amazonaws.com/production/351d7734-f4e7-4d40-82ef-5009ec266c3f/original)](https://ampli-images.s3.amazonaws.com/production/351d7734-f4e7-4d40-82ef-5009ec266c3f/original)

Rede em topologia com domínio de colisão. Fonte: adaptada de Nunes (2017).

Assim finalizamos nosso estudo sobre operação de uma rede Ethernet, observando que esta tecnologia utiliza o método CSMA/CD para compartilhamento de um único canal de comunicação e dispositivos de rede, como hubs, switches, roteadores e pontes para definição de domínios de colisão e broadcast. Este planejamento faz com que uma rede tenha a performance adequada dentro das possibilidades de utilização de equipamentos de comutação.

______

**➕****Saiba mais**

O cabeamento utilizado dentro do padrão IEEE 802.3, ou seja, o padrão Ethernet, teve importantes evoluções tecnológicas nos últimos 50 anos. Comer (2016) relata que desde a versão original, na década de 1970, a Ethernet passou por várias alterações, sendo que a mais significativa foi no cabeamento. O cabo de rede utilizado no primeiro padrão Ethernet era chamado de _Thicknet_, ou cabo Ethernet grosso, passando pelos cabos _Thinnet_, chamados de cabo Ethernet, ou coaxial fino, pelos cabos de par trançado e hubs, utilizou diferentes tipos de conectores e chegou a padrões de cabos metálicos de par trançado mais atuais, que suportam redes Gigabit Ethernet.

A leitura da Seção 15.7, Evolução da Ethernet e cabos _Thicknet_, do Capítulo 15, _Tecnologias de LAN com fio (Ethernet e 802.3)_, do livro _Redes de Computadores e internet_, de Comer (2016), é prazerosa e traz informações sobre a evolução histórica e aplicada na prática de cabos de rede no padrão Ethernet.