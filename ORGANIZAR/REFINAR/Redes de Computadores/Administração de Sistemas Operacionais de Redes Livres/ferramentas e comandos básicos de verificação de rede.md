### Introdução

Em termos de redes, provavelmente não há nada que não possa ser feito com o Linux. O Linux é usado para construir todos os tipos de sistemas e aparelhos de rede, incluindo firewalls, roteadores, servidores de DNS, boxes NAS (_**Network Attached Storage**_) e assim por diante. Assim como o assunto da rede é vasto, também o número de comandos que podem ser usados para configurá-la e controlá-la é vasto. Concentraremos a nossa atenção apenas em alguns comandos mais utilizados. Os comandos escolhidos para nosso tópico incluem aqueles usados para redes e aqueles usados para transferir arquivos (serviço importante de rede). Além disso, vamos explorar o ssh, um programa que é usado para executar logins remotos [1].

Este tópico abordará:

- **ping** - Enviar um ECHO_REQUEST ICMP para os hosts da rede.
- **traceroute** - Mostrar o rastreamento da rota dos pacotes para um host de rede.
- **Ip -** Mostra e manipula o roteamento, dispositivos, políticas de roteamento e túneis.
- **netstat** - Mostrar conexões de rede, tabelas de roteamento, estatísticas de interface de rede, conexões mascaradas e multicast.
- **ftp** programa de transferência de arquivos na Internet.
- **wget** - download de rede/internet não-interativo.
- **ssh** - Cliente SSH OpenSSH (programa de login remoto).

Aqui é importante você ter um pouco de conhecimento de rede. Nesse contexto, na era da Internet, alguém usando um computador precisa de um entendimento básico de conceitos de rede. Para fazer uso deste capítulo, devemos estar familiarizados com os seguintes termos:

- Endereço IP (Protocolo Internet)
- Nome do host e do domínio
- URI (Uniform Resource Identifier)

**Não tem problema se esta é sua primeira disciplina. Uma pequena consulta na internet sobre os 3 itens acima é o suficient**

**Nota: Alguns dos comandos que vamos ver podem, dependendo da sua distribuição, requerer a instalação de pacotes adicionais dos repositórios da sua distribuição. Além disso, alguns comandos podem exigir privilégios de superusuário para serem executados.**

### Analisando e Monitorando a Rede

Talvez você não seja o administrador do sistema, mas, geralmente, é útil examinar o desempenho e o funcionamento da rede. Nem que seja para saber se o seu provedor de internet está sendo honesto com o serviço contratado.

### Ping

O comando de rede mais básico é o **ping**. O comando ping envia uma rede especial pacote chamado ICMP ECHO_REQUEST para um host especificado. A maioria dos dispositivos de rede ao receber este pacote responderá automaticamente a ele, permitindo que a conexão de rede seja verificada.

É possível configurar a maioria dos dispositivos de rede (incluindo hosts Linux) para ignorar esses pacotes. Isso geralmente é feito por razões de segurança, para parcialmente esconder um servidor de um atacante em potencial. Também é comum que os firewalls sejam configurados para bloquear tráfego ICMP.

Por exemplo, para ver se podemos alcançar **uninove.br**, podemos fazer o uso do ping como abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818381/36850.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818381/36850.png)

Pressionei Ctrl-c depois de o ping ter lançado o oitavo pacote e, assim, o programa mostrou estatísticas de desempenho. Uma rede com desempenho correto exibirá zero por cento de perda de pacotes. Um bem sucedido "ping" irá indicar que os elementos da rede como a plca de rede, as rotas, os roteadores e o cabeamento estão em perfeita ordem. Caso contrário o ping não responderia.

### Traceroute

O programa traceroute, alguns sistemas usam o programa tracepath no lugar do traceroute, exibe uma lista de todos os "hops"(nós de rede) por onde o pacote passará para atingir o host desejado. Por exemplo, para ver a rota tomada para alcançar o uninove.br. Veja o exemplo abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818382/36851.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818382/36851.png)

