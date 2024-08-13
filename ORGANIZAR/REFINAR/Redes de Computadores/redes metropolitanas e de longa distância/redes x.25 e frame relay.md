**Arquitetura X.25 e Frame Relay**

**Objetivo**: O objetivo desta aula é fornecer subsídios necessários a uma visão geral das recomendações X.25 e seu funcionamento e das redes Frame Relay, que foi seu sucessor. Uma vez que ambas as tecnologias são ainda amplamente utilizadas no mundo todo.

**1. - Introdução ao X.25**

Nesta aula as recomendações X.25 não serão estudadas em todos os seus detalhes, uma vez que teríamos que estudá-las em várias aulas, por ser um tema considerado (por muitos profissionais) como uma rede do passado, o que não é verdade.

No início da década de 70, surgiram às primeiras redes experimentais comutadas por pacotes, como exemplo a ARPANET, que oferecia uma interface de datagramas ao usuário.

Antes desta data, não existiam o conceito de redes de longa distância de forma compartilhada, e as poucas empresas que necessitavam de conectividade entre suas filiais o faziam por _**links**_ dedicados conhecidos como Linhas Privadas (LPs) ou por linhas telefônicas discadas, que em termos gerais tem o mesmo significado. Com a diferença que as LPs tinham uma tarifação reduzida por estarem conectadas 24 horas por dia ao passo que as discadas ou comutadas, cobrava-se pelo degrau tarifário e pelo tempo de utilização.

Em meados da década de 70, começaram a surgir as primeiras redes comerciais comutadas por pacotes, quando então o mercado percebeu a necessidade de se estabelecer uma interface padrão para estas redes públicas para que os fabricantes de equipamentos pudessem desenvolver _**software**_ e _**hardware**_ de forma homogênea em um único padrão e assim alcançar a interoperabilidade.

Com este objetivo, o Comitê Consultivo Internacional em Telegrafia e Telefonia (CCITT), hoje _**International Telecommunications Union**_ (ITU), desenvolveu uma série de padrões para redes públicas comutadas por pacotes. Estes padrões foram conhecidos como Recomendações da Série X. As recomendações X.25 descreve o protocolo padrão de acesso entre computadores e a rede pública, determinando que o serviço oferecido por uma rede X.25 é um serviço de circuito virtual.

**2. - Arquitetura das Recomendações X. 25**

As recomendações X.25 seguem os três níveis básicos do modelo de referencia OSI, os quais se enquadram perfeitamente nos níveis 1, 2 e 3, ou seja, níveis: Físico, Enlace e de Rede.

Nestas recomendações foi determinada uma terminologia para diferenciar os equipamentos e suas conexões. Os computadores e terminais ligados a um _**Mainframe**_ são chamados de Equipamento Terminal de Dados (ETD). Cada ETD liga-se à rede através de uma central de comutação conhecida como Equipamento de Comutação de Dados (ECD).

No nível Físico as recomendações X.25 especificam as características eletromecânicas da ligação com o modem, níveis de tensão, tipo de sinais trocados entre os dispositivos, disposição física dos pinos dos conectores e tipo de cabos utilizados.

A camada Física oferece um meio de transporte de informações de dados não confiável, causados por uma série de razões, tais como: interferências eletromagnéticas, falhas de sincronização do receptor em relação ao transmissor e problemas de defeito nos componentes que remontam os circuitos. Portanto, presumir que os dados irão chegar íntegros somente pelo uso do nível Físico é um erro.

Os sistemas necessitam de argumentos que possam checar e recuperar os dados, caso eles tenham sido corrompidos durante a transmissão, estes argumentos estarão contidos na camada 2, ou seja, na camada de Enlace do modelo de referência OSI. O nível 2 é, portanto, responsável pelo agrupamento dos bits recebidos pela camada física em quadros. Os quadros em realidade são um conjunto de bits delimitados por um conjunto de bits especiais chamados de _**Flags**_. Entre os _**Flags**_ encontram-se todos os bits separados por quantidade determinada, geralmente em bytes (conjunto de 8 bits), com funções especiais de controle e carga útil a ser transportada.

Também no nível 2 é implementado o enlace lógico que pode ser visto pelos níveis superiores como sendo imune a erros. O controle de erros do nível 2 detecta quando um bit foi recebido com valor diferente daquele que foi transmitido através do campo FCS, conforme estudado no protocolo HDLC.

