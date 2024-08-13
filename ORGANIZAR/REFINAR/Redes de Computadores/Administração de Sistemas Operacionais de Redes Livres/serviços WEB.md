### Introdução

O termo Serviços WEB vem mudando nos últimos 5 anos. A medida que se migra para nuvem (_**cloud computing**_), SaaS (_**Software as a Service**_), IaaS (_**Infrastructure as a Service**_), etc., o termo ganha uma dimensão ilimitada e perde-se um pouco a noção do que pode ser considerado um Servidor WEB que é o foco deste tópico. Os serviços considerados **?**_**as a service**_**?** estão muito além do escopo deste tópico pois envolvem muito mais uma colocação comercial estratégica do que algo que possa ser considerado um novo conceito, **sob o ponto de vista de tecnologia de redes**. Falar -  _**O que há mais de moderno atualmente em TI (tecnologia da informação) não envolve novos conceitos em redes, parece mais um sacrilégio**_, mas deixe eu ver se consigo me explicar sem perder muito do seu tempo.

O conceito/tecnologia para se ter computadores virtuais, ou seja, executados no nível software e simulando todas as partes do computador (**virtualização**), somado ao conceito/tecnologia para automaticamente unir as forças de mais que um computador para atender uma aplicação (**clusterização**) já existia há mais de 30 anos. Mais tarde, sem mudar nada nesta tecnologia já se falava em ?**alugar**? softwares que atendiam remotamente usando estas duas tecnologias. Bem, isto não vendeu muito até que resolveram somar estas duas tecnologias e dar um nome muito mais comercial e atraente: ?_**Cloud Computing**_**?**.

Assim a indústria que estava desesperada por vender softwares sob demanda e alugados cunhou os termos primeiro SaaS, mais tarde PaaS, IaaS, etc. e pegou carona no _**Cloud Computing**_. Podíamos discutir isto por dias, mas a ?coisa? é mais ou menos isto aí, guardando proporções e respeitando muito trabalho sério e empresas idôneas, mas, para me resguardar dos neófitos da informática dos nomes bonitos, quero deixar claro que esta explicação é extremamente grosseira e não reflete os detalhes, vantagens e desvantagens, ou seja, não vamos tomar partido! Como falei, disto tudo que estamos explicando, para este estudo, vamos considerar o **serviço WEB aquele fornecido pelos WEB** _**Servers**_ **e** _**Application Servers**_**, isto é, servidores que hospedam, controlam e publicam sites e aplicações web as quais são acessadas via browsers.**

### Servidores WEB e Servidores de Aplicativos/Aplicações

Falar **WEB**, resumidamente, significa que o ambiente de trabalho é a internet. Para um leigo ambos estes servidores parecem a mesma coisa, mas, na verdade, um WEB Servers é o responsável por publicar o que está guardado em páginas **html (**_**hypertext markup language**_**)**. Enquanto um _**Application Server**_ é um servidor onde um programa comercial cujo código é especializado em cumprir as funções de negócio do sistema e, por uma questão de acesso multi localizado e multi plataforma, exibe as telas de entrada de dados e saída de dados no formato que os **browsers** entendem, podendo, portanto, ser acessado por uma URL (link) [1].

Na maioria das vezes, esses termos Servidor Web (**WEB Server**) e Servidor de Aplicativos (**App Server**) são usados de forma intercambiável.

Aqui estão algumas das principais diferenças nos recursos do Servidor da Web e do Servidor de Aplicativos:

- O Servidor Web foi projetado para servir conteúdo HTTP. O App Server também pode servir conteúdo HTTP, mas não está limitado a apenas HTTP. Pode ser fornecido outro suporte de protocolo, como RMI / RPC
- Web Server é projetado principalmente para servir conteúdo estático, embora a maioria dos Servidores Web tenha plugins para suportar linguagens de script como Perl, PHP, ASP, JSP, etc., através das quais esses servidores podem gerar conteúdo HTTP dinâmico [1].
- A maioria dos servidores de aplicativos tem o Web Server como parte integrante deles, o que significa que o App Server pode fazer o que o servidor Web é capaz de fazer. Além disso, o App Server possui componentes e recursos para oferecer suporte a serviços em nível de aplicativo, como pool de conexões, pool de objetos, suporte a transações, serviços de mensagens, etc [1].
- Como servidores web são bem adequados para conteúdo estático e servidores de aplicativos para conteúdo dinâmico, a maioria dos ambientes de produção tem servidor web agindo como proxy reverso para o servidor de aplicativos. Isso significa que ao atender a uma solicitação de página, o conteúdo estático (como imagens / HTML estático) é servido pelo servidor web que interpreta a solicitação. Usando algum tipo de técnica de filtragem (principalmente extensão do recurso solicitado) o servidor web identifica o pedido de conteúdo dinâmico e envia de forma transparente ao servidor de aplicativos

