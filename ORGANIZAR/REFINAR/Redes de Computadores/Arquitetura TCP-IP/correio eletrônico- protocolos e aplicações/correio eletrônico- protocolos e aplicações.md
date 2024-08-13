### Introdução

O serviço de correio eletrônico, comumente chamado de e-mail, é uma das aplicações mais antigas utilizadas na Internet. Ele existe desde os primórdios da Internet, mas passou por grandes transformações ao longo do tempo. No seu início, as mensagens trocadas por e-mail eram compostas apenas por pequenas notas de texto. Ao passo que, atualmente, os serviços de e-mail incorporam diversas características, incluindo mensagens em anexo, hiperlinks, textos em formato HTML, fotos e respostas automáticas.

Assim como o correio normal, o e-mail é um meio de comunicação assíncrono – você envia uma mensagem de e-mail quando for conveniente para você, sem a ter que negociar com o seu remetente o horário e a data de entrega. Mas a grande vantagem, como você deve conhecer, está associada com a rapidez e a facilidade de distribuição (Forouzan, B. A, 2010).

### Componentes de um Serviço de e-mail convencional

Os principais elementos de um sistema de correio eletrônico são: **Agentes de usuários (UA), servidores de correio, Agente de Transferência de Mensagem (MTA) e Agente de Acesso a Mensagem (MAA)** (Forouzan, B. A, 2010):

- **Servidores de correio**: eles formam o núcleo da infraestrutura do e-mail. Cada usuário possui uma caixa de e-mail, que na verdade é um arquivo especial, com restrição de acesso, onde somente o proprietário da caixa de e-mail tem acesso a ela.
- **Agente de Transferência de Mensagem (MTA):** O principal protocolo utilizado como MTA **é o** SMTP. Usa o TCP para transferir dados de modo confiável do remetente para o destinatário. O SMTP, assim como a maioria dos protocolos da camada de aplicação utilizam o paradigma cliente-servidor, um lado cliente, que funciona no servidor de e-mail do cliente e um lado servidor, que funciona no destinatário do correio. Quando um servidor em envia a correspondência para outro, ele age como cliente SMTP e quando o servidor do destinatário recebe, age como servidor SMTP. Mais detalhes sobre o protocolo SMTP serão explicados mais a frente neste mesmo tópico.
- **Agente de Acesso a Mensagem (MAA):** Enquanto que a entrega das mensagens de correio eletrônico usa o SMTP, conhecido também como protocolo _push_ (O SMTP empurra a mensagem). Os MAA são considerados protocolos do tipo Pull; o cliente tem que puxar a mensagem no servidor. Atualmente, os principais protocolos do tipo MAA são o POP3 (Post Office Protocol version 3, Protocolo de acesso a correio versão 3) e o IMAP4 (Internet Mail Access Protocol, version 4, Protocolo de acesso a e-mail de internet, versão 4). Ambos serão descritos em detalhes na sequência neste mesmo tópico.
- **Agentes de usuário (UA)**: os agentes de usuário permitem que os usuários leiam, responda, encaminhem, componham e salvem as mensagens. O Microsoft Outlook e Apple Mail são exemplos de agentes de usuário. Tais agentes estão instalados nas máquinas dos usuários. Eles podem ser baseados em comandos, permitindo que o usuário digite comandos para enviar, receber etc. ou baseados em GUI (Interface Gráfica de Usuário). Eudora, Outlook e Netscape são exemplos de UA baseados em GUI. Os principais serviços oferecidos por um UA são mostrados na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753130/39868.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753130/39868.png)

Fonte: Forouzan, B. A, 2010

Para explicar a correlação entre os componentes usaremos quatro arquiteturas, conforme mostrado na figura que segue. Em todas as arquiteturas temos os usuários Alice e Bob, tendo sempre Alice como remetente e Bob como destinatário (Forouzan, B. A, 2010).

**Arquitetura 1 – Alice e Bob no mesmo sistema**

Quando o remetente (Alice) e o destinatário (Bob) estão no mesmo servidor de e-mail, é necessário apenas o **agente de usuário (UA)**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753160/39869.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753160/39869.png)

Fonte: Forouzan, B. A, 2010

**Arquitetura 2 – Alice e Bob em sistemas diferentes**

Quando o remetente (Alice) e o destinatário (Bob) estão em sistemas diferentes são utilizados dois agentes de usuário e um par de protocolos SMTP, um cliente e um servidor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753167/39870.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753167/39870.png)

Fonte: Forouzan, B. A, 2010

**Arquitetura 3 – Alice conectada por meio da LAN ou WAN e Bob diretamente ao seu sistema**

Quando o remetente (Alice) é conectado por meio da LAN ou WAN ao servidor de e-mail, é necessário dois agentes e dois pares do SMTP. O primeiro cliente SMTP esta localizado no computador de Alice, enquanto que o Servidor de e-mail de Alice possui o servidor SMTP. O segundo par SMTP consiste do cliente SMTP localizado no sistema de Alice e do servidor SMTP localizado no sistema de Bob, ambos conectados por meio da Internet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753174/39871.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/3/1/1753174/39871.png)