O nível 2 do X.25 utiliza como protocolo de controle de linha, o HDLC (estudado anteriormente), portanto, basta aplicar tudo que foi aprendido no nível de Enlace do X.25.

O nível 3 do X. 25 é o de Rede, responsável pelo tratamento das informações em forma de pacotes. Neste nível aparece a noção de circuitos virtuais e de pacotes, sendo responsável por criar e manter associações entre ETDs, que preservam a sequência dos dados trocados entre eles.

Na verdade não há um circuito físico destinado a cada interligação entre os equipamentos ETDs e a rede. Há uma associação temporária entre dois ETDs e entre eles existem diversos equipamentos comutadores, criando uma chamada virtual ou temporária, a qual recebe o nome de _**Switched Virtual Circuit**_ ou simplesmente SVC, que são aqueles em que se disca para o número que se deseja transmitir e após a conclusão do envio da mensagem, a conexão é desfeita ou _**Permanent Virtual Circuit**_ (PVC) que mantêm a conexão permanente entre os ETDs.

**3. - Funcionamento Estrutural da Rede X. 25**

Como descrição básica do seu funcionamento, os dados são divididos em pacotes de vários tamanhos e a cada um é atribuído um endereço e demais informações pertinentes de controle.

Para se conseguir a alta qualidade na transferência, os pacotes são envelopados em quadros, ou seja, são carregados por quadros em sua área de _**payload**_ de um quadro do tipo HDLC.

Cada quadro (que é enviado por um enlace) é armazenado temporariamente em um _**buffer**_ de memória, até que sua informação seja verificada e o quadro ter sido aprovado pelo receptor. O fato de cada quadro ser armazenado em cada comutador, no trajeto entre origem e destino, resulta em atrasos, mas em compensação chega a seu destinatário sem erros de bits de forma intacta.

Caso um pacote chegue a um comutador com erro, ele será descartado e será solicitada ao comutador anterior uma nova retransmissão. Como este tem uma cópia do pacote em seu _**buffer**_, bastará reencaminhar o mesmo adiante e este procedimento ocorrerá com todos os comutadores do trajeto, caso tenham recebidos pacotes danificados.

Trata-se, portanto, de um método de armazenamento e encaminhamento, porque cada comutador primeiro armazena os pacotes e depois os envia adiante. O tratamento de pacotes realizado pelos nós consiste principalmente numa verificação do formato do pacote, seleção de uma via de saída, verificação de erros e espera de capacidade disponível da via de saída. A figura 1 exemplifica uma rede X. 25.

Esta condição foi importante às redes X.25 porque foram criadas em uma época onde a infraestrutura de redes era precária. Utilizavam-se, em geral, as redes telefônicas, que naquela ocasião eram completamente construídas com cabos de par metálico e todos os seus problemas oriundos destes. Os cabos de fibra óptica e os modernos meios de transmissão digital ainda estavam em fase embrionária, portanto o X.25 tinha de ser robusto e a toda prova.

Outro fator determinante também é que naquela época o que imperava em computação não eram os microcomputadores (PCs), que nem existiam da forma que conhecemos hoje, mas os _**mainframes**_ e em suas pontas remotas, terminais ditos “burros”, sem processamento e que não tinham condição de solicitar novamente algum pacote, caso este estivesse comprometido ou que nem tivesse chegado ao terminal.

**4. - Serviços Disponibilizados**

As redes X.25 disponibilizam uma transferência de arquivos em pequenos pacotes, conhecida como uma rede orientada a conexão. Mas o que é uma rede orientada a conexão?

Redes orientadas a conexão são aquelas que antes de enviar os dados do cliente, necessitam realizar uma conexão física e lógica entre as entidades. Podemos tomar como exemplo uma simples ligação telefônica, em que não se tira o monofone do gancho e o indivíduo começa a falar diretamente. Para isso, antes é necessário conectar-se ao destinatário, para depois iniciar o diálogo. Nas redes X.25 o processo é o mesmo, existindo dois tipos de conexões: As conexões SVC e os PVC, conforme já mencionado.

Os serviços implementados aos clientes conectados a uma rede X.25 são:

