**1. Introdução**

No início da utilização da Internet (no final da década de 80), o principal protocolo utilizado era o _**Serial Line Internet Protocol**_ (SLIP), entretanto, era pouco eficiente para as emergentes conexões _**dial-up,**_ que conectavam os usuários através das linhas discadas, e neste aspecto em particular, o SLIP apresentava falhas que limitava o crescimento da Internet.

Para tal expansão, a Internet necessitava de um protocolo ponto a ponto, com diversas funções, tais como: garantir a integridade da comunicação, executar funções de autenticação, negociar condições das linhas de conexão e inclusive cuidar do tráfego de roteadores e de usuários domésticos, conectados através dos provedores de serviços da Internet, os _**Internet Service Provider**_ (ISP).

Foi então desenvolvido o protocolo PPP e definido na norma RFC 1661 que recebeu novas contribuições, descritas em outras normas RFCs, até se tornar o padrão existente atualmente.

O protocolo PPP trata da detecção de erros, executa a negociação e aferição do _**link**_ de conexão, aceita vários protocolos de nível 3 e até de nível 2 encapsulado, permite que endereços _**Internet Protocol**_ (IP) sejam negociados durante a conexão das estações, assim como a autenticação das estações que se conectam e muitas outras características que o tornaram o principal protocolo utilizado na Internet.

O PPP dispõe dos seguintes recursos listados:

1 – Atribuição dinâmica de endereços IP

2 – Configuração e controle do enlace de dados

3 – Encapsulamento e multiplexação de vários protocolos de rede

4 – Testes da qualidade do _**link**_ e determinação da velocidade mais adequada

5 – Detecções de erros

6 – Compactação de dados.

**2. Os Componentes do PPP**

O protocolo resolve a conectividade com a Internet usando três métodos principais. São eles:

- Método HDLC, empregado para encapsular datagramas em linhas seriais, ou seja, em _links_ ponto a ponto.
- Método _Link Control Protocol_ (LCP), empregado para configurar e testar o _link_ de enlace de dados.
- Método _Network Control Protocol_ (NCP) usado para configurar diferentes protocolos da camada de rede_._

O PPP foi projetado para suportar qualquer protocolo de nível 3, incluindo o IP e o _**Appletalk**_, utilizando a mesma arquitetura do modelo de referencia OSI trabalhando nas três camadas primeiras:

- Camada 1 (física) - ele utiliza meios síncronos e meios assíncronos para a conexão dos usuários, isso significa dizer que o PPP tanto pode trabalhar em _links_ dedicados do tipo canalização E1 ou Redes Digitais de Serviços Integrados (RDSI) no método síncrono, assim como em linhas discadas de telefonia comum para conexões _dial-up_ ao atendimento a usuários domésticos e seu respectivo _modem_.
- Camada 2 (de enlace) - o PPP executa a autenticação utilizando duas metodologias que estudaremos mais adiante, como o _Password Authentication Protocol_ (PAP) e o _Challenge Handshake Protocol_ (CHAP).

Vale ressaltar que também na camada 2 é executado o protocolo LCP responsável pelo teste e determinação da velocidade do _**link**_, ajustando a cada situação a melhor opção de conexão.

Já na camada 3 de rede o PPP executa o enquadramento de vários protocolos de nível três. Pode-se dizer, portanto, que o PPP é um multiprotocolo de nível superior, sendo adaptável a qualquer tipo de plataforma de comunicação. A figura 1 representa o quadro PPP, onde temos os campos e suas respectivas funções, onde:

- _**Flag**_: Indica o início e o final do quadro PPP e é formado pela sequência binária 01111110.
- Endereço: O PPP não atribui endereços individuais às estações, portanto o campo endereço sempre terá o endereço de broadcast, ou seja, 11111111.
- Controle: Formado por 1 byte com a sequência binária 00000011, que significa uma transmissão de dados de usuário sem sequência.
- Protocolo: Formado por 2 bytes identificando o protocolo enquadrado que o PPP está transportando naquele momento.
- Dados: Pode variar desde 0 a vários bytes dependendo exclusivamente do protocolo encapsulado que o PPP carrega neste momento, pois o tamanho do _**payload**_ depende de cada protocolo específico. O tamanho máximo padronizado do campo de dados é de 1500 bytes.
- _**Frame Check Sequence**_ (FCS): Campo com 2 bytes ou 16 bits, executa a verificação da integridade do quadro transmitido.

**3. O Protocolo LCP e NCP do PPP**

O protocolo PPP oferece um método automatizado de estabelecer, configurar, dar a manutenção e encerrar uma conexão ponto a ponto, seja ela estabelecida numa ligação síncrona ou assíncrona, passando por quatro fases:

- Fase 1: Negociação da configuração e estabelecimento da ligação em que um computador de origem envia quadros LCP para configurar e estabelecer o enlace de dados.

- Fase 2: Teste e determinação da qualidade do _**link**_ que será realizado antes da ativação dos protocolos de nível 3, sendo esta fase opcional.

