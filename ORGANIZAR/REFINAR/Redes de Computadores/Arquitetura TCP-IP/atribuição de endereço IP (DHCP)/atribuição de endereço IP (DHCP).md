### DHCP

O DHCP (Dynamic Host Configuration Protocol – Protocolo de configuração de dinâmica de Host) é uma aplicação do tipo cliente-servidor protocolo que tem por função básica atribuir ou conceder endereços IPs automaticamente as estações de trabalho de uma rede que possuam a função DHCP habilitada. Imagine que você tenha uma rede grande com centenas ou milhares de computadores e que você precisa atribuir as configurações TCP/IP para cada cliente. Essa tarefa poderia se tornar extremamente trabalhosa e passível de erros de configuração. Por esse motivo a atribuição de endereço de forma automática se torna extremamente vantajosa. Mas nem sempre é conveniente atribuir endereços IPs de forma automática, principalmente para os roteadores e servidores. Neste caso devemos atribuir o endereço de forma estática.

Além da atribuição dos endereços IPs de rede, o servidor DHCP fornecerá também a máscara de rede, gateway padrão, DNS e WINS. Ainda é possível as seguintes configurações em um servidor DHCP (Microsoft Corp., 2017):

- Conceder endereços IP por um tempo específico aos clientes DHCP e, em seguida, renovar automaticamente os endereços IP quando o cliente solicitar uma renovação.
- Atualizar automaticamente os parâmetros de cliente DHCP, alterando uma opção de servidor ou escopo no servidor de protocolo DHCP, em vez de fazer isso individualmente em todos os clientes DHCP.
- Reservar endereços IP para computadores específicos ou outros dispositivos, de forma que eles sempre tenham o mesmo endereço IP e também recebam as opções DHCP mais atualizadas.
- Excluir endereços IP ou intervalos de endereços da distribuição feita pelo servidor de protocolo DHCP, para que esses endereços IP e intervalos possam ser usados para configurar estaticamente os servidores, os roteadores e outros dispositivos que exigem endereços IP estáticos.
- Fornecer serviços DHCP para várias sub-redes, se todos os roteadores entre o servidor de protocolo DHCP e a sub-rede para a qual deseja fornecer serviço estiverem configurados para encaminhar mensagens DHCP.
- Configurar o servidor de protocolo DHCP para executar serviços de registro de nome DNS para clientes DHCP.
- Fornecer atribuição de endereços multicast a clientes DHCP baseados em IP.

### Métodos de alocação de endereços

Existem basicamente três métodos para atribuição de endereços utilizando o serviço DHCP que pode ser utilizado dentro de uma rede, conforme mostrado abaixo. É comum encontrarmos diferentes métodos de alocação de endereços. A forma de alocação vai depender do porte da organização, política de segurança e serviços que estão sendo ofertados na rede (Kurose, James F e Ross, 2013).

- Alocação manual: Este tipo de alocação associa o endereço **MAC do dispositivo cliente com o endereço IP a ser alocado**. O endereço é atribuído pelo administrador da rede durante a configuração.
- Alocação automática: O DHCP atribui automaticamente o endereço **IP estático permanentemente sem arrendamento** para host dentro de um _**pool**_ (faixa de endereço a ser distribuída ou escopo).
- Alocação dinâmica: A alocação dinâmica é a mais comum forma de distribuição de endereços IPs. Neste caso o endereço IP pertencente a um pool de endereços do servidor é arrendado por um período de tempo determinado chamado de _**lease time**_. O cliente ficará com o endereço até que expire a concessão e ele solicite uma renovação ou caso o cliente seja desligado. Caso o tempo de alocação do endereço expire e o cliente não consiga renovar a sua concessão, o cliente continuará tentando contatar o servidor via mensagem de broadcast.

**Endereço APIPA**

Caso um servidor esteja indisponível na rede, o próprio cliente atribui automaticamente para si um endereço dentro da faixa do 169.254.x.y. Isso pode ocorrer em caso de problemas com a configuração do servidor DHCP ou o cliente não consegui encontrar o servidor DHCP para iniciar a negociação. Pode ocorrer de não existir mais endereços disponíveis no Pool para ser disponibilizado (Microsoft Corp., 2017).

### Processo de atribuição de endereço

Nas solicitações DHCP, a porta de origem (cliente) é a UDP 68, enquanto que a porta de destino (servidor) é a porta 67, com endereço MAC e IP setados com o MAC de A e 0.0.0.0, respectivamente. Observe que o endereço MAC de destino é setado com FF-FF-FF-FF-FF-FF, já que o cliente ainda não conhece o servidor DHCP que responderá a sua solicitação. No campo DHCPDISCOVER, correspondente à camada de Aplicação, os endereços estão setados em 0.0.0.0, pois, novamente, é justamente o que o cliente precisa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/1/1632173/39072.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/1/1632173/39072.png)

Fonte: Cisco Systens

Quando um dispositivo com DHCP ativado é inicializado ele passa por seis estados de aquisição de endereço, conforme detalhado abaixo (Bugallo, A. M. et. al, 2017):

