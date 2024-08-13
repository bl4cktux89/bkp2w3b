O objetivo deste material é permitir que o leitor tenha uma visão estimativa do dimensionamento para fins de gerência de execução de projetos e, mesmo, um suporte para a confecção de contratos de prestação de serviços no contexto de projeto e execução de Data Centers.

**Qual a unidade de medida mais adequada para condicionadores de ar em Data Centers?**

De uma maneira um pouco trivial, a medida para capacidade de volumes de ar condicionado veio dos primeiros equipamentos que simplesmente sopravam ar entre pedras de gelo provocando ar frio. Usando medidas norte americanas, quando este equipamento derretia 2 mil pounds de gelo (1 pound é uma libra, que corresponde a 453,6 Kg) em 24 horas, foi definido como uma tonelada de refrigeração. Nas medidas britânicas, BTU (British Thermal Units), as quais foram adotadas por todos, 1 ton de ar refrigerado precisa de 12.000 BTU/hora por  24 horas. No caso de grandes consumidores de refrigeração como os Data Centers, pensa-se em termos de consumo de energia e, por uma questão de conveniência, adotou-se que 1 ton de ar refrigerado é equivalente a resfriar 3,5 kW de calor, ou toneladas de refrigeração (TR).

**O que pensar ao dimensionar?**

**CRAC** (_**Computer Room Air Conditioning)**_ é um dispositivo que monitora e mantém a temperatura, distruibuição do ar e umidade relativa de uma _**computer room**_ em um Data Center.

Para um dimensionamento, por exemplo, para 20 ton CRAC, ou seja, um CRAC que precisa ter a capacidade de resfriar 20 ton, precisamos resfriar 70 kW de calor, como definido acima. Mas não podemos simplesmente fazer isto. Precisamos pensar numa situação de sobre carga e sobre dimensionar (over-size) de 20 % e, ainda, em casos de previsão de um crescimento, talvez, sobre dimensionar em 50% tanto em caso de água resfriada. Ainda não é tão simples fazer dimensionamento somente pelo calor que precisamos resfriar. Lembrando que existem dois tipos de calor: o sensível e o latente. O sensível é aquele que sentimos diretamente e o latente é o necessário para evaporar a umidade. Ou seja, quando o condicionador de ar tem que lidar com o calor latente, ou cuidar da umidade, ele “rouba” a capacidade do equipamento de lidar com o calor sensível.

Ora, a umidade esperada da _**computer room**_ (sempre falamos de _**computer room**_ porque é lá onde existem os equipamentos que precisam ser mantidos mais frios, se um processador de um computador aquecer, ele precisa rever mais vezes seu cálculos, pois aumenta do número de erros) é de 45% RH (_**relative humidity =**_ umidade relativa), mas, se resfriar demais, vai gerar um arrefecimento latente e a umidade vai cair. Estranhamente, precisaríamos gastar energia devolvendo a umidade do ar. Por outro lado, quanto mais quente mais baixa é a umidade relativa (relativa) embora tenha o mesmo teor de umidade, pois a umidade está lá, mas, em forma de vapor. Infelizmente não conseguimos medir a umidade real diretamente e em tempo de automatizar o processo de resfriamento. Precisaríamos coletar o ar e medir em laboratório. Então se continua com RH.

A maioria dos condicionadores de ar são controlados pela temperatura de retorno. Embora pareça errado, quanto maior a temperatura de retorno, mais o CRAC terá capacidade de refrigerar. Se baixar mais a temperatura exigida em um ambiente com alta umidade relativa, menos calor será removido e, na realidade a temperatura vai aumentar, além de gastar mais potência (energia) para fazer isto. Na tabela 1 podemos ver como o nível de umidade afeta a performance em uma cenário onde queremos um condicionador (tipo chilled-water) com capacidade 22 ton.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/9/257952/14332.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/9/257952/14332.png)

