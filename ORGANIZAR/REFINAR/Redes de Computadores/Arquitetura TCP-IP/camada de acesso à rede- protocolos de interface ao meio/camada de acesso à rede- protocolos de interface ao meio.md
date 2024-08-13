![[Untitled 32.png|Untitled 32.png]]

### **Introdução**

Os nós de uma rede, tais como, roteadores switches, etc. são interligados por de canais de comunicação que transportam os **datagramas** (porção de dados originais) de um hospedeiro de origem até um hospedeiro de destino. O **datagrama** tem que ser transportado por meio de cada um dos enlaces individuais, como mostrado na figura acima. Cada nó dessa rede encapsula o **datagrama** da camada de rede no que é chamado de **quadro** da camada de enlace e o transmite para dentro do enlace.

### Protocolos e serviços da camada de enlace

O protocolo da camada de enlace define o formato do quadro trocado entre as extremidades nós de cada enlace, bem como as ações detecção de erros, retransmissão, controle de fluxo e controle de acesso ao meio de transmissão. Como exemplo de protocolos da camada de enlace podemos citar os protocolos para rede locais: Ethernet utilizados em redes cabeadas; e 802.11 (a, b, g, n e ac) utilizado em redes wireless. Além dos protocolos PPP (point-to-point protocolos) e Frame-relay utilizados em redes WAN (redes de longa distância).

Enquanto que a camada física é responsável pela representação elétrica ou óptica dos dados provenientes das camadas de enlace, um protocolo da camada de enlace é responsável por movimentar os dados por um único enlace no caminho. Isso quer dizer os dados que saem do seu computador podem passar por diferentes protocolos da camada de enlace em cada enlace ao longo do caminho. Por exemplo, você pode estar conectado a uma rede wireless 802.11 até o roteador/modem da operado de telecomunicações e na sequência utilizar o padrão ADSL (**A**symmetric **D**igital **S**ubscriber **L**ine - Linha Digital Assimétrica) por meio da linha telefônica até a operada de telecomunicação. Outros padrões de rede da camada de enlace são mostrados na tabela 1.

![[Untitled 1 22.png|Untitled 1 22.png]]

![[Untitled 2 20.png|Untitled 2 20.png]]

### Funções da camada de Enlace

Embora o serviço básico da camada de enlace seja mover os datagramas de um nó ao outros, os serviços de cada protocolo podem variar de um para o outro. Entre os possíveis serviços que podem ser implementados por protocolos da camada de enlace são:

- **Enquadramento dos dados:** Quase todos os protocolos da camada de enlace encapsulam os datagramas provenientes da camada de rede dentro de um quadro na camada de enlace antes de transmiti-lo pelo enlace, conforme mostrado na figura 2 e detalhado na figura 3. As informações contidas nesse quadro podem incluir os campos de início e fim de quadro, corresponde a uma sequência binária que permite a placa de rede do receptor identificar que acabou de chegar um quadro ou que o mesmo terminou.

![[Untitled 3 14.png|Untitled 3 14.png]]

Acesso ao Enlace: Um protocolo de acesso ao meio de transmissão (MAC – Media Access Control) especifica as regras com as quais os quadros serão transmitidos pelo enlace. Em enlaces ponto-a-ponto (transmissor e receptor únicos) a utilização do MAC é simplificada ou inexistente. Em redes multiacesso, quando vários nós compartilham um único enlace de broadcast – o denominado problema de acesso múltiplo, conhecido também colisão.

![[Untitled 4 14.png|Untitled 4 14.png]]

Entrega Confiável: Nem sempre um protocolo da camada de enlace fornece o serviço de entrega confiável, muitas vezes essa funcionalidade é implementada por protocolos da camada de transporte (como TCP). A entrega confiável na camada de enlace ocorre principalmente em transmissões altas taxas de erro, como em enlaces sem fio e via satélite mostrado na figura abaixo. Por outro lado, a implementação de confiabilidade na camada de enlace pode ser considerada desnecessária em enlaces de baixa taxa de erros como, por exemplo, enlaces de fibra e algumas aplicações que requerem cabos par-trançados, abaixo. Neste caso, a confiabilidade ficará a cargo dos protocolos de camada superior.

![[Untitled 5 13.png|Untitled 5 13.png]]

- **Controle de Fluxo:** Muitas vezes quando você está conversando com uma pessoa que fala muito rápido é necessário pedir para que ela fale mais devagar, justamente para que você possa compreender perfeitamente o que a pessoa diz. O mesmo é implementado em alguns protocolos da camada de enlace de dados com o objetivo de evitar que o remetente sobrecarregue o destinatário com uma quantidade de quadros que impossível de ser processado. Sem esse controle de fluxo, o buffer pode transbordar e os quadros podem ser perdidos. De forma semelhante, esse mecanismo também é implementado na camada de transporte.
- **Detecção de Erro:** problemas de leitura com o hardware da camada de enlace podem ser provocados por interferência eletromagnética e atenuação levando o receptor a interpretar um bit 1 como 0 e vice-versa. Para evitar que dados contendo erros sejam repassadas as camadas superiores, o transmissor introduz bits de detecção de erros o que obriga o receptor a executar a verificação de erros. Esse mecanismo também pode ser implementado na camada de transporte, entretanto, normalmente, a implementação na camada de enlace pode ser mais sofisticada e implantada em hardware.
- **Half-duplex e Full-duplex:** Em uma transmissão do tipo full-duplex, dois nós pedem enviar e receber quadros simultaneamente, enquanto que na half-duplex esse processo ocorre nas duas direções, mas não simultaneamente.

