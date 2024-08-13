### Conceitos

DNS (Domain Name System), é o serviço que promove a tradução entre nomes Internet e endereços da Internet. Você já sabe isto, mas é importante olharmos o assunto do começo.

Nomes de Internet são os nomes que usamos para se referir a hosts na Internet, como [**www.uninove.br**](http://www.uninove.br/) ou máquina1.minhaempresa.com.br, por exemplo.

Os endereços da Internet (IP?s) são os números que os roteadores usam para mover o tráfego pela Internet em direção a um host/máquina específica, tal como 211.2.26.121.

**Vamos fazer uma implantação de um servidor de DNS, através de um pacote chamado BIND, mas antes, vamos começar a compreender os elementos principais do DNS. Trataremos de dois principais elementos que serão explicados em detalhes. Os Registros DNS (DNS Records) e a Zona DNS (DNS Zone).**

O que são registros DNS?

Os registros DNS ou os arquivos de zona são usados para mapear URIs para os respectivos IPs. Localizados em servidores chamados servidores DNS, esses registros são normalmente a conexão de seu site com o mundo exterior. Solicitações de seu site são encaminhadas para seus servidores DNS e, em seguida, obtém-se um apontamento para o endereço dos WebServers que servem o site ou para os servidores de e-mail, por exemplo, para receber o que há em sua inbox [1].

### Tipos de registros DNS.

**A primeira parte da implantação de um servidor DNS é a elaboração dos registros.**

Os principais tipos de registros do DNS são:

- **A**
- **AAAA**
- **CNAME**
- **MX**
- **PTR**
- **NS**
- **SOA**
- **SRV**
- **TXT**
- **NAPTR**

Os registros DNS acima são utilizados principalmente em todas as configurações de DNS.

Para cada um destes registro, vamos ver exemplos.

### Registro A

Registro A ou Registro de Endereço.

Registro de Endereço, atribui um endereço IP a um nome de domínio ou subdomínio. Quando o sistema de nome de domínio foi projetado, foi recomendado que nenhum dois registros A se referem ao mesmo endereço IP. Quer dizer que cada IP aponta para um único domínio. Atenção, nem todos os IPs apontam para um domínio, mas os IP?s que apontam para um domínio, apontam apenas para este domínio.

Suponha que você tenha o domínio luckygav.net e queira atribuir endereço IP 10.10.0.1 ao seu servidor web, então você deve criar um registro A com "www.luckygav.net" como o **FQDN** - **Fully Qualified Domain Name*** e "10.10.0.1" no valor.

- **-**Você vai entender melhor com os exemplos

A partir de agora, todos os pedidos de acesso ao www.luckygav.net serão enviados para um servidor com esse IP.

Basicamente é útil usar um registro A quando você tem subdomínios residindo em vários sistemas.

Você pode usar um registro A com "*** .luckygav.net** " para permitir qualquer serviço (ftp, smtp, pop,etc.) ou componente do domínio **luckygav.net** ser resolvido para o seu IP, embora um registro curinga **(*)** CNAME é muitas vezes melhor do que um registro curinga A.

**Exemplo de um registro A**

**luckygav.net. IN A 10.10.0.1**

Onde

**IN** indica Internet

**A** indica o registro de endereço.

O exemplo acima indica que o endereço IP para o domínio **luckygav.net** é **10.10.0.1**

### Registro AAAA

Um registro AAAA ou registro de endereço IPv6 mapeia um nome de host para um endereço IPv6 de 128 bits.

O registro de recurso de endereço DNS normal é definido para um endereço IPv4 de 32 bits, portanto, um novo foi criado para permitir que um nome de domínio seja associado a um endereço IPv6 de 128 bits. Os quatro "A" s ("AAAA") são um mnemônico para indicar que o endereço IPv6 é quatro vezes o tamanho do endereço IPv4. O registro AAAA é estruturado de forma muito semelhante ao registro A nos formatos de arquivo binário e mestre; É apenas muito maior.

**Exemplo de registro AAAA**

O registro AAAA foi criado para ajudar na transição e coexistência entre as redes IPv4 e IPv6. Um servidor de nomes IPv4 pode fornecer endereços IPv6:

**Linux AAA 3ffe: 1900: 4545: 2: 02d0: 09ff: fef7: 6d2c**

### Registro CNAME

Um registro CNAME ou **registro de nome canônico**, cria um alias (apelido) para o domínio e aponta todos os subdomínios para os registros do DNS original .

Você deve usar um registro CNAME sempre que desejar associar um novo subdomínio a um registro A já existente; Ou seja, você pode fazer "www.luckygav.net" para "luckygav.net", que já deve ter tido um IP atribuído no registro A. Isso permite que você tenha quantos subdomínios desejar sem precisar especificar o IP para cada registro. Use um CNAME se você tiver mais serviços apontando para o mesmo IP. Desta forma, você terá que atualizar apenas um registro no evento de uma mudança de endereço IP.

**Não use nomes de host definidos pelo CNAME em registros MX.**

**Exemplo de CNAME.**

**mail.luckygav.com IN CNAME mail.luckygav.net**

Onde

IN indica Internet

CNAME indica registro CNAME.

### Registro MX

Um registo MX ou um **registro de servidor de transporte de correio,** mapeia um nome de domínio para uma lista de servidores de transporte de correio para esse domínio.

**Exemplo de registro MX - servidores de correio simples**

**luckygav.net. 14400 IN MX 0 luckygav.net.**

O registro MX mostra que todos os e-mails @ luckygav.net devem ser encaminhados para o servidor de correio em **luckygav.net**. O registro DNS mostra que **luckygav.net** está localizado em **10.10.0.1**. Isso significa que o e-mail para **pedro@luckygav.net** será encaminhado para o servidor de e-mail em **10.10.0.1**. Isso termina a tarefa do registro MX. O servidor de e-mail nesse servidor, em seguida, assume, coleta o e-mail e, em seguida, procede a distribuí-lo para o usuário ?**pedro**?.

É importante que haja um ponto **(?.?)** após o nome de domínio no registro MX. Se o ponto estiver ausente, ele roteia para ?**luckygav.net.luckygav.net? (o que, obviamente você não quer)**. O número 0 indica Número de Preferência. O correio é sempre encaminhado para o servidor que tem o número de preferência mais baixo. Se houver apenas um servidor de email, é seguro marcá-lo 0.

**Mais de um Servidor de Correio**

Se você quiser usar vários servidores de e-mail, é necessário usar os número de preferência do registro MX. Os valores de preferência de registro MX indicam qual servidor de correio usar e em que ordem tentar quando algum falhar ou não responder. Um número de preferência maior é menos preferido (nível de prioridade). Assim, um servidor de correio com uma preferência zero (0) é sempre preferido sobre todos os outros servidores de trânsito de correio. A definição de valores de preferência para números iguais torna os servidores de correio igualmente preferidos.

**Exemplo com sintaxe de registro MX - Vários servidores transporte de email**

**luckygav.net. 14400 IN MX 0 luckygav.net.**

**luckygav.net. 14400 IN MX 30 server2.luckygav.net**

Você pode ter entradas MX ilimitadas para contingência ou propósito de backup. Se todos os registros MX têm números de preferência iguais, o cliente simplesmente tenta todos os servidores de preferência iguais em ordem aleatória e, em seguida, passa para o registro MX com o próximo número de preferência mais alto.

### Registro PTR

Um registro PTR ou um **registro de ponteiro** mapeia um endereço IPv4 para o nome canônico desse host.

Configurar um registro PTR para um nome de host no domínio **in-addr.arpa** que corresponde a um endereço IP, implementa a procura de DNS **inversa** para esse endereço. Por exemplo [**www.dominio.com**](http://www.dominio.com/) tem o endereço IP 206.0.10.7, mas um registro PTR mapeia 7.10.0.206.in-addr.arpa.

**Exemplo de registro PTR**

**7.10.0.206.in-addr.arpa. IN PTR dominio.com**

Aqui como você vê que o endereço IP é invertido e adicionado com in-addr.arpa e isso aparece no lado esquerdo, enquanto o nome do domínio real está no lado direito de **IN PTR**.

Isso é usado principalmente como uma medida de segurança e anti-spam em que a maioria dos servidores de e-mail ou servidores de e-mail fazem **reverse lookup DNS** para verificar se o host está realmente vindo de onde ele alega vir. É sempre aconselhável ter um registro DNS reverso apropriado (PTR) configurado para seus servidores, especialmente quando você está executando um servidor de email / smtp.

### Registro NS

Um registro NS (name server) ou **registro de servidor de nomes** mapeia um nome de domínio para uma lista de servidores DNS com autoridade para esse domínio. As delegações dependem dos registros NS.

O registro NS indica os servidores de nomes que têm autoridade para um determinado domínio. Os registros NS de cada autoridade para qualquer domínio serão listados no servidor pai. Estes são chamados **?registros de delegação?** e ,como estes registros estão no servidor principal, eles indicam a delegação do domínio para os servidores que são autoridade sobre ele (o domínio).

O registro NS também será listado nos registros de Zona do Servidor de Nomes que é autoridade sobre o Domínio em si. Esses registros são chamados como **registros de autoridade**.

Os registros NS encontrados no servidor pai devem coincidir com os registros NS no servidor autoridade também. No entanto, você pode ter registros NS listados no servidor autoridade que não está listado no servidor pai. Essa configuração é normalmente usada para configurar Servidores de Nomes Stealth (**Stealth Name Servers**), que são servidores de nomes ocultos. O benefício de ter um servidor de nomes stealth é que a internet, em geral, não sabe o endereço dele, e não pode facilmente atacá-lo.

**Exemplo de registro NS**

**luckygav.net. IN NS zeus.luckygav.net.**

Onde:

IN indica a Internet

NS indica o tipo de registro que o registro do servidor de nomes

O exemplo acima indica que o **zeus.luckygav.net** é o servidor autoridade para o domínio **luckygav.net.**

### Registro SOA

Um registro SOA (**Start of Authority**) ou **registro de início de autoridade** especifica o servidor DNS que fornece informações autoritativas sobre um domínio da Internet, o email do administrador do domínio, o número de série do domínio e vários temporizadores relacionados à atualização da zona.

Um Registro SOA **é a parte mais essencial de um arquivo de Zona**. O registro SOA é uma maneira para o administrador do domínio dar informações simples sobre o domínio como:

- **quantas vezes ele foi atualizado**
- **quando foi atualizado pela última vez**
- **quando verificar recursivamente para obter mais informações**
- **quais são os endereços de e-mail dos administradores.**

Um arquivo de ZONA (ZONE) pode conter apenas um registro SOA.

Um registro SOA devidamente otimizado e atualizado pode reduzir a largura de banda entre os servidores de nomes, aumentar a velocidade de acesso ao site e garantir que o site esteja vivo mesmo quando o servidor DNS primário estiver inativo.

**Exemplo de Registro SOA**

Aqui está o registro SOA. Observe o delimitador inicial **?(?** .Ele deve estar na mesma linha, caso contrário, o registro fica quebrado. Cuidado com o **?;?** também não pode faltar.

**luckygav.net 14400 IN SOA zeus.luckygav.net. pedro.luckygav.net (**

**2016123001; Número de série**

**55080; Taxa de atualização em segundos**

**7200; Atualizar repetir em segundos**

**3600000; Expiração em segundos**

**600; Mínimo em segundos)**

Nome - **luckygav.net** é o nome principal nesta zona.

TTL - 14400 - TTL define a duração em segundos que o registro pode ser armazenado em cache por programas do lado do cliente. Se estiver definido como 0, indica que o registro não deve ser armazenado em cache. O intervalo é definido para estar entre 0 a 2147483647 (perto de 68 anos!).

Class - IN - A classe mostra o tipo de registro. IN equivale a Internet. Outras opções são todas históricas. Assim, enquanto o seu DNS está na Internet ou Intranet, você deve usar IN.

Nameserver - **zeus.luckygav.net.** - O nameserver é o servidor que contém os arquivos de zona. Pode ser um servidor externo, nesse caso, o nome de domínio inteiro deve ser especificado seguido por um ponto. Caso seja definido neste arquivo de zona, ele pode ser escrito como ?**ns**.?

Endereço de email - root.ns.nameserver.com. - Este é o email do administrador do nome de domínio. Agora, isso é realmente confuso, porque as pessoas esperam um **@** em um endereço de e-mail. No entanto, neste caso, o e-mail é enviado para **pedro@luckygav.net**, mas escrito como **pedro.luckygav.net**. E **sim**, lembre-se de colocar o ponto atrás do nome de domínio.

Número de série - 2016123001 - Este é um tipo de sistema de numeração de revisão para mostrar as alterações feitas à Zona DNS. Este número tem de incrementar, sempre que qualquer alteração é feita para o arquivo de zona. A convenção padrão é usar a data de atualização YYYYMMDDnn, onde nn é um número de revisão no caso de mais de uma atualização seja feita em um dia. Portanto, se a primeira atualização feita hoje seria 2016123000 e segunda atualização seria 2016123001.

Refresh - 55080 - Este é o tempo (em segundos) quando o servidor DNS escravo será atualizado a partir do mestre. Esse valor representa a freqüência com que um servidor secundário irá verificar o servidor primário para ver se o número de série da zona aumentou (para que ele saiba solicitar uma nova cópia dos dados para a zona). Ele pode ser escrito como "15h20M" indicando 15 horas e 20 minutos. Se você tiver um servidor de Internet regular, você pode mantê-lo configurado entre 6 a 24 horas.

Tentar novamente - 7200 - Agora suponha que um servidor escravo tentou entrar em contato com o servidor mestre e não conseguiu entrar em contato porque ele estava inativo. O valor Repetir (tempo em segundos) informará quando voltar. Esse valor não é muito importante e pode ser uma fração do valor de atualização.

Expiração - 3600000 - Este é o tempo (em segundos) que um servidor escravo manterá um arquivo de zona em cache como válido, se não puder entrar em contato com o servidor primário. Se esse valor é definido para 2 semanas (em segundos), significa que o servidor escravo ainda seria capaz de dar informações de domínio de seu arquivo de zona em cache por 2 semanas, sem que ninguém percebesse a diferença. O valor recomendado é de 2 a 4 semanas.

Mínimo - 600 - Este é o tempo padrão (em segundos) que os servidores escravos devem armazenar em cache o arquivo de Zona. Este é o campo de tempo mais importante no Registro SOA. Se as informações de DNS continuarem mudando, mantenha-as por um dia ou menos. Caso contrário, se o registro DNS não mudar regularmente, intensifique-o entre 1 a 5 dias. O benefício de manter esse valor alto, é que as velocidades de seu site aumentam drasticamente como resultado de pesquisas reduzidas.

### Registro SRV

A teoria por trás de SRV é que, dado um nome de domínio conhecido, exemplo.com, por exemplo, dado um determinado serviço, WEB (http) que é executado no TCP, uma consulta DNS pode ser emitida para encontrar o nome de host que os fornece em tal domínio - e que pode ou não estar dentro do domínio.

**Exemplo de registro SRV**

Serviço.Protocolo.Nome TTL Classe rr PRI PESO PORTA ALVO

**_http._tcp.exemplo.com. IN SRV 0 5 80 servidor1.exemplo.com.**

**Serviço**

Define o nome do serviço simbólico (ver IANA port-numbers) preenchido com um **'_'** (sublinhado). Não é sensível a maiúsculas ou minúsculas. Os valores mais comuns são:

_http - serviço web

_ftp - serviço de transferência de arquivos

_ldap - Serviço LDAP (controle de acesso de diretórios)

**Protocolo**

Define o nome do protocolo (consulte IANA nomes de serviço) precedido por um '_' (sublinhado). Não é sensível a maiúsculas ou minúsculas. Os valores mais comuns são:

_tcp - protocolo TCP

_udp - protocolo UDP

**Nome**

Definido na RFC 2782, mas não está bem claro. Deixando a entrada em branco (sem um ponto) irá substituir a raiz de zona atual, ou você pode explicitamente adicioná-lo como no _http._tcp.example.com acima. (Com um ponto).

**TTL**

Padrão TTL parâmetro. Para obter mais informações sobre valores TTL.

**PRI**

A prioridade relativa deste serviço (intervalo 0 - 65535). A prioridade mais baixa é a mais alta.

**PESO**

Utilizado quando mais de um serviço com a mesma prioridade. Um inteiro não assinado de 16 bits no intervalo 0 - 65535. O valor 0 indica que não deve ser aplicada nenhuma ponderação. Se o peso for 1 ou maior, é um número relativo no qual o maior é mais frequentemente entregue, ou seja, dado dois registros SRV com Prioridade = 0, um com peso = 1 e o outro com peso 6 terá o seu peso RR entregue primeiro 6 vezes fora de 7 pelo servidor de nome.

**PORTA**

Normalmente, o número de porta atribuído ao serviço simbólico, mas não é um requisito, por exemplo: É permissível definir um serviço _http com um número de porta de 8100 em vez da porta 80 que seria o mais usual.

**ALVO**

O nome do host que irá fornecer este serviço. Não precisa estar na mesma zona (domínio).

### Registro TXT

Um registro TXT permite que um administrador insira texto arbitrário em um registro DNS. Por exemplo, esse registro é usado para implementar a especificação Sender Policy Framework (SPF) ou seja, mecanismo para evitar spoofing.

**Exemplo de registro TXT**

Domínios SPF têm de publicar pelo menos duas diretivas: um identificador de versão e um mecanismo padrão.

**luckygav.net. TXT "v = spf1 -all?**

Este é o registro SPF mais simples possível: significa que seu domínio **luckygav.net** nunca envia e-mails. Faz sentido fazer isso quando um domínio é usado apenas para serviços da web e não trata de e-mails.

Os servidores MX enviam e-mails, configuramos:

**luckygav.net. TXT "v = spf1 mx -all?**

Vamos fingir que **luckygav.net** tem dois servidores MX, mx01 e mx02. Ambos seriam autorizados a enviar e-mail de **luckygav.net** e outras máquinas no domínio também podem enviar e-mail, configuramos:

**luckygav.net. TXT "v = spf1 mx ptr -all?**

Isso designa todos os hosts cujo hostname PTR está no domínio **luckygav.net**.

Quaisquer outras máquinas que não estejam no domínio também enviem e-mail desse domínio, configuramos:

**luckygav.net. TXT "v = spf1 a:luckygav.net mx ptr -all"**

O endereço IP do luckygav.net não aparece na lista de servidores MX. Portanto, adicionamos um mecanismo "a" ao conjunto de diretrizes para combiná-lo.

**luckygav.net. TXT "v = spf1 a mx ptr -all"**

Cada um de seus servidores de email devem ter um registro SPF também. Quando seus servidores de email criarem uma mensagem de retorno, eles a enviarão usando um remetente de em branco: **<>**. Quando um MTA (**Mail Traffic Agent - nada mais que um servidor de transporte de correio**) SPF vê um remetente em branco, ele irá executar a procura usando o nome de domínio HELO em vez disso do remetente em branco. Esses registros abaixo cuidam desse cenário.

**amx.mail.net. TXT "v = spf1 a -all"**

**mx.mail.net. TXT "v = spf1 a -all"**

### Registro NAPTR

Os registros NAPTR (NAPTR significa "Naming Authority Pointer") são um tipo mais novo de registro DNS que suporta a reescrita baseada em expressões regulares.

**Exemplo de Registro NAPTR**

**$ ORIGIN 3.8.0.0.6.9.2.3.1.1.5.5.e164.arpa.**

**NAPTR 10 100 "u" "E2U + sip" "! ^. * $! Sip:info@luckygav.net!" .**

**NAPTR 10 101 "u" "E2U + h323" "! ^. * $! H323:info@luckygav.net!" .**

**NAPTR 10 102 "u" "E2U + msg" "! ^. * $! Mailto:info@luckygav.net!" .**

Este conjunto de registros mapeia o número de telefone +551132960083 em três possíveis URIs ordenados identicamente, com uma preferência para SIP, H323 e, finalmente, e-mail. Em cada caso, a expressão regular corresponde ao AUS completo (^. $) E o substitui por um URI (por exemplo, **sip:info@luckygav.net**). Como este é um registro de terminal, este URI é retornado para o cliente. Embora a maioria dos registros NAPTR substituem completamente o AUS, é possível a expressão regular referenciar retroativamente parte do AUS **(Application Unique String - um método de acesso direto a URI em um string único)**, para pegar um número de ramal, por exemplo:

$ ORIGIN 0.6.9.2.3.1.1.5.5.e164.arpa. *

**NAPTR 10 100 "u" "E2U + sip" "! ^ + 551132960 (. *) $! Sip: \ 1@luckygav.net!" .**

### Registro DNS curinga

Um registro DNS curinga é um registro em um arquivo de zona DNS que irá corresponder a todas as solicitações de domínio inexistentes, ou seja, domínio para os quais não há registros.

### Zona DNS

**A segunda parte da configuração de um servidor DNS é os arquivos de zona**.

Um arquivo de zona contém os registros de recurso do DNS para todos os domínios associados à zona. Os arquivos de zona armazenam todos os dados dos serviços oferecidos por um servidor DNS. Nesta seção, vamos descrever o formato do arquivo de zona básica [2].

O arquivo de zona precisa ser criado dentro do diretório de trabalho do servidor DNS. Não há necessidade de nomes específicos de arquivos de zona, mas um padrão razoável é db.domain.name, o nome do domínio precedido por db. Em nosso caso, apenas por questões didáticas, usamos o **db.luckygav.net**.

O formato básico do arquivo de zona é:registros de tempo de vida (TTL) seguido pelo início de autoridade (SOA). O TTL instrui os servidores DNS não autoritativos, quanto tempo devem armazenar em cache os registros recuperados do arquivo de zona. Quanto mais longo for este período, mais tempo levará para propagar as alterações nos arquivos de zona. Quanto mais curto o TTL, mais difícil será o funcionamento dos servidores DNS, porque os servidores que não são autoridade sobre o domínio terão que fazer a mesma pergunta/busca com mais freqüência. Valores de algumas horas a um dia são razoáveis.

Um valor TTL inteiro é interpretado como segundos, embora para aqueles de nós que não são bons de cálculo, adiciona-se **m** no final, significa minutos, **h** para horas, **d** para dias e **w** para semanas. Um dia seria representado por qualquer uma das seguintes linhas:

**$ TTL 86400**

**$ TTL 1440m**

**$ TTL 24h**

**$ TTL 1d**

A seção SOA é um detalhe importante e um pouco complexo, mas cada campo no **SOA** tem um propósito significativo e olhando uma parte de cada vez, fica simples. O **SOA** começa com o domínio principal da zona (usaremos **luckygav.net** neste estudo), a classe da zona (**IN**), **SOA** e os seguintes sete campos em ordem:

**MNAME:** O servidor mestre dns para a zona (por exemplo ns1.luckygav.net.).

**RNAME:** Um endereço de e-mail para alguém responsável pelo domínio (com **@** substituído por um **.** (ponto)) como, por exemplo, **adm.luckygav.net**, no lugar de adm@luckygav.net**.**

**Serie Number:** Este valor é talvez a maior fonte de risco do cabeçalho relacionado ao DNS. Para tornar as coisas mais rápidas e eficientes, o BIND processa arquivos de zona em outro formato. Quando o BIND carrega um arquivo de zona na inicialização, ele verifica o número de série e só processa o arquivo de zona se o número de série for maior do que a versão processada anteriormente. Portanto, se você alterar o arquivo de zona, mas não o número de série, o BIND ignorará as alterações.

Um formato comum para o número de série contém a data e um número de série exclusivo (AAAAMMDDNN), como 2017012402 para a segunda revisão (02) do arquivo em 24 de janeiro de 2017. Isso permite 100 alterações no arquivo em um dia. Se mais mudanças são necessárias, eu recomendo que você planeje melhor as alterações.

Servidores secundários ou escravos podem ser configurados para consultar o servidor mestre periodicamente para verificar se o número de série foi alterado e, portanto, se ele precisar, atualizar o arquivo de zona.

**Retry :** Se o servidor DNS mestre da zona falhar em responder a uma solicitação de atualização de um servidor escravo, o servidor escravo perguntará isso a cada período deste tempo. Normalmente, em uma hora ou menos.

**Expire :** No caso de uma falha do servidor DNS mestre, um servidor escravo continuará a utilizar os dados existentes durante **este** período de tempo. Depois que o tempo de expiração passou, os dados são considerados obsoletos e não serão usados no momento em que o domínio não resolver logger. Esse valor deve ser longo o suficiente para permitir que as interrupções do servidor mestre sejam corrigidas, na ordem das semanas.

**Negative Caching TTL :** As respostas negativas (como quando um registro solicitado não existe) também podem ser armazenadas em cache em servidores que não são autoridade sobre o domínio. Este campo age como o TTL global, mas, especificamente para respostas negativas. Valores pequenos são apropriados (15m a 2h).

Os campos podem ser colocados entre parênteses se eles se estenderem sobre mais de uma linha. Juntando tudo isso, o arquivo de zona fica assim para o domínio luckygav.net (sem os registros de recursos)

**$ TTL 1d**

**luckygav.net. IN SOA ns1.luckygav.net (**

**adm.luckygav.net**

**2017012402**

**1h**

**15m**

**4w**

**1h)**

**Configuração de Registros e Zona de DNS**

Agora podemos juntar o que conhecemos, zona, registros e recursos.

Estes são os arquivos que contêm a lista de todos os hosts no seu domínio e seu endereço IP correspondente.

Primeiro, há uma série de registros DNS que precisa de uma pequena revisão.

**SOA** - Início da Autoridade. Este é o registro que indica que este servidor é autoridade para o domínio especificado.

**NS** - Servidor de nomes: Especifica o servidor de nomes a ser usado para procurar um domínio.

**MX** - Mail Exchange: Especifica o (s) servidor (es) de e-mail para o domínio.

**A** - Registro usado para vincular um FQDN a um endereço IP.

**CNAME** - Canonical name: Usado para atribuir aliases a registros **A** existentes.

**PTR** - Usado para referenciar recursos aos endereços IP do mapa para um FQDN.

Há muitos outros tipos de registros, mas estes são os registros mais comumente usados.

Um arquivo de zona contém duas partes. Primeiro, a seção SOA e, em seguida, a lista de registros DNS. Um arquivo típico de zona seria como algo abaixo:

$ TTL 86400

@ IN SOA mailer.luckygav.net. adm.luckygav.net.

2017111202; serial

21600; Atualizar a cada 6 horas

3600; Tente novamente após uma hora

604800; Expira após uma semana

86400); TTL mínimo de 1 dia

IN NS mailer.luckygav.net.

IN MX 10 mailer.luckygav.net.

mailer IN A 192.168.3.1

firewall IN A 192.168.3.19

switch IN A 192.168.3.3

relay IN A 192.168.3.20

cisco IN CNAME switch

www IN CNAME mailer

mrtg IN CNAME mailer

O registro SOA pode ser um pouco complicado. Primeiro, lista o servidor de nomes para o domínio e, em seguida, o endereço de e-mail da administração do domínio (observe que o @ foi substituído por um ponto). O número de série não tem de ser uma data, no entanto, sempre que houver uma alteração no arquivo de zona no servidor de DNS principal este número deve ser alterado, o número de série tem de ser aumentado por algum valor. Dessa forma, qualquer servidor escravo saberá que uma atualização foi feita, e eles (os dois servidores) farão uma transferência de zona para obter a nova cópia do arquivo de zona. Os outros números são explicados no próprio arquivo, e os números que apresentamos aqui são os valores padrão .

O próximo registro é o registro do servidor de nomes. Aqui, ele simplesmente se refere a si mesmo como o servidor de nomes, no entanto, se você tiver vários servidores para um domínio (um mestre, e pelo menos um escravo), você deve colocar uma entrada para cada servidor de nomes.

O registro MX também aponta para o mesmo servidor. Se tiver mais de um servidor de correio, pode adicionar vários registos MX. O valor é para prioridade; Quanto menor o número, maior a prioridade. Um servidor de correio secundário deve, portanto, ter um valor mais elevado (isto é, em nosso caso, 20).

A seguir estão todos os registros A sem qualquer ordem específica. Se você tem muitos hosts, você pode querer colocá-los em ordem alfabética ou numericamente, o que funcionar para você. E, no final, temos os registros CNAME. Desde que meu "mailer" servidor é também o meu servidor web, eu precisava do "www" para apontar para o mesmo endereço IP como "mailer".

E, agora, o arquivo de zona reversa com todos os registros PTR. Isso é realmente útil se você precisa procurar um nome de host quando você sabe o endereço IP.

$ TTL 86400

@ IN SOA mailer.luckygav.net. Hostmaster.luckygav.net.

2017111202; serial

21600; Atualizar após 6 horas

3600; Tente novamente em 1 hora

604800; Expira após uma semana

86400); Mínimo TTL de um dia

IN NS mailer.luckygav.net.

19 IN PTR firewall.luckygav.net.

3 IN PTR switch.luckygav.net.

1 IN PTR mailer.luckygav.net.

20 IN PTR relay.luckygav.net.

Não há muita diferença na forma como o arquivo de zona parece, exceto que ele contém apenas o registro SOA e registros PTR. O intervalo de endereços IP foi especificado no arquivo de configuração, portanto apenas o último octeto (19,3,1 e 20) está listado no arquivo de zona.

### Instalando o Servidor BIND no Linux.

Vamos utilizar a versão Bind9 em uma máquina Ubuntu.

Primeiro passo é instalar o pacote no Ubuntu:

Lembre-se de ser super usuário para fazê-lo.

**\#apt-get install bind9**

Aparecerá a tela seguinte:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/8/9/838999/36666.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/8/9/838999/36666.png)

