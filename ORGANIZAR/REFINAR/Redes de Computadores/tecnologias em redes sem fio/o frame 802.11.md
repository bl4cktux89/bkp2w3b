### Objetivo:

Neste tópico vamos analisar o formato do frame 802.11 responsável pela comunicação das redes wireless. Estudaremos todos os detalhes e as diferenças básicas em relação ao frame 802.3 utilizado nas redes cabeadas.

### Introdução

O modelo de referência OSI foi criado para orientar os fabricantes de hardware a seguir um padrão de desenvolvimento para a construção de sistema e equipamentos tais como: computadores e seus acessórios. Hoje, todo e qualquer equipamento que se conecte a uma rede segue este padrão, formado por sete camadas, como podemos verificar abaixo:

Camada 7 – Camada de aplicação

Camada 6 – Camada de apresentação

Camada 5 – Camada de sessão

Camada 4 – Camada de transporte (onde é encontrado o protocolo TCP)

Camada 3 – Camada de rede (onde é encontrado o protocolo IP)

Camada 2 – Camada de enlace (onde é encontrado o protocolo Ethernet)

Camada 1 – Camada física

Cada uma destas camadas possui designações bem distintas fornecendo serviços à camada inferior e à superior. Por exemplo: a camada 3, que é a responsável pela formação do pacote IP e da designação do endereçamento dos hosts de origem e destino e é por seu intermédio que conseguimos enviar pacotes para hosts que estão fora da nossa rede.

Como as redes wireless também são sistemas de conexão de equipamentos em uma rede que não utiliza cabos é mais que obvio que esta tecnologia também siga as recomendações do modelo de referência OSI descrito acima.

Os sistemas wireless utilizam praticamente todas as camadas do modelo OSI, porém nas duas camadas inferiores temos certas divergências se comparadas às camadas utilizadas nas redes cabeadas, são elas: a camada física e a camada de enlace. (MEDEIROS, 2010)

### Camada Física

A camada física é a responsável pela transmissão dos quadros por um canal de comunicação. Este canal nas redes padrão 802.3 são os cabos UTPs e nas 802.11 são as ondas de rádio. O padrão 802.11 de 1997 define três técnicas de transmissão para as redes wireless: uma utilizando infravermelho e outras duas utilizando métodos de RF (Radiofrequência): o FHSS _**(Frequency Hopping Spread Spectrum)**_ e o DSSS _**(Direct Sequence Spread Spectrum).**_

Em 1999, foi apresentado mais uma nova técnica para alcançar maior largura de banda: o OFDM _**(Orthogonal Frequency Division Multiplexing),**_ conforme já estudamos em tópicos passados.

Na camada física que encontramos os transmissores de rádio e seus respectivos moduladores.

### Camada de Enlace

Imediatamente acima da camada física encontra-se a camada de enlace onde nas especificações do protocolo 802.11 são definidas duas subcamadas: a camada LLC _**(Logical Link Control)**_ e a camada MAC _**(Media Access Control).**_

### Subcamada LLC

A subcamada LLC tem como função básica ocultar as diferenças entre as variações do 802 e torna–lá indistinguíveis no que se refere à camada de rede, isto é, ela trabalha como um tradutor entre quadros 802.11 das redes sem fio para quadros 802.3 das redes cabeadas, provendo assim, um único formato e uma única interface com a camada 3 de rede.

Esta subcamada fornece três opções de serviço: serviço de quadros não–confiável, serviço de quadros com confirmação e serviço confiável orientado a conexões.

O cabeçalho LLC possui três campos: um ponto de acesso de destino, um ponto de acesso de origem e um campo de controle (número de sequência e confirmação).

### Subcamada MAC

A subcamada MAC determina como o canal é alocado, isto é, qual terá a oportunidade de transmitir o frame no espaço, devendo este ser compatível com o padrão _**Ethernet**_ utilizado nas redes cabeadas. No _**Ethernet**_ o protocolo empregado é o CSMA/CD _**(Carrier Sense Multiple Access/Collision Detection),**_ o qual necessita que os rádios estejam habilitados a enviar e receber ao mesmo tempo.

Isto não é possível nas redes sem fio, pois os rádios utilizam o processo _**halfduplex,**_ o que significa que não podem transmitir e receber dados ao mesmo tempo em uma única frequência. Também não há como garantir que todas as estações estejam aptas a "escutar" as outras, o que pode causar os problemas da estação oculta e da estação exposta.

Assim, o padrão 802.11 utiliza o protocolo CSMA/CA _**(Carrier Sense Multiple Access/Collision Avoidance),**_ uma variante do CSMA/CD. Na resolução desses problemas, a subcamada MAC emprega dois modos de operação: um conhecido como DCF _**(Distributed Coordination Function**_ – função de coordenação distribuída) e o outro chamado de PCF _**(Point Coordination Function**_ – função de coordenação de ponto). Todos os rádios desenvolvidos devem aceitar a função de DCF, porém o PCF é função opcional e é encontrado apenas em alguns modelos. O modo DCF não utiliza nenhuma espécie de controle central e tem o protocolo CSMA/CA, no qual são usados os métodos de detecção do canal físico e do canal virtual.

No primeiro método, quando uma estação for efetuar uma transmissão, ela detecta o canal de frequência e se este estiver ocioso, a estação começará imediatamente a transmitir. Se o meio estiver ocupado, a transmissão será adiada até o canal ficar disponível. No caso de haver uma colisão, as estações envolvidas terão de esperar um tempo aleatório, determinado por um algoritmo e podendo fazer novas tentativas posteriormente.

