**Introdução**

Um Data Center deve ser o local com o maior nível de segurança dentro de uma organização, um local à parte da edificação, cuja função principal é abrigar uma sala de equipamentos (ER) que executa serviços de missão crítica.

Entende-se como serviço de missão crítica aplicativos e ambientes de alta tecnologia, construídos para evitar a paralisação das atividades computacionais e a perda de dados importantes de uma empresa ou um negócio. Para isso, a TIA 942 especifica diversas diretrizes da construção do cabeamento que será instalado no seu interior, fornecendo total redundância de rotas e vias de altíssima velocidade e com possibilidades de crescimento escalonado.

**Concepção de um projeto de Data Center**

Ao se projetar um Data Center, uma série de questões deverão ser analisadas e não somente o cabeamento. Deve-se levar em consideração, em primeiro lugar, a necessidade de espaços e expansão do local, o fornecimento de energia elétrica com redundância, sistemas de climatização redundantes, sistemas de segurança e controle de acesso, sistemas de aterramento e serviços especializados de conexão externa também com redundância.

Um Data Center é considerado conforme seu nível de disponibilidade de serviços, sendo dividido em quatro níveis, conforme descrito pelo Uptime Institute, são eles:

- Tier 1 – Indisponibilidade menor que 28 horas e 48 minutos por ano.
- Tier 2 – Indisponibilidade menor que 22 horas por ano.
- Tier 3 – Indisponibilidade menor que 1 hora e 36 minutos por ano.
- Tier 4 – Indisponibilidade menor que 24 minutos por ano.

Conforme a não necessidade de indisponibilidade dos serviços, classificam-se os Data Centers de acordo com o aumento de seu nível de "Tier", aumenta-se também seus níveis de redundância aplicados aos equipamentos, energia elétrica, pessoal especializado, serviços de telecomunicações, entre outros.

Comentando sobre energia elétrica, um Data Center de nível Tier 4 deverá ter como sistemas de fornecimento de energia dois equipamentos do tipo No-Break, com seus redundantes equipamentos em espera no caso de falha de um deles e estes alimentados por duas subestações de energia elétrica com entradas e fiação diferentes na edificação.

Em cada ramificação de entrada elétrica, um sistema de grupo gerador elétrico movimentado por óleo diesel ou gás deverá ser instalado, garantindo o fornecimento constante de energia elétrica ao referido espaço.

Os sistemas de No-Break devem ser intervalados, ou seja, no caso de pane de um, o seu equipamento redundante assumirá imediatamente, sem que ocorra a paralisação de nenhum serviço especializado.

Essa redundância também deverá ser aplicada a todos os componentes utilizados para a construção do Data Center, que vão desde as entradas elétricas diferentes até o nível de servidores, equipamentos de conectividade tipo Switchs e, principalmente, o cabeamento.

A norma TIA 942 faz referência a diversas outras normas, entre elas a ANSI/TIA/EIA-568, ANSI/TIA/EIA-569 e a ANSI/TIA/EIA-606 já estudadas anteriormente.

Ela divide o cabeamento no interior do Data Center em diversas subáreas descritas e ilustradas a seguir como:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105015/a18i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105015/a18i01_cabestru80_100.jpg)

http://www.tiaonline.org" role="complementary" tabindex="0">Fonte: [**http://www.tiaonline.org**](http://www.tiaonline.org/)

- MDA – Área de Distribuição Principal
- HDA – Área de Distribuição Horizontal
- EDA – Área de Distribuição de Equipamentos
- Entrance Room – Sala de Entrada
- Telecom Room – Sala de Telecomunicações
- Offices, Operations Center – Sala de Operações e Suporte

**Áreas do Data Center**

**MDA – Área de Distribuição Principal**

Esta área é o ponto central do cabeamento estruturado do Data Center e deve abrigar os patch panels, DIOs e blocos principais do cross connect, os equipamentos switch e roteadores CORE de grande porte, permitindo assim, manobras de portas e serviços de forma central, rápida e organizada.

Para abrigar o MDA, utiliza-se normalmente racks do tipo torre (abertos) de 44UAs de altura e guias verticais e horizontais de alta densidade, o que possibilita um grande número de cabos de manobra, patch cords e line cords de cobre e ópticos. A figura a seguir exemplifica um rack tipo torre de alta densidade.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105016/a18i02_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105016/a18i02_cabestru80_100.jpg)

**HDA – Área de Distribuição Horizontal**

É um espaço situado entre o MDA e o EDA, ou seja, área de distribuição entre os equipamentos de conectividade principais e os servidores.

Sua principal função é a redução da quantidade de cabos entre esses dois equipamentos, pela instalação de equipamentos do tipo switches intermediários ou como nas salas de TR, instalados os equipamentos de borda que farão a conectividade com os servidores.

É comum também nesta área a instalação de switches do tipo KVM que permitem com apenas um teclado, mouse e monitor controlar e gerenciar diversos servidores.

Neste espaço são instalados racks fechados (gabinetes) com altura de 44UAs e portas de metal perfuradas para permitir a circulação de ar, conforme ilustrado na figura a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105017/a18i03_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105017/a18i03_cabestru80_100.jpg)

**EDA – Área de Distribuição de Equipamentos**

A Área de Distribuição de Equipamentos é o local em que se localizam os equipamentos responsáveis pelo fornecimento dos serviços para os usuários de uma rede. Entre eles destacam-se os servidores, sistemas de backup, sistemas de armazenamento e storages e sistemas de fitas Date.

