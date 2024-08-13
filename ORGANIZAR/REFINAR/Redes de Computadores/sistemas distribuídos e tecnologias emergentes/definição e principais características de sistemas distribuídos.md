No decorrer dos tempos os Sistemas de Computação foram evoluindo em tamanho e tecnologia. Dos gigantes equipamentos que ocupavam salas e salas aos atuais Mainframes, com seus múltiplos processadores e pequenas máquinas, muito se alterou, com relação aos seus componentes, velocidade de processamento, comunicação e compartilhamento de recursos.

Nos pequenos equipamentos, chamados de PC’s (computadores pessoais), desde seu surgimento na Década de 80, também tivemos mudanças e evolução, mas a principal mudança está relacionada com o compartilhamento dos recursos o que só foi possível com o surgimento das redes de computadores de alta velocidade.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287970/16630.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287970/16630.jpg)

Rede de computadores com compartilhamento de recursos.

As Redes Locais – LAN’s (Local-Area-Network) passaram a permitir que diversos equipamentos localizados em um determinado local, compartilhassem suas informações entre si. Dessa mesma forma, as Redes de Longas Distâncias – WAN’s (Wide-Area Networks) permitiram que milhões de máquinas se comunicassem no mundo inteiro.

Quando as redes de computadores começaram a se tornar viável técnica e economicamente, surgiu um grande avanço na criação das arquiteturas de redes.

Como resultado do avanço dessas tecnologias, temos que, atualmente, ficou fácil montar um sistema de computação com grandes quantidades de computadores que se conversam através de uma rede de alta velocidade.

Sistemas Operacionais de Rede permitem compartilhar diferentes recursos de uma determinada estação entre os demais membros da rede. Um dos recursos mais importantes para ser compartilhado é o disco, permitindo que múltiplas estações possam acessar uma única base de dados.

Sistemas Distribuídos não são diferentes dos sistemas em rede, são sistemas fracamente acoplados interconectados por uma rede de comunicação.

Do ponto de vista de um processador específico, os demais processadores e respectivos recursos são remotos, enquanto seus recursos são locais. O propósito de um sistema distribuído é fornecer um ambiente eficiente para o compartilhamento de recursos remotos.

Esses sistemas são denominados de redes de computadores ou _**Sistemas Distribuídos.**_

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287971/16631.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287971/16631.jpg)

Um exemplo de Sistema Distribuído.

Várias são as definições dadas pelos pesquisadores no que se refere aos “Sistemas Distribuídos”, vejamos algumas delas:

_**“Um Sistema Distribuído consiste de um conjunto de processos distintos, espacialmente separados que se comunicam por troca de mensagens”**_

_**Lamport, 1978**_

()

Lamport considera que, qualquer rede de computadores interligados é considerada um Sistema Distribuído.

_**“Sistema Distribuído é um conjunto de processadores que não compartilham memória nem relógio. Os processadores se comunicam por meio de redes de comunicação”**_

Silberschatz, 2000

()

Para Silberschatz, os sistemas distribuídos são mais flexíveis e seus componentes possuem maior autonomia se assemelhando muito a sistemas de rede, porém com o controle de um único Sistema Operacional.

_**“Sistema Distribuído é um conjunto de computadores independentes que se apresenta a seus usuários como um sistema único e coerente”**_

Tanenbaum, 2007

()

Na visão de Tanenbaum os Sistemas Distribuídos são compostos por computadores com autonomia, permitindo que cada um possua seu Sistema Operacional local, fazendo com que seus usuários se sintam trabalhando em um único sistema.

Uma característica desse tipo de sistema diz respeito aos computadores, que independentemente de serem poderosos (Mainframes) ou de pequeno porte (PC’s), está no modo como estes se comunicam, sendo ocultas aos usuários. A outra, diz respeito à maneira consistente e uniforme, na qual usuários e aplicações interagem com o sistema.

O critério básico para esta consideração será a possibilidade de compartilhar recursos entre componentes separados que trabalharão de maneira cooperativa.

As estratégias adotadas para implementar Sistemas Distribuídos depende de diversos fatores, tais como: disponibilização de uma rede de alta velocidade, compartilhamento de recursos, objetivo da aplicação, características e restrições do ambiente, custo do projeto, etc. Aliado a tudo isso, acrescentamos a disponibilização de uma arquitetura de **rede do tipo Cliente-Servidor**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287972/16632.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287972/16632.jpg)

Rede do Tipo Cliente-Servidor

**EXEMPLOS DE SISTEMAS DISTRIBUÍDOS**

**INTERNET**

A flexibilidade e o compartilhamento de recursos entre sistemas separados geograficamente é uma característica dos Sistemas Distribuídos, sendo assim podemos considerar a INTERNET como um Sistema Distribuído.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287990/16652.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287990/16652.jpg)

A Internet e a Comunicação Global.

Do ponto de vista geográfico a Internet representa o mais amplo dos sistemas em rede com maior potencial de compartilhamento de recursos. Apesar de apresentar baixo desempenho, a facilidade de acesso aos recursos e a possibilidade de trabalhar de maneira cooperativa a grandes distâncias torna a Internet um bom exemplo de sistemas distribuídos.

Apesar de suas vantagens, os problemas de comunicação (intrusão e perdas de dados) são evidentes no ambiente da Internet.

**INTRANET**

A Intranet se torna um ambiente alternativo para promover a produtividade em ambiente corporativo ou mesmo residencial. Com uma configuração similar e até possuindo acesso à Internet, sua configuração adequada permite maior segurança e trabalho cooperativo eficiente para os objetivos da empresa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287974/16655.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/7/9/287974/16655.jpg)

Intranet - Ambiente corporativo

**COMPUTAÇÃO MÓVEL**

A computação móvel está intimamente ligada aos computadores portáteis e, portanto, vinculada aos sistemas embarcados. A computação móvel deve possibilitar total mobilidade ao usuário, permitindo liberdade para obter e manipular informação a qualquer hora e em qualquer lugar.

Como característica deste modelo pode-se citar as redes sem fio e os dispositivos portáteis.

**COMPUTAÇÃO UBÍQUA**

Computação Ubíqua é um agrupamento de uma grande quantidade de dispositivos pequenos e baratos que estão presentes no ambiente físico dos usuários, como residência e escritório, além dos dispositivos portáteis.

Apesar de sua semelhança com a computação móvel, na computação ubíqua o usuário é beneficiado quando ele permanece em um único ambiente, como uma biblioteca ou em sua casa, isto é, está presente no ambiente.

De acordo com o Dicionário Michaelis ubíquo significa onipresente; que está ou pode estar em todos os lugares ao mesmo tempo.