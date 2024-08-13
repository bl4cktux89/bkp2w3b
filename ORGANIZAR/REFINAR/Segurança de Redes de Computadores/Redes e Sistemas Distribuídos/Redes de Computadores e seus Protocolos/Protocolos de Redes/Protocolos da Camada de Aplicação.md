[![](https://ampli-images.s3.amazonaws.com/production/0ebb7093-c4e3-4855-a3bb-14fb43e45ed5/original)](https://ampli-images.s3.amazonaws.com/production/0ebb7093-c4e3-4855-a3bb-14fb43e45ed5/original)

A camada de aplicação é uma camada composta por protocolos de rede de nível de aplicação, que são acessadas e possuem interação direta com usuários. Esses protocolos são responsáveis pela operacionalização de sistemas e aplicações finais para o usuário.

Conforme definido por Tanenbaum (2011), as camadas abaixo da camada de aplicação têm a função de oferecer um serviço de transporte confiável, mas, na verdade, elas não executam nenhuma tarefa para os usuários. Há protocolos nas camadas inferiores que entregam serviços de transporte confiável e não confiável.

A camada de aplicação define como os programas vão se comunicar com as aplicações de rede e como se dará o gerenciamento da interface com o que o usuário irá utilizar para executar a aplicação. Em geral, as aplicações são executadas em um browser (navegador) de internet.

A seguir, vamos descrever alguns dos principais protocolos da camada de aplicação.

**HTTP**

Protocolo de transferência de hipertexto utilizado em sistemas de WWW para representação de sistemas dentro de navegadores. Trata-se de um protocolo com intenso uso na atualidade, pois a grande parte dos sistemas da internet é executada utilizando-se esse protocolo. Conforme Kurose e Ross (2013), o HTTP define como os clientes requisitam páginas aos servidores e como eles as transferem aos clientes. Esse protocolo está no coração da Web; é por meio desse padrão de comunicação em redes que as páginas de conteúdo dos Websites são programadas e distribuídas via internet.

De acordo com Laudon e Laudon (2014), a WWW, formatada pelo HTTP, refere-se a um sistema de padrões universalmente aceitos para armazenar, recuperar, formatar e apresentar informações utilizando-se o modelo cliente/servidor em sistemas de redes de computadores. O protocolo TCP utiliza a porta 80 ou a porta 8080 para acessar o HTTP.

______

**🔁Assimile**

O HTTP é representado pelo conjunto de letras no início de um endereço dos serviço de WWW seguido do nome de domínio que especifica o servidor de arquivos que será identificado pelo _Uniform Resource Locator_ (URL) no aplicativo de navegação de internet (browser). Um exemplo completo de URL é: https://www.iana.org/.

Existem diversos _browsers_ (navegadores) disponíveis para acesso ao conteúdo da WWW. O primeiro a utilizar interface gráfica foi o Mosaic, que deu origem à Netscape, e os mais conhecidos na atualidade são: Google Chrome, Mozilla Firefox, Microsoft Edge, Microsoft Internet Explorer, Safari e Apple Opera.

______

**SMTP**

Protocolo de gerenciamento e distribuição de sistema de mensagens eletrônicas para sistemas de e-mail. De acordo com Kurose e Ross (2013), o correio eletrônico existe desde o início da Internet e era uma das aplicações mais populares em seu início. Em um sistema de correio eletrônico, há três componentes principais na operação do serviço: agentes de usuário, servidores de correio eletrônico e o protocolo SMTP.

Os agentes de usuário são compostos por aplicativos como M_icrosoft Outlook, Google Mail_, entre outros e permitem que os usuários verifiquem seus e-mails, leiam, respondam, encaminhem suas mensagens. Os servidores formam a infraestrutura principal do sistema, mantendo caixas postais em servidores. Por último, o SMTP, como protocolo de aplicação desse serviço, utiliza um serviço confiável de transferência via TCP para transferir as mensagens do servidor do correio do remetente para o destinatário. O protocolo TCP utiliza a porta 25 para acessar o SMTP; considerando-se o uso de criptografia, o TCP utiliza a porta 465 para o SMTP.

_**Post Office Protocol**_ **(POP3) e** _**Internet Mail Access Protocol**_ **(IMAP)**

Adicionalmente ao SMTP, existem outros dois protocolos na gestão de sistemas de correio eletrônico. O POP3 é um protocolo utilizado também para sistemas de correio eletrônico para o gerenciamento de _e-mails_, assim como o IMAP. O POP3 realiza o _download_ das mensagens de _e-mail_ ao acessar uma caixa de correio eletrônico para a caixa de entrada no sistema gerenciador, liberando o espaço ocupado pelas mensagens no servidor de _e-mail_, enquanto o IMAP é um protocolo de correio eletrônico que acessa a caixa de e-mail e sincroniza as pastas da conta do usuário, mas não faz seu _download_.

Esse protocolo é melhor para usuários que utilizam o sistema de correio eletrônico em diversas plataformas. O protocolo TCP utiliza a porta 110 para o protocolo POP3 e a porta 143 para o protocolo IMAP. Considerando-se o uso de criptografia, o TCP utiliza a porta 995 para POP3 e porta 993 para o IMAP. A figura abaixo apresenta uma tela de configuração (parcial) de conta utilizando protocolos de acesso ao serviço de correio eletrônico.

[![](https://ampli-images.s3.amazonaws.com/production/df840573-a536-4a3e-9009-8732aaaefc7a/original)](https://ampli-images.s3.amazonaws.com/production/df840573-a536-4a3e-9009-8732aaaefc7a/original)

Exemplo de configuração de conta em e-mail via protocolo POP3. Fonte: Wikimedia Commons.