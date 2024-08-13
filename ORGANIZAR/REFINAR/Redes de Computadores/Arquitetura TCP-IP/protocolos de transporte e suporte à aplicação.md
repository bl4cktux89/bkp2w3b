### Introdução

Para discutirmos os protocolos da camada de transporte e suas implementações utilizando software de captura de pacotes Wireshark. O foco do presente tópico é a camada de Transporte, mais especificamente, os protocolos UDP e TCP. Entretanto, vamos abordar brevemente as demais camadas.

O Wireshark, como pode ser observado na figura abaixo, utiliza o modelo TCP/IP de cinco camadas para mostrar e detalhar as informações de cada protocolo. De cima para baixo. Na Figura 1(a) é mostrada a captura de um pacote da Aplicação DNS (Domain Name System – Sistema de Nome de Domínios) que utiliza como protocolo de transporte UDP (User Datagram Protocol – Protocolo de Datagrama de Usuário), enquanto que na Figura 1(b) é mostrada a captura de pacote da Aplicação HTTP (Hypertext Transfer Protocol – Protocolo de Transferência de Hipertexto). Além disso, observa-se que as capturas mostram que os protocolos DNS e HTTP utilizam, respectivamente, IPv6 e IPv4, respectivamente. E na camada de Enlace ou Acesso a rede, o protocolo de controle de acesso ao meio é o Ethernet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/1/1768188/40218-camadas-do-modelo-tcpip-de-cinco-camada.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/1/1768188/40218-camadas-do-modelo-tcpip-de-cinco-camada.jpg)

Fonte: wireshark

O serviço DNS, mostrado na captura da figura 1(a), como já comentado, utiliza o protocolo de transporte UDP na camada de transporte. O UDP é protocolo de transporte não confiável e sem conexão, como pode ser observado na figura acima. Quando comparamos as camadas de Transporte da figura 1 (a) e (b), percebemos que o UDP possui menos elementos de controle de transmissão (baixo overhead), tendo apenas o endereço de porta de origem (Src Port) e a porta de destino (Dst Port), enquanto que o TCP apresenta os campos anteriores e ainda o número de sequência (Seq) e reconhecimento (Ack). Isso se deve, pois, o TCP é confiável, necessitando receber confirmação.

A complexidade do TCP em relação ao UDP pode ser ilustrada ao observarmos os detalhes do segmento, conforme mostrado na figura 2 (a) e (b), respectivamente. Como pode ser visto, existem muito mais campos no TCP do que no UDP

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/1/1768193/40219-detalhes-do-protocolo-tcp-no-wireshark.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/1/1768193/40219-detalhes-do-protocolo-tcp-no-wireshark.jpg)

Fonte: Wireshark

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/1/1768197/40220-detalhes-do-protocolo-udp-no-wireshark.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/1/1768197/40220-detalhes-do-protocolo-udp-no-wireshark.jpg)

Fonte: wireshark

### Estabelecimento de conexão TCP

O estabelecimento de uma conexão TCP começa com o processo conhecido como _**three-way-handshake**_ (aperto de mão três vezes). A captura de segmento TCP é mostrado na figura 3. O processo começa com o cliente (à esquerda) enviando um segmento com a flag Syn (sincronização) ativada para o servidor (site [**www.uninove.br**](http://www.uninove.br/)) que está “ouvindo” na porta 443 (HTTPs – HTTP seguro). Perceba que a porta de origem (65423) também é enviada e o número de sequência (Seq) é setado em 0. Como este processo é de sincronismo e não possui dados da camada de aplicação, o Ack é setado em 0.

Na sequência, o servidor também envia um segmento com a flag Syn ativada, para indicar que ele também quer estabelecer sessão. Além disso, a flag Ack também é setada, o que indica que o servidor recebeu Ack = 0 (cliente envia Ack=x, servidor envia Ack=x+1). O handshake triplo termina com o cliente respondendo com a flag Ack = 1. A partir desse momento a conexão está estabelecida. Cabe reforçar que o _**three-way-handshake**_ não ocorre com o protocolo UDP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768202/40221-estabelecimento-de-conex-o-tcp.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768202/40221-estabelecimento-de-conex-o-tcp.jpg)

Fonte: Wireshark

### Transferência de dados

Após o estabelecimento da conexão, conforme mostrado anteriormente, a transferência de dados pode ser iniciada. Nesta etapa, o cliente como o servidor podem transmitir tanto dados como confirmação. Para mostrar isso, acessei a aplicação HTTP (porta 80) da minha rede local que possui o IP 192.168.0.14.

A confirmação é combinada com os dados, no que é chamada de piggybacking (carregar nas costas). Para o envio de dados a flag Psh (Push – empurrar) é ativada, assim como a flag Ack, conforme figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768205/40222-envio-de-dados-tcp-flag-psh-e-ack-ativa.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768205/40222-envio-de-dados-tcp-flag-psh-e-ack-ativa.jpg)