- Recuperação de informações de bases de dados nacional e internacional.
- Correio eletrônico
- Caixas de banco automáticas.
- Terminais de pagamento com cartão de débito/crédito.
- Transferência de arquivos.
- Tráfego de terminais para _mainframe_ do tipo processamento de transações bancárias.

Quando um processo de nível 4 em um Equipment Terminal Data (ETD) deseja enviar uma sequência de pacotes, através da rede para outro processo também de nível 4 em outro ETD, ele tenta estabelecer uma chamada virtual. O ETD transmissor escolhe de um grupo um canal lógico livre do seu lado e envia ao Equipment Commutation Data (ECD) um pacote chamado _**Call Request**_ (CR). Este pacote indica que o transmissor quer estabelecer uma chamada virtual utilizando um canal lógico ao receptor.

O ECD receptor ao receber o pacote CR escolhe um número de canal lógico livre e encaminha ao ETD receptor um pacote chamado _**Incoming Call**_ (IC), indicando a chegada de uma chamada virtual. Se o ETD receptor estiver disponível a aceitar a chamada, ele indicará um estado de conectado e enviará ao ECD receptor um pacote de _**Call Accepted**_, que será encaminhado ao ECD transmissor indicando um Estado de Conexão entre as duas entidades ou Conexão Estabelecida (CE). Note que deve haver dois circuitos virtuais para uma conexão lógica, entre as duas entidades e, ambos com número de canais lógicos diferentes.

Após este estado de conexão inicial os dois computadores estarão aptos a iniciar a transmissão dos dados exatamente igual a uma ligação telefônica.

Como detalhe final, esta interação de conexão descrita acima se refere ao nível 3 do X.25 entre ETDs e ECDs remotos, enquanto que no nível 2 do X.25 as interconexões são feitas de enlaces a enlaces como qualquer protocolo de nível 2, utilizando então os canais virtuais. Outra questão importante é que nunca deverão existir, na mesma conexão física, dois circuitos virtuais com o mesmo número, mas poderão existir circuitos virtuais repetidos no decorrer do trajeto entre os dois ETDs, transmissor e receptor.

**5. - Redes Frame Relay**

**5.1 - Introdução**

A rede X.25 reinou absoluta por um largo espaço de tempo, desde a sua criação até sua implementação, pois, antes dela só existiam o arrendamento de linhas telefônicas para a interconexão de empresas e estações em localidades remotas.

Este reinado se manteve até o inicio dos anos 90, mas, com o aumento das aplicações _**cliente-servidor**_ que demandam curto tempo de resposta, o aumento substancial do tráfego de telefônico e de dados e o aumento do tráfego em rajadas mostrou a tecnologia X.25 um gargalo, principalmente por causa da sua limitada capacidade de transmissão que na época era de 64 Kbits.

O _**Frame Relay**_ foi desenvolvido para atender os novos requisitos de velocidade, tráfego em rajadas, novas aplicações e largura de banda. A transferência de quadros obteve muito sucesso na ocasião, porque, veio de encontro com a necessidade emergente das empresas de interconectarem suas LANs a preços mais competitivos e de forma mais simples.

Atualmente a tecnologia de transferências de quadros é a melhor e a mais econômica rede, com a função de interconectar as LANs com abrangência mundial ficando conhecida como a rede X.25, refinada ou melhorada principalmente ao atendimento ao tráfego da Internet.

O objetivo da aplicação do _**Frame Relay**_ é sacrificar os serviços prestados pela rede X.25, como funções de correção de erros, cópia dos quadros transmitidos em _**buffer**_ para retransmissão (caso necessário), controle de fluxo (em detrimento ao aumento), otimização da largura da faixa flexível da rede comutada por pacotes e a alta taxa de bits transmitidos nas redes comutadas por circuitos. O resultado foi conseguido agora com as redes _**Frame Relay**_ que consegue alta taxa de transferência de quadros podendo chegar até 50 Mbits, porém, sem a eficiência da correção em circuitos com alta taxa de erros de bits.

O _**Frame Relay**_ esta associado às transmissões por cabeamento óptico, onde a taxa de erro de bits declinou muito, tornando a transferência de quadros perfeitamente adequada a esta via.

O protocolo utilizado na transferência de quadros é extremamente simples sendo contemplados nos dois primeiros níveis do modelo de referência OSI, o nível físico e o de enlace, e desta forma, os circuitos são agora chaveados e não roteados e com isso ganhando agilidade e rapidez na comutação.

