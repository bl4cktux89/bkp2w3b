### Introdução

A camada de Transporte, também é conhecida como camada host-to-host. Essa designação está associada com a capacidade de estabelecimento de comunicação fim a fim. Isso significa que está camada estabelece uma comunicação direta entre um cliente e o servidor da aplicação. Como exemplo, imagine que você tenha que acessar o site da Uninove (Servidor). Para tanto, você precisa de um programa cliente e, neste caso, será o seu navegador (cliente). Nessa comunicação as camadas de transporte do cliente e do servidor se comunicam diretamente sem intermediários. Enquanto que os protocolos da camada de enlace de dados se preocupam com o enlace entre um nó e outro diretamente conectados e a camada de internet busca descobrir o melhor caminho para o destino dos pacotes, a camada de transporte é responsável pelo gerenciamento da conexão entre o cliente e servidor, sem se preocupar com o que ocorre nas camadas inferiores. Lembre-se que as camadas são projetadas de modo independente, apenas fornecem serviços as camadas superiores. A figura abaixo exemplifica esse processo. Perceba que a comunicação, apesar de passar pelas camadas inferiores, é fim-a-fim

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268165/13267.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268165/13267.png)

Relação entre as camadas do modelo TCP/IP

A característica fundamental dos protocolos da pilha TCP é que, antes de iniciar qualquer transmissão de dados propriamente dita, o protocolo estabelece um canal virtual entre o host de origem e destino por meio de um processo conhecido como orientação da conexão. De uma maneira simplória, esse processo consiste em negociar parâmetros para estabelecimento da conexão, transmissão de dados e por fim, o encerramento da conexão. Para entender melhor esse processo, vamos fazer uma analogia: Imagine que duas pessoas, A e B, que não se conhecem necessitam se falar. As duas pessoas são bem educadas e por isso o diálogo poderia ser da seguinte forma:

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/3/3/3/1833313/38747.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/3/3/3/1833313/38747.png)

Podemos dizer, a partir da analogia acima, que os protocolos da Pilha TCP são educados, justamente porque todos os passos de uma transmissão são negociados previamente para garantir a confiabilidade na transmissão. E se o diálogo fosse feito com UDP? Na verdade, não existiria nenhum diálogo!! O UDP (User datagram Protocol, Protocolo de Datagrama de usuário) poderíamos chama-lo de mal educado, pois não quer saber se o servidor pode receber ou não. A única característica que ele tem do TCP é o fato de receber blocos de dados das camadas superiores e os quebra em segmentos menores. Não existe controle de fluxo, confirmação, muito menos estabelecimento de um circuito virtual. Portanto, se a pessoa A está usando UDP, ela enviará o que ela quiser da forma que achar melhor, sem pedir licença para a pessoa B. Caso a pessoa B esteja disponível, a transmissão ocorrerá de maneira satisfatória. Caso contrário, a camada de aplicação se encarregará de reportar o erro.

### Protocolos TCP/IP

A camada transporte pode ser divida em dois protocolos principais ou classes de protocolos: TCP e UDP. O protocolo TCP (Transmission Control Protocol, Protocolo de Controle de Transmissão) tem como principal característica oferecer maior confiabilidade na transmissão devidos aos mecanismos de (Kurose, James F e Ross, W. Keith, 2013):

- **Segmentação:** Blocos de dados vindos da camada de aplicação são segmentados em blocos menores. Cada um desses blocos menores é identificado com um número de sequência para que o destinatário possa reordena-los. Isso ocorre quando a mensagem supera o Tamanho Máximo do Segmento (MSS). Por exemplo, você tem que enviar um vídeo de 200.000 bytes e o valor do MSS esteja definido como 1000 bytes. Para transmitir essa quantidade dados 200 segmentos deverão ser criados e numerados. Supondo, agora, que o primeiro byte de dados seja numerado como zero. Para transmitir os 200 segmentos, o primeiro número de sequência será 0, o segundo será 1, o terceiro será 2 e assim por diante, conforme mostrado na figura abaixo (Kurose, 2013).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/8/1/1638144/38874.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/8/1/1638144/38874.jpg)

