A _**Telecommunications Industry Association**_ (TIA) é uma associação comercial que representa a indústria de tecnologia da informação e comunicação global através do desenvolvimento de normas nas áreas de telecomunicações, telefonia móvel, tecnologia da informação, redes de computadores, cabeamento, satélite, etc. TIA é credenciada pelo ANSI. Já a EIA(_**Eletronic Industries Alliance**_) também credenciada pela ANSI, desenvolve padrões e especificações técnicas de componentes eletrônicos, de telecomunicações e Internet.

A ANSI, _**American National Standards Institute**_, foi fundada em outubro de 1918, nos Estados Unidos, com a missão de supervisionar a criação, promulgação e uso de normas e diretrizes que afetam os negócios em quase todos os setores.

A TIA, em associação com a EIA, desenvolveram a norma TIA/EIA 942.

Essa norma especifica os requisitos mínimos para a infraestrutura de telecomunicações e salas de informática em data centers. A topologia proposta deve ser aplicável em qualquer porte de data center, independentemente de um novo data center ou a expansão de um data center existente.

Idealmente, os passos do processo de concepção do design deveriam ser:

1. Estimar equipamentos de telecomunicações, energia e climatização do data center em cenários de pico. Antecipar futuras tendências sobre a vida útil do data center.
2. Fornecer espaço, energia, refrigeração, segurança, piso elevado, aterramento, proteção elétrica, e outras utilidades e funcionalidades requeridas por arquitetos e engenheiros. Fornecer funcionalidades para o centro de operações, área de carga e descarga, sala de estoque e outras áreas de apoio.
3. Coordenadas preliminares dos espaços do data center planejados pelo arquiteto e engenheiros. Sugerir as alterações necessárias.
4. Criar um piso plano com condições para alocações de grandes salas e espaços. Fornecer requisitos para vias de telecomunicações.
5. Obter um plano de atualização, com percursos de telecomunicações, equipamentos elétricos e mecânicos futuramente adicionados ao data center em capacidade de pico.
6. Projetar o cabeamento do sistema de telecomunicações com base nas necessidades dos equipamentos alocados no data center.

Data Centers são ambientes de missão crítica e requerem integração entre todas as utilidades. Os sistemas que devem ser consideradas em um projeto são:

- Arquitetura;
- Elétrica;
- Ar Condicionado;
- Telecomunicações;
- Gestão;
- Manutenção;
- Segurança

A figura 1 relaciona os espaços necessários para o data center e os outros espaços da construção:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268574/12301.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268574/12301.jpg)

Figura 1: Relação de Espaços em um Data Center. Fonte: TIA 942

Fonte: Norma TIA 942 págnia 21

**ESPAÇO DE TELECOMUNICAÇÕES E TOPOLOGIAS**

No sistema de telecomunicações, deve-se considerar:

- Sistemas elétricos;
- Sistemas de aterramento;
- Sistema de cabeamento estruturado;
- Passagem de cabos;
- Racks e gabinetes;
- Equipamentos ativos de rede;
- Sistema de administração de rede;
- Segurança

Espaços típicos dentro de um data center incluem:

- Sala de entrada (_entrance room_ ER)

É o espaço usado para a interface entre o sistema de cabeamento estruturado do data center e o cabeamento do edifício. Inclui equipamentos dos provedores de serviços e acessos. Para melhorar a segurança, recomenda-se que esta sala fique fora do _**Computer Room**_, evitando que técnicos de provedores de acesso ou serviços circulem pelas áreas protegidas.

Data Centers podem ter várias ERs para fornecer redundância ou evitar exceder o máximo suportado de cabeamento.

A ER pode estar ao lado ou junto à área de distribuição principal.

- Área de distribuição principal (_main distribution area –_ MDA)

A MDA fica dentro do _**computer room**_ e abriga o distribuidor principal do cabeamento (_**cross-connect**_ principal - MC). Os equipamentos comumente instalados nesse espaço são _**core**_ da rede do data center, como switch Ethernet _**core**_, roteador _**core**_, switches SAN (Storage Area Network) e equipamentos para a distribuição de serviços de voz (switches para serviços de voz sobre IP, VoIP e PABX).

- Área de distribuição horizontal (_horizontal distribution area_ – HDA)

Quando o MDA suporta todo o _**computer room**_, não há necessidade de HDAs. No entanto, um data center típico tem várias HDAs.

