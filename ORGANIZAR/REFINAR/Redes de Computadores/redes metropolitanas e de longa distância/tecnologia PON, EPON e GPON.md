**1. INTRODUÇÃO**

A Norma IEEE 802.3ah – _**Ethernet in the First Mile**_ (EFM) lançada em 2004 trata do fornecimento de um sinal Ethernet para acesso aos assinantes em alta velocidade e com total segurança. Atualmente as tecnologias existentes utilizam os pares de metal da rede de telefonia convencional, sujeito às vicissitudes deste meio físico, já bastante antigo e com sérias restrições tecnológicas.

O crescimento do uso da Internet com novos _**home offices**_, sistemas de videoconferência, telefonia IP e navegação com acesso rápido levaram as atuais tecnologias de acesso de última milha a sua exaustão e colapso, pois, o meio utilizado não suporta altas velocidades com segurança e degradação. Neste panorama vem surgindo também o fornecimento de rádio e televisão pela Internet, o IPTV que veio a contribuir de forma negativa para o aumento da banda de consumo e a total incapacidade do meio atual de fornecer adequadamente o serviço.

Neste ínterim surge a tecnologia EFM que promete fornecer uma infraestrutura capaz de atender a todas estas demandas, onde o ponto fraco desta antiga conexão era entre o assinante e seu provedor de acesso, passando pela rede telefônica convencional. O EFM propõe a instalação de redes totalmente ópticas, passando por ruas e avenidas na expectativa do fornecimento em alta velocidade ao usuário final. Neste contexto o EFM compõem as seguintes soluções:

- Ponto a ponto em fibra óptica;
- Ponto multiponto em fibra óptica.

Os tipos de acessos proposto pelo EFM são baseados na tecnologia FTTx, onde a letra “x” é uma variação dos diferentes tipos de assinantes que podem receber esta conexão. Os modelos implementados são:

- _FTTB – Fiber to the Building;_
- _FTTA – Fiber to the Apartament;_
- _FTTH – Fiber to the Home._

**2. Tipos de Acesso**

**2.1** _**Fiber to the Building**_ **(FTTB)**

Neste tipo de acesso a rede óptica parte da concessionária de telecomunicações e terminará na entrada de um edifício comercial.

Este percurso ótico finaliza na rede _**drop**_ do assinante e deverá ser encaminhada a _**Entrance Facility**_ do edifício, que é o ponto no qual é feita a interface entre o cabeamento externo (provedores de serviço e interligação de campus) e a infraestrutura de telecomunicações interna ao edifício.

A partir desta finalização o acesso interno dos usuários é realizado através de uma rede de par metálico em tecnologia de cabeamento estruturado e, consequentemente, este acesso não será mais de responsabilidade da companhia de telecomunicações que forneceu à conectividade a rede, mas sim do pessoal interno responsável pela manutenção da rede de _**cabling**_.

A solução FTTB não determina se o cabeamento óptico externo que é de responsabilidade da concessionária de telecomunicações será lançado no formato ponto a ponto ou ponto multiponto. Sendo que existem diferenças significativas nas questões de valores e de banda passante entre estes dois modelos que ainda estudaremos.

**2.2** _**Fiber to the Apartament**_ **(FTTA)**

Nesta modalidade de arquitetura de fornecimento de acesso óptico, a rede de transmissão adentra ao edifício comercial ou residencial chegando a uma sala especial de equipamentos (não necessariamente é uma _**Entrance Facility**_, mas é recomendado quando este local existe na edificação).

A partir desta sala o sinal principal óptico é dividido através de divisores ópticos e encaminhado um cabo para cada apartamento ou sala comercial do prédio.

As divisões internas podem ser muitas, mas cada apartamento receberá no seu interior uma única e exclusiva fibra óptica.

