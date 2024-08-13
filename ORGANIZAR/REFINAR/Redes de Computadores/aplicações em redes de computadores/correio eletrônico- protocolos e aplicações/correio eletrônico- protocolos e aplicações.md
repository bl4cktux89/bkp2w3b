O protocolo SMTP é um protocolo baseado em texto simples, onde um ou vários destinatários de uma mensagem são especificados e depois as mensagens são transferidas.

Esse protocolo usa por padrão a porta 25 numa rede TCP (ou 465 para conexão criptografada via SSL). No Brasil, porém, desde 2013, provedores e operadoras de internet passaram a utilizar a porta 587, como medida de segurança para diminuir o número de spans.

Da mesma forma que a busca de uma página na internet, via DNS, os servidores de e-mail também são resolvidos por servidores tipo DNS. A resolução DNS de um servidor SMTP de um dado domínio é possibilitada por sua entrada MX (_**M**__**ail e**__**X**__**change**_).

Dada a especificação inicial, que contemplava apenas texto ASCII, este protocolo não é ideal para a transferência de arquivos. Alguns padrões foram desenvolvidos para permitir a transferência de arquivos em formato binário através de texto simples, como o caso do MIME. Hoje em dia, quase todos os servidores SMTP suportam a extensão **8BITMIME**.

O SMTP é um protocolo de envio apenas, o que significa que ele não permite que um usuário descarregue as mensagens de um servidor. Para isso, é necessário um _**cliente de e-mail**_ com suporte ao protocolo POP3 ou IMAP, o que é o caso da maioria dos clientes atuais

O SMTP transfere mensagens de servidores de correio remetentes para servidores de correio destinatários. Definido pelo IETF RFC 821 o _**Simple Mail Transfer Protocol**_ (SMTP), é um serviço de correio modelo do serviço de transferência de arquivos FTP. SMTP transfere mensagens de correio entre os sistemas e fornece notificação sobre e-mails recebidos, conforme figura 1.

![[pic1.png]]

  

