**1. INTRODUÇÃO**

A expressão “última milha” refere-se ao atendimento de usuários em suas localidades, ou seja, nos seus bairros e vilas.

O atendimento existente hoje é feito pela rede de telefonia convencional, que por muitos anos atendeu de forma eficiente as facilidades de voz, porém, com o advento da Internet e suas conexões em banda larga, a rede de telefonia mostrou-se pouco eficiente nos quesitos de largura de banda.

A tecnologia então empregada para o atendimento à Internet por este meio é o xDSL e suas variações, que de uma forma geral, tem atendido os usuários, porém, não com a qualidade e a velocidade esperada.

Neste sentido, na atualidade, também é empregado para o atendimento às conexões de Internet as redes híbridas, destinadas a princípio ao fornecimento de sinais de televisão.

As primeiras redes de TV a Cabo foram construídas na década de 40. Em seus primórdios sua finalidade era fornecer canais de televisão para comunidades localizadas em regiões onde o sinal via espaço não chegava com boa qualidade, devido aos fatores de grande distância entre o transmissor e os usuários, com suas antenas, limitações de barreiras entre estes dois elementos ou características geográfica desfavorável do terreno.

A ideia deste tipo de rede é simples, ou seja, constituí de uma antena e seus transmissores (construídos em um ponto privilegiado), como por exemplo: no centro de um povoado em que poderia receber os sinais dos canais abertos, em boa qualidade e, distribuí-los através de cabos para essa comunidade. Dessa maneira, no início as _**Community Antenna Television**_ (CATV) eram antenas comunitárias, ou seja, várias pessoas faziam uso dela para receber sinais de televisão.

Com o amadurecimento da tecnologia e o surgimento de novos serviços, as redes de televisão a cabo se modernizaram e, hoje elas não funcionam apenas para atender cidades ou regiões aonde o sinal de TV aberta é fraco ou ruim. Atualmente as operadoras de TV a cabo oferecem diversos programas fechados, sendo uma opção de entretenimento para muitas pessoas, além de oferecer serviços de banda larga e voz sobre IP (_**VoIP)**_, tornando esta rede quase que totalmente digital.

No entanto, para que fosse possível oferecer todos esses serviços aos clientes, as operadoras tiveram que se modernizar. Um dos grandes passos foi adoção da arquitetura híbrida. A palavra híbrida advém do fato da utilização de enlaces ópticos e cabos coaxiais para a distribuição do sinal.  A figura 1 ilustra de maneira simplificada uma rede _**Hybrid Fiber Coax**_ (HFC).

É importante notar que o enlace óptico transporta o sinal por longas distâncias, ele vai desde a central de distribuição chamada de _**HeadEnd**_ até o nó óptico e, a partir daí segue-se cabos coaxiais que distribuem os sinais até a casa ou empresa do usuário final, em outras palavras, utiliza-se as fibras para longas distâncias e, em contrapartida, os cabos coaxiais para as pequenas.

**2. CABOS PARA HFC**

Antes de iniciarmos qualquer discussão a respeito do funcionamento das redes HFC, se faz importante que se conheça seus componentes, e entre os principais, destaca-se os cabos, pois são eles que irão transportar os sinais da central operadora até o usuário final.

**2.1 Cabos Coaxiais**

O cabo coaxial é um dos principais elementos que compõe a rede HFC, pois são eles os responsáveis pela distribuição dos sinais de radiofrequência dos distribuidores de localidade, chamados de _**nodes**_ às residências e empresas. A utilização dos cabos coaxiais é importante porque possibilitam o reaproveitamento das frequências que estão sendo irradiadas pelo ar, isto é, podem-se utilizar duas frequências iguais sem que elas se misturem, pois uma esta confinada nos cabos coaxiais enquanto que a outra esta sendo irradiada no espaço e vice versa. Isso ocorre devido à blindagem do cabo coaxial, que não permite que sinais de radiofrequência ingressem ou “vazem” do cabo. A figura 2 ilustra um cabo coaxial e seus elementos descritos a seguir:

