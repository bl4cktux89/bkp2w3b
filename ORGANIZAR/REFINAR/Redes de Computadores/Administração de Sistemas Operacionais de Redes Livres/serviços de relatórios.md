### Introdução

Hoje em dia as empresas, mesmo no uso doméstico, preferem trabalhar com menos impressoras para minimizar os custos de manutenção e o tempo perdido com os consumos de expediente das impressoras. No ambiente Linux existem dois grandes gerenciadores de impressora. O primeiro e mais elaborado é o CUPS [1].

### CUPS - Servidor de impressão

O principal mecanismo para impressão e serviços de impressão do Ubuntu é o Sistema Comum de Impressão UNIX (**CUPS** - _**Common UNIX Printing System**_). Este sistema de impressão é uma camada de impressão portátil disponível gratuitamente, que se tornou o novo padrão para impressão na maioria das distribuições Linux.O CUPS gerencia trabalhos de impressão e filas e fornece impressão em rede usando o IPP (_**Internet Printing Protocol**_) padrão, oferecendo suporte para uma grande variedade de impressoras, das matriciais até a laser entre muitas outras. O CUPS também suporta _**PostScript Printer Description**_ (PPD) e detecção automática de impressoras de rede e apresenta uma ferramenta simples de configuração e administração baseada na Web [2].

Antes de entender como se instala o CUPS, vamos falar um pouco sobre o seu funcionamento.

### CUPS em redes heterogêneas

Com CUPS e algum software livre adicional pode-se configurar um servidor de impressão universal, para a recepção de trabalhos, bem como a transmissão de quase todos os tipos de conexões de impressora e quase todos os protocolos de impressão em rede suportados.

CUPS não só pode receber trabalhos de aplicativos locais, como oferece seu protocolo nativo IPP também ao mundo exterior, para que os clientes de impressão enviem trabalhos pelos meios de transmissão. Com daemons adicionais, quase todos os outros protocolos de impressão estão disponíveis na extremidade receptora: LPD (Unix), SMB (Windows), E AppleTalk (MacOS).

O CUPS imprime na maioria dos tipos de impressoras conectadas localmente: Impressoras em portas paralelas, USB, serial e IEEE 1394, impressoras SCSI e até mesmo em dispositivos multifuncionais da HP usando HPOJ. Impressoras conectadas diretamente à rede ou conectadas a servidores remotos são acessíveis com os protocolos TCP / Socket (HP JetDirect ou similar), IPP, LPD, SMB e AppleTalk [1].