Dependendo da quantidade de divisões e do projeto a ser implementado na edificação, questões de banda passante para cada ponto de acesso pode ser comprometido, pois em realidade, só existe uma fibra óptica entrando no prédio, e partir desta, o sinal óptico será dividido ocasionando a diminuição da banda passante total do cabo pelo compartilhamento do meio.

**2.3** _**Fiber to the Home**_ **(FTTH)**

Nesta opção de topologia a rede FTTH a rede de transmissão óptica adentra à residência do assinante e por meio desta todas as facilidades de conectividade são oferecidas.

Esta instalação é realizada pela migração do cabo _**drop**_ de descida da concessionária, para uma fibra de uso interno, através de uma emenda óptica pelo processo de fusão e a instalação de uma caixa de bloqueio óptico.

Esta migração se faz necessária devido o cabo _**drop**_ ser do tipo “geleado”, ou seja, o seu interior é preenchido por uma geleia de petróleo com propriedades de evitar a umidade e dar maior segurança mecânica no lançamento do mesmo. Em caso de propagação de incêndio, a migração dos cabos e a passagem pela caixa de bloqueio não permitirá que as chamas continuem fazendo do cabo um estopim.

A solução FTTH não especifica também se o cabeamento óptico, que parte da concessionária, será ponto a ponto ou ponto multiponto, porém, por uma condição financeira não seria interessante à instalação de uma única fibra para cada residência, devido aos altos custos deste investimento.

A opção mais viável financeiramente é a solução ponto multiponto, onde uma única fibra será dividida em várias outras na rede _**drop**_ de descida, já muito próxima do assinante.

**3. Topologia Ponto a Ponto**

Esta topologia pretende levar uma fibra óptica do tipo SM até um ponto de demarcação em um local centralizado dos assinantes e deste ponto de demarcação levar uma fibra óptica também SM para cada ambiente, seja ele uma empresa, casa ou prédio. A transição no ponto de demarcação (de uma única fibra que vem da concessionária para várias fibras que irão atender os assinantes) é feita por um equipamento terminal óptico de rede.

O grande problema desta solução é a instalação de um equipamento ativo em local externo, com problemas de temperatura, vandalismo e demais situações.

Nesta solução, cada assinante recebe uma fibra óptica advinda diretamente deste ponto de demarcação numa configuração estrela, e a alimentação lógica e de conectividade com a Internet é fornecida pelo cabo que vem lançado desde a concessionária. Também nesta situação o _**link**_ principal deverá ser compartilhado com todos os assinantes e suas aplicações. A figura 1 ilustra esta topologia.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259087/13367.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259087/13367.jpg)

Figura 1 - Rede FTTx ponto a ponto.

**4. Topologia Ponto Multiponto**

Esta arquitetura tem como objetivo suportar a tecnologia _**Passive Optical Network**_ (PON). Esta solução consiste basicamente da instalação de um equipamento na concessionária de telecomunicações denominado de Optical Line Terminal (OLT). Este equipamento pode suportar várias linhas de assinante dependendo da configuração e da tecnologia empregada. Nas redes PON que será assunto de nossa próxima aula, em uma única fibra partindo da concessionária e, vários assinantes podem ser conectados onde a divisão desta fibra acontece (de forma passiva), isto é, sem a necessidade da utilização de equipamentos ativos no trajeto conforme a solução ponto a ponto.

Nesta relação de divisão existe uma economia muito grande em cabeamento e infraestrutura de suporte, portanto, a rede em topologia ponto multiponto com a tecnologia PON vem ganhando espaço em substituição gradativa das redes metálicas utilizadas na telefonia convencional. A grande vantagem da tecnologia PON é que ela é totalmente digital, podendo suportar todas as mídias existentes hoje como telefonia IP, televisão IP, HDTV, Televisão _**on-demand**_, vídeo conferência em _**real time**_ e acesso em alta velocidade à Internet. A figura 2 ilustra uma rede ponto multiponto com tecnologia PON.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259088/13368.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259088/13368.jpg)

