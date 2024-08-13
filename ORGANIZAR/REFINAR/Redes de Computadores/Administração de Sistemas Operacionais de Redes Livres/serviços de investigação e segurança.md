### Introdução

Quando falamos em investigação e segurança, estamos falando de métodos e procedimentos aceitos para apreender adequadamente, salvaguardar, analisar dados e determinar o que acontece nos computadores. Informações processáveis para lidar com casos de sinistro e casos forenses de um computador. Passos repetitivos e eficazes. É uma boa maneira de descrever a metodologia que seria ideal para proteção e descoberta de situações já ocorridas. Uma série de ações ajudarão o investigador a manter-se na pista e assegurar a apresentação apropriada da evidência de uma invasão ou roubo de informações do computador para o caso criminal ou civil no tribunal, nos processos legais e nas ações disciplinares internas, no manuseio dos incidentes do malware e em problemas operacionais incomuns. Além disso, definir, como o fizemos acima, o que compreende a investigação e segurança, é um bom ponto de partida para ter um conhecimento razoável de princípios, diretrizes, procedimentos, ferramentas e técnicas de segurança [1].

Vamos começar com:  O que poderíamos fazer para implementar segurança, depois como oferecer segurança como serviço e, por fim, como são feitas as investigações. **Não** vamos falar de backups, espelhamento, RAID, ou outras tecnologias que versam sobre a proteção através da garantia de não perda.  Mas, do que estamos falando?

Claro que, depois de algum incidente, existem uma variedade de estados operacionais, ou seja, o sistema não caiu e/ou os dados não foram roubados e/ou não existem usuários escondidos acessando o sistema, mas, houve algo, houve uma tentativa. OU, de fato, houve queda dos sistemas e/ou houve roubo de dados e/ou existe algum usuário escondido acessando remotamente o sistema. Qualquer um dos estados foi causado por um incidente.

Veja bem, às vezes a segurança foi perfeita, pois evitou o sucesso de um ataque, mas mesmo assim houve incidentes. A investigação do incidente pode ajudar a prever futuras tentativas após o ataque. Existem dois lados: Do atacante e do atacado.

Pequena pausa para uma explicação: Vamos chamar de ?atacante? e ?atacado?. Pronto! Neste texto não ficaremos com aqueles preciosismos de definir ?vítima? ou pior, diferenciar o ?hacker? do ?cracker? ou chamar de ?white hat? ou ?black hat?.  O que importa aqui é você saber que um atacante bem-sucedido é: Alguém que não sabe muito, mas encontrou um sistema totalmente mal preparado e usou uma ferramenta que baixou da internet **ou** é alguém que estudou profundamente os protocolos (lembra aquelas **RFC?s**: _**Request for comments**_) e sabe como fazer uso deles, além de verificar os programas comerciais com profundidade para achar brechas. Entenda também que este é um estudo para administração de redes. Algo mais especialista de segurança de redes deve ser tratado em estudos especialistas.

Algumas vezes o ataque foi malsucedido para quem recebeu o ataque, mas, bem-sucedido para quem atacou. O que significa isto? Que estranho? Sim, neste caso o atacante atacou algo que ele sabia, ou não, estar protegido, mas o objetivo não era o ataque principal. O atacante queria outra coisa. Vamos dizer que o atacante tentou logar remotamente como ?root? em seu sistema. Claro que você já protegeu seus sistemas disto. Nem você mesmo entra como ?root? remotamente. É uma das primeiras regras de segurança que você vai ver aqui (isto está publicado até no manual dos escoteiros mirins). Você olha na log do sistema (syslog) e sorri feliz. Conta para o colega ao lado, veja que tolo (você não fala bem isto!), tentando me atacar com esta idiotice! Haha! Mas, o atacante conseguiu as informações que precisava nas respostas negativas do sistema. Ou recebeu a informação diretamente do sistema operacional ou da questão do que também se chama de ?Engenharia Social?, o atacante apenas atacou para saber o ?estilo de segurança? do atacado. O atacante pode usar sua experiência para identificar estilos de profissionais e saber onde eles pecam! Por outro lado, com a mesma modernidade que a GOOGLE descobre que você deve estar interessado em comprar um cachorrinho cor de rosa, o atacante pode usar AI (**Artificial Intelligence**) para entender seus estilos e erros. Por outro lado, você pode ser um atacado experto e também usar os ataques para entender o perfil do atacante!! Você também pode ser um atacante?!!!!, mas o que eu posso fazer!

Tocando levemente no assunto, depois poderemos aprofundar melhor, como os ataques existem? Talvez você fique imaginando isto. Não no sentido de qual o motivo de alguém querer atacar seu sistema, pois isto não vamos gastar mais que três linhas neste estudo, não é o objetivo. Aqui o que interessa saber é: **Por que os ataques são possíveis?**

Antes da missão verdadeira deste estudo vamos à primeira pergunta (muito, muito mesmo, sucintamente): Por que alguém iria atacar seu sistema? As respostas são muitas. A razão mais comum (na sua cabeça e de toda a grande maioria da população) é: Roubar as suas senhas. Principalmente as senhas de contas bancárias. É, esta é uma das razões comuns, mas saiba que estes ataques são os mais medíocres. Geralmente executados por vírus (**vírus**), ou cavalos-de-tróia (os famosos **trojans**), páginas falsas de sites (_**fake pages**_) e, em geral, apetrechos de mesma natureza. Noutro parágrafo, qual estiver respondendo à pergunta: Por que os ataques são possíveis? Eu explico melhor isto. Bem, como falei, estes ataques são medíocres, mas funcionam. O que a maioria das pessoas não espera são os outros motivos para atacar seu sistema. Por exemplo, o atacante não está interessado em qualquer informação do seu sistema. Ele não quer saber sua senha da conta do banco. Ele quer algo maior. Quer parar totalmente as transações da companhia de cartão de crédito XXXX através de um ataque DDoS (_**Distributed Denial of Service**_) e sua máquina será uma das mil máquinas que ele usará para este ataque. Estes alguns motivos para o atacante.

### Entendendo a base dos ataques.

Vamos à pergunta que interessa para este estudo: Por que os ataques são possíveis? Eles são possíveis devido aos protocolos somado à o que chamamos de brechas. Claro que este estudo é muito limitado. Vamos dar uma noção de segurança de redes (não abrangendo segurança da informação) para embasar o processo de proteção [1].

