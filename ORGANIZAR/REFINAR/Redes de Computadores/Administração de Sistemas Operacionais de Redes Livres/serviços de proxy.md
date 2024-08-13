### Introdução:

Proxy não é um protocolo ou uma estrutura que faz parte dos protocolos como ocorre com a família TCP/IP, representada pelo IP, TCP, DNS, SNMP,etc. O Proxy é uma função e, por conseguinte, é realizada por um computador dotado de um software especializado para tanto, um **Servidor Proxy**[1].

Um servidor proxy é um computador dedicado ou um sistema de software executado em um computador que atua como um intermediário entre um dispositivo de um lado, como um computador (por exemplo, o computador no qual você está lendo este estudo) e outro servidor (por exemplo, o servidor no qual eu publiquei este estudo) onde um usuário ou cliente está acessando e solicitando um serviço. O servidor proxy pode existir na mesma máquina que um servidor de firewall ou pode estar em um servidor separado, que encaminha solicitações através do firewall. Da mesma forma, outros serviços podem estar juntos, como o Servidor de Gateway, Servidor Web. Você pode entender melhor com a visão da figura 1.

Uma vantagem de um servidor proxy é que seu **cache** pode servir todos os usuários. Se um ou mais sites da Internet são frequentemente solicitados, estes provavelmente estarão no cache do proxy, o que melhorará o tempo de resposta do usuário. Um proxy também pode registrar suas interações, o que pode ser útil para a solução de problemas.

Veja um exemplo simples de como os servidores proxy funcionam:

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/1/0/9/2/1109295/36612.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/1/0/9/2/1109295/36612.jpg)

Quando um servidor proxy recebe uma solicitação de um recurso da Internet (como uma página da Web), ele (o Proxy) verifica em seu cache local a cópia páginas anteriores, ou seja, páginas que já foram visitadas anteriormente. Se encontrar a página, ela retorna para o usuário sem a necessidade de encaminhar a solicitação para a Internet. Se a página não estiver no cache, o servidor proxy, atuando como um cliente em nome do usuário, usará um de seus próprios endereços IP para solicitar a página do servidor para na Internet. Quando a página é devolvida, o servidor proxy relaciona-a com o pedido original e reencaminha-a para o usuário. Isto é o aspecto de cache da proxy. Ele também é usado para verificar o conteúdo das páginas, por exemplo, verificar se a palavras ?sexo? faz parte da página e, caso seja considerado proibida a pesquisa em sites com esta palavra, o proxy ?barra? (proíbe) a entrega da página.

Os servidores proxy são usados para fins legais e ilegais. Na empresa, um servidor proxy é usado para facilitar a segurança, controle administrativo ou serviços de cache, entre outros propósitos. Em um contexto de computação pessoal, os servidores proxy são usados para permitir a privacidade do usuário e navegação anônima. Os servidores proxy também podem ser usados para a finalidade oposta: Para monitorar o tráfego e minar a privacidade do usuário.

Para o usuário, o servidor proxy é invisível; Todas as solicitações da Internet e respostas retornadas parecem estar enviadas e recebidas diretamente no servidor de Internet endereçado. O proxy não é realmente invisível, seu endereço IP deve ser especificado como uma opção de configuração no seu navegador ou outro programa de protocolo. Isto é feito automaticamente pelas diretivas de segurança, no caso do Windows, impostas pelo AD (_**Active Directory**_). Por outro lado, podemos forçar, através de um firewall, a transparência do proxy[1].

Os usuários podem acessar proxies online na internet (você contrata-os) ou configurar navegadores web para usar constantemente um servidor proxy de sua própria rede. As configurações do navegador incluem opções manuais e automaticamente detectadas para proxies HTTP, SSL, FTP e SOCKS. Os servidores proxy podem servir muitos usuários ou apenas um por servidor. Essas opções são chamadas proxies compartilhados e dedicados, respectivamente. Há uma série de razões para se usar proxies e, portanto, vários tipos de servidores proxy, são, muitas vezes, classificados em em categorias sobrepostas.

### Servidores Proxy Diretos e Reversos

Os proxies **diretos** enviam os pedidos de um cliente para um servidor web. Os usuários acessam os proxies diretos navegando diretamente por um endereço de proxy da web ou configurando as configurações de Internet apontando para um proxy específico local. Os proxies diretos permitem a evasão de firewalls (você pode estar pulando o firewall) e aumentam a privacidade e a segurança de um usuário, mas às vezes podem ser usados para baixar materiais ilegais, como materiais protegidos por direitos autorais ou sites ilícitos de qualquer natureza[1].

