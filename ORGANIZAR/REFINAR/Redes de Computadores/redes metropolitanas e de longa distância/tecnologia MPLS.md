**1. INTRODUÇÃO**

A rede MPLS associa o mundo TCP/IP com a comutação de pacotes proporcionando designação, encaminhamento eficiente do fluxo de dados através da rede, com relativa qualidade de serviço e com a determinação de classes de serviços.

Em uma rede IP convencional, todos os dados são tratados da mesma forma, pois não há classes de serviços diferenciadas, mas sim, apenas um único serviço que é a entrega das informações.

Na rede IP as informações são segmentadas em pequenos pacotes, e cada pacote recebe um cabeçalho que contém as informações do endereço do destinatário bem como demais informações de controle.

Quando estes dados são destinados a outro computador que não pertencem à mesma rede, os pacotes serão encaminhados através de roteadores, que irão encaminhar os pacotes até o destinatário final.

Cada roteador recebe um pacote de cada vez e executa o roteamento, independente dos outros pacotes e, que consiste em verificar o endereço do destinatário encaminhando pela melhor rota possível. Esta funcionalidade pode ser descrita em três passos conhecido como algoritmo de roteamento _**Hop-by-hop**_:

- Verificar qual é o nó mais próximo do destinatário
- Ir até este nó.
- Repetir os passos anteriores até se alcançar o destinatário.

Estes três passos são executados consultando as tabelas de roteamento interna dos equipamentos e verificando qual é o prefixo mais longo que coincide com o endereço do destino final do pacote.

Observe que estes três passos são executados para cada pacote que adentra a um roteador que basicamente resume-se assim:

1 – O pacote entra no roteador e após passar pela camada 2 com sua verificação de erros é encaminhado ao nível 3 de rede.

2 – O roteador verifica o endereço de destinatário do pacote e procura em suas tabelas qual é a melhor rota de encaminhamento.

3 – O pacote então é novamente levado à camada 2, onde ele será encapsulado em um outro quadro, recebendo novos endereços _**Mac Address**_ e, então, será encaminhado a  porta correspondente para ser transmitido.

Este processo todo é executado para cada pacote que entra no roteador, mesmo que todos eles sigam para o mesmo destinatário consumindo tempo e causando atraso na propagação dos datagramas, por causa de todo o processamento necessário para rotear cada pacote independentemente. A tecnologia MPLS resolve esta questão com a comutação dos pacotes e não mais o roteamento.

Para deixar bem esclarecido a diferença fundamental entre rotear e comutar pode-se considerar que roteamento é executado na camada 3, enquanto a comutação realiza-se na camada 2 do modelo de referencia OSI, portanto, economiza-se um processamento de nível 3.

**2. Características Básicas do MPLS**

Os dados em uma rede MPLS são encaminhados através de caminhos pré-estabelecidos anteriormente, sendo feito a partir da descoberta da melhor rota que se realiza por roteamento igual a uma rede convencional IP, porém, depois desta rota descoberta, os dados são comutados em nível 2 (do modelo de referencia OSI) economizando processamento e todos os _**frames**_ sendo transmitidos por um único caminho.

A tecnologia MPLS é utilizada em _**backbones**_, e consiste em uma solução para problemas das redes convencionais, tais como escalabilidade, velocidade, gerenciamento e designação de _**Quality off Service**_ (QoS) para cada aplicação, dependendo das suas necessidades particulares.

Entre varias vantagens do MPLS destaca-se:

- Qualidade de Serviço – QoS;
- Classes de Serviço – Cós;
- Orientação à conexão em redes IP;
- A transferência da comutação da camada 2 para a camada 3;
- Menor complexidade nas decisões de encaminhamento dos datagramas;
- _Virtual Private Network_ (VPNs)

A aplicação mais interessante do MPLS é sua utilização em conjunto como IP, pois desta forma temos o melhor das duas tecnologias. No IP temos as vantagens do roteamento na descoberta dos destinatários e no MPLS a comutação de circuitos, tornando assim a transferência extremamente rápida.

**3. Funcionamento da Rede MPLS**

O funcionamento básico da rede MPLS consiste que cada pacote que adentra a rede receberá uma etiqueta, um rótulo (_**label**_) que será aplicado por um roteador de borda denominado _**Label Edge Router**_ (LER).

Uma vez dentro da rede MPLS os pacotes são encaminhados através de uma rota comutada por etiquetas (_**label**_), denominado _**Label Switch Patch**_ (LSP). Esta rota é formada por roteadores de comutação por rótulos chamados _**Label Switch Router**_ (LSR) que tomam a decisão de encaminhamento dos pacotes baseado exclusivamente nas informações destas etiquetas.

