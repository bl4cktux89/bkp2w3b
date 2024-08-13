**Introdução**

A rede MPLS associa o mundo TCP/IP com a comutação de pacotes, proporcionando designação, encaminhamento eficiente do fluxo de dados através da rede, com relativa qualidade de serviço e com a determinação de classes de serviços. Em uma rede IP convencional, todos os dados são tratados da mesma forma, pois  não há classes de serviços diferenciadas, mas apenas um único serviço: a entrega das informações.

Na rede IP, as informações são segmentadas em pequenos pacotes e cada um deles recebe um cabeçalho que contém as informações do endereço do destinatário, bem  como demais informações de controle. Quando estes dados são destinados a outro computador que não pertence à mesma rede, os pacotes serão encaminhados através de roteadores até o destinatário final.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259267/12263.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259267/12263.png)

Etiqueta MPLS

### A rede MPLS é a junção de duas formas de transmissão de dados: roteamento e comutação.

Na rede MPLS, só existe o roteamento no início da formação de um caminho entre origem e destino com a utilização dos protocolos convencionais de roteamento. Após este caminho ser conseguido, todos os demais pacotes sempre seguirão por esta via.Para a comutação nos equipamentos entre origem e destino, serão utilizadas as informações contidas num rótulo, que será acrescentado a cada pacote ao adentrar a rede.

Os equipamentos básicos da rede MPLS são: roteador LER, que faz a interconexão entre o mundo MPLS e as demais redes, além de ser responsável pela adição e retirada das etiquetas quando os pacotes entram e saem da rede, e o roteador LSR, que tem como função a troca e o encaminhamento dos pacotes no interior da rede MPLS. Portanto, equipamentos LER estão situados na periferia e equipamentos LSR no centro da rede MPLS.

**Funcionamento da rede MPLS**

O funcionamento básico da rede MPLS consiste em: cada pacote que adentre a rede receberá uma etiqueta, um rótulo (label), que será aplicado por um roteador de borda, denominado Label Edge Router (LER).Uma vez dentro da rede MPLS, os pacotes são encaminhados através de uma rota comutada por etiquetas (label), denominadas Label Switch Patch (LSP). Esta rota é formada por roteadores de comutação por rótulos, chamados de Label Switch Router (LSR), que tomam a decisão de encaminhamento dos pacotes baseados exclusivamente nas informações destas etiquetas.

Em cada salto, o router LSR retira o rótulo existente e aplica um novo que diz ao próximo router como encaminhar o pacote. Este funcionamento é muito parecido com as das redes (X.25 e seus VCs, as redes Frame Relay e seus DLCIs e as Redes ATM com os VCS e VPs). Basicamente a ideia é a mesma.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/0/253036/12127.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/0/253036/12127.jpg)

Rede MPLS

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/4/259422/12264.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/4/259422/12264.png)

Troca de etiquetas da Rede MPLS

### **Componentes do MPLS**

A rede MPLS é formada por diversos componentes entre equipamentos e infraestrutura, porém vamos descrever os principais equipamentos e suas diretivas a fim de resumir o entendimento sem perder a essência de seu conceito.

### **Componentes do MPLS**

A rede MPLS é formada por diversos componentes entre equipamentos e infraestrutura, porém vamos descrever os principais equipamentos e suas diretivas a fim de resumir o entendimento sem perder a essência de seu conceito. Os equipamentos principais são:

### **Label Switch Routers (LSR)**

São os equipamentos que trabalham por comutação de etiquetas, isto é, são responsáveis por intercambiar os caminhos pela leitura das informações contidas nos rótulos,substituindo cada rótulo por outro que determina a próxima operação a ser realizada no próximo equipamento.Os equipamentos LSR utilizados nas redes MPLS normalmente são roteadores IP ou switches ATM habilitados para tal. Eles devem ter alguma funcionalidade definida pelo MPLS. Os equipamentos LSR são situados no interior, ou núcleo, da rede MPLS e são muito simples em processamento e operação, pois sua função é apenas trocar etiquetas entre os enlaces dos equipamentos segundo uma tabela já estabelecida anteriormente no momento da conexão.

### **Label Edge Routers (LER)**

São roteadores situados na periferia da rede MPLS tendo a função de ser a conexão e a interligação entre a rede MPLS e todas as demais, como: Frame Relay, Ethernet e ATM.A principal função dos roteadores LER é a designação e a retirada das etiquetas para o tráfego que entra e que saí da rede MPLS, além de determinar a melhor classe de serviço (QoS) correspondente às necessidades daquele específico tráfego.Ao contrário dos demais protocolos que analisam o cabeçalho inteiro de cada pacote independentemente se eles são do mesmo processo, o MPLS propõe que são necessárias apenas duas funções para permitir o transporte dos pacotes em uma rede.

A primeira função classifica todos os pacotes em um número mínimo de classes de envio equivalentes, ou Forwarding Equivalent Class (FEC), em outras palavras, o roteador LER vai determinar a real necessidade de banda para cada conjunto de pacotes e adicionar a estes uma FECespecífica. Com isso, temos FECs para aplicações diferenciadas: por exemplo, pacotes de áudio e vídeo receberam uma FEC de melhor capacidade enquanto tráfego de transferência de arquivos uma FEC não tão rápida ou de grande banda passante.Como segunda função, a rede MPLS apenas escolhe quais interfaces devem ser usadas para escoar as classes de envio em cada equipamento intermediário (LSR) no decorrer da rede. Três pacotes "A" pertencentes à mesma FEC serão igualmente transportados pelo mesmo caminho.Forwarding Equivalent Class Uma FEC consiste num conjunto de pacotes que serão encaminhados da mesma maneira e pelo mesmo percurso no interior de uma rede MPLS. Pacotes com um mesmo fluxo de dados geralmente pertencem a mesma FEC e nesta designação, critérios de QoS podem ser atribuídos a designação das FECs.

### **Label Switch Patch (LSP)**

O LSP é um caminho comutado por rótulos, ou seja, um caminho através do qual uma sequência ordenada de LSRs estabelecidos entre origem e destino determina um caminho comum para a passagem de todos os pacotes pertencentes a uma FEC específica, em outras palavras, é um caminho através do qual transitarão pacotes de uma mesma classe que compartilham o mesmo destino.Quando determinado dado adentra a rede MPLS, uma rota deve ser estabelecida até seu destinatário final. Isso é conseguido com a utilização dos protocolos convencionais de roteamento e,assim, o caminho fica definido e os pacotes pertencentes a este caminho não precisam mais ser roteados, mas sim chaveados (ou comutados) com base nas informações de seus rótulos.

Estas etiquetas são distribuídas entre LSRs no momento do estabelecimento de um LSP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/3/6/3636/i01_553.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/3/6/3636/i01_553.jpg)

MPLS