CUPS pode ser facilmente expandido para lidar com outros protocolos. Para suportar outro tipo de destino para onde os trabalhos de impressão podem ser enviados, basta escrever um novo back-end CUPS. Backends podem até ser escritos ou em shell scripts ou Perl. Depois de o ter escrito, torná-lo "executável para o resto dos usuários", coloque-o no diretório **/usr/lib/cups/backend/**, reinicie o CUPS e configure uma fila de impressão usando-o. Como o back-end tem que ser parecido para funcionar com o CUPS é descrito no "Manual de Programadores de Software CUPS" no capítulo "Escrevendo Backends" (http://www.cups.org/spm.html\#WRITING_BACKENDS). Se você quiser fazer seu servidor de impressão escutando um protocolo ainda não suportado, você precisa gravar um daemon ouvindo esse protocolo e acessando o CUPS através das ferramentas usuais de linha de comando ("lpr", "lpq", "lpstat", etc. ...) ou através da biblioteca CUPS. Você encontra informações da API para a biblioteca CUPS no "Manual do programador de software CUPS" no capítulo "A API CUPS" ([**http://www.cups.org/spm.html#CUPS_API**](http://www.cups.org/spm.html#CUPS_API)) [1].

### IPP - Protocolo de impressão via Internet

O **IPP -** _**Internet printing protocol**_ é o protocolo nativo do CUPS: Portanto, nenhum daemon extra é necessário para receber trabalhos de impressão IPP. O daemon CUPS atende as solicitações IPP na porta 631. A porta 631 é a porta padrão para o IPP. Dependendo de sua configuração, ele também aceita o IPP criptografado por SSL, geralmente na porta SSL 443. Os clientes IPP podem ser outras máquinas rodando GNU/Linux, Unix ou MacOS X (a partir da versão 10.2) com CUPS. Máquinas com outros sistemas operacionais podem ter um built-in IPP: como o Windows 98SE, ME, 2000 e XP. Para outras versões do Windows, a Microsoft fornece complementos gratuitos. No cliente é preciso usar:

  **Ipp: // : 631 / impressoras /**

Ou   **http: // : 631 / impressoras /**

Como URI (Unified Resource Identifier)/endereço de destino. Para conexão criptografada por SSL, é preciso usar:

  **https: // : 443 / impressoras /**

Mas tanto o servidor como o cliente devem suportá-lo.

CUPS tem ainda uma funcionalidade adicional: Pela primeira vez, IPP é construído sobre o protocolo HTTP. Isso significa que o CUPS também é um servidor HTTP. Quando você insere os URIs acima em um navegador da web normal, você entra em sua interface web. Aqui você pode ver o status da impressora (trabalhos, erros, ...) e configurar sua impressora. Além disso, você pode adicionar e remover impressoras gerenciar trabalhos, ler a documentação e muito mais através desta interface da web do CUPS.  Basta começar:

  **http: // : 631 /**

Para acesso não criptografado ou

**https: // : 443 /**

Quando você tem suporte ao acesso criptografado.

Se você tiver clientes CUPS, poderá ativar a facilidade de "navegação" do seu servidor CUPS. Desta forma, os clientes irão "ver" as impressoras no servidor automaticamente. Os administradores não precisam fazer nenhuma configuração nos clientes quando ativam a "navegação".

Se você tiver outros clientes e quiser imprimir em PostScript a partir deles, muitas vezes o driver de impressora pode usar um arquivo "PPD" (_**PostScript Printer Description**_) para suporte completo dos recursos das impressoras. Você pode baixar os arquivos PPD para qualquer impressora configurada a partir do servidor CUPS:   **http: // : 631 / impressoras / .ppd**

Ou   **https: // : 443 / impressoras / .ppd**

### Clientes LPD Unix

Muitos sistemas Unix e GNU/Linux usam o sistema de impressão LPD (às vezes também chamado de LPR) ou uma das variantes LPD melhoradas LPRng ou GNUlpr. Claro que é possível converter esses sistemas para CUPS. Mas no caso de você não querer isso, você pode configurar CUPS para aceitar trabalhos enviados a partir desses clientes.

O suporte CUPS para clientes baseados em LPD suporta todas as funções básicas para impressão com êxito. Com o LPD, é possível imprimir arquivos em impressoras específicas, listar o status da fila e assim por diante. No entanto, a configuração automática do cliente e as opções da impressora não são possíveis através do protocolo LPD. Assim, com os clientes LPD, você precisa configurar manualmente cada cliente para as impressoras que precisa acessar.

O mini-daemon "cups-lpd" oferece suporte para clientes LPD e pode ser usado a partir dos daemons "inetd" ou "xinetd". Adicione a seguinte linha ao arquivo /etc/inetd.conf. Ele habilita o suporte LPD em seu servidor através do daemon "inetd":

**printer stream tcp nowait lp /usr/lib/cups/daemon/cups-lpd cups-lpd \**

**-o document-format=application/octet-stream**

Digite esta é uma linha, sem a barra invertida. Adapte o caminho para "cups-lpd" de acordo com a sua instalação.

Depois de adicionar esta linha, dê um restart na rede para que o "inetd" reler sua configuração:

 **killall -HUP inetd**

Se você estiver usando o daemon "xinetd", crie um arquivo chamado **/etc/xinetd.d/cups-lpd**. Deve conter as seguintes linhas:

**service printer**

**{**    **socket_type = stream**    **protocol = tcp**    **wait = no**    **user = lp**    **server = /usr/lib/cups/daemon/cups-lpd**    **server_args = -o document-format=application/octet-stream****}**

O daemon "xinetd" lê automaticamente o novo arquivo de configuração e habilita o suporte à impressão LPD. Algumas distribuições do sistema operacional já possuem um arquivo /etc/xinetd.d/cups-lpd, mas pode ser desativado por uma linha contendo " **= no**" para ativar o arquivo.

O parâmetro "-o document-format = application / octet-stream" mostrado nos exemplos é opcional. Faz com que o CUPS ignore a informação de tipo mime que o cliente pode enviar com o **printjob**. Isso força o CUPS a detectar automaticamente o tipo de arquivo e pré-processar o arquivo de acordo. Você pode remover a opção se isso causar problemas para você.

Aviso de segurança: "cups-lpd" atualmente não executa qualquer controle de acesso com base nas configurações em /etc/cups/cupsd.conf ou nos arquivos /etc/hosts.allow ou /etc/hosts.deny usados pelos TCP wrappers (controladores ACL - Access list). Portanto, executar "cups-lpd" no seu servidor permitirá que qualquer computador em sua rede (e talvez toda a Internet) possa imprimir em seu servidor.