- Fase 3: Negociação da configuração do protocolo de nível 3 onde o computador de origem envia quadros NCP para escolher e configurar estes protocolos e após esta configuração, os dados destes protocolos serão transmitidos.

- Fase 4: Encerramento da ligação onde o _**link**_ ficará conectado até que os protocolos LCP e NCP fechem a mesma ou até que ocorra um evento que force este fechamento prematuramente.

Os quadros LCP são divididos em três classes de operação, a saber:

- Classe de estabelecimento de _**link**_: Usado para estabelecer e configurar um _**link**_.
- Classe de encerramento de _**link**_: Usado para terminar um _**link**_.
- Classe de manutenção de _**link**_: usado para manter e gerenciar um _**link**_ executando o _**debug**_ quando necessário a um problema externo.

Na fase de negociação da configuração do estabelecimento do _**link**_, cada computador envia pacotes LCP para configurar e estabelecer a comunicação de dados. Os pacotes LCPs contêm campos de opções de configuração que permite aos dispositivos negociarem aspectos da comunicação, como o _**Maximum Transmission Unit**_  (MTU)_**,**_ compactação e autenticação, se for o caso.

Após esta etapa, o LCP irá abrir a conexão e negociar os parâmetros para a transferência dos protocolos de camada 3, sendo esta fase concluída quando um quadro de confirmação for enviado por ambos os lados.

Na fase da determinação da qualidade do _**link**_ opcional, o LCP poderá testar o _**link**_ e determinar qual é a melhor taxa de transferência de protocolos de nível 3, após a fase do estabelecimento da conexão e, deste modo, garantindo esta transferência.

Também após a fase do estabelecimento da conexão (e antes da configuração do protocolo de nível 3), o PPP poderá autenticar os envolvidos na comunicação pela escolha de uma das metodologias de verificação. O LCP poderá atrasar a transmissão das informações dos protocolos de nível 3 até que a autenticação seja concluída com êxito.

Quando a fase da determinação da qualidade do _**link**_ é encerrada, os protocolos da camada de rede podem ser configurados separadamente pelo protocolo NCP apropriado e serem ativados ou desativados a qualquer momento.

Os dispositivos PPP enviam pacotes NCP para escolher e configurar um ou mais protocolos do nível 3 (do modelo de referência OSI) e ao final desta configuração em pleno êxito, os pacotes desta camada poderão ser enviados.

**4. Autenticação no Protocolo PPP**

Referente às questões de segurança, o protocolo PPP utiliza dois outros protocolos para a autenticação, são eles:

- _**Password Authentication Protocol**_ – PAP

- _**Challenge Handshake Protocol**_ - CHAP

A fase de autenticação é opcional no protocolo PPP e ela acontece depois do estabelecimento do _**link**_ e da escolha do protocolo de autenticação preferido, onde um ou os dois extremos podem ser autenticados. A autenticação ocorre antes da fase de configuração do protocolo de nível 3, fase esta que negocia os protocolos do nível de rede que o PPP irá transportar.

As opções de autenticação exigem que o lado que gera a chamada insira informações de autenticação a fim de, garantir que o usuário tenha permissão da rede para realizar a chamada.

O processo de autenticação deve primeiramente ser configurado para acontecer no PPP e, após esta configuração, deve-se escolher qual método de autenticação será executado, o PAP ou o CHAP.

**4.1 Password Authentication Protocol (PAP)**

O PAP é um protocolo de autenticação de texto em formato simples, isso quer dizer que, o nome do usuário e a senha são esperados pelo servidor de acesso remoto e trafegam pela conexão em formato de texto aberto, sem nenhum critério de criptografia ou proteção.

Um usuário remoto que capture pacotes onde está acontecendo uma conexão autenticada, vai obter de maneira simples com a utilização de um _**software**_ de _**sniffer,**_ o nome do usuário e sua senha e, posteriormente, poderá utilizar esta identificação positiva para ganhar acesso ao sistema.

O PAP também não oferece nenhuma proteção contra ataques de tentativa e erro, ou seja, caso não seja validado o usuário na primeira tentativa de conexão, o transgressor poderá repetir a senha indefinidamente, sem um bloqueio de temporização das tentativas de _**logon**_.

O método de autenticação proposto pelo PAP é que após a conclusão da fase do estabelecimento do _**link**_, um _**handshake**_ duplo é usado pelo envio do nome de usuário e senha, esta ação é repetida vezes através do _**link**_ até que a autenticação seja confirmada. A figura 2 exemplifica a metodologia de autenticação do PAP.

Para melhorar a confiabilidade do PAP foi desenvolvido o _**Shiva Password Authentication Protocol**_ (SPAP), que é um protocolo de mão dupla empregado em servidores de acesso remoto _**Shiva**_, utilizando mecanismos de criptografia reversa. O protocolo SPAP é mais seguro que o PAP, porém menos seguro que o CHAP.