O método de verificação da ociosidade do canal é feito através do algoritmo de verificação da nitidez conhecido como CCA – _**Clear Channel Assessment**_ - que através de amostragem da energia coletada na antena do rádio pode se determinar se o canal está livre.

No método PCF o controle da transmissão é feito pelo _**Acess Point**_, que efetua o _**polling**_ das outras estações, verificando se elas têm algum quadro a enviar. Este método é altamente seguro, pois apenas uma estação irá transmitir o que resultará em um índice de colisões e paralisações da rede a nível zero.

Tanto o método DCF quanto o PCF trabalham a detecção do canal físico, mas também temos a detecção do canal pela metodologia virtual, através do protocolo RTS/CTS _**– Request to Send e Clear to Send.**_

### _Request to Send and Clear to Send –_ RTS/CTS

O mecanismo RTS/CTS foi criado na perspectiva da redução das colisões nas redes wireless pela reserva do canal para a transmissão dos frames pelas estações. O seu funcionamento consiste em:

- Uma estação que deseja transmitir um dado qualquer procura primeiramente através do algoritmo CCA se o meio (espaço) está ocioso.
- Encontrando o meio ocioso, ela envia à estação destino um frame RTS que por sua vez responderá à estação origem com um frame CTS.

Ambos os frames contém o campo _**“Duration/ID”,**_ que define o período de tempo necessário para o envio dos dados e o retorno da estação que os recebeu por um ACK - _**Acknowledge**__**,**_ que é a confirmação positiva do recebimento do frame. Para cada frame transmitido por uma rede wireless é necessário a confirmação do recebimento deste através do ACK positivo, ou seja, o frame chegou intacto no receptor ou de um NAC – _**Negative Acknowledge**_ que informa se o frame chegou corrompido.

Como os frames RTS e CTS viajam pelo meio, todas as outras máquinas no raio de alcance desta rede wireless também irão detectar este frame e adiarão suas transmissões pelo mesmo período de tempo fornecendo assim o espaço livre e sem riscos de colisões.

O tempo que cada máquina vai adiar suas transmissões é conhecido como NAV – _**Network Allocation Vetor**_, que manterá uma previsão de duração de tráfego pela rede baseado nas informações contidas no campo supra mencionado _**“Duration/ID”.**_

O protocolo RTS/CTS pode ser opcional em alguns modelos de Access Point, e nestes modelos além de existir a possibilidade do desligamento desta função, tem-se ainda a opção de uma segunda função que é conhecida como _**“On With Threshold”**_ – OWT que permitirá a configuração da ativação da função RTS/CTS somente com valores pré-estabelecidos do tamanho dos pacotes, por exemplo: deseja-se apenas ligar a função RTS/CTS com pacotes de VoIP e não para os demais pacotes, melhorando assim a eficiência da rede. (SANTOS JUNIOR, 2005)

### Quadros 802.11

O padrão 802.11 define três diferentes tipos de quadros: Quadros de dados, quadros de controle e quadros de gerenciamento. Cada um deles possui um cabeçalho com uma variedade de campos usados na subcamada MAC conforme ilustrado na figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/3/292303/18202.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/3/292303/18202.jpg)

Figura 1 - Frame 802.11

A descrição de cada campo que forma o quadro 802.11 é mostrado a seguir:

- Controle de quadro com 2 bits: Este campo possui 11 subcampos, divididos da seguinte forma:

- Versão do protocolo com 2 bits: Que permite a operação de duas versões do protocolo ao mesmo tempo na mesma célula.
- Campo Tipo com 2 bits: Dados, Controle ou Gerenciamento).
- Campo Subtipo com 4 bits: Indicando quadros de RTS ou CTS.
- Os bits Para DS e De DS: Indicam se o quadro está indo ou vindo do sistema de distribuição entre as células.
- O bit MF: Significa que haverá mais fragmentos.
- O bit Repetir: Indica a retransmissão de um quadro enviado anteriormente.
- O bit Potência: É usado pelo ponto de acesso para deixar ou retirar o receptor do estado de espera.
- O bit Mais: Indica que o transmissor tem quadros adicionais para o receptor.
- O bit W: Especifica que o corpo de quadro foi criptografado com algoritmo WEP _(Wired Equivalent Privacy)._
- O bit O: Informa ao receptor que uma sequência de quadros com este bit terá que ser processada em ordem.
- _**Duration/ID**_ com 2 bytes: Este campo informa por quanto tempo o quadro e sua confirmação ocuparão o meio (espaço).
- Quatro campos de endereço com 6 bytes cada um: Contém os endereços de origem e destino do quadro, e de origem e destino do ponto de acesso.
- Sequência com 2 bytes: Este campo permite que os fragmentos sejam numerados. Doze bits identificam o quadro e quatro identificam o fragmento, totalizando dezesseis bits disponíveis.
- Dados: Este campo contém a carga útil de até 2.312 bytes.
- Total de verificação com 4 bytes: É realizado pela camada MAC da estação transmissora que calcula uma sequência de 32 bits para a verificação do frame usando um código de redundância cíclica, CRC - _**Cyclic Redundancy Code**_ o resultado é colocado no final do frame com o objetivo de que a estação receptora verifique se o frame chegou livre de erros.

### Revisão

O protocolo utilizado pelas redes wireless para acesso ao meio é o CSMA/CA.

O CSMA/CA verifica o meio e através da medição da nitidez do canal, ele habilita a estação a transmitir.

Para auxiliar o protocolo CSMA/CA, foi desenvolvido o protocolo RTS/CTS que faz uma reserva do meio antes de qualquer transmissão para que sejam evitadas as colisões.

Para cada frame transmitido é necessário um reconhecimento de pacote recebido sem erros através do ACK