- Condutor central – Condução do sinal de radiofrequência e alimentação dos equipamentos;
- Dielétrico – Isolamento entre o condutor central e a malha externa de proteção;
- Condutor externo – Blindagem do sinal e aterramento do sistema;
- Capa – Proteção do cabo contra corrosão e abrasão, a proteção elétrica contra curtos-circuitos e choques elétricos.

**2.1.1 Tipos de Cabos Coaxiais**

Nos sistemas de CATV utilizam-se diversos tipos de cabos coaxiais, que tem a ver com sua bitola (grossura), faixa de resposta de frequência e condições e ambientes de instalação.

Nos aspectos construtivos existem os cabos autossustentados e os não sustentados. O primeiro dispensa o uso de cabo mensageiro ou cordoalha de aço para seu lançamento e sustentação nos postes. Este tipo de cabo tem em seu invólucro uma cordoalha de aço que é usada para sustentá-lo. Devido ao custo deste tipo de cabo ser mais elevado (em relação ao não sustentado), no Brasil prefere-se utilizar a segunda opção.

O cabo não sustentado necessita, antes da sua instalação propriamente dita, o lançamento de um cabo de aço chamado mensageiro. Este cabo de aço é esticado entre dois postes a fim de receber através de “espinamento” o referido cabo coaxial que será, em outras palavras, costurado ao cabo de aço.

O processo de “espinamento” é feito com uma máquina que irá unir os dois tipos de cabos com um arame (que fica enrolado entre eles) garantindo assim uma perfeita acomodação e total segurança neste lançamento. A figura 3 ilustra este processo.

Além disso, existem cabos de diversos tamanhos (bitolas), sendo que a escolha do uso de cada um é dependente das necessidades técnicas do local e do projeto. As bitolas mais utilizadas para os cabos de uso externo são de: 0.500, 0.540, 0.750 e 0.860 que correspondem ao seu diâmetro em polegadas e são designados tecnicamente como cabo “tronco”. O cabo “tronco” é dividido em dois grupos: PIII e QR. Os cabos de bitola 0.500 e 0.750 são atribuídos ao grupo PIII e os de bitola 0.540 e 0.860 ao grupo QR.

A diferença básica entre estes dois grupos refere-se à construção, os cabos PIII possuem condutores externos mais rígidos e pesados, o que proporciona uma maior resistência mecânica, enquanto que os cabos QR são mais modernos e leves, pois são revestidos com uma lâmina de alumínio, proporcionando assim maior mobilidade e flexibilidade no seu manuseio e consequentemente maior fragilidade. Os cabos de uso interno são designados por cabo “_**drop**_” e possuem a designação técnica RG e só devem ser instalados na entrada do usuário final ou dentro da sua localidade.

**2.1.2 Características Elétricas dos Cabos Coaxiais**

Uma das características mais importantes existente nos cabos coaxiais diz respeito a sua resistência elétrica. Quanto maior for à bitola do cabo, menor é a atenuação que o sinal sofre no seu trajeto. Isso ocorre porque quanto maior for o diâmetro menor será a resistência à passagem da corrente elétrica. As resistências típicas dos cabos utilizadas em CATV são:

1. 5,64 ohms por quilometro lançado
2. 5,28 ohms por quilometro lançado
3. 2,55 ohms por quilometro lançado
4. 2,37 ohms por quilometro lançado

Os cabos apresentados acima por suas características são mais indicados para as instalações externas, ou seja, nas ruas. Nas instalações internas são empregados cabos mais finos e flexíveis do tipo RG11, RG06 e RG59. Esses cabos, apesar de não terem a mesma qualidade que os cabos de rede externa, são ideais para a instalação no assinante devido às qualidades apresentadas. Além disso, os _**taps**_ e acopladores só aceitam em suas portas os cabos da linha RG.