Mostrar a relação entre temperatura de retorno, umidade relativa e capacidade de refrigeração

Fonte: Autoria própria

Se você utilizar dutos para canalizar o ar quente de volta para os CRACs, e mantiver o ar de retorno a 27 °C ou superior, impedindo que ele se misture com o ar frio, você pode obter melhor capacidade de refrigeração real a partir da mesma máquina. Mantendo baixa a umidade, melhor ainda será o desempenho.

Outro cuidado que deve ser tomado é o fluxo de ar. O condicionador de ar deve insuflar ar, na maioria das instalações, por baixo. Este fluxo de ar provoca uma pressão menor (vácuo) puxando o calor que deveria subir, para baixo. Isto provoca grandes perdas de capacidade de refrigeração e energia, consequentemente. Atualmente, a maioria dos CRACs têm seus ventiladores com um sistema de regulagem automática e um sistema de sensores espalhados para melhor adequar a velocidade do fluxo. No entanto, melhor usar um sistema computacional de dinâmica de fluídos antes de desperdiçar muito investimento em um sistema CRAC caro.

**Quais os passos para calcular os parâmetros do condicionador de ar?**

Seguindo os passos da tabela 2, extrairemos a potência total de resfriamento, o que pode ser transformada facilmente em BTUs e, desta forma determinar como serão distribuídos os CRACs e sua capacidade nominal. Por uma questão de simplificação, assumiu-se, na literatura técnica, que toda a energia entregue aos equipamentos é transformada em calor.  No caso de cálculo puro da _**computer room**_, retire a linha UPS com baterias, principalmente no caso de Data Centers de grande porte, onde a norma TIA 942 exige que UPS acima de 100kVA devem estar fora da _**computer room**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/4/258412/14336.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/4/258412/14336.png)

Tabela 2: Tabela prática para cálculo de refrigeração

Fonte: Autoria própria

Segue uma breve explicação de cada item:

Equipamentos de TI: São os servidores, roteadores, switches, modens, etc. Que estão, normalmente, localizados nos racks. Trata-se do consumo de energia.

UPS com baterias: Trata-se da potência total do Nobreak/UPS.

PDUs: os _**power distribution units**_, ou unidades de distribuição de energia, consomem uma quantidade de energia (impedância dos cabos, disjuntores magnéticos e sistema anti surto). Esta energia também gera calor e é proporcional as energias circulantes pelo data center.

Iluminação: A energia gasta em iluminação transforma-se quase que inteiramente em calor.

Pessoas: As pessoas geram calor.

**Total: kW**

**Para BTU: kW x 3412**

**Para TR: kW x 0,283**

**EXEMPLO BÁSICO DE DIMENSIONAMENTO DE UM SISTEMA DE REFRIGERAÇÃO**

Exemplo: Atribuindo que os equipamentos de uma _**computer room**_ de um data center médio consomem 400 kW (A = 400000W).

B = Carga dimensionada para UPS é  700 kW

C = Área da _**computer room**_ = 300m2

D = Número de pessoas na _**computer room**_ = 10 (estimado, depende dos serviços oferecidos pelo data center).

Pela tabela 2, teremos:

A = Total de carga de TI = 400000W

UPS com baterias = (0,04 x 700000) + (0,05 x 400000) = 28000 + 20000 = 48000W

PDUs = (0,01 x 700000) + (0,02 x 400000) = 7000 + 8000 = 15000W

Iluminação: 21,53 x 300 = 7659W

Nº de pessoas: 100 x 10 = 1000W

Total: 400000 + 48000 + 15000 + 7659 + 1000 = 471659W = 471,66kW

Para BTU: 471,66 x 3412 = 1603303,92 BTU/h.

Para TR: 471,66 x 0,2844 = 134,1 TR

Portanto, o sistema de refrigeração desse data center será dimensionado em vários refrigeradores de ar, que somados, terão 472 kW. Sem contar margem para crescimento.