A HDA inclui _**cross connect**_ horizontal (HC), switches LAN, switches SAN e switches KVM (teclado/vídeo/mouse) para equipamentos finais localizados nas áreas de distribuição de equipamentos.

- Área de distribuição de zona (_zone distribution área_ – ZDA)

ZDA é um ponto de interligação opcional entre a HDA e a área de distribuição de equipamentos para permitir a reconfiguração e flexibilidade nas tomadas. Geralmente posicionada embaixo do piso.

- Área de distribuição de equipamento (_equipamento distribution area_ – EDA).

É o espaço alocado para o equipamento final, como servidores e equipamentos de  _**storage**_ (armazenamento).

Abaixo, a figura 2 mostra uma topologia típica de um data center:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268575/12305.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268575/12305.jpg)

Figura 2: Exemplo de uma topologia básica de um data center. Fonte: TIA 942

Fonte: Norma TIA 942 págnia 24 adaptada com traduções

**ELEMENTOS BÁSICOS DO SISTEMA DE CABEAMENTO DE UM DATA CENTER**

A Figura 2 ilustra um modelo representativo para os vários elementos funcionais que compreendem um sistema de cabeamento para um data center. Ela retrata a relação entre os elementos e como eles são configurados para criar o sistema total.

Os elementos básicos da estrutura do sistema de cabeamento centro de dados são os seguintes:

a) Cabeamento horizontal;

b) Cabeamento de backbone

c) Cross-connect na _**entrance room**_ ou MDA

d) Cross-connect principal (MC) na MDA

e) Cross-connect Horizontal (HC) na sala de telecomunicações, HDA ou MDA

f) Tomada de Zona ou ponto de consolidação de ZDA

g) Tomada na área de distribuição do equipamento

**REQUISITOS DO** _**COMPUTER ROOM**_

A _**computer room**_ é um espaço de ambiente controlado, com a função de abrigar equipamentos de T.I., cabeamento e sistemas de telecomunicações que alimentam esses equipamentos.

Como requisitos gerais, deve-se prever carga do piso (equipamentos, cabos, carga concentrada ou uniforme), folga entre equipamentos (necessária para a manutenção), fluxo de ar, energia e restrições de comprimento do circuito.

**Localização**

Ao selecionar o espaço para a _**computer room**_, deve-se prever sua expansão. Evitar posições que tenham componentes que a limitem, como elevadores e paredes externas. Deve ser acessível para a entrega de equipamentos de grandes dimensões.

Deve estar localizada longe de fontes de interferência eletromagnética, como transformadores de energia elétrica, motores e geradores, etc. Não deve ter janelas exteriores para não aumentar a carga de calor e reduzir a segurança.

**Tamanho**

A _**computer room**_ deve ser dimensionada para atender às exigências conhecidas de equipamento específico incluindo folgas adequadas; estas informações podem ser obtidas a partir dos fornecedores dos equipamentos. O dimensionamento deve conter as exigências atuais e um fator para ampliação futura.

A altura mínima da c_**omputer room**_ deve ser de 2,6m a partir do piso acabado para qualquer obstrução, como _**sprinklers,**_ luminárias ou câmeras. A norma recomenda uma altura livre de 0,46m entre o topo de um rack mais alto e a parte mais baixa do teto.

A porta de entrada deve ser dupla, com cada folha medindo 1m de largura e 2,13m de altura. Deve facilitar a entrada de grandes equipamentos, portanto, não devem ter separador entre as folhas ou deverão ser removíveis.

A estrutura de fixação do piso elevado deve ser montada sobre a laje da _**computer room**_. A capacidade de carga deve ser suficiente para suportar tanto a carga distribuída, quanto a concentrada, com cabeamento mídia associada. O mínimo de capacidade de carga no piso distribuído é de 7,2 kPa (732,36kgf/m2). O recomendado é de 12 kPa (1.220,6036kgf/m2). Deve-se tomar o cuidado com a capacidade desse piso suportar cargas penduradas na parte inferior do pavimento. O piso deve ter um mínimo de 1,2 kPa (122,06036kgf/m2) para suportar cargas penduradas. O recomendado é de 2,4 kPa (244,12072kgf/m2)

**Acesso**

Portas da _**computer room**_ devem fornecer acesso apenas ao pessoal autorizado.

