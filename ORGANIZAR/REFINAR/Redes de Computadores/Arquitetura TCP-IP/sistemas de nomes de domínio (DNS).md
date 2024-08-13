### Introdução

Existem diversas aplicações nas redes locais e na internet que necessitam do serviço de resolução de nomes de domínio. O DNS (Domain Name System – sistema de nome de domínios) é uma aplicação do tipo cliente/servidor que possibilita o uso de endereços da camada de aplicação, por exemplo, [**www.uninove.br**](http://www.uninove.br/),  em vez de usar o endereço lógico da camada de Internet, seja ele IPv4 ou IPv6.

Dentro do paradigma clientes/servidor, existem programas que podem ser utilizados diretamente pelo usuário, como é o caso do HTTP, para acessar a página da Uninove, e aqueles que dão suporte para aplicações da camada de aplicação. O DNS se enquadra nessa última categoria, oferecendo suporte, por exemplo, ao HTTP e aos programas de e-mail. Isso quer dizer que, você pode acessar o site [**www.uninove.br**](http://www.uninove.br/) diretamente pelo endereço IP do site. Mas imagine ter que memorizar todos os endereços de sites e e-mail que você utiliza na internet, é claro que, ficaria inviável. Daí podemos ter a ideia da grande importância do serviço DNS.

A figura abaixo mostra um exemplo de um programa de e-mail (SMTP: Simple Mail Transfer Protocol – Protocolo Simples de transferência de e-mail) fazendo uso do DNS para dar suporte a sua aplicação. O usuário do e-mail conhece muito bem o e-mail do destinatário, por exemplo, fulano@uninove.br, mas o TCP/IP precisa identificar de forma exclusiva a entidade de destino por meio do endereço IP do servidor uninove.br. Para tanto, o programa cliente DNS envia uma solicitação a um servidor DNS (na porta 53) previamente configurado para que seja feito o mapeamento do endereço de e-mail para o IP correspondente, antes de enviar o e-mail propriamente dito.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/3/1/1763169/39533.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/3/1/1763169/39533.png)

Quando a internet estava em seus primórdios o mapeamento de endereços era feito por meio de um arquivo de host, contendo apenas duas colunas: nome e endereço. Cada host poderia manter seu arquivo de host em disco e atualiza-lo periodicamente a partir de um arquivo hosts mestre. Quando ele precisava de um mapeamento, o host consultava a sua tabela de host e contra o mapeamento.

Atualmente, seria impossível manter em apenas um arquivo de host tal mapeamento. Esse arquivo seria muito grande e com atualizações constantes para cada host da rede. A solução seria armazenar o arquivo de host em um único computado, permitindo que todos os hosts que necessitam de resolução consultassem esse servidor. Entretanto, o volume de tráfego gerado na internet seria enorme.

A solução usada nos dias de hoje, consiste em dividir esse enorme volume de dados em partes menores armazenados em computadores diferentes. A partir desse método, um host que necessita de um mapeamento consulta um servidor mais próximo que conteria a resolução necessária.

### Espaço de Nomes

Com o objetivo de evitar ambiguidades, os nomes atribuídos ás máquinas devem ser escolhidos cuidadosamente a partir de um espaço de nomes (name space) com total controle sobre o relacionamento com o endereço IP. Os endereços, como você já sabe, são únicos, os nomes também devem ser. A organização de nomes pode ser feita de duas maneiras: plana ou hierárquica (Forouzan, B. A. 2010).

- **Espaço de nomes plano:** Nesse formato deve existir um único computador que mantem todas as informações de nomes e endereços com o objetivo de evitar duplicatas. Os nomes seriam formados por uma sequência sem estrutura definida. Imagine o seu nome completo, ele possui uma estrutura formada por nome, prenome e sobrenome, obedecendo uma estrutura. Se utilizarmos o espaço de nomes planos, o nome, prenome e sobrenome poderia chamar apenas NOME. No espaço plano, basta que o nome identifique apenas um endereço, não importando a sua formação.
- **Espaço Hierárquico:** em um espaço de nome hierárquico é constituído por várias partes. A primeira parte pode definir a natureza da organização, a segunda parte pode estabelece o nome de uma organização, a terceira pode determinar o departamento dentro de uma organização e assim por diante. Dessa forma, cada parte pode ser decentralizada, onde cada parte pode ser definida por um departamento dentro da instituição. É dessa forma que a internet é formada de forma estruturada e hierárquica. Imagine que duas universidades, USP e Uninove atribuam a um de seus servidores o nome _ava._ A USP recebeu da autoridade central o nome usp.br e a UNINOVE recebeu uninove.br. O nome formado ao final continuará sendo único e composto por ava.uninove.br e ava.usp.br. A autoridade central controla apenas o uninove.br e usp.br, o prenome fica a cargo da instituição.

### Espaço de nomes de domínio

Para que a internet tivesse um espaço de nome hierárquico, foi estabelecido o conceito de **espaço de nomes de domínios**. Este modelo é estruturado em árvore invertida, com a raiz na parte superior e com ramificações para baixo, conforme mostrado na figura abaixo. A árvore pode ter apenas 128 níveis: do nível 0 (raiz) ao nível 127.

Cada nó da árvore recebe um rótulo (label) que é uma string de, no máximo, 63 caracteres. O label raiz é uma string nula (string vazia). O DNS exige que cada filho de um nó que se ramificam a partir de um mesmo tenham labels distintos, garantindo, dessa forma, a exclusividade dos nomes de domínios.

Além disso, cada nó da árvore tem nome de domínio. Um **nome de domínio completo** é uma sequência de label separados por pontos (.). Os nomes são sempre lidos do nó para cima, em direção à raiz. O último label é o label raiz nulo. Isso significa que o nome de domínio completo sempre termina em um label nulo, portanto, com um (.) como ultimo caractere, pois a string null não é nula (Forouzan, B. A. 2010).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/3/2/1763212/39534.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/3/2/1763212/39534.png)

