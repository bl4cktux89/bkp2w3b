Esta experiência tem como objetivo apresentar uma rede local afetada por um ataque de negação de serviço (Denial of Service -DoS), baseado no envio de falsas mensagens NA, para que este possa ser analisado. Nesse cenário, a máquina n3Faker responderá a todas as requisições NS, informando ser o portador do endereço IPv6 verificado pelo processo de Duplicate Address Detection (DAD) e impedindo que novas máquinas obtenham conectividade. Na sequencia, o software NDPMon será utilizado para demonstrar como este tipo de ataque pode ser detectado. Para o presente exercício será utilizada a topologia descrita no arquivo: 3-01-DoS-NA.imn.

**COMO OBTER OU TER ACESSO AO LIVRO LABORATÓRIO DE IPV6: APRENDA NA PRÁTICA USANDO UM EMULADOR DE REDES DO NICBR**

Este laboratório faz parte do livro Aprenda na prática usando um emulador de redes do NicBr.

Para a realização deste exercício será utilizada a topologia descrita no arquivo: 3-01-DoS-NA.imn. que está disponível no site do NicBR, gratuitamente.

Siga os procedimentos indicados e vamos praticar !

Para saber mais, acesse faça o Download das máquinas virtuais e do livro em http://ipv6.br/pagina/livro-ipv6/

Ou ainda disponível, na versão física, em uma das Bibliotecas dos Campis da Universidade Uninove ! Confira !Venha nos visitar !

### Introdução

Uma das principais funções do NDP ( Neighbor Discovery Protocol) é a descoberta de vizinhança, que facilita a autoconfiguração e comunicação entre dispositivos da rede. Dentre essas funções o estabelecimento de endereços Mac-address ( endereços físicos) dos dispositivos vizinhos, a identificação dos endereços IP duplicados e a localiação dos roteadores em uma rede. A maneira como essas funções são desempenhadas,  apresentam-se através de mensagens ICMPv6. Santos, Moreiras (2015)

De modo similiar ao seu antecessor, o IPV4, usuários mal intencionados podem realizar ataques à rede IPV6 ou usuários que compartilham o barramento da rede. Como exemplo, pode-se citar a funcionalidade DAD (Duplicate address detection). A DAD verifica de um determinado endereço IP já está sendo utilizado por um outro dispositivo na rede, nesse caso, o dispositivo envia uma mensagem Neighbor Solicitation (NS) para validação do endereço IP e dessa forma, evitar duplicação de IPs, através da solicitação Neighbor Advertisement (NA), uma vez que a solicitação ( NA) informa que um dispositivo já utiliza esse endereço, impedindo os demais dispositivos da rede de receberem IPs duplicados. Santos, Moreiras (2015)

O DoS (**denial-of-service**) ou negação de serviços, que ataca essa funcionalidade, sendo esse um método que hackers utilizam para que um dispositivo infectado passe a responder a mensagens Neighbor Solicitation (NS) enviadas em uma rede, mesmo que não sejam enviadas ou destinadas a esse dispositivo, informando qualquer endereço IPv6 validado pelo DAD (Duplicate address detection). Impossibilitando que novos dispositivos possam obter um endereço válido e feche a conexão. Santos, Moreiras (2015)

Roteiro experimental

1. Inicie o CORE e abra o arquivo 3-01-DoS-NA.imn localizado no diretório lab, dentro do Desktop. A topologia de rede, representada pela Figura 3.1,deve aparecer.O objetivo dessa topologia de rede é representar o mínimo necessário para que o ataque seja analisado.

inicialize a simulação e verifique a configuração de endereços IPv6 nos nós n1Host, n2Host e n3Faker.Ao contrário de outras experiências, não atribuímos endereços unicast globais às interfaces de rede, pois o processo será realizado utilizando somente os endereços unicast link-local. O processo de DAD é realizadopara toda atribuição de endereços IPv6.

3. Abra um terminal de n1Host, com um duplo-clique e execute um ping6 para o n2Host:

![[Untitled 28.png|Untitled 28.png]]

# ping6 -c 4 -I eth0 fe80::200:ff:feaa:1

O resultado do comando é representado pela Figura 3.2.

![[Untitled 1 18.png|Untitled 1 18.png]]

4. Em paralelo, efetue:

(a) A coleta dos pacotes trafegados na interface eth0 de n3Faker. As instruções de coleta de pacotes utilizando tcpdump ou Wireshark se encontram no Apêndice C.(b) Efetue os seguintes passos enquanto a coleta é realizada:i. Abra outro terminal de n3Faker com um duplo-clique e utilize o seguinte comando para realizar o ataque:# dos-new-ip6 eth0O dos-new-ip6 é um executável que pertence ao pacote THC-IPv6. Este pacote é uma ferramenta desenvolvida para detectar vulnerabilidades de segurança do IPv6 e do ICMPv6. O dos-new-ip6 atua escutando todos os endereços multicast solicited-node e respondendo as consultas do DAD informando que todos os endereços testados estão em uso, gerando um ataque de DoS.ii. Abra um terminal de n1Host, desative a interface de rede eth0 e ative-a para verificar a negação de serviço:

# ip link set eth0 down# ip link set eth0 up# ip addr show eth0# ifconfig eth0

O resultado dos comandos é representado pela Figura 3.3.

![[Untitled 2 16.png|Untitled 2 16.png]]

Mediante esta sequência de comandos, a interface eth0 efetua o procedimento de DAD para a obtenção de endereço IPv6 de link-local. Note que o resultado do comando ip addr show eth0 indica que não houve a atribuição do endereço por meio do texto tentative dadfailed. Em paralelo, o comando ifconfig eth0 não indicou qualquer tipo de falha durante a atribuição de endereço IPv6.

O resultado em n3Faker da execução de dos-new-ip6 é representado pela Figura 3.4.

![[Untitled 3 10.png|Untitled 3 10.png]]

iii. Ainda no terminal de n1Host, verifique novamente a conectividade com n2Host:

# ping6 -c 4 -I eth0 fe80::200:ff:feaa:1

O resultado do comando é representado pela Figura 3.5.

![[Untitled 4 10.png|Untitled 4 10.png]]

Note que tal comando confirma que o endereço unicast link-local não foi atribuído à interface eth0 de n1Host.

iv. No terminal de n3Faker, encerre o comando dos-new-ip6 por meio da sequência de teclado Ctrl+C.

5. Efetue a análise dos pacotes coletados na interface eth0 de n3Faker. Aplique o filtro icmpv6 no Wireshark e procure pelos pacotes NS e NA. O pacote NS enviado por n1Host foi recebido por n3Faker. Como resposta à mensagem, n3Faker enviou pacotes NA ao n1Host para informar que o endereço IPv6 unicast link-local fe80::200:ff:feaa:0 já está sendo utilizado, apesar do endereço IPv6 unicast link-local de n3Faker serfe80::200:ff:feaa:2, conforme verificado no passo 2.

O comportamento de n3Faker, por meio do comando dos-new-ip6, gera uma negação de serviço, pois impede que qualquer dispositivo que venha a pertencer ao enlace consiga ativar sua interface de comunicação.Este ataque poderia ser evitado com a utilização da suíte de protocolos SEND (Secure Neighbor Discovery), descrito na RFC 3971.  Entretanto, durante o desenvolvimento desta experiência, aindanão existia uma implementação funcional para Linux.Nos próximos passos, o NDPMon, uma ferramenta para a geração de logs e registros de comportamentos suspeitos no enlace, será utilizada para auxiliar na detecção de ataques e na identificação de máquinas atacantes.6. Encerre a simulação,, e inicialize novamente a simulação.

7. Abra um terminal de n3Faker, com um duplo-clique e efetue o ataque denegação de serviço. No terminal execute o comando:# dos-new-ip6 eth0

8. Abra um terminal de n2Host, com um duplo-clique, e inicie o monitoramento por meio do NDPMon. Para isto o seguinte comando deve ser executado:# ndpmon -i eth0 -v

9. Abra um terminal de n1Host, desative a interface de rede eth0 e ative-a para verificar a negação de serviço:# ip link set eth0 down# ip link set eth0 up# ip addr show eth0

Após a execução deste procedimento, analise o resultado do monitoramento do enlace realizado em n2Host. O log gerado pelo NDPMon indica, por meio da linha [monitoring_na] New Ethernet DAD DoS, que ocorreu umataque de negação de serviço no processo de detecção de endereço duplicado.

Também é possível analisar qual endereço sofreu a negação de serviço verificando o campo Target Address da mesagem NA capturada pelo NDPMon.

A Figura 3.6 representa o log gerado pelo NDPMon. Note que esta figura apresenta apenas parte das informações geradas, visto que seu conteúdo é muito extenso.

O NDPMon também pode ser configurado para alertar em caso de detecção de ataques. Por exemplo, por meio do envio de e-mails, permitindo uma rápida ação dos administradores de rede para mitigar os problemascausados. Santos, Moreiras (2015)

![[Untitled 5 9.png|Untitled 5 9.png]]

10. Encerre a simulação.