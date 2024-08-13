### **Objetivos**

Neste tópico discutiremos uma das mais modernas redes que estão sendo pesquisadas, uma tecnologia ainda embrionária cujo objetivo é o monitoramento de pacientes com sensores em redes instaladas no corpo humano.

### **Introdução**

Na área de saúde os avanços tecnológicos estão produzindo sistemas inteligentes e, plataformas para o monitoramento de pacientes de forma continuada, este avanço proporciona um acompanhamento médico mais pontual e uma interação dinâmica por meio da telemedicina (Wen 2008). Essa evolução tecnológica, associada às antenas com irradiações de baixa potência, permitiu o desenvolvimento de uma nova concepção de arquitetura de rede designada como WBAN _**(Wireless Body Area Networks),**_ ou redes corporais sem fio, que monitoram os pacientes internados em hospitais ou em domicilio pelo uso da rede mundial de computadores, a Internet.

Uma WBAN é uma rede corporal de sensores sem fio ou dispositivos que podem ser afixados ao corpo humano ou implantados sob a pele. Os sinais vitais são coletados e mensurados para indicar as condições físicas do paciente e muitas vezes, para acionar o fornecimento de medicamentos, como no caso das bombas de insulina. Estes sinais mensurados e constantemente monitorados vêm auxiliar cuidadores para casos que exijam rápida intervenção da equipe terapêutica ou, uma atenção mais especial de alerta, conforme a patologia do paciente. Um exemplo desta monitoração são os índices glicêmicos dos pacientes diabéticos do tipo I. Contribuindo ainda para o monitoramento continuo e de forma remota, uma nova modalidade de pacientes vem a ser somado aos acamados. Nesta última década observa-se um crescimento acentuado no número de idosos que requerem os serviços de cuidado domiciliar (Figueiredo _**et al**_. 2008).

Como apurado pelo Instituto Brasileiro de Geografia e Estatística (IBGE), a população idosa que representava 8,6% dos brasileiros em 2000, equivalendo a aproximadamente quinze milhões de pessoas, deverá ultrapassar os 15% até o ano de 2020 (Secretária de Direitos Humanos 2012). Estes números, somados aos pacientes hospitalares e de pacientes em cuidados de _**Home Care**_ evidenciam a necessidade da organização de equipes de terapia multidisciplinar com o aprimoramento dos conhecimentos técnicos científicos e, principalmente, de recursos tecnológicos acessíveis como o monitoramento contínuo (Freitas 2009).

### **A utilização das WBANs**

As novas políticas de saúde pública que focam na economia em leitos hospitalares, o atendimento aos idosos e acamados em modalidade de _**Home Care**_ e o envelhecimento da população mundial, apontam para um mercado promissor e multimilionário, que são equipamentos e sensores de monitoramento clínico,  o qual  é o terceiro maior mercado mundial de sensores sem fio (Chakraborty _**et al.**_ 2013).

A OMS (Organização Mundial de Saúde) identificou que cerca de 17,5 milhões de pessoas morrem a cada ano por causa de ataques cardíacos. Atualmente, mais de 246 milhões de pessoas sofrem de diabetes (estimando-se 380 milhões de pessoas em 2025). A OMS ainda faz a projeção de indivíduos que morrerão de doenças cardiovasculares até 2025, sendo de aproximadamente 20 milhões de pessoas. Essas mortes podem ser potencialmente prevenidas e evitadas, por intermédio de um sistema de telemedicina baseado na WBAN (Chahakraborty _**et al.**_, apud OMS 2013). Estes números evidenciam a necessidade de monitoramento continuo e a utilidade da WBAN. Inúmeros outros exemplos de doentes iriam se beneficiar com o uso do monitoramento continuado ou prolongado, tais como hipertensão, asma, parkinson, insuficiência renal, alzheimer, acompanhamento pós-operatório, monitoramento de _**stress**_ e a prevenção da síndrome de morte súbita infantil, com causa ainda desconhecida pela ciência médica (Latré _**et al**_. 2011).

Estas aplicações podem ser consideradas como um indicador do tamanho do mercado para a WBAN, e a tecnologia poderia fornecer a conectividade necessária para apoiar médicos e terapeutas na gestão da saúde de pacientes e idosos. Um exemplo da aplicação de uma rede WBAN é ilustrado na Figura 1 em que vários sensores são instalados na roupa ou diretamente sobre a pele do paciente e, que permitiria a mensuração, como exemplo a temperatura corporal, pressão arterial, frequência cardíaca ECG e EEG, taxa de saturação de oxigênio no sangue entre outros sinais vitais.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/7/8/317889/21535.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/7/8/317889/21535.jpg)

FIGURA 1 - Sensores para Aplicação em WBAN

Fonte: (Santos, 2015)