**Orientação para outros equipamentos**

Equipamentos elétricos, tais como a distribuição e condicionamento de energia e UPS (_**uninterruptible power supply**_) até 100 kVA será permitida na _**computer room**_, com a exceção de baterias que contém líquidos.

UPS maior do que 100 kVA ou contendo baterias que contém líquidos, deve estar localizado em um sala separada.

Equipamentos não relacionados com o suporte da sala de computador (por exemplo, tubulações, dutos, etc.) não devem ser instalados, atravessar ou entrar na sala de computador.

**Acabamento**

Pisos, paredes e teto devem pintados, ou construídos de um material para minimizar a poeira.

Acabamentos devem ser de cor clara para melhorar a iluminação da sala. Os pisos devem ter propriedades anti-estáticas .

**Iluminação**

Iluminação deve ser de no mínimo 500 lux no plano horizontal e 200 lux no plano vertical, medida 1 m acima do piso acabado no meio de todos os corredores entre racks e gabinetes.

Aparelhos de iluminação não devem ser alimentados a partir do mesmo painel de distribuição elétrica dos equipamentos de TI na _**computer room**_. Interruptores _**dimmer**_ não devem ser usados.

**Sinalização e considerações sísmicas**

Deve ser desenvolvido no âmbito do plano de segurança do edifício.

**Ambiental**

A _**computer room**_ deve ser protegida contra contaminantes, de acordo com a norma ANSI / TIA-569-B.

Se a _**computer room**_ não tiver um sistema HVAC (_**heating, ventilation and air conditioning**_) dedicado, deve ter fácil acesso ao sistema de distribuição HVAC principal. HVAC deve ser fornecido numa base de 24 horas por dia 365 dias por ano.

HVAC (_**heating, ventilation and air conditioning**_ = condicionamento de calor, ventilação e ar) é o sistema que controla a climatização do data cente

Se a estrutura construída não puder garantir o funcionamento contínuo para grandes volumes, uma unidade autônoma será fornecida para a _**computer room**_.

O sistema HVAC deve ser suportado pelo gerador _**standby**_ do _**computer room**_. Se não houver esse gerador, o sistema HVAC deve ser interconectado a um sistema de geração _**standby**_.

**Classificação em camadas (**_**Tiering)**_

Data Centers devem ser capazes de continuar suas funções em condições catastróficas. Pontos únicos de falha devem ser eliminados para melhorar a redundância e a confiabilidade tanto no âmbito da infraestrutura de apoio do data center, como nos serviços fornecidos externamente.

**Redundância:**

Redundância aumenta a tolerância a falhas e facilita a manutenção. Pode ser entendida como a duplicidade de partes, módulos, encaminhamentos, componentes e sistemas, com o objetivo de evitar o tempo de parada (_**downtime**_) de um data center.

**Critérios de redundância**::

**N:** Exigência básica. Sistema atende aos requisitos básicos e não tem redundância.

**N + 1:** fornece uma unidade, módulo, caminho ou sistema em adição à exigência básica. A falha ou manutenção dessa unidade, módulo, caminho ou sistema redundante, não irá interromper as operações.

**N + 2:** fornece duas unidades, módulos, caminhos ou sistemas adicionais à exigência básica. A falha ou manutenção de quaisquer duas unidades isoladas, módulos ou caminhos não causa interrupção das operações.

**2N:** Duas unidades básicas completas. Uma ativa, outra _**standby**_. A falha ou manutenção de uma unidade inteira, módulo, caminho ou sistema não irá interromper as operações.

**2(N+1):** Duas unidades N+1 completas. Mesmo no caso de falha ou manutenção de qualquer unidade, módulo, caminho ou sistema, alguma redundância será fornecida e operações não serão interrompidas.

**Disponibilidade**

A disponibilidade de um sistema é o tempo que ele está disponível para uso em relação ao tempo total de operação, por ano. A redundância ajuda na disponibilidade do sistema.

Disponibilidade = (MTTF) / (MTTF + MTTR)

Onde,   MTTF (_**Mean Time To Failure**_) = tempo médio para falhar;

MTTR (_**Mean Time To Recovery**_) = tempo médio para voltar a operação.

Ex.: Se um data center, na média, leva 6 meses para falhar, então o MTTF é 6 meses. Se, para voltar a operação, na média, leva 20 minutos, então o MTTR é 20.