Exemplo de tal configuração é o Apache Tomcat HTTP Server e o Oracle (anteriormente BEA) WebLogic Server. O Servidor HTTP do Apache Tomcat é o Servidor Web e o Oracle WebLogic é o Servidor de Aplicativos.Em alguns casos, os servidores estão bem integrados, como o IIS (Internet Information Server) e o .NET Runtime. O IIS é um servidor web. Quando equipado com o ambiente de tempo de execução .NET, o IIS é capaz de fornecer serviços de aplicativos [2].

### Uma visão de um servidor WEB.

O que um servidor web faz é trabalhar o protocolo HTTP. Quando o servidor Web recebe uma solicitação HTTP, ele responde com uma resposta HTTP, como o envio de uma página HTML, por exemplo. Para processar uma solicitação, um servidor Web pode responder com uma página ou imagem HTML estática, enviar um redirecionamento ou delegar a geração de resposta dinâmica a algum outro programa, como scripts CGI, JSPs (JavaServer Pages), servlets, ASPs (Active Server Pages ), JavaScripts no lado do servidor ou alguma outra tecnologia do lado do servidor. Qualquer que seja o seu propósito, esses programas do lado do servidor geram uma resposta, na maioria das vezes em HTML, para visualização em um navegador da Web.

- Aqui o termo **?lado do servidor?** refere-se a uma forma de trabalhar, ou melhor, uma arquitetura de sistemas que posiciona o peso maior de processamento, incluindo as regras de negócio, no servidor (lado do servidor) e deixa apenas a apresentação dos dados em vídeo e/ou saídas de qualquer natureza, além da entrada de dados, no lado cliente (client side).

Entenda que o modelo de delegação de um servidor Web é bastante simples. Quando um pedido chega ao servidor Web, o servidor Web simplesmente passa a solicitação para o programa mais capaz de lidar com ele. O servidor Web não fornece qualquer funcionalidade além de simplesmente fornecer um ambiente no qual o programa do lado do servidor pode executar e transmitir as respostas geradas. O programa do lado do servidor geralmente fornece para si funções como processamento de transações, conectividade de banco de dados e mensagens. Por tal motivo, muitas vezes o servidor Web não passa de um Proxy para um outro servidor de aplicações/aplicativos.Uma vez que o servidor da Web pode não suportar transações ou o pool de conexões de banco de dados, ele pode empregar várias estratégias para tolerância a falhas e escalabilidade como, por exemplo, o balanceamento de carga, cache e agrupamento, os quais são recursos frequentemente atribuídos erroneamente aos servidores de aplicativos.

### Uma visão de um servidor de aplicações.

O que poderíamos chamar de servidor de aplicativos, olhando para um um conceito com olhar do desenvolvimento de sistemas, é uma estrutura que expõe a lógica de negócios para cliente (o lado do usuário) por meio de vários protocolos, possivelmente incluindo HTTP. Enquanto um servidor Web trata principalmente do envio de HTML para exibição em um navegador da Web, um servidor de aplicativos fornece acesso à lógica de negócios para uso pelos programas de aplicativos do cliente. O programa aplicativo pode usar essa lógica da mesma forma que chamaria um método em um objeto, uma função ou uma sub-rotina. Obviamente não nos interessa neste estudo uma explanação mais demorada sobre o funcionamento em si das aplicações e sim um foco na estrutura que deve existir para fornecer este ambiente.

Esses clientes de servidor de aplicações podem incluir GUIs (interface gráfica de usuário) em execução em um PC, um servidor Web ou até mesmo outros servidores de aplicativos. As informações que viajam para a frente e para trás entre um servidor de aplicativos e seu cliente não é restrita de exibição simples de **html**. Em vez disso, exibe as informações da lógica de programa. Uma vez que a lógica assume a forma de ?chamadas? de dados e métodos e não o HTML estático, o cliente pode empregar a lógica das regras de negócios expostos, da maneira que bem quiser.Na maioria dos casos, o servidor expõe essa lógica de negócios através de um componente de API, como o modelo EJB (Enterprise JavaBean) encontrado em servidores de aplicativos J2EE (Java to Platform, Enterprise Edition). Além disso, o servidor de aplicativos gerencia seus próprios recursos. Esses deveres de manutenção de gateways incluem segurança, processamento de transações, pooling de recursos e mensagens. Como um servidor Web, um servidor de aplicativos também pode usar várias técnicas de escalabilidade e tolerância a falhas.

