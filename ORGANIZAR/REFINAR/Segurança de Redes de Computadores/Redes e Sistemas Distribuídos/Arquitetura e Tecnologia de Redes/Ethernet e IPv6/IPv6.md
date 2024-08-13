[![](https://ampli-images.s3.amazonaws.com/production/be01b857-b4cf-455f-8bc7-30a8f3bb4d55/original)](https://ampli-images.s3.amazonaws.com/production/be01b857-b4cf-455f-8bc7-30a8f3bb4d55/original)

Conforme sustentam Kurose e Ross (2013), o projeto de endereçamento IPv6 teve início na década de 1990, mediante um aumento expressivo do número de computadores e dispositivos que se interconectavam às redes de computadores. Atualmente, o conceito de IoT (_Internet of Things_) corrobora com um aumento exponencial no número de sensores e dispositivos que estão sendo conectados à internet. Importante observar que o esgotamento do IPv4 ocorreu em 2014.

O projeto do IPv6 foi liderado pela IETF (_Internet Engineering Task Force_) e contou com a participação da LACNIC (_Latin American and Caribbean Internet Addresses Registry_), com um estudo e monitoramento a respeito do esgotamento de endereços IPv4 disponíveis no mundo.

Com a intenção de desenvolver um novo protocolo de endereçamento e roteamento de rede, o IPv6 veio para suprir algumas necessidades além das possibilidades do protocolo IPv4:

1. Resolver a escassez de endereços IPs na internet.
2. Simplificar o cabeçalho do endereço IP.
3. Deixar como opcional alguns campos de cabeçalho IP, para facilitar o roteamento de pacotes na rede.
4. Melhorar a segurança das transmissões, adicionando o IPSec (_Internet Protocol Secure_).

A figura abaixo apresenta o formato de um datagrama IPv6.

[![](https://ampli-images.s3.amazonaws.com/production/baaf2580-3399-4082-b715-6947cdf267d0/original)](https://ampli-images.s3.amazonaws.com/production/baaf2580-3399-4082-b715-6947cdf267d0/original)

Formato do datagrama IPv6. Fonte: Kurose e Ross (2013, p. 264).

É importante salientar que o datagrama IPv6 também pode ser composto por 64 bits, conforme sustenta IPv6.BR (2020).

A seguir, é apresentada uma breve descrição dos campos do datagrama IPv6.

- Versão: (4 bits) versão do protocolo IP (4 ou 6).
- Classe de tráfego: (8 bits) campo para prioridade.
- Rótulo de fluxo: (20 bits) identifica o fluxo de datagramas.
- Comprimento da carga útil: (16 bits) tamanho total do pacote (datagrama).
- Próximo cabeçalho: (8 bits) identifica o protocolo ao qual o conteúdo será entregue (TCP ou UDP).
- Limite de saltos: (8 bits) limite de saltos em roteadores.
- Endereço IP de origem: (128 bits) endereço do remetente.
- Endereço IP de destino: (128 bits) endereço do receptor
- Dados: dados a serem transmitidos.

Comer (2015) sustenta que, da mesma forma que o IPv4, o IPv6 atribui um endereço exclusivo para cada conexão entre um computador e uma rede física. Um endereço IPv6 possui 128 bits, o que permite um total de 340 undecilhões de endereços (2128), em um formato de oito grupos de quatro dígitos hexadecimais. Conforme apresenta Stallings (2016), a combinação de endereços longos e diversos por interface permite melhor eficiência de roteamento pelo IPv4.

Ainda de acordo o mesmo autor, a notação para um endereço IPv6 usa oito números hexadecimais para representar os oito blocos de 16 bits no endereço de 128 bits, com os números separados por dois pontos (:). Exemplo: 835C:5B9D:BC27:0000:0000:0000:C4B8:1FBB. Este número realmente é muito grande e suficiente para que possamos endereçar os dispositivos das redes pessoais, locais, metropolitanas, globais e os dispositivos de IoT na internet. A figura abaixo apresenta a composição de um endereço IP de 128 bits.

[![](https://ampli-images.s3.amazonaws.com/production/128e66cf-9c03-44bc-b232-7167f729db2f/original)](https://ampli-images.s3.amazonaws.com/production/128e66cf-9c03-44bc-b232-7167f729db2f/original)

Formato do endereço IPv6. Fonte: elaborada pelo autor.

Um endereço IPv6 tem sua composição diferenciada de um endereço IPv4, apesar de ter uma mesma abordagem na atribuição aos _hosts_. Como nos endereços em notação CDIR (_Classless Inter-domain Routing_), a divisão entre parte da rede (prefixo) e parte do _host_ (sulfixo) no endereço ocorre em limites flexíveis na utilização de seus bits. O endereço IPv6 possui três níveis de hierarquia, conforme sustenta Comer (2015). Um prefixo inicial é um valor único e global usado para roteamento na internet, atribuído a uma organização. A segunda parte do endereço identifica a sub-rede (ou seja, a própria rede) da organização. A terceira parte especifica o host de rede.

Um endereço IPv4 tem tamanho variável e definido por um ISP (_Internet Service Provider_), ou servidor de serviços de internet, em conformidade com a necessidade de volume de hosts de uma empresa cliente. A terceira parte do endereço tem tamanho fixo de 64 bits, formando um prefixo global de /64. A figura abaixo apresenta a estrutura de um endereço IPv6.

[![](https://ampli-images.s3.amazonaws.com/production/1793eaaa-9964-408b-86f0-d41cdf192d24/original)](https://ampli-images.s3.amazonaws.com/production/1793eaaa-9964-408b-86f0-d41cdf192d24/original)

Formato do endereço IPv6. Fonte: Comer (2015, p. 316).

Segundo Stallings (2016), o protocolo IPv6 permite a definição de três tipos de endereços: _unicast, anycast e multicast._

- _**Unicast**_: possui um identificador para uma única interface de rede, ou seja, para um único host, sendo que um pacote enviado para um endereço _unicast_ é entregue para a interface identificada pelo endereço.
- _**Anycast**_: possui um identificador para um conjunto de interfaces (em diferentes nós de rede), sendo que um pacote enviado para um endereço _anycast_ é entregue para uma das interfaces identificadas por esse endereço (o mais próximo na distância de roteamento).
- _**Multicast**_**:** possui um identificador para um conjunto de interfaces (em diferentes nós de rede), sendo que um pacote enviado para um endereço _multicast_ é entregue para todas as interfaces identificadas pelo endereço.

______

**🔁Assimile**

Os blocos de um endereço IPv4 são chamados de **octetos**, pois possuem oito símbolos binários (bits), que variam de 00000000 a 11111111. Os blocos de um endereço IPv6 são chamados de **decahexateto** ou **duocteto**, pois possuem quatro símbolos hexadecimais, os quais variam de 0000 até FFFF. Veja a composição do endereço IPv6 exemplificado no texto: **835C:5B9D:BC27:0000:0000:0000:C4B8:1FBB**.

______

Com o objetivo de manter os dois protocolos coexistentes e interoperáveis, ou seja, que possam ser utilizados e se prover de endereçamento e roteamento nas redes de computadores que podem ser configuradas apenas com endereços IPv4, apenas com endereços IPv6 ou com os dois protocolos, o que se chamou de Pilha Dupla (Dual Stack).

Dispositivos de rede que suportam o conceito de Pilha Dupla defendido por Kurose e Ross (2013) os hosts configurados com IPv6 também devem possuir uma implementação IPv4 completa, o que os determinará como IPv6/IPv4. Na operação de um dispositivo configurado como Pilha Dupla, as mensagens oriundas da camada de Aplicação serão encapsuladas na Pilha Dupla, para que a mensagem enviada à camada de enlace e física (host de rede no TCP/IP) seja enviada ao meio disponível, onde podem ocorrer duas situações: 1. Mensagem com formato IPv4 é encapsulada com Ipv6; 2. Mensagem com formato IPv6 é encapsulada com IPv4.

______

**📝 Exemplificando**

Dispositivos de rede, ou seja, _hosts_ que estiverem configurados com o protocolo IPv6, deverão também ter uma implementação IPv4. Ao interagir um host IPv4, um _host_ IPv6/IPv4 poderá usar datagramas IPv4; ao interagir com um _host_ IPv6, poderá utilizar o IPv6. _Hosts_ IPv6/IPv4 possuem endereços IPv6 e IPv4. Dispositivos de rede, como computadores, câmeras IP, impressoras, smartphones e dispositivos de IoT, devem estar configurados com a opção de Pilha Dupla.

______

Os endereços IPv6s e as máscaras (e sub-rede, se desejado) precisam ser informados em cada host da rede. Segue, na figura a seguir, um exemplo de configuração de endereço IPV6 e máscara de rede (e/ou sub-rede) em um sistema Windows. Os servidores DHCP também podem ser configurados para configuração automática de endereços em _hosts_ em uma rede.

[![](https://ampli-images.s3.amazonaws.com/production/df38a6e1-651e-43a1-b8e8-61bce195e6a6/original)](https://ampli-images.s3.amazonaws.com/production/df38a6e1-651e-43a1-b8e8-61bce195e6a6/original)

Exemplo de configuração de endereço IPv6. Fonte: captura de tela elaborada pelo autor.