Figura 2 - Topologia ponto a multiponto

**5. Motivação da tecnologia PON**

Depois da digitalização da maioria dos serviços nas telecomunicações, as companhias investiram maciçamente na modernização das suas centrais de comutação e em seus _**links**_ de comunicação. Não mais que 60 anos atrás, a única opção de comunicação a longas distâncias eram as redes telefônicas, onde a interligação entre suas centrais se fazia por cabos de par metálico de altíssima capacidade, com mais de 3.600 pares por cabo, o que permitia a conexão de 3.600 conversações telefônicas ao mesmo tempo.

Com a modernização dos sistemas, a voz que antes era transmitida de forma analógica passou a ser digitalizada pelos processos de quantização e os grandes cabos de par metálico foram gradativamente sendo substituídos por cabos ópticos. Esta tecnologia de utilização com sinais luminosos ao invés de sinais elétricos na sua transmissão pode agora transportar mais de 10.000 ligações telefônicas simultaneamente em apenas um par de fibras.

A partir deste momento, todos os serviços começaram a ser digitalizados, como exemplo, a voz humana, as imagens e tudo mais analógico, que acabou por fim, sendo transformado em uma sequencia binária. Nesta evolução de sistemas e de tecnologia, quase todos os processos foram melhorados e modernizados, com exceção da rede de distribuição telefônica, conhecida como “rede de última milha”.

As redes de acesso ao assinante (última milha) nos últimos anos, se transformou em um dos maiores problemas enfrentados pelas companhias de telecomunicações, porque o surgimento de novos serviços digitais como IPTV, Televisão HDTV, Vídeo Conferencia, vídeo _**on-demand**_ e navegação em banda larga pela Internet encontra nas redes de acesso o seu maior desafio.

As redes são na sua maioria formadas por cabos metálicos de pares trançados categoria 3, que segundo a normativa ANSI/EIA/TIA 568C classifica estes cabos como sendo de categoria três ou simplesmente CAT3. O fato é que cabos de par trançado desta categoria suportam taxas de transmissão de até 16 Mbits. Portanto, o problema não são os cabos das redes de acesso, mas sim, a forma que elas foram projetas para permitir somente um canal de comunicação de 4 KHz no máximo, ou seja, um canal de voz apenas. As redes de acesso são construídas com filtros e bobinas de pupinização, que mantém somente este pequeno canal ativo.

As soluções paliativas da utilização da rede de acesso com soluções do tipo ADSL ou Linha Digital de Assinante para acesso à banda larga, logo se tornarão ineficientes, porque a demanda por maior largura de banda vem crescendo dia a dia com o surgimento de novos serviços digitais.

Neste contexto as fibras ópticas surgem como uma boa alternativa para atender o aumento de demanda das redes de acesso. A instalação de novos cabos ópticos irá gradativamente substituir as redes de par metálico. Com a obrigatoriedade de dotar todos os edifícios e urbanizações com instalações de fibra óptica, devido ao Decreto-Lei 123/2009, muitas empresas de telecomunicações estão amplamente empenhas nestas novas redes de acesso, que muito em breve irá fornecer ao assinante de um canal óptico de alta taxa de transmissão.

**6. Tecnologia de Rede de Acesso** _**Passive Optical Network**_ **(PON)**

Utilizando uma configuração _**Ethernet in the First Mile**_ (EFM) com topologia Ponto Multiponto, as redes PON são a melhor escolha pela grande capacidade de transmissão e pela economia em recursos financeiros na sua implementação.

A configuração Ponto Multiponto é basicamente formada por um cabo de fibra óptica SM que é lançado desde a concessionária de telecomunicações _**Central Office**_ (OC)_**,**_ conectado a um equipamento de distribuição chamado _**Optical Line Terminal**_ (OLT), que é o responsável por todos os aspectos de sincronização e interfaceamento dos assinantes.