Todos os números apontados pela OMS e visualizando esta nova fatia substancial de mercado, levaram empresas e pesquisadores a desenvolverem estudos e sistemas de WBAN, quase todos baseados em padrões de outros sistemas já desenvolvidos que também operam na banda ISM, tais como, _**Wi-Fi**_ (IEEE 802.11/a/b/g), _**Bluetooth**_ (IEEE 802.15.1),  _**UWB**_ (IEEE 802.15.3), e _**Zigbee**_ (IEEE 802.15.4) (Latré _**et al.**_ 2011). Todos estes padrões operam na banda ISM (_**Industrial, Scientific and Medical**_), considerada livre de licenciamento, e que, atualmente, encontra-se completamente saturada. A Banda ISM compreendem três segmentos do espectro (902 a 928 MHz, 2.400 a 2.483,5 MHz e 5.725 a 5.850 MHz) reservados para uso sem a necessidade de licenciamento para sua transmissão.

### **Arquitetura de Redes Corporais**

Um sistema WBAN é destinado ao monitoramento de sinais vitais humanos operando sem a necessidade de cabos, e do confinamento do paciente a um único local. Para tanto, o meio que permite esta mobilidade física são as ondas eletromagnéticas ou de rádio frequência, que permite de certa forma, dentro da sua célula de abrangência espacial, uma mobilidade, portanto, um erro ou a perda da informação médica por congestionamento de frequências ou o desvanecimento dos sinais é algo inaceitável em se tratando de vidas humanas. Portanto, pesquisadores e a indústria científica procuram desenvolver sistemas baseados na WBAN obedecendo sistematicamente a vários requisitos necessários, como:

**Confiabilidade**

A confiabilidade envolve as fases da medição dos sinais vitais e análise das coletas. A medição implica na precisão dos dados fisiológicos coletados através do _**hardware**_ dos sensores e do _**software**_ que manipula estes dados adquiridos. A comunicação é a etapa que envolve a garantia e a integridade na transferência dos dados coletados entre os sensores e a central de monitoração. Nas comunicações os protocolos utilizam a confirmação do recebimento correto da central enviando ao sensor um ACK _**Acknowledgement**_ ao dispositivo móvel destinatário. No caso do sensor não receber a confirmação do ACK num determinado espaço de tempo, o nó deverá retransmitir as informações novamente por um número de vezes pré-determinado até receber o ACK (Souza e Mesquita 2013).

**Segurança e Privacidade**

As informações e os dados coletados pelos sensores devem estar disponíveis somente para os profissionais de saúde autorizados, tanto por razões éticas como legais. Portanto, a segurança é uma questão importante a ser considerada no desenvolvimento de aplicações de redes sem fio para a área médica. As informações de saúde devem ser confidenciais, já que seu acesso pode causar risco de vida ao paciente, ou  ser disponibilizada publicamente (Souza e Mesquita 2013).

### **Sensibilidades ao Contexto**

Sensibilidade ao contexto pode ser definida como um procedimento de informação relevante ao paciente ou ainda, um serviço oferecido para um paciente de forma individual ou particular (Dey _**et al**_. 1998). Em Caldarelli _**et al.**_ (2002), no estudo no IMSS _**(Instituto Mexicano del Seguro Social)**_ revelou quatro elementos contextuais críticos que devem ser considerados no desenvolvimento de aplicações sensíveis ao contexto:

- **Localização e estado dos dispositivos** – Médicos e profissionais de saúde podem ter necessidade do acesso direto a documentos ou dispositivos que possam disponibilizar dados ou análise do seu paciente.
- **Perfil do utilizador** - No caso de uma casa de terapia ou hospital, o sistema terá que reconhecer os procedimentos e os indivíduos em particular. Diversos médicos, terapeutas ou enfermeiros, mesmo sem se conhecerem, terão que comunicar entre si; cabe ao sistema certificar-se que uma mensagem é entregue à pessoa correta (que desempenha determinado papel) para um determinado paciente.
- **Tempo de entrega** – A troca de informação num centro de reabilitação, casa de repouso ou hospital tende a ser sensível ao tempo, o que significa que uma mensagem pode ser relevante apenas por certo período de tempo. No caso de um médico que escreve uma mensagem para ser entregue à enfermeira do próximo turno, a mensagem só deve ser entregue no início do turno e não quando é escrita.
- **Localização** - Local onde os profissionais de saúde se encontram, dentro da área de abrangência da edificação e o tempo de acesso ao paciente num caso de alarme de maior criticidade.

**Energia**

Os nós ou dispositivos sensores são alimentados invariavelmente por uma bateria, que procurando a comodidade ao paciente, devem ser pequenas e ter um número mínimo de substituição ou recarga. Os micros controladores usados nos dispositivos sensores devem dispor de mecanismos que economizam energia. Um deles é o _**Dynamic Power Management**_ (DPM) (Sinha e Chandrakasan 2001).