**5.2 - Funcionamento da Rede** _**Frame Relay**_

A característica fundamental das redes de transferência de quadros é que elas são orientadas a conexão e o _**Frame Relay**_ não é uma exceção. Em uma rede orientada a conexão todos os quadros de uma ligação especifica são enviados ao longo da mesma rota por meio da rede, assegurando assim a menor quantidade de _**overhead**_ em cada quadro e possibilitando uma rápida transferência nos nós. Com a finalidade de verificar a quantidade de informações enviadas na rede, foram definidos alguns parâmetros que, somados, permitiram o maior controle e gerenciamento da rede como um todo. Os parâmetros de usuários são:

- _Committed Information Rate_ (CIR) - Taxa de informação compromissada à capacidade de transferência média acordada.

O CIR é o trafego médio especificado por um usuário, que é compromissado pela concessionária de telecomunicações a se manter neste nível de forma garantida, isso significa dizer que o valor contratado do CIR jamais poderá ser inferior. O Cliente poderá selecionar o valor do CIR entre valores típicos de: 0, 8, 32 e múltiplos de 64 Kbits/s. O valor zero é usado se o cliente não consegue fazer uma estimativa do seu tráfego interno para a conexão na rede _**Frame Relay**_, e a concessionária o fará aplicando valores do CIR fracionados até se conseguir uma estimativa regular.

O valor do CIR nada tem a ver com a velocidade do _**link**_ físico, mas é sim uma taxa garantida dentro do mesmo. Um usuário pode ter uma conexão física de 2 Mbits e uma conexão lógica ou circuito virtual de apenas 64 Kbits. Em outras palavras, uma mesma conexão física pode transportar vários circuitos virtuais e estes podem ter diferentes tipos de CIR.

- _Comitted Burst Size_ (Bc)- Tamanho da rajada compromissada à quantidade máxima de dados, que é permitido ao usuário transmitir durante um período de tempo.

Em outras palavras o Bc é a máxima quantidade de dados (em bits) que o usuário pode entregar à rede em um dado intervalo de tempo (T), onde:

CIR = Bc / T

- _Excess Burst Size_ (Be) - Tamanho das rajadas em excesso a quantidade de dados em bits que é permitido ao usuário exceder o Bc durante um período de tempo.

O nível Be é em realidade o identificador do número máximo de bits que a rede tentará entregar, excedendo o nível Bc durante o intervalo de tempo. Sendo o Be um nível configurado máximo de transferência, qualquer tentativa de envio de quadros acima deste valor será descartada imediatamente.

A figura 2 identifica os diversos níveis e as condições na transferência dos quadros em cada um destes níveis, onde é demonstrado um tráfego abaixo no nível Bc e portanto, uma transferência sem nenhum problema ou condições específicas.

Já a figura 3 ilustra uma condição específica onde o tráfego excede Bc sendo menor que Bc + Be. Nesta condição temos as seguintes questões: Os três primeiros quadros são transmitidos sem ultrapassar Bc, já o quarto quadro resulta em um número total de bits transmitidos dentro do intervalo de tempo maior do que Bc, portanto, o quarto quadro é marcado para eventual descarte pela rede caso ela fique congestionada (o bit DE = 1).

Na figura 4 temos uma condição de descarte onde o tráfego excede a Bc + Be e nesta condição observa-se que os dois primeiros quadros não excedem Bc e são transmitidos normalmente, o terceiro quadro excede Bc e é marcado com o bit DE = 1 (elegível para descarte), caso a rede fique congestionada, porém, o quarto quadro excede Bc + Be e é descartado de imediato.

Todos estes níveis de controle garante uma rede transparente aos usuários e consequentemente um alto desempenho na transferência de quadros. Por estas razões, o _**Frame Relay**_ tornou-se uma rede de âmbito global, sendo atualmente a principal rede para a conexão entre LANs em diferentes partes do mundo.

**6. - Para refletir**

As redes X.25 foram desenvolvidas na década de 70, numa ocasião onde as telecomunicações eram ocupadas pelas redes telefônicas convencionais e os grandes computadores (_**mainframes**_).

