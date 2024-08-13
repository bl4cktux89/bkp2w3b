O File Transfer Protocol (FTP) fornece os elementos básicos de compartilhamento de arquivos entre hosts. FTP usa TCP para criar uma conexão virtual para informações de controle e, em seguida, cria uma conexão TCP separada para transferências de dados. A conexão de controle usa uma imagem do protocolo TELNET para trocar comandos e mensagens entre hosts. A figura 1 apresenta a forma de transporte de arquivos entre os sistemas de arquivos local e remoto.

![[pic1 4.jpg|pic1 4.jpg]]

  

Na solicitação FTP, são utilizadas 2 instancias para acessar um arquivo no servidor (Estrutura Cliente- servidor), sendo uma para conexão e controle, utilizando a porta 21 e outra para conexão e troca de dados, utilizando a porta 20, conforme figura 2.

A transferência de arquivos acontece entre um computador chamado "cliente" (aquele que solicita a conexão para a transferência de dados) e um servidor (aquele que recebe a solicitação de transferência). O utilizador, através de software específico, pode selecionar quais arquivos enviar ou receber do servidor. Para existir uma conexão ao servidor, caso o servidor exija, o utilizador informa um nome de utilizador (ou username, em inglês) e uma senha password, bem como o nome correto do servidor ou seu endereço IP.

![[pic2 3.jpg|pic2 3.jpg]]

  

Durante a transferência de dados sobre a rede, quatro representações de dados podem ser utilizadas:

· Modo ASCII: usado para texto. Dado é convertido, se necessário, da representação de caracteres do host remetente para 8-bit em ASCII antes da transmissão, e (novamente, se necessário) para a representação de caracteres do host destinatário. Como consequência, esse modo é inapropriado para arquivos que contenham dados numéricos em binário, ponto flutuante ou forma decima codificada em binário.

· Modo imagem (normalmente chamada de modo binário): a máquina remetente envia cada arquivo byte a byte e como tal, o destinatário armazena o fluxo de bytes conforme ele os recebe (o suporte ao modo imagem tem sido recomendado para todas as implementações de FTP).

· Modo EBCDIC: utilizado para texto simples entre hosts utilizando o conjunto de caracteres EBCDIC.

· Modo local: permite que dois computadores com configurações idênticas enviem dados em um formato proprietário sem a necessidade de convertê-los para ASCII.

Alguns dos comandos mais comuns são descritos a seguir:

- USER username: usado para enviar identificação do usuário ao servidor.
- PASS password: usado para enviar a senha do usuário ao servidor.
- LIST: usado para pedir ao servidor que envie uma lista com todos os arquivos existentes no atual diretório remoto.
- RETR filename: usado para extrair um arquivo do diretório atual do hospedeiro remoto.
- STOR filename: usado para armazenar um arquivo no diretório atual do hospedeiro remoto.

Algumas respostas típicas, junto com suas possíveis mensagens, são as seguintes:

- 331 Nome de usuário OK, senha requisitada
- 125 Conexão de dados já aberta; iniciando transferência
- 425 Não é possível abrir a conexão de dados
- 452 Erro ao escrever o arquivo

**Estrutura do protocolo**

**Comandos:** Quadros de controle FTP são trocas TELNET e pode conter comandos Telnet e opção negociação. No entanto, a maioria dos quadros de controle FTP são texto ASCII simples e pode ser classificada como comandos de FTP ou mensagens de FTP. Os comandos padrão FTP são como se segue:

|Comando|Descrição|
|---|---|
|[[ABOR]]|Abortar processo de conexão de dados.|
|[[ACCT]]|Conta de privilégios de sistema.|
|[[ALLO]]|Alocar bytes para armazenamento de arquivos no servidor.|
|[[APPE]]|Anexar arquivo para o arquivo de mesmo nome no servidor.|
|[[CDUP]]|Mude para o diretório principal no servidor.|
|[[CWD]]|Altere o diretório de trabalho no servidor.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/transferência de arquivos- FTP e TFTP/Untitled Database/DELE]]|Excluir arquivo especificado no servidor.|
|[[AJUDA]]|Retorna informação sobre comando especificado.|
|[[LISTA]]|Lista informações se o nome é um arquivos de arquivos ou lista se o nome é um diretório.|
|[[Modo]]|Modo de transferência (S = córrego, B = bloco, C = comprimido).|
|[[MKD]]|Criar diretório especificado no servidor.|
|[[NLST]]|Listar o conteúdo do diretório especificado.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/transferência de arquivos- FTP e TFTP/Untitled Database/NOOP]]|Porque nenhum outro do que a confirmação do servidor ação.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/transferência de arquivos- FTP e TFTP/Untitled Database/PASS]]|Senha para o sistema de log-in.|
|[[PASV]]|Espera servidor pedido de conexão de dados.|
|[[PORT]]|Endereço IP e de dois bytes porta do sistema ID.|
|[[PWD]]|Mostrar diretório de trabalho atual.|
|[[SAIR]]|Faça logoff do servidor FTP.|
|[[REIN]]|Reinitialize conexão para log-in status.|
|[[DESCANSO]]|Transferência de arquivos Reiniciar dado offset.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/transferência de arquivos- FTP e TFTP/Untitled Database/RETR]]|Recuperar arquivo (cópia) do servidor.|
|[[RMD]]|Remover diretório especificado no servidor.|
|[[RNFR]]|Mudar o nome de caminho de idade.|
|[[RNTO]]|Mudar o nome para novo caminho.|
|[[SITE]]|Parâmetros específicos de locais fornecidas pelo servidor.|
|[[SMNT]]|Montar a estrutura do arquivo especificado.|
|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/transferência de arquivos- FTP e TFTP/Untitled Database/STAT]]|Retorna informação sobre o processo ou o diretório atual.|
|[[STOR]]|Store (cópia) do arquivo para o servidor.|
|[[STOU]]|Arquivo de armazenamento de nome do servidor.|
|[[STRU]]|Estrutura de dados (F = arquivo, R = registro, P = página).|
|[[SYST]]|Voltar o sistema operacional utilizado pelo servidor.|
|[[TYPE]]|Tipo de dados (A = ASCII, E = EBCDIC, I = binário).|
|[[USUÁRIO]]|Nome de usuário para o sistema de log-in.|

  
  

