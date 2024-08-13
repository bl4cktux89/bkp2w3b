[![](https://ampli-images.s3.amazonaws.com/production/c212f192-342d-44e0-a7a9-b57160c04ef3/original)](https://ampli-images.s3.amazonaws.com/production/c212f192-342d-44e0-a7a9-b57160c04ef3/original)

O DHCP permite atribuir endereços IP, máscaras de sub-rede e outras informações de configuração a computadores clientes em uma rede local. Uma rede que possui um servidor DHCP disponível permite aos seus computadores obterem um endereço IP através de solicitação e atribuição automática pelo servidor, conforme defendem Northrup e Mackin (2009).

Um administrador de rede pode configurar um serviço de DHCP para que determinado host receba o mesmo endereço IP toda vez que se conectar, ou um endereço IP temporário, diferente a cada conexão. Kurose e Ross (2013) classificam o DHCP como um protocolo _plug and play_, considerando sua capacidade de automatizar os aspectos relativos à rede da conexão de um host. Ademais, o DHCP é um protocolo cliente-servidor, no qual, em geral, um _host_ representa o cliente. A figura abaixo ilustra um servidor DHCP conectado à rede 223.1.2.0/24, servindo o roteador de agente de repasse para clientes conectados às sub-redes 223.1.1.0/24 e 223.1.3.0/24. Para um hospedeiro recém-chegado, o protocolo DHCP e um processo de quatro etapas:

1. Descoberta do servidor DCHP.
2. Oferta dos servidores DHCP.
3. Solicitação DHCP.
4. Configuração de requisição DHCP.

[![](https://ampli-images.s3.amazonaws.com/production/099992c4-ad55-4221-b4ad-5e52f0cf5631/original)](https://ampli-images.s3.amazonaws.com/production/099992c4-ad55-4221-b4ad-5e52f0cf5631/original)

Servidor DHCP em uma rede. Fonte: Kurose e Ross (2013, p. 256).

A seguir, temos um exemplo de topologia de rede com um servidor DHCP instalado e configurado através da ferramenta _Packet Tracer_, demonstrada na figura a seguir. A imagem refere-se ao departamento Servidor, no qual existe um servidor de rede que suporta serviços de DNS, DHCP, HTTP, FTP, entre outros, ligados a um Switch que interliga e serve toda uma rede de um departamento. A parte inferior da figura a seguir mostra a configuração do serviço de DHCP no _Packet Tracer._

[![](https://ampli-images.s3.amazonaws.com/production/e7ec1340-c32d-4535-9666-25f689c685ed/original)](https://ampli-images.s3.amazonaws.com/production/e7ec1340-c32d-4535-9666-25f689c685ed/original)

[![](https://ampli-images.s3.amazonaws.com/production/84f97b30-6d16-4e73-9a6f-ca2c2ba54580/original)](https://ampli-images.s3.amazonaws.com/production/84f97b30-6d16-4e73-9a6f-ca2c2ba54580/original)

Exemplo de configuração de servidor DHCP na ferramenta Packet Tracer. Fonte: elaborada pelo autor.

Em distribuições Linux, as configurações podem ser feitas em menus do ambiente gráfico ou via configuração textual no arquivo **/etc/dhcpd.conf**. A sua ativação se dá pela execução do programa **ntsysv** com a seleção da opção dhcpd. Ainda em Linux, o servidor DHCP pode ser executado através do comando **# service dhcpd start**.

Em um ambiente Windows Server, a configuração do intervalo de endereços a serem automaticamente atribuídos aos hosts se dá por meio do menu **Iniciar > Programas > Ferramentas Administrativas > DHCP**. A figura a seguir apresenta as telas de configuração de um servidor DHCP em plataforma Windows Server e cliente em plataforma Windows.

[![](https://ampli-images.s3.amazonaws.com/production/3e9a6834-47fa-4e46-a584-bc2880bea787/original)](https://ampli-images.s3.amazonaws.com/production/3e9a6834-47fa-4e46-a584-bc2880bea787/original)

[![](https://ampli-images.s3.amazonaws.com/production/2b28d267-1b25-4527-831a-7cb57e1e3c57/original)](https://ampli-images.s3.amazonaws.com/production/2b28d267-1b25-4527-831a-7cb57e1e3c57/original)

Configuração de intervalos de endereços IPv4. Fonte: captura de tela elaborada pelo autor.

______

**💭Reflita**

A configuração manual de endereços IP em redes de computadores locais pode ser uma estratégia mais assertiva quando se pensa em maior segurança, porém adequa-se a ambientes com poucos dispositivos na rede, devido à dificuldade de configuração individual e manual de cada dispositivo. Em redes maiores, a utilização de um servidor DHCP traz maior comodidade à gestão da rede, no entanto pode oferecer maiores riscos à segurança da rede.

Assim, um servidor DHCP mantém um banco de dados dos endereços que o servidor pode atribuir a hosts da rede. Quando um servidor DHCP atribui um endereço a um computador na rede, este se torna um host ativo com o endereço atribuído por seis ou oito dias por padrão.

______

**➕** **Pesquise mais**

O site de suporte da Microsoft traz uma seção interessante, chamada Noções básicas sobre endereçamento _TCP/IP e sub-rede_, que explica o endereçamento IP de uma rede.

Configurar uma rede com o IPv4 e sub-redes leva à utilização dos endereços IPs em redes de classes A, B ou C, alocados em sub-redes. Esta configuração deve seguir uma política de atribuição de endereços, utilizando-se de máscaras de rede para a realização da divisão das redes. O padrão CIDR (_Classless Inter-Domain Routing_) também é utilizado para configuração de sub-redes. Adicionalmente, existe o VLSM (_Variable Length Subnet Masking_), também utilizado para planejamento e configuração de endereços IPs e máscaras em sub-redes. O site _Hardware_ pode ser visitado para um estudo complementar sobre este assunto junto ao conteúdo: _Faixas de endereços IP CIDR e máscaras de tamanho variável_ (MONQUEIRO, 2007).