Os proxies **reversos** tratam de forma transparente todas as solicitações de recursos nos servidores de destino sem exigir nenhuma ação por parte do solicitante.

Os Proxies reversos são usados para:

- Ativar o acesso indireto quando um site não permite conexões diretas como uma medida de segurança.
- Permitir o balanceamento de carga entre servers.
- Transmitir conteúdo interno para usuários da Internet.
- Desativar o acesso a um site, por exemplo, quando um ISP (_Internet Service Provider_) ou o governo deseja bloquear um site.

Os sites podem ser bloqueados por razões **mais ou menos** legítimas. Proxies **reversos** podem ser usados para impedir o acesso a conteúdos imorais, ilegais ou protegidos por direitos autorais. Às vezes, essas razões são justificáveis, mas às vezes a justificativa é duvidosa. Proxies inversos às vezes impedem sites de notícias de acesso onde os usuários podem visualizar informações vazadas. Eles também podem impedir que os usuários acessem sites onde possam divulgar informações sobre ações do governo ou da indústria. O bloqueio do acesso a esses sites pode violar os direitos de liberdade de expressão (este é um campo um tanto nebuloso, pois será que uma empresa não pode decidir o que o usuário pode acessar de sua própria rede?).

### Outros tipos de Proxies

Proxies **transparentes** são normalmente encontrados perto, ou junto, da saída/gateway de uma rede corporativa. Estes proxies centralizam o tráfego de rede. Em redes corporativas, um servidor proxy está associado a, ou faz parte de, um servidor de gateway que separa a rede local das redes externas (normalmente a Internet) e um firewall que protege a rede contra intrusões externas e permite que os dados sejam verificados por segurança antes da entrega a um cliente na rede. Esses proxies ajudam a monitorar e administrar o tráfego de rede, já que os computadores em uma rede corporativa são geralmente dispositivos seguros que não precisam de anonimato para tarefas tipicamente do dia-a-dia[1].

Proxies **anônimos** escondem o endereço IP do cliente, permitindo que eles acessem materiais bloqueados por firewalls ou contornem as proibições de endereços IP. Eles podem ser usados para maior **privacidade** e/ou **proteção contra-ataques**.

Proxies altamente anônimos escondem até o fato de que eles estão sendo usados por clientes e apresentam um endereço IP público sem proxy. Assim, ele não só esconde o endereço IP do cliente, usando-os, eles também permitem o acesso a sites que podem **bloquear os servidores proxy**. Exemplos de proxies altamente anônimos incluem **I2P** e **TOR**.

Os proxies **Socks 4 e 5** fornecem um serviço de proxy para dados UDP e operações de consulta de DNS, além do tráfego da Web. Alguns servidores proxy oferecem ambos os protocolos Socks.

Proxies de **DNS** enviam solicitações de serviço de nome de domínio (DNS) de LANs (_**Local Area Networks**_ - Redes locais) para servidores de DNS da Internet enquanto gravam no cache para melhor a velocidades em consultas futuras.

### Proxy hacking

No hacking de proxy, um invasor tenta roubar cópias de uma página da web autêntica no índice de um mecanismo de pesquisa e nas páginas de resultados da pesquisa. O hacker proxy teria um outro site fraudulento emulando o original ou o que quer que eles quiserem (arquivos, formulários) para mostrar aos clientes solicitantes da página.

Veja como funciona: O invasor cria uma cópia da página da Web segmentada em um servidor proxy e usa métodos como preenchimento de palavra-chave e vinculação à página copiada de sites externos para aumentar artificialmente o ranking do mecanismo de pesquisa. A página autêntica terá ranking inferior e pode ser vista como conteúdo duplicado (porque vem depois na lista de sites pesquisados), caso em que um mecanismo de pesquisa pode removê-lo de seu índice.

Esta forma de _**hacking**_ também pode ser usada para entregar páginas com intenção maliciosa. A pirataria de proxy pode direcionar os usuários para o site bancário falso, por exemplo, para roubar informações da conta que podem ser vendidas ou usadas para roubar fundos da conta. O atacante também pode usar o _**hack**_ para direcionar os usuários para um site infectado por _**malware**_ para comprometer suas máquinas para uma variedade de propósitos ilegais[1].