Naquela ocasião as redes de telecomunicações eram precárias, levando ao desenvolvimento de um protocolo e uma rede robusta, que pudessem exercer além do transporte dos dados, a sua correção e a garantia de que os dados chegariam intactos ao destinatário.

As redes X.25 então foram desenvolvidas com velocidade máxima de 64 Kbits por segundo chegando atualmente a 2 Mbits e são dedicadas exclusivamente, ao tráfego de dados.

O desenvolvimento das redes X.25 foi a primeira experiência na utilização de circuitos virtuais em compartilhamento dos _**links**_ físicos, chamados na ocasião de linhas arrendadas e com isso obter uma economia significativa em telecomunicações. As redes X.25 foram implementadas no mundo todo e são totalmente normatizadas.

As redes _**Frame Relay**_ é uma evolução das redes X.25 com melhorias substanciais nas questões de velocidade e capacidade de transferência de arquivos.

Em contra partida, diferente das redes X.25, as redes _**Frame Relay**_ não são apropriadas a _**links**_ de comunicação com grande taxa de erro de bits por estas não guardarem em seus _**buffers**_ os quadros a serem transmitidos.

As redes _**Frame Relay**_, portanto, são indicadas em _**links**_ com boa infraestrutura, com baixa taxa de erro de bits como os _**links**_ ópticos.

A velocidade das redes de transferência de quadros pode chegar até 50 Mbits e elas possuem mecanismos de proteção contra excessos de transferências de dados pelos clientes descartando os quadros transmitidos acima destes limites.

Atualmente a rede de transferência de quadros é a principal rede de interconexão entre as redes LANs em diferentes localidades formando assim uma das principais redes de longa distância.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252942/11213.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252942/11213.jpg)

Funcionamento básico da rede X.25

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252937/11214.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252937/11214.jpg)

Figura 2 - Demonstração do nível de tráfego normal abaixo do CIR

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252934/11215.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252934/11215.jpg)

Figura 3 - Tráfego acima do CIR em uma rede Frame Relay

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252936/11216.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/9/252936/11216.jpg)

Figura 4 - Descarte do quadro após ultrapassar o nível BE

**1. - Modelo de Referência OSI**

Em principio a rede de transferência de quadros usa as duas camadas mais baixas do modelo de referência OSI, a camada física e a de enlace, porém, afastando-se um pouco do tradicional HDLC.

O _**Frame Relay**_ usa uma versão adaptada de procedimento de acesso de enlace no canal, que foi desenvolvida originalmente para as Redes Digitais de Serviços Integrados (RDSI) _**ISDN**_. Nas redes de transferência de quadros, esta adaptação é chamada de LAPF que é realmente uma parte do protocolo LAPB – Procedimento Equilibrado de Acesso de Enlace do X.25 e irmão gêmeo do HDLC – Controle de Enlace de Dados de Alto Nível da OSI.

No _**Frame Relay**_, no nível de enlace são recomendados duas especificações que são as: Q.922 Superior que contém funções para transmissão e controle de fluxo para assegurar que o usuário final receba informações corretas e a recomendação Q.922 de Núcleo, que descreve todas as funções que todos os nós em uma rede de transferência de quadros devem ser capazes de executar. Todos os _**switchs**_ _**Frame Relay**_ devem estar envolvidos na verificação do quadro, sendo capazes de detectar os pontos iniciais e finais de cada quadro, bem como se estes estão corretamente formatados. Todas as informações de usuário são enviadas transparentemente por meio dos nós, o que significa dizer que nenhum nó pode tirar qualquer conclusão sobre o conteúdo destas informações, tornando a rede extremamente segura. Também nos nós deve ser executado a verificação de erros em relação à transmissão pela recontagem e comparação do campo FCS de cada quadro. Os erros detectados não podem ser corrigidos pela rede, e os quadros danificados são simplesmente descartados.

Portanto, a rede de transferência de quadros basicamente trabalha nos dois níveis inferiores do modelo de referência OSI como já mencionado, então, a cada conexão entre os nós deve existir um endereço local como no X.25 existiam os Circuitos Virtuais ou simplesmente os VCs.

De fato, a rede _**Frame Relay**_ usa um endereçamento local, de enlace denominado _**Data Link Connection Identifier**_ (DLCI)_**.**_ O DLCI é o número que identifica em cada acesso de enlace entre os nós, definidos sobre o referido acesso. Por exemplo, um circuito virtual entre dois nós da rede de transferência de quadros se caracteriza por dois DLCI’s, um de origem e outro de destino formando assim um _**link**_.