Outro detalhe bastante importante na construção dos cabos coaxiais diz respeito ao chamado efeito pelicular. O efeito pelicular é o fenômeno do aumento da resistência aparente de um condutor em função do aumento da frequência. Uma corrente continua se distribui uniformemente no condutor, já um sinal alternado faz com que corrente tende a se distribuir de maneira diferente, sendo que grande parte dela se desloca pela superfície, conforme ilustrado na figura 4.

Para minimizar o efeito pelicular, o condutor central dos cabos coaxiais são construídos utilizando dois materiais com propriedades elétricas diferentes, a fim de melhorar a condutividade. É empregado o alumino que apresenta uma condutividade de 37,7 mile ôhms*106 no centro do condutor central e o cobre que possui uma condutividade de 59,6 mili ôhms*106 nas bordas do mesmo condutor conforme ilustrado na figura 5.

Outro efeito a ser considerado é a atenuação dos cabos coaxiais. Quando um sinal de radiofrequência trafega em um cabo coaxial, ocorrem perdas na amplitude do sinal, o interessante é que essas perdas não são iguais para todas as frequências, ou seja, um sinal com frequência de 20 MHz sofrerá atenuações diferentes de um sinal de 100 MHz. Pelo fato de que a atenuação depender da frequência, conclui-se que aumentando a frequência, a atenuação aumentará também. A consequência desse efeito para as redes de televisão a cabo é que os canais de maior frequência serão mais atenuados, sendo necessário que o ganho no amplificador seja diferente para as diversas frequências. A tabela 1 ilustra a atenuação típica dos cabos externos (tronco) e a tabela 2 dos cabos internos (_**drop**_).

**Tabela** **1 – A****tenuação dos cabos tronco (dB/100 m)**

|Title|Frequência em MHz|0.500"|0.540"|0.750"|0.860"|
|---|---|---|---|---|---|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled\|Untitled]]|5|0.52|0.46|0.36|0.3|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 6\|Untitled 6]]|50|1.71|1.44|1.15|1.02|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 2\|Untitled 2]]|110|2.49|2.26|1.71|1.51|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 7\|Untitled 7]]|220|3.64|3.22|2.49|2.13|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 9\|Untitled 9]]|300|4.3|3.74|2.95|2.49|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 4\|Untitled 4]]|450|5.35|4.63|3.67|3.12|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 5\|Untitled 5]]|550|5.97|5.18|4.07|3.48|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 8\|Untitled 8]]|750|7.12|6.1|5.02|4.07|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/hybrid fyber-coax HFC, fiber to the x FTTx/Untitled Database/Untitled 3\|Untitled 3]]|1000|8.27|7.12|5.84|4.72|

  
  

**Tabela 2 –** **Atenuação máxima em decibel dos cabos** _**drop**_ **por 100 metros**

|Frequência em MHz|RG 59 - dB/100m|RG06 - dB/100m|RG11 - dB/100m|
|---|---|---|---|
|5|[[2,82]]|1,90|1,25|
|55|[[6,73]]|5,25|3,15|
|83|[[8,04]]|6,40|3,87|
|187|[[11,81]]|9,35|5,74|
|211|[[12,47]]|10,00|6,23|
|250|[[13,45]]|10,82|6,72|
|300|[[14,60]]|11,64|7,38|
|350|[[15,75]]|12,63|7,94|
|400|[[16,73]]|13,61|8,53|
|450|[[17,72]]|14,43|9,02|
|500|[[18,7]]|15,09|9,51|
|550|[[19,52]]|16,08|9,97|
|600|[[20,34]]|16,73|10,43|
|750|[[22,87]]|18,54|11,97|
|865|[[24,67]]|20,01|13,05|
|1000|[[26,64]]|21,49|14,27|

  
  

**2.2 Cabos de Fibra Óptica**

No cabeamento HFC pode-se determinar que os cabos coaxiais são responsáveis pelo atendimento à parte secundária da rede ou, a mais próxima do usuário final. Por sua vez os cabos ópticos são responsáveis pela parte primária da rede HFC, ou seja, são os cabos que partem do _**HeadEnd**_, ou em outras palavras, do escritório da concessionária de televisão a cabo.

