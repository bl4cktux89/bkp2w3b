### Introdução

O IPv6 trouxe uma gama de funções perante o seu antecessor, o IPv4. Essas novidades trouxeram uma melhor segurança, desempenho e praticidade. A sua função principal é atribuir endereços aos dispositivos encontrados na rede mundial, além de enviar pacotes de dados, de um dispositivo para o outro através da rede local ou da internet.

O IPv6 contém a função de auto-configuração que atribui à rede todos os atributos básicos para que ela funcione corretamente, como: IP, Máscara de rede e Gateway. O IPv6 carrega automaticamente serviços de IPSec, aumentando sua segurança perante a rede mundial.

### Função de Qualidade de Serviço

Traz inserções de QoS (termo de Qualidade de serviço), como o tratamento especial de conteúdo Multimídia que passa a utilizar uma conexão mais adequada; a otimização do cabeçalho que contém menos campos e consequentemente economiza tempo para ser lido pelos nós intermediários, contando com a função de cabeçalhos de extensão que só são anexados ao cabeçalho principal, caso se faça necessário.

![[Untitled 14.png|Untitled 14.png]]

### Quadro Comparativo entre as versões do protocolo IP (Internet Protocol)

O campo Classe de tráfego (_**Traffic Class**_), que substitui o antigo campo Tipo de serviços (Type of Service - ToS),  apresenta a classificação de serviços e a priorização dos pacotes, que quando sinalizado de acordo com as classes de serviços e sua prioridade, sendo elas: baixa, normal, media, alta, e de acordo com suas classificações de serviço e politicas de tráfego, podem conferir ao tráfego de rede, maior velocidade e garantias asseguradas ao processamento de informações e transmissão de dados.

### Função de Multicasting

Com o aumento na quantidade de endereços Multicast (quando 1 remetente envia pacotes destinados à um grupo de destinatários); inicializa-se automaticamente junto com o TCP/IP; otimiza o tipo de rede P2P (Peer-to-Peer, ou ponto a ponto em português), tornando-a mais prática, tanto na implantação, quanto na usabilidade; o Broadcast é substituído pelo Multicast, que, ao invés de enviar um pacote para todos os nós disponíveis, envia apenas aos nós que o solicitar, proporcionando uma otimização do tempo na rede, além de proporcionar mais segurança, já que o envio de pacotes, de informações, somente acontecem dentro de seus próprios dominios.

### Path MTU Discovery

O nó atual identifica se o tamanho do pacote ultrapassa o MTU (maximum transmission unit) da rede por qual vai passar, caso passe o nó descarta o pacote e envia uma mensagem de erro ICMP ao nó de origem do pacote. E então o mesmo divide o pacote em vários fragmentos, cada um devidamente identificado e reenvia novamente com confiablidade.

[https://www.youtube.com/watch?v=5OtebbSnwoM](https://www.youtube.com/watch?v=5OtebbSnwoM)

O IPv6 inclui o DNS, o NAT e o DHCP; tornou-se possível realizar configurações no TCP/IP através de softwares; otimização da qualidade de serviço (QoS) utilizando-se o campo Identificador de Fluxo do cabeçalho principal; possibilidade de mudar o estado da rede (entre pública e privada) sem alterar o endereço.

Multihoming: Com esta função, um host pode ter mais de um ISP (Internet Service Provider, provedor de internet em português), garantindo a sua operação com alta disponibilidade;

DHCPv6 Stateful: Neste serviço, o servidor atribui um endereço IP, entre outras informações, aos terminais da rede e armazena estes dados em uma tabela.

Já no DHCPv6, o servidor permite que os terminais formem seus endereços IP com base no Mac address e outras informações; uso dos campos relacionados à prioridade e fluxo dos pacotes e fim de separá-los de acordo com as suas exigências de QoS;

Existência de 3 formas de endereço:

- Unicast (contém apenas um remetente e um destinatário),
- Multicast (contém um remetente e um grupo de destinatários) e
- Anycast (contém um remetente e um grupo de destinatários, onde a entrega é feita apenas ao destinatário mais próximo pertencente a este grupo).

[https://www.youtube.com/watch?v=6Zp-YSKORZQ](https://www.youtube.com/watch?v=6Zp-YSKORZQ)

> [!info] IPv6  
> Antonio Marcos Moreiras Rodrigo Regis dos Santos Alexandre Yukio Harano Edwin Santos Cordeiro Tiago Jun Nakamura Eduardo Barasal Morales Heitor de Souza Ganzeli Rodrigo Matos Carnier Gustavo Borges Lugoboni Desenvolvido pelos membros do projeto IPv6.  
> [http://ipv6.br/pagina/livro-ipv6/](http://ipv6.br/pagina/livro-ipv6/)