**Quais os ambientes possíveis?**

Como exemplo, considere uma loja de roupas online que forneça informações sobre preços e disponibilidade em tempo real. Muito provavelmente, o site fornecerá um formulário com o qual você pode escolher um produto. Quando você envia sua consulta, o site executa uma pesquisa e retorna os resultados incorporados em uma página HTML. O site pode implementar essa funcionalidade de várias maneiras. Vou mostrar-lhe um ambiente que não usa um servidor de aplicações e outro que usa.

### Apenas um Servidor Web

Um servidor Web sozinho fornece toda a funcionalidade da loja de roupas on-line. O servidor Web recebe uma solicitação e, em seguida, passa para um programa do lado do servidor (Server-Side) capaz de lidar com a solicitação. O programa do lado do servidor procura as informações de preço de um banco de dados ou um arquivo simples. Uma vez recuperado, o programa do lado do servidor usa as informações para formular a resposta em HTML e, em seguida, o servidor Web envia de volta para o navegador da Web.

Para resumir, um servidor Web simplesmente processa solicitações HTTP respondendo com páginas HTML.

### Um servidor Web + um Servidor de Aplicações

Este ambiente se assemelha primeiro em que o servidor Web ainda delega a geração de resposta para um script. No entanto, agora você pode colocar a lógica de negócios para a pesquisa de preços em um servidor de aplicativos. Com essa mudança, em vez do script saber como procurar os dados e formular uma resposta, o script pode simplesmente chamar o serviço de pesquisa do servidor de aplicativos. O script pode usar o resultado do servidor de aplicações quando então, o script gera sua resposta em HTML.

Nessa situação, o servidor de aplicativos atende a lógica de negócios para pesquisar as informações de preços de um produto. Essa funcionalidade não diz nada sobre exibição ou como o cliente deve usar as informações. Em vez disso, o cliente e o servidor de aplicativos enviam dados de um lado para outro. Quando um cliente chama o serviço de pesquisa do servidor de aplicativos, o serviço simplesmente procura as informações e as devolve ao cliente.

Ao separar a lógica de preços do código (programa) gerador de respostas HTML, a lógica de preços torna-se muito mais reutilizável entre as aplicações. Um segundo cliente, tal como uma caixa registadora, poderia também chamar o mesmo serviço que um vendedor ambulante poderia verificar acessando diretamente da casa do cliente. Em contraste, no primeiro ambiente, o serviço de pesquisa de preços não é reutilizável porque as informações estão incorporadas na página HTML. Resumindo, no segundo modelo, o servidor Web trata as solicitações HTTP respondendo em uma página HTML enquanto o servidor de aplicativos atende à lógica do aplicativo processando solicitações de preços e disponibilidade.

Falando assim, uma pequena consulta de preço de um produto, leva a pensar que não há vantagem em se ter um servidor a mais. Na verdade, no primeiro ambiente, em processamento real e com volumes de transações reais, tanto o trabalho do lado cliente (cujo desenvolvimento dos programas é muito maior e mais suscetível a manutenções constantes), como sob o ponto de vista do gargalo (afunilamento de demanda) do lado servidor a diferença é gigantesca, inviabilizando este modelo.

Recentemente, os serviços da Web em XML perturbaram a linha entre os servidores de aplicativos e os servidores da Web. Ao passar uma carga XML para um servidor Web, o servidor Web, agora, pode processar os dados e responder muito como servidores de aplicativos têm no passado.

Mais importante, sabemos que uma grande quantidade de servidores de aplicativos também contém um servidor Web, o que significa que você pode considerar um servidor Web um subconjunto de um servidor de aplicativos. Embora os servidores de aplicativos contenham funcionalidade de servidor Web, os desenvolvedores raramente implementam servidores de aplicativos nessa capacidade. Em vez disso, quando necessário, eles frequentemente implementam servidores Web autônomos em conjunto com os servidores de aplicativos. Essa separação de funcionalidade auxilia o desempenho.

### Implementando um Servidor WEB - WEB Server

Em se tratando de Linux, pode-se entender que falar Web Server é falar **?Apache?.**

O servidor web Apache está entre os servidores web mais populares do mundo. É bem documentado, e tem sido amplamente utilizado para grande parte da história da web, o que o torna uma opção padrão grande para hospedar um site.

