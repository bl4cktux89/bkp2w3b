O _**Socket**_ teve origem na Universidade de Berkeley, como sendo a API (Application Programming Interface) de desenvolvimento do protocolo TCP/IP para o ambiente UNIX .

Um _**Socket**_ é similar a um descritor de arquivo. Ele identifica o ponto final _**(endpoint)**_ para a comunicação.

O s_**ocket**_, que é um manipulador _**(handle)**_, que está associado a um largo conjunto de dados armazenados na implementação do protocolo de rede. Quando uma operação para criar um _**socket**_ é chamada, o sistema retorna um manipulador, como descritor de _**socket**_. Esse descritor é usado em todos os outros comandos relacionados ao _**socket**_ e é intercambiável com o descritor de arquivo usado em funções _**read**_ e _**write**_.

Os dados associados ao _**socket**_ incluem várias informações, como o endereço IP das máquinas que estão se conectando, as portas dos dois lados da conexão TCP e o estado da conexão corrente.

A camada de _**sockets,**_  dentro do contexto da comunicação, corresponde a camada de Sessão do Modelo OSI, que tem como função o gerenciamento das sessões de comunicação processo a processo entre os _**hosts**_. Ela é também responsável por estabelecer e encerrar as conexões entre os aplicativos cooperantes

Para o ambiente Windows foi desenvolvido o _**Windows Sockets - Winsock**_, visando facilitar a interconexão entre as estações Windows, através do protocolo TCP/IP, que é base para o acesso a Internet. _**Windows Sockets**_ é uma interface aberta para programação em rede sob o Microsoft Windows.

A especificação da interface do Windows sockets define claramente a divisão entre a aplicação de rede e o protocolo da rede.

O Winsock API aumenta a funcionalidade dos _**sockets**_ de Berkeley, ao acrescentar extensões específicas do Windows para suportar a natureza orientada a mensagens do S.O. baseado no Windows.

Todas as aplicações que hoje em dia acessam a Internet diretamente da residência do usuário, usando FTP, E-mail, Telnet, SMTP, entre outros, utilizam os sockets como base de comunicação, através do protocolo TCP/IP.

Para o ambiente Windows, o relacionamento entre as aplicações e o ambiente de rede, pode ser demonstrado na figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256888/14303.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256888/14303.png)

Relacionamento da biblioteca dos sockets no ambiente Windows

Fonte:

Na API do _**sockets**_ é possível determinar se a comunicação que se vai estabelecer é _**com conexão - STREAM**_, ou _**sem conexão - DATAGRAMA**_.

Para se trabalhar numa comunicação _**baseada em conexão**_, na camada de transporte do TCP/IP, o protocolo utilizado é o TCP, determinando que somente após o estabelecimento de uma comunicação é possível efetuar troca de mensagens.

Para a abertura de uma conexão com _**sockets**_, é necessário que várias funções da biblioteca Winsock sejam chamadas. A figura 2 demonstra a seqüência de operações tanto no lado Servidor quanto no lado Cliente.

No caso de se estabelecer uma conexão Stream, o Servidor é primeiramente inicializado. A função Socket define o descritor no qual a aplicação se associará quando desejar transmitir uma mensagem. Posteriormente a função Bind interliga o descritor ao endereço IP da máquina servidora e a porta TCP/IP na qual as transmissões irão ocorrer. A função Listen permite ao Servidor ficar “escutando” qualquer solicitação de conexão.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256889/14306.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256889/14306.png)

Conexão Stream

Fonte:

Quando uma solicitação chega de um Cliente após ativar a função Connect, o Servidor cria um processo filho mediante a função Accept, numa nova porta TCP/IP. O pedido do Cliente é associado a esta porta, permitindo assim a transferência de dados pelas funções Send/Recv, deixando, desta forma, a porta original de conexão do Servidor livre para efetuar novas conexões.

Ao término da comunicação, o Cliente utiliza a função CloseSocket para fechar a conexão, liberando a porta do processo filho do Servidor para ser ligada a outro processo de comunicação. O Servidor só irá utilizar esta função quando for desligado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256890/14325.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256890/14325.png)

Fechamento da conexão

Fonte:

A seqüência e as funções definidas para uma conexão Datagrama são as mesmas da conexão Stream, excluindo apenas as funções Listen, Accept e Connect. Isto ocorre pelo fato do protocolo baseado em Datagrama não utilizar uma conexão real entre as máquinas       Figura 3 - Conexão Datagrama origem         e destino, implementando, automaticamente dentro das funções de troca de mensagens, Send/Recv, um cabeçalho com o endereço IP da máquina no qual será feita a comunicação.

Um ponto a ser observado, é que, para a transmissão, tanto na função Send ou Recv, os _**sockets**_ somente operam com dados do tipo Char.