Continuando…opte por “S” e a instalção procederá até o final.

Para ver se está tudo ok, digite o seguinte comando e aparecerá destacado, entre outras informações, que o **bind** está “rodando”.

**\#service bind9 status**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839001/36667.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839001/36667.png)

Pressione a tecla “q” para sair dessa tela.

Vamos começar a configurar. Comece com o comando abaixo. (Não esqueça, sempre como super usuário)

**\#vim /etc/bind/named.conf.local**

Apague todas as linhas que estiverem neste arquivo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839002/36668.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839002/36668.png)

Agora vamos criar os diretórios necessários para conter os arquivos que precisamos.

**\#cd /etc/bind**

**\#mkdir zones**

**\#cd zones**

Vamos criar a base de dados de nosso domínio.

**\#vim luckygav.net.db**

Digite os dados para ficar conforme abaixo. (substitua o domínio (luckygav.net) pelo teu domínio e os IPs pelos teus Ips).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839003/36669.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839003/36669.png)

Vamos agora fazer o sistema de busca inversa - **Reverse DNS LookUp**

**\#vim /etc/bind/zones/rev.0.168.192.in-addr.arpa**

Veja abaixo o que colocar neste arquivo. Não esqueça de trocar por seus dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839005/36671.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839005/36671.png)