Os **protocolos** (no contexto da computação) são aquelas regras de funcionamento dos sistemas como um todo. A relação física/eletrônica do hardware, a ?conversa? entre o software básico, aquele que define o funcionamento do computador, e o hardware, as conversas entre computadores e as conversas entre elementos ativos das redes, de todas as naturezas.

Vamos dar um exemplo prático e muito simples. Se você mandar uma pergunta para uma outra máquina: ?Ei! Máquina xyz, você está aí? Pelo protocolo de redes, ela (a outra máquina) tem que responder para você: ?Sim, estou aqui?. Nesta ida e volta o ?atacante? só fez uma pergunta, mas recebeu de volta as seguintes informações: Que a máquina com este nome existe, qual o endereço de rede (**IP**) da outra máquina existe e está sendo usado e aquela máquina está online e, ainda, quanto tempo médio leva para você alcançá-la. Isto é bastante informação, você não acha? Com uma simples pergunta, a qual o **protocolo** exige que seja respondido, o atacante sai com várias informações. Isto parece meio bobo, mas não é. Os ataques começam com algo simples assim. Vamos ver este exemplo na prática, veja o print de tela abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830831/36791.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830831/36791.png)

Com um simples programa chamado “**PING**” descobri:

1. O site [**www.terra.com.br**](http://www.terra.com.br/) está hospedado em uma máquina com o nome **web-portal-cdn** sob o controle do domínio **terra.com.br**.
2. O endereço de rede ou IP é **200.192.193.12** (deve ser, mas se não for, pelo menos sei que alcanço aquela máquina através deste IP, pois pode haver **NAT (**_**Network Address Translation**_**)**.
3. Para um pacote de 64 bytes chegar na outra máquina somado ao tempo de resposta até minha máquina varia, mas na média leva 24 milissegundos.

Se eu fizer algo parecido, mas usar o programa “**MTR**” o que descubro?

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830832/36792.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830832/36792.png)

Acabo descobrindo por onde os pacotes passam para chegar na máquina desejada. Primeiro passou pelo meu roteador, depois passou pelos rotadores do meu provedor, a Embratel fez alguma parte do caminho e depois chegou num roteador do domínio terra.com.br.

Posso querer garantir um ataque mais rápido e, antes eu invado uma das máquinas que estão ligadas às redes que estão mais perto do meu destino, pois agora sei algumas.

Mas quem fez o trabalho para mim?

Os protocolos. Sim, o que acabo de fazer é mandar um pacote de rede formatado no protocolo **ICMP (**_**Internet Control Message Protocol**_**)** para a outra máquina. Esta outra máquina, quando recebe um protocolo ICMP, tem a **obrigação** de responder. Por que? Porque senão a rede não funciona. O ICMP precisa circular livremente pela rede porque ele dá informações importantes para que tudo funcione. Por exemplo. Uma das funções do ICMP seria:  O ICMP avisa para o emissor de um pacote que o destinatário perdeu o seu pacote e ele (o emissor) deve repetir o envio. Se isto não for obedecido, as mensagens ficam sem sentido. O ICMP me deu algumas respostas acima. Outro protocolo o **DNS (Domain Name System),** que também é um sistema responsável por transformar os nomes em endereços, me deu a informação do IP designado para a máquina que responde pelo site. O DNS é obrigado a fazer isto, senão a internet nem existiria da forma que existe.

Vamos ver um pequeno exemplo. Após as informações conseguidas acima e, através de outros protocolos, eu posso ver em que cidade fica este site. Eu posso angariar ou pedir emprestado (invadir, rsss) milhares de máquinas nesta cidade e enviar PINGs de 1500 bytes para o site, fazendo isto simultaneamente em todas as máquinas? já pensou que a resposta é obrigatória, a máquina atacada (ou o conjunto de máquinas atacadas) teriam que responder todas estas mensagens que foram abertas e montar respostas, etc. Ocorre que esta máquina não dá conta de tudo, então começa a preparar respostas de erro para avisar ao emissor que seu pacote não pode ser respondido e, porque leva tempo montando estas respostas, perde mais ICMPs que estão chegando , e precisa de mais respostas? assim por diante. O site não está mais respondendo solicitação de páginas WEB de seus clientes. Para os clientes, o site PAROU!!!! O sistema está colapsado!!

Você acaba de entender (grosseiramente é claro) como é um ataque **DDoS (Distributed Denial of Service)**.

Você viu? Os protocolos preparam o serviço para o atacante!!! E o resto? **O resto você faz**. O acesso remoto (por SSH) pelo usuário ?root? é desabilitado por default. Mas, num momento de angústia, na madrugada de domingo para segunda, você precisa ?porque precisa? habilitar o acesso. Ok. Só que na segunda, você esquece de voltar ao normal ou vem aquele ?grilo falante? (a consciência) avisando: Olha! Não esquece de desabilitar o acesso pelo ?root? do SSH!! E sua mente, de pronto responde: Sim, sim? amanhã arrumo um tempo pois agora estou fazendo o RRRGAANG (Relatório do Relatório do Relatório da Gerência de Assuntos Aleatórios Não Gerenciáveis) do ITIL. Resultado: Na hora do almoço, um cara esperto sentado à mesa ao lado da sua, no bar super badalado VSV (Vendo e Sendo Visto Ltda.) ouve a sua conversa com a garota que você quer impressionar, quando você diz:  Amanhã não poderei almoçar com você, pois preciso desabilitar o acesso root no SSH!! (A garota pensa: Quem é esta Rute?). O cara esperto ao lado olha para você e diz. Ei! Amigo, você não trabalha naquela empresa? como é o nome mesmo? Você, todo orgulhoso, fala eu trabalho na YXZ Corporation. O cara esperto termina conversa de qualquer jeito e, na madrugada entre hoje e amanhã, faz um ataque _**brute force**_ (tenta tudo que é tipo de senha, bilhões de vezes) pois já sabe o nome do usuário (root) e por respostas a protocolos também sabe qual máquina responde pelo domínio da XYZ Corporation. Você sofreu dois tipos de ataques aqui. Engenharia Social (falando o que não deve fora da empresa) e uma Invasão por _**Brute Force**_ (avisou que o root via SSH estava liberado e o nome do seu domínio). Eu falei....  Você faz o resto.

As coisas não são tão simples assim, mas, para exemplificar, o processo, a motivação e o fatos são mais ou menos estes.

Não vamos entrar em mais detalhes. O importante é você entender a base do porquê e por onde deve proteger seu sistema, ou sua rede, ou a rede dos outros.

### Protegendo o Sistema

Proteger seu servidor Linux é importante para proteger seus dados, propriedade intelectual e tempo, das mãos de atacantes. O administrador do sistema é responsável pela segurança do computador Linux. Vamos ver algumas opções práticas para o que é chamado de endurecimento/**hardening** de uma instalação padrão do sistema Linux [1].

**O que vamos ver aqui são boas práticas e elas estão presentes na maioria dos estudos e compêndios sobre servidores Linux.**

Vamos começar!

Todos os dados transmitidos através de uma rede estão abertos à monitorização. Criptografe dados transmitidos sempre que possível com senha ou usando chaves/certificados.

Abaixo, vamos ver algumas das opções que significam atitudes seguras ao fazer cópias, transferências, etc.

### Dados Encriptados

- **Scp, ssh, rsync ou sftp** para transferência de arquivos. Você também pode montar o sistema de servidor de arquivos remoto ou o seu próprio diretório pessoal usando ferramentas especiais de **sshfs**, por exemplo.
- **GnuPG** permite criptografar e assinar seus dados e comunicação, apresenta um sistema de gerenciamento de chave versátil, bem como módulos de acesso para todos os tipos de diretórios de chave pública.
- **Fugu** é um frontend gráfico para a linha de comando de transferência de arquivos seguros (SFTP). SFTP é semelhante ao FTP, mas ao contrário do FTP, toda a sessão é criptografada, o que significa que nenhuma senha é enviada em formato de texto não criptografado e, portanto, muito menos vulnerável à interceptação de terceiros.
- **FileZilla** um cliente multi-plataforma que suporta FTP, FTP sobre SSL/TLS (FTPS) e SSH _File Transfer Protocol_ (SFTP).
- **OpenVPN** é uma forma de você se conectar em outras máquinas de outras redes de forma a criar um túnel entre as duas máquinas e o transporte é criptografado.
- **Lighttpd SSL** (_Secure Server Layer_) Configuração e Instalação de **https**.
- **Apache SSL** (Camada de Servidor Seguro) Configuração e Instalação de Https (mod_ssl).

Estas são ferramentas do dia a dia. Se você fornecer segurança para uma empresa remotamente, pode oferecer um servidor de arquivos (como o Samba) onde os usuários só conseguem acessar, copiar e transferir, pelos métodos acima.

Por exemplo, você pode usar o FIleZilla (tela inicial abaixo):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830834/36794.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830834/36794.png)

**Pare com FTP, Telnet e serviços Rlogin/Rsh**

Na maioria das configurações de rede, nomes de usuário, senhas, comandos FTP/ telnet/rsh e arquivos transferidos podem ser capturados por qualquer pessoa na mesma rede usando um _**sniffer**_ de pacotes. A solução comum para este problema é usar **OpenSSH**, **SFTP** ou **FTPS** (FTP sobre SSL), que adiciona criptografia SSL ou **TLS** para FTP. Digite o seguinte comando para excluir estes serviços que são obsoletos para os tempos atuais [1].

**# apt-get remove  inetd xinetd ypserv tftp-server telnet-server rsh-servir**

**Reduzir o número de pacotes para diminuir vulnerabilidade**

Você realmente precisa de todo tipo de serviços web instalados? Evite instalar software desnecessário para evitar vulnerabilidades no sistema. Use o gerenciador de pacotes apt-get e / ou dpkg (no caso Debian, Ubuntu) para revisar todo o conjunto de pacotes instalados em um sistema. Exclua todos os pacotes indesejados.

**# dpkg --list**

**# dpkg --info packageName**

**# apt-get remove packageName**

Veja um list de pacotes abaixo. É uma infinidade de pacotes, porém muitos nem deviam estar instalados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830835/36795.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830835/36795.png)

**Uma rede para cada Serviço**

Executar serviços de rede diferentes em servidores separados ou instância VM (Virtuais). Isso limita o número de outros serviços que podem ser comprometidos. Por exemplo, se um invasor capaz de explorar com êxito um software como o tráfego do Apache, ele terá acesso a todo o servidor, incluindo outros serviços, como MySQL, o servidor de e-mail e assim por diante [1].

**Mantenha o kernel e o software do Linux atualizados**

A aplicação de patches de segurança é uma parte importante da manutenção do servidor Linux. O Linux fornece todas as ferramentas necessárias para manter seu sistema atualizado e também permite atualizações fáceis entre as versões. Todas as atualizações de segurança devem ser revistas e aplicadas o mais rapidamente possível. Novamente, use o gerenciador de pacotes como **apt-get** ou **dpkg** para aplicar todas as atualizações de segurança.

**\#apt-get update**

**\#apt-get upgrade**

**Use as extensões de segurança do Linux**

O Linux vem com vários patches de segurança que podem ser usados para proteger seu sistema contra programas mal configurados ou comprometidos. Se possível, use o **SELinux** e outras extensões de segurança do Linux para impor limitações na rede e em outros programas. Por exemplo, o SELinux fornece uma variedade de políticas de segurança para o kernel do Linux.

O **SELinux** é um conjunto de políticas/módulos de segurança que vão ser aplicados na máquina para melhorar a segurança geral da máquina. Estes, são os módulos de segurança Linux (LSM) que são carregados no kernel para melhorar a segurança no acesso a serviços/arquivos e que melhoram a segurança. O SELinux é a forma abreviada de **Security Enhanced Linux**. SElinux é um recurso de segurança que foi enviado com várias distribuições Linux, é muito mais seguro do que qualquer outro tipo ou método de segurança.  Abaixo está o modelo de segurança no Linux.

### Configuração do SELinux

SELinux é definido em três modos:

- **Enforcing** - A política de segurança do SELinux é aplicada. Se isso estiver definido, o SELinux estará habilitado e tentará aplicar as políticas SELinux estritamente, ou seja, a força.
- **Permissive** - SELinux grava avisos em vez de força e inibir. Esta configuração apenas dará aviso quando qualquer configuração de diretiva SELinux for violada, em log.
- **Disable** - Nenhuma política SELinux foi carregada. Isso desativará totalmente as diretivas SELinux.

E o SELinux é definido em dois níveis:

- **Targeted** - Os processos segmentados são protegidos,
- **Mls** - (Multi Level Security) Proteção Multi Nível de segurança.

### Obter estado do SELinux

O SELinux está ativado ou não na sua máquina? Use o comando abaixo para obter o status.

**\#getenforce**

A saída será "Ativado/Enable" ou "Desabilitado/Disable"

Veja o print abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830836/36796.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830836/36796.png)

Para ver o status do SELinux de forma simplificada você pode usar **sestatus**

**\#sestatus**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830837/36797.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830837/36797.png)

Você pode ver que o SELinux está executando com o comando:

**\#systemctl status selinux**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830838/36798.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830838/36798.png)

### Como desativar o SElinux

Podemos fazê-lo de duas maneiras

1) Modo permanente: edite **/etc/selinux/config**

Alterar o status do SELINUX de **enable** para **disable**

**SELINUX = enable**

Para

**SELINUX = disable**

Salve o arquivo e saia.

2) Modo temporário: Execute abaixo o comando (No terminal)

