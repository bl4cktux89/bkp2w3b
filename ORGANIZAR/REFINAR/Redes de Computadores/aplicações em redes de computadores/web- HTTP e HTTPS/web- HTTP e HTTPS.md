HTTP é sigla de _**HyperText Transfer Protocol**_ que em português significa "Protocolo de Transferência de Hipertexto". É um protocolo de comunicação entre sistemas de informação que permite a transferência de dados entre redes de computadores, principalmente na _**World Wide Web**_ (Internet).

É um protocolo de nível de aplicativo com a leveza e velocidade necessária para distribuição colaborativa, sistemas de informação hipermídia. As mensagens são transmitidas em um formato semelhante ao usado pelo Internet Mail e os _**Multipurpose Internet Mail Extensions**_ (MIME). (Compatível com a IETF RFC1945 maio de 1996.)

**Características gerais:**

- Protocolo da camada de aplicação;
- Funciona baseado na troca de requisição resposta;
- Cabeçalho das mensagens é texto puro (não binário);
- Não orientado a conexões;
- Não guarda estado entre conexões distintas, isto é, cada conexão é nova para o servidor.

O HTTP é o protocolo utilizado para transferência de páginas HTML do computador para a Internet. Por isso, os endereços dos websites (URL) utilizam no início a expressão "http://", definindo o protocolo usado. Esta informação é necessária para estabelecer a comunicação entre a URL e o servidor Web que armazena os dados, enviando, desta forma, a página HTML solicitada pelo usuário.

Para que a transferência de dados na Internet seja realizada, o protocolo HTTP necessita estar agregado a outros dois protocolos de rede: TCP (_**Transmission Control Protocol**_) e IP (_**Internet Protocol**_). Esses dois últimos protocolos formam a arquitetura TCP/IP, necessário para a conexão entre computadores clientes-servidores.

A figura 1 apresenta a arquitetura para pedidos na web por meio de um navegador também conhecido como browser.

![[img1 2.png|img1 2.png]]

**Passos que ocorrem quando se acessa um link:**

1. O browser identifica a URL;

2. O browser solicita ao DNS o endereço IP do servidor;

3. Resposta DNS;

4. O browser faz uma conexão TCP;

5. Envia uma solicitação HTTP para aquela página;

6. O servidor envia a página como resposta HTTP;

7. O browser retorna outras URLs quando precisa;

8. O browser apresenta a página;

9. As conexões TCP são encerradas.

![[img2 2.png|img2 2.png]]

Uma estação cliente solicita e conexão a um servidor web, via protocol HTTP que pode ser por conexões persistentes HTTP 1.1 de forma sequencial, e em pipeline conforme figura 3. As conexões no HTTP podem ser persistentes e não persistentes:

- **Conexões não persistentes** — cada par de requisição/resposta deve ser enviado por uma conexão TCP distinta.
- **Conexões persistentes** — todas as requisições e suas respostas devem ser enviadas por uma mesma conexão TCP.

(a) múltiplas conexões e solicitações sequenciais.

(b) Conexão persistente e solicitações sequenciais.

(c) Conexão persistente com solicitações em pipeline.

![[Untitled 48.png|Untitled 48.png]]

O Protocolo de Transferência de Hipertexto na busca de um objeto na web pode enviar diversos métodos, conforme tabela 1, podendo ler um objeto ou diversos objetos em um servidor web, que são os métodos utilizados na criação de uma solicitação HTTP.

![[Untitled 1 32.png|Untitled 1 32.png]]

As respostas, as solicitações HTTP, são padrões do mundo da internet com códigos da linha 100,200,300,400,500,600 conforme tabela 2.

![[Untitled 2 28.png|Untitled 2 28.png]]

**O protocol HTTP**

O format do protocol HTTP é apresentado na figura 4

A primeira linha é chamada de linha de requisição e as demais, linhas de cabeçalho. No caso da linha de requisição existem 3 campos, o de método, o do URL e da versão do HTTP. O campo método pode assumir os da tabela 1. A grande maioria das requisições utiliza o método GET, utilizado nos navegadores WEB.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/9/256997/14253.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/9/256997/14253.png)

Figura 4 - Formato do protocolo HTTP

Fonte: Kurose, James F. Redes de computadores, 2013

Segue um exemplo de uma mensagem de requisição:

**Mensagem de requisição HTTP**

GET /somedir/page.html HTTP/1.1

Host: www.someschool.edu

Connection: close

User-agent: Mozilla/5.0

Accept-language: fr

(dados dados dados dados dados ...)

![[Untitled 3 19.png|Untitled 3 19.png]]