No passado, as redes HFC eram de pequeno alcance com o atendimento a poucas quadras ou quilômetros e, naquela ocasião, não se utilizava os cabos ópticos, porém, com o aumento das distâncias e do consumidor, a utilização das fibras ópticas foi fundamental para o crescimento e a proliferação das redes HFC.

Conforme relatado por Soares (1995), a transmissão através das fibras ópticas é realizada pelo envio de um sinal luminoso, codificado dentro do domínio de frequência do infravermelho.

Uma fibra óptica é composta basicamente de um material dielétrico que normalmente é o vidro ou o plástico, transparente e flexível de dimensões reduzidas.

Existem dois tipos de fibras ópticas: as Multímodais (MM) e as _**Singlemode**_ (SM), onde as diferenças mais sensíveis entre estes dois modelos está no modo de propagação dos feixes de luz no seu interior.

A fibra SM tem o seu núcleo com dimensões muito pequenas, entre 8 a10 µm e seu tamanho comercial é de 9 µm de núcleo e casca de 125 µm. Este tipo de fibra óptica possibilita somente um modo para a propagação da luz, fato que garante uma grande banda passante. Possui baixa atenuação menor que 0,5 dB/km, chegando a 0,16 dB/km e permitindo alcances de até 100 km, e uma grande banda passante de 10 a 100 GHz. Devido às pequenas dimensões do núcleo, torna-se necessário concentrar o máximo de energia no mesmo, o que implicará na utilização de fontes do tipo laser o que torna o custo dos equipamentos transmissores e receptores elevado.

Outro tipo de fibra óptica é a MM na classificação de índice gradual. A fibra índice gradual tem o núcleo com dimensões um pouco maiores que a SM, 62,5/125 µm ou 50/125 µm e possui uma variação gradual do seu índice de refração do núcleo. Esta alteração proporciona caminhos de propagação com tempos mais próximos reduzindo a dispersão e atenuação para valores da ordem de 3,5 dB/km.

Nas redes locais LAN seu emprego está ligado às distâncias de até 2 km na tecnologia de 100 Mbps, a 550 m na tecnologia de 1.000 Mbps com fibra 50/125 e 300 m na tecnologia de 10.000 Mbps.

A fibra MM índice gradual 62.5/125 mm é a mais utilizada para redes locais, porém, com o advento do gigabit a fibra de 50/125 µm começou a se tornar mais popular por conseguir atingir a distância de 550 m contra os 275 m nas tecnologias de transmissão de 850 µm.

As fibras SM são utilizadas nos sistemas de telecomunicações, onde as distâncias e a bandas passantes são grandes, como nas redes metropolitanas MAN e redes de grande alcance WAN. Nas redes locais LAN a fibra óptica mais recomendada é a MM e seu emprego está ligado às distâncias não superiores a 2 km.

Nas redes HFC atuais são empregadas às fibras ópticas SM e seu enlace compreende distâncias de até 20 km.

**3. COMPONENTES DAS REDES HFC**

A rede HFC é um misto de cabos coaxiais e cabos de fibra óptica. Neste conglomerado de cabos existem os equipamentos e conversores que iremos descrever brevemente. São eles:

_**3.1 HeadEnd**_

O _**HeadEnd**_ é o ponto de recebimento e distribuição dos sinais de TV a cabo. Sua localização deve ser em local com boa recepção dos sinais de TV local aberta, e dos sinais provenientes dos satélites. Após o recebimento desses sinais, equipamentos localizados no _**HeadEnd**_ tratam, codificam e distribuem esses sinais através das fibras ópticas, até chegar aos _**nodes**_ das redes coaxiais.

Todos os sinais captados são realocados em novas frequências, conforme o plano de canalização estipulado pela operadora, para isso utiliza-se moduladores com filtros com alocação precisa de uma banda de 6 MHz para cada canal. Desta forma um sistema de CFTV pode transportar vários canais analógicos em seus cabos, e cada um é transmitido em uma frequência diferente, sem que ocorra interferência entre eles.