Alguns meios foram desenvolvidos para comprometer as habilidades do proxy. Aplicativos Flash e Java especialmente criados, Javascript, Active X e alguns outros plugins do navegador podem ser usados para revelar a identidade de um usuário proxy, portanto proxies não devem ser usados em sites não confiáveis ou em qualquer lugar em que o anonimato seja importante.

Proprietários de sites que suspeitam que tenham sido vítimas de um _**hack**_ proxy pode testar a teoria, procurando uma frase que seria quase única na identificação de seu site. Seu site deve ser proeminente (aparecer primeiro) na página de resultados do mecanismo de busca (SERP - _**search engine results page**_). Se um segundo site com o mesmo conteúdo aparecer, ele pode ser uma página **hakeada** proxy.

Os servidores proxy em muitas formas aumentam a segurança, mas como muitas coisas na computação podem ser vulneráveis. Para evitar ataques DoS e invasão de rede, os administradores devem manter o software atualizado, usar o balanceamento de carga, impor autorização e autenticação seguras e bloquear tráfego não solicitado, proxies maliciosos e proxies abertos[1].

### Instalando um Proxy no Ubuntu

Há muitas razões pelas quais você pode querer aprender a configurar um servidor proxy no Ubuntu Linux para encaminhar o tráfego do seu navegador. Talvez você esteja navegando em uma rede sem fio e sem segurança, ou talvez você não queira que o chefe no trabalho veja onde você está passeando na Internet. Seja qual for a sua razão, é bastante simples hoje em dia, desde que você tenha alguns conhecimentos básicos será capaz de criar um sistema proxy em sua máquina seguindo as orientações aqui apresentadas.

Vamos utilizar o **Squid-ProxyServer**, talvez o mais conhecido e útil proxy para ambiente Linux. O Squid é um aplicativo de servidor proxy completo que fornece serviços de proxy e cache para o protocolo de transporte de hipertexto (HTTP), protocolo de transferência de arquivos (FTP) e outros protocolos de rede populares. O Squid pode implementar cache e proxy de solicitações SSL (Secure Sockets Layer) e cache de pesquisas de DNS (Domain Name Server), e realizar cache/proxy transparente. O Squid também suporta uma grande variedade de protocolos de cache, como o ICP (Internet Cache Protocol), o Hyper Text Caching Protocol (HTCP), o Cache Array Routing Protocol (CARP) e o Web Cache Coordination Protocol (WCCP) [2].

O servidor de cache de proxy Squid é uma excelente solução para uma variedade de necessidades de servidores de proxy e é escalável para uso doméstico até nível de redes corporativas, fornecendo mecanismos de controle de acesso extenso e granular e monitoramento de parâmetros críticos de rede através do _**Simple Network Management Protocol**_ **(SNMP)**.

### Instalação

Vamos começar com o comando abaixo: **(Não esqueça de trabalhar como superusuário)**

**\#apt-get install squid**

Esta é a primeira tela que aparecer ao executar o comando acima:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835221/36613.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835221/36613.png)

Fonte:

Pode optar por “S” de sim ou “Y” de yes, para dar continuidade.

O Squid é configurado editando as diretrizes contidas no arquivo de configuração **/etc/squid/squid.conf**. Os exemplos a seguir ilustram algumas das diretivas que podem ser modificadas para afetar o comportamento do servidor Squid. Para obter uma configuração mais detalhada do Squid, consulte as referências de **www.squid-cache.org.**

Antes de editar o arquivo de configuração, você deve fazer uma cópia do arquivo original e protegê-lo de escrita/sobre escrita para que você tenha as configurações originais como referência e reutilizar conforme necessário, em caso de desastres na sua configuração (acredite, isto acontece). Faça esta cópia e proteja-a da escrita usando os seguintes comandos:

**\#cp /etc/squid/squid.conf /etc/squid/squid.conf.original**

**\#chmod a-w /etc/squid/squid.conf.original**

Agora abra o arquivo de configuração **/etc/squid/squid.conf** com um editor como, por exemplo, o comando abaixo:

**\#vim /etc/squid/squid.conf**

Para configurar seu servidor Squid para escutar na porta TCP **8181** em vez da porta TCP padrão **3128**, altere a diretiva **http_port** como tal:

**http_port 8181**

Veja como fica no arquivo de configuração:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835225/36614.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835225/36614.png)

Fonte:

Altere a diretiva visible_hostname para dar ao servidor Squid um nome de host específico. Esse nome de host não precisa necessariamente ser o nome de host do computador. Coloquei **luckyproxy.**

  **visible_hostname luckyproxy**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835232/36615.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835232/36615.png)

Fonte:

Usando o controle de acesso do Squid, você pode configurar o uso de serviços da Internet protegidos pelo Squid para estarem disponíveis apenas aos usuários com determinados endereços IP (Internet Protocol). Por exemplo, mostrarei o acesso de usuários da sub-rede **192.168.0.0/24** somente:

Adicione o seguinte no final da seção ACL do seu arquivo **/etc/squid/squid.conf**:

**acl rede_exemplo src 192.168.0.0/24**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835236/36616.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835236/36616.png)

Fonte:

Em seguida, adicione o seguinte ao topo da seção http_access do seu arquivo **/etc/squid/squid.conf**:

 **http_access allow rede_exemplo**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835318/36617.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835318/36617.png)

Fonte:

Usando os esses recursos de controle de acesso do Squid, você pode configurar o uso de serviços de Internet protegidos pelo Squid para estar disponível somente durante o horário comercial normal. Por exemplo, vamos ilustrar o acesso de funcionários de uma empresa que está operando entre as 8h e as 18h, de segunda a sexta-feira, e que usa a sub-rede 192.168.0.0/24:

Adicione o seguinte no final da seção ACL do seu arquivo **/etc/squid/squid.conf:**

**acl rede_exemplo src 192.168.0.0/24 ** Esta parte já fizemos!! ******

**acl horario_exemplo time M T W T F 9:00-17:00**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835320/36618.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835320/36618.png)

Fonte:

Em seguida, adicione o seguinte ao topo da seção http_access do seu arquivo **/etc/squid/squid.conf:**

**http_access allow rede_exemplo horario_exemplo**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835321/36619.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835321/36619.png)

Fonte:

Depois de fazer alterações no arquivo **/etc/squid/squid.conf**, salve o arquivo e reinicie o aplicativo do servidor squid para efetuar as alterações usando o seguinte comando inserido em um prompt do terminal:

**\#systemctl restart squid.service**

**E, verificando o status**

**\#systemctl status squid.service**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835322/36620.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835322/36620.png)

Fonte:

**Squid funcionado!!!**

**Nota Importante: Você percebeu na figura anterior a diretiva:**

**http_access** **deny all**

O que isto quer dizer? Veja que ela vem depois de liberarmos a rede para uso no horário comercial. **Aqui vem a coisa mais importante sobre ACLs** (Access Lists), quando você trabalha com ACLs, seja no proxy ou em firewall, roteadores, etc. primeiro você coloca a regra particular de depois, por último a generalização. É o único jeito de funcionar. Então o **http_access deny all** significa sim que tudo está proibido para todos menos para aquela regra que colocamos antes, quando avisamos que, para a rede 192.168.0.0/24 durante os dias comerciais e horários comerciais, o http está liberado através da última diretiva que diz **http_access allow rede_exemplo horario_exemplo.** Entendeu?

### Conclusões

Agora você pode perceber que preparar um proxy não é tão complicado. Neste momento se você colocar nos brownsers (Internet Explorer, Firefox, Chrome,etc.) em qualquer máquina de sua rede, Windows, ou Linux, não interessa, elas vão solicitar tudo e receber tudo da máquina proxy e, agora, eles obedecerão estas regras que colocamos.

Veja um exemplo de como fazemos isto em uma máquina Windows com o browser **Chrome**, abaixo:

Entrar em **Configurações/Mostrar configurações avançadas/Rede/Alterar configurações de proxy/Configurações da LAN**. Marque a opção “**Usar um servidor proxy …**” e preencha no campo “**Endereço**” o IP de nosso servidor proxy (**192.168.0.10**) e preencha o campo “**Porta**” o número da porta designada em nossa instalação (**8181**, lembra?). Pronto o Chrome vai usar este proxy.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835324/36621.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835324/36621.png)

Fonte:

Por outro lado, falamos sobre o Proxy Transparente, isto é, não precisar colocar estas informações sobre proxy nos brownsers. Por que não coloquei aqui? Simples, esta tarefa não é da configuração do proxy e sim do firewall. Consiste em desviar o tráfego das portas 80 para a porta 8181 (no nosso exemplo). Podemos ver isto em um estudo específico sobre firewalls.