Primeiro eu gostaria de falar no "LAMP". É um grupo de software de código aberto que normalmente é instalado em conjunto para permitir que um servidor hospede sites dinâmicos e aplicativos da web. Este termo é na verdade um acrônimo que representa o sistema operacional Linux, com o servidor web Apache. Os dados do site são armazenados em um banco de dados MySQL, e o conteúdo dinâmico é processado pelo PHP. O LAMP seria uma recomendação para você ter um servidor web e servidor de aplicações ao mesmo tempo.

**Neste estudo, vamos instalar o Apache.**

### Instalando o Apache

A instalação do Apache, de forma simples e eficiente pode ser feita usando o apt, um pacote que gerencia os pacotes do Ubuntu. Um gerenciador de pacotes nos permite instalar a maioria dos softwares livres de qualquer dificuldade buscando-os em um repositório mantido pela Ubuntu. Mas isto você já sabe.

A partir de agora, cada comando feito será executado na minha máquina e sempre estarei mostrando os resultados dos comandos.

Primeiro, iniciando digitando esses comandos:

 **\#Sudo apt-get update**

**\#Sudo apt-get install apache2**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831782/36760.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831782/36760.png)

Fonte:

Como estamos já superusuários comando sudo não será necessário. Essas operações são executadas com privilégios de root.

Depois de inserir o comando apt-get, o sistema informará os pacotes que planeja instalar e a quantidade de espaço em disco que eles terão. Pressione “S” e pressione Enter para continuar e a instalação prosseguirá.

Vamos checar se, até agora, está tudo ok.

**\#apache2ctl configtest**

Veja o que aconteceu!

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831787/36761.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831787/36761.png)

Fonte:

Use um editor de texto (VIM, por exemplo) e abra o arquivo de configuração principal do Apache:

 **\#vim  /etc/apache2/apache2.conf**

Adicione uma diretiva chamada **ServerName**, apontando para o seu nome de domínio principal. Se você não tem um nome de domínio associado ao seu servidor, você pode usar o endereço IP público do servidor. No meu caso eu criei um domínio nesta máquina e esta linha vai ficar assim:

Fonte:

Vejam que o nome deste servidor é **LuckyGavNote**.

Em seguida, verifique se há erros de sintaxe digitando:

**\#apache2ctl configtest**

Como adicionamos a diretiva ServerName global, tudo o que você deve ver é:

**Saída**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831792/36763.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831792/36763.png)

Fonte:

Sintaxe OK

Reinicie o Apache para implementar suas alterações:

 **\#systemctl restart apache2**

Agora você deveria verificar se tudo está de acordo com o planejado entrando com o seu endereço IP público do servidor ou o próprio localhost em seu navegador da Web:

**http://localhost**

Você visualiza a página do Ubuntu 16.04 Apache, colocada lá para testes e informativo. Tem a aparência da figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831795/36764.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831795/36764.png)

Fonte:

A página é maior do que apresentei acima, mas é o suficiente para você perceber que está tudo funcionando. Quando você colocou o endereço da própria máquina, aparece a página HTML que está armazenada no diretório **/var/www/html** no arquivo **index.html**.

Para ficar mais satisfeito, abra este arquivo (**vim /var/www/html/index.html**) e modifique com alguma informação sua.

**Cuidado para não cometer erros nos tags do HTML**. Substitua o nome da página Apache**2 Ubuntu Default Page** pelo seu nome, por exemplo. Vamos mudar só o nome da página que aparece no topo do brownser e no quicktab (aqui no Brasil chamamos de “orelha”.

Veja como fiz: (Mudei apenas a linha <title>)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831797/36765.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831797/36765.png)

Fonte:

Veja como ficou:

Canto esquerdo superior do FIREFOX:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831798/36766.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/7/831798/36766.png)

Fonte:

No quicktab das páginas abertas no FIREFOX

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/8/831801/36767.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/8/831801/36767.png)

Fonte:

OK! Só para você ver que funciona.

Para criar condições para múltiplos sites no mesmo servidor Apache através do Apache Virtual Hosts, você deve consultar os manuais do Apache.

### Conclusão

Criar estrutura para serviços WEB é algo relativamente simples. Um exemplo é o servidor WEB Apache. Você ainda poderia instalar um servidor de aplicações conjugado o Tomcat. O que deve ficar em mente para as pessoas que têm interesse em trabalhar com o desenvolvimento ou a comercialização de serviços WEB é que a instalação é simples, mas a documentação técnica de arquivos, diretórios e arquivos de configuração devem ser rigorosamente bem feitos e mantidos.