[![](https://ampli-images.s3.amazonaws.com/production/95bdd43f-14b5-4a81-99f5-f161e603740d/original)](https://ampli-images.s3.amazonaws.com/production/95bdd43f-14b5-4a81-99f5-f161e603740d/original)

A camada de transporte ou _Transport Layer_ é uma camada composta por protocolos de transporte de dados em rede que fornecem à camada de aplicação serviços de empacotamento e comunicação de duas formas, sendo uma delas via serviços orientados à conexão e a outra via serviços não orientados à conexão. Ela tem como objetivo principal gerenciar conexões ponto a ponto para garantir a integridade dos dados por meio de sequenciamento de pacotes segmentados no envio e recebimento de mensagens. Suas principais funções são: tratar questões de transporte entre _hosts_, contabilizar o transporte de dados, estabelecer circuitos virtuais, detectar e recuperar falhas e controlar o fluxo de informações. Ademais, nessa camada, há o endereçamento via portas das informações, via protocolos de camada de aplicação.

De acordo com Tanenbaum (2011), quando um processo de aplicação deseja estabelecer uma conexão com um processo de aplicação remoto, é necessário especificar a aplicação com a qual ele vai se conectar, o que ocorre por meio da definição de um endereço de transporte, chamados de portas ou _Transport Service Access_ Point (TSAP), que se associam a sessões de acesso, chamadas de _Socket_. Exemplificando, quando um usuário solicita o acesso a um site de internet, ele digita o URL referente ao _site_, que vai abrir uma sessão no _browser_ identificada pelo endereço IP relacionada a URL e seguida do número da porta, que identifica o serviço. O usuário ainda poderá solicitar uma nova página, em uma nova aba do navegador, com o endereço adicionado do número de porta, que é a mesma referente ao serviço de HTTP, porém com um TSAP diferente, que identifica um novo _socket_.

A figura abaixo mostra um exemplo de comunicação utilizando-se as portas dentro de um sistema de rede de computadores. Na figura, podemos perceber que no segmento A-B, o número da porta de origem serve como parte de um endereço de retorno (por exemplo, quando B quer enviar um segmento de volta para A, a porta de destino no segmento B-A toma seu valor do valor da porta de origem do segmento A-B). Observe, também, que o endereço de retorno completo é o endereço IP adicionado do número da porta de origem de A. Utilizando o UDP, por exemplo, o servidor usa um método recvfrom() para extrair o número de porta cliente-servidor de origem do segmento que recebe do cliente e envia um novo segmento ao cliente com o número de porta que extraiu, servindo como o número de porta de destino desse novo segmento.

[![](https://ampli-images.s3.amazonaws.com/production/a303c4ca-57e5-4129-aeac-b8e11a9e70ba/original)](https://ampli-images.s3.amazonaws.com/production/a303c4ca-57e5-4129-aeac-b8e11a9e70ba/original)

Comunicação em redes de computadores por meio de portas (TSAP). Fonte: Kurose; Ross (2013, p. 142).

Tanenbaum (2011) afirma que a camada de transporte juntamente à camada de rede formam o núcleo da hierarquia de protocolos. A seguir, apresentaremos a descrição de seus principais protocolos.

_**User Datagram Protocol**_ **(UDP)**

É um protocolo de nível de transporte não orientado à conexão utilizado para transmissões que necessitam de maior velocidade de entrega, porém ele não garante a entrega dos dados e é utilizado, por exemplo, em aplicações de _streaming_ de áudio e vídeo, em que a falta de um fragmento da mensagem não é relevante. A camada de transporte mapeia o pedido de transmissão de host feito ao serviço não orientado à conexão fornecido pela camada de inter-rede.

As principais características de um protocolo UDP são:

1. Protocolo de transporte sem conexão.
2. Transporta dados sem confiabilidade entre hosts.
3. Realiza transmissão sem conexão e de forma não confiável.
4. Não tem tratamento de erros;
5. Não garante a entrega das mensagens;
6. Sem controle de congestionamento.
7. Sem controle de fluxo.
8. Não reagrupa mensagens.

As aplicações desse protocolo são para _streaming_ media, teleconferência, telefonia IP e controles.

Um segmento UDP é simples, tem uma estrutura formada por campos de cabeçalho com os números de porta de origem e destino do _host_ de rede, o comprimento do número de _bytes_ do segmento e o campo com informação de verificação dos erros no segmento e, naturalmente, o campo de dados (mensagem). A figura abaixo apresenta a estrutura de um segmento UDP. Observe que o cabeçalho UDP tem apenas quatro campos com 2 _bytes_ cada. Os números de porta permitem que o host destinatário passe os dados da aplicação ao processo correto que está funcionando no sistema final do destinatário. O campo de comprimento especifica o número de _bytes_ no segmento UDP (cabeçalho mais dados). A soma de verificação é usada pelo host receptor para verificar se foram introduzidos erros no segmento. Por fim, o campo de comprimento especifica o comprimento do segmento UDP, incluindo o cabeçalho, em bytes.

[![](https://ampli-images.s3.amazonaws.com/production/d5aeb14b-e929-4f73-8dd6-ae21342bffde/original)](https://ampli-images.s3.amazonaws.com/production/d5aeb14b-e929-4f73-8dd6-ae21342bffde/original)

Estrutura do segmento do UDP. Fonte: Kurose; Ross (2013, p. 148).

O UDP é um protocolo não orientado à conexão, sem garantia de entrega, utilizado para aplicações que necessitam de velocidade de acesso e não obrigatoriamente da entrega de 100% dos dados, como transmissões de áudio e vídeo pela internet, jogos online e sistemas de mensagens instantâneas, como o WhatsApp, por exemplo. Os principais protocolos de aplicação que utilizam esse tipo de transmissão são: TFTP, DHCP, SNMP, NFS e DNS.