Enquanto "xinetd" tem suporte de controle de acesso embutido, você deve usar o pacote TCP wrappers com "inetd" para limitar o acesso a apenas os computadores que devem ser capazes de imprimir através do servidor.

Consulte também as páginas man para "cups-lpd", "inetd" e "xinetd" para obter mais informações.

### Clientes SMB / CIFS - Windows

Em muitas redes GNU/Linux ou Unix é usado principalmente como sistema operacional de servidor. Na maioria das empresas, a maioria das estações de trabalho ainda estão executando o Windows. Para esses, o servidor deve emular o comportamento de um servidor de impressão do Windows. Especialmente a facilidade de varredura de rede do Windows deve encontrar as impressoras. Sob drivers de impressora do Windows muitas vezes são executados no lado do cliente, mas são oferecidos pelos servidores para download e instalação semiautomática. É muito conveniente ter esses recursos "Point and Print" para clientes Windows a partir de um servidor CUPS.

O próprio pacote CUPS não precisa fornecer essa funcionalidade em si. Pode contar aqui com o pacote gratuito Samba ([**http://www.samba.org/**](http://www.samba.org/)). E esta é a segunda forma que eu estava falando na introdução. Então CUPS e SAMBA são as duas formas de servir impressão em rede e na WEB.

Ao instalar o Samba, certifique-se de que ele é compilado com o suporte do CUPS. Verifique se o comando "**ldd que smbd tem libcups ? em** sua saída.

Para configurar o SAMBA para CUPS, edite o arquivo smb.conf (No diretório /etc ou / etc samba). Na seção "[global]" substitua as linhas "printing" e "printcap" existentes com:

**printing = cups**

**printcap name = cups**

Não é necessário definir comandos de impressão ou de manipulação de trabalhos (como lpq ou lprm). O Samba chama as funções de biblioteca do CUPS ao receber um **printjob** de clientes Windows. Portanto, ignora quaisquer definições de comando definidas de outra forma no smb.conf.

Isso é tudo que há para ele! Os usuários remotos agora poderão navegar e imprimir em impressoras em seu sistema.

O Samba também pode disponibilizar drivers de impressora Windows para que os clientes possam baixá-los e instalá-los automaticamente. Veja mais sobre isso no site do SAMBA.

### Instalando CUPS

Para instalar o CUPS no seu computador Ubuntu, basta usar sudo (também você pode usar o superusuário) com o comando apt-get e dar os pacotes para instalar como o primeiro parâmetro. Uma instalação completa do CUPS tem muitas dependências de pacotes, mas todas podem ser especificadas na mesma linha de comando. Digite o seguinte em um prompt do terminal para instalar o CUPS:

**\#apt-get install cups**

Após a autenticação com sua senha de usuário, os pacotes devem ser baixados e instalados sem erros. Após a conclusão da instalação, o servidor CUPS será iniciado automaticamente.

Para solucionar problemas, você pode acessar os erros do servidor CUPS através do arquivo de log de erro em: **/var/log/cups/error_log**. Se o log de erros não mostrar informações suficientes para solucionar quaisquer problemas encontrados, a verbosidade do log do CUPS pode ser aumentada alterando a diretiva LogLevel no arquivo de configuração (discutido abaixo) para "depurar" ou até mesmo usar o "debug2", que registra tudo, a partir do padrão de "info". Se você fizer essa alteração, lembre-se de alterá-la novamente uma vez que você resolveu o problema, para evitar que o arquivo de log se torne excessivamente grande.

### Configuração

O comportamento do servidor do Sistema de Impressão Comum UNIX é configurado através das diretrizes contidas no arquivo **/etc/cups/cupsd.conf**. O arquivo de configuração do CUPS segue a mesma sintaxe que o arquivo de configuração primário para o servidor HTTP Apache, portanto os leitores familiarizados com a edição do arquivo de configuração do Apache devem se sentir à vontade durante a edição do arquivo de configuração do CUPS. Alguns exemplos de configurações que você pode querer mudar inicialmente serão apresentados mais adiante.

Antes de editar o arquivo de configuração, você deve fazer uma cópia do arquivo original e protegê-lo de gravação, para que você tenha as configurações originais como uma referência e reutilizar conforme necessário. Copie o arquivo **/etc/cups/cupsd.conf** e proteja-o contra gravação com os seguintes comandos, digitados no prompt do terminal:

**\#cp /etc/cups/cupsd.conf /etc/cups/cupsd.conf.original**

**\#chmod a-w /etc/cups/cupsd.conf.original**

**ServerAdmin**: Para configurar o endereço de e-mail do administrador designado do servidor CUPS, basta editar o arquivo de configuração /etc/cups/cupsd.conf com o editor de texto preferido e adicionar ou modificar a linha **ServerAdmin** de acordo. Veja como ficou para meu endereço que é luckygav@luckygav.net.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822064/36722.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822064/36722.png)

**Listen**: Por padrão no Ubuntu, a instalação do servidor CUPS só escuta na interface loopback no endereço IP 127.0.0.1. Para instruir o servidor CUPS a escutar no endereço IP de um adaptador de rede real, você deve especificar um nome de host, o endereço IP ou, opcionalmente, um emparelhamento de endereço / porta IP através da adição de uma diretiva de escuta. Por exemplo, se seu servidor CUPS reside em uma rede local com hostname LuckyGavNote e você gostaria de torná-lo acessível para os outros sistemas nesta sub-rede, você iria editar o /etc/cups/cupsd.conf e adicionar uma diretiva **Listen**, como aparece na figura anterior.

No exemplo acima, você pode comentar ou remover a referência para o endereço Loopback (127.0.0.1) se você não quiser que o cupsd escute nessa interface, mas preferiria que apenas escute nas interfaces Ethernet da Rede de Área Local (LAN). Para ativar a escuta de todas as interfaces de rede para as quais um determinado nome de host está vinculado, incluindo o Loopback, você pode criar uma entrada de escuta para o nome de host Atatruk como tal:

**Listen Atatruk:631  # Ouve as interfaces de Atatruk.**

Ou omitindo a diretiva Listen e usando, em vez disso, a diretiva Port como abaixo. Na verdade, vamos deixar o nosso assim. É mais genérico para testes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822073/36723.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822073/36723.png)

