### Introdução

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/7/299762/20050.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/7/299762/20050.jpg)

Alta densidade de portas em Fibras Opticas

Depois da digitalização da maioria dos serviços nas telecomunicações, as companhias investem maciçamente na modernização de suas centrais de comutação e em seus links de comunicação.

Não mais que 60 anos atrás, a única opção de comunicação a longas distâncias eram as redes telefônicas, em que a interligação entre suas centrais era feita por cabos de par metálico de altíssima capacidade, com mais de 3.600 pares por cabo, permitindo a conexão de 3.600 conversações telefônicas ao mesmo tempo.Com a modernização dos sistemas, a voz que antes era transmitida de forma analógica passou  a ser digitalizada pelos processos de quantização e os grandes cabos de par metálico foram, gradativamente, sendo substituídos por cabos ópticos. Essa tecnologia de utilização, com sinais luminosos ao invés de sinais elétricos na sua transmissão, pode agora transportar mais de 10.000ligações telefônicas, simultaneamente, em apenas um par de fibras.

A partir desse momento, todos os serviços começaram a ser digitalizados, por exemplo, a voz humana, as imagens e tudo mais analógico, que acabou, por fim, sendo transformado em uma sequência binária.Nessa evolução de sistemas e de tecnologia, quase todos os processos foram melhorados e modernizados, com exceção da rede de distribuição telefônica, conhecida como "rede de última milha".

As redes de acesso ao assinante (última milha), nos últimos anos,transformou-se em um dos maiores problemas enfrentados pelas companhias de telecomunicações, porque o surgimento de novos serviços digitais, como IPTV, Televisão HDTV, Vídeo Conferência, vídeo on-demand e navegação em banda larga pela Internet, encontra nas redes de acesso o seu maior desafio.

As redes são, na sua maioria, formadas por cabos metálicos de pares trançados, que segundo a classificação da normativa ANSI/EIA/TIA 568C classifica estes cabos na categoria três ou simplesmente CAT3. O fato é que estes cabos nesta categoria suportam taxas de transmissão de até 16 Mbits, portanto, o problema não são só dos cabos das redes de acesso, mas sim a forma que elas foram projetas para permitir somente um canal de comunicação de 4 KHz no máximo, ou seja, um canal de voz apenas. As redes de acesso são construídas com filtros e bobinas chamados de pupinização, que mantém somente esse pequeno canal ativo, eliminando as frequências maiores e consequentemente diminuindo a performance do cabo.

**Tecnologia de Rede de Acesso Passive Optical Network (PON)**

Neste panorama de modernização, o que se destaca são as redes PON.

Utilizando uma configuração Ethernet in the First Mile (EFM), com topologia Ponto Multiponto,as redes PON é a melhor escolha pela grande capacidade de transmissão e pela economia em recursos financeiros na sua implementação.

A rede  Ponto Multiponto é, basicamente, formada por um cabo de fibra óptica SM, lançado desde a concessionária de telecomunicações Central Office (OC), conectado a um equipamento de distribuição chamado Optical Line Terminal (OLT), que é o responsável por todos os aspectos de sincronização e interfaceamento dos assinantes.

Esse cabo será lançado até muito próximo a um núcleo de assinantes nos bairros e periferias e, nesse local, o sinal será dividido por um divisor óptico passivo, chamado splitter. Esse artefato pode dividir o sinal principal em até 128 sinais na tecnologia GPON ou em até 32 sinais na tecnologia EPON. Isso significa dizer que, uma única fibra óptica pode atender em até 128 ou 32 assinantes,simultaneamente, com um canal de alta taxa de transmissão totalmente digital, a uma distância de até 20 km das ONTs, cobrindo uma ampla área geográfica.

Uma vez realizada a divisão pelo splitter, uma nova fibra óptica SM será lançada até o interior da moradia do assinante. Nela será instalado o equipamento receptor chamado Optical Network Terminal (ONT), responsável pela codificação e separação dos sinais de Internet banda larga, televisão HD e telefone VoIP.

**ASSISTA AO VÍDEO**