O DPM desliga os componentes de hardware que não estão sendo utilizados e usa um escalonamento por relógio para religa-los. Dentre os componentes de maior consumo em um sensor, uma atenção especial deve ser dada ao sistema de transmissão, o rádio deve ter um baixo consumo juntamente com o micro controlador e o sistema operacional deve ser sensível ao contexto das aplicações ou mensurações que o sensor em questão estiver realizando. Um software bem desenvolvido levará em consideração o tempo de acionamento dos rádios para a transmissão de uma informação, considerando a relevância destes dados. Um exemplo desta sensibilidade pode ser dado por um sensor de temperatura, onde as informações coletadas não necessitam de ser informadas a cada instante, pois no corpo humano, a temperatura leva certo período de tempo para sofrer alguma mudança significativa. (Grillo 2009)

**Mobilidade e Facilidade de Uso**

O principal objetivo de sistemas para monitoramento remoto de saúde é permitir que os pacientes tenham uma vida independente, que seus sinais fisiológicos possam ser mensurados no cotidiano de suas vidas e, que estes sinais possam, de uma forma inteligente, alertar em caso de intercorrências. As redes de sensores sem fio estão possibilitando o desenvolvimento de aplicações que permitem e incentivam a mobilidade dos pacientes, criando assim, sistemas ubíquos para cuidados da saúde. O grande desafio para os pesquisadores é o desenvolvimento de sistemas úteis, amigáveis e discretos, levando sempre em consideração a dimensão física dos dispositivos; cuidados com antenas e baterias também são itens a serem considerados (Ko _**et al**_. 2010).

**As redes WBAN e o modelo de referência OSI**

As redes com tecnologia WBAN podem utilizar as três camadas do modelo de referência OSI da ISO que são: Física, Enlace e Rede.

**Camada Física:**

O meio utilizado para a comunicação entre sensores e central de monitoramento em uma WBAN são as ondas de rádio frequência. Por uma questão de custos e de operacionalidade para a alocação de canais, opta-se pela utilização da banda ISM (_**Industrial, Scientific and Medical**_) como principal meio de comunicação. A criação da banda ISM pelo FCC e sua desregulamentação do espectro de frequência, eliminou a necessidade de usuários e de organizações terem de pagar pelo uso destas faixas, de perder tempo com questões técnicas para o planejamento de uso e de evitar as interferências com sistemas de rádio existentes e pagos. O FCC então, liberou algumas faixas de frequências impondo certas restrições técnicas na potência irradiada e na modulação empregada. As faixas liberadas são (Santos Jr. 2012):

- 900 MHz (902 MHz a 928 MHz) - Possui uma largura de banda de 26 MHz com largura de 1Mbps.
- 2,4 GHz (2,400 GHz a 2,4835 GHz) - Essa faixa de frequência apresenta largura de banda de 83,5 MHz; é utilizada pelos equipamentos e dispositivos IEEE 802.11 “_b”_, “_g”_, “_n”_ e o “_ac”_, bem como o padrão IEEE 802.15 _(Bluetooth),_ fornos de micro-ondas e telefones sem fio.
- 5,0 GHz outra banda livre, sem a necessidade de licenciamento, dividido novamente em três faixas de operação, a saber:
    - Banda Baixa (5,15 GHz a 5,25 GHz) - O FCC especifica potência máxima de saída de 50mW para aplicações internas.
    - Banda Média (5,25 GHz a 5,35 GHz) - O FCC especifica potência máxima de saída de 250mW para aplicações internas e externas e pequenas distâncias.
    - Banda Alta (5,725 GHz a 5,825 GHz) - O FCC limita a potência máxima de transmissão na saída de 1000mW ou (1W) para aplicações externas em enlaces de rádio de grande distância.

A frequência na banda ISM utilizada neste estudo é a de 2,4GHz e esta faixa de frequência encontra-se atualmente congestionada em virtude dos vários serviços que utiliza e, sobretudo, os das redes _**WIFI**_.

No sentido de encontrar soluções devido do congestionamento da banda ISM, o FCC (_**Federal Communications Commission**_) nos Estados Unidos aprovou a alocação de uma largura de banda de 40 MHz de espectro exclusivamente para o uso na WBAN. Esta nova alocação encontra-se em uma nova faixa de frequência que vai de 2,360GHz a 2,400 GHz, os novos equipamentos que serão produzidos estarão inclusos em uma nova nomenclatura de funcionalidades designada como MBANs (_**Body Medical Area Networks**_) (Buckiewicz 2014).