Em cada salto o _**router**_ LSR retira o rótulo existente e aplica um novo que diz ao próximo _**router**_ como encaminhar o pacote. Este funcionamento é muito parecido com as das redes já estudas:  X.25 e seus VCs, as redes _**Frame Relay**_ e seus DLCIs e as Redes ATM com os VCS e VPs. Basicamente a ideia é a mesma. E a figura 1 ilustra uma rede MPLS.

**4. Componentes do MPLS**

A rede MPLS é formada por diversos componentes entre equipamentos e infraestrutura, porém vamos descrever os principais equipamentos e suas diretivas a fim de resumir ao entendimento sem perder a essência do seu conceito.

Os equipamentos principais são_**: Label Switch Routers**_ (LSR) e _**Label Edge Routers**_ (LER).

- _**Label Switch Routers**_ **(LSR)**

LSR são equipamentos que trabalham por comutação de etiquetas, isso é, eles são responsáveis de intercambiar os caminhos pela leitura das informações contidas nos rótulos, substituindo cada rótulo por outra que determina a próxima operação a ser realizada no próximo equipamento.

Os equipamentos LSR utilizados nas redes MPLS normalmente são roteadores IP ou _**switches**_ ATM habilitados para tal. Eles devem ter alguma funcionalidade definidas pelo MPLS implementadas. Os equipamentos LSR são situados no interior ou núcleo da rede MPLS e são muito simples em processamento e operação, pois sua função é apenas de trocar etiquetas entre os enlaces dos equipamentos segundo uma tabela já estabelecida anteriormente no momento da conexão.

- _**Label Edge Routers**_ **(LER)**

São roteadores situados na periferia da rede MPLS tendo a função de ser a conexão e a interligação entre a rede MPLS e todas as demais, como exemplo: _**Frame Relay**_, Ethernet e ATM.

A principal função dos roteadores LER é a de designação e a retirada das etiquetas para o tráfego que entra e que saí da rede MPLS e de determinar a melhor classe de serviço (QoS) correspondente as necessidades daquele especifico tráfego.

Ao contrário dos demais protocolos que analisam o cabeçalho inteiro de cada pacote independentemente se eles são do mesmo processo, o MPLS propõe que são necessárias apenas duas funções para permitir o transporte dos pacotes em uma rede.

A primeira função classifica todos os pacotes em um número mínimo de classes de envio equivalentes ou _**Forwarding Equivalent Class**_ (FEC) que em outras palavras, o roteador LER vai determinar a real necessidade de banda para cada determinado conjunto de pacotes e adicionar a estes uma FEC especifica. Com isso, temos FECs para aplicações diferenciadas, onde pacotes de áudio e vídeo receberam uma FEC de melhor capacidade, enquanto tráfego de transferência de arquivos uma FEC não tão rápida ou de grande banda passante.

Como segunda função a rede MPLS apenas escolhe que interfaces devem ser usadas para escoar as classes de envio em cada equipamento intermediário (LSR) no decorrer da rede. Três pacotes “A” pertencentes à mesma FEC e serão igualmente transportados pelo mesmo caminho.

- _**Forwarding Equivalent Class**_ **(FEC)**

Uma FEC consiste num conjunto de pacotes que serão encaminhados da mesma maneira e pelo mesmo percurso no interior de uma rede MPLS. Pacotes com um mesmo fluxo de dados geralmente pertencem a mesma FEC e nesta designação, critérios de QoS podem ser atribuídos a designação das FECs.

- _**Label Switch Patch**_ **(LSP)**

O LSP é um caminho comutado por rótulos, ou seja, um caminho através do qual uma sequencia ordenado de LSRs, estabelecidos entre origem e destino, determinam um caminho comum para a passagem de todos os pacotes pertencentes a uma FEC especifica. Em outras palavras, uma LSP é um caminho através do qual transitarão pacotes de uma mesma classe, que compartilham o mesmo destino.

Quando um determinado dado adentra a rede MPLS, uma rota deve ser estabelecida até seu destinatário final. Isso é conseguido com a utilização dos protocolos convencionais de roteamento, e assim, o caminho fica então definido e os pacotes pertencentes a este caminho não precisam mais ser roteados, mas agora eles serão chaveados ou comutados com base nas informações de seus rótulos.

Estas etiquetas são distribuídas entre LSRs no momento do estabelecimento de um LSP.

**Para refletir:**

A rede MPLS é a junção de duas formas de transmissão de dados, a forma de roteamento e a forma da comutação.