Outros tipos de sinais (que são transportados pela rede HFC) surgiram juntamente com a internet, e são eles o _**downstream**_ e _**upstream**_. O _**downstream**_ é o sinal que o assinante recebe do _**HeadEnd**_, e isso ocorre quando algum arquivo é baixado da Internet ou quando algum site é acessado. Resumindo, o _**downstream**_ é o fluxo de dados que vai do _**HeadEnd**_ até o assinante.

Já o _**upstream**_ é o sinal que o assinante envia ao _**HeadEnd**_, e isso pode ocorrer durante uma conversa em uma sala de bate papo, ou programas e jogos interativos. Cada um desses sinais está em frequências diferentes, conforme ilustrado pela figura 6.

Então, nas modernas redes HFC temos sempre uma banda de retorno ativada, no sentido da saída do assinante para o _**HeadEnd**_, sendo responsável pelas transmissões de sinais digitais, como exemplo, a comunicação com a Internet, comunicação de liberação de serviços _**pay per view**_ ou interatividade, onde a faixa de frequência abrange entre 5 MHz a 30 MHz ou 42 MHz, dependendo das características da planta da rede e do número de amplificadores instalados.

Estes dois sentidos acontecem separadamente na fibra óptica, ou seja, as bandas são separadas nas fibras TX e RX, porém, no cabo coaxial temos sempre as duas bandas de descida e de retorno trafegando simultaneamente. Para que exista a separação dos dois sentidos, é instalado nos amplificadores e terminais dos assinantes um filtro duplex e, este filtro possui três terminais. Um terminal trabalha nos sinais de descida, outro terminal nos sinais de retorno e o terceiro conector responsável pela combinação destes dois sinais de forma conjugada.

**3.2 Arquitetura e Topologia HFC**

A topologia mais tradicional é a do tipo “árvore e galho” ou _**Tree and Branch,**_ que consiste basicamente de um cabo coaxial tronco partindo do _**HeadEnd**_ seguindo em direção as várias regiões que devem ser atendidas.

Nesta configuração ainda não existe a utilização de cabos de fibra óptica, portanto, o emprego de amplificadores em quantidade era fundamental para a recuperação do sinal que irá se degradar ao longo das linhas. A figura 7 ilustra esta topologia.

Pelo fato da utilização do grande número de amplificadores em série, não haveria problema algum se eles só recuperassem o sinal degradado. Infelizmente para recuperar o sinal em níveis aceitáveis, todo amplificador acrescenta uma parcela de ruído. A somatória destes ruídos pode alcançar níveis não aceitáveis, prejudicando assim a qualidade da rede como um todo.

Uma das soluções para este problema seria a construção de vários _**HeadEnd**_ localizados por regiões e com isso diminuindo o comprimento dos cabos coaxiais tronco (lançados nas ruas) e, consequentemente, diminuindo o número de amplificadores.

Esta solução, apesar de funcional teoricamente, esbarrava no custo para a criação de vários _**HeadEnd.**_ Portanto, foi necessário buscar outro tipo de solução, mais econômica e de fácil implementação, culminando na adoção da solução híbrida com a utilização das fibras ópticas.

No início das redes híbridas, os cabos ópticos eram lançados em paralelo aos cabos coaxiais tronco, com o único objetivo de servir de redundância. Estes cabos seguiam desde o _**HeadEnd**_ até os _**Nodes**_ (nós ópticos que são instalados já muito próximo ao assinante).

Percebeu-se que a utilização das fibras, como apenas redundância aos cabos coaxiais, era muito pouca, ao passo que as fibras podiam oferecer muito mais serviços, pois nos momentos que os cabos coaxiais não estavam operando e sim as fibras, a qualidade do sinal aumentava juntamente com a velocidade.