Trata-se de um protocolo que funciona em modo conectado, encapsulado no protocolo TCP. O correio é entregue diretamente ao servidor de correio do destinatário. O protocolo SMTP funciona graças a comandos textuais enviados ao servidor SMTP (para a [**porta**](http://br.ccm.net/contents/274-portas-entradas-tcp-ip) 25). Cada um dos comandos enviados pelo cliente (validados pela [**cadeia de caracteres ASCII**](http://br.ccm.net/contents/54-o-codigo-ascii) CR/LF, equivalente a um clique na tecla ENTER) é seguido de uma resposta do servidor SMTP composta de um número e de uma mensagem descritiva.

A porta 25, por ser utilizada há mais tempo, possui uma vulnerabilidade maior a ataques e interceptação de mensagens, além de não exigir autenticação para envio das mensagens, ao contrário da modificação para a porta 587, que oferece esta segurança a mais. A medida foi tomada através do CGI, a fim de minimizar a quantidade de SPAM’s que circulam por domínios brasileiros, a partir da constatação de que no início de 2010, o Brasil estava em segundo lugar no ranking mundial de envio de SPAM’s, devido a vulnerabilidades à _**malwares**_ ou configurações feitas incorretamente. Segundo o [**CGI**](http://www.nic.br/imprensa/clipping/2009/midia282.htm), a intenção é que a porta 25 seja bloqueada, minimizando os riscos de invasão.

Por esses motivos, diversos provedores optaram por adotar a porta 587, que para retransmissão da mensagem, utiliza autenticação do SMTP, o que dificulta o uso indevido de contas de e-mail ou de maquinas como zumbis, método bastante utilizado por spammers, em que maquinas de usuários aleatórios são usadas como emissores de SPAM, implicando na prática de [**Spoofing**](http://wiki.locaweb.com.br/pt-br/Spoofing), problema comum com usuários de e-mail.

A seguir apresentamos um formato textual para o envio de e-mail, considerando dois usuários, Alice e Bob, personagens muito conhecidos no mundo das redes.

Alice envia uma mensagem a Bob:

- Um cabeçalho de mensagem típico é semelhante a:

From: alice@uninove.br

To: bob@uninove.br

Subject: vamos estudar redes.

- Após o cabeçalho da mensagem, vem uma linha em branco e, em seguida, o corpo da mensagem (em ASCII).

![[pic2.png]]

  

Para o funcionamento do e-mail é necessário que o agente usuário (1), instalado na máquina da Alice envie a mensagem (2) para o servidor de correio local (3). O servidor de correio local da Alice também, por meio de mensagens SMTP, reencaminha a mensagem (4) para o servidor de correio do Bob (5). Ao final, por meio do protocolo POP o agente de na máquina usuário de Bob transfere o e-mail (6) para o agente instalado na máquina de Bob.

- Protocolos de e-mail e suas entidades comunicantes

![[pic3.png]]

  

As especificações de base do protocolo SMTP exigem que todos os caracteres transmitidos sejam codificados em [**código**](http://br.ccm.net/contents/54-o-codigo-ascii) ASCII de 7 de 7 bits e que o oitavo bit esteja explicitamente a zero. Assim, para enviar caracteres acentuados, é necessário recorrer a algoritmos que integrem as especificações MIME :

**SMTP**

Formato de mensagens (1) – Cabeçalho e tipos de mensagens SMTP

|Cabeçalho|Significado|
|---|---|
|[[To-]]|O(s) endereço(s) de correio eletrônico do(s) destinatário(s) principal(is)|
|[[Cc-]]|O(s) endereço(s) de correio eletrônico do(s) destinatário(s) secundário(s)|
|[[Cco-]]|O(s) endereço(s) de correio eletrônico para cópias carbono ocultas|
|[[From-]]|A(s) pessoa(s) que criou(aram) a mensagem|
|[[Sender-]]|O endereço de e-mail do remetente|
|[[Received-]]|A linha incluída por cada agente de transferência ao longo da rota|
|[[Return-Path-]]|Pode ser usada para identificar um caminho de volta ao remetente|
|[[Date-]]|A data e hora em que a mensagem foi enviada|
|[[Reply-To-]]|O endereço de e-mail para onde as respostas devem ser enviadas|
|[[Message-Id-]]|O número exclusivo que será usada para fazer referência a essa mensagem posterior|
|[[In-Reply-To-]]|Message-Id da mensagem original correspondente a essa reposta|
|[[References-]]|Outras Messa-Ids relevantes|
|[[Keywords-]]|Palavras-chave do usuário|
|[[Subject-]]|Pequeno resumo da mensagem apresentado em apenas uma linha|
|[[MIME-Version-]]|Identifica a versão do MIME|
|[[Content-Description-]]|String inteligível que identifica o conteúdo da mensagem|
|[[Content-ID-]]|Identificador exclusivo|
|[[Content-Transfer-Encoding-]]|Como o corpo da mensagem é codificado para transmissão|
|[[Content-Type-]]|Tipo e formato do conteúdo|

  
  

|Tipo|Subtipos de exemplo|Descrição|
|---|---|---|
|[[text]]|plain, html, xml, css|Texto em vários formatos|
|[[image]]|gif, jpeg, tiff|Imagens|
|[[audio]]|basic, mpeg, mp4|Sons|
|[[video]]|mpeg, mp4, quicktime|Filmes|
|[[model]]|vrml|Modelo 3D|
|[[application]]|octect-stream, pdf, javascript, zip|Dados produziados por aplicações|
|[[message]]|http, rfc822|Mensagem encapsulada|
|[[multipart]]|mixed, alternative, parallel, digest|Combinação de vários tipos|

  
  

Analogia do correio eletrônico referindo-se a envelopes e mensagens.

- (a) Correspondência em papel.
- (b) Correspondência eletrônica.

Analogia ao sistema postal

![[pic4.png]]

  

Comandos mais utilizados no envio SMTP

|Comando|Exemplo|Descrição|
|---|---|---|
|[[HELO (doravanteEHLO)]]|HELO 193.56.47.125|Identificação com a ajuda do endereço IP ou do nome de domínio do computador remetente|
|[[MAIL FROM-]]|MAIL FROM: expediteur@domaine.com|Identificação do endereço do remetente|
|[[RCPT TO-]]|RCPT TO: destinataire@domaine.com|Identificação do endereço do destinatário|
|[[DATA]]|DATA message|Corpo do mail|
|[[QUIT]]|QUIT|Saída do servidor SMTP|
|[[HELP]]|HELP|Lista dos comandos SMTP suportados pelo servidor|

  
  

Exemplo de Transferência de mensagem - cabeçalho

![[pic5.png]]

![[pic6.png]]

![[pic7.png]]

![[pic8.png]]

  

Características da RFC 821- [**http://www.cis.ohio-state.edu/htbin/rfc/rfc821.html**](http://www.cis.ohio-state.edu/htbin/rfc/rfc821.html)

Comandos SMTP comandos são mensagens ASCII enviados entre hosts SMTP. Comandos possíveis são os seguintes:

|Comando|Descrição|
|---|---|
|[[DATA 2]]|Começa composição de mensagens.|
|[[EXPN]]|Retorna nomes na lista de correio especificado.|
|[[HELO]]|Retorna identidade do servidor de correio.|
|[[HELP 2]]|Retorna informações sobre o comando especificado.|
|[[MAIL FROM]]|Inicia uma sessão de correio de host.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/correio eletrônico- protocolos e aplicações/Untitled Database/NOOP\|NOOP]]|Faz com que nenhuma ação, a não ser a confirmação do servidor.|
|[[QUIT 2]]|Encerra a sessão mail.|
|[[RCPT TO]]|Designa que recebe mail.|
|[[RSET]]|Redefine conexão mail.|
|[[SAML FROM]]|Envia uma mensagem para o terminal de usuário e caixa de correio.|
|[[SEND FROM]]|Envia uma mensagem para o terminal do usuário.|
|[[SOML FROM]]|Envia e-mail para terminal de usuário ou caixa de correio.|
|[[TURN]]|Interruptores papel do receptor e emissor.|
|[[VRFY]]|Verifica a identidade de um utilizador.|

  
  

Mensagens de mensagens de resposta SMTP consistem de um código de resposta, seguido de um texto explicativo, como segue:

|Código de Resposta|Texto explicativo|
|---|---|
|211|[[(Resposta ao status do sistema ou pedido de ajuda)]]|
|214|[[(Resposta para ajudar a pedido)]]|
|220|[[Serviço de correio pronto]]|
|221|[[Serviço de correio de conexão de fechamento]]|
|250|[[Transferência de correio concluída]]|
|251|[[Usuário não local, para a frente para]]|
|354|[[Comece a mensagem de correio, terminar com]]|
|421|[[Serviço de correio indisponíveis]]|
|450|[[Caixa postal indisponíveis]]|
|451|[[Erro local no comando de processamento]]|
|452|[[Sistema de armazenamento insuficiente]]|
|500|[[Comando desconhecido]]|
|501|[[Mal parâmetro]]|
|502|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/correio eletrônico- protocolos e aplicações/Untitled Database/Não comandar implementado\|Não comandar implementado]]|
|503|[[Sequência incorreta de comandos]]|
|504|[[Parâmetro não implementado]]|
|550|[[Caixa postal não encontrada]]|
|551|[[Usuário não local, tente]]|
|552|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/correio eletrônico- protocolos e aplicações/Untitled Database/Alocação de armazenamento excedida\|Alocação de armazenamento excedida]]|
|553|[[Caixa postal nome não permitida]]|
|554|[[Mail falha na transação do e-mail]]|

  
  