Na saída acima , podemos ver que a conexão do nosso sistema de teste para uninove.br está passando mais de 11 roteadores. Para os roteadores que forneceram informações de identificação, seus nomes de host, endereços IP e dados de desempenho, que inclui três amostras de tempo de ida e volta do sistema local para o roteador, são mostrados. Para roteadores que não fornecem identificação, que pode ser por causa da configuração do roteador, congestionamento de rede, firewalls, etc., vemos asteriscos como na linha para o hop número 12.

**Ip**

O programa ip é uma ferramenta de configuração de rede multi-usos que faz uso de uma gama de recursos de rede disponíveis nos kernels modernos do Linux. Substitui o anterior e, agora **obsoleto** programa **ifconfig**. Com ip, podemos examinar interfaces de rede de um sistema e a tabela de roteamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818383/36852.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818383/36852.png)

No exemplo acima, vemos que nosso sistema de teste tem cinco interfaces de rede. O primeiro, chamado lo, é a interface de loopback, uma interface virtual que o sistema usa para "falar sozinho em rede". A segunda, chamada eth1, é a interface Ethernet (cabeada). A terceira é uma interface de wi-fi wlan2 e a quinta outra wifi chamada wlx0014d1e600a7. A quarta, que não aparece, existia como um WiFi USB, mas, ao ser excluída, não causou a numeração nova na quinta interface.

Ao realizar diagnósticos de rede, uma das coisas importantes a serem procuradas são a presença da palavra "UP" na primeira linha para cada interface, indicando que a interface de rede está habilitada e a presença de um endereço IP válido no campo inet no o terceira linha de cada interface. Cuidado, não parece ser a terceira linha porque a tela estava curta para informar tudo e as linhas anteriores da interface ficaram quebradas. Para sistemas que usam DHCP (_**Dynamic Host Configuration Protocol**_), um endereço IP válido neste campo irá confirmar se o DHCP está funcionando.

### Netstat

O programa **netstat** é usado para examinar várias configurações de rede e suas estatísticas.Através do uso de suas várias opções, podemos observar muitos recursos em nossa configuração de rede. Usando a opção "-ie", podemos examinar as interfaces de rede em nosso sistema:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818390/36853.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818390/36853.png)

Usando a opção "-r" será exibida a tabela de roteamento da rede do kernel. Isso mostra como oRede está configurada para enviar pacotes de uma rede para outra rede:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818391/36854.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818391/36854.png)

Neste exemplo simples, vemos uma tabela de roteamento típica para uma máquina cliente em uma LAN (_**Local Area Network**_ - Rede Local) por trás de um firewall / roteador. A terceira linha da listagem mostra o destino 192.168.1.0. Endereços IP que terminam em zero referem-se a redes e não hosts/máquinas, então este destino significa qualquer host na LAN 192.168.0.0, ou seja, uma rota para esta rede. É claro que um computador que pertence a uma certa rede (192.168.0.0) também é o caminho (rota) para esta rede. Mais claramente, se um computador está em uma rede, qualquer outro computador que puder alcançá-lo, acessará a rede 192.168.0.0 através dele. O próximo campo, Gateway/Roteador, é nome ou endereço IP do gateway (roteador) usado para ir do host atual para a rede de destino. Um asterisco neste campo indica que nenhum gateway é necessário. Observe que, na primeira linha, aparece um IP neste campo, o IP 192.168.0.1 e que no campo destination/destino apare a palavra “default”. Isto significa que qualquer rede que esteja sendo procurada será resolvida pelo roteador 192.168.0.1, portanto a primeira linha contém o destino padrão. Esta palavra “padrão” para significar “default”, infelizmente, é resultado de uma antiga tradução mal feita do inglês que perpetuou-se na literatura técnica. Para todos os povos da língua inglesa e francesa, a palavra “default” tem o significado de “na falta de…”. Isto significa que qualquer tráfego destinado a uma rede que não esteja listada na tabela (“na falta de…”), deve ir para o roteador onde será encaminhado para o destino. No nosso exemplo, vemos que o gateway é definido como um roteador com o endereço 192.168.0.1, que presumivelmente sabe onde estão as redes procuradas. Como no comando **ip**, o programa **netstat** tem muitas opções e aqui observamos apenas um par delas. Confira as páginas man do ip e netstat para obter uma lista completa de opções.