O FCC pretende também expandir os serviços existentes de Radiocomunicação de Dispositivos Médicos, alocando a faixa de frequência de 2360 a 2390 MHz. Os dispositivos MBANs que utilizarão esta nova faixa irão operar sob uma base de "_**license by-rule**_" que elimina a necessidade de pedir certificação de emissão individual, porém, a utilização destes novos produtos restringe somente as operações internas em unidades de cuidados de saúde e estarão sujeitas ao registro e aprovação do FCC. Já a banda de 2,390GHz a 2,400 GHz não estará sujeita a registro e podem ser usadas em todas as áreas, incluindo nas residências e casas de repouso (Buckiewicz 2014).

Com estas novas frequências de operação ainda não exploradas, o IEEE (_**Institute of Electrical and Electronics Engineers**_) desenvolve um novo padrão designado como IEEE 802.15.6, que considera, além de um padrão único de transmissão, o suporte para a qualidade de serviço (_**QoS**_), o consumo de energia extremamente baixo e taxas de dados de até 10 Mbps quando necessárias. Ao mesmo tempo também abrange conformidade a não interferência nas comunicações de dispositivos de irradiação primária (FCC 2012).

Nestas novas diretrizes, o uso de antenas portáteis são elementos que devem ser considerados, principalmente devido à presença de pessoas (variando com o sexo masculino ou feminino, parâmetros físicos como magro, pesado). Neste estudo, o padrão de irradiação EIRP (_**Equivalent Isotropically Radiated Power**_) deverá ser minimizado em consideração à taxa de absorção específica SAR (_**SpecificAbsorption Rate**_), que é a medida dosimétrica utilizada para estabelecer limites à emissão de radiação por campos eletromagnéticos não ionizantes. O conceito de dose de energia absorvida por unidade de massa foi desenvolvido para estabelecer os limites para a radiação ionizante (Latré _**et al.**_ 2011).

**Camada de Enlace de Dados:**

Nas WBANs a eficiência no consumo de energia é de extrema importância para o tempo de vida dos sensores (Polastre _**et al**_. 2004). Neste contexto, vários critérios são propostos para minimizar o consumo de energia, como evitar colisão, diminuir o _**overhearing**_ (escuta inútil), controle do _**overhead**_ e _**idlelistening**_ (escuta ociosa, quando não há tráfego na rede). Nas arquiteturas de protocolos que são utilizados nas WBANs, uma das camadas de maior relevância é a MAC (_**Medium Access Control**_), pois os métodos de controle de acesso ao meio influenciam diretamente o consumo de energia dos dispositivos sensores. Este critério fica mais rigoroso quando sensores podem ser implantados ao corpo humano onde a substituição ou mesmo à recarga de baterias é algo impraticável. Portanto, nestes sensores e atuadores a durabilidade de uma bateria deve ser atendida por muitos meses ou anos (Van Dam _**et al.**_ 2003).

Pela relevância da camada MAC nas redes sem fio, duas categorias são largamente empregadas, são elas:

- Baseadas em contenção (CSMA/CA)
- Sem contenção (TDMA e polling)

As técnicas de acesso _**TDMA**_ e _**Polling**_ são as mais pesquisadas e empregas nos estudos das redes WBANs, mas também, algumas pesquisas e experimentos fazem uso do CSMA/CA - _**Carrier Sense Multiple Access/Collision Avoidance**_ (Weder 2010).

**Camada de Rede:**

Desenvolvimento de protocolos de roteamento eficientes para as WBANs não é uma tarefa fácil devido às características específicas do próprio ambiente. Em primeiro lugar, a largura de banda disponível para esta aplicação é limitada, compartilhada e pode variar muito devido ao desvanecimento do sinal associado ao ruído e as interferências do ambiente (Alam e Hamida 2014).

Embora muitas pesquisas estão sendo realizadas para a conservação da energia e a eficiência do roteamento de redes _**ad hoc**_ de sensores não médicos, principalmente com a utilização do campo ATIM _**(ad hoc Traffic Indication Message)**_ existente nos frames de _**Beacon,**_ infelizmente está perspectiva  mostrou-se inadequado para as WBANs (Latré _**et al. 2011)**_.

Como exemplo, a maioria dos protocolos para as redes de sensores sem fio considera apenas redes com sensores homogêneos do tipo um para um, onde muitos paradigmas da comunicação surgem. Em muitos casos, a rede é considerada estática. Em contraste com uma rede WBAN que tem dispositivos móveis e heterogêneos com rigorosos requisitos de tempo entre sensores e atuadores. Por conseguinte, são necessários protocolos especializados para WBAN que são subdivididos em duas categorias: os de encaminhamento baseado na temperatura do corpo do paciente e os baseados em _**cluster**_ (Latré _**et al**_. 2011).

### **Projetos Acadêmicos e Comerciais**

A utilização de redes de sensores para a aquisição dos sinais vitais é uma tendência no monitoramento da saúde humana, esta rede é designada WBAN e é formada por pequenos dispositivos eletrônicos independentes conhecidos como “nós” ou simplesmente sensores corporais. Estes pequenos sensores são dispositivos que possuem poder de processamento limitado que, geralmente faz uso de micro controladores, possui pouca memória e um sistema de rádio comunicação que trata das transmissões dos sinais coletados pelas ondas de rádio.

