### Introdução

Quantas vezes você já digitou no seu navegador o acrônimo WWW, mas o que isso significa? O World Wide Web (WWW – rede mundial de computadores). O WWW é um repositório de informações espalhados por diversos lugares ao redor do mundo, representando uma combinação única de flexibilidade, facilidade de transporte recursos para facilitar a vida do usuário diferente de todos os outros serviços oferecidos na Internet. O projeto do WWW fui iniciado no final da década de 1980 pelo Cern (European Laboratory for Particle Physics, Laboratório europeu de física da partícula) com o objetivo de criar um sistema para gerenciar os recursos distribuídos e grande quantidade de dados gerados por pesquisadores que estudavam as partículas elementares. Inicialmente, o WWW era disponível apenas para pesquisadores e universidade, mas a sua robustez e facilidade foi tão grande que acabou chegando ao usuário final para fins de entretenimento, propaganda etc.

### Arquitetura WWW

A arquitetura WWW é um serviço cliente/servidor distribuído, no qual um cliente usando um navegador (browser), pode acessar diferentes serviços hospedados em diferentes servidores e, consequentemente, em diferentes localidades, denominadas sites. Alguns elementos da arquitetura WWW são descritos abaixo (Forouzan, B. A, 2010):

- **Cliente (browser):** atualmente, existem uma série de browsers, tais como, Internet Explorer, Edge, Firefox, Chrome, Eudora etc. Todos eles com a capacidade de exibir um documento Web e com arquitetura semelhante composto basicamente por três partes: um **controlador, programas cliente e interpretadores**. O **controlador** tem a função capturar as entradas do teclado e do mouse usados para acessar o documento desejado pelo usuário. Após o documento ter sido acessado, o controlador utiliza um interpretador, que tem a função de exibir o documento na tela. O interpretador de comandos pode ser HTML, Java ou JavaScript dentre outros, enquanto que o **programa cliente** e aplicação que faz interface com o usuário, que pode ser FTP, SMTP ou HTTP. Na figura a seguir é mostrada a arquitetura básica de um browser.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/3/1779379/40023.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/3/1779379/40023.jpg)

Fonte: Forouzan, B. A, 2010

- **Servidor:** é no servidor web que a página é hospedada. Dentre os servidores web podemos citar, o Apache (aplicação aberta para Linux) e o IIS (Internet Information Service, Serviço de informação para a internet) da Microsoft. Normalmente, o arquivo do site é alocado na memória cache para acesso mais rápido. Também é possível utilizar a técnica de multitarefas baseadas em threads, multiprocessadores e até mesmo em clusters.
- **Uniform Resource Lacator (URL):** O protocolo HTTP utiliza o conceito de localizadores. A URL (Localizadora de recursos uniformes) é um padrão para especificações de qualquer tipo de informação na Internet. A constituição da URL é formada por quatro partes, conforme mostrada e detalhada abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/3/1779398/40025.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/3/1779398/40025.jpg)

Fonte: Forouzan, B. A, 2010

**Onde:**

- **Protocolo:** é o programa servidor usado para acessar o comento; entre eles temos: o HTTP, FTP ou SMTP. Na sequência do presente tópico estudaremos em detalhes os protocolos HTTP e HTTPs.
- **Host:** é o servidor onde as informações estão hospedas. Normalmente, as páginas web recebem nomes alternativos (Alias) começando com www.
- **Porta:** número de porta do servidor. Quando incluída ela estará entre o campo de host e Path (caminho).
- **Caminho:** informa a localização do arquivo dentro do host. O caminho do arquivo pode ser composto por barras, indicando para separas diretórios de subdiretórios (Padrão dos sistemas operacionais UNIX).

### HTTP

O protocolo HTTP pertence a classe de protocolos de nível de aplicação do modelo TCP/IP, utilizando protocolo TCP no nível da camada de transporte e suas requisições são feitas por meio da porta 80. Ele é utilizado, como visto anteriormente, na WWW para distribuição e recuperação de informação, principalmente, de documentos hipertextos. Portanto, a troca de informações entre o navegador e o servidor na web é feita por meio desse protocolo (Kurose, J. F. 2014).

### Funcionamento do HTTP

O programa do cliente, geralmente o browser, estabelece uma conexão e faz uma requisição ao programa do servidor web. As regras do protocolo HTTP definem a sintaxe desse pedido e o servidor retorna uma resposta. Se estiver tudo correto, essa resposta conterá a informação desejada pelo cliente em um formato baseado nas regras estabelecidas pelo protocolo. Uma solicitação HTTP é composta das seguintes partes (Mendes, D. R. 2010):

- Comando: Representa a ação a ser tomada
- URI (Universal Resource Identifier, Identificação de recursos Universal): Representa a informação requisitada;
- Versão do protocolo

### Solicitação e resposta HTTP