- **INICIALIZA:** Ao inicializar pela primeira vez, o cliente difunde na rede uma mensagem em broadcast para todos os possíveis servidores DHCP por meio de uma mensagem **DHCPDISCOVER** **em um datagrama UDP. Após o envio, o cliente passa para o estado Seleciona.**
- **SELECIONA:** Neste estado o cliente continua aguardando a resposta dos servidores DHCP que receberam o **DHCPDISCOVER**. Os servidores habilitados a responder solicitação DHCP enviam ao cliente uma mensagem **DHCPOFFER**. Nesta mensagem estão embutidas as informações necessárias para a configuração do cliente e o endereço IP do servidor DHCP que o oferece como empréstimo. Depois de receber as mensagens de todos os servidores DHCP, o cliente optará por uma e enviará uma mensagem **DHCPREQUEST**, entrando na sequência, no estado **SOLICITA**.
- **SOLICITA:** Nesse estado o cliente aguarda uma confirmação à mensagem **DHCPREQUEST**. Essa resposta é remetida por meio de uma confirmação **DHCPACK.** A partir desse instante o cliente passa a ter e utilizar um endereço IP e todas as outras informações que foram enviadas pelo servidor. Na sequência o cliente entra no estado **LIMITE**. O processo de aquisição de endereços IPs é resumido na figura abaixo (do estado **INICIALIZA** até **LIMITE**).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/1/1632172/39054.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/1/1632172/39054.png)

- **LIMITE:** O cliente, agora, permanece no estado **LIMITE** **até que a sua concessão vença ou que ele solicite que a concessão seja renovada, ou seja, liberando o endereço IP alocado. A partir de desse instante o cliente não pode mais enviar mensagens na rede usando o endereço IP anteriormente fornecido.**
- **RENOVA:** Ao receber a mensagem **DHCPACK****,** o cliente adquiri a informação do período de locação do endereço. Com essa informação, ele três temporizadores utilizados para controlar os períodos de renovação. Quando o temporizador ultrapassa o valor de renovação, o cliente tentará renovar a concessão. Para tanto, ele envia novamente uma mensagem **DHCREQUEST** ao servidor, passando assim para o estado **RENOVA** e aguarda resposta. Nessa mensagem segue embutido o endereço IP atual e uma extensão para o mesmo. O servidor poderá renovar ou negar a solicitação. Caso o servidor renove a alocação, enviará um **DHCPACK** ao cliente. Recebendo essa mensagem o cliente retorna ao estado **LIMITE.** No segundo caso, o servidor envia um **DHCPACK** informando para o cliente interromper o uso do endereço IP e passe para o estado **INICIALIZA.**
- **VINCULA NOVAMENTE:** Ao entrar no estado **RENOVA**, cliente aguarda a resposta do servidor. Caso a resposta não chegue (O servidor pode estar desligado ou desconectado), o cliente permanece nesse estado, utilizando normalmente a rede, até que seja ultrapassado o limite do segundo temporizador. Nesse ponto, o cliente passa do estado **RENOVA** para o estado **VINCULA NOVAMENTE****.** A partir desse instante o cliente pressupõe que o servidor que originalmente forneceu o endereço IP já não esteja mais disponível e tentar obter a renovação com qualquer outro servidor que responda a solicitação broadcast **DHCPREQUEST. Caso recebe um DHCPACK** de algum servidor habilitado, o cliente retornará ao estado **LIMITE.** Caso receba um **DHCPNACK****,** ele entrará para o estado **INICIALIZA.** Se o cliente não receber qualquer resposta, ele permanecerá utilizando o endereço IP inicialmente locado até que seja atingido o valor limite do terceiro temporizador, fazendo com que ele passe para o estado **INICIALIZA** (Bugallo, A. M. et. al, 2017)**.**

### Formato da mensagem DHCP

A figura abaixo mostra o formato da mensagem DHCP. Por meio dessa mensagem também é possui responder solicitações do tipo BOOTP (Bootstrap Protocol, protocolo de inicialização). O BOOTP permite a alocação automática do endereço IP, ou seja, atribui automaticamente um endereço IP de forma permanente, entretanto, incapaz de alocar endereços IPs de forma dinâmica.

![[Untitled 39.png|Untitled 39.png]]

### Simulação 1 - Configuração do serviço DHCP em um servidor

A simulação que segue mostrará configuração do serviço DHCP no servidor do simulador Packet Tracer. Nessa simulação veremos:

- Configuração do escopo DHCP;
- Endereço IP APIPA;
- Encaminhamento de broadcast via comando _**ip helper-address**_

Vídeo Configuração do serviço DHCP em um servidor:

[**https://drive.google.com/file/d/1PuHy6_n9jr9pbk_kt6Yi0cM5WW5PAknh/view?usp=sharing**](https://drive.google.com/file/d/1PuHy6_n9jr9pbk_kt6Yi0cM5WW5PAknh/view?usp=sharing)

### Simulação 2 - Configuração do serviço DHCP em um roteador

A simulação a seguir veremos a configuração do serviço DHCP no roteador Cisco.

Vídeo Configuração do serviço DHCP em um roteador:

[**https://drive.google.com/file/d/15P9naIL2oBrW8KwUhcQpa73NBWCg5b-Y/view?usp=sharing**](https://drive.google.com/file/d/15P9naIL2oBrW8KwUhcQpa73NBWCg5b-Y/view?usp=sharing)