**2. - Modelo de referencia Frame Relay**

Como já estudado, as Redes _**Frame Relay**_ trabalham nos níveis mais baixos do modelo de referencia OSI, o nível 1 (físico) e o nível 2 (enlace), portanto, podemos concluir que as redes _**Frame Relay**_ são em realidade uma rede de transferência de quadros.

A estrutura deste quadro é bastante simples, contendo os campos comuns como: _**flags**_, campo de transporte de informações _**payload**_, campo de verificação dos bits transmitidos FCS e o Campo de Endereço que neste particular, além de transportar o endereço do enlace momentâneo daquela conexão, transporta uma série de bits reservados para o controle do congestionamento da rede.

**3. -**  **Estrutura de Quadros da Rede** _**Frame Relay**_

A estrutura do quadro de uma rede de transferência de quadros é demonstrada na figura 1 e a partir daqui, iremos estudar cada campo especificamente, são eles:

- _Flags_: Todos os quadros começam e terminam com um indicador formado por um octeto (8 bits) em um padrão igual sempre formado por um bit zero, seguido de seis bits uns e finalizando com mais um bit zero – 01111110.
- _Payload_: Este é o campo onde é encontrada a informação do usuário, os dados propriamente ditos que necessitam ser transportado, portanto, o _payload_ é o _container_ de carga e seu tamanho ou capacidade é definida pela operadora de telecomunicações que opera a rede, porém, o Fórum de transferência de quadros recomenda uma carga máxima de 1600 bytes. A informação é transportada pela rede de forma completamente inalterada e não é interpretada pelo protocolo em nenhum dos nós que esta viaja.
- Campo _Frame Check Sequence_ (FCS): O FCS é a sequencia de verificação do quadro formado por dois octetos (16 bits) e tem a função de verificar o quadro de erros ocorridos durante a transmissão no enlace, esta verificação é feita a cada nó que o quadro atravessa, porém, em caso de erro detectado, o quadro é descartado e não é solicitado sua retransmissão como nas redes X.25. Esta função deverá ser executada pelas camadas superiores no receptor da informação. Todos os bits do quadro são verificados, exceto os _flags_ e o próprio campo FCS.
- Campo de Endereço: O campo de endereço é formado a principio por dois octetos, onde os seis bits do primeiro octeto e os quatros bits do segundo irão formar o endereço DLCI de 10 bits indicando o próximo destino para qual o quadro deve ser transportado.

Ainda dentro do campo de endereço temos mais alguns bits responsáveis pelo controle de congestionamento e descarte de quadros na rede, são eles:

- Bit CR: O bit CR de comando e resposta ocupa o sétimo bit do primeiro octeto e não é usado pelo protocolo de transferência de quadros, sendo enviado como bit “transparente”, por intermédio dos nós e ainda poderá ser utilizado pelo usuário quando requerido em alguma aplicação mais especial.
- Bit EA: O bit EA ocupa o oitavo bit no primeiro e segundo octeto e sua função é de endereço estendido que pode permitir o aumento do endereço DLCI para mais de 10 bits. Se o bit EA é posicionado em bit zero, seguir-se-á outro octeto de endereço aumentando assim os bits que formam o endereço DLCI. Se o bit EA estiver posicionado em um, o octeto em questão é o último no campo de endereço. Atualmente nenhum fabricante utiliza o bit EA em seus equipamentos ou aplicações.
- Bit FECN: O bit FECN ocupa o quinto bit do segundo octeto do campo de endereço e sua função é sinalizar a notificação de congestionamento explícito à frente. Esta sinalização alertará o extremo receptor que, momentaneamente a rede passa por dificuldades de congestionamento e o receptor não precisará fazer nenhuma ação especifica, pois ela refere-se apenas numa indicação.
- Bit BECN: O bit BECN ocupa o sexto bit do segundo octeto e sua função é similar ao bit FECN, indicando uma notificação de congestionamento explícito para trás, onde alertará o extremo transmissor sobre uma situação de sobrecarga na rede. Algumas aplicações e equipamentos mais inteligentes com a notificação BECN diminuirá sua taxa de transmissão pela redução da janela deslizante, até que a notificação desapareça, mas esta função é rara atualmente nas implementações.
- Bit DE: Ocupando o sétimo bit do segundo octeto o bit DE tem uma função muito especial indicando a elegibilidade de descarte onde o quadro deve ser descartado em caso de sobrecarga na rede.

