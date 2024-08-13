[![](https://ampli-images.s3.amazonaws.com/production/00baac5b-f11e-4723-b48c-27af26abc461/original)](https://ampli-images.s3.amazonaws.com/production/00baac5b-f11e-4723-b48c-27af26abc461/original)

O DNS é um protocolo utilizado para um sistema de domínio que faz a interconexão de URL (_Uniform Resource Locator_), ou seja, nomes de endereços de sites da internet com endereços IP. Este protocolo implementa um serviço importante de resolução de nomes mediante endereços IPs externos, localizados dentro de uma estrutura hierárquica na internet. As empresas também utilizam servidores de DNS para que suas redes locais possam encontrar informações mediante a utilização de nomes, inseridas como URL no lugar de endereços IPs, utilizando-se de um servidor de DNS.

De acordo com Kurose e Ross (2013), o DNS costuma ser empregado por outras entidades da camada de aplicação, como o HTTP, SMTP e FTP, para traduzir nomes de hosts fornecidos por usuários para endereço IP. De forma sintética, para que uma URL informada em um navegador possa retornar o conteúdo do site, é necessário que ele busque o seu endereço IP correspondente através de alguns passos:

1. O _host_ do usuário executa o lado cliente da aplicação DNS.
2. O navegador extrai o nome do host do URL e passa o nome para o lado do cliente da aplicação DNS.
3. O cliente DNS envia uma consulta com o nome do _host_ para um servidor DNS.
4. O cliente DNS recebe uma resposta com o endereço IP do nome do _host_ pesquisado.
5. O navegador recebe o endereço do DNS e abre uma conexão TCP com o processo servidor do HTTP via porta 80 naquele endereço IP.

O DNS é um protocolo que implementa um serviço de resolução (tradução) de nomes, endereços de páginas definidas por suas URL (_Uniform Resource Locator_) em endereços IPs dentro de uma estrutura hierárquica de servidores espalhados pelo mundo todo. Na internet, existem servidores DNS raiz que se interligam a servidores de domínio de alto nível, chamados de TLD (_Top Level Domain_), responsáveis por domínios, como .com, .org, .net, .edu e .gov, e por domínios de alto nível de países, como .uk, .fr., .br.

Abaixo destes servidores, estão os servidores DNS autorizativos (de autoridade, ou locais), disponibilizados por organizações que desejam oferecer hosts servidores para acesso público na internet, e finalmente os servidores de nomes locais, que necessariamente não pertencem a uma hierarquia e são chamados de servidores de nomes _default_. A figura abaixo apresenta os servidores raiz do mundo em 2012.

[![](https://ampli-images.s3.amazonaws.com/production/3743e102-adc8-4626-a020-8fda7d8a2394/original)](https://ampli-images.s3.amazonaws.com/production/3743e102-adc8-4626-a020-8fda7d8a2394/original)

Servidores raiz no mundo em 2012. Fonte: Kurose e Ross (2013, p. 99).

Em sua funcionalidade básica, quando um resolvedor tem uma consulta sobre um nome de domínio, ele a envia a um dos servidores de nomes local. Se o domínio que estiver sendo buscado estiver sob a jurisdição do servidor de nomes, serão retornados os registros com as informações de acesso. Caso o domínio for remoto e não houver informações sobre o domínio solicitado no local, o servidor de nomes (DNS) enviará uma mensagem de consulta para o servidor DNS de nível superior, buscando o domínio solicitado. Dois protocolos agem neste processo: o próprio DNS que traduz nomes simbólicos em endereços IP e o LDAP (_Ligh-weith Directory Access Protocol_), que organiza as informações como uma árvore e permite pesquisas em diferentes componentes e realiza a busca pelas informações solicitadas. A figura a seguir ilustra a relação hierárquica e distribuída entre servidores de controle de DNS espalhados pelo mundo com servidores locais.

Conforme exemplificam Kurose e Ross (2013): um hospedeiro **cis.poly.edu** deseja o endereço IP de **gaia.cs.umass.edu**. Considere que o servidor DNS local é **dns.poly.edu** e que um servidor DNS autorizativo para **gaia.cs.umass.edu** seja denominado **dns.umass.edu**. Como mostra a próxima figura, o hospedeiro **cis.poly.edu** primeiro envia uma mensagem de consulta DNS ao seu servidor DNS local dns.poly.edu. A mensagem de consulta contém o nome de hospedeiro a ser traduzido, isto é, gaia.cs.umass.edu. O servidor DNS local transmite uma mensagem de consulta a um servidor DNS raiz, que verifica o sufixo **edu** e retorna ao servidor DNS local uma lista de endereços IP de servidores TLD responsáveis por edu.

O servidor DNS local retransmite a mensagem de consulta a um desses servidores TLD, o qual, por sua vez, percebe o sufixo **umass.edu** e responde com o endereço IP do servidor DNS autorizado para a instituição com dns.umass.edu. O servidor DNS local reenvia a mensagem de consulta para **dns.umass.edu**, que responde com o endereço IP de gaia.cs.umass.edu. Para poder obter o mapeamento para um único nome de hospedeiro, foram enviadas oito mensagens DNS: quatro mensagens de consulta e quatro de resposta.

[![](https://ampli-images.s3.amazonaws.com/production/df36a667-12bd-4827-bbcc-2e1fabc69761/original)](https://ampli-images.s3.amazonaws.com/production/df36a667-12bd-4827-bbcc-2e1fabc69761/original)

Interação entre servidores de DNS. Fonte: Kurose e Ross (2013, p. 100).

Dentro de uma organização, é possível implementar um servidor de DNS para que informações possam ser compartilhadas dentro da estrutura da rede. De acordo com Northrup e Mackin (2009), a implantação de um servidor DNS é um procedimento razoavelmente simples, especialmente em um controlador de domínio. Kurose e Ross (2013) identificam um DNS como um servidor organizado de maneira hierárquica e distribuída. A seguir, temos um exemplo de topologia de rede com um servidor DNS instalado e configurado através da ferramenta _Packet Tracer_, demonstrada na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/868aee79-178b-4c81-8338-1156c078fce5/original)](https://ampli-images.s3.amazonaws.com/production/868aee79-178b-4c81-8338-1156c078fce5/original)

[![](https://ampli-images.s3.amazonaws.com/production/6d1b2945-f1d5-4e80-9195-e9305a1ddcc1/original)](https://ampli-images.s3.amazonaws.com/production/6d1b2945-f1d5-4e80-9195-e9305a1ddcc1/original)

Servidor DNS em uma rede. Fonte: elaborada pelo autor.

Em um sistema Windows Server, a ativação do servidor DNS se dá primeiramente pela criação de uma zona DNS, que é um banco de dados com registros que associam nomes a endereços para uma parte definida de um espaço de nomes DNS. Depois, o servidor DNS precisa ser configurado para registros de DNS e, por último, configurar a replicação e transferência de zona. Já em distribuições Linux, as configurações podem ser feitas em menus do ambiente gráfico ou via configuração textual no arquivo _**/etc/named.conf**_. O arquivo _**localhost**_ define todas as configurações de domínio local para informar o endereço de consulta ao hostname localhost. O banco de dados do domínio é definido pelos arquivos zona e zona reversa.

______

**🔁Assimile**

De forma geral, o DNS trata da busca de endereços IPs para que você possa fazer suas buscas e operações via sistemas em rede, dentro da WWW (_World Wide Web_), por exemplo. Na prática, um conjunto de páginas web em formato HTTP, chamado de site, é acessado através de um endereço URL informado em um _browser_, que carrega a sua página principal, chamada de _home page_, dentro de um ambiente WWW. Sites de busca auxiliam na localização de URLs dentro desta estrutura hierárquica, como Google, Yahoo, Bing, Baidu, entre outros. O Google representa, conforme Laudon e Laudon (2014), mais de 83% das buscas realizadas na internet.

______

Junto à configuração do endereço IP do host e às informações de máscara de rede, deve também ser informado o endereço de DNS na rede. Segue, na figura abaixo, um exemplo de configuração de endereço de DNS em um sistema Windows.

[![](https://ampli-images.s3.amazonaws.com/production/d3fcb565-df25-490b-82b0-36efa42ac5d4/original)](https://ampli-images.s3.amazonaws.com/production/d3fcb565-df25-490b-82b0-36efa42ac5d4/original)

Exemplo de configuração de DNS. Fonte: captura de tela elaborada pelo autor.