![[Untitled 6 9.png|Untitled 6 9.png]]

### Protocolos de acesso Ponto a Ponto e Multiponto

Os protocolos de acesso ao meio de transmissão podem ser divididos em duas classes: Protocolos de acesso Ponto-a-Ponto e Multiponto. Os protocolos do tipo ponto a ponto consistem em um único remetente e um único receptor na outra extremidade do enlace, como é o caso dos protocolos PPP (point to point) e HDLC. O segundo tipo, conhecido como multiponto ou enlace em broadcast, permite que um único enlace seja compartilhado por muitos nós, como é o caso das transmissões em rede LAN (com o protocolo Ethernet) e das transmissões de TV que utilizam esse modo de propagação desde que foi inventada.

O problema associado aos protocolos de acesso múltiplo está em controlar o acesso a meio de comunicação com o objetivo de evitar o que é chamado de colisão. Nesse tipo de transmissão dois nós podem enviar simultaneamente por meio do canal. Em redes Ethernet cabeadas ou sem fio utilizam o **CSMA/CD** _**Carrier Sense Multiple Access**_ with Collision Detection ou Acesso múltiplo com detecção de portadora  e detecção de colisão**),** mostrado na figura abaixo, e **CSMA/CA (**_**Carrier Sense Multiple Access**_ collision avoidance ou Acesso múltiplo com detecção de portadora com anulação/prevenção de colisão) , respectivamente.

![[Untitled 7 8.png|Untitled 7 8.png]]

O conceito básico por traz do **CSMA/CD** é a capacidade de uma estação detectar uma colisão enquanto transmite. Quando não uma colisão, a estação recebe apenas o seu próprio sinal. Entretanto, quando há uma colisão, a estação recebe o seu próprio sinal e o sinal de uma segunda estação. Neste caso, a intensidade do sinal é superior a transmissão sem colisão.

Em redes com fio, o sinal recebido tem praticamente o mesmo nível de energia do que o enviado, já que o comprimento do cabo é pequeno, no máximo, 100 metros ou existem repetidores que amplificam a energia entre o emissor e o receptor. Isso significa que, em caso de colisão, a energia praticamente dobra. No entanto, para uma rede sem fio, a maior parte da energia é perdida durante a transmissão. Portanto, o sinal recebido possui muito pouca energia. Se tivéssemos uma colisão em redes sem fio, 5% a 10% de energia é adicionada, não sendo suficiente para ser detectada e caracterizada como colisão.

Em redes sem fio, em vez detectar uma colisão, precisamos evita-la. Para tanto foi criado o CSMA/CA, que utiliza as estratégias de espaçamento entre frames, janela de contenção e confirmação, conforme mostrado na figura abaixo, para que a transmissão possa ser efetivada com sucesso (Forouzan, B. A. 2010).

![[Untitled 8 8.png|Untitled 8 8.png]]

- **Espaçamento entre frames (IFS):** Mesmo com o canal ocioso, a transmissão é postergada, evitando dessa forma que uma estação envie dados imediatamente. A estação aguarda por um certo período de tempo, chamado espaço entre frames (Interframe space – IFS). Mesmo determinando que o canal esteja ocioso, uma outra estação pode já ter iniciado uma transmissão, mas que ainda não atingiu a outra estação que também deseja transmitir. Por isso, a estação precisa aguardar um tempo igual ao tempo de contenção, descrito a seguir. O IFS pode ser utilizado também para determinar a prioridade de uma estação.
- **Janela de contenção:** define um intervalo de tempo dividido em slots. A estação que já está pronta para transmitir escolho o slot de tempo randômico de acordo com algoritmo de recuo exponencial binário. Isso quer dizer que a estação configura um slot de tempo na primeira vez e, na sequência, vai dobrando cada vez que a estação não é capaz de detectar um canal ocioso após o IFS. Esse mecanismo permite que uma estação que detecta que o canal esteja ocupado, não precise reiniciar o processo, simplesmente para o time e o reinicia quando percebe que o canal está ocioso. Isso dá prioridade à estação com maior tempo de espera.
- **Confirmação:** Mesmo com todos os mecanismos anteriormente apresentados, ainda pode ocorrer colisões. A confirmação positiva pelo host receptor garante que o frame não foi corrompido ou que não foram destruídos durante a colisão (Forouzan, B. A. 2010).

A figura abaixo ilustra o processo. Observe que o canal precisa ser “escutado” antes e após o IFS e também durante o tempo de contenção. Em cada time slot da janela de contenção, o canal é “escutado”.  Se for constatado a ociosidade, o timer continua. Se o canal estiver ocupado, o timer é interrompido e continua após o canal se tornar ocioso novamente.

![[Untitled 9 7.png|Untitled 9 7.png]]