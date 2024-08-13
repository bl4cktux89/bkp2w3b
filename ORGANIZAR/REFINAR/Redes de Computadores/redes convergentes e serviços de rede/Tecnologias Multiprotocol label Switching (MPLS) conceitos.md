**Introdução**

O MPLS é uma tecnologia que reune uma série de protocolos e funcionalidades, em destaque requisitos de segurança e qualidade de serviço, garantindo flexibilidade, escalabilidade e interoperabilidade de diferentes tipos de redes e tecnologias de camada 2 como ATM, Frame Relay, PPP, Ethernet bem como as de camada 3 tais como IPV4, IPV6, AppleTalk, IPX...

Essa flexibilidade fez com que o MPLS garantisse maior confiabilidade e flexibilidade nas redes de computadores, garantindo o melhor esforço para aplicações Multimídia, em ambientes LAN e WAN, graças ao uso de técnicas utilizadas em cabeçalhos de camada 2 e 3.

O MPLS foi desenvolvido em 1996 de modo proprietário pela Cisco Networks, passando de proposta e tornando-se uma padronização em 2001 pela comunidade de desenvolvimento de tecnologias de Redes pela RFC 3031, ( IETF e IEEE).

A rede MPLS associa o mundo TCP/IP com a comutação de pacotes, proporcionando designação, encaminhamento eficiente do fluxo de dados através da rede, com qualidade de serviço e com a determinação de classes de serviços.Em uma rede IP convencional, todos os dados são tratados da mesma forma, pois não há classes de serviços diferenciadas, mas apenas um único serviço: a entrega das informações, sem a preocupação em classificar ou priorizar entregas de serviços específicos, como dados, voz e imagens.Na rede IP, as informações são segmentadas em pequenos pacotes e cada um deles recebe um cabeçalho que contém as informações do endereço de origem e destino, bem como demais informações de controle, que podem adicionar priorização ou classificação das informações.

Quando estes dados são destinados a outro computador que não pertence à mesma rede, os pacotes serão encaminhados através de roteadores até o destinatário final.Cada roteador recebe um pacote de cada vez e executa o roteamento (independente dos outros pacotes), que consiste em verificar o endereço do destinatário encaminhando pela melhor rota possível. Esta funcionalidade pode ser descrita em três passos conhecido como algoritmo de roteamento hop-by-hop:

1. Verificar qual é o nó mais próximo do destinatário.2. Ir até este nó.3. Repetir os passos anteriores até se alcançar o destinatário.Estes três passos são executados consultando as tabelas de roteamento interna dos equipamentos e verificando qual é o prefixo mais longo que coincide com o endereço do destino final do pacote.Observe que estes três passos são executados para cada pacote que adentra a um roteador:

**Resumidamente ...**

1. O pacote entra no roteador e, após passar pela camada 2 com sua verificação de erros, é encaminhado ao nível 3 de rede.2. O roteador verifica o endereço de destinatário do pacote e procura em suas tabelas qual é a melhor rota de encaminhamento.3. O pacote é novamente levado à camada 2, na qual ele será encapsulado em um outro quadro, recebendo novos endereços do tipo Mac Address e, então, será encaminhado à porta correspondente para ser transmitido.

Este processo todo é executado para cada pacote que entra no roteador, mesmo que todos eles sigam para o mesmo destinatário consumindo tempo e causando atraso na propagação dos datagramas por causa de todo o processamento necessário para rotear cada pacote independentemente. A tecnologia MPLS resolve esta questão com a comutação dos pacotes, e não mais o roteamento. Para deixar bem esclarecida a diferença fundamental entre rotear e comutar, pode-se considerar que roteamento é executado na camada 3, enquanto a comutação realiza-se na camada 2 do modelo de referência OSI, portanto, economiza-se um processamento de nível 3.

**Características básicas do MPLS**

Os dados em uma rede MPLS são encaminhados através de caminhos pré-estabelecidos anteriormente, isto sendo feito a partir da descoberta da melhor rota por roteamento igual a uma rede convencional IP, porém, depois desta rota descoberta, os dados são comutados em nível 2 (do modelo de referência OSI), economizando processamento e todos os frames sendo transmitidos por um único caminho.

A tecnologia MPLS é utilizada em backbones e consiste em uma solução para problemas, como escalabilidade, velocidade, gerenciamento e designação de Quality off Service (QoS) para cada aplicação, das redes convencionais, dependendo das suas necessidades particulares.

**Principais vantagens**

Entre varias vantagens do MPLS, destacam-se:

- Qualidade de serviço – QoS.
- Classes de serviço – CoS.
- Orientação à conexão em redes IP.
- Transferência da comutação da camada 2 para a camada 3.
- Menor complexidade nas decisões de encaminhamento dos datagramas.
- Virtual Private Network (VPN).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/0/4/10417/i03_551.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/0/4/10417/i03_551.jpg)

Túnel VPN

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258997/14817.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258997/14817.jpg)

Qualidade de serviço em uma chamada

A aplicação mais interessante do MPLS é sua utilização em conjunto como IP, pois desta forma temos o melhor das duas tecnologias. No IP, temos as vantagens do roteamento na descoberta dosdestinatários e, no MPLS, a comutação de circuitos, tornando assim a transferência extremamente rápida.

**Componentes do MPLS**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/3/6/3636/i01_553.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/3/6/3636/i01_553.jpg)

Elementos da Rede MPLS

O funcionamento básico da rede MPLS consiste no encaminhamento dos pacotes que adentrem a rede e recebem uma etiqueta, um rótulo (label), que será aplicado por um roteador de borda, denominado Label Edge Router (LER).Uma vez dentro da rede MPLS, os pacotes são encaminhados através de uma rota comutada por etiquetas (label), denominadas Label Switch Patch (LSP). Esta rota é formada por roteadores de comutação por rótulos, chamados de Label Switch Router (LSR), que tomam a decisão de encaminhamento dos pacotes baseados exclusivamente nas informações destas etiquetas.

O MPLS é baseado em uma tomada de decisão através de Roteadores que rotulam e priorizam tráfego, através de etiquetas adicionadas no encaminhamento desses pacotes, garantindo aos pacotes que possuem classificação para diferenciação de serviços envio expresso e garantido.