O valor máximo MSS é acertado entre o transmissor e receptor no estabelecimento da conexão TCP, por meio do uso do **campo opções** do cabeçalho TCP. Geralmente, o valor de MSS é escolhido de tal forma que evita a fragmentação do pacote IP da camada de internet. Ou seja, MSS mais os cabeçalhos devem ser menores do que o MTU (Maximum Tranfer Unit, unidade máxima de transmissão) da camada de enlace – MSS + Cabeçalhos ≤ MTU.O MTU típico da camada das redes Ethernet é de 1500. Sabendo que os cabeçalhos TCP e IP são tipicamente definidos em 20 Bytes, o que resta para o MSS ou dados da camada de Aplicação é igual a 1460 bytes, conforme ilustrado na figura abaixo com base no modelo TCP/IP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635332/38875.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635332/38875.jpg)

- **Número de sequência e reconhecimento:** O número de reconhecimento (ACK) é o número de sequência que um host espera receber após uma transmissão. Isso indica que o host recebeu os segmentos anteriores e está pronto para os próximos. Seguindo com o nosso exemplo anterior, suponha que um host A recebeu os segmentos de 0 a 100 de B. A enviará um número de ACK 101 para B informando que ele recebeu todos dados até este número. Veja abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635340/38964.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635340/38964.jpg)

- **Controle de Congestionamento:** O TCP ao receber mensagens de reconhecimento ACK (Acknowledgement) recebidos em função do tempo de acordo com o tempo de ida e volta, o TCP prediz se a rede está ou não congestionado e desse modo, pode reduzir sua taxa de transferência. Em outras palavras, caso haja a perda de pacotes ou atraso, o TCP supõe que há congestionamento e reduz fluxo de dados enviados.
- **Estabelecimento da conexão TCP:** O processo de estabelecimento pode ser considerado a principal diferença com os protocolos da pilha UDP. O processo é ilustrado na figura abaixo.

1. Antes de iniciar a transmissão, o host 1 envia um segmento de sincronização, chamado **SYN** (com o _**flag**_ **Syn** setado em 1), com um número de sequência escolhido aleatoriamente (Seq=X).
2. O Host 2 recebe o **SYN**, inicializa a variável e aloca buffer, e envia uma mensagem de reconhecimento de conexão (**SYN-ACK**), com as flags SYN e ACK setadas com 1. Tendo como objetivo reconhecer a solicitação de conexão, especificando o número de sequência inicial em Seq=Y e Ack=X+1.
3. Recebido o reconhecimento (ACK) do host 2, o host 1 confirma a conexão com um ACK (_flag_ Syn agora em 0 e _**flag**_ **Ack** setado em 1), indicando um reconhecimento válido e na sequência, aloca buffer e inicializa as variáveis de conexão (Seq=X+1, Ack=Y+1). Como a conexão e bidirecional, o host 2 aproveita o envio do ACK para enviar também a solicitação de conexão SYN com número de sequência y.
4. Da mesma forma o host 1 devolve o ACK = y +1 e o número de sequência x acrescido de + 1.

Como pode ser observado esse processo ocorre em três, conhecido como Three-way Handshake (aperto de mão três vezes).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268363/13275.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268363/13275.png)

Processo de estabelecimento da conexão

Para garantir essa confiabilidade o TCP necessita de muitos campos de controle, conforme mostrado na figura abaixo, o que resulta em um maior uso de largura de banda (overhead). Atualmente, as redes são muito mais confiáveis do que no passado e por isso, muitos dos controles poderiam ser dispensados. O TCP é, portanto, um protocolo que deve ser utilizado em aplicações que requerem alto grau de confiabilidade como, por exemplo, transferência de arquivos via FTP (Filippetti, Marco. A. 2017).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268174/13270.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268174/13270.png)

Cabeçalho TCP

Os campos do cabeçalho TCP de 20 bytes de comprimento são descritos abaixo  (Tanenbaum, A. S, 2011):