Sempre que você fizer alterações no arquivo de configuração **/etc/cups/cupsd.conf,** você precisará reiniciar o servidor CUPS digitando o seguinte comando em um prompt do terminal:

**\#systemctl restart cups.service**

Depois veja como ficou o status do serviço.

**\#systemctl status cups.service**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822077/36724.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822077/36724.png)

O CUPS pode ser configurado e monitorado usando uma interface web, que por padrão está disponível em http://localhost: 631/admin. A interface da Web pode ser usada para executar todas as tarefas de gerenciamento da impressora.

Para executar tarefas administrativas através da interface web, você deve ter a conta raiz habilitada no servidor ou autenticar-se como um usuário no grupo **lpadmin**. Por motivos de segurança, o CUPS não autenticará um usuário que não tenha uma senha.

Para adicionar um usuário ao grupo lpadmin, execute no prompt do terminal:

**\#usermod -aG nome-de-usuário lpadmin**

Veja como foi feito no meu exemplo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822079/36725.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822079/36725.png)

Digitando a URL: 127.0.0.1:631 abrirá o gerenciamento CUPS em sua máquina:

Primeiro a Tela HOME:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822086/36726.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822086/36726.png)

Nesta tela aparece toda a documentação para usuários CUPS, administradores e desenvolvedores. É um material muito rico e vale a pena ser explorado.

Optando pelo menu Administration, vemos a seguinte tela:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822091/36727.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822091/36727.png)

Desta tela de administração pode-se fazer de tudo. Alterar a configuração, adicionar printers, gerenciar as printers já adicionadas, etc. Também é possível observar, cancelar, pausar os JOBS, as impressões que estão nas filas das impressoras. Vamos optar por gerenciar impressoras e ver a única que está conectada à minha máquina:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822093/36728.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822093/36728.png)

Solicitando a opção **Manage Jobs,** para gerenciar os serviços solicitados de impressão e em seguida, a opção Show **Completed Jobs t**emos uma amostra das impressões controladas pelo CUPS, como vemos abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822096/36729.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822096/36729.png)

Bom, não vamos ficar vendo todos os detalhes aqui, mas você pode e deve explorar as possibilidades para poder gerenciar impressores profissionalmente em sua empresa.

Agora você pode ir nas máquinas Windows e abrir **Painel de Controle -> Impressoras e Fax-> Adicionar impressora de rede** e ver a tela abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822099/36730.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/0/822099/36730.png)

Onde SERVER é o hostname de seu servidor Linux. Você podia também apenas procurar a impressora que ela seria ofertada na lista.

### Conclusão

É fácil colocar um servidor de impressão para servir à rede de uma empresa, ou mesmo doméstica. Você pode fazê-lo com o CUPS e com o SAMBA. Como o CUPS temos um controle mais forte das impressoras, e dos jobs, mas com o Samba temos integração perfeita com usuários, controle de domínio e uma relação com Windows transparente através do SMB. No entanto para o SAMBA poder ter todo seu poder, é necessário que CUPS esteja ativo. Já o CUPS não precisa de mais nada, apenas a si mesmo.