**Mensagens**

Mensagens FTP são respostas aos comandos FTP e consistem de um código de resposta seguido de um texto explicativo. Mensagens FTP padrão são as seguintes:

|Código de Resposta|Texto explicativo|
|---|---|
|110|[[Restart marcador na marca aaaa = mmmm (novos ponteiros de arquivo)]]|
|120|[[Serviço pronto em nnn minutos]]|
|125|[[Conexão de dados aberto, transferência de partida]]|
|150|[[Conexão aberta]]|
|200|[[Tudo OK]]|
|202|[[Não comandar implementado 2]]|
|211|[[(Resposta de status do sistema)]]|
|212|[[(Resposta de status Directory)]]|
|213|[[(Status do arquivo resposta)]]|
|214|[[(Help mensagem de resposta)]]|
|215|[[(Tipo de resposta do sistema)]]|
|220|[[Serviço pronto]]|
|221|[[Faça logoff da rede]]|
|225|[[Conexão de dados aberto]]|
|226|[[Fechar conexão de dados]]|
|227|[[Entre em modo passivo (endereço IP, porta ID)]]|
|230|[[Log em rede]]|
|250|[[Ação de arquivo concluída]]|
|257|[[Nome do caminho criado]]|
|331|[[Senha requerida]]|
|332|[[Nome da conta necessária]]|
|350|[[Ação de arquivo pendente]]|
|421|[[Serviço desligando]]|
|425|[[Não é possível abrir conexão de dados]]|
|426|[[Conexão fechada]]|
|450|[[Arquivo não disponível 2]]|
|451|[[Erro local encontrado]]|
|452|[[Espaço em disco insuficiente]]|
|500|[[Comando inválido]]|
|501|[[Mau parâmetro]]|
|502|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/transferência de arquivos- FTP e TFTP/Untitled Database/Não comandar implementado]]|
|503|[[Bad seqüência de comandos]]|
|504|[[Parâmetro inválido para o comando]]|
|530|[[Não está logado na rede]]|
|532|[[Precisa de conta para armazenar arquivos]]|
|550|[[Arquivo não disponível]]|
|551|[[Tipo de página desconhecido]]|
|552|[[organizar/REFINAR/Redes de Computadores/aplicações em redes de computadores/transferência de arquivos- FTP e TFTP/Untitled Database/Alocação de armazenamento excedida]]|
|553|[[O nome do arquivo não é permitido]]|

  
  

**TFTP**

O protocolo TFTP, _**Trivial File Transfer Protocol**_ , trata a transferência de arquivo de forma mais simples pois utiliza o UDP. TFTP suporta arquivos de escrita e leitura; não suporta serviço de diretório de autorização do usuário.

**Comandos:** Os seguintes são comandos TFTP:

|Comando|Descrição|
|---|---|
|[[Leia Pedido]]|Pedir para ler um arquivo.|
|[[Escrever Pedido]]|Solicitação para gravar em um arquivo.|
|[[Dados de Arquivo]]|Transferência de dados do arquivo.|
|[[Dados de reconhecimento Reconheça]]|Confirmação de dados do arquivo.|
|[[Erro]]|Indicação de erro.|

  
  

**Parâmetros** TFTP Ler e Escrever comandos, pedir usar os seguintes parâmetros:

|Parâmetro|Descrição|
|---|---|
|[[Nome do arquivo]]|O nome do arquivo, expresso entre aspas, onde o protocolo é para executar a operação de leitura ou gravação.|
|[[Modo]]|Datamode. O formato do arquivo de dados que o protocolo é a transferência. Os seguintes formatos são possíveis: formato caráter netascii padrão ASCII. Octeto dados binários de oito bits. Correio formato de caracteres ASCII padrão com nome de usuário no lugar do nome do arquivo.|

  
  

Dados TFTP e dados de reconhecer comandos usam os seguintes parâmetros:

|Comando|Descrição|
|---|---|
|[[Bloco]]|Número do bloco ou o número de seqüência do quadro atual de dados de arquivo.|
|[[Dados]]|Primeira parte dos dados de arquivos exibidos para os quadros de dados TFTP.|
|[[Erros TFTP]]|Quadros de erro TFTP conter um código de erro em parênteses, seguido pela mensagem de erro, como se segue:(0000)Erro desconhecido.(0001)Arquivo não encontrado.(0002)Violação de acesso.(0003)Sem espaço em disco.(0004)TFTP operação ilegal.(0005)Desconhecido ID de Transferência.(0006)Filename já existe.(0007)Usuário desconhecido.|
|[[(0000)]]|Erro desconhecido.|
|[[(0001)]]|Arquivo não encontrado.|
|[[(0002)]]|Violação de acesso.|
|[[(0003)]]|Sem espaço em disco.|
|[[(0004)]]|TFTP operação ilegal.|
|[[(0005)]]|Desconhecido ID de Transferência.|
|[[(0006)]]|Filename já existe.|
|[[(0007)]]|Usuário desconhecido.|