Fonte: Adaptado de Forouzan, B. A. 2010

### Hierarquia dos servidores de nomes

Para evitar que problemas de segurança e desempenho ao armazenar os nomes de domínios em um único servidor, como já comentando anteriormente, a solução foi distribuir as informações por um grande número de computadores denominados servidores DNS. Os servidores DNS são do tipo (Kurose, James F, 2013):

- **Servidores DNS raiz:** Na internet existem 13 servidores raiz, denominados de A a M. Embora seja referido com 13 servidores raiz como sendo um único servidor, na verdade, cada servidor raiz é estruturado de forma distribuída, formando um conglomerado de servidores.
- **Servidores DNS de Domínio de Alto Nível (TLD):** são os servidores responsáveis por domínios de alto nível como _**com**_, _**org**__,_ _**edu**_ e _**gov**_, além de todos os domínios de alto nível de países, tais como _**uk**_, _**fr**_, _**br**_ e _**jp**_. A Empresa Verisign Global Registry Sevices é responsável por manter os servidores TLD para os domínios de alto nível do tipo _**com**_ e a Educause mantém os servidores TLD para os domínios de alto nível do tipo _**edu,**_ conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/3/222365/8104.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/3/222365/8104.png)

Distribuição dos DNS raiz ao redor do mundo

- **Servidores DNS autoritativos:** toda organização que possui hosts que podem ser acessados a partir da internet (web site ou serviço de e-mail) deve fornecer registro DNS acessíveis publicamente para mapear os nomes desses domínios para endereço IP. Esse tipo de servidor pode ser fornecido por algum provedor de serviço que permite que registre a sua organização ou se a organização desejar, ela pode ter o seu próprio servidor autoritativo. Empresas de grande porte e universidades optam por ter o seu próprio servidor primário e secundário autoritativos. Na Figura abaixo são mostrados os três níveis até aqui apresentados.
- **Servidores DNS locais:** Tais servidores não pertencem a hierarquia de servidores DNS, mas são fundamentais para o funcionamento dos usuários finais residências e corporativos. Cada provedor de serviço de internet (ISP) fornecem aos seus clientes os servidores DNS que são adquiridos por meio da solicitação DHCP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/3/222321/8103.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/3/222321/8103.png)

Três níveis de DNS: de cima para baixo: Raiz, TLD e Autoritativo

### Consulta recursiva e iterativa

- **Consulta recursiva:** Quando o hospedeiro requisitante (cis.poly.edu) da figura abaixo faz uma requisição de resolução de nomes, ele não recebe respostas parciais. O servidor DNS local trabalha em favor do hospedeiro requisitante até que tenha a resposta desejada para retornar. Esse mecanismo é conhecido como **consulta recursiva** (Tannenbaum, Andrew S, 2011).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/7/256704/13767.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/7/256704/13767.jpg)

Consulta recursiva

- **Consulta iterativa:** Por outro lado, quando um servidor raiz ou TLD retorna apenas a resposta parcial e o servidor local prossegue para a próxima consulta, o mecanismo é chamado de consulta iterativa, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/7/256705/13766.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/7/256705/13766.jpg)

Consulta Iterativa

### Registros e Mensagens DNS

