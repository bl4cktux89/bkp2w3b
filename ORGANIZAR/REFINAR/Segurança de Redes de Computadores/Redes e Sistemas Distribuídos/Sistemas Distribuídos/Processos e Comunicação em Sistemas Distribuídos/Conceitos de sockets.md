[![](https://ampli-images.s3.amazonaws.com/production/4b27567e-9b4c-474d-bfa4-18b3786f79e6/original)](https://ampli-images.s3.amazonaws.com/production/4b27567e-9b4c-474d-bfa4-18b3786f79e6/original)

A padronização da interface da camada de transporte permitiu que os protocolos de troca de mensagens sejam utilizados pelos programadores no desenvolvimento de aplicações que envolvam mais de uma máquina. Uma mensagem enviada de um processo para outro deve passar pela rede, e uma forma de realizar a implementação dessa comunicação é utilizando a interface de software denominada socket. É uma interface entre a camada de aplicação e o protocolo da camada de transporte.

> “Socket é um terminal de comunicação para o qual uma aplicação pode escrever dados que devem ser enviados pela rede subjacente e do qual pode ler dados que chegam.” (TANENBAUM; STEEN, 2007, p. 85).

[![](https://ampli-images.s3.amazonaws.com/production/5b02732e-9031-42cb-a649-d7ae5d123766/original)](https://ampli-images.s3.amazonaws.com/production/5b02732e-9031-42cb-a649-d7ae5d123766/original)

Comunicação entre dois processos via socket. Fonte: elaborada pela autora.

A figura acima ilustra a comunicação utilizando _socket_ entre dois processos de máquinas diferentes. A seta vermelha indica a origem e o destino da mensagem. Para que o Processo 2 receba uma mensagem do Processo 1, é necessário que a mensagem trafegue pela rede. Como o Processo 1 é o processo emissor, é necessário que, quando a mensagem for enviada por ele, contenha o dado, o endereço e o identificador do processo receptor da mensagem.

Na camada de rede da internet, o endereço é fornecido pelo IP (_Internet Protocol_), que identifica a máquina destino de forma única. O identificador do processo receptor é um número de porta. Aplicações mais utilizadas possuem um número de porta padrão, como é o caso do servidor web, que é identificado pela porta 80, e o servidor de e-mail, pela porta 25.

A interface _socket_ pode utilizar os protocolos de transporte TCP (_Transmission Control Protocol_) ou UDP (_User Datagrama Protocol_). _Sockets_ utilizando TCP/IP possuem as primitivas sintetizadas no quadro abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/b4bbf6b3-d262-485f-a541-0e1362173214/original)](https://ampli-images.s3.amazonaws.com/production/b4bbf6b3-d262-485f-a541-0e1362173214/original)

Primitivas da interface socket para TCP/IP. Fonte: adaptado de Tanenbaum e Steen (2007, p. 85).

- Uma chamada _socket_ retorna um descritor de arquivo que será utilizado em outras chamadas.
- A chamada _bind_ designa um endereço para o _socket_ no servidor.
- A chamada _listen_ aloca espaço para a fila de chamadas recebidas ao mesmo tempo.
- _Accept_ é utilizada para bloquear a espera por uma conexão de entrada.
- _Connect_ bloqueia o responsável pela chamada e inicia o processo de conexão.
- _Send_ e _receive_ são usadas para transmitir e receber dados em uma conexão _full-duplex_.
- Quando ambos os lados executarem _close_, a conexão será encerrada.

A implementação de programas no modelo cliente-servidor envolve a implementação de um processo cliente e um processo servidor, que utilizam _sockets_ para comunicação. Os serviços de _ssh_ (_secure shell_) e _ftp_ (_file transfer protocol_) são exemplos de implementações que utilizam sockets. O programa ssh é usado para realizar conexão entre duas máquinas e possui um processo cliente denominado ssh e um processo servidor denominado _**sshd**_ (_ssh deamon_). O programa ftp é usado para transferência de arquivo entre duas máquinas e possui um processo cliente denominado _ftp_ e um processo servidor denominado _**ftpd**_ (_ftp deamon_).

Os _sockets_ TCP são orientados à conexão e têm um canal exclusivo de comunicação entre cliente e servidor. Uma aplicação que faz transações bancárias é um exemplo de aplicação que pode usar sockets TCP.

Várias linguagens de programação, como _Java, PHP_ e _Python_, fornecem _socket_ ao desenvolvedor API, para facilitar o desenvolvimento das aplicações.

______

**💭Reflita**

Atualmente, existem muitos jogos que você pode jogar com seus amigos, por exemplo, _Minecraft, League of Legends_ e _Among Us_. Você já pesquisou como são implementados esses jogos? Como um jogador é capaz de visualizar os movimentos do outro jogador? É necessária a criação de processos e _threads_? Há comunicação entre processos ou compartilhamento de dados entre _threads_?