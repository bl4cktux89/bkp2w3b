### Introdução

Atualmente, um dos processos mais utilizados em nossas redes e na internet é a transferência de arquivos. Embora a transferência de arquivos possa ser dada por meio dos protocolos HTTP e SMTP, o FTP (File Transfer Protocol, Protocolo de transferência de arquivo) é mais adequado, pois utiliza mecanismos de controle e confiabilidade mais eficientes. Por esse motivo o FTP é o protocolo padrão da arquitetura TCP/IP utilizado para copiar arquivo de um host para outro.

O FTP veio a resolver alguns problemas relacionados, por exemplo, a convenções de nomes de arquivos e a estruturas de diretório diferentes entre o host emissor e receptor. Para tanto, o FTP se difere de outras aplicações TCP/IP, ao utilizar duas conexões distintas entre os hosts. Uma delas é utilizada para transporte de dados propriamente dita e a outra é utilizada para transporte de informações de controle, tais como, comandos e respostas, o que aumenta consideravelmente a sua eficiência em relação a outros protocolos.

A **conexão de controle** utiliza regras de comunicação muito simples, transferindo apenas uma linha de comando ou uma linha de resposta por vez. Em contrapartida, a conexão de dados utiliza regras mais complexas em função dos diferentes tipos de dados que devem ser transferidos. Entretanto, essa complexidade fica a cargo da aplicação FTP e não da camada de transporte. Para o TCP ambas as conexões são tratadas da mesma forma (Forouzan, B. A, 2010).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/0/1768091/39669.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/0/1768091/39669.png)

### Atenção

**O serviço FTP utiliza os serviços do TCP, estabelecendo duas conexões TCP: uma conexão de controle na porta 21; e a transferência de dados na porta 20.**

A figura abaixo mostra a arquitetura simplificada do FTP. O cliente tem três componentes básicos: a interface com o usuário, processo cliente de transferência de arquivo e processo cliente de controle. No lado do servidor existem dois componentes, processo servidor de controle e processo servidor de transferência de dados. A conexão de controle é estabelecida entre os processos de controle do host e do servidor e a conexão de transferência de dados é estabelecida entre os processos de transferência de dados também entre cliente e servidor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/0/1768093/39670.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/0/1768093/39670.png)

Fonte: Forouzan, B. A, 2010

A **conexão de controle** permanece estabelecida durante toda a atividade de uma sessão FTP. Por outro lado, a **conexão de dados** é aberta e encerrada com base no envio e recebimento do arquivo a partir do momento em que a conexão de controle é estabelecida. Uma vez encerrada a transmissão de dados, a conexão de dados se encerra. Esse processo pode ser realizado quantas vezes forem necessários, desde que a conexão de controle esteja aberta (Forouzan, B. A, 2010). Como o FTP envia informações a partir de uma sessão de controle separada dizemos que tais informações são enviadas **fora da banda**. O HTTP, em contrapartida, envia linhas de cabeçalho de requisição e resposta pela mesma conexão TCP que carrega o próprio arquivo transferido (kurose, J. 2013).

### Comunicação via conexão de controle

A conexão de controle é usada para envio de informações, tais como, identificação do usuário, senha, comandos para mudar de diretório remoto e comando de envia (put) e receber (get) arquivos. Os principais comandos são mostrados na tabela abaixo. Para tanto, o FTP usa estratégia semelhante ao protocolo SMTP em suas conexões de controle. Ele utiliza o conjunto de caracteres ASCII de 7 bits. Esse método simples é adequado para uma conexão quando se tem apenas uma linha curta para enviar comandos (ou receber) de cada vez. Deste modo, não precisamos nos preocupar com o formato do arquivo a ser transferido ou recebido.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/8/0/1758092/39674.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/8/0/1758092/39674.png)

### Comunicação via Conexão de Dados

Como já discutimos, o objetivo da conexão de controle é bem distinto da conexão de dados. A transferência de arquivos ocorre por meio da conexão de dados sob o gerenciamento da conexão de controle e de seus comandos de controle. A transferência de arquivos via FTP atende uma das três finalidades a seguir.

- Um arquivo deve ser copiado do servidor para o cliente. Esse processo é denominado recuperação de arquivo sob supervisão do comando RETR.
- Um arquivo deve ser copiado do cliente para o servidor. Esse processo é chamado de armazenamento de arquivo e corre sob supervisão do comando STOR.
- A lista de arquivos deve ser enviada do servidor para o cliente. Isso é feito sob supervisão do comando LIST.

### Atenção

**O FTP trata uma lista de nomes de arquivos ou diretórios como um arquivo. Ela é transmitida via conexão de dados**

Antes de transmitir um arquivo por meio da conexão de dados, o cliente deve definir a estrutura de dados, o tipo de arquivo e o modo de transmissão na conexão de controle. Ao definir esses três atributos resolvemos problema de heterogeneidade das comunicações. Os três atributos são explicados a seguir com base na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/0/1768094/39671.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/8/0/1768094/39671.png)

Fonte: Forouzan, B. A, 2010

- **Tipo de arquivo:** O FTP pode transferir dados por meio do tipo de arquivo ASCII, EBCDIC ou imagem. O arquivo ASCII é o formato padrão para transferência de texto. Sendo cada caractere codificado usando-se 7 bits. Se um ou ambos os lados utilizam codificação EBCDIC (utilizado pela IBM), o arquivo pode ser transferido usando-se essa codificação. O arquivo de imagem utiliza o formato padrão para transferência de arquivos binários. Programas executáveis utiliza esse padrão.
- **Estrutura de Dados:** O FTP pode transferir um arquivo nas modalidades de estrutura de dados: estrutura de arquivo, o arquivo é um fluxo contínuo de byte (stream); estrutura de registro, o arquivo é dividido em registro para uso somente em arquivos texto; estrutura de páginas, o arquivo é dividido em páginas, cada uma das quais contendo um número e um cabeçalho, permitindo que as páginas podem ser armazenadas e acessadas de forma aleatória ou sequencialmente.
- **Modo de transmissão:** O FTP pode transferir um arquivo via **fluxo contínuo (stream), modo de blocos e modo comprimido**. No **fluxo contínuo** (padrão) os dados são entregues ao TCP na forma de fluxo contínuo de bytes. Quando se utiliza o modo em bloco, os dados são entregues ao TCP em blocos e cada bloco recebe um cabeçalho de 3 bytes. No **modo comprimido**, um arquivo, normalmente muito grande, é comprimido utilizando geralmente a codificação run-length. Neste tipo de compactação, a ocorrência consecutiva de uma mesma sequência de dados é substituída pela ocorrência e pelo número de repetições. Por exemplo, os espaços em um arquivo texto ou caracteres nulos em uma sequência de arquivo binário.

### TFTP

O Protocolo TFTP (Trivial file Transfer Protocol, protocolo de transferência de arquivo jasimples) é uma opção quando a robustez oferecida pelo protocolo FTP não é requerida em uma transferência de dados. Além disso, o TFTP não possui mecanismos de autenticação. Por esse motivo deve ser utilizado em transmissões na internet, limitando o seu uso para transferência de arquivos de configuração ou sistemas operacionais, de um PC para um switch ou de um PC para um roteador. Tais equipamentos devem estar habilitados a escutar a porta UDP de 69. Por se tratar de uma aplicação que utiliza UDP na camada de transporte, a correção de erros fica a cargo da camada de aplicação. Veja abaixo a simulação de transferência de arquivo de configuração do roteador para um servidor TFTP.