O método para ser executada no recurso. Pedido-URI O identificador de recursos uniforme, o recurso sobre o qual se aplica o pedido, ou seja, o recurso de rede. HTTP versão A versão de HTTP a ser utilizado. Versão HTTP A versão HTTP que está sendo usado. Status-código Um código de resultado inteiro de 3 dígitos da tentativa de entender e satisfazer o pedido. Motivo Frase Uma descrição textual do código de status.

Formato geral de uma mensagem de resposta HTTP. Conforme figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/0/257009/14255.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/0/257009/14255.png)

Figura 5 - Formato da resposta a solicitação HTTP

Fonte: Kurose, James F. Redes de computadores 2013

**Mensagem de resposta HTTP**

{C}•       Apresentamos a seguir uma mensagem de resposta HTTP típica:

HTTP/1.1 200 OK

Connection: close

Date: Tue, 09 Aug 2011 15:44:04 GMT

Server: Apache/2.2.3 (CentOS)

Last-Modified: Tue, 09 Aug 2015 15:11:03 GMT

Content-Length: 6821

Content-Type: text/html

(dados dados dados dados dados ...)

Os dados são textos html gerados por uma linguagem de hiper texto.

A tabela 3 apresenta outros tipos de solicitação e resposta HTTP

|Cabeçalho|Tipo|Conteúdo|
|---|---|---|
|[[User-Agent]]|Solitcitação|Informações sobre o navegador e sua plataforma|
|[[Accept]]|Solitcitação|O tipo de páginas que o cliente pode manipular|
|[[Accept-Charset]]|Solitcitação|Os conjuntos de caracteres aceitáveis para o cliente|
|[[Accept-Enconding]]|Solitcitação|As codificações de páginas que o cliente pode lidar|
|[[Accept-Language]]|Solitcitação|Os idiomas com os quais o cliente pode lidar|
|[[If-Modified-Since]]|Solitcitação|Data e hora para verificar a atualização|
|[[If-None-Match]]|Solitcitação|Tags enviadas anteriormente para verificar atualização|
|[[Host]]|Solitcitação|O nome DNS do servidor|
|[[Authorization]]|Solitcitação|Uma lista de credenciais do cliente|
|[[Referer]]|Solitcitação|O URL anterior do qual a solicitação veio|
|[[Cookie]]|Solitcitação|Cookie previamente definido enviado de volta ao servidor|
|[[Set-Cookie]]|Resposta|Cookie para o cliente armazenar|
|[[Server]]|Resposta|Informações sobre o servidor|
|[[Content-Encoding]]|Resposta|Como o conteúdo está codificado (por exemplo, gzip)|
|[[Content-Language]]|Resposta|O idioma usado na página|
|[[Content-Length]]|Resposta|O tamanhho da página em bytes|
|[[Content-Type]]|Resposta|O tipo MME da página|
|[[Content-Range]]|Resposta|Identifica uma parte do conteúdo da página|
|[[Last-Modified]]|Resposta|Data e hora da última modificação na página|
|[[Expires]]|Resposta|Data e hora de quando a página deixa de ser válida|
|[[Location]]|Resposta|Informa para onde o cliente deve enviar sua solicitação|
|[[Accept-Ranges]]|Resposta|Indica que o servidor aceitará solicitações de intervalos de bytes|
|[[Date]]|Ambos|Data e hora em qua a mensagem foi enviada|
|[[Rage]]|Ambos|Identifica uma parte da página|
|[[Cache-Control]]|Ambos|Diretivas para o modo de tratar caches|
|[[ETag]]|Ambos|Tag para o conteúdo da página|
|[[Upgrade]]|Ambos|O protocolo para o qual o tarnsmissor deseja passar|

  
  

Comparando este métodos, figura 6, em todos os casos é necessário a solicitação (1) get HTTP, a verificação se existe o objeto (2) no cache local ( estação do cliente) com a verificação da validade do objeto. A solicitação GET (3)  solicita ao servidor WEB que compara com a data do objeto em cache. Dependendo da validade do objeto o servidor WEB pode retornar uma não modificação (4a) ou a resposta com o objeto alterado (4b).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/1/258141/14259.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/1/258141/14259.jpg)

Figura 6 - Cache HTTP

Fonte: TANENBAUM, Andrew S. Redes de computadores . 2011

Talvez o que mais atraia a maioria dos usuários da Web é que ela funciona por demanda e o protocolo  HTTP é executado em dois programas:

·         um cliente e

·         outro servidor.

