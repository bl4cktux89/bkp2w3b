[![](https://ampli-images.s3.amazonaws.com/production/9d5e6004-59d2-4f72-b512-6dfe5ad5278f/original)](https://ampli-images.s3.amazonaws.com/production/9d5e6004-59d2-4f72-b512-6dfe5ad5278f/original)

Comer (2016) define que o objetivo da medição de redes é o provisionamento da rede: projetar uma rede para fornecer um nível específico de serviço e, em termos gerais, isto é conhecido como Qualidade de Serviço, ou _Quality of Service_ (QoS). Ela pode ser vista como o conjunto de regras, mecanismos e tecnologias que objetivam a utilização eficaz do sistema. Como vimos anteriormente, os fatores que influenciam na performance da rede são a latência, o _jitter_, a perda de pacotes e a largura de banda disponível. O QoS busca garantir ao usuário ou gestor da rede de computadores controle adequado sobre sua estrutura de rede. Uma aplicação de utilização de QoS é determinar quais dispositivos da rede e quais serviços de rede precisam de prioridade na conexão.

O atendimento às necessidades de performance dos sistemas de redes de computadores, a QoS, utiliza-se de dois modelos conceituais:

- **IntServ:** utiliza o fluxo dos dados por meio do protocolo no caminho que a mensagem deve percorrer e garante o envio e recebimento de mensagens fim a fim.
- DiffServ: utiliza uma marcação no pacote transmitido pela rede para classificá-lo e efetuar os tratamentos necessários de forma independente para os pacotes.

De acordo com Comer (2016), o IETF (_Internet Engineering Task Force_) criou uma série de tecnologias e protocolos relacionados à QoS. Os três mais significativos são: RSVP/COPS (_Resource ReSerVation Protocol / Common Open Policies Services_), DiffServ e MPLS (_Multiprotocol Label Switching_).

- **RSVP/COPS**: modelo baseado no IntServ, no qual o IETF desenvolveu dois protocolos para fornecer QoS: o protocolo de reserva de recursos (RSVP) e os serviços abertos de políticas comuns (COPS). O RSVP é uma versão de QoS, em que a reserva de recursos é necessária para cada sessão TCP ou UDP. O COPS é um protocolo usado conjuntamente com o RSVP para especificar e aplicar políticas.
- **DiffServ**: uma vez abandonados os IntServ, o IETF criou os serviços diferenciados (_DiffServ, ou Differentiated Services_) para definir um mecanismo de QoS que define como as classes podem ser especificadas para o cabeçalho IPv4 ou IPv6, para especificar a classe de um datagrama.
- **MPLS:** é um mecanismo de comunicação orientado à conexão construído em cima do IP. Para usar o MPLS, um gerente configura caminhos de encaminhamento através de um conjunto de roteadores com o MPLS habilitado.

A análise da performance da rede que considera a qualidade dos serviços, a disponibilidade da rede, a capacidade de processamento e o armazenamento é determinada pelo termo _Service Level Agreement_ (SLA), ou seja, um acordo de nível de serviço definido e medido constantemente.