As sondas desenvolvidas são também dispositivos eletrônicos que coletam os sinais vitais, sejam eles, elétricos, calor, umidade ou pressão. Uma vez feita esta coleta, é função do micro controlador transformar estes dados em informação útil para posteriormente ser classificado em um nó central (Luís e Patsko 2006).

Os sensores que também incorporam atuadores devem executar esta parametrização e acionar diretamente os atuadores. Os atuadores são também dispositivos eletrônicos encarregados do fornecimento de insumos medicamentosos ao paciente. Um exemplo destes sensores com atuadores são os produtos da ACCU-CHEK, bem como outros desenvolvimentos em parceria com universidades e empresas. (Santos, 2015)

**Projeto ACCU-CHEK – Diabetes**

Um exemplo de sensores com atuadores  para o tratamento do diabetes _**Mellitus**_ tipo 1 onde este dispositivo possui uma sonda que tem a função de executar de forma invasiva a coleta de pequena quantidade de sangue denominado “destro” que, posteriormente, será mensurada e classificada pelo micro controlador. De posse da informação correta, o sistema de rádio enviará comandos ao atuador que, neste caso, trata-se de uma bomba de infusão, responsável pela administração da dosagem correta de insulina ao paciente. A Figura 1 ilustra o projeto.

Este sistema fisiológico é o que mais que se aproxima da função do pâncreas humano, com taxa basal (Taxa de Metabolismo Basal é a quantidade mínima de energia (calorias) necessária para manter as funções vitais do organismo em repouso) hora a hora (0,05 Unidade por hora) liberada em 20 intervalos por hora. Segundo o fabricante, este sistema consegue atender o perfil glicêmico de mais de 99% dos pacientes com diabetes do tipo I. A tecnologia WBAN atua neste sistema fornecendo a comunicação entre sensores e atuadores via padrão _**Bluetooth**_ IEEE 802.15.1. A Figura 2 ilustra o produto descrito (Accu-Chek 2015).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318084/21536.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318084/21536.png)

Figura 2 - Projeto ACCU-CHEK

Fonte: ACCU-CHEK, 2015

**Projeto MobiHealth**

Desenvolvido pela Comissão Europeia nos anos de 2002 e 2004, o _**Mobihealth**_ inicialmente destinava-se a criar uma plataforma de serviços para pacientes e profissionais de saúde, utilizando a comunicação via redes GPRF ou 3G. Posteriormente o projeto foi continuado pelo grupo de pesquisas holandês _**HealthService24**_ (de 2004 a 2008); nesta fase do projeto o foco foi no desenvolvimento de uma base de serviços sensíveis ao contexto do usuário, e à partir daí, o projeto passou a ser chamado de _**Freeband**_. Atualmente o projeto continua em desenvolvimento, mas agora visando potencial de mercado e conta atualmente com parcerias de hospitais, serviços médicos e empresas operadoras de telecomunicações.

O projeto _**MobiHealth**_ foi desenvolvido para o atendimento a várias áreas da saúde, como _**Home Care,**_ traumas, monitoramento de alto risco, e portadores de doenças crônicas. Basicamente um grupo de sensores (sendo cada sensor para uma coleta específica de dados clínicos) é instalado no corpo do paciente, e a comunicação entre sensores e sua unidade móvel (unidade central) é realizada por tecnologia _**Bluetooth**_ IEEE 802.15.1 que atualmente trata-se de um PDA _**(Personal Digital Assistant)**_ do fabricante HTC. Estes dados, uma vez recolhidos e codificados, podem ser encaminhados para um servidor de aplicação na Web pela rede GPRS ou 3G. A Figura 3 ilustra um sensor e estação base do projeto _**MobiHealth**_ (MobiHealth 2015).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318085/21538.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318085/21538.png)

Figura 3 - Projeto MobiHealth

Fonte: MobiHealth, 2015

**Projeto** _**UbiMon**_

O projeto Ubimon _**(Ubiquitous monitoring environment for wearable and implantable sensors ou Ambiente de Monitoração Onipresente para Sensores Vestíveis ou Implantáveis)**_ foi desenvolvido pelo Departamento de Computação do _**Imperial College (London, Inglaterra)**_ e tem como objetivo o sensoriamento em tempo real de pacientes não internados em hospitais e que estão exercendo suas atividades normalmente; o sistema considera não só os aspectos fisiológicos dos pacientes, mas também o contexto destas coletas. Esta diferenciação tem se tornado um dos maiores desafios do projeto, pois com o foco nas coletas das arritmias cardíacas pós-operatória, a identificação real de uma intercorrência no conglomerado das atividades do cotidiano do paciente é o grande desafio. Como exemplo, uma alteração nos sinais de ECG (eletrocardiograma) pode ser tanto devido à condição cardíaca do paciente quanto ao estresse físico e mental ao qual o paciente está submetido. Portanto, o projeto _**Ubimon**_ estuda a identificação destas anormalidades através de algoritmos de comparação. A Figura 4 ilustra algumas situações de captura dos sinais vitais em pacientes em suas atividades do dia a dia (Jwp _**et al. 2004)**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318088/21539.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318088/21539.png)

