[![](https://ampli-images.s3.amazonaws.com/production/aa796b86-450c-4691-a97e-da3d6c0970fa/original)](https://ampli-images.s3.amazonaws.com/production/aa796b86-450c-4691-a97e-da3d6c0970fa/original)

Vamos iniciar nossos estudos sobre o modelo de referência e os protocolos de redes de computadores. Tais estudos são fundamentais para o entendimento de como os diversos dispositivos e sistemas se comunicam em uma rede de computadores, como se dá essa troca de informações e como os serviços e as aplicações são oferecidos em uma rede de computadores.

Padrões de comunicação são de extrema importância quanto à transmissão de dados entre computadores e sistemas em uma rede de computadores, principalmente quando vemos a quantidade e a diversidade de dispositivos e sistemas conectados à internet hoje. Antes da criação de um modelo de referência, quando uma empresa desejava desenvolver uma solução de computação em rede, ela precisava construir um sistema de informação baseado no conjunto de hardware, software, redes, dados e serviços, e todos baseados em tecnologias homogêneas, ou seja, era preciso que os computadores, os sistemas operacionais, os cabos e as aplicações, por exemplo, utilizassem tecnologias padronizadas entre os diferentes hosts (computadores) conectados a uma rede.

Com a evolução da tecnologia e o aumento de dispositivos de um sistema de informação, houve a necessidade de se desenvolver um modelo que possibilitasse que diferentes tecnologias interoperassem dentro de uma rede de computadores, o que exigiu que as tecnologias de rede fossem divididas em camadas ou níveis e organizadas em um modelo de referência.

Nesse cenário, a ISO normatizou um modelo de camadas de protocolos chamado OSI, que se tornou o modelo de referência ISO/OSI para os sistemas de redes de computadores, sobretudo para organização e interoperação dos protocolos de rede. Esse modelo foi originalmente organizado em sete camadas (aplicação, apresentação, sessão, transporte, rede, enlace e física) com funções bem definidas, conforme sua nomenclatura. Conforme afirmam Kurose e Ross (2013, p. 36-37), cada protocolo de rede pertence a uma das camadas do modelo, e uma camada de protocolo pode ser executada em softwares, hardware ou em uma combinação de ambos. A figura a seguir nos mostra a estrutura de camadas do modelo OSI.

[![](https://ampli-images.s3.amazonaws.com/production/7bcd3c7c-5bb0-41e6-ad0b-a1dc333e46a3/original)](https://ampli-images.s3.amazonaws.com/production/7bcd3c7c-5bb0-41e6-ad0b-a1dc333e46a3/original)

Modelo OSI. Fonte:elaborada pelo autor.

De acordo com Tanenbaum (2011), as funções das camadas são as seguintes:

- **Camada de aplicação**: camada mais próxima do usuário em que ocorre a comunicação; responsável por operacionalizar os sistemas de informação/aplicativos, definindo como ocorre a comunicação entre esses sistemas e os usuários e como as informações devem ser transmitidas e recebidas via protocolos existentes. Um exemplo de protocolo dessa camada é o _Hyper Text Transfer Protocol_ (HTTP), utilizado para sistemas baseados em hipertexto no universo da _World Wide Web_ (WWW) e acessado via navegadores (browsers).
- **Camada de apresentação**: responsável por definir a apresentação e a formatação dos dados. Essa camada tem por objetivo a compreensão dos dados, considerando a sintaxe e a semântica das informações transmitidas pela rede, direcionando os dados para aplicações finais na camada de aplicação.
- **Camada de sessão**: essa camada permite que os usuários, em diferentes hosts ou em uma instância de navegador, como _software_ de aplicação, estabeleçam sessões de comunicação entre as aplicações.
- **Camada de transporte**: essa camada tem como função básica aceitar dados da camada acima, dividi-los em unidades menores e determinar o tipo de serviço a ser executado com um protocolo orientado à conexão ou com um protocolo não orientado à conexão. O _Transmission_ Control _Protocol (TCP)_ e o User _Datagram Protocol_ (UDP) são exemplos de protocolos dessa camada.
- **Camada de rede**: essa camada tem como objetivo controlar as operações da sub-rede, identificando e gerenciando a maneira como os pacotes de dados são roteados do _host_ de origem até o host de destino e realizando, também, o endereçamento lógico dos _hosts_ de rede. Um exemplo de protocolo dessa camada é o Internet _Protocol_ (IP).
- **Camada de enlace**: essa camada tem como tarefa principal transformar um canal de comunicação em uma linha de dados livre de erros. Alguns exemplos de protocolos dessa camada são o _IEEE_ 802.3 para redes cabeadas e o _IEEE_ 802.11 para redes _wireless_, _Asynchronous Transfer_ Mode (ATM) e Frame _Relay_.
- **Camada física**: camada que trata a transmissão de sinais, o meio físico e onde está situada toda a parte de hardware da rede, como placas, _switches_, conectores, cabos, entre outros.

Conforme afirma Tanenbaum (2011), o modelo OSI segue os seguintes princípios: uma camada deve ser criada onde houver necessidade de outro grau de abstração; cada camada deve executar uma função bem definida; a função de cada camada deve ser escolhida tendo-se em visa a definição de protocolos; e os limites de cada camada devem ser escolhidos para minimizar o fluxo de informações.

Os dados transmitidos em um sistema de redes são chamados de “carga útil” ou _payload_, conforme Kurose e Ross (2013). Para cada camada, os dados (ou carga útil) adicionados de informações de cada camada recebem nomes diferentes.

Considerando-se o modelo OSI, os dados da camada física são chamados de bits, os dados na camada de enlace são chamados de quadros (_frame_), os dados na camada de rede são chamados de datagramas (pacotes), os dados na camada de transporte são chamados de segmentos ou, tecnicamente, de _Transport Protocol_ _Data Unit_ (TPDU), os dados na camada de sessão são chamados de _Section Protocol Data Unit_ (SPDU), na camada de apresentação de _Presentation Protocol Data Unit_ (PPDU) e, por fim, na camada de aplicação de mensagem ou _Application Protocol Data Unit_ (APDU).

[![](https://ampli-images.s3.amazonaws.com/production/c72b703e-3c20-4c4b-81f2-d5cc4b93fdc1/original)](https://ampli-images.s3.amazonaws.com/production/c72b703e-3c20-4c4b-81f2-d5cc4b93fdc1/original)

Terminologia de dados nas camadas do modelo OSI. Fonte: elaborada pelo autor.