**1. - INTRODUÇÃO**

Desde os primórdios do uso da Internet para a conexão de poucas instituições de ensino nos EUA, nunca se imaginou um crescimento exponencial e tão rápido como foi o seu que, atualmente, ela funciona pela aplicação do protocolo BGP, que é considerado por muitos especialistas e pelo Dr. Douglas E. Comer, como sendo: "_**a cola que mantém a Internet unida e permite a interconexão universal**_”.

No inicio dos anos 70, o principal _**backbone**_ da Internet era a ARPANET, que nada mais era que uma pequena rede de longa distância que conectava algumas das principais instituições de ensino superior nos Estados Unidos da América e boa parte destas conexões era via _**dial-up**_.

As instituições de pesquisa conectadas à rede precisavam gerenciar manualmente as tabelas de rotas para todos os possíveis destinos, ou seja, todas as outras redes conectadas e a cada dia que a rede ia crescendo por mais instituições solicitando sua conexão à mesma, tornou este serviço manual de gerenciamento impossível de ser feito.

Foi necessário então (a partir destas dificuldades) desenvolver uma nova forma de conectar as instituições e isso foi feito ao criar um reduzido grupo de roteadores centralizados, chamados _**core router**_ que, em suas tabelas, tinham as rotas para todos os possíveis destinos da Internet e um grupo maior de roteadores conectados ao _**core**_ que possuíam rotas parciais e locais para seus destinatários chamados _**nocore routers,**_ ou, roteadores fora do núcleo.

Os roteadores do núcleo eram administrados pelo (Internet Network Operations Center (INOC) e, ficaram responsáveis pelo _**backbone**_ da ARPANET, enquanto os roteadores fora do núcleo eram das instituições de ensino e administrado localmente.

Este esquema funcionou por algum tempo, mas percebeu-se que não era possível ter mais instituições de ensino entrando na rede e esta rede ser totalmente colapsada em apenas um único centro. Os projetistas notaram também que as interconexões de um _**backbone**_ com arquitetura complexa não devem ser encaradas como várias redes independentes conectadas a um núcleo apenas, mas como uma organização que controla várias redes e que garante que as informações sobre as rotas internas são consistentes e que pode escolher um de seus roteadores para fazer a ponte de comunicação para o mundo exterior (MOURA 1999).

**2. - Sistemas Autônomos - Autonomous Systems (AS)**

Atualmente a Internet não esta mais conectada a um único _**backbone**_ ou grupo de roteadores que controlam toda a sua atividade, isso nem seria possível devido à massificação de redes, empresas e pessoas que estão conectadas a mesma.

O conceito então de Sistemas Autônomos se refere a um conjunto de redes com um mesmo domínio administrativo, que possuem políticas de roteamento e de regras em comum. A Internet hoje é formada por um grande número de Sistemas Autônomos, sendo cada um administrado por uma ou mais organizações.

Todos os Sistemas Autônomos possui uma identificação numérica, o ASN que foi definido na resolução RFC 1930 e é represento por um número de 16 bits. Cada um possui um identificador único e estas atribuições foram definidas pela _**Internet Assigned Numbers Authority**_ (IANA) ou seus correspondentes em cada área designada.

Junto com a IANA outras organizações também trabalham juntas em associação e são conhecidas como _**Regional Internet Registry**_ (RIR), onde temos as seguintes divisões:

1. _American Registry for Internet Numbers_ (ARIN) _–_ Responsável pelas Américas, Caribe e África.
2. _Reseaux IP Europeennes – Network_ (RIPE-NCC) – Responsável pela Europa.
3. _Ásia Pacific – Network Information Centre_ (AP-NIC) – Responsável pela Ásia e Pacífico.

Os Sistemas Autônomos possibilitam a divisão do grupo de redes interconectadas globalmente em redes menores e mais fáceis de gerenciar. O roteamento entre as ASs é realizado por protocolos do tipo _**Exterior Gateway Protocol**_ (EGP) como o _**Border Gateway Protocol**_ (BGP) que atualmente encontra-se na sua versão 4.

Questões políticas, aspectos econômicos e de segurança podem ser configurados nos roteadores de interligação das ASs preservando assim o tráfego e demais normas pré-estabelecidas.

No Brasil temos o Comitê Gestor da Internet no Brasil (CGI.br) e o Núcleo de Informação e Coordenação do Ponto BR (NIC.br), entidades estas responsáveis pelo controle, fornecimento e gerenciamento dos ASs e suas políticas e da distribuição de IPs.

O CGI não administra o AS em questão, pois isso é feito por sua entidade administrativa, mas sim, o CGI administra a interconexão destes ASs em perfeita harmonia de funcionamento. Na tabela 1 podem-se verificar alguns ASs, seus ASN e sua organização administrativa que controla o seu funcionamento e a figura 1 ilustra um Sistema Autônomo típico.

|ASN|Extensão|Empresa|Contato|Departamento|
|---|---|---|---|---|
|1251|100|[[Fundacção de Amparo a Pesquisa do Estado de São Paulo]]|Jorge Futoshi Yamamoto|NOC|
|1251|810|[[Instituto Nacional de Pesquisas Espaciais]]|Benicio Pereira de Carvalho Filho|NOC|
|1251|820|[[UNESP]]|Carlos Coletti|GRC (Assessoria de Informática)|
|1251|830|[[Universidade Estadual de Campinas]]|Daniela Regina Barbetti Silva|CSIRT|
|1251|840|[[Universidade de São Paulo]]|André Gerhard|CSIRT - USP|
|1916|100|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 7]]|Alexandre Leib Grojsgold|CO Rio de Janeiro|
|1916|200|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 9]]|Jose Wilson do Nascimento|CO Brasilia|
|1916|300|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 5]]|Marcel Faria|GER Campinas|
|1916|400|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 6]]|PoP - RJ|LNCC - Rio|
|1916|500|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 8]]|POP Salvador|POP - BA|
|1916|600|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa]]|Jairo Carlos Filho|POP - SP|
|1916|601|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 2]]|Rogério Herrera Mendonca|POP - SP|
|1916|700|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 4]]|Mauricio Noronha Chagas|NOC Brasilia|
|1916|767|[[RNP - Associação de Rede Nacional de Ensino e Pesquisa 3]]|Rafael de Oliveira Ribeiro|Gerência de Operações|
|1916|800|[[CAIS-RNP - Centro de Atendimento a Incidentes de Segurança da RNP]]|Jacomo Dimmit Boca Piccolini|CAIS|
|2715|100|[[Rede Rio]]|Marita Maestrelli|NOC|
|2715|626|[[Fundação de Amparo a Pesquisa-RJ]]|Marita Maestrelli|REDERIO|

  
  