Os servidores DNS executando um banco de dados distribuído do DNS armazenam o que é chamado de Registros de Recursos (RR). Os RR fornecem o mapeamento de nomes de hospedeiros para o respectivo endereço IP. Cada mensagem de resposta DNS leva consigo um ou mais registros de recursos. Os registros de recursos são formados por cinco elementos: Tempo_de_Vida (TTL), Nome_domínio, Valor, Tipo e Classe (Tannenbaum, Andrew S, 2011).

- **Nome_domínio**: Informa o domínio ao qual esse registro pertence. Muitas vezes existem muitos registros para cada domínio, e cada banco de dados armazena informações sobre vários domínios. Cabe acrescentar que Nome_domínio depende do campo TIPO.
- **TTL**: fornece uma indicação de estabilidade do registro. Informações muito estáveis recebem um valor alto como, por exemplo, 86.400, que corresponde ao número de segundos de um dia. Por sua vez, as informações muito voláteis recebem 60 (1 min). Este valor permite ao servidor DNS determinar durante quanto tempo um determinado registro será mantido em cache.
- **Classe**: Terceiro campo de cada registro de recurso é chamado de classe. Caso as informações sejam relacionadas a Internet, ele é sempre IN. Para informações não relacionadas a Internet podem assumir outros códigos; mas raramente são empregados.
- **Valor**: O campo valor, assim como Nome_domínio, depende do tipo. Esse campo pode ser um número, um nome de domínio ou uma string ASCII. Na tabela anterior é mostrada uma breve descrição desse campo.
- **TIPO**: informa qual é o tipo de registro. Os mais importantes são mostrados na tabela abaixo.

|Tipo|Valor|Significado|
|---|---|---|
|**SOA**|[[parâmetros para essa zona]]|(_**Start of Authority**_): indicam o início de uma zona, isto é, de um conjunto de registros localizado dentro de um espaço de nomes de DNS. Cada zona deve ter um registro SOA|
|**A**|[[inteiro de 32 bits]]|Ele contem um endereço IPv4 de 32 bits de alguns hosts. Esse é o tipo de registro é o mais importante. Um determinado host pode ter duas ou mais placas de rede associada ao mesmo domínio|
|**AAAA**|[[inteiro de 128 bits]]|endereço de IPv6 de um host de 128 bit, semelhante ao registro A|
|**MX**|[[prioridade, domínio disposto a aceitar correio eletrônico]]|Indica o nome do host preparado para aceitar mensagens de correio eletrônico para o domínio especificado|
|**NS**|[[nome de um servidor de domínio]]|Especifica um servidor de nomes para o domínio ou subdomínio. É um host que tem uma cópia do bando de dados para um domínio|
|**CNAME**|[[Nome de domínio]]|Permite a criação de nomes alternativos. Por exemplo, podemos criar um apelido para o site redes.ava.uninove.br, com CNAME igual a rava.uninove.br|
|**PTR**|[[Nome alternativo de um endereço IP]]|É quase sempre usada em pesquisas inversas, quando se tem o endereço IP e deseja-se o nome da máquina|
|**SPF**|[[Estrutura de política do servidor]]|É um tipo de registro que permite a um domínio codificar informações sobre quais máquinas no domínio enviarão correio eletrônico ao restante da internet, ajudando a máquina receptora a verificar se o e-mail é válido.|
|SRV|[[serviço]]|Generaliza o registro MX que é feito apenas para correio eletrônico.|
|**TXT**|[[texto ASCII descritivo]]|Permitiam que os domínios originalmente se identificassem de forma arbitrária.|

  
  

### Mensagem DNS

O Serviço DNS possui dois tipos de mensagens: consulta e resposta. No entanto, apresenta o mesmo formato de mensagem. Alguns campos são configurados em zero para mensagens de consulta. O cabeçalho tem 12 bytes, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/7/256737/13769.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/6/7/256737/13769.jpg)

Cabeçalho DNS

a função de cada um dos campos é detalhada abaixo:

- **Identificação:** Usado pelo cliente para associar uma resposta a uma consulta. O cliente configura um número de identificação diferente cada vez ele envia uma consulta.
- **Flags:** é um conjunto de subcampos que definem o tipo de mensagem, que pode ser: tipo de mensagem, tipo de resposta solicitada, tipo de resolução desejada (recursiva ou iterativa) e assim por diante.
- **Número de perguntas:** contém o número da seção de perguntas da mensagem.
- **Número de resposta:** contem o numero de resposta da seção resposta da seção de resposta de uma mensagem de resposta.
- **Número de registro de autoridade:** contem o número de registro de autoridades da seção autoridade de uma mensagem de resposta.
- **Número de registro (RRs) de informações adicionais:** possui o número de registro de informações adicionais da seção de informação adicional de uma mensagem de resposta.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/3/2/1763233/39535.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/6/3/2/1763233/39535.png)