Para a transmissão de dados puramente do tipo caractere, o sistema desenvolvido baseado em _**sockets**_ não impõe nenhuma restrição. Entretanto, para sistemas desenvolvidos sob o paradigma da Orientação a Objeto, que manipula tanto objetos simples, como complexos ou longos, é necessário que, ao se transmitir, se faça uma conversão da classe do objeto para o tipo Char. No momento em que a informação chega ao seu destino, é necessário que o receptor faça a reconversão, isto é, do tipo Char para o tipo original do objeto.

Esta peculiaridade para a transmissão de dados de tipos diferentes de Char, faz com que o destinatário da mensagem possua o conhecimento prévio de todos os tipos possíveis de objetos que podem ser transmitidos.

Interfaces de Comunicação utilizando Sockets

Windows sockets é um dos mecanismos existentes para o desenvolvimento de aplicações em rede por meio de troca de mensagens. A compatibilização entre as bibliotecas de sockets de diferentes fornecedores permite a troca de bibliotecas sem afetar as aplicações. Como dito anteriormente, a API do Winsock representa uma barreira bem definida entre as aplicações de rede e os protocolos utilizados.

A figura4 mostra a relação do Modelo Windows _**sockets**_ com o Modelo OSI/ISO

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256891/14328.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/8/256891/14328.png)

Relação do Modelo Windows sockets com o Modelo OSI / ISO

Fonte:

Pode-se notar que a interação da aplicação com o protocolo TCP/IP faz-se somente pela API que o Windows _**sockets**_ disponibiliza, minimizando assim maiores possibilidades de geração de erros.

Para que se estabeleça uma comunicação no padrão TCP, faz-se necessário seguir uma seqüência de operações pré-definidas. O diagrama de estado da seqüência de conexão Stream Socket, pode ser visto na figura 5.

O Servidor deve ser sempre colocado “no ar”, antes de qualquer tentativa de comunicação. Para esta abertura de conexão com _**sockets**_, é necessário que várias funções da biblioteca Winsock sejam chamadas.

A função _**Socket**_ define o _**socket**_, que é um descritor a partir do qual a aplicação se associará quando desejar transmitir uma mensagem. O Servidor, por sua vez, executa outras duas funções que são disparadas em seqüência: a função _**Bind**_, que associa o número de uma porta com o endereço IP da máquina servidora, e a função _**Listen**_, que fica “escutando” na porta selecionada esperando que haja uma solicitação de conexão.

Quando a função _**Connect**_ for ativada pelo Cliente, uma solicitação de conexão para o Servidor é enviada e, caso a resposta a esta solicitação seja afirmativa, o Cliente e o Servidor passam para o estado de _**conectado**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/9/256911/14330.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/9/256911/14330.png)

Diagrama de estado do Stream Socket

Fonte:

Uma vez estabelecida a conexão, a troca de mensagem passa a ser efetuada e a função Recv retira do buffer de leitura as informações que foram trocadas entre o Cliente e o Servidor. Caso não se consiga enviar alguma mensagem pela função Send, por causa do estouro da capacidade do buffer, os dados são armazenados e retransmitidos posteriormente.

Os dados OOB (_**Out-of_Band**_) possuem um nível de prioridade de transmissão acima dos outros dados. Isto possibilita uma alteração na seqüência a ser transmitida, porém esta interferência na seqüência fica transparente ao usuário.

Ao término da comunicação, o Cliente utiliza a função CloseSocket para fechar a conexão, liberando a porta do processo filho do Servidor para ser ligada a outro processo de comunicação. O Servidor só irá utilizar esta função quando ele for desligado.

Portanto, primeiro o Servidor é posto no “ar” (1), em seguida o Cliente escolhe o nome de Servidor e a porta no qual sera feita a conexão (2a) e solicita uma conexão (2b), quando a conexão é aceita, o Servidor cria um processo filho, numa nova porta TCP/IP (3), associando o pedido do Cliente à esta porta, permitindo assim a troca de mensagens (4), deixando a porta original da conexão do Servidor livre para efetuar novas conexões, como pode ser visto na figura 6.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261711/14333.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261711/14333.png)

Criação de Processo Filho para a comunicação

Fonte:

Caso ocorra uma perda de conexão, tanto por parte do Cliente quanto pelo Servidor sem antes ter sido efetuada a função CloseSocket, quem ainda estiver “no ar” não poderá reutilizar a porta que estava sendo utilizada até que o seu fechamento se dê de forma correta. Para evitar que problemas desta natureza possam vir a ocorrer, é necessário o desenvolvimento de uma função de _**Time-out**_, de modo a proporcionar um nível de segurança ainda maior para as conexões.

A função de _**Time-out**_ fica checando se existe troca de informações nas conexões existentes, e permite que a função CloseSocket seja ativada automaticamente ao se verificar a inexistência de qualquer tipo de troca de mensagem após um determinado tempo, possibilitando assim a otimização das portas do protocolo TCP/IP.