Os formatos das mensagens de solicitação de respostas são similares, conforme apresentado na figura abaixo. Uma mensagem de solicitação é formada por uma linha de solicitação, um cabeçalho e, em alguns casos, um corpo. A mensagem de resposta é formada pela linha de status, cabeçalho e, algumas vezes, o corpo.

Na tabela que segue são mostrados os comandos utilizados pelo HTTP na interação entre o cliente e o servidor. É importante salientar que toda essa comunicação é feita de maneira transparente para o usuário, ou seja, o usuário não tem contato direto com a interação.

![[Untitled 41.png|Untitled 41.png]]

### Resposta HTTP

As requisições feitas ao servidor HTTP são respondidas ao navegador que apresenta o resultado ao usuário. Uma resposta HTTP é formada, como comentado anteriormente, por três elementos: uma linha de status, indicando sucesso no pedido; uma descrição. Os códigos de status têm funcionalidade semelhante aos empregados nos protocolos FTP e SMTP. Os códigos mais comuns são mostrados na tabela abaixo.

|Title|Código|Mensagem|Descrição|
|---|---|---|---|
|[[Untitled 12]]|200|OK|O pedido foi realizado corretamente|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 5]]|201|CREATED|Segue um comando POST, indica o sucesso, o corpo do resto do documento deve indicar o URL onde o documento recentemente criado deveria encontrar-se|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 8]]|202|ACCEPTED|O pedido foi aceito, mas o procedimento seguinte não foi realizado|
|[[Untitled 24]]|203|PARTIAL INFORMATION|Quando este código é recebido em resposta a um comando GET, isto indica que a resposta não está completa|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 4]]|204|NO RESPONSE|O servidor recebeu o pedido mas não há informação a ser retornada|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 6]]|205|RESET CONTENT|O servidor indica ao navegador para excluir o conteúdo dos campos de um formulário|
|[[Untitled 19]]|206|PARTIAL CONTENT|Trata-se de uma resposta a um pedido que comporta o cabeçalho _**range**_. O servidor deve indicar o cabeçalho _**content-range**_|
|[[Untitled 16]]|**30x**|**Redirecionamento**|**Estes códigos indicam que o recurso não está mais no lugar indicado**|
|[[Untitled 15]]|301|MOVED|Os dados pedidos foram transferidos para um novo endereço|
|[[Untitled 20]]|302|FOUND|Os dados pedidos são de um novo URL, mas talvez tenham sido deslocados desde então|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 3]]|303|METHOD|Isto implica que o cliente deve tentar um novo endereço, tentando um outro método além do GET|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 10]]|304|NOT MODIFIED|Se o cliente efetuou um comando GET condicional (perguntando se o documento foi alterado desde a última vez) e se o documento não tiver sido alterado, ele devolve este código|
|[[Untitled 13]]|**40x**|**Erro devido ao cliente**|**Estes códigos indicam que o pedido está incorreto**|
|[[Untitled 23]]|400|BAD REQUEST|A sintaxe do pedido está mal formulada ou impossível de validar|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled]]|401|UNAUTHORIZED|O parâmetro da mensagem dá as especificações das formas de autorização aceitáveis. O cliente deve reformular o seu pedido com os dados de autorização corretos|
|[[Untitled 22]]|402|PAYMENT REQUIRED|O cliente deve reformular o seu pedido com os dados de pagamento corretos|
|[[Untitled 18]]|403|FORBIDDEN|O acesso ao recurso foi recusado|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 9]]|404|NOT FOUND|Muito comum! O servidor não encontrou nada no endereço indicado. Partiram sem deixar endereço|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 11]]|**50x**|**Erro devido ao servidor**|**Estes códigos indicam que houve um erro interno no servidor**|
|[[Untitled 21]]|500|INTERNAL SERVER ERROR|O servidor encontrou uma condição inesperada que o impediu de satisfazer o pedido|
|[[Untitled 14]]|501|NOT IMPLEMENTED|O servidor não suporta o serviço pedido|
|[[Untitled 17]]|502|BAD GATEWAY|O servidor recebeu uma resposta inválida por parte do servidor que tentava acessar agindo como uma passarela ou um proxy|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 2]]|503|SERVICE UNAVAILABLE|O servidor não pode responder no momento, pois o tráfego está muito denso (todas as linhas do seu correspondente estão ocupadas, tente novamente)|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura TCP-IP/protocolo HTTP e HTTPS/Untitled Database/Untitled 7]]|504|GATEWAY TIMEOUT|A resposta do servidor demorou muito em relação ao que a gateway foi preparada para recebê-la (o tempo que lhe estava destinado esgotou-se)|

  
  

**Exemplo – Solicitação e resposta HTTP**