Figura 4 - Projeto Ubimon

Fonte: Wikipedia

A arquitetura do sistema é composta de uma unidade de processamento local formada por um telefone celular ou PDA com um cartão _**compact flash**_, responsável pela aquisição, análise e apresentação dos sinais pactados pelos sensores. Este dispositivo também é responsável por apresentar mensagens de alerta ao paciente no caso de intercorrência de alguma anormalidade dos sinais vitais. Os sinais vitais são coletados pelos sensores e transmitidos via cabo ou _**Bluetooth**_ IEEE 802.15.1 ao PDA e este, além da mensuração dos dados, tem a função de enviar via, rede GPRS ou 3G, as informações a um servidor central que permite que analistas, monitorem em tempo real as atividades diárias dos pacientes e podem alertá-los nos casos de uma intercorrência clínica (Jwp _**et al. 2004)**_.

**Projeto** _**Alarm-Net**_

O _**Alarm-net**_ foi desenvolvido pela Universidade da Virginia, e teve como objetivo principal o monitoramento em tempo real de idosos e pacientes com necessidades de cuidados médicos e terapêuticos. Por meio de uma rede de sensores sem fio instalados nos pacientes, consegue-se monitorar um histórico das condições médicas nos lares, observando tendências, identificando padrões e alterações na condição física dos pacientes observados. Os sensores são para a coleta de sinais vitais, mas também para a aquisição das condições ambientais do local onde reside a pessoa e, com estes dados, podem mensurar diversas condições a serem melhoradas como, temperatura ambiente, umidade, som, aspectos poluentes, iluminação e pressão, todos estes parâmetros são analisados no servidor central e acompanhados por monitores que podem a qualquer momento alarmar pacientes e familiares de alguma possível intercorrência (Souza e Mesquita 2013).

A arquitetura do projeto _**Alarm-Net**_ é ilustrada na Figura 5 em que um PDA recebe todas as informações do paciente transmitidas pelos sensores via _**Bluetooth**_ IEEE 802.15.1 que, depois de processar os valores, tem a capacidade de transmitir estas informações pelas redes GPRS ou 3G a um servidor central, para arquivamento em banco de dados e posteriores estudos das condições do referido paciente (Wood _**et al.**_ 2006).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/4/319405/21540.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/4/319405/21540.jpg)

Figura 5 - Projeto AlarmNet

Fonte: Souza e Mesquita, 2013

**Projeto** _**CodeBlue**_

O projeto _**CodeBlue**_ foi desenvolvido pela Universidade de Harvard com foco na infraestrutura de rede para sensores sem fio em aplicações médicas. O sistema possui suporte para uso em emergências, cuidados médicos em situações de desastres e reabilitação de pacientes com problemas cardíacos. O projeto atende a duas demandas, a primeira, pela rede de sensores para monitoramento de sinais vitais e registros médicos para uso em decisões nos tratamentos de saúde, e a segunda, a possibilidade da localização física dos pacientes e intercorrências pela rede de telefonia celular. Esta prerrogativa do projeto permite o atendimento de vítimas em desastres e acidentes, através da coleta de sinais vitais e localização dos pacientes durante o regaste. O sistema permite integrar estes dados com as informações de outros sistemas de saúde, possibilitando que o corpo clínico possa, remotamente, dar pareceres médicos e indicar o procedimento mais adequado. (Kim _**et al**_. 2013)

O _**CodeBlue**_ pode operar com diferentes tipos de sensores desde que estes possam enviar sinais vitais a um determinado intervalo de tempo. Estas informações podem ser transmitidas para um computador ou notebook através de cabos ou diretamente para os PDAs dos profissionais de saúde, através da comunicação _**wireless.**_ Os sensores devem transmitir na frequência de 433MHz para um PDA denominado Mestre devidamente preparado e deste a transmissão será via _**Bluetooth**_ IEEE 802.15.1, para um computador central como mostra a Figura 6.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/4/318423/21541.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/4/318423/21541.png)

Figura 6 - Esquema de Ligação Projeto CodeBlue

Fonte: Kim et al. 2013