### Acesso Remoto

Um administrador de redes precisa sempre poder acessar os serviços de rede, gateway e configurações em geral de redes, de qualquer lugar onde estiver. Muitas vezes, quase todas as vezes, os serviços de rede não podem esperar que você volte de algum compromisso ou viagem para que as providências necessárias sejam tomadas. Por muitos anos, os sistemas operacionais Unix-like tiveram a capacidade de serem administrados remotamente através de um acesso de rede. Nos primeiros dias, antes da adoção geral da Internet, existiam alguns programas populares usados para fazer logon em hosts remotos. Exemplos deles foram o Rlogin e o telnet. Esses programas, no entanto, sofrem das mesmas falhas que o programa ftp tem - Eles transmitem todas as suas comunicações (incluindo nomes e senhas) em cleartext. Isto os torna totalmente inapropriados para serem na era da Internet.

SSH

Para resolver este problema (segurança), um novo protocolo chamado SSH (Secure Shell) foi desenvolvido. O SSH resolve os dois problemas básicos da comunicação segura com um host remoto. O primeiro dos problemas é, que o host remoto é quem ele diz ser (evitando assim o chamado "homem do meio"), e o segundo problema, criptografa todas as comunicações entre o computador local e hosts remotos.O SSH consiste de duas partes. Um servidor SSH é executado no host remoto, ouvindo conexões na porta 22, enquanto um cliente SSH é usado no sistema local para comunicar-se com o servidor remoto.A maioria das distribuições Linux enviam uma implementação do SSH chamada OpenSSH do projeto OpenBSD. Algumas distribuições incluem o cliente e os pacotes de servidor padrão (por exemplo, Red Hat/Fedora), enquanto outros (como o Ubuntu) apenas fornecem o cliente. Para um sistema para receber conexões remotas, ele deve ter o servidor OpenSSH instalado, configurado e em execução, e, se o sistema estiver em execução ou estiver após um firewall, deve permitir conexões de rede para a entrada de pacotes na porta TCP 22.[1]

Se você não tiver um sistema remoto para conectar-se nele, mas quiser experimentar estes acessos remotos, certifique-se de que o pacote OpenSSH-server está instalado no seu sistema e use o localhost como o nome do host remoto. Dessa forma, sua máquina criará conexões de rede com um computador remoto que é ele mesmo.

Abaixo o programa cliente SSH é usado para se conectar ao server SSH remoto. Para se conectar a um host remoto chamado LuckyGavNote (o mesmo computador de onde estamos produzindo os exemplos) procedemos como segue:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818393/36855.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818393/36855.png)

Houve uma falha (proposital, é claro). O sistema informa que a conexão não pode ocorrer e foi recusada. A razão é que não há um servidor SSH instalado neste computador. Então vamos aproveitar e mostrar como instalar o servidor.

Veja na figura abaixo a execução da instalação do openssh-server:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818397/36856.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/3/818397/36856.png)

Observe que precisei tornar-me superusuário para poder instalar o pacote.

A tela seguinte mostra a primeira saída do comando. Apresenta pacotes que tornaram-se obsoletos pela instalação anterior de alguns pacotes, mostra quanto precisará de espaço em disco para fazer a instalação e pergunta que o usuário quer prosseguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818405/36857.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818405/36857.png)

Em seguida apresentamos a tela final da instalação, mostrando as tarefas de configuração e preparação para a execução e lançamento do servidor de ssh.