**O protocolo POP3**

O _**Post Office Protocol**_ (termo em inglês que, traduzido, significa "Protocolo dos correios"), ou **POP3**, é um protocolo utilizado no acesso remoto a uma caixa de correio eletrônico. Ele está definido no RFC 1939 e permite que todas as mensagens contidas numa caixa de correio eletrônico possam ser transferidas sequencialmente para um computador local. Dessa maneira, o utilizador pode ler as mensagens recebidas, apagá-las, responder-lhes, armazená-las etc.

O funcionamento do protocolo POP3 diz-se _**off-line**_, uma vez que o processo suportado se baseia nas seguintes etapas:

- É estabelecida uma ligação TCP entre a aplicação cliente de e-mail (_User Agent - UA_) e o servidor onde está a caixa de correio (_Message Transfer Agent - MTA_)
- O utilizador autentica-se;
- Todas as mensagens existentes na caixa de correio são transferidas sequencialmente para o computador local;
- As mensagens são apagadas da caixa de correio (opcionalmente, o protocolo pode ser configurado para que as mensagens não sejam apagadas da caixa de correio; se esta opção não for utilizada, deve-se utilizar sempre o mesmo computador para ler o correio eletrônico, para poder manter um arquivo das mensagens);
- A ligação com o servidor é terminada;
- O utilizador pode agora ler e processar as suas mensagens (_off-line_).