Foi adotado um esquema de acesso múltiplo por divisão de tempo (TDMA) como implementação básica no mecanismo de sincronização de tempo entre os sensores. Em uma comunicação, o Mestre enviará um frame de requisição definido como um “super quadro” cuja função é a sincronização e o balizamento dos sensores com a intensão de evitar as colisões de quadros de informações. A Figura 7 ilustra esta distribuição de _**time slots**_, onde o “super quadro” é dividido em intervalos de 2049 _**time slots**_ com tempo de resposta de 2,4ms, permitindo assim a transmissão de pacotes de comprimento máximo de 61 bytes mais um período de segurança antes e depois para acomodar as instabilidades se existirem (Kim _**et al.**_ 2013).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/5/312529/21542.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/5/312529/21542.png)

Figura 7 - Super Quadro.

Fonte: Fonte: (Kim et al. 2013)

O projeto suporta o uso de sensores de oximetria, eletrocardiograma (ECG ou EKG), eletromiografia (EMG) e de movimentos, este último é empregado para avaliar a eficácia no tratamento de Parkinson e na reabilitação física após um acidente vascular cerebral (AVC). A Figura 8 ilustra alguns dos sensores desenvolvidos pelo projeto _**CodeBlue**_ (Souza e Mesquita 2013)_**.**_

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/9/319933/21543.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/9/319933/21543.png)

Figura 8 - Sensores CodeBlue

Fonte: Souza e Mesquita, 2013

**Projeto CSMA/CA –** _**Multiceiver**_

Desenvolvido por Santos (2015) o projeto utiliza na camada física o método de transmissão CSMA/CA e com todos os problemas relacionados aos altos índices de colisões, porém, o pesquisador fez uso do protocolo _**Multiceiver**_ com garantia de entrega e a criação de canais virtuais em apenas um canal físico verdadeiro. Com esta implementação consegue-se uma maior quantidade de sensores transmitindo em um número menor de canais físicos utilizados.

Outra contribuição de Santos (2015) foi a demonstração da utilização de canais com pouco tráfego dentro da banda ISM para o atendimento dos requisitos de congestionamento nesta faixa. Foram utilizadas frequências com pouco ou nenhum tráfego, frequências estas situadas acima do canal 11 para _**WIFI**_, ou seja, acima de 2,473GHz até o final da banda. No Brasil, a ANATEL (Agencia Nacional de Telecomunicações) em concordância ao FCC (_**Federal Communications Commission**_) não disponibiliza para uso comercial os canais 12, 13 e 14 (frequências de 2,456GHz, 2,461GHz e 2,466GHz respectivamente), lembrando que cada canal tem uma largura de banda de 22MHz e estão afastados 5MHz do início de cada um e, existindo apenas três canais não sobrepostos, com afastamento de 3MHz (canais 1, 6 e 11). A Figura 9 ilustra a canalização em 2,4GHz utilizada em WIFI (Medeiros 2007).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/5/312573/21544.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/5/312573/21544.png)

Figura 9 - Distribuição em 2,4GHz

Fonte: Fonte: Adaptado de (Santos Jr. 2012)

Portanto, frequências acima de 2,474GHz não serão encontradas transmissões das redes _**WIFI**_ que constituem mais de 90% do tráfego gerado (Medeiros 2007). Uma análise com o _**wifi-analyzer acrylic professional®**_ constatou numa captura que o espectro ISM acima do canal 4Ah está completamente vazio de transmissões. Uma imagem desta captura é retratada na Figura 10, que especifica a região de interesse para o estudo, que se encontra livre de transmissões.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/9/318939/21545.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/9/318939/21545.jpg)

FIGURA 10 - Detalhes da Área de Interesse no Scaneamento em 2,4GHz

Fonte: Santos, 2015

Uma análise mais apurada foi retratada na Figura 11, que mostra o espectro global da banda ISM de 2,4GHz. Para esta análise foi empregado o _**Data Analyzer Canalyzer**_ versão _**Lite**_ que confirma a área de interesse, livre de qualquer transmissão.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/3/319394/21546.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/3/319394/21546.png)

Figura 11 - Análise espectral.

Fonte: Santos, 2015

No trabalho de Santos (2015) foram desenvolvidos sensores operando em canais acima dos utilizados nas redes WIFI com um índice de colisão inferior a 2% de perda em 1000 pacotes transmitidos consecutivamente e, uma perda de dados clínicos real de 0% devido as retransmissões do protocolo _**Multiceiver**_. O trabalho deste pesquisador abriu novas possibilidades para o emprego do CSMA/CA de forma mais efetiva e os testes em laboratório resultaram em um consumo muito baixo (22,9mA para o sensor de batimento cardíaco em pleno funcionamento) com uma duração de 22 horas de transmissões consecutivas em intervalos de tempo de um segundo. A bateria utilizada nos testes foi de 700mA/hora recarregável e foi alcançado distancias de até 50 metros em espaço livre entre sensores. A imagem 12 a seguir ilustra os protótipos desenvolvidos por Santos (2015).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/6/319646/21547.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/9/6/319646/21547.jpg)