Esses equipamentos também são montados em racks do tipo gabinete com portas de metal perfuradas para permitir a circulação de ar no seu interior.

Entre o HDA e o EDA é possível a criação de pontos de consolidação conhecidos como ZDA (Zone Distribution Área), que tem a função igual a do CP – Ponto de Consolidação, que permite mudanças mais rápidas e fáceis nos racks da EDA.

**Entrance Room – Sala de Entrada**

É uma área específica, idêntica à Entrada de Facilidades, que vai permitir a entrada dos serviços das operadoras de telecomunicações e concessionárias.

Também é utilizada muitas vezes para fazer a conexão entre o Data Center e os edifícios correspondentes por meio do seu backbone horizontal.

Conhecido como ponto de demarcação, a Entrance Room é o local em que todas as operadoras de telecomunicações disponibilizam seus serviços em equipamentos devidamente montados em racks particulares e não compartilhados entre elas.

**Telecom Room – Sala de Telecomunicações**

Essas áreas contêm o cabeamento que irá suportar as áreas externas à sala de computadores e poderá estar alojada na própria sala de computadores ou em outro espaço separado.

Nessa sala estão instalados os switches KVM e os equipamentos que fornecem conexão para os equipamentos na área de suporte e supervisão.

**Offices, Operations Center – Sala de Operações e Suporte**

Esse espaço é reservado ao pessoal administrativo, de suporte e operação a todos os equipamentos instalados no interior do Data Center.

Esse espaço deve conter os computadores com seus respectivos operadores e diversos painéis de controle e alarme das operações que vão sendo processadas no interior da sala de computadores, conforme ilustrado na figura a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105019/a18i04_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105019/a18i04_cabestru80_100.jpg)

**Distribuição dos Cabos**

A distribuição dos cabos no interior do Data Center, sejam eles de cobre ou cabos ópticos, respeita a premissa da redundância completa no estilo estrela estendida.

Isso significa dizer que, partindo do MDA em direção aos HDAs, um grupo de cabos (cobre e ópticos) deve atender a todos os racks instalados e com possibilidade de interligação com cabos de racks de HDA entre si.

Dos racks HDA também devem partir cabos em direção aos EDAs, nas mesmas características apresentadas, ou seja, os racks devem ser atendidos pelos cabos vindo do rack em que estão alocados seus equipamentos ou por outros racks, formando caminhos secundários e até terciários de rotas.

Note que essa configuração somente será possível quando se tem a interligação também de racks do EDA entre si, montando assim uma topologia em estrela estendida e esses racks devem ser interligados entre si formando uma segunda rota, caso o cabo primário venha a sofrer alguma interrupção.

Como elementos de interligação, a normativa [**TIA 942**](https://ava.uninove.br/seu/AVA/topico/topico.php) reconhece os seguintes elementos:

- Cabos de par trançado, blindados ou não, categoria 6 ou 6A.
- Cabos coaxiais de 75 ohms.
- Cabos de fibra óptica multímodo 62,5/125 micron ou 50/125 micron com forte recomendação às fibras de 50/125 micron otimizadas para aplicações laser a 850nm.
- Cabos de fibra óptica monomodo otimizadas ou zero pico d?água.

Todos os cabos devem seguir as recomendações referentes à classe de flamabilidade, e no Data Center são admitidos cabos do tipo UTPs dos tipos CM, CMR e CMP respectivamente: cabos de pares metálicos para uso geral, cabos de pares metálicos Riser (instalados na vertical) e cabos de pares metálicos Plenum ou LSZH (low smoke zero halogen).

Para as fibras ópticas são admitidos os cabos do tipo COG, COR, COP e LSZH respectivamente: cabos ópticos de uso geral uso interno, cabos ópticos Riser, cabos ópticos Plenum ou os cabos LSZH (low smoke zero halogen).

Apesar das normas admitirem os cabos CM, recomenda-se fortemente a utilização de cabos Plenum ou LSZH.

A flamabilidade dos cabos utilizados nas redes de computadores segue a classificação do laboratório UL (Underwriters Laboratories, Estados Unidos), que é reconhecida e utilizada no mundo todo. Essa ordem de classificação, que está definida segundo o grau de flamabilidade, fumaça e emissão de gases tóxicos são:

- CMP – Plenum Communication Cable – desenvolvido para operar em instalações com a presença de fluxo de ar forçado, locais com grande demanda de pessoas, como aeroportos, hospitais, teatros e qualquer outro local em que haja concentração de população.
- CMR – Riser Communication Cable – projetado para operar em locais confinados, sem fluxo de ar forçado, de forma vertical de instalação como shafts etc.
- CMG ou CM – General Purpose Communication Cable – cabo de uso geral com pouca proteção contra incêndios, devendo ser instalado em localidades com baixa população de pessoas e em locais sem fluxo de ar forçado.
- CMX – Communication Cable, Limited Use – Cabo para uso limitado, em locais protegidos, sem fluxo de ar forçado e baixa densidade de pessoas.

Temos ainda os cabos LSZH (Low Smoke Zero Halogen), que são a melhor escolha para locais com altíssima densidade populacional e com fluxo de ar forçado, sendo adequados para hospitais, teatros, aeroportos, cinemas e todo e qualquer local com confinamentos de pessoas e cabos expostos, pois estes emitem pouca fumaça e nenhum gás tóxico.