Este cabo será lançado até muito próximo a um núcleo de assinantes nos bairros e periferias e, neste local, o sinal será dividido por um divisor óptico passivo chamado de _**splitter.**_ Este artefato pode dividir o sinal principal em até 128 sinais na tecnologia GPON ou em até 32 sinais na tecnologia EPON. Isso significa dizer que, uma única fibra óptica pode atender em até 128 ou 32 assinantes simultaneamente, com um canal de alta taxa de transmissão totalmente digital, a uma distância de até 20 km das ONTs, cobrindo uma ampla área geográfica.

Uma vez realizado a divisão pelo _**splitter**_, uma nova fibra óptica SM será lançada até o interior da moradia do assinante. Nesta localidade será instalado o equipamento receptor chamado de _**Optical Netowrk Terminal**_ (ONT), responsável pela codificação e separação dos sinais de Internet banda larga, televisão HD e telefone VoIP. A figura 3 ilustra uma rede em modalidade Ponto Multiponto com características PON.

Os dois equipamentos principais da rede PON são a OLT e o ONU descritos a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259089/13369.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259089/13369.jpg)

Figura 3 - Topologia PON - Ponto a multiponto

**6.1** _**Optical Line Terminal**_ **(OLT)**

Equipamento responsável pela viabilização dos serviços para os assinantes tendo também como função o controle e a qualidade do serviço QoS e o SLA. A OLT é o elemento que realiza a multiplexação dos diferentes usuários na fibra óptica.

A primeira geração de PONs operava de forma muito semelhante ao _**Time Division Multiplexing**_ (TDM)_**,**_ onde a banda era alocada definitivamente para o usuário, uma vez que a banda fosse alocada era impossível a utilização desta banda por outro usuário. Com a evolução das gerações de PONs, a alocação de banda se tornou dinâmica. A reutilização da banda nos métodos de operação através da alocação dinâmica considera o perfil do tráfego. O método de alocação e operação considera também as políticas de QoS e SLAs configuradas para cada assinante.

A OLT interliga as ONUs através da técnica WDM onde todas as informações são transmitidas em uma única fibra em dois comprimentos de onda diferentes, um comprimento de 1490 nm para as informações de baixada (_**downstream**_), e outro comprimento de onda de 1510 nm para as informações de subida (_**upstream**_).

A informação do canal de distribuição é transmitida em modo _**broadcast**_, isto é, a informação é transmitida para todos os elementos da rede. Como a informação chega a todos os usuários se faz necessário utilizar um sistema de criptografia para manter a privacidade das comunicações. As informações de retorno, ou seja, no sentido do assinante para a rede, os dados são transmitidos utilizando o protocolo de acesso múltiplo TDMA, onde cada elemento da rede tem um período de tempo especifico para sua transmissão, permitindo que um mesmo canal de transmissão e seu comprimento de onda sejam compartilhados por vários assinantes.

**6.2** _**Optical Network Unit**_ **(ONU)**

Este equipamento é simples e sua função é converter o sinal óptico da OLT para as portas padrões dos equipamentos de aplicação do assinante, como Porta Ethernet, porta de voz e porta de vídeo. A tecnologia PON foi projetada para evitar os altos custos de conexões ópticas Ponto a Ponto para cada site, condomínio, residência, etc. A alta capacidade de banda de um sinal ótico de uma única fibra é enviada para um ou mais divisores passivos (_**splitters)**_ e retransmitido para múltiplos equipamentos ONUs. Todos os ONUs transmitem e recebem sinais em um canal próprio e com banda dinamicamente alocada e QoS e SLAs individuais. A inteligência da operação da OLT avalia os QoS e SLAs individuais e a disponibilidade do segmento PON, que ele opera e, então, é aplicada a alocação dinâmica de banda bem como a viabilidade do compartilhamento deste segmento PON. A figura 4A ilustra a técnica da utilização de comprimento de onda bidirecional no sentido de descida e a figura 4B o tráfego de subida.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/9/270991/13373_2.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/9/270991/13373_2.jpg)