- **Número de Porta de Origem**: número que identifica o protocolo da camada de aplicação (processo) que envia os dados
- **Número de Porta de Destino**: número que identifica o protocolo da camada de aplicação (processo) que recebe os dados
- **Número de Sequência**: número que identifica no processo de reordenação dos segmentos no lado destino
- **Número de Confirmação**: Identifica qual o último segmento transmitido com sucesso. Se a flag ACK estiver ativada o valor deste campo será o próximo número de sequência que o destinatário espera receber.
- **Comprimento do Cabeçalho** (Data offset): Define o tamanho do cabeçalho TCP em palavras de 32 bits. O tamanho mínimo é de 5 palavras (20 bytes, sem opções) e o tamanho máximo é de 15 palavras (60 bytes, com opções).
- **Flags: Bits de Controle** (Cada flag usa 1 bit), que define:
    - URG - Campo Ponteiro de Urgente quando ativado.
    - ACK - Bit de Confirmação. Quando ativado, indica que o segmento carrega uma mensagem de confirmação e que o valor do campo Número de Confirmação é válido, e carrega o próximo número de sequência esperado pelo host.
    - PSH - Bit de Push. Quando ativado, indica que o transmissor do segmento usa o recurso TCP Push.
    - RST - Bit de Reset. Quando ativado indica que o transmissor encontrou um problema e deseja resetar a conexão.
    - SYN - Bit de Sincronismo. Requisição para sincronizar números de sequência e estabelecer uma conexão entre dois hosts.
    - FIN - Bit de Finalização. Quando ativado indica que o transmissor do segmento requisita que a conexão seja encerrada.
- **Tamanho da Janela**: Define o tamanho da janela de recepção, ou seja, o número de bytes que o transmissor deste segmento quer aceitar do host de destino, em cada transmissão. **Checksum**: Usado para verificação de erros do cabeçalho e dos dados transmitidos.
- **Ponteiro de Urgente**: Utilizado para priorizar o encaminhamento de determinados segmentos.
- **Opções**: Campo opcional, que representa informações não cobertas pelos demais campos do cabeçalho TCP como, por exemplo, o MSS.

### Protocolo UDP

A primeira coisa que podemos falar sobre o UDP User Datagrama Protocolo (Protocolo de datagrama de usuário) é que ele não é confiável. Não confunda confiável com seguro. A segurança de uma transmissão é feita por outros protocolos. A falta de confiabilidade do UDP está associada, principalmente, com a não garantia que o pacote chegará ao seu destinatário. Outra característica importante desta classe de protocolos é que ele não é orientado a conexão, ou seja, não estabelece circuitos virtuais entre origem e destino  (Filippetti, Marco. A. 2017).. A única funcionalidade existente no UDP semelhante ao TCP, como já comentado anteriormente, é a capacidade de efetuar a segmentação de blocos de dados provenientes da camada de Aplicação. Por esses motivos a sua complexidade é reduzida assim como o seu cabeçalho, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635342/38965.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635342/38965.jpg)

O protocolo UDP surgiu após o TCP - em 1980 - em resposta a complexidade do TCP que se traduz em menor uso da largura de banda em virtude do seu cabeçalho com poucos campos, conforme mostrado na figura acima. Existem diversar aplicações que fazem uso do UDP, dentre elas, podemos citar a solicitação de endereços IPs via protocolo DHCP e também o protocolo utilizado para gerência de redes (SNMP). Abaixo são mostrados alguns protocolos da pilha TCP e UDP. Observe que alguns protocolos como, por exemplo, o DNS pode utilizar tanto UDP quanto TCP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/7/240772/9234.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/7/240772/9234.png)

Protocolos TCP e UDP

Os campos do cabeçalho UDP são descritos abaixo (Tanenbaum, A. S, 2011):

- **Número de Porta de Origem**: número que identifica a porta lógica (processo) de quem envia os dados
- **Número de Porta de Destino**: número que identifica a porta lógica (processo) de quem deve receber os dados
- **Comprimento**: Este é um campo que especifica o comprimento em bytes do cabeçalho UDP mais os dados carregados.
- **Checksum**: É um campo opcional e pode ser usado para verificação de erros via checagem de redundância cíclica (CRC) do cabeçalho e dos dados .
- **Dados:** Dados propriamente ditos passados da camada de aplicação para a de transporte.