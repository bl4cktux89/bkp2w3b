**Introdução**

Conforme estudamos na aula anterior, o Data Center recebe classificações segundo sua indisponibilidade máxima, medida anualmente e adotada por toda a comunidade computacional.

De acordo com o negócio para o qual o Data Center foi instalado, deverá suportar associados aos recursos financeiros, define-se o escopo do projeto e quão complexo serão seus sistemas de redundância para que não ocorram paralisações das operações computacionais.

A quantificação e a qualificação da infraestrutura se fazem necessárias para o ambiente no qual os sistemas serão instalados e, consequentemente, os custos envolvidos nessa qualificação aumentam conforme as exigências do negócio.

O ambiente Data Center é definido como um prédio inteligente, construído sob normas internacionais e melhores práticas construtivas, dotado de mecanismos para segurança de acesso, detecção preventiva e combate a situação de riscos, com vistas a manter um ambiente propício à hospedagem de equipamentos que compõem a infraestrutura de Tecnologia da Informação.

A TIA 942 define quatro níveis, denominados Tiers (camadas), os quais correspondem a uma classificação progressiva de disponibilidade da infraestrutura de um Data Center. Os Tiers foram originalmente definidos pelo _**Uptime Institute**_ e correspondem aos seguintes níveis de classificação de riscos: Tier 1: Básico; Tier 2: Componentes redundantes; Tier 3: Manutenção concorrente; e Tier 4: Tolerante a falhas.

**Tier 1: Básico**

É o projeto mais simples dos níveis e está suscetível a interrupções planejadas ou não planejadas.

Erros operacionais ou falhas espontâneas da infraestrutura do site podem provocar a interrupção dos serviços. Permite uma indisponibilidade (_**downtime**_), ou seja, tempo que uma aplicação ou sistema permanece indisponível para utilização anual de no máximo 28 horas e 48 minutos. As características básicas de um Data Center Tier 1 são:

- Não há redundância de componentes.
- Apenas uma linha para sistema de energia e de controle de temperatura.
- Não é necessário ter um piso elevado.
- Sistemas de refrigeração podem ser montados com equipamentos de conforto, porém deve-se utilizar intervalador com dois equipamentos.

Ele possui distribuição de energia e resfriamento de computador, porém estes podem ser de atendimento geral ou de várias unidades, aumentando assim os riscos de paralisação.

A infraestrutura deve ser completamente desligada, anualmente, para execução de manutenção preventiva e trabalho de reparo. As situações urgentes podem determinar desligamentos frequentes.

Os erros de operação ou falhas espontâneas dos componentes de infraestrutura do local ocasionarão a interrupção do Data Center.

**Tier 2: Componentes redundantes**

Em face da redundância nos equipamentos, esta categoria é menos suscetível a falhas.

O ambiente possui piso elevado e planejamento N+1 (_**need plus one**_), ou seja, a distribuição de circuitos não é redundante. Permite uma indisponibilidade (_**downtime**_) anual de no máximo 22 horas, conforme demonstra a tabela de terminologia de redundância a seguir:

![[Untitled 62.png|Untitled 62.png]]

As características básicas desse Tier são:

- Componentes redundantes (partes de _Switch_ e _Routers_).
- N+1, um módulo adicional ao mínimo do necessitado.
- Apenas uma linha de sistema de energia e de controle de temperatura.
- Links Redundantes para interligar pontos-chave do DC.
- A redundância de links não atende aos servidores.
- Necessidade de piso elevado.
- Menos suscetível a paradas que o Tier 1.
- As instalações de camada II com componentes redundantes são ligeiramente menos suscetíveis a interrupções de atividade planejada ou não planejada do que um Data Center Tier 1, porém eles possuem no-breaks e grupo gerador de energia, mas seu projeto é de (N+1), que tem uma via única de distribuição total.
- A manutenção da linha de energia crítica (ramal alimentador principal) e outras partes da infraestrutura do local precisarão de desligamento do processamento quando efetivamente ocorrer uma pane ou manutenções corretivas.

**Tier 3: Manutenção concorrente**

Permite atividades planejadas de manutenção sem a necessidade de interrupção dos serviços. Permite uma indisponibilidade (_**downtime**_) anual máxima de até 1 hora e 36 minutos.

Suas características principais são:

- Operação de 24 horas.
- Possui redundância das linhas de alimentação de energia e controle de temperatura, porém só um lado fica ativo.
- Componentes redundantes.
- Permite manutenção sem interrupção.
- Deve ter dois provedores de telecomunicação e duas salas de entrada (EFs).
- Pode migrar para Tier 4.
- Permite qualquer atividade planejada de infraestrutura do local sem interromper, de nenhuma forma, as operações do local.
- As atividades planejadas incluem manutenções preventivas e corretivas.
- Permite a substituição de componentes, acréscimo ou remoção de componentes de produção, teste de componentes e sistemas, e assim por diante.
- Para grandes locais, utiliza-se água refrigerada nos sistemas de ar-condicionado, resultando em dois conjuntos de tubulações independentes. Deve haver disponibilidade de capacidade e distribuição suficientes para simultaneamente carregar a carga em uma via enquanto executa a manutenção ou teste na outra. As atividades não planejadas, tais como erro na operação ou falha espontânea dos componentes da infraestrutura da instalação, ainda ocasionarão a interrupção do Data Center.

**Tier 4: Tolerante a falhas**

Além de possuir infraestrutura e capacidade para operar sob qualquer tipo de ação de manutenção programada, o ambiente é também tolerante a falhas, garantindo o fornecimento de recursos de energia elétrica, ar-condicionado, mesmo durante a ocorrência de pior caso intempestivo (enchentes, falta de energia elétrica, falta de água, queda de pequenas aeronaves etc.). Permite uma indisponibilidade (_**downtime**_) anual máxima de até 24 minutos. Suas características básicas são:

- Infraestrutura para qualquer atividade planejada ou não.
- Sistemas de energia e ventilação distribuídos (redundantes) e com componentes redundantes.
- Equipamentos críticos de backup para telecomunicações.
- Redundância no backbone (fibra e cobre).
- Sistemas críticos devem ter cabeamento horizontal redundante.
- É quase como dois Tier 3.
- Permite qualquer atividade planejada sem interromper a carga crítica. A função de resistência à falha também fornece a capacidade da infraestrutura do local de sustentar pelo menos uma falha não planejada de caso extremo ou evento de impacto de carga crítica.
- Em virtude dos regulamentos de incêndio e segurança elétrica, ainda haverá exposição de tempo ocioso devido aos alarmes de incêndio ou pessoal iniciando o desligamento de emergência.
- Requer que todo o hardware de computadores tenha dupla entrada de energia e possa ser alimentado por apenas um dos sistemas em caso emergência.

**Demais necessidades**

As salas projetadas para servirem de Data Center precisam ser equipadas com piso elevado e estes devem ter sua altura mínima de 150 mm, quando forem de baixa densidade, e altura de 30 mm ou mais quando forem Data Center de altíssima capacidade.

É comum encontrar Data Center com alturas de piso elevado de 400 mm a até 1.000 mm, dependendo da capacidade de equipamentos instalados no seu interior, e todo esse piso elevado com capacidade de 250 lbs por painel instalado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105034/a19i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105034/a19i01_cabestru80_100.jpg)

O ambiente da sala de computadores deve ser climatizado com a utilização de ar-condicionado de precisão, onde possa ser garantida uma temperatura entre 18ºC e umidade relativa do ar em torno de 40% a 55%, com uma variação máxima de 5ºC por hora. Esse equipamento deverá funcionar 24 horas por dia, 365 dias por ano, ininterruptamente.

Para auxiliar o sistema de climatização de todo o ambiente, deve-se instalar sistema de insuflamento de ar pelo piso elevado, com a adição de placas perfuradas, dotando o espaço de corredores frios e corredores quentes.

O cabeamento elétrico deverá ser instalado em eletrocalhas perfuradas ou aramados nos corredores frios com largura entre 600 mm e 1.000 mm, e os cabos UTPs e cabos de fibra óptica nos corredores quentes entre 1.000 mm e 1.200 mm, respectivamente.

Os racks que tiverem instalados no seu interior equipamentos devem ter a frente voltada para os corredores frios e a parte traseira sempre voltada para os corredores quentes.

Todos os cabos não utilizados deverão ser removidos, a fim de melhorar a circulação do ar abaixo do piso elevado, e o interior da sala de computadores deverá permanecer com as luzes apagadas, a fim de evitar o aquecimento desnecessário.

A iluminação do Data Center deverá ser no mínimo de 500 lux medidos a um metro do piso acabado, e seu rebaixamento de teto não deverá ser menor que 2,60 metros.

**Identificação**

Todos os componentes do Data Center deverão ser identificados de maneira única, o que facilitará a manutenção e a visualização dos equipamentos no seu interior.

Para a identificação e localização dos racks dentro da sala de computadores, um sistema de coordenadas deverá ser criado a fim de rapidamente localizar o referido rack. Esse sistema representa o piso elevado e suas placas dando identificação por colunas e linhas de todas as posições no interior do ambiente, e essas identificações são transportadas a uma planta com todas as informações.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105037/a19i03_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105037/a19i03_cabestru80_100.jpg)

Os racks devem ser identificados na parte superior e inferior, e pela parte frontal e traseira, contendo também a identificação dos equipamentos ativos em cada rack; inicia-se a numeração do topo do rack para sua base, informando na sequência o pavimento, coluna, linha, tipo e sequência numérica do equipamento. Como exemplo de uma identificação (01AC04 – SRV03), pode-se indicar as seguintes informações:

- 01 – Pavimento 01.
- AC – Linha no layout AC.
- 04 – Coluna no layout 04.
- SRV03 – Servidor 03 olhando de cima pra baixo conforme imagem anterior.

Todos os racks instalados no interior da sala de computadores deverão estar aterrados, segundo a normativa STD 607 já estudada em aulas passadas, e todo o piso elevado juntamente com sua estrutura de fixação, bem como as eletrocalhas no seu interior deverão fazer parte desse aterramento.

Outra preocupação do projetista de Data Center diz respeito ao combate a incêndio, que deverá ser feito através de gás HFC227, e o FM 200 se dá através de um sistema automático que permite a atuação rápida e eficiente do agente extintor.

O FM 200 é um agente extintor que não deixa resíduos, não é tóxico, não provoca choque térmico ou condensação de umidade significativa. Possui capacidade extintora imediata graças a uma combinação de inibição molecular da reação de combustão e resfriamento da chama, cuja concentração de extinção é alcançada em aproximadamente 10 segundos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105040/a19i04_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/5/0/105040/a19i04_cabestru80_100.jpg)

Para finalizar a aula, vamos nos lembrar de três aspectos importantes:

- A normativa TIA-942 recomenda também uma perfeita identificação baseada na normativa ANSI/TIA/EIA 606 para gerenciamento e administração dos racks instalados no interior do Data Center.
- Para a contenção de incêndios no interior do Data Center, utiliza-se gás que extingue o oxigênio do local com a utilização de gás do tipo FM 200.
- A iluminação para Data Center segue a mesma determinada para as salas de equipamentos, que é de 500 lux medidos a 1 metro do piso acabado.
- Utiliza-se ar-condicionado de precisão no interior do Data Center e ele tem de funcionar 24 horas por dia, 365 dias por ano, sem paralisação.