Um cliente de acesso remoto envia um pedido de autenticação SPAP, contendo o nome de usuário e uma senha (codificada) ao servidor de acesso remoto e este decifra e confere o usuário e senha. Caso esteja correto, o servidor enviará ao usuário uma mensagem _**SPAP Authenticate-ACK**_ ou uma mensagem _**SPAP Authenticate-NAK.**_ Quando as credenciais do usuário estiverem incorretas, a conexão será fechada e não será permitida a repetição, através de um controle de tempo das tentativas de _**logon**_.

**4.2 Challenge Handshake Authentication Protocol (CHAP)**

O CHAP é um protocolo de autenticação de desafio de resposta. Ele usa o protocolo de criptografia _**Message Digest**_ 5 (MD5) apenas em um único sentido para responder a um desafio de resposta emitido por um servidor de acesso remoto.

O protocolo CHAP é um avanço baseado nos protocolos PAP e SPAP, pois a senha nunca é enviada com o primeiro pacote de mensagem. Em realidade, a senha é usada para criar e enviar uma _**string**_ de desafio de um só sentido. O servidor conhecendo a senha do cliente duplica a operação para comparar o resultado das respostas do cliente que deseja a conexão ao referido servidor de acesso remoto.

O protocolo CHAP é usado praticamente em todas as conexões _**dial-up**_ e também de serviços de acesso à banda larga e funciona da seguinte forma:

O servidor de acesso remoto envia uma mensagem de desafio CHAP que contém uma chave de sessão e uma _**string hash**_ de desafio arbitrária. Um código _**hash**_ é comumente usado como valor de referência ao validar uma mensagem transmitida do servidor ao cliente. Um código _**hash**_ unidirecional é gerado a partir de uma mensagem antes da transmissão e enviado ao cliente. Após o envio, o cliente gera um _**hash**_ unidirecional da mensagem (usando o mesmo método aplicado pelo servidor). Se os valores coincidirem, os bytes da mensagem são considerados corretos, autenticando assim o cliente para acesso à rede.

Por exemplo: a palavra Uninove aplicada a um código _**hash**_ usando o protocolo MD5 de criptografia ficaria assim: 23bb187faece1874749c22b88c1b825c, ou seja, o desafio lançado pelo servidor diferentemente do protocolo PAP, agora será transmitido totalmente codificado, ficando praticamente impossível sua captura e utilização. A figura 3 ilustra a autenticação usando um _**handshake**_ triplo utilizado pelo protocolo CHAP.

Outro recurso apreciado do CHAP é a verificação periódica do usuário, melhorando assim as questões de segurança. O protocolo PAP só executa esta verificação uma única vez, o que o torna vulnerável a reprodução e a ações de _**hackers**_. Além disso, o PAP permite que o usuário tente obter a autenticação quando desejar, sem um texto desafio (pois não existe neste caso), tornando a conexão vulnerável a ataques de _**storm**_ (enxurrada de tentativas), enquanto o CHAP não permite que o usuário tente obter uma autenticação sem um texto desafio.

O CHAP oferece proteção contra ataques de reprodução através do uso de um valor de desafio variável, que é exclusivo e imprevisível. O uso de desafios repetidos visa limitar o tempo de exposição a qualquer ataque, sendo que a frequência e a temporização são controladas pelo servidor de acesso remoto.

**5. Para refletir**

- O PPP é o principal protocolo utilizado na Internet atualmente.
- Ele permite conexões de _links_ seriais síncronos e assíncronos.
- Ele é ideal para a conexão de _links_ em linhas telefônicas _dial-up_.
- O PPP executa a conexão, testes, verificação de qualidade e encerramento das ligações utilizando o protocolo LCP e NCP.
- O PPP pode enquadrar qualquer protocolo de camada 3 sem nenhum problema, sendo ideal para a conectividade de múltiplas plataformas.
- Diferentemente do HDLC, o PPP permite a autenticação dos participantes da comunicação.
- O PPP utiliza as três camadas iniciais do modelo de referência OSI nas suas operações.
- Você poderá selecionar o PAP ou o CHAP quando estiver configurando a autenticação PPP.
- O PAP é um protocolo de autenticação pouco eficiente, por demonstrar em texto claro o nome do usuário e a senha.
- O CHAP oferece proteção contra ataques de reprodução através do uso de um valor de desafio variável, que é exclusivo e imprevisível.
- O CHAP é o protocolo de autenticação mais usado nas conexões _dial-up_ e na validação do acesso remoto de clientes a servidores, que desejam se conectar.
- ERICSSON TELECOMUNICAÇÕES. Entendendo Telecomunicações. São Paulo. Érica, 2000.
- SOARES, L.F.G. _Redes de computadores: das LANs, MANs e WANs às Redes ATM_. Rio de Janeiro: Campus, 1995.
- STARLIN, G. _Redes de computadores, comunicação de dados: TCP/IP: conceitos, protocolos e uso. Rio de Janeiro_: Alta Books, 2004.

()

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258555/12668.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258555/12668.jpg)

Figura 2 - Autenticação PAP do PPP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258556/12669.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258556/12669.jpg)

Figura 3 - Autenticação CHAP do PPP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258552/11200.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258552/11200.jpg)

Figura 1 - Quadro PPP básico