Deve-se deixar nas mesmas unidades, portanto:

6 meses = 6 (meses) x 30 (dias) x 24 (horas) x 60 (minutos) = 259.200 minutos

Disponibilidade = (259200) / (259200 + 20) = 0,9992, ou seja, 99,92%.

**Confiabilidade**

A confiabilidade é o percentual de tempo que o sistema está operando de acordo com a necessidade. Ela é especificada pelo MTBF (_**Mean Time Between Failure)**_, tempo médio entre falhas. Equipamento com alto MTBF e redundância aumentam a confiabilidade do sistema.

**Tiers**

A Norma TIA/EIA 942 propõe uma séria de regras aplicáveis para classificar um Data Center chamados de TIERS, que considera 4 níveis. Esses níveis são definidos pelo The Uptime Institute, instituto emissor de certificação tier para data centers com base em suas disponibilidades.

Níveis mais altos correspondem não somente à maior disponibilidade, mas também custos mais altos de construção. O fator humano e dos procedimentos de funcionamento também são importantes, principalmente no quesito confiabilidade.

A norma recomenta que as instalações devam ser mantidas, atualizadas e testadas, sem interrupções de operações. Adicionalmente, devem ser projetadas para acomodar o crescimento futuro com pouca ou nenhuma interrupção nos serviços.

Cada Tier suporta o nível anterior e são adicionadas novas exigências.

**Tier 1:**

- Básico (requisito N).
- Operações podem ser interrompidas por manutenção planejada ou causas acidentais.
- Não é necessária redundância de alimentação de energia na entrada da empresa.
- Não é necessária redundância física de telecomunicações, embora possa existir a redundância lógica.
- Rotular todos os patch panels, tomadas, cabos, todos os armários e racks com seu identificador na frente e na traseira.
- _Computer room_ tem distribuição elétrica e sistema de climatização dedicados. Sem redundância.
- Pode ter ou não piso elevado, UPS ou grupo gerador.
- A infraestrutura deve ser completamente desligada anualmente para serviços de manutenção.
- Situações urgentes, erros de operação ou falhas podem requerer desligamentos mais frequentes.
- A conexão entre a ER, MDA e HDA é feita através de um único caminho.
- Potenciais pontos de falhas são falta de energia da concessionária, falha de equipamentos do provedor, roteadores ou comutadores e qualquer evento danoso nos caminhos de interligação nas áreas ER, MDA, HDA, ZDA e EDA. Interrupção nos serviços de telecomunicações providos ao data center.
- Apresenta disponibilidade 99,67%, o que represente um _downtime_ (parada anual) de 28,8h.

**Tier 2:**

- Componentes redundantes (requisito N+1).
- Menos susceptível à interrupção para manutenção ou causas acidentais do que Tier 1.
- Os equipamentos de telecomunicações, tanto do Data Center como das operadoras, e comutadores devem ter módulos redundantes (fontes de energia, placas, processadores, etc.).
- Todos os patch cords e jumpers devem ser rotulados em ambas as extremidades do cabo com o nome da conexão em ambas as extremidades do cabo.
- O cabeamento do backbone principal LAN e SAN das HDAs devem ter fibra óptica ou par trançado redundantes em toda a topologia estrela. Conexões redundantes podem estar nos mesmos passadores de cabos.
- Sobrepondo a topologia estrela, é possível configurar topologias lógicas em anel ou malha, fornecendo caminhos alternativos.
- Devem-se ter duas caixas de acesso de telecomunicações e dois caminhos de entrada até a ER. É recomendado que exista uma separação física de no mínimo 20 metros entre estes caminhos por todo o percurso e que os mesmos cheguem a ER por lados opostos.
- São necessários módulos UPS redundantes e gerador elétrico, que não precisa de redundância. Também não é necessária redundância na entrada de serviço de distribuição de energia.
- O sistema de climatização inclui várias unidades de ar condicionado com o objetivo de manter a temperatura e umidade relativa do espaço, com uma unidade redundante. A unidade de ar condicionado é redundante, mas o sistema de tubulação tem um único caminho, onde uma falha ou manutenção a uma secção do tubo irá provocar a interrupção parcial ou total do sistema de ar condicionado.
- Possíveis pontos de falhas para a instalação Tier 2 são falhas nos sistemas de ar condicionado ou de energia que podem ocasionar a parada das operações ou qualquer evento catastrófico dentro da _entrance room_ ou MDA pode atrapalhar todos os serviços de telecomunicações do data center.
- Apresenta disponibilidade de 99,75%, o que represente um _downtime_ de 22,0 h.