Fonte: Wireshark

Vamos, agora, entender como ocorre o processo de envio de dados e confirmação. Para iniciar devemos utilizar o modo gráfico do Wireshark, que mostra o processo ao longo do tempo, conforme mostrado na figura abaixo. Cada linha representa um segmento enviado ou recebido, além de mostrar também, as PSH, ACK e o tamanho do segmento TCP (Len). Observe que as portas de origem e destino são, respectivamente, 53590 e 80. Vamos detalhar o processo para os primeiros quatro segmentos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768206/40223-fluxo-de-transfer-ncia-de-dados-tcp.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768206/40223-fluxo-de-transfer-ncia-de-dados-tcp.jpg)

Fonte: Wireshark

**Atenção**

Embora o TCP mantenha o controle sobre os segmentos que são enviados e recebidos, não existe um campo específico para indicar **o número de um segmento em seu cabeçalho**. Em vez disso ele utiliza o **número de sequência e o número de confirmação**. Esses dois campos se referem ao número de bytes e não ao número do segmento. Os bytes de dados são numerados pelo TCP em cada uma das conexões. A numeração começa com um número gerado randomicamente entre 0 e 232 -1. O valor do campo **número de sequência (Seq)** define **o número do primeiro byte de dados** contido naquele segmento. Enquanto que o valor do **campo confirmação (Ack)** define o **número do próximo byte** que o lado remoto espera receber. Este número é cumulativo (Forouzan, B. A, 2010).

**Primeiro Segmento**

O primeiro segmeto TCP com flag PSH é mostrado na figura abaixo

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768208/40224-primeiro-segmento-tcp-com-flag-psh-ativ.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768208/40224-primeiro-segmento-tcp-com-flag-psh-ativ.jpg)

O primeiro segmento enviado pelo cliente possui os seguintes dados, conforme extraído do Wireshark:

- Número de Sequência (Seq) = 1. Indica o número do primeiro byte a ser enviado
- Número de reconhecimento (Ack) = 1.
- Tamanho do segmento TCP (Len) = 445. É o tamanho em bytes do segmente TCP mais os bytes da camada de aplicação, neste caso, HTTP.
- A flag PSH está ativada, indicando o envio de dados.

**Segundo Segmento**

O segundo segmeto TCP com flag PSH é mostrado na figura abaixo

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768211/40226-segundo-segmento-tcp-com-flag-psh-ativa.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768211/40226-segundo-segmento-tcp-com-flag-psh-ativa.jpg)

Fonte: Wireshark

O segundo segmento corresponde a resposta e o envio de dado do servidor para o cliente, que contem:

- Número de Sequência (Seq) = 132. Indica o número do primeiro byte a ser enviado
- Número de reconhecimento (Ack) = 446. 446 é indicativo que o servidor recebeu os bytes de 1 a 445.
- Tamanho do segmento TCP (Len) = 5. É o tamanho em bytes do segmente TCP mais os bytes da camada de aplicação, neste caso, HTTP.
- A flag PSH está ativada, indicando o envio de dados.

**Terceiro Segmento**

O terceiro segmeto TCP com flag PSH é mostrado na figura abaixo. A direção de envio é do cliente para o servidor

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768214/40227-terceiro-segmento-tcp-com-flag-psh-ativ.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768214/40227-terceiro-segmento-tcp-com-flag-psh-ativ.jpg)

