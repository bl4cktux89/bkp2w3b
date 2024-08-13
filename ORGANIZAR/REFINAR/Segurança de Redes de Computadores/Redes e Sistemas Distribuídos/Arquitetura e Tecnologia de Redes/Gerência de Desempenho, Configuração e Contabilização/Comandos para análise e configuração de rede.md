[![](https://ampli-images.s3.amazonaws.com/production/441ebbed-9f24-4dc7-8193-c5ee3ef8267e/original)](https://ampli-images.s3.amazonaws.com/production/441ebbed-9f24-4dc7-8193-c5ee3ef8267e/original)

A análise e a configuração de redes de computadores fazem uso de comandos em _prompt_ de comando nos sistemas operacionais Microsoft Windows e de distribuições Linux, para que pacotes de software sejam implementados no sistema e possam ser utilizados pelo administrador da rede para gerir os _host_ e dispositivos de rede em geral e, assim, configurar hardware e software e gerenciar o tráfego na rede. A seguir, serão apresentados alguns comandos básicos de gestão de redes.

**Ping**

O comando ping é usado para testar a capacidade de um host de rede de se comunicar com outro. Ele retorna dados referente a um teste simples de conexão de rede e à qualidade de entrega de pacotes. A próxima figura apresenta a saída do comando ping utilizado junto ao endereço IP (8.8.8.8) de um servidor do Google. Podem ser observadas informações sobre a conexão, como tempo de resposta e TTL (_Time To Live_) da mensagem, uma estatística de pacotes enviados como pacotes perdidos e a latência da rede, com mínimo, máximo e média.

[![](https://ampli-images.s3.amazonaws.com/production/68e6ab1d-4ad0-4bbf-aa2c-52f6a7d44253/original)](https://ampli-images.s3.amazonaws.com/production/68e6ab1d-4ad0-4bbf-aa2c-52f6a7d44253/original)

Exemplo de utilização do comando ping. Fonte: captura de tela do prompt de comando do sistema elaborada pelo autor.

**Tracert**

O comando tracert é semelhante ao ping, mas com a função adicional de enviar solicitações de eco do ICMP (_Internet Control Message Protocol_) e do TTL (_Time to Live_) da solicitação, para que se verifique a lista de roteadores pelos quais os pacotes estão passando em cada salto. Este comando apresenta o caminho de um pacote percorrido na rede. Em distribuições Linux, utilize o comando traceroute para esta finalidade. A figura abaixo apresenta a saída do comando tracert utilizado junto ao endereço IP de um servidor do Google.

[![](https://ampli-images.s3.amazonaws.com/production/387f4aea-26f1-4740-88fd-f1ee11c96fb3/original)](https://ampli-images.s3.amazonaws.com/production/387f4aea-26f1-4740-88fd-f1ee11c96fb3/original)

Exemplo de utilização do comando tracert. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

**Ipconfig**

O comando ipconfig exibe informações básicas de configuração do endereço IP do host. Pode-se utilizar a opção ipconfig /all para verificar informações detalhadas. Em distribuições Linux, utilize o comando ifconfig para realizar a operação realizada pelo ipconfig em sistemas Windows. A Figura 2.41 apresenta a saída do comando ipconfig utilizado no computador local. Veja que há um volume importante de informações de endereçamento do _host_, com o endereço IPv6, o endereço IPv4 de configuração automática, considerando que há um servidor de endereços no sistema (DHCP – _Dynamic Host Configuration Protocol_), a máscara de rede e o gateway padrão da rede, onde o host está se conectando localmente.

[![](https://ampli-images.s3.amazonaws.com/production/8e40808d-9e10-4ac2-9f45-65fec34d6b01/original)](https://ampli-images.s3.amazonaws.com/production/8e40808d-9e10-4ac2-9f45-65fec34d6b01/original)

Exemplo de utilização do comando ipconfig. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

**Hostname**

O comando hostname retorna o nome do dispositivo (computador) local. A figura abaixo apresenta um exemplo de saída do comando hostname com o devido nome do _host_ local.

[![](https://ampli-images.s3.amazonaws.com/production/8165fbb8-4a0b-483a-8c81-1cec9ac3ede9/original)](https://ampli-images.s3.amazonaws.com/production/8165fbb8-4a0b-483a-8c81-1cec9ac3ede9/original)

Exemplo de utilização do comando hostname. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

**Netstat**

O comando netstat apresenta uma estatística da rede. Este comando possui várias funções, sendo que o comando netstat -e mostra um resumo das estatísticas da rede. A figura abaixo apresenta a saída do comando netstat -e com informações da rede. Veja que é apresentado um relatório com bytes recebidos e enviados, pacotes unicast, pacotes não unicast, descartados e erros. Com essas informações, o gestor pode reconhecer a performance da rede.

[![](https://ampli-images.s3.amazonaws.com/production/c532da14-fe78-4ebd-91a3-e7dce426e27c/original)](https://ampli-images.s3.amazonaws.com/production/c532da14-fe78-4ebd-91a3-e7dce426e27c/original)

Exemplo de utilização do comando netstat. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

**Nslookup**

O comando nslookup apresenta um diagnóstico de problemas de resolução de nomes DNS (_Domain Name System_) apresentando o endereço IP do servidor DNS padrão do dispositivo. Conhecendo o nome do servidor DNS, pode-se digitar os nomes de _hosts_. Ele faz uma consulta de nomes de servidores de DNS na internet. A figura abaixo apresenta a saída do comando nslookup 8.8.8.8.

[![](https://ampli-images.s3.amazonaws.com/production/2e8039ac-05ab-4ab7-86e0-9d017ccc1939/original)](https://ampli-images.s3.amazonaws.com/production/2e8039ac-05ab-4ab7-86e0-9d017ccc1939/original)

Exemplo de utilização do comando nslookup. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

**ARP**

O comando arp corresponde a um protocolo de resolução de endereços através do mapeamento de endereços IP junto ao endereço MAC (_Media Access Control_). A figura abaixo apresenta a saída do comando arp com o mapeamento dos endereços lógicos (IP) e físicos (MAC) de um dispositivo.

[![](https://ampli-images.s3.amazonaws.com/production/2174035e-5f0e-45a3-b158-c1b806aea3c4/original)](https://ampli-images.s3.amazonaws.com/production/2174035e-5f0e-45a3-b158-c1b806aea3c4/original)

Exemplo de utilização do comando arp. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

**Route**

O comando route exibe as tabelas de roteamento do dispositivo e permite observar informações de direcionamento de pacotes de uma sub-rede para outra. A figura a seguir apresenta a saída parcial de um comando route print, atributo que imprime as tabelas de roteamento local.

[![](https://ampli-images.s3.amazonaws.com/production/edaa56fe-9715-4352-a16d-12d30c6a9b37/original)](https://ampli-images.s3.amazonaws.com/production/edaa56fe-9715-4352-a16d-12d30c6a9b37/original)

Exemplo de utilização do comando route. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

Aqui, apresentamos alguns comandos básicos para análise e configuração de dados de rede, porém ainda há diversos outros comandos e sistemas operacionais que podem ser utilizados na configuração e gestão de redes de computadores.