**Tier 3:**

- Manutenção e operação simultâneas (Requisitos N+2).
- Permite que atividades de manutenção planejada ou por causas acidentais sejam executadas sem a interrupção da operação dos equipamentos críticos de TI.
- Data Center deve ser servido por, pelo menos, dois provedores de acesso. Esses provedores de acesso tem que ser totalmente independentes um do outro. Cabeamento ou pontos de presenças devem ser separados por pelo menos 20 m ao longo de toda a sua rota, para ser considerada rota diversificada.
- Deve ter duas _entrance room_ (ER), de preferência em extremidades opostas, com um mínimo de 20 m de separação física entre as duas entradas. As ERs não devem compartilhar equipamentos de telecomunicações, as zonas de proteção contra incêndio, unidades de distribuição de energia e ar-condicionado devem ser distintas. Os equipamentos dos provedores em cada ER devem ser capazes de continuar funcionando caso haja falhas na outra ER.
- Todo o cabeamento_, cross-connects_ e _patch cords_ devem ser documentados utilizando planilhas, bancos de dados, ou programas projetados para fazer a administração do cabo.
- Deve ter caminhos de backbone redundantes entre as ER, MDA e HDA.
- As entradas das redundâncias das conexões de switch do backbone devem ser separadas.
- Os equipamentos envolvidos nessa redundância devem estar ativos (_hot standby_).
- Os requisitos elétricos devem ser fornecidos com, pelo menos, pelo menos, redundância N+1 no módulo, caminho, e nível do sistema, incluindo gerador e sistemas UPS, sistema de distribuição, e todos os alimentadores de distribuição.
- O sistema de climatização inclui várias unidades de ar condicionado com capacidade de refrigeração para manter a temperatura e umidade relativa ideais, com unidades redundantes suficientes para permitir a falha ou serviço a um quadro elétrico. Esse nível de redundância pode ser obtido por fornecer duas fontes de energia para cada unidade de ar condicionado. O sistema de tubulação tem caminhos redundantes, o que uma falha ou manutenção de uma secção de tubo não irá causar a interrupção do sistema de ar condicionado. Todas as unidades de ar condicionado da _computer room_ devem ter o apoio de um gerador.
- Potenciais pontos únicos de falha são eventos catastróficos dentro da MDA ou HDA, que poderá interromper todos os serviços.
- Apresenta disponibilidade de 99,98%, que está associado a um _downtime_ de 1,6 h.

**Tier 4**

- Tolerante a falhas (requisitos 2N ou 2(N+1))
- Todo o cabeamento de backbone deve ser redundante. Cabeamento entre dois espaços devem seguir caminhos fisicamente separados. Esse cabeamento deve ser protegido em condutos fechados ou com armaduras (_braided cable sleeve_)
- Os equipamentos críticos de telecomunicações, de acesso do provedor, roteadores, switches devem ser redundantes, com fontes de energia redundantes. O sistema deve comutar automaticamente para o equipamento de backup.
- O data center deve ter duas MDAs, em extremidades opostas, com um mínimo de 20 de separação física. Não compartilham zonas de proteção contra incêndio, unidades de distribuição de energia e equipamentos de ar condicionado.
- A duas MDAs deverão ter caminhos próprios para as ERs e HDAs.
- As entradas de energia devem ser dedicadas ao data center e isoladas das outras instalações. O edifício deve ter pelo menos duas alimentações de serviços públicos de diferentes subestações para redundância.
- Possíveis pontos de falha são MDA e HDA se não houver redundância.
- Apresenta disponibilidade de 99,995%, associado a um _downtime_ de 0,4 h.

Resumo da classificação em Tier:

![[Untitled 66.png|Untitled 66.png]]

**Localização geográfica do data center:**

Algumas considerações na escolha do local de construção de um data center:

- O local não deve estar sujeito a inundações;
- Evitar proximidade a cabeceira de pistas de aeroportos;
- Evitar localidades muito próximas a linhas de transmissão elétrica;
- Locais próximos às concessionárias de energia elétrica e a centros de serviços são recomendados;
- Capacidade de crescimento.