Para anunciar as rotas para suas redes internas entre si, os ASs precisavam concordar em usar um esquema único, como um mesmo idioma por toda a Internet. Esta linguagem comum e o protocolo BGP-4.

**3. - Border Gateway Protocol Version 4 (BGP-4)**

O BGP-4 é um protocolo de roteamento para ser utilizado entre Sistemas Autônomos baseados no protocolo TCP/IP.

Pode-se considerar que o BGP é um protocolo completo e funcional, pois, leva em consideração todas as questões políticas de roteamento entre os ASs, baseado em regras arbitrárias por eles definidas e, extinguiu os problemas de “_**loops**_” dos seus antecessores. Além disso, o BGP-4 foi à primeira versão do BGP a suportar endereços agregados _**Classless Interdomain Routing**_, ou simplesmente CIDR e o conceito de super-redes.

Nesta conceituação o BGP assume que existem duas categorias de sistemas de roteamentos nos ASs: Um sistema denominado _**Interior Gateway Protocol**_ (IGP), que trata do roteamento interno do AS e que este poderá ser qualquer protocolo de uso mais comum como: RIP, OSPF, IGRP, EIGRP; ou até mesmo através de rotas estáticas pré-definidas.

Outra categoria é o _**Exterior**_ BGP (eBGP) que constrói suas tabelas internas e um gráfico externo com as informações trocadas pelos sistemas vizinhos, através do roteador de borda ou de periferia, conhecido como roteadores _**peers**_ (destinados a atribuições políticas).

Ainda temos no interior da nuvem que forma o AS, os roteadores internos, estes na nomenclatura BGP são os roteadores _**neighbors**_ que são conectados entre si por uma sessão TCP utilizando a porta 179 para o transporte das informações de roteamento, de modo que ele próprio não precisa preocupar-se a respeito da correta transmissão das informações, pois a sessão TCP se encarregará de todos os aspectos de segurança e da confirmação do recebimento correto dos dados.

Como exemplo temos na figura 2 uma ilustração de um AS típico com seus roteadores _**neighbor**_ e _**peers**_ devidamente conectados em uma nuvem.