Partindo desta constatação, algumas operadoras de televisão a cabo começou a desativar os cabos tronco e só utilizar as fibras como _**backbone**_ principal e com isso, as redes HFC expandiram por muitas regiões, atendendo um número maior de usuários a um custo menor.

A fibra óptica então é utilizada para transportar os sinais à longa distância, criando assim múltiplos pontos de distribuição chamados de NODES – Conversores Ópticos Elétricos. Nestes NODES a recepção é feita a partir da fibra e a distribuição através dos cabos coaxiais conforme ilustra a figura 8.

A utilização dos NODES em resumo foi a criação de _**HeadEnd**_ virtuais, onde cada um pode ser instalado nas proximidades dos assinantes e com isso criando uma célula de atendimento. Nesta categoria de células temos a seguinte divisão:

- Super Célula com atendimento de 7.000 a 9.000 residências;
- Célula _Standard_ com atendimento de 1.500 a 2.500 residências;
- Célula Mini com atendimento de 500 a 650 residências;
- Célula Micro com atendimento de 100 a 150 residências.

**3.3 Componentes  Internos e Externos**

Até o presente momento verificamos o percurso que os sinais percorrem na rede HFC. Partindo do _**HeadEnd**_ – Central, vários cabos de fibra óptica são lançados pelo posteamento em direção as células situadas em cada região de atendimento.

Em um local estratégico ou mais próximo possível do centro das células são instalados em armários de rua, fixados em postes ou calçadas, onde os equipamentos NODES recebem as fibras ópticas e converteram os sinais luminosos em sinais elétricos, que serão encaminhados para o atendimento aos assinantes.

Partindo de cada NODES são lançados cabos coaxiais (tronco), até muito próximo de uma célula de assinantes e, neste _**core**_ são acoplados aos TAP – componente de derivação de sinais.

Para o atendimento aos assinantes atualmente as instalações são divididas em dois grupos, a saber: Instalação de casas e instalação em apartamento.

Na instalação em casas a conexão é feita diretamente no componente de derivação de sinais – TAP que está mais próxima da residência, partindo deste TAP um cabo coaxial do tipo _**drop**_ será lançado deste até a residência, sendo conectado diretamente ao _**Decoder**_ do assinante.

Na instalação de um assinante que reside em um apartamento, a implementação não é feita diretamente do TAP que está mais próximo do prédio. Na maioria das vezes será necessária uma rede interna no prédio de distribuição de sinais, para que este assinante possa ser conectado. Esta rede interna é chamada de _**Multiple Dwelling Unit**_ (MDU).

Assim como na conexão de uma casa, teremos um cabo coaxial _**drop**_ que sai do poste e segue até a entrada de serviços do referido prédio que alimentará um amplificador. Este amplificador em conjunto com os cabos e componentes passivos garantirão a qualidade dos sinais para os assinantes que residem no referido prédio e que, por sua vez, em cada unidade será conectado ao _**Decoder**_ do morador.

Tanto a rede externa como a interna necessita de componentes além dos cabos para o perfeito equilíbrio dos sinais, a fim de manter em um nível aceitável, nem muito forte, pois teríamos a saturação das imagens e nem muito baixo porque perderíamos a qualidade nas transmissões.

Como principais componentes passivos temos os divisores, os acopladores direcionais e os TAPs.

O divisor é um componente passivo cuja principal função é dividir a potência do sinal de radiofrequência, que é acoplado em sua entrada, em duas saídas de igual amplitude. O sinal é atenuado em aproximadamente em 3,5 dB quando passa por este dispositivo e a figura 9 ilustra os dois tipos de divisores utilizados em redes HFC, o de uso interno e o de uso externo.

Os acopladores direcionais também são divisores, porém fazendo a divisão do sinal que é nele acoplado (de forma assimétrica), ou seja, nas saídas temos valores diferentes para cada saída. Esta forma desbalanceada de dividir o sinal é bastante apreciada nas instalações, quando se precisa de uma potência específica para uma determinada necessidade.