Fonte: Forouzan, B. A, 2010

**Arquitetura 4 – Ambos conectados por meio da LAN ou WAN**

Quando o remetente e o destinatário do correio eletrônico estão conectados por meio de uma rede LAN ou WAN são necessários dois agentes de usuário (UA) e dois pares de MTA (cliente e servidor) e um par de agente de acesso a mensagem (MAA, cliente e servidor). Normalmente o MTA é o protocolo SMTP e o MAA pode ser o protocolo POP3 ou IMAP4.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/0/4/1750485/39872.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/0/4/1750485/39872.png)

Fonte: Forouzan, B. A, 2010

### Protocolo SMTP

O protocolo SMTP foi definido pelo RFC 5321, como já discutido, ele é o principal protocolo utilizado para enviar correios eletrônicos na Internet, tanto de um cliente para um servidor, quanto para servidor-servidor. Só para você ter uma ideia, o SMTP foi definido originalmente em 1982, antes mesmo do protocolo HTTP, mas já era utilizado muito antes disso. As especificações gerais são detalhadas abaixo (Forouzan, B. A, 2010):

- O protocolo SMTP é um protocolo baseado em texto simples;
- As especificações originais contemplavam apenas texto ASCII de 7 bits, este protocolo não é ideal para a transferência de arquivos. Por exemplo, exige que os dados binários de multimídia fossem codificados em ASCII antes de serem enviados por meio do SMTP;
- Alguns padrões foram desenvolvidos para permitir a transferência de arquivos em formato binário através de texto simples, como o caso do MIME;
- Hoje em dia, quase todos os servidores SMTP suportam a extensão **8BITMIME**.
- Esse protocolo usa por padrão a porta 25 numa rede TCP (ou 465 para conexão criptografada via SSL).
- No Brasil, porém, desde 2013, provedores e operadoras de internet passaram a utilizar a porta 587, como medida de segurança para diminuir o número de spams.
- Da mesma forma que a busca de uma página na Internet, via DNS, os servidores de e-mail também são resolvidos por servidores tipo DNS. A resolução DNS de um servidor SMTP de um dado domínio é possibilitada por sua entrada MX (_Mail e__**X**__change_).

**Comando e respostas SMTP**

O SMTP usa **comando** e **resposta** para transferir entre um cliente MTA e um servidor (MTA), conforme mostrado na figura abaixo. Os principais comandos e respostas são mostrados na tabela abaixo.

![[Untitled 40.png|Untitled 40.png]]

![[Untitled 1 27.png|Untitled 1 27.png]]

### POP3

O POP3 é definido no RFC 1939 como um protocolo usado para acesso ao correio eletrônico, considerado um **Agente de Acesso a Mensagem (MAA).** O POP3 utiliza a porta 110 para abrir uma conexão com o servidor de e-mail. Embora mais simples, o POP3 funciona a partir de comando textuais semelhantes ao SMTP. Com a conexão ativada, o protocolo passa por três fases: autorização, transação e atualização (kurose, J. 2013).

Fase 1– Autorização: O agente do usuário (UA) envia o nome do usuário e a senha em texto aberto para autenticar o usuário. Entretanto, de acordo com RFC 1939, o POP3 pode utilizar autenticação MD5 para garantir a confidencialidade na autenticação.

Fase 2 – Transação: Nesta etapa recupera a mensagem e também pode marcar as mensagens que devem ser apagadas, remover marcas e também adquirir estatísticas do correio eletrônico. O POP3 em tem dois modos de operação: keep e delete: no modo keep, a mensagem é mantida no servidor e na delete, ela é mantida. Além disso, as mensagens podem ser listadas e baixar. Na figura abaixo mostramos de forma simplificada os comandos e respostas do POP3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/0/5/1750510/39873.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/0/5/1750510/39873.png)

Fonte: Forouzan, B. A, 2010

### Webmail

Atualmente muitos sites da Web fornecem serviços de e-mail gratuitos, como Gmail e o Uol. A Uninove também fornece o seu e-mail. Independente de qual provedor de e-mail vocês utilizam, a ideia por traz é muito simples. Considerando novamente que Alice faça parte do e-mail da Uninove, com alice@uninove.br, e deseja enviar uma mensagem para bob@usp.br, utilizando o serviço de webmail. A transferência da mensagem do servidor (@uninove.br) remetente para o servidor do correio do destinatário (@usp.br) ocorrera ainda por meio do protocolo SMTP. Entretanto, a transferência de mensagens do servidor @usp.br para o browser de Bob é feita pelo protocolo HTTP. Para ler a mensagem, Bob não utilizará POP3 ou IMAP4, utilizará também, normalmente, o protocolo HTTP.