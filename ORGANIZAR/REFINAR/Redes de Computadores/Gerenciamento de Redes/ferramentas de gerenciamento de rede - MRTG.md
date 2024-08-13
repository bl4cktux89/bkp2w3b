**Introdução**

Olá! Seja bem-vindo à décima quinta aula! Nela, discutiremos uma ferramenta muito utilizada em ambientes computacionais de curta e longa distância, uma vez que o MRTG elabora gráficos com base na coleta de informações das MIBs dos agentes.

**O MRTG**

O MRTG (_**Multi Router Traffic Grapher**_) é um software livre (sob a licença GNU GPL – _**General Public License**_) criado por Tobias Oetiker, que gera imagens em formato PNG através da coleta de informações de agentes numa estrutura baseada na arquitetura SNMP. Por padrão, o MRTG gera as imagens e as indexa na estrutura HTML, logo, é necessário ter um servidor web instalado para que possam ser acessadas; isso cria comodidade, já que os relatórios podem ser vistos de qualquer computador (conforme a configuração feita), todavia, as imagens podem ser acessadas na própria máquina através de uma ferramenta que consiga exibir esse formato de imagem.

Este software pode ser executado no GNU/Linux, contudo há uma versão para Windows chamada de PRTG. A seguir, trataremos da configuração do MRTG no GNU/Linux, especificamente com a distribuição Ubuntu.

**Ambiente**

Para testar e compreender a configuração, simularemos tudo em uma mesma máquina. Necessitaremos do Ubuntu instalado e seus repositório atualizados, portanto, instalaremos os pacotes SNMPD, MRTG e APACHE2.

**Instalação e configuração**

Para instalar os 3 pacotes no Ubuntu, basta aplicar o comando de instalação, já que todos eles fazem parte do repositório principal, da seguinte forma:

`1.` `apt-get install mrtg snmpd apache2`

Mensagens serão exibidas e também será perguntado se deseja continuar. Tecle "S" (de sim, ou "Y", para _**yes**_). Quando a instalação finalizar, os softwares já estarão instalados e pré-configurados.

Para configurar o MRTG, devemos criar/editar o arquivo de configuração do MRTG (/etc/mrtg.cfg). O arquivo deverá conter as seguintes informações:

`1.` `WorkDir: /var/www/html/mrtg` `2.` `Language: brazilian` `3.` `Options[_]: bits,growright` `4.` `RunAsDaemon: yes` `5.` `Target[LAN]: 1:public@127.0.0.1:` `6.` `MaxBytes[LAN]: 12500000` `7.` `AbsMax[LAN]: 12500000` `8.` `Unscaled[LAN]: dwmy` `9.` `Title[LAN]: Exemplo de Análise de Tráfego para Rede Local de 100Mbps` `10.` `PageTop[LAN]: <h1> Análise de Tráfego para Rede Local de 100Mbps </h1>`

Salve e feche o arquivo.

Cada item é fundamental e deve ser escrito da mesma forma que foi mostrada. Deve-se, inclusive, observar letras maiúsculas e minúsculas.

Agora, vamos configurar o SNMP: edite o arquivo de configuração do SNMP (/etc/snmp/snmpd.conf). Ache o tópico "## sec.name source community" e altere/descomente as linhas para o seguinte:

`1.` `com2sec local localhost private` `2.` `com2sec mynet 192.168.0.0/24 public` `3.` `com2sec public default public`

Observe a segunda linha, na qual estão definidos nome e endereço da rede. Encontre/altere/descomente as seguinte linhas:

`1.` `group mygroup v1 mynet` `2.` `group mygroup v2c mynet` `3.` `group local v1 local` `4.` `group local v2c local` `5.` `group public v1 public` `6.` `group public v2c public`

Por último, encontre/altere/descomente as seguinte linhas:

`1.` `view all included .1 80` `2.` `access mygroup "" any noauth 0 all none none` `3.` `access public "" any noauth 0 all none none` `4.` `access local "" any noauth 0 all all all`

Salve e feche o arquivo.

Agora, devemos criar o diretório em que ficarão as páginas HTML do MRTG, depois reiniciaremos os serviços:

`1.` `mkdir /var/www/html/mrtg` `2.` `3.` `/etc/init.d/snmpd restart` `4.` `/etc/init.d/apache2 restart` `5.` `/usr/bin/mrtg –LANG=C /etc/mrtg/mrtg.cfg`

Pronto! Agora abra o navegador e digite: "HTTP://127.0.0.1/html/mrtg". Os gráficos serão exibidos. Leva algum tempo para aparecer o tráfego porque o MRTG atualiza a cada 5 minutos.