O componente TAP consiste em um divisor conjugado a um acoplador direcional e sua função é prover pontos de acesso aos assinantes. Normalmente encontra-se TAPs com 2, 4, 8 e até 16 saídas conforme ilustra a figura 10 e a atenuação deste componente pode variar na ordem de 4 a 29 dB.

**3.4 Fonte de Alimentação -** _**Line Power Insert**_ **(LPI)**

A fonte de alimentação funciona em conjunto com o LPI, cuja função é fornecer da rede de alimentação da concessionária de 127 ou 220 volts, uma tensão alternada entre 60 a 90 volts de onda _**quasi-square**_, ou seja, um sinal de onda quase quadrada, para o funcionamento dos componentes ativos da rede, os amplificadores.

A fonte é formada por um gabinete afixado diretamente no poste onde em seu interior há um módulo conversor e um módulo inversor, que será responsável em alimentar os equipamentos caso aconteça uma falta de energia da concessionária. Este inversor é acoplado a três baterias que garantirão um funcionamento pleno da rede, por um período superior a três horas de paralisação da energia elétrica.

A alimentação dos ativos é feita diretamente pelo próprio cabo coaxial e a inserção desta alimentação alternada de 60 a 90 volts se dá por um componente passivo denominado PLI, cuja função é a de proteção para a rede em qualquer situação ou evento de curto circuito na fonte, onde um fusível de proteção se romperá abrindo assim todo o circuito. A figura 11 ilustra a fonte devidamente instalada em um poste, o LPI e a forma de onda resultante na saída desta alimentação.

**Para refletir:**

A tecnologia HFC é uma rede híbrida que utiliza, em sua parte final mais próxima ao usuário, cabos do tipo coaxiais e na região mais distante do usuário cabos de fibra óptica.

A tecnologia HFC foi concebida a princípio para o fornecimento de televisão em localidades onde o acesso via sinal de rádio frequência em espaço aberto não era possível.

Hoje as redes de HFC estão capacitadas ao fornecimento de sinais de televisão em programação fechada, bem como acesso a Internet e sistema de telefonia.

Na rede HFC o ponto central é denominado _**HeadEnd**_ e deste local partem cabos de fibra óptica para cada centro de células.

Em cada célula são instalados conversores ópticos elétricos denominados NODES que tem a função de um mini _**HeadEnd**_ ou um virtual.

Destes NODES são lançados os cabos coaxiais, através das quadras da célula e, partindo de divisores _**TAPs**_ são conectados às residências dos assinantes.

Partindo dos _**TAPs**_ são lançados cabos do tipo _**drop**_ que adentram a residência onde são divididos por divisores passivos e acoplados ao equipamento _**Decoder.**_

Os _**Decoders**_ são em realidade os _**cable modem**_, última etapa antes de o sinal ser acoplado na televisão e no computador.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/6/267690/12790.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/6/267690/12790.jpg)

Figura 1 - Rede Hybrid Fiber Coax (HFC)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/6/267698/12791.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/6/267698/12791.jpg)

Figura 2 - Ilustração de uma cabo Coaxial

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268576/12792.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268576/12792.jpg)

Figura 3 - Maquina de Espinamento

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267706/12793.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267706/12793.jpg)

Figura 4 - Efeito Pelicular

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267707/12795.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267707/12795.jpg)

Figura 5 - Composição do cabo coaxial.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/7/268775/12798.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/7/268775/12798.png)

Figura 6 - Distribuição de canais na HFC

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/7/268778/12801.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/7/268778/12801.png)

Figura 7 - HFC só com cabos Coaxiais.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/7/268789/12802.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/7/268789/12802.png)

Figura 8 - HFC - Mista

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/1/269166/12803.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/1/269166/12803.png)

Figura 9 - Divisores para HFC

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/1/269167/12871.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/1/269167/12871.png)

Figura 1- Componente TAP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/0/270017/12872.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/0/270017/12872.png)

Figura 11 - Fonte de alimentação - PLI