Fonte: Wireshark

O terceiro segmento corresponde a resposta e envio de dados do cliente para o servidor, que contem.

- Número de Sequência (Seq) = 446. Indica o número do primeiro byte a ser enviado
- Número de reconhecimento (Ack) = 137. 137 é indicativo que o cliente recebeu os bytes de 132 a 136.
- Tamanho do segmento TCP (Len) = 446. É o tamanho em bytes do segmente TCP mais os bytes da camada de aplicação, neste caso, HTTP.
- A flag PSH está ativada, indicando o envio de dados.

**Quarto Segmento**

O quarto segmeto TCP com flag PSH é mostrado na figura abaixo. A direção de envio é do cliente para o servidor

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768215/40228-quarto-segmento-tcp-com-a-flag-psh-ativ.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768215/40228-quarto-segmento-tcp-com-a-flag-psh-ativ.jpg)

Fonte: Wireshark

O quarto segmento corresponde a resposta e envio de dados do servidor para o cliente, que contem.

- Número de Sequência (Seq) = 137. Indica o número do primeiro byte a ser enviado
- Número de reconhecimento (Ack) = 892. 137 é indicativo que o cliente recebeu os bytes de 446 a 891.
- Tamanho do segmento TCP (Len) = 136. É o tamanho em bytes do segmente TCP mais os bytes da camada de aplicação, neste caso, HTTP.
- A flag PSH está ativada, indicando o envio de dados.

### Encerramento da conexão TCP

O encerramento da conexão TCP envolve a ativação da flag FIN (finalização) por um processo que pode acontecer em três (handshake triplo) ou quatro (handshake quadruplo) vias. A execução desse processo pode ser iniciada tanto pelo cliente quanto pelo servidor. Na figura abaixo é mostrado o processo de encerramento iniciado pelo cliente. Neste processo, ambos os lados encerram a conexão, mas pode ocorrer de um dos lados ter ainda dados para serem enviados e, dessa forma, apenas um dos lados encerrar a conexão.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768218/40291-processo-de-encerramento-de-conex-o-tcp.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768218/40291-processo-de-encerramento-de-conex-o-tcp.jpg)

Fonte: Wireshark

**Primeiro segmento**

A solicitação de encerramento da conexão é enviada pelo cliente. As flags FIN e ACK são ativadas e o número de sequência do primeiro byte é 642 e o ACK= 4588.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768219/40292-encerramento-da-conex-o-tcp-flags-fin-e.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768219/40292-encerramento-da-conex-o-tcp-flags-fin-e.jpg)

Fonte: Wireshark

**Segundo segmento**

O servidor envia um ACK, confirmando o encerramento da conexão. A flag ACK é ativada, sendo o número de sequência do primeiro byte é 4588 e o ACK= 643 (642+1), confirmando o segmeto anteriormente recebido.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768224/40293-encerramento-de-conex-o-tcp-envio-de-um.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768224/40293-encerramento-de-conex-o-tcp-envio-de-um.jpg)

Fonte: Wireshark

**Terceiro segmento**

Como o servidor também não tem dados a serem enviados, ele também ativa a **flag FIN e ACK.** O Servidor agora escolhe um número aleatório para o ACK e ativa a flag FIN, além de informar que o primeiro byte tem o número de sequência igual 91291.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768226/40294-encerramento-de-conex-o-tcp-servidor-ta.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768226/40294-encerramento-de-conex-o-tcp-servidor-ta.jpg)

Fonte: Wireshark

**Quarto segmento**

O envio do quarto segmento do handshake de 4 vias consiste da resposta do cliente a solicitação de encerramento da conexão pelo servidor. Para tanto, a flag ACK é ativada. O ACK é enviado com valor em 91292 (91291 + 1) e o primeiro byte do segmento é 2986.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768229/40295-encerramento-da-conex-o-tcp-flag-ack-at.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/2/1768229/40295-encerramento-da-conex-o-tcp-flag-ack-at.jpg)