Figura 4A e 4B - Tráfego na Rede PON

**7. Tecnologia de Redes EPON e GPON**

As instalações de redes PON no mundo continuam crescendo a cada dia, principalmente no Japão, Coréia, nos Estados Unidos e na Europa atualmente ela quase que ultrapassou a rede de par metálico. As instalações das redes ópticas passivas encontram-se divididas em dois tipos principais, a Ethernet PON (ou EPON) instalada no Japão e Coréia, e a GPON nos EUA e Europa. As principais características e diferenças destes dois modelos são apresentadas a seguir:

**7.1 Comparativo entre EPON e GPON**

Basicamente as duas tecnologias são bastante parecidas nos aspectos físicos e de instalação, as duas são consideradas FTTH – _**Fibra to the Home**_ e ambas utilizam a tecnologia passiva de divisão de sinais.

Como temos duas tecnologias, é obvio que temos também dois grupos muito dispostos a defender seus interesses e sua técnica. Enquanto os promotores das redes GPON argumentam que o padrão está há mais tempo no mercado, logrando assim a maturidade pelas várias versões e _**up-grade**_ apresentados enquanto o padrão EPON ainda é bastante novo e passivo de aperfeiçoamento.

Em contrapartida, os defensores das redes EPON citam que a maioria do tráfego das redes espalhadas pelo mundo começa e termina com tráfego IP e Ethernet. Então qual razão para interpor mais um protocolo de encapsulamento nas redes?

Em resumo, o que irá determinar qual das duas tecnologias deve ser instalada dependerá de um vasto estudo realizado pelas concessionárias, onde os fatores determinantes são o custo de implantação, desempenho da tecnologia, eficiência na razão da divisão do sinal e principalmente custos de manutenção com pessoal de retaguarda altamente capacitado.

**8. Diferenças Básicas entre EPON e GPON**

Os aspectos mais determinantes que mostram as diferenças entre as duas tecnologias diz respeito à arquitetura disponibilizada para cada uma.

A tecnologia GPON fornece redes complexas em topologia de árvores da camada 2 do modelo de referencia OSI baseadas no protocolo ATM e múltiplos protocolos para suportar e executar a conversão. Enquanto isso, a tecnologia EPON, usa simples redes da camada 2 utilizando o protocolo IP para dados, voz e vídeo.

A GPON usando o protocolo ATM necessita gerar circuitos virtuais que são providenciados por diferentes tipos de serviços e enviados para os assinantes. Esta técnica para transporte oferece um serviço de alta qualidade, pois, para cada aplicação especifica são gerados circuitos virtuais condizentes. Em contrapartida, os equipamentos da rede GPON precisam de algumas conversões de protocolos, segmentação, terminação do canal virtual e o encapsulamento no protocolo PPP. Resumidamente a estrutura GPON consiste de múltiplas redes da camada 2 sobre a mesma rede da camada física e cada rede com um protocolo diferente.

A tecnologia EPON por outro lado é bem mais simples, pois ela fornece conectividade para qualquer tipo de redes baseadas no protocolo IP, dispensando todo o aparato que a tecnologia GPON necessita, referente às conversões e encapsulamento.

Como as redes Ethernet dominam quase na sua totalidade as redes espalhadas pelo mundo, em redes locais, redes metropolitanas e até mesmo em _**backbones**_ de redes internacionais, a tecnologia EPON pode ser rapidamente implementada e gerenciada a um custo muito inferior ao seu concorrente GPON.

**8.1 Largura de Banda**

A tecnologia GPON oferece taxa de transmissão assimétrica sendo 1,25 Gbps ou 2,5 Gbps de _**downstream**_, e taxas escaláveis de _**upstream**_ a partir de 155 Mbps até 2,5 Gbps.