O **protocolo POP** (_**Post Office Protocol**_, que se pode traduzir por "protocolo de posto dos correios") permite, como o seu nome o indica, recuperar o seu correio num servidor distante (o servidor POP). É necessário para as pessoas não ligadas permanentemente à Internet, para poderem consultar os mails recebidos offline.

Existem duas versões principais deste protocolo, o POP2 e o POP3, aos quais são atribuídas respectivamente as portas 109 e 110, funcionando com o auxílio de comandos textuais radicalmente diferentes.

Tal como no caso do protocolo SMTP, o protocolo POP (POP2 e POP3) funciona graças a comandos textuais enviados ao servidor POP. Cada um dos comandos enviados pelo cliente (validado pela sequência CR/LF) é composto por uma palavra-chave, eventualmente acompanhada de um ou vários argumentos, e seguida de uma resposta do servidor POP, composta por um número e por uma mensagem descritiva.

  

|Comandos POP2|Descrição|
|---|---|
|[[HELLO]]|Identificação através do endereço IP do computador remetente|
|[[FOLDER]]|Nome da caixa a consultar|
|[[READ]]|Número da mensagem a ler|
|[[RETRIEVE]]|Número da mensagem a recuperar|
|[[SAVE]]|Número da mensagem a salvaguardar|
|[[DELETE]]|Número da mensagem a suprimir|
|[[QUIT 3]]|Saída do servidor POP2|

  
  

  

|Comandos POP3|Descrição|
|---|---|
|[[USER]]|Este comando permite a autenticação. Deve ser seguido do nome do utilizador, quer dizer, uma cadeia de caracteres que identificam o utilizador no servidor. O comando USER deve preceder o comando PASS.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/correio eletrônico- protocolos e aplicações/Untitled Database/PASS\|PASS]]|O comando PASS, permite indicar a palavra-passe do utilizador, cujo nome foi especificado aquando de um comando USER prévio.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/correio eletrônico- protocolos e aplicações/Untitled Database/STAT\|STAT]]|Informação sobre as mensagens contidas no servidor|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/correio eletrônico- protocolos e aplicações/Untitled Database/RETR\|RETR]]|Número da mensagem a recuperar|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/correio eletrônico- protocolos e aplicações/Untitled Database/DELE\|DELE]]|Número da mensagem a suprimir|
|[[LIST msg]]|Número da mensagem a afixar|
|[[NOOP 2]]|Permite deixar a ligação aberta no caso de inatividade|
|[[TOP]]|Comando que afixa n linhas da mensagem, cujo número é dado em argumento. No caso de resposta positiva do servidor, este devolve os cabeçalhos da mensagem, seguidamente uma linha virgem e por último as n primeiras linhas da mensagem.|
|[[UIDL msg]]|Pede ao servidor para enviar de novo uma linha que contém informações sobre a mensagem eventualmente dada em argumento. Esta linha contém uma cadeia de caracteres, chamada lista de identificador única, permitindo identificar de maneira única a mensagem no servidor, independentemente da sessão. O argumento opcional é um número que corresponde a uma mensagem existente no servidor POP, quer dizer uma mensagem não apagada)|
|[[QUIT 4]]|O comando QUIT pede a saída do servidor POP3. Provoca a supressão de todas as mensagens marcadas como apagadas e reenvia o estado desta acção.|

  
  

O protocolo POP3 gere assim a autenticação com a ajuda de um nome de utilizador e de uma palavra-passe, em contrapartida não é seguro porque a senha, assim como o mail, circula às claras (de maneira não codificada) na rede. Na realidade, de acordo com o RFC 1939, é possível codificar a palavra-passe que utiliza o algoritmo MD5 e assim beneficiar com uma autenticação protegida. Contudo, sendo este comando opcional, poucos servidores o aplicam. Por outro lado, o protocolo POP3 bloqueia a caixa de correio aquando da consulta, o que significa que uma consulta simultânea por dois utilizadores de uma mesma caixa de correio é impossível.

**O protocolo IMAP**

Assim como o POP, o protocolo IMAP protocolo também pode ser utilizado para transferir mensagem dos servidores SMTP para a caixa de correio local. O protocolo **IMAP** (_**Internet Message Access Protocol**_) é um protocolo alternativo ao protocolo POP3 mas que oferece muitas mais possibilidades como:

- Permite gerir vários acessos simultâneos
- Permite gerir várias caixas de correio
- Permite triar o correio de acordo com mais critérios

Seguem os principais comandos do protocolo IMAP

![[pic9.png]]

![[pic10.png]]