Em uma transferência de quadros, caso a razão de envio esteja abaixo do valor de CIR contratado, a rede transmitirá os quadros sem reserva, porém, quando a taxa excede ao valor de Bc, imediatamente o bit DE é setado (levado a nível lógico 1) e com isso, quando a rede está congestionada, os quadros com bit DE setados serão descartados, caso a rede esteja operando em condições normais, os quadros com bit DE setados serão transmitidos naturalmente.

Em uma situação em que a taxa ultrapasse não só o nível Bc mas também o nível Be, os quadros que ultrapassaram em primeira estância o nível Bc já estarão com seu bit DE ativado e quando estes ultrapassarem o nível Be, serão imediatamente descartados, mesmo que a rede não esteja numa situação de congestionamento.

Esta posição de controle tem como objetivo manter a rede sempre em níveis aceitáveis de transferência de quadros, evitando os gargalos, congestionamento e a sensação de uma rede lenta aos usuários finais.

**4. - Controle de Fluxo**

O controle de fluxo em uma rede é fundamental a sua sobrevivência e nas redes _**Frame Relay**_ isso não é uma exceção.

A finalidade do controle de fluxo é impedir que o extremo transmissor repasse mais informações que o extremo receptor possa aceitar. Algumas vezes uma parte especifica da rede é sobrecarregada por não poder suportar esta cadencia total. Se a rede assume o papel de receptora de informações, o controle de fluxo poderá ser utilizado para evitar degradação séria do desempenho global da rede e nestas situações é que os sinalizadores FECN e BECN entram em serviço mais especificamente.

Quando um nó da rede for sobrecarregado, todos os bits FECN e BECN em todos os quadros das conexões por meio da rede serão sinalizados e com isso, o transmissor ou receptor poderá reduzir a taxa de transferência até a recuperação da rede. Infelizmente poucos são os elementos da rede (como roteadores) que são equipados com funções de interpretar o BECN e o FECN a fim de iniciar uma ação de redução da carga, por meio do armazenamento temporário em _**buffers**_.

Outro detalhe ainda sobre o endereçamento DLCI é que ele é composto de 10 bits, podendo representar até 1024 conexões lógicas, porém, algumas conexões lógicas são reservadas para transferências especiais. Após descontar estas conexões com finalidades especiais, restam 992 diferentes valores de DLCI para uso no tráfego.

De forma semelhante as redes X.25, só poderá existir um valor DLCI no mesmo enlace, porém, valores repetidos de DLCI no percurso poderá coexistir sem nenhum problema. Lembre-se que o valor DLCI só tem significado local, onde uma conexão lógica muda estes valores DLCI entre os extremos constantemente.

**5. - Para refletir**

O protocolo _**Frame Relay**_ é relativamente simples e seu principal campo é o campo de endereço, que contem o endereço DLCI da conexão lógica, mas também alguns bits responsáveis pelo tráfego dos quadros na rede.

O endereço DLCI só tem relevância local, isto é, entre os enlaces e no mesmo enlace não poderão existir endereços DLCI repetidos, porém, no trajeto entre receptor e transmissor poderá existir números repetidos.

O endereço DLCI conta com 10 bits e, portanto, são possíveis 1024 endereços, entretanto, somente 992 são disponibilizados em virtude de alguns serem reservados para transferências especiais.

No interior do campo de endereço existem dois sinalizadores FECN e BECN responsáveis pela indicação de congestionamento sendo lançados BECN para trás na rede e FECN para frente.

O bit DE é utilizado com a função de marcar o quadro em questão que está ultrapassando o valor de CIR contratado e, neste caso, se a rede estiver em pleno funcionamento sem nenhuma ocorrência de alto tráfego, ela tentará transmitir o quadro mesmo estando o bit DE setado. Caso o quadro ultrapasse o nível Be e já estando com o bit DE ativado, o mesmo será descartado imediatamente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/0/253075/11217.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/0/253075/11217.jpg)

Figura 1 - Campos do Quadro Frame Relay.