Figura 12 - Sensores Desenvolvidos.

Fonte: Santos, 2015

### **Requisitos para o Desenvolvimento das WBAN**

As aplicações que fazem uso do sensoriamento para fins médicos e de cuidados da saúde humana necessitam atender diversas demandas e requisitos. Estes requisitos têm como propósito garantir a confiabilidade, a segurança e a privacidade das informações coletadas, pois, delas depende a escolha do melhor tratamento ao paciente. Independentemente de os equipamentos serem protótipos ou dispositivos comerciais, devem atender a rigorosos requisitos de segurança aplicados pelas normas e pela legislação pertinente. No Brasil, a ANVISA (Agencia Nacional de Vigilância Sanitária) é a entidade responsável pela verificação e aprovação de qualquer equipamento ou dispositivo com finalidades ao uso em seres humanos. Qualquer empresa que deseja comercializar equipamentos para uso médico e terapêutico deverá requerer o referido registro. Por sua vez, a ANVISA exige que o fabricante do produto obtenha um certificado de conformidade técnica emitido pelo INMETRO (Instituto Nacional de Metrologia, qualidade e Tecnologia). A certificação irá comprovar, através de diversos tipos de ensaios em laboratórios credenciados, que o equipamento ou dispositivo eletro-médico atenda aos requisitos técnicos normativos de segurança elétrica, operação, documentação, produção e funcionalidade (ANVISA 2015). Antes de submeter o protótipo a apreciação da ANVISA, alguns desafios devem ser vencidos e superados na sua totalidade. São aqueles relacionados à garantia das seguintes características: confiabilidade, segurança e privacidade, sensibilidade ao contexto, energia, mobilidade e facilidade de uso.

### **Identificação por Radiofrequência – RFID**

A RFID é uma tecnologia de identificação que utiliza a radiofrequência, utilizada para identificação como no caso do sistema de código de barras, para capturar dados. A tecnologia surgiu inicialmente na década de 1980 como uma solução para os sistemas de rastreamento e controles de acesso. Os estudos avançaram e foi desenvolvido o Código Eletrônico de Produtos - EPC _**(Electronic Product Code).**_ O EPC definiu uma arquitetura de identificação de produtos que utilizava os recursos proporcionados pelos sinais de radiofrequência e que foi chamada posteriormente de RFID _**(Radio Frequency Identification)**_. (Pinheiro, 2004)

**Aplicações**

O RFID apresenta-se como uma solução para processos produtivos onde se deseja capturar as informações sobre produtos mesmo estes estando em movimento ou localidades insalubres onde o uso de etiquetas por código de barras não seria possível. Atualmente o grande diferencial da tecnologia é o uso em produtos que necessitam ser rastreados ou seguros como por exemplo os itens de lojas e supermercados.

Os equipamentos RFID podem operar em duas faixas de frequência, tem-se os sistemas de Baixa Frequência (30KHz a 500KHz) para curta distância de leitura e de baixo custo operacional. Normalmente utilizados para controles de acesso, rastreabilidade e identificação e os sistemas de Alta Frequência (850MHz a 950MHz e 2,4GHz a 2,5GHz) para leitura em médias e longas distâncias e leituras a alta velocidade. Normalmente utilizados para leitura de _**Tags**_ em veículos e coleta automática de dados utilizadas por exemplo nos pedágios de automóveis nas estradas.

**Funcionamento**

As etiquetas afixadas nos produtos são dotadas de um pequeno circuito eletrônico que são alimentados e rastreados por ondas de radiofrequência e, também são dotados de uma pequena antena de metal. Para transmissão de dados, as etiquetas respondem a sinais de rádio de um transmissor enviando de volta informações quanto a sua localização e identificação. Estes dados captados pelos receptores são identificados e parametrizados servindo assim como base de dados para uma infinidade de aplicações. A figura 13 ilustra uma aplicação para as etiquetas RFID.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318091/21548.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318091/21548.png)

Figura 13 - Equipamentos RFID

Fonte: Flickr

### **Revisão:**

- A tecnologia WBAN ainda é embrionária, porém, quando alcançar sua plenitude poderá favorecer muitos pacientes nos mais diversos acometimentos de saúde.
- Muitas técnicas de transmissão estão em estudo, onde, as mais pesquisadas são o TDMA, _Polling_ e o CSMA/CA. Também se tem encontrado pesquisas utilizando os padrões existentes como o WIFI.
- A tecnologia WBAN será cada vez mais utilizada, pois, a humanidade com os avanços da medicina e dos fármacos está cada vez mais tento mais anos de vida e a tecnologia vai auxiliar médicos e cuidadores no trato destas pessoas.
- Os estudos continuam e queremos crer que em muito poucos anos, já devemos ser invadidos por uma legião de equipamentos e sistemas que vão contribuir ainda mais para o cuidado de pacientes.