Na rede MPLS só existe o roteamento no início da formação de um caminho entre origem e destino com a utilização dos protocolos convencionais de roteamento. Após este caminho ser conseguido, todos os demais pacotes sempre seguirão por esta via.

Para a comutação nos equipamentos entre origem e destino serão utilizadas as informações contidas num rotulo que será acrescentado a cada pacote ao adentrar a rede MPLS.

Os equipamentos básicos da rede MPLS são: Roteador LER que faz a interconexão entre o mundo MPLS e as demais redes. Este equipamento é responsável pela adição e a retirada das etiquetas quando os pacotes entram e saem da rede e o roteador LSR que tem como função a troca e o encaminhamento dos pacotes no interior da rede MPLS. Portanto, equipamentos LER estão situados na periferia e equipamentos LSR no centro da rede MPLS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/0/253036/12127.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/0/253036/12127.jpg)

Rede MPLS e a troca de etiquetas

**1. INTRODUÇÃO**

Em continuação ao estudo da tecnologia MPLS, iremos nos aprofundar um pouco mais nos detalhes técnicos, estudando a etiqueta e seu significado no encaminhamento dos pacotes.

A etiqueta ou rótulo é um identificador curto, de tamanho fixo e significado apenas local, isso quer dizer que, as informações nela contida são válidas apenas naquele enlace e vão informar ao equipamento seguinte, o próximo caminho que o pacote deve seguir, ou seja, identificar a FEC.

O cabeçalho MPLS é posicionado sempre depois de qualquer cabeçalho de nível 2 e antes do cabeçalho de nível 3 do modelo de referencia OSI. Diz-se que a etiqueta MPLS em realidade fica situada na camada 2,5 do OSI, se é que ela existe... Mas para entendimento acadêmico, fica valendo o exemplo...

O rótulo MPLS tem seu tamanho definido em 4 octetos e ele deve ser pensado como uma forma abreviada para o cabeçalho do pacote comum, identificando de forma simples ao roteador ou _**switch**_ a decisão que ele deve tomar a fim de encaminhar o referido pacote. Neste contexto, o rótulo nada mais é do que uma abreviação para um fluxo agregado de dados do usuário. A figura1 ilustra uma etiqueta MPLS com seus referidos campos que são:

- Campo _Label_ - Com 20 bits carrega o valor atual do rótulo MPLS.
- Campo EXP – Com 3 bits indica a classe de serviço a que o pacote pertence, ou seja, indica a prioridade do pacote.
- Campo _Stack_ – É utilizado para o enfileiramento de etiquetas, caso o pacote receba mais de uma.
- Campo TTL – Tem a mesma função do TTL encontrado no cabeçalho do pacote IP convencional. Sua função é contar por quantos roteadores o rótulo passa, diminuindo a contagem a cada passagem em um até chegar ao número zero onde o pacote será descartado evitando _loops_.

Conforme verificado, uma FEC consiste em um conjunto de pacotes que serão encaminhados por um único caminho que é o LSP. A FEC é representada por uma etiqueta, e cada LSP é associado a uma FEC.

Ao receber um pacote vindo de outras redes, o roteador LER verifica a qual FEC ele deverá pertencer e o encaminha através do LSP correspondente. Portanto há uma associação Pacote – Etiqueta – FEC – LSP, onde esta associação acontece somente uma vez, quando o pacote adentra a rede MPLS.

No interior da rede as etiquetas vão sendo trocadas à medida que passam pelos roteadores LSR cuja função e trocar estas etiquetas, determinando o próximo salto sempre pela mesma LSP.

Com a Comutação de etiquetas o processo de encaminhamento dos pacotes tornou-se extremamente rápido e com isso, a rede MPLS possui alta capacidade de transferência sendo utilizada nos grandes _**Backbones**_ das concessionárias de telecomunicações, podendo absorver e transferir qualquer tipo de protocolo que adentra a mesma.

**2.** _**Label Information Base**_ **(LIB)**

A LIB é uma tabela existente em cada roteador / switch da rede MPLS que demonstra o encaminhamento ou as informações correlacionadas das etiquetas e as interfaces do equipamento. Uma vez criada uma LSP, vai existir uma relação com a etiqueta e a interface e esta relação será armazenada na LIB.

Quando um pacote entra em um equipamento LSR, este verifica para qual interface de saída este pacote deve ser encaminhado utilizando as informações da tabela, realizando assim a troca da etiqueta de entrada por outra de saída a fim de que o pacote possa alcançar o próximo LSR e assim sucessivamente.

O componente de encaminhamento é responsável por criar e manter a tabela LIB. Ele examina a informação contida no cabeçalho do pacote e, faz uma busca na LIB para que consiga estabelecer uma associação entre o pacote e um rótulo particular (INACIO, 2007).