**\#echo 0 > /etc/selinux/enforce**

Ou

**setenforce 0**

### Ativando o SELinux

1) Modo permanente: edite **/etc/selinux/config**

Alterar o status do SELINUX de **disable** para **enable**

**SELINUX = disable**

Para

**SELINUX = enable**

Salve o arquivo e saia.

2) Modo temporário: Execute abaixo o comando (No terminal)

**\#echo 1 > /etc/selinux/enforce**

Ou

**setenforce 1**

Pronto, o servidor Linux já está mais seguro. Existem mais algumas tarefas para produzir mais segurança:

### Política de contas de usuário e senhas

Use os comandos **useradd/usermod** para criar e manter contas de usuário. Certifique-se de ter uma política de senha boa e forte. Por exemplo, uma boa senha inclui pelo menos 8 caracteres e uma mistura de alfabetos (letras gregas ajudam), número, caracteres especiais, etc. O mais importante é escolher uma senha que você possa lembrar. Use ferramentas como "**John the ripper**" para descobrir senhas de usuários fracos em seu servidor. Configure a **pam_cracklib.so** para aplicar a política de senhas. Isto significa: Seja o atacante e use pacotes de descoberta de senhas contra você mesmo. Não acredite que está tudo bem.

### Tempo de validade da senha.