Seu rival, a tecnologia EPON oferece taxa simétrica (descida e subida iguais) a 1,25 Gbps no máximo.

**8.2 Alcance**

Ambas as tecnologias podem alcançar aproximadamente 20 km medidos desde a OLT até a ONU. Este valor é medido linearmente e devem ser considerados todos os aspectos do trajeto.

**8.3 Fator de Divisão**

A tecnologia GPON pode suportar até 128 ONU por OLT, ou seja, uma divisão de 1:128. A tecnologia EPON oferece uma divisão máxima de 32 ONU por OLT ou uma divisão de 1:32. Em alguns casos especiais, onde se diminua drasticamente a distância e aumentando a potência do laser, pode-se chegar em até 64 assinantes.

**8.4 Sistema de Gerenciamento**

A tecnologia EPON requer um simples sistema de gerenciamento, enquanto a GPON demanda três sistemas de gerenciamento, para os três protocolos de camada 2 que precisa.

Consequentemente EPON é muito mais econômica em sua implementação do que a GPON, além de necessitar quadro técnico altamente especializado para esta função.

**8.5 Segurança e Proteção**

A tecnologia GPON utiliza criptografia _**Advanced Encryption Standard**_ (AES) no sentido _**downstream**_ apenas. Na tecnologia EPON o mecanismo de criptografia ainda não foi definido pelo padrão, tornando os fornecedores incompatíveis, pois alguns fabricantes utilizam também o AES nos dois sentidos, mas como não foi padronizado, nem todos utilizam tornando a tecnologia proprietária até este momento.

**8.6 Quantidade de Assinantes**

O padrão EPON suporta dois tipos de ONUs, o tipo A onde a perda do sinal pode variar entre 5 dB até 20 dB, e o tipo B onde a perda máxima varia entre 10 dB a 25 dB, oferecendo serviços de conexão até 32 usuários tipicamente.

O padrão GPON suporta também ONUs do tipo C onde a perda de sinal varia entre 15 dB a 30 dB. O tipo C permite estender a rede além dos 20 km diminuindo assim a quantidade de assinante para no máximo 64 por PON.

**Para refletir:**

A norma IEEE 802.3ah _**Ethernet in the First Mile**_ (EFM) tem como objetivo tratar do fornecimento de conexão à Internet em alta velocidade.

O EFM apresentou duas topologias baseadas em cabeamento óptico, sendo: Conexão Ponto a Ponto e Conexão Ponto Multiponto.

Apesar das duas topologias serem funcionais, a mais interessante do ponto de vista econômico é a concepção Ponto Multiponto, por dispensar o uso de equipamentos ativos instalados em ambiente hostil.

A topologia Ponto Multiponto é a base da tecnologia PON e esta tecnologia vem ganhando espaço em várias cidades do mundo, inclusive no Brasil, em substituição às redes de par metálica da telefonia convencional.

Com as necessidades de maior banda nas conexões digitais as redes de par metálico deverão ser gradativamente substituídas pelas redes em tecnologia PON.

A tecnologia PON permite que apenas uma única fibra possa ser dividida seu sinal em um grande número de usuários.

As tecnologias que vem se destacando na PON são a GPON e a EPON.

A tecnologia GPON utiliza várias redes e vários protocolos baseados na camada 2 do modelo de referencia OSI e trabalha basicamente com o ATM. A tecnologia EPON trabalha apenas com IP e pode transportar qualquer informação baseada em IP.

A tecnologia EPON pode oferecer uma divisão de até 32 assinantes por fibra, enquanto que a tecnologia GPON oferece até 128 usuários por fibra.

A GPON esta há mais tempo no mercado e consegue atender melhor às necessidades dos assinantes, porém, perde nos requisitos de implantação, gerenciamento e manutenção. Já a tecnologia EPON é bastante simples e os custos para sua implementação e manutenção são bem inferiores ao seu concorrente.