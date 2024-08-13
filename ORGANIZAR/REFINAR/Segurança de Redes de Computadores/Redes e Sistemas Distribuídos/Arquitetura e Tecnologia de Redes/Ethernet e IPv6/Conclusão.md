[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

Esta aula trouxe para você importantes conceitos a respeito do padrão Ethernet (IEEE 802.3) e suas diferentes versões utilizadas para implementação de sistemas de redes de computadores locais através de cabos, com uma tecnologia amplamente utilizada nos últimos 30 anos. De forma complementar, e com grande importância, trouxe também informações sobre o IPv6 como uma versão atualizada do protocolo IP para endereçamento e roteamento de redes, que deverá ser utilizado como padrão de endereçamento de redes junto à versão IPv4. Estas informações são fundamentais para que um profissional de tecnologia da informação possa projetar e implementar uma rede de computadores com performance adequada.

**Relatório do Projeto De Redes: Equipamentos de Rede e Análise De Domínios de Colisão e** _**Broadcast**_

Após a análise da topologia da rede e distribuição de hosts junto aos dispositivos comutadores, a equipe de consultoria pode apresentar informações de descrições dos equipamentos de rede que pertencem ao ambiente de _coworking_ e se utilizam do padrão Ethernet para transferência de dados na rede, de acordo com a topologia a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/939aa3b8-9806-47ab-8039-3a4de350d7a4/original)](https://ampli-images.s3.amazonaws.com/production/939aa3b8-9806-47ab-8039-3a4de350d7a4/original)

Topologia de rede para análise dos domínios de colisão e broadcast mapeados. Fonte: elaborada pelo autor.

Lista de equipamentos da rede:

- Sistemas: um servidor, uma impressora, dois desktops e um switch.
- Gerência: um switch, duas impressoras e três desktops.
- Clientes1: um switch e quatro desktops.
- Reuniões: um roteador.
- Clientes2: um switch, um hub e quatro desktops.
- Visitantes: um roteador.

**Domínio de colisão**: há quatro domínios de colisão, considerando que cada switch na topologia forma um domínio de colisão. Importante apresentar que o _hub_ não implementa um domínio de colisão e, caso a empresa tenha interesse em substituí-lo por um _switch_, poderá ter uma rede com menor colisão dentro de sua topologia.

**Domínio de broadcast:** há dois domínios de broadcast, considerando que cada roteador da topologia apresentada forma um domínio de broadcast.

Na atualidade, os _hubs_ podem ser substituídos por switches devido à evolução dos equipamentos nos últimos anos e ao custo com o equipamento ter diminuído, possibilitando sua utilização em maior escala em projetos de rede. Neste estudo, o _hub_ está sendo utilizado como elemento de comutação para exemplificar à empresa que seu uso atende parcialmente às necessidades da rede.