[**https://youtu.be/qhhzZCzXDSE**](https://youtu.be/qhhzZCzXDSE)

**Optical Line Terminal (OLT)**

Equipamento responsável pela viabilização dos serviços para os assinantes, tendo também como função o controle e a qualidade do serviço QoS e o SLA. A OLT é o elemento que realiza a multiplexação dos diferentes usuários na fibra óptica.A primeira geração de PONs operava de forma muito semelhante ao Time Division Multiplexing (TDM), em que a banda era alocada definitivamente para o usuário, uma vez que colocada era impossível sua utilização por outro. Com a evolução das gerações de PONs, a alocação de banda se tornou dinâmica. A reutilização da banda nos métodos de operação por meio da alocação dinâmica considera o perfil do tráfego. O método de alocação e operação considera também as políticas de QoS e SLAs configuradas para cada assinante.A OLT interliga as ONUs através da técnica WDM na qual todas as informações são transmitidas em uma única fibra, em dois comprimentos de onda diferentes, um de 1490 nm para as informações de baixada (downstream), e outro de 1510 nm para as informações de subida (upstream).A informação do canal de distribuição é transmitida em modo broadcast, isto é, para todos os elementos da rede. Como a informação chega a todos os usuários, se faz necessário utilizar um sistema de criptografia para manter a privacidade das comunicações. As informações de retorno, ou seja, no sentido do assinante para a rede, os dados são transmitidos utilizando o protocolo de acesso múltiplo TDMA, em que cada elemento da rede tem um período de tempo específico para sua transmissão, permitindo que um mesmo canal e seu comprimento de onda sejam compartilhados por vários assinantes.

**Optical Network Unit (ONU)**

Este equipamento é simples e sua função é converter o sinal óptico da OLT para as portas padrões dos equipamentos de aplicação do assinante, como porta Ethernet, porta de voz e porta de vídeo.A tecnologia PON foi projetada para evitar os altos custos de conexões ópticas Ponto a Ponto para cada site, condomínio, residência etc. A alta capacidade de banda de um sinal ótico de uma única fibra é enviada para um ou mais divisores passivos (splitters) e retransmitido para múltiplos equipamentos ONUs. Todos os ONUs transmitem e recebem sinais em canal próprio, com banda dinamicamente alocada e QoS e SLAs individuais. A inteligência da operação da OLT avalia os QoS e SLAs individuais e a disponibilidade do segmento PON que ele opera, então, é aplicada a alocação dinâmica de banda bem como a viabilidade do compartilhamento desse segmento PON.

**Tecnologia de Redes EPON e GPON**

As instalações de redes PON continuam crescendo a cada dia, principalmente no Japão, Coréia,Estados Unidos e Europa, que, atualmente, quase ultrapassou a rede de par metálico. As instalações das redes ópticas passivas encontram-se divididas em dois tipos principais, a Ethernet PON (ou EPON), instalada no Japão e Coréia, e a GPON, nos EUA e Europa. As principais características e diferenças desses dois modelos são apresentadas a seguir:

**Comparativo entre EPON e GPON**

Basicamente as duas tecnologias são bastante parecidas nos aspectos físicos e  de instalação,consideradas FTTH – Fibra to the Home, e ambas utilizam a tecnologia passiva de divisão de sinais.

Como são duas tecnologias, é obvio que temos também dois grupos muito dispostos a defender seus interesses e sua técnica. Os promotores das redes GPON argumentam que o padrão está a mais tempo no mercado, logrando assim a maturidade pelas várias versões e up-grade apresentados, enquanto o padrão EPON ainda é bastante novo e passivo de aperfeiçoamento.

Em contrapartida, os defensores das redes EPON citam que a maioria do tráfego das redes espalhadas pelo mundo começa e termina com tráfego IP e Ethernet.

Então, qual a razão para interpor mais um protocolo de encapsulamento nas redes?

Em resumo, o que irá determinar qual das duas tecnologias deve ser instalada dependerá de um vasto estudo realizado pelas concessionárias, para as quais os fatores determinantes são o custo de implantação, desempenho da tecnologia, eficiência na razão da divisão do sinal e, principalmente,custos de manutenção com pessoal de retaguarda altamente capacitado.

**Diferenças básicas entre EPON e GPON**

**ASSISTA AO VÍDEO**

[**https://youtu.be/ib8YbxGhalA**](https://youtu.be/ib8YbxGhalA)

Os aspectos mais determinantes que mostram as diferenças entre as duas tecnologias diz respeito à arquitetura disponibilizada para cada uma.

A tecnologia GPON fornece redes complexas em topologia de árvores da camada 2, do modelo de referência OSI, com base no protocolo ATM e múltiplos protocolos para suportar e executar a conversão. Enquanto isso, a tecnologia EPON usa simples redes da camada 2, utilizando o protocolo IP para dados, voz e vídeo.

A GPON, empregando o protocolo ATM, necessita gerar circuitos virtuais que são providenciados por diferentes tipos de serviços e enviados para os assinantes.

Essa técnica para transporte oferece um serviço de alta qualidade, pois, para cada aplicação específica, são gerados circuitos virtuais condizentes. Em contrapartida, os equipamentos da rede GPON precisam de algumas conversões de protocolos, segmentação, terminação do canal virtual e o encapsulamento no protocolo PPP. Resumidamente, a estrutura GPON consiste em múltiplas redes da camada 2 sobre a mesma rede da camada física, e cada rede com um protocolo diferente.

A tecnologia EPON, por outro lado, é bem mais simples, pois fornece conectividade para qualquer tipo de rede com base no protocolo IP, dispensando todo o aparato que a tecnologia GPON necessita, referente às conversões e encapsulamento.

Como as redes Ethernet dominam quase na sua totalidade as redes espalhadas pelo mundo,nas locais, metropolitanas e até mesmo em backbones de redes internacionais, a tecnologia EPON pode ser rapidamente implementada e gerenciada a um custo muito inferior ao do seu concorrente GPON.

**Largura de banda**

A tecnologia GPON oferece taxa de transmissão assimétrica, de 1,25 Gbps ou 2,5 Gbps de downstream, e taxas escaláveis de upstream a partir de 155 Mbps até 2,5 Gbps. Seu rival, a tecnologia EPON, oferece taxa simétrica (descida e subida iguais) a 1,25 Gbps, no máximo.

**Alcance**

Ambas as tecnologias podem alcançar aproximadamente 20 km medidos desde a OLT até a ONU. Esse valor é calculado linearmente e devem ser considerados todos os aspectos do trajeto.

**Fator de divisão "splitagem"**

A tecnologia GPON pode suportar até 128 ONU por OLT, ou seja, uma divisão de 1:128. A tecnologia EPON oferece uma divisão máxima de 32 ONU por OLT ou uma divisão de 1:32. Em alguns casos especiais, em que se diminui drasticamente a distância e aumenta a potência do laser, pode-se chegar em até 64 assinantes.

Sistema de Gerenciamento A tecnologia EPON requer um simples sistema de gerenciamento, enquanto a GPON demanda três, para os três protocolos de camada 2 que necessita.

Consequentemente, a EPON é muito mais econômica em sua implementação do que a GPON,além de necessitar de quadro técnico altamente especializado para essa função.

**Segurança e Proteção**

A tecnologia GPON utiliza criptografia Advanced Encryption Standard (AES) no sentido downstream apenas. Na tecnologia EPON o mecanismo de criptografia ainda não foi definido pelo padrão, tornando os fornecedores incompatíveis, pois alguns fabricantes utilizam também o AES nos dois sentidos, mas como não foi padronizado, nem todos usam, tornando a tecnologia proprietária até o momento.

Quantidade de Assinantes

O padrão EPON suporta dois tipos de ONUs, o A, no qual a perda do sinal pode variar entre 5 dB até 20 dB, e o B, no qual a perda máxima varia de 10 dB a 25 dB, oferecendo serviços de conexão até 32 usuários, tipicamente.

O padrão GPON suporta também ONUs do tipo C, no qual a perda de sinal varia de 15 dB a 30 dB. O tipo C permite estender a rede além dos 20 km, diminuindo assim a quantidade de assinantes para no máximo 64 por PON.

**Revisando ...**

Com as necessidades de maior banda nas conexões digitais as redes de par metálico deverão ser gradativamente substituídas pelas redes em tecnologia PON.

A tecnologia PON permite que apenas uma única fibra possa ser dividida e seu sinal em um grande número de usuários.

As tecnologias que vem se destacando na PON são a GPON e a EPON.A tecnologia GPON utiliza várias redes e protocolos com base na camada 2 do modelo de referencia OSI e trabalha basicamente com o ATM. A tecnologia EPON trabalha apenas com IP e pode transportar qualquer informação com base em IP.

A tecnologia EPON pode oferecer uma divisão de até 32 assinantes por fibra, enquanto que a tecnologia GPON oferece até 128 usuários por fibra.

A GPON está a mais tempo no mercado e consegue atender melhor às necessidades dos assinantes, porém, perde nos requisitos de implantação, gerenciamento e manutenção. Já a tecnologia EPON é bastante simples e os custos para sua implementação e manutenção são bem inferiores ao seu concorrente.