O comando “**chage”** muda o número de dias entre as alterações de senha e a data da última alteração de senha. Esta informação é utilizada pelo sistema para determinar quando um usuário deve alterar sua senha. O arquivo **/etc/login.defs** define a configuração específica do site para a suíte de senhas sombra, incluindo a configuração da idade da senha. Para desativar o tempo de validade da senha, digite:

**\#chage -M 99999 Nome_do_Usuário**

Para obter informações sobre a expiração da senha, digite:

**\#chage -l Nome_do_Usuário**

Vamos testar isto. Veja o print abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830840/36799.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830840/36799.png)

Finalmente, você também pode editar o arquivo **/etc/shadow** nos seguintes campos:

**{Nome_do_Usuário}: {password}: {lastpasswdchanged}: {Minimum_days}: {Maximum_days}: {Warn}: {Inactive}: {Expire}:**

Onde,

**Minimum_days**: o número mínimo de dias necessários entre a mudança de senha, ou seja, o número de dias restantes para que o usuário tenha permissão para alterar sua senha.

**Maximum_days:** o número máximo de dias em que a senha é válida (após isto, o usuário é forçado a mudar sua senha).

**Warn:** O número de dias antes da que a senha expire, o usuário será avisado de que sua senha deve ser alterada.

**Expire**: Dias desde 1 de janeiro de 1970, que a conta está desativada, ou seja, uma data absoluta especificando quando o login pode não ser mais usado.

Eu recomendo o comando chage em vez de editar manualmente o **/etc/shadow**:

**# chage -M 60 -m 7 -W 7 Nome_do_Usuário**

### Restringindo o uso de senhas anteriores

Você pode impedir que todos os usuários usem ou reutilizem as mesmas senhas antigas no Linux. O parâmetro do módulo pam_unix “**remember”** pode ser usado para configurar o número de senhas anteriores que não podem ser reutilizadas.

### Bloqueando contas de usuário após falhas de login

Em Linux, você pode usar o comando **faillog** para exibir registros **faillog** ou para definir limites de falha de login. **Faillog** formata o conteúdo do registro de falhas do arquivo **/var/log/faillog**. Ele também pode ser usado para manter contadores e limites de falhas. Para ver tentativas de login com falha, digite:

**\#faillog -a**

- *** Aqui um ponto de referência importante para tentativas de ataques** _**force brute**_

Para desbloquear uma conta após falhas de login, execute:

**\#faillog -r -u Nome_do_Usuário**

Observe que você pode usar o comando passwd para bloquear e desbloquear contas:

Bloqueio de Conta

**\#passwd -l Nome_do_Usuário**

Desbloqueio de Conta

**\#passwd -u Nome_do_Usuário**

### Encontrando contas sem senha.

Digite o seguinte comando

**# awk -F: '($ 2 == "") {print}' /etc/shadow**

Bloqueie todas as contas de senha vazia encontradas na saída do comando acima:

**# passwd -l conta_do_usuário**

Certifique-se de que nenhuma conta não-root tenha UID definido como 0

Apenas a conta root tem UID 0 com permissões completas para acessar o sistema. Digite o seguinte comando para exibir todas as contas com o UID definido como 0:

**# awk -F: '($ 3 == "0") {print}' /etc/passwd**

Você só deve ver uma linha da seguinte maneira:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830841/36800.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830841/36800.png)

Se você vir outras linhas, exclua-as ou certifique-se de que outras contas estão autorizadas por você para usar o UID 0, por qualquer motivo.

### Desativar o Login do root

Nunca faça login como usuário root. Você deve usar **sudo** para executar comandos de nível de raiz, quando necessário. O sudo aumenta consideravelmente a segurança do sistema sem compartilhar senha de root com outros usuários e administradores. Sudo fornece recursos de auditoria e rastreamento simples também.

### Segurança física do Servidor