Uma página Web é constituída de objetos que é apenas um arquivo que se pode acessar com um único URL.

A maioria das páginas Web é constituída de um arquivo-base HTML e diversos objetos referenciados. O HTTP usa o TCP como seu protocolo de transporte subjacente e é denominado como um protocolo sem estado.

**O HTTP / 2**

HTTP / 2 é semelhante ao HTTP1 e 1.1, mas acrescenta alguns novos características como forma de aumentar a velocidade. Foram feitas alterações na forma que os dados são alterados e transportados entre o cliente e o servidor. HTTP / 2 permite que o servidor envie dados antes que uma mensagem de resposta seja recebida. Novas melhorias incluem multiplexação de pedidos e respostas, a compressão de cabeçalho, e priorização de solicitações. Finalmente, HTTP / 2 também permite um processamento mais eficiente de mensagens através do uso de formatação de mensagem binária.

HTTP / 2 é composta por frames, quando cada quadro tem sua própria finalidade.

Multiplexação é conseguido fazendo com que cada HTTP Request / Response seja associado com seu próprio fluxo. O controle de fluxo e priorização para garantir que seja possível usar eficientemente fluxos multiplexados. HTTP / 2 acrescenta um novo modo de interação por meio do qual um servidor pode enviar (empurrar) as respostas a um cliente. O Push (empurrar) do servidor permite que um servidor envie dados especulativamente a um cliente que o servidor antecipa que o cliente terá, trocando algumas informações de uso de rede contra um ganho potencial de latência.

Porque os campos de cabeçalho HTTP usados â¿¿â¿¿em uma conexão pode conter grandes quantidades de dados redundantes, os quadros que os contêm são compactados. O formato do cabeçalho do quadro. O comprimento da carga útil  do quadro  é expresso como um número inteiro de 24 bits. Os 9 octetos de cabeçalho de quadro não estão incluídos no presente valor. O tipo de estrutura tem 8 bits. Também possui um campo flag, de 8 bits,  reservados para flags booleanas específicos para cada  tipo de quadro. O quadro também permite um identificador de fluxo.

**HTTP seguro**

(S-HTTP) prevê mecanismos de comunicação segura entre um par cliente-servidor HTTP, a fim de permitir que as transações comerciais  sejam feitas de forma segura. S-HTTP fornece um protocolo flexível que suporta múltiplos modos de operação ortogonais, os principais mecanismos de gestão, modelos de confiança, algoritmos criptográficos e formatos de encapsulamento através da negociação entre as partes e opções para cada transação. Sintaticamente, mensagens HTTP seguras são as mesmas como HTTP, que consiste de uma linha de pedido de estado ou seguido por cabeçalhos e um corpo. No entanto, a gama de cabeçalhos é diferente e os organismos são tipicamente criptograficamente reforçada.

O HTTPS (_**Hyper Text Transfer Protocol Secure**_), insere uma camada de proteção na transmissão de dados entre seu computador e o servidor. Em sites com endereço HTTPS, a comunicação é criptografada, aumentando significativamente a segurança dos dados. É como se cliente e servidor conversassem uma língua que só as duas entendessem, dificultando a interceptação das informações.  A porta TCP usada por norma para o protocolo HTTPS é a 443.

O protocolo HTTPS é utilizado, em regra, quando se deseja evitar que a informação transmitida entre o cliente e o servidor seja visualizada por terceiros, como por exemplo no caso de compras online. A existência na barra de endereços de um cadeado (que pode ficar do lado esquerdo ou direito, dependendo do navegador utilizado) demonstra a certificação de página segura SSL. A existência desse certificado indica o uso do protocolo HTTPS e que a comunicação entre o browser e o servidor se dará de forma segura. Para verificar a identidade do servidor é necessário abrir esse certificado com um duplo clique no cadeado para exibição do certificado.

Para saber se está navegando em um site com criptografia, basta verificar a barra de endereços, na qual será possível identificar as letras HTTPS e, geralmente, um símbolo de cadeado que denota segurança. Além disso, o usuário deverá ver uma bandeira com o nome do site, já que a conexão segura também identifica páginas na Internet por meio de seu certificado.

Para preparar uma página web de modo a aceitar conexões HTTPS, o administrador deve criar um certificado de chave pública para o servidor web. Esse certificado deve ser assinado por uma autoridade certificadora confiável para que o navegador aceite a conexão e não exiba avisos. A autoridade certifica que o proprietário do certificado é o operador do servidor web que o apresenta. Os navegadores web são geralmente distribuídos com uma lista de autoridades de certificação de assinatura para que elas possam verificar certificados assinados por eles.