A figura abaixo o acesso a um documento. Para tanto, é utilizado o comando GET para obter uma imagem no caminho /usr/bin/imagem1. A linha de solicitação exibi o comando GET, a URL e a versão HTTP (1.1). O cabeçalho apresenta duas linhas de informação indicando que o cliente pode aceitar o formato da imagem (GIF ou JPEG). Como pode ser observado, a mensagem de solicitação não possui um corpo. Por sua vez, a mensagem de resposta contem a linha de status e quatro linhas de cabeçalho definindo: a data, o servidor, a versão do MIME e o tamanho do documento. O corpo do documento viria depois do cabeçalho.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/1/1/1781192/40027.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/1/1/1781192/40027.jpg)

Fonte: Forouzan, B. A, 2010

### HTTPS

O HTTPS (HTTP seguro) é a combinação protocolo HTTP, discutido anteriormente, com o protocolo SSL (Secure Socket Layer) Camada de segurança de socket) ou TLS (Transport Layer Secutity, Camada de segurança de segurança) para oferecer segurança na camada de transporte, conforme mostrado na figura abaixo. O SSL foi desenvolvido pelo Netscape em 1994 e, posteriormente, o IETF desenvolveu o TLS, baseada no anterior. Abaixo discutiremos apenas o SSL, mas tenha em mente que os dois são muito similares com pequenas diferenças.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/3/292375/17548.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/3/292375/17548.png)

Conexões SSL agem como soquetes conectados por TCP e suas camadas

Um protocolo de transporte seguro para as aplicações tem por objetivo fornecer serviços de segurança ponto a ponto para as aplicações que utilizam transporte na camada de transporte como, por exemplo, o TCP. Dessa forma, fornece serviços de segurança para cliente que desejam realizar compras on-line e que necessitam (Forouzan, B. A, 2010):

- Que o servidor pertença ao verdadeiro fornecedor e não ao impostor. O cliente poderia fornecer, por exemplo, o número do cartão de crédito. Da mesma forma, o servidor precisa reconhecer que o cliente é legitimo.
- Ter certeza que o conteúdo da mensagem seja alterado durante o transporte, garantindo a integridade da mensagem.
- Ter certeza que a mensagem não seja interceptada por um impostor e acesse informações confidenciais.

### Serviços SSL

O SSL foi desenvolvido para receber dados de qualquer protocolo da camada de aplicação, mas, normalmente é empregado pelo HTTP. O SSL recebe os dados da camada de aplicação e realiza os seguintes serviços (Forouzan, B. A, 2010):

- **Fragmentação:** O SSL divide os dados em blocos de 2 ou menos.
    
    14
    
- **Compressão (opcional):** Cada um dos fragmentos de dados é comprimido por meio de métodos negociados entre o cliente e o servidor
- **Integridade de Mensagens:** a integridade dos dados é garantida por uma função resumo, chamada função hash. O SSL usa a função hash com chaves para um MAC. O MAC (Message authentication code, código de autenticação de mensagem). Os dados são enviados junto com o MAC e a função hash. No destinatário, a mensagem é separada do MAC e, na sequência, a função hash é executada e gerado um novo MAC. Caso o MAC o gerado seja igual ao AC enviado, a mensagem é considerada integra, caso contrário, ela foi modificada.
- **Confidencialidade:** para garantir a confidencialidade a mensagem original e MAC são criptografados utilizando uma chave simétrica. Essa chave é conhecida tanto pelo cliente quanto pelo servidor.
- **Framing:** É acrescentado um cabeçalho ao payload criptografado. Na sequência, o payload é passado a um protocolo de transporte confiável, no caso do HTTP, utiliza-se o TCP.

### Processo SSL

O processo de estabelecimento de sessão segura via SSL consiste na realização de quatro tarefas ou quatro protocolos, conforme figura abaixo, sendo (Forouzan, B. A, 2010):

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/1/1/1781197/40028.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/1/1/1781197/40028.jpg)

Fonte: Forouzan, B. A, 2010

- **Recordo Protocol:** é o transportador. Ele transporta as mensagens dos outros protocolos, assim como os dados da camada de aplicação.
- **Handshake Protocolo:** fornece os parâmetros do record protocol, como conjuntos de cifras e fornece chaves e parâmetros de segurança, além de autenticar o servidor para o cliente e vice-e-versa (se necessário). Esse processo é realizado em quatro fases, conforme mostrado na figura baixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/1/2/1781212/40029.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/1/2/1781212/40029.jpg)

Fonte: Forouzan, B. A, 2010

- **Alert Protocol:** Informa a ocorrência de erros e anomalias. Informa o problema e o nível (de aviso ou fatal).
- **ChangeCipherSpec Protocol:** durante a fase de handshake são informados os parâmetros de segurança. Mas eles não podem ser usados a qualquer momento, somente quando tenham enviados e recebidos uma mensagem especial, conhecida como como ChangeCipherSpec. A figura abaixo mostra todas essas etapas de uma conexão via SSL.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/8/1779847/40030.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/8/1779847/40030.jpg)