A LIB consiste então em uma sequencia de entradas que são utilizadas no encaminhamento dos pacotes. Esta sequencia de entradas é criada de acordo com as FEC’s e os rótulos associados a elas. A figura 2 ilustra uma tabela LIB de forma simplificada e acadêmica.

**3. Protocolo** _**Label Distribution**_ **(LDP)**

O protocolo LDP é o responsável pela distribuição das etiquetas entre os roteadores de comutação por rótulos – LSR, desta forma possibilitando a criação das LSPs.

Para tanto, o protocolo LDP oferece mecanismos de descoberta de LSR para permitir que LSRs encontrem uns aos outros e estabeleçam uma comunicação. O LDP roda sobre o TCP para garantir a entrega das mensagens, pois, o TCP é dotado de artifícios de notificação de recebimento retratado pelo número de reconhecimento.

Para ficar bem claro então, o LDB é o protocolo de distribuição das etiquetas que formam as LSPs. Portanto, para que ocorra um _**link**_ de comunicação, são necessárias duas LSPs entre a origem e destino, formando assim um caminho bidirecional, onde cada caminho poderá ter uma FEC diferente em cada sentido.

Apesar de que outros protocolos possam ser usados para a função de entrega de pacotes como exemplo: o BGP ou o RSVP, o LDP tem se mostrado o mais empregado, sendo uma das partes mais importantes do MPLS cada vez mais utilizado pela indústria construtora desta tecnologia.

Resumidamente o LDP mapeia as informações da camada de rede em caminhos diretos comutados na camada de enlace, tornando-se responsável por criar efetivamente as LSP’s. Uma conexão fim a fim para o envio de dados é criada à medida que o LDP distribui rótulos para uma data FEC. A FEC associa um LSP especifico aos pacotes mapeados a esse LSP. A troca de informação entre dois equipamentos LRS são denominadas pares LDP (ou LDP _**peers**_), onde uma sessão é estabelecida para eles se comunicarem. Existem quatro tipos de mensagens LDP (MAGALHÃES, 2007):

- Mensagem de descoberta: anuncia a presença de um LSR à rede;
- Mensagem de sessão: estabelece, mantém e finaliza sessões LDP;
- Mensagem de anúncio de rótulo: cria, modifica e exclui associações de rótulos a FECs;
- Mensagem de notificação: provê informações de estado da rede e sinalização de erros

**4. Empilhamento de Rótulos**

O MPLS foi projetado para ser usado em redes de grande porte suportando comutação de etiquetas com operações hierárquicas, baseado na habilidade de um pacote poder carregar mais de uma etiqueta. Portanto, o MPLS possui a característica de definição de pilha de rótulos, que consiste em uma sequencia de cabeçalhos MPLS, onde, um pacote rotulado pode conter em sua área de dados outro pacote rotulado, o que possibilita a criação de LSPs, uma sobre a outra.

O empilhamento de rótulos MPLS permite que redes MPLS distintas troquem informações, sem se preocupar com rotas interdomínio. O processamento de um pacote rotulado é totalmente independente do nível de hierarquia dos rótulos, ou seja, o nível de rótulo é irrelevante para o LSR, onde, o rótulo do topo sempre será a base, abstraindo-se os demais rótulos que pode haver abaixo dele. Por ser o MPLS um protocolo múltiplo ele é compatível com diversos protocolos de camada 2 e 3 sempre sendo acrescentado um rotulo entre estas camadas.

**Para refletir:**

1. A Tecnologia MPLS acrescenta uma etiqueta de pequena dimensão com informações curtas entre a camada 2 e a camada 3 do modelo de referencia OSI.
2. Estas informações vão permitir aos _Switch/router_ executar a comutação ao invés do roteamento.
3. Em cada equipamento da rede MPLS existe uma tabela LIB onde todas as informações de comutação estão contidas, indicando qual interface deverá ser usada para cada pacote que entra e é analisado pelo _router_.
4. O protocolo mais utilizado na rede MPLS é o LDP que, apesar de ser simples, consegue executar a comutação e a descoberta de novos equipamentos na rede e, devido a isso, abrangendo todas as necessidades de funcionamento.
5. O empilhamento de rótulos MPLS permite que redes MPLS distintas troquem informações, sem se preocupar com rotas interdomínio.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259267/12263.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259267/12263.png)

Figura 1 - Etiqueta e seus campos MPLS

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/4/259427/12264.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/4/259427/12264.png)

Figura 2 - Encaminhamento de pacotes em uma rede MPLS