O funcionamento básico do BGP consiste na divulgação as redes externas ao AS, ou seja, a outros ASs quais são as rotas para as redes internas dentro do mesmo. Esta funcionalidade de divulgação é realizada pelos roteadores de borda, que em realidade são as fronteiras do referido AS. Além desta função, os roteadores de borda tem a função política de acesso ao AS, isso significa dizer que as entidades administrativas devem estabelecer contratos de parcerias (entre elas), a fim de que as questões políticas de acesso sejam equacionadas em comum acordo.

Em resumo os sistemas são um aglomerado de roteadores interconectados, porém, nessa massa de equipamentos e programas, cada um tem uma designação e função bem específica, que são eles:

1. Roteadores _Peers_
2. Roteadores _Neighbors_
3. Protocolos eBGP
4. Protocolos iBGP

Em um AS todos os roteadores que possuem uma sessão BGP estabelecida são chamados de _**neighbors**_ (vizinhos), porém, quando uma atribuição política é destinado a um determinado roteador, ele recebe a designação de _**peers**_ (pares), pois estes estão situados na borda da rede, executando a interconexão entre os ASs.

No interior da rede, existem roteadores que são vizinhos, mas não de equipamentos de outro AS, mas sim do seu próprio. Neste caso as sessões estabelecidas entre eles acontecem internamente ao AS. O que permite isso é o _**internal**_ BGP (iBGP), que permite a troca de rotas no mesmo sistema.

De forma análoga, a troca de rotas entre ASs é feita pelo _**exterior**_ BGP (eBGP). O algoritmo do eBGP trabalha, basicamente, anunciando as rotas, enquanto o iBGP não anuncia rota alguma. Assim, para fazer o iBGP funcionar adequadamente dentro de um AS, é necessário estabelecer sessões BGP entre todos os roteadores que utilizam o iBGP, formando uma malha completa de sessões iBGP dentro do AS.

Vale ressaltar que no iBGP os  _**neighbors**_ não necessitam estar diretamente conectados através de uma linha serial ou via interface Ethernet, entretanto, os roteadores  _**peers**_ devem estar conectados de forma direta, ou seja, através de  _**link**_ serial ou interface Ethernet (MOURA, 1999). Este conceito está ilustrado na figura 3.

**4. - Sessão BGP**

Conforme já relatado, o BGP faz uso da porta 179 TCP para criar as sessões entre roteadores _**neighbors**_ e _**peers**_ e podem transportar, deste modo, as informações.

Antes do estabelecimento de uma sessão BGP, os roteadores trocam mensagens do tipo _**OPEN**_ entre si, que são enviadas para se iniciar a abertura de uma sessão BGP entre roteadores _**neighbors**_ ou _**peers.**_ Esta mensagem tem como objetivo entrar em comum acordo e trocar os parâmetros entre os _**routers**_ como exemplo: tempo máximo de espera entre mensagens (_**hold time)**_ da sessão e, caso não haja discordância e nem erros durante a negociação dos parâmetros (entre as partes), a sessão BGP é estabelecida, seguindo os seguintes passos:

1. Estabelecer a conexão TCP entre os dois roteadores que trocam mensagens de abertura da sessão e negociam os parâmetros de operação;
2. Transmitir no primeiro fluxo de dados a tabela de rotas BGP completa. Atualizações incrementadas podem ser feitas na tabela, à medida que novas mudanças ocorreram;
3. Manter a informação da versão da tabela que todos os pares do roteador possuem, enquanto durar a sessão entre eles, uma vez que, não há a atualização completa da tabela após a primeira atualização. Se a sessão for interrompida por qualquer motivo, o processo é iniciado novamente a partir do primeiro passo;
4. Enviar mensagens de _keepalive_ periodicamente para manter a sessão aberta, quando não há troca de informações e dados entre os roteadores;
5. Enviar mensagens de aviso quando ocorrem erros ou outras situações especiais;
6. Encerrar a sessão e fechar a conexão, enviando uma mensagem de erro ao verificar um erro no _link_ (MOURA, 1999).

Quando a sessão é estabelecida entre os roteadores, são trocadas todas as informações de roteamento, ou seja, as melhores rotas já selecionadas por cada um dos _**router**_, enviando apenas os melhores caminhos aos seus vizinhos.

Esta tabela será atualizada somente quando houver mudanças nas rotas, como a queda de uma ou o surgimento de novas rotas. Neste caso, mensagens do tipo _**UPDATE**_ irão trazer estas atualizações às tabelas dos _**routers**_. Caso não existam atualizações a serem informadas, os roteadores trocam apenas mensagens tipo _**KEEPALIVE**_ para certificar que a comunicação entre eles está ativa.

A última mensagem BGP é do tipo _**NOTIFICATION,**_ cujo objetivo é informar a detecção de erros durante ou após o estabelecimento de uma sessão BGP. A tabela 2 ilustra as mensagens de erros com seu código primário e o secundário que fazem parte do campo de notificação.

As mensagens trocadas em sessões BGP têm o comprimento máximo de 4.096 bytes, e mínimo de 19 bytes. Todas as mensagens são compostas de, no mínimo, um cabeçalho e, opcionalmente, uma parte de dados. O formato do cabeçalho das mensagens BGP é ilustrado na figura 4. A descrição de cada campo do cabeçalho é a seguinte:

**Campo Marcador**

Serve para verificar a autenticidade da mensagem recebida e se houve perda de sincronização entre os roteadores vizinhos BGP. Caso a mensagem seja do tipo OPEN, ou se a mensagem tipo OPEN não possuir informação de autenticação, o campo deve estar todo preenchido com números um (1); senão, o campo _**marker**_ terá o seu conteúdo baseado em parte do mecanismo de autenticação usado.

**Campo Comprimento**

Deve conter um número que representa o comprimento total da mensagem, incluindo o cabeçalho. Como pode haver mensagens que não possuem dados após o cabeçalho, a menor mensagem BGP enviada é de 19 bytes (16 + 2 + 1 bytes).

**Campo Tipo**

Deve conter um número que representa o código de um tipo de mensagem. Os tipos de mensagens já estudados são: KEEPALIVE, NOTIFICATION, OPEN e UPDATE.

**5. - Conclusão**

- O BGP versão 4 possibilita o intercâmbio de informações de roteamento entre os diversos Sistemas Autônomos, que em conjunto, formam a Internet atual.
- De uma forma simplificada, ele permite que os dados trafeguem entre os ASs até chegar ao AS de destino, e dentro dele siga até o seu destino final (computador).
- Cada Sistema Autônomo é administrado de forma independente por uma organização, porém, todos os ASs seguem regras equivalentes para a perfeita integração na Internet.
- Esta aula demonstrou de forma simplificada e básica os mecanismos de funcionamento da Internet. Para estudos mais abrangentes recomendam-se literaturas especificas, de conotação técnica e de gestão, pois não só basta conhecer os requisitos técnicos, mas o grande segredo são as questões de gerenciamento e administração, sem esquecer as políticas, porque no mundo da Internet, negociações e políticas são as diretrizes de uma boa administração, que deve ser sempre voltada à cooperação e a integração.

**6. - Para refletir.**

1. Um Sistema Autônomo (AS) é um conjunto de roteadores interconectados e administrados por uma única empresa.
2. Existem diversos ASs interconectados de diferentes empresas trabalhando em conjunto, provendo conectividade entre as redes formando a atual Internet.
3. Para identificar todos os AS, foram designados o Número do Sistema Autônomo ou ASN.
4. Todos os AS tem suas próprias políticas internas, porém, existe uma cooperação entre eles para possibilitar o tráfego comum dos dados.
5. Para interconectar todos os ASs em perfeita harmonia foi criado o protocolo BGP que atualmente esta na versão 4.
6. Existem em diversos países órgãos responsáveis pela designação de ASs e pelo fornecimento de bloco de números de _Internet Protocol_ (IPs) a cada AS que terá a responsabilidade para gestão e distribuição destes as empresas e pessoas.
7. O BGP na versão 4 é o protocolo utilizado nas redes que formam a Internet.
8. Os equipamentos roteadores são divididos em dois grupos principais: os roteadores de borda chamados _peers_ e os roteadores de centro denominados _neighbors._
9. Os roteadores _peers_ tem a função política de determinar as regras de acesso ao seu AS e os roteadores _neighbors_ formam a nuvem, conectando diversas redes de empresas e de usuários comuns.
10. O protocolo BGP utiliza uma conexão TCP montando entre os roteadores sessões, tornando as mensagens extremamente seguras.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/6/252662/11614.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/6/252662/11614.jpg)

Figura 2 - Sistema autônomo BGP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/6/252666/11615.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/6/252666/11615.jpg)

Figura 3 - Links em um AS

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/5/252525/11616.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/5/252525/11616.jpg)

Figura 4 - Cabeçalho BGP