Ao mesmo tempo que é apresentada a tarefa de descompactação dos pacotes e pré-configuração, esta tela mostra que chaves criptografadas públicas foram criadas para que o acesso e a “conversa” entre cliente e servidor sejam protegidas por criptografia.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818406/36858.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818406/36858.png)

Pronto, vamos voltar a ver aquela tentativa de acesso remoto. Não esqueça que estamos fazendo um acesso remoto, mas na própria máquina. Se você quiser provar que “a coisa” funciona mesmo, faça uma nova máquina virtual para acessá-la, mas eu garanto que este acesso é exatamente e honestamente um acesso remoto. Entenda que o sistema operacional não sabe que está acessando o mesmo computador, ele simplesmente utiliza-se dos protocolos de acesso remoto a acessa o computador desejado nos mesmos moldes de uma acesso verdadeiramente remoto. Isto ocorre porque o modelo de referência de rede trabalha em envelopes ou invólucros, ou seja, não interessa o meio de transmissão dos pacotes, nem os controles de transporte, segurança e roteamento, tudo é tratado independentemente em camadas que “entendem” ou “conversam” entre si. Abaixo mostramos a tentativa de acesso:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818407/36859.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818407/36859.png)

Observe tudo o que aconteceu. Primeiro podemos perceber o nome do host a ser acessado, o IP (127.0.1.1) aparece como o IP localhost da máquina remota, mas sabemos que este IP deveria ser o IP 127.0.0.1. Por que aparece 127.0.1.1 ? Simples, o ssh percebe que os IPs são iguais e coloca a máquina remota com outro IP para realizar a comunicação sem conflitos de rede. É claro que esta é a única “estranheza” causada por estarmos acessando a própria máquina como se fosse remota. Nesta linha ainda há a interpretação da ação feita. A frase descrita aqui “fala” que a autenticação do host não pode ser estabelecida. Isto ocorre porque é o primeiro acesso, portanto não houve troca de palavras chave da criptografia. A próxima linha da figura acima mostra qual é a chave que será usada para o estabelecimento da conexão. Em seguida é perguntado se o usuário que continuar com o processo de acesso e avisa que este servidor remoto estará sendo adicionado à lista de hosts conhecidos. Assim, estas etapas de esclarecimento e questionamentos será pulada em acessos futuros. Se por qualquer motivo você precisar “zerar” o host em questão, ou seja, tirá-lo da lista de hosts conhecidos, acesse o arquivo known_hosts e apague as linhas correspondentes ao servidor que quer eliminar. Este arquivo está no subdiretório .ssh (este ponto na frente de “ssh” faz parte do nome do subdiretório e produz o efeito de ocultar o subdiretório, por questões óbvias de segurança). Este subdiretório está dentro do subdiretório do usuário que, por sua vez está dentro do subdiretório “home”. Finalmente, a máquina remota entende que um usuário está fazendo login e já aparece uma requisição de password.

Para sair da máquina remota, use o comando “exit”.

Também é possível conectar a sistemas remotos usando um nome de usuário diferente. Por exemplo, se o usuário local tivesse uma conta chamada "luciano" no sistema remoto, o usuário local poderia logar para a conta luciano no sistema remoto da seguinte maneira:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/9/818947/36860.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/9/818947/36860.png)

Observe que o nome do usuário que pertence à máquina remota deve aparecer antes do nome ou IP da máquina remota e observe, também que o prompt (em verde) está mostrando quem é o usuário que está logado. Se você criou um usuário novo só para fazer este exemplo, não esqueça de removê-lo pois esta é uma brecha comum de segurança, quando criamos usuários só para teste sem planejar a segurança e colocar senhas mais elaboradas, etc.

### Conclusões

Aqui foram apresentados alguns poucos, mas os principais e mais usados comandos de monitoramento e controle de rede. Existem protocolos especiais que contribuem para serviços e servidores de monitoramento de rede os quais serão tratados em tópico específico. Com os comandos mostrados, pode-se garantir 90% do trabalho de diagnose de problemas em redes no dia-a-dia de um administrador de redes.