Você deve proteger o acesso ao console físico dos servidores Linux. Configure o BIOS e desative a inicialização a partir de dispositivos externos, como DVDs/CDs/USB. Defina a senha do BIOS e do gerenciador de inicialização **grub** para proteger essas configurações. Todos os computadores de produção devem ser bloqueados nos IDCs (Internet Data Center) e todas as pessoas devem passar algum tipo de verificação de segurança antes de acessar seu servidor.

O modo de single-user (usuário isolado da rede) é usado para recuperação do sistema. No entanto, por padrão, nenhuma autenticação é usada se o modo de usuário único for selecionado. Isso pode ser usado para ignorar a segurança no servidor e obter acesso à raiz. Para habilitar a autenticação para o modo de usuário único, abra o arquivo **/etc/inittab**,

**# vim /etc/inittab**

Adicione a seguinte linha ao arquivo:

**~~: S: wait: /sbin/sulogin**

### Desativar serviços indesejados

Desative todos os serviços e daemons desnecessários (serviços que são executados em segundo plano). Você precisa remover todos os serviços indesejados da inicialização do sistema. Digite o seguinte comando para listar todos os serviços que são iniciados no momento da inicialização no nível de execução # 3:

**# apt-get install sysv-rc-conf**

**\#sysv-rc-conf**

Você verá o print a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830844/36801.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830844/36801.png)

Para desativar o serviço, digite:

**# service Nome_do_serviço stop**

**Desmarcá-lo no sysv-rc-conf**

### Encontre as portas abertas de rede

Use o seguinte comando para listar todas as portas abertas e programas associados:

**\#netstat -tulpn**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840887/36803.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840887/36803.png)

OU

**\#nmap -sT -O localhost** (se precisar instale: \#apt-get install nmap)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840889/36804.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840889/36804.png)

**\#nmap -sT -O servidor.dominio.com** (ex. samba@luckygav.net)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840890/36805.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840890/36805.png)

Acabamos de checar o site [**www.terra.com.br**](http://www.terra.com.br/) , observe como ele está **coerente**. A máquina que hospeda o site tem apenas as portas 80 e 443 abertas. Ambas necessárias para páginas WEB.

**Também saiba: Ao fazer isto com nmap, já causei um alerta na área de segurança do site, pois uma checagem de portas abertas precede um possível ataque.**

Use **iptables ou o ufw** para fechar portas abertas ou parar todos os serviços de rede indesejados usando o serviço acima e comandos **sysv-rc-conf**.

### X Windows

O que chamamos **XWindows**, nada mais é do que a capacidade de trabalhar na forma gráfica. X Windows no servidor não é necessário. Mesmo que você sinta uma vontade louca de trabalhar neste ambiente, se você é um administrador de redes responsável e sério, não ceda à tentação. Não há motivos para executar o X Windows em seu correio eletrônico e servidor web Apache, eles operam no ambiente de linha de comando. Você pode desativar e remover o X Windows para melhorar a segurança e o desempenho do servidor. **A quantidade de possibilidades em termos de malware’s e invasões é gigantesca no ambiente gráfico. Você pressiona botões e, na verdade, não sabe o que está sendo executado quando os pressiona.**

Edite **/etc/inittab** e defina o nível de execução para **3**. Finalmente, remova o sistema X Windows, digite:

**# vim /etc/init/gdm.conf**

Comente todas as linhas abaixo.

**\#start on (filesystem**

**# and started dbus**

**# and (drm-device-added card0 PRIMARY_DEVICE_FOR_DISPLAY=1**

**# or stopped udevtrigger))**

**\#stop on runlevel [016]**

Depois, avisa o **grub**:

**# update-grub**

### Iptables e TCPWrappers

Iptables (já falamos nele) é um programa de aplicativo de interface com o usuário que permite que você configure o firewall (**Netfilter** fizemos um estudo sobre este assunto). Fornecido pelo kernel do Linux. Use o firewall para filtrar o tráfego e permitir apenas o tráfego necessário. Também use o **TCPWrappers** um sistema ACL (Access Control List) de rede baseado em host para filtrar o acesso à rede para a Internet. Você pode evitar muitos **DoS** e **DDoS** se aprender a usar bem o **Iptables**.

### Reforçando o SYSCTL

Sysctl é uma função derivada dos sistemas Unix que visa criar limites e controles no Kernel em tempo de execução. O arquivo **/etc/sysctl.conf** é usado para configurar os parâmetros do kernel. O Linux lê e aplica configurações de **/etc/sysctl.conf** no momento da inicialização.

O kernel do Linux (ou patch to kernel) fornece o recurso ExecShield para proteger contra sobrecarga ou transbordo de buffer, como:

- Colocação aleatória da pilha
- Colocação aleatória de regiões de memória
- Prevenção de execução em memória que só deve armazenar dados
- Manipulação de buffers de texto com cuidado e mais.

Veja como atualizar no **sysctl.conf**:

Acrescente as linhas:

**kernel.exec-shield = 1**

O randomize_va_space ajuda a evitar o “buffer overflow” e pode ter qualquer um dos seguintes valores:

0 - Não randomize stack e vdso page.

1 - Ativar proteção e aleatorizar pilha, página vdso e mmap.

2 - Ligue a proteção e aleatorizar pilha, vdso page e mmap + aleatorizar o endereço base brk.

Acrescente:

**kernel.randomize_va_space = 1**

Para evitar spoofing:

**net.ipv4.conf.all.rp_filter = 1**

Desativar o roteamento da IP fonte. Sem isto, pode-se criar uma maneira de encaminhar um pacote através de um firewall para um IP inacessível, especificando esse IP na rota.

**net.ipv4.conf.all.accept_source_route = 0**

Ignorar solicitação de transmissão. Ignora pings de transmissão, reduzindo o dano dos ataques SMURF.

**net.ipv4.icmp_echo_ignore_broadcasts = 1**

Alguns roteadores ignoram o RFC 1122 e enviam respostas de erro descartadas que foram registradas. Pode ser possível desencadear esse log por falsificação; isso levaria a preencher o disco rígido com logs de rejeitos, causando uma negação de serviço (**DoS**). Então assinale:

**net.ipv4.icmp_ignore_bogus_error_messages = 1**

Certifique-se de que os pacotes falsificados sejam registrados

**net.ipv4.conf.all.log_martians = 1**

### Separando as partições de disco

A separação dos arquivos do sistema operacional dos arquivos do usuário pode resultar em um sistema melhor e seguro. Verifique se os seguintes sistemas de arquivos estão montados em partições separadas:

 **/usr**

**/home**

**/var e /var/tmp**

**/tmp**

Crie partições separadas para raízes do servidor **Apache** e **FTP**. Edite o arquivo **/etc/fstab** e verifique se você adicionou as seguintes opções de configuração:

1. **Noexec** - Não configure a execução de nenhum binário nesta partição (impede a execução de binários, mas permite scripts).
2. **Nodev** - Não permita caracteres ou dispositivos especiais nesta partição (evita o uso de arquivos de dispositivos como zero, sda, etc.).
3. **Nosuid** - Não configure o acesso SUID/SGID nesta partição (evite o **setuid bit**).

O **setuid** (set user id) é um bit de permissão, que permite aos usuários executar um programa com as permissões de seu proprietário.

Exemplo **/etc/fstab**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840891/36806.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840891/36806.png)

**IPv6 desative, por enquanto.**

O Protocolo de Internet versão 6 (IPv6) fornece uma nova camada de Internet do conjunto de protocolos TCP / IP que substitui o protocolo de Internet versão 4 (IPv4) e oferece muitos benefícios. Atualmente, não há ferramentas boas que possam verificar problemas de segurança num sistema de rede IPv6. A maioria das distribuições do Linux começou a ativar o protocolo IPv6 por padrão. Atacantes podem enviar tráfego mal-intencionado via IPv6, já que a maioria dos administradores não está monitorando. A menos que a configuração da rede o exija, desative o IPv6 ou configure o firewall do Linux IPv6:

Se você está usando Ubuntu, abra o arquivo **/etc/modprobe.d/aliases**

**# vim /etc/modprobe.d/aliases**

Encontre a linha:

**alias net-pf-10 ipv6**

Substituir por:

**alias net-pf-10 off**

**alias ipv6 off**

Salve e feche o arquivo. Finalmente, reinicie o sistema. O suporte a IPv6 agora deve estar desabilitado e ainda melhorou o desempenho de DNS.

### Arquivos globalmente liberados para escrita.

Para o funcionamento normal do Linux, alguns arquivos são World-writable?s. Qualquer pessoa pode modificar o arquivo world-writable, resultando em um problema de segurança. Use o seguinte comando para encontrar todos os arquivos com esta liberação:

**find /dir -xdev -type d**  **-print**

Você precisa investigar cada arquivo relatado e definir o usuário correto e permissão de grupo ou excluí-lo.

### Arquivos tipo sem proprietário (Noowner)

Arquivos sem serem propriedade de qualquer usuário ou grupo podem representar um grande problema de segurança. Podemos procurá-los com o seguinte comando:

**find /dir -xdev**  **-print**

Você precisa investigar cada arquivo relatado e atribuí-lo a um usuário e grupo apropriados ou excluí-lo.

### Sistema centralizado de autenticação

Sem um sistema de autenticação centralizado, os dados de autenticação de usuário tornam-se inconsistentes, o que pode levar a credenciais desatualizadas e contas esquecidas que deveriam ter sido excluídas logo após o desuso. São famosos os casos de funcionários que já saíram de empresas, mas ainda detinham o acesso e fizeram grandes estragos recentemente. Um serviço de autenticação centralizado permite que você mantenha o controle central sobre a conta do Linux/UNIX e os dados de autenticação. Você pode manter os dados de autenticação sincronizados entre os servidores. Não use o serviço **NIS** para autenticação centralizada. Use o **OpenLDAP** para clientes e servidores. **OpenLdap** é um controlador de acesso a diretórios [1].

### Controle de contas com auditoria

Um pacote importante é o **auditd** é fornecido para a auditoria do sistema. Ele é responsável por produzir registros de auditoria em disco. Durante o boot, as regras em /etc/audit.rules são lidas por este **daemon**. Você pode abrir o arquivo **/etc/audit.rules** e fazer alterações como, por exemplo, a localização do log de arquivos de auditoria. Com o **auditd** você pode responder às seguintes perguntas:

1. Quais os eventos de inicialização e desligamento do sistema (reiniciar / interromper), assim como data e hora do evento?
2. Qual o usuário responsável pelo evento?
3. Qual o tipo de evento (editar, acessar, excluir, escrever, atualizar arquivos e comandos ocorreram?
4. O evento teve sucesso ou falha?
5. Registrou eventos que modificam a data e a hora?
6. Quem fez alterações para modificar as configurações de rede do sistema?
7. Quais eventos que modificaram as informações de usuário/grupo.
8. Quem fez alterações em um arquivo xyx?

### Detecção de intrusão

Um sistema de detecção de intrusão de rede (**NIDS**) é um sistema de detecção de intrusão que tenta detectar atividades mal-intencionadas, como, ataques de negação de serviço, varredura de portas ou mesmo tentativas de invadir computadores monitorando o tráfego de rede. Como falei acima, apenas de eu ter mostrado como ver as portas abertas do site terra.com.br, certamente o **NIDS** de lá me colocou em suspeita.

É uma boa prática implantar qualquer software de verificação de integridade antes que o sistema fique online em um ambiente de produção. Se possível, instale o software **AIDE** antes que o sistema esteja conectado a qualquer rede. AIDE é um sistema de detecção de intrusão baseado em host (**HIDS**) que pode monitorar e analisar os o funcionamento interno de um sistema computacional.

O **Snort** é um software para detecção de intrusão que é capaz de realizar log de pacotes e análise de tráfego em tempo real em redes IP.

### Protegendo arquivos e diretórios

O Linux oferece excelentes proteções contra o acesso não autorizado a dados. As permissões de arquivo e MAC impedem o acesso não autorizado de acessar dados. No entanto, as permissões definidas pelo Linux são irrelevantes se um invasor tiver acesso físico a um computador e simplesmente pode mover o disco rígido do computador para outro sistema para copiar e analisar os dados sensíveis. Você pode facilmente proteger arquivos e partições no Linux usando as seguintes ferramentas:

Para criptografar e descriptografar arquivos com uma senha, use o comando **gpg**.

A senha de Linux ou UNIX protege arquivos com **openssl** e outras ferramentas.

Veja como criptografar diretórios com o **ecryptfs**.

**TrueCrypt** é um software gratuito de criptografia de disco de código aberto para Linux.

Howto: criptografia de disco e partição no Linux para dispositivos móveis.

Como configurar o Swap criptografado no Linux.

# 20.1: Protegendo Servidores de E-mail

### Oferecendo Serviços de Segurança de Rede com o Linux.

Agora que você sabe onde e como proteger um servidor Linux, você já tem uma máquina segura para atender a clientes remotos.

A primeira ação para proteger redes de clientes remotos seria desviar o fluxo de acesso com proxy. Você pode configurar o cliente para apontar para seu servidor. Lembrando que você precisa estar apontado pelo DNS como um IP público.

Ao mesmo tempo pode-se colocar uma pequena máquina como agente físico no cliente com objetivo de ser o **GATEWAY** daquele cliente. Desta forma você terá acesso criptografado e poderá monitorar individualmente aquele cliente, inclusive recebendo alertas.

Você sempre pode envolver uma razoável e confortável camada de criptografia ao longo do tráfego de Internet de seu cliente para fazer trabalhos de todos os tipos, e com o alto volume de troca de dados, é mais crucial do que nunca nos negócios hoje.

Atualmente **OpenVPN** é a melhor escolha para proteger a rede em um ambiente de redes não confiáveis (quase todas).

Uma nota rápida sobre VPNs: existem muitas VPNs comerciais que não valem nada em termos de operacionalidade. São pouco melhores do que sites protegidos por SSL, porque confiam em todos os clientes. Uma VPN verdadeira (**rede privada virtual**) conecta dois pontos finais confiáveis em um ambiente de redes não confiáveis.

Você precisa de uma VPN que não permita fazer login de qualquer computador aleatório que o cliente encontrar, e isso é bom porque, presumivelmente, você entende que fazer login na sua rede privada de um host infectado é uma coisa ruim e desastrosa, independentemente da segurança da conexão. Então, você precisa ter a opção de configurar o servidor e o cliente [1].

### Investigação de ocorrências de segurança

Não é precisa procurar em computadores especiais ou ir atrás de acontecimentos em outros lugares. Seu servidor é sempre um palco de tentativas de ataque. Os atacantes estão constantemente tentando diferentes mecanismos para atacar seu sistema. Você deve ser capaz de detectar essas diferentes tentativas e saber o que fazer quando acontecer. Você também pode distinguir as condições normais de operação de um ataque real. É preciso determinar se houve ou não uma intrusão e/ou até que ponto o ataque ocorreu [2].

Detecção de intrusão é o método no qual um administrador de segurança usa para detectar a presença de um intruso não autorizado. Um Sistema de Detecção de Intrusão (IDS) como já falado acima, é a combinação de ferramentas que um administrador de segurança usa para detectar a intrusão. Resumidamente, os tipos disponíveis de detecção de intrusão incluem:

- **Detecção de Intrusão Baseada em Rede** - Esses mecanismos geralmente consistem em uma caixa preta que se coloca na rede em modo sem proteção, ouvindo os padrões indicadores de uma intrusão ou entendendo estilos de ataque com comentamos no início deste estudo.
- **Detecção de Intrusão Baseada em Host** Esses mecanismos tipicamente incluem auditoria para eventos específicos que ocorrem em um host específico. Estes não são tão comuns, devido à sobrecarga que incorrem ao monitorar cada evento do sistema.
- **Monitoramento de arquivos de log** - Esses mecanismos geralmente são programas que analisam arquivos de log depois que um evento já ocorreu, como tentativas de login com falha, etc. Certamente são muito eficazes, comportando boa parte dos mecanismos forenses.
- **Verificação de Integridade de Arquivos -** Esses mecanismos geralmente controlam cavalos de tróia, ou arquivos que de outra forma foram modificados, indicando que um intruso já esteve lá. O Tripwire é um dos pacotes mais eficientes neste campo.

Ser capaz de detectar uma intrusão é tão importante como poder parar isso uma vez que acontece. É importante que você seja capaz de detectar os sinais sutis deixados por um intruso durante o ataque do seu sistema [2].

Os sinais suspeitos de intrusão incluem pelo menos o seguinte:

**Indicações do usuário**

- Falha nas tentativas de logon
- Log-ins para contas que não foram usadas por um longo período de tempo
- Log-ins durante horas que não é o horário de trabalho
- A presença de novas contas de usuário que não foram criadas pelo administrador do sistema
- Entradas ou logins de lugares estranhos, bem como repetidas tentativas falhadas

**Indicações do sistema**

- Modificações em software de sistema e arquivos de configuração
- Lacunas na contabilidade do sistema que indicam que nenhuma atividade ocorreu durante um longo período de tempo
- Desempenho do sistema excepcionalmente lento
- O sistema trava ou reinicia
- Registros curtos ou incompletos
- Registros contendo **timestamps** estranhos
- Registros com permissões ou propriedade/owner incorretas
- Registros ausentes
- Desempenho anormal do sistema
- Processos desconhecidos
- Exibições gráficas incomuns ou mensagens de texto.

**Indicações do sistema de arquivos**

- A presença de arquivos ou programas novos e desconhecidos
- Alterações nas permissões de arquivos
- Alterações inexplicadas no tamanho do arquivo. Certifique-se de analisar todos os seus arquivos do sistema, incluindo aqueles em seu diretório $ HOME /, como $ HOME / .bashrc para entradas $ PATH modificadas, bem como alterações nos arquivos de configuração do sistema em / etc
- Arquivos **suid** e **sgid** no sistema que não correspondem à sua lista principal de arquivos suid e sgid
- Nomes de arquivos desconhecidos em diretórios
- Arquivos perdidos

**Indicações de rede**

- Sondagens repetitivas dos serviços disponíveis em suas máquinas
- Conexões de locais incomuns
- Tentativas repetidas de login de hosts remotos
- Dados de log arbitrários em arquivos de log, indicando tentativa de criar negação de serviço ou serviço de falha
- Sondagens repetitivas de portas abertas

Com o objetivo de descobrir se um intruso violou seu sistema, você deve estar familiarizado com as ferramentas normais de administração do sistema e poder usá-los para encontrar os **rastros** podem ter sido deixados para trás. Este procedimento pode ser relativamente fácil ou praticamente impossível, dependendo da quantidade de preparação que você teve, bem como do ambiente em que você detectou o intruso e, principalmente, da habilidade do intruso [2].

Neste estudo existem indicações que listam as várias ferramentas disponíveis. Algumas das ferramentas e métodos que você deve estar treinado incluem:

- Análise do arquivo de logs. Certifique-se de ver informações na **syslog**, responsável pelo registro de muitos eventos do sistema que são úteis no rastreamento de conexões ao seu sistema, bem como eventos do sistema local.
- Familiarize-se com os últimos comandos, **lastcomm** e netstat. Eles são razoáveis para mostrar informações valiosas sobre os usuários, comandos e conexões em seu sistema.
- Procure sinais de intrusão física. A primeira coisa a observar sempre é quando sua máquina foi reiniciada. Uma vez que o Linux é um sistema operacional robusto e estável, as únicas vezes que sua máquina deve reiniciar é quando **você** reinicializá-la para promover atualizações do sistema operacional, trocas de hardware ou similares. Você sempre deve investigar as reinicializações da máquina. Verifique se há sinais de adulteração no caso e na área do computador. Embora muitos intrusos limpem os rastros de sua presença nos registros/logs, é uma boa ideia verificar todas elas e anotar qualquer discrepância.
- Certifique-se de que o software que você está usando para procurar o intruso não foi comprometido. Não confie nas ferramentas que você está usando e no resultado que elas produzem. Considere colocar um conjunto de arquivos executáveis binários seguros em mídias externas que podem ser usadas mais tarde, com confiança. Veja o sistema **trinux**. Trata-se de um Linux preparado para rodar em pendrives, CD?s,etc. E faz varredura completa da segurança de um sistema.
- Siga as diretrizes fornecidas pelo CERT neste documento **ftp://info.cert.org/pub/tech_tips/UNIX_configuration_guidelines***
- Verifique outros sistemas locais que podem ter sido usados para atacar o seu sistema
- Verifique se há sistemas em sites remotos que possam estar envolvidos ou afetados
- Investigue hardware não autorizado ligado à rede
- Observe seus sistemas se há qualquer coisa incomum, e investigue qualquer coisa que você encontrar
- Notificar sua equipe de resposta a incidentes se você encontrar algo que poderia ter sido realizado por um usuário não autorizado
- Use as ferramentas de monitoramento de rede. Existem também várias ferramentas de monitoramento de rede habilidosas que também são úteis. É importante manter-se ciente do estado da sua rede, para que você saiba quando for alertado sobre um evento específico.
- **CERT** ("_**Computer Emergency Readiness Team**_") foi formado pela Agência de Projetos Avançados de Pesquisa de Defesa (**DARPA -** _**Defense Advanced Research Projects Agency**_) depois de um desastre na internet através de um ataque de **worms**.

### Arquivos Deletados e Investigação

Estudos provam as informações de arquivos excluídos podem sobreviver intactas por meses ou mesmo anos, e essa informação de atributo do arquivo excluído pode fornecer informações sobre atividades ocorridas no sistema que você não pode obter a partir de informações comuns de atributos dos arquivos.

Os padrões de tempo de acesso ao arquivo **MACtime,** dos arquivos existentes podem fornecer uma ótima visão do comportamento passado do sistema. Mas, eles sofrem de uma grande desvantagem: as informações **MACtime** são destruídas sempre que um arquivo é acessado de uma forma ou de outra. As informações de MACtime dos arquivos existentes são voláteis, sem deixar rastros. A próxima vez que você olhar, mudou [2].

No arquivo excluído as informações **MACtime** são diferentes. Quando um arquivo é excluído, suas informações **MACtime** não mudam até que ele seja substituído. Em outras palavras, as informações de **MACtime** do arquivo excluído ficam congeladas no tempo.

O mesmo é verdadeiro para o conteúdo do arquivo excluído. Uma vez excluído, o conteúdo do arquivo não muda até que ele seja substituído. Nos sistemas de arquivos com boas propriedades de controle e aproveitamento de espaço, os arquivos excluídos podem permanecer intactos por anos. A informação de arquivo excluída é como uma marca d'água [2].

Esta característica de exclusão e persistência pode acontecer em qualquer nível de abstração. No nível de abstração dos sistemas de arquivos, as informações excluídas persistem como blocos de disco não alocados até que sejam substituídos. **No nível de abstração das cabeças de leitura do disco magnético, as informações sobrepostas persistem como modulações analógicas nas informações mais recentes**. E no nível de abstração dos domínios magnéticos, as informações sobrescritas persistem como padrões magnéticos das faixas magnéticas.

Em cada camada na hierarquia de abstrações que compõem sistemas de computador, as informações ficam congeladas quando são excluídas. Embora as informações apagadas se tornem cada vez mais ambíguas à medida que descemos para níveis mais baixos e inferiores de abstração, também achamos que as informações excluídas se tornam cada vez mais persistentes. A volatilidade é uma característica das abstrações que tornam úteis os sistemas informáticos.

Tudo isso tem grandes consequências, não só para os atacantes cuja atividade é reconstruída com análise de intrusão pós-ataque, mas também para a privacidade de usuários legítimos de sistemas informáticos.

### Conclusão

Produzir um serviço de segurança, passa, inevitavelmente, pela preparação do próprio servidor. Após ter um ambiente segura através de uma série de configurações e, principalmente, através de atitudes diárias de manutenção e observação, podemos oferecer segurança para ambientes remotos. Por sua vez, os ambientes remotos precisam estar ligados nesta segurança preparada antecipadamente através de desvios de tráfego e aplicação de agentes remotos. Existem padrões a serem rigorosamente cumpridos através de informações fornecidas por instituições como a CERT, mas também sabemos que a invasão é virtualmente inevitável. O que podemos fazer é produzir uma barreira muito forte para evitar a invasão, outras barreiras para minimizar os estragos provocados pela invasão como, por exemplo quando usamos equipamentos colocados para serem propositadamente atacados, chamados Honeypot, que aqui no Brasil chamamos de ?boi-de-piranha?, ou como quando criamos estruturas, partições, permissões de acesso cuidadosamente pensadas, proibimos login com root, bloqueamos as portas de acesso, etc. e, por último, nos esmeramos na conduta de investigação das ocorrências.