**Está quase pronto!!! Tome uma xícara de café...**

Agora precisamos avisar ao sistema que este é o servidor de DNS que deve ser primeiro considerado. E que, caso os clientes deste servidor requisitarem URIs que não são conhecidas por este servidor, ele (o servidor) buscará “recursivamente” ao servidor que serve como alternativa (geralmente o servidor de DNS do provedor).

Para isto editamos o arquivo abaixo!!

**\#vim /etc/resolv.conf**

Atenção agora!! Talvez você tenha aberto o resolv.conf e recebido uma tela como a abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839006/36673.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839006/36673.png)

Estranho Não!

O que ocorre aqui é uma questão estratégica que muitos administradores acabam cometendo erros amadores?. Este computador/servidor está preparado (através de um moderno software a prova de leigos, mas que atrapalha muito os administradores, o Network-Manager) para receber IPs direto do roteador do provedor (aquele equipamento que os técnicos do provedor deixam em sua empresa/casa). Nem é o roteador mesmo, na verdade é uma caixinha que contém um computador preparado para ser um roteador, um firewall, um servidor de DHCP, um modem, um rádio transmissor e mais algumas outras coisinhas, e que chamamos simplesmente de roteador. Claro, nós profissionais de Redes de Computadore sabemos que é só uma apelido falar ?roteador? (sabemos mesmo? rsss...) , mas muitos outros leigos e até mesmo os técnicos do provedor pensam que aquilo é um roteador. Então, este computador ?pega? um IP automaticamente do servidor de DHCP (Dynamic Host Configuration Protocol) e pronto!!! Está feito o estrago!! Ora, um servidor que será usado por clientes não pode ter seu endereço IP sujeito a mudanças. **ELE PRECISA DE UM ENDEREÇO DE IP FIXO!!!!** Por tal motivo que o arquivo ?resolv.conf? está com estes dados. Então precisamos avisar ao sistema que este computador tem um IP fixo igual aquele que colocamos nos arquivos de zona do DNS.

**Cuidado!! Quando fizer isto você também precisa acessar aquela caixinha do provedor e avisar que o endereço de IP que você vai fixar, não pode ser usado mais por ninguém, ou seja, o servidor de DHCP não pode oferecer este endereço de IP para ninguém.**

Entre no arquivo **/etc/network/interfaces** e deixe um IP fixo para este servidor. Consulte os sites sobre Linux, pois este não é o escopo deste tópico.

Acertado isto, coloque o endereço do provedor para o IP do DNS, vai servir como DNS para o servidor de DND. (ãh?) Sim, o servidor de DNS precisa ter algum servidor de DNS que o auxilie quando ele ainda não sabe os endereços de IP dos domínios. Geralmente é o IP do provedor. Veja como fica abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839007/36675.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839007/36675.png)

**PRONTO!!!!!**

Agora você pode reinicializar o BIND9 e verificar o status do servidor. Deve aparecer algo como abaixo. Qualquer mensagem em vermelho, simplesmente procure por erro nos arquivos de configuração. Procure pontos (.) que estão faltando, registros, nomes corretos de arquivos e domínios e Ips.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839008/36677.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839008/36677.png)

Agora pegue outro computador (pode ser um virtual) que esteja na mesma rede que seu novo servidor de DNS e aponte o DNS para o IP de seu servidor. Ele deve continuar resolvendo nomes!!!