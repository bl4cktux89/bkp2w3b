# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/1f326556-bfff-4971-aee1-499f3301b824/original)](https://ampli-images.s3.amazonaws.com/production/1f326556-bfff-4971-aee1-499f3301b824/original)

### **Qual é o foco da aula?**

Na segunda aula desta unidade, vamos compreender os conceitos de SIC, as normas de segurança da família 2700 e mecanismos de segurança.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer o modelo PDCA aplicado aos processos do SGSI;
- examinar a descrição do ciclo PDCA no SGSI ;
- interpretar os tipos de ataques cibernéticos.

### **Situação-problema**

Estudante, depois de ajudar o nosso amigo Fernando Bezerra, aquele analista de riscos da rede e dos sistemas de segurança pública da SSPMG, a resolver os problemas do pequeno município de Caratinga, ele pensou que poderia conduzir sua rotina normalmente, mas não foi bem assim. Logo no dia seguinte, ele recebeu uma mensagem pelo WhatsApp de seu amigo da Faculdade de Sistemas de Informação, Flávio Damasco, que trabalhava na mesma função que Fernando só que na iniciativa privada. Flávio comentava que o sistema de controle de acesso e cadastro de funcionários, visitantes e prestadores de serviços do Condomínio de Escritórios Inteligentes Gallery, na cidade de Vespasiano – MG, havia sido invadido por hackers. Flávio Damasco ligou para Fernando para que juntos pudessem analisar o tipo de invasão. Fernando ficou preocupado, matutando os seguintes questionamentos: se o sistema do Condomínio de Escritórios Gallery, que tem uma quantidade imensa de recursos, foi invadido, será que os sistemas da SSPMG também poderiam sofrer os mesmos ataques? Será que não existe nenhum sistema totalmente seguro? Essa invasão de sistemas que têm dados de altos executivos poderia causar alguma consequência maior para os resultados da criminalidade? O que teria de ser analisado e implantado por Fernando e Flávio para garantir a segurança?

Essa missão não será fácil e, para cumpri-la, você precisará ter entendido muito bem os conceitos básicos de segurança da informação, conhecido as normas e padronizações referentes à segurança da informação, conseguido identificar as ameaças mais comuns à segurança da informação e empregado corretamente os mecanismos de defesa e segurança da informação na Segurança Pública e Privada. Nesse contexto, vamos ajudar nossos personagens, Fernando e Flávio, a resolverem seus conflitos? Perceba que, ao responder os questionamentos aqui apresentados, você estará promovendo uma análise de alguns problemas encontrados na Segurança Pública, relativos aos aspectos da Segurança da Informação. Apresente esta análise através de um relatório.

Agora, estudaremos alguns conceitos.

# **SIC**

[![](https://ampli-images.s3.amazonaws.com/production/a05ce482-fef7-4d04-9ebb-f0fa10b47556/original)](https://ampli-images.s3.amazonaws.com/production/a05ce482-fef7-4d04-9ebb-f0fa10b47556/original)

Após termos aprendido a Gestão Estratégica da Informação, prosseguiremos na nossa missão, estudando a Segurança da Informação, um tema bastante latente atualmente, que indica a crescente importância desta atividade na manutenção da informação e na rotina das pessoas e empresas. Vamos começar compreendendo alguns conceitos fundamentais em Segurança da Informação, o primeiro deles será o próprio conceito de Segurança da Informação e Comunicações (SIC), que nada mais é do que a proteção da informação, no sentido de preservar o valor que ela representa para um indivíduo ou uma organização. Além disso, segundo a Norma ABNT ISO/IEC 27002 (2013), Segurança da Informação é a proteção da informação das várias ameaças, para garantir a continuidade do negócio, diminuir o risco e aumentar os lucros e as oportunidades de negócio. A segurança da informação é obtida por meio da implantação de um conjunto de medidas que envolve pessoas, processos e tecnologias, visando garantir a disponibilidade, integridade, confidencialidade, autenticidade e irretratabilidade ou não-repúdio da informação. Essas características são conhecidas também como atributos de uma informação segura ou princípios de segurança da informação. A seguir, detalharemos cada um deles:

- **Disponibilidade**: é a qualidade da informação estar sempre acessível e em condições de ser utilizada pelo usuário autorizado.
- **Integridade**: é a garantia de que a informação não foi alterada, mantendo suas características originais.
- **Confidencialidade**: é a propriedade de que a informação será acessada somente por usuários autorizados, evitando seu conhecimento ou sua divulgação a pessoas sem permissão.
- **Autenticidade**: é a garantia de que a informação foi originada na fonte anunciada, ou seja, que a informação foi produzida por quem diz tê-la produzido.
- **Irretratabilidade ou não-repúdio**: é a característica de não poder negar ações referentes à informação, isto é, o usuário não conseguir negar que enviou a informação, ou a acessou, ou a modificou, ou a copiou, ou a destruiu, ou etc.

_______

**🔁 Assimile**

Segurança da Informação e Comunicações (SIC) significa proteger a informação preservando seu valor e garantindo os princípios da disponibilidade, integridade, confidencialidade, autenticidade e irretratabilidade.

_______

Fazer a segurança da informação (SIC) envolve reconhecer exatamente o valor da informação e como está sendo feita sua gestão (GI) para identificar possíveis vulnerabilidades ou fragilidades nesse processo; como essas vulnerabilidades podem ser exploradas; e quais ameaças podem investir sobre a informação, valendo-se das vulnerabilidades, podendo causar um evento, um incidente ou uma catástrofe de segurança da informação. Dessa forma, conceituaremos melhor o que vem a ser estas três situações decorrentes da ação das ameaças sobre as informações.

- **Evento de segurança da informação**: qualquer fato ocorrido em relação à informação que infringe um princípio da segurança, mas sem causar maiores consequências para a empresa. Ex.: uma falta de energia elétrica deixa a informação indisponível temporariamente.
- **Incidente de segurança da informação**: é uma ocorrência que viola um ou mais princípios da segurança da informação, via de regra, intencionalmente, e que compromete o negócio ou a atividade da organização gerando consequências indesejáveis e prejudiciais. Ex.: um ataque de negação de serviço a um site de comércio eletrônico, interrompendo propositalmente as vendas pela internet e gerando prejuízos.
- **Catástrofe de segurança da informação**: é um incidente de grandes proporções, inviabilizando quase ou permanentemente a atividade da organização. Ex.: o atentado de 11 de setembro de 2001 às Torres Gêmeas, nos EUA, causou a destruição dos principais bancos de dados (_Data Warehouse_) de uma ou duas grandes financeiras americanas, simplesmente extinguindo as atividades delas no mercado.

Ainda sobre os conceitos de SIC, o conjunto de medidas para obter a segurança da informação, citado anteriormente, envolve a Segurança física ou do ambiente, a Segurança lógica ou Controle de acesso, a Segurança da rede ou da transmissão, e a Segurança do armazenamento. A saber:

- **Segurança física**: preocupa-se em evitar o acesso físico às instalações e informações da organização por indivíduos não autorizados ou estranhos à empresa.
- **Segurança lógica**: visa garantir que o acesso à informação eletrônica seja feito dentro dos princípios da SIC. É implementado através de senhas, níveis de acesso e privilégios, etc.
- **Segurança da rede**: consiste em estratégias e políticas – implementadas através de softwares, hardwares e procedimentos – adotadas para impedir o acesso não autorizado, o uso indevido, a modificação ou a negação de serviço durante a transmissão da informação pela rede.
- **Segurança no armazenamento**: é um conjunto de medidas que visa preservar a informação que estiver guardada, envolvendo cópias de segurança (backup), dispositivos de armazenamento (fitas, discos, cartões SD, nuvem, CD/DVD) e redundância de dados.

Para finalizar essa primeira parte da nossa aula, cabe destacar que, em uma organização, deve existir um documento que registre as diretrizes de SIC a serem adotadas pela empresa e que devem ser observadas por todos seus integrantes e colaboradores e, inclusive, aplicada a todos seus sistemas de informação e processos corporativos. Este documento é chamado de **Política de Segurança da Informação (POSIC)** e estabelece o conjunto de regras e critérios para implantação da SIC na organização, sendo o documento mais importante dentro do sistema de segurança da informação, justamente por estabelecer o que será segurado e como a segurança será realizada.

# **ABNT NBR ISO/IEC 27000**

[![](https://ampli-images.s3.amazonaws.com/production/bd6e42d1-a3af-448d-843d-5ed7331f57d4/original)](https://ampli-images.s3.amazonaws.com/production/bd6e42d1-a3af-448d-843d-5ed7331f57d4/original)

Tudo que nós aprendemos até agora está previsto, descrito e detalhado em uma série de normas e padronizações sobre a Segurança da Informação. As principais normas são as ABNT NBR ISO/IEC da família 27000, que praticamente padronizam toda a atividade relativa à SIC, no Brasil, e cujo estudo, de pelo menos algumas delas, é obrigatório para os profissionais de segurança da informação.

Neste aspecto é importante informar que não existe nenhuma distinção sobre a aplicação das normas na Segurança Pública ou Privada, mas, na verdade, elas são seguidas por quase todas as pessoas e organizações que praticam a SIC de forma séria e consciente. Além das certificações emitidas pela ABNT, é claro, que sempre agregam valor às práticas da empresa, projetando seu nome no mercado e ampliando sua vantagem competitiva.

A família ABNT NBR ISO/IEC 27000 é composta por mais de quarenta normas, sendo a maioria delas direcionada a objetivos específicos dentro da SIC. Contudo, duas delas formam a base para uma SIC bem estruturada e eficiente, são as normas ABNT NBR ISO/IEC 27001:2013 e ABNT NBR ISO/IEC 27002:2013, as quais veremos sucintamente.

A ABNT ISO/IEC 27001:2013 define os requisitos para um Sistema de Gestão da Segurança da Informação (SGSI), apresentando um modelo para estabelecer; implementar e operar; monitorar e analisar criticamente; e manter e melhorar um SGSI. O SGSI deve também atender às necessidades, aos objetivos, aos requisitos de segurança, aos processos e ao tamanho e à estrutura da organização. A 27001 se baseia no ciclo PDCA (_Plan-DoCheck-Act_ ou Planejar-Executar-Verificar-Atuar) para organizar os processos do SGSI (Figura e Tabela abaixo) (ABNT 27001, 2013).

[![](https://ampli-images.s3.amazonaws.com/production/a9e1d7a7-e8a0-407a-9622-2bc45eb06eee/original)](https://ampli-images.s3.amazonaws.com/production/a9e1d7a7-e8a0-407a-9622-2bc45eb06eee/original)

Modelo PDCA aplicado aos processos do SGSI. Fonte: ABNT NBR ISO/IEC 27001 (2013).

[![](https://ampli-images.s3.amazonaws.com/production/087dc757-cf9d-4340-ab01-defc670ace9b/original)](https://ampli-images.s3.amazonaws.com/production/087dc757-cf9d-4340-ab01-defc670ace9b/original)

Descrição do ciclo PDCA no SGSI. Fonte: ABNT NBR ISO/IEC 27001 (2013).

Já a norma ABNT NBR ISO/IEC 27002:2013 apresenta um Código de Prática para a Gestão da Segurança da Informação, ou seja, a norma é um guia para implantação da segurança da informação na organização, operacionalizando o SGSI descrito na 27001 e estabelecendo os objetivos de controle e controles para o tratamento dos riscos que deverão ser gerenciados. Esses objetivos e controles são descritos em onze seções da 27002, a saber:

- Política de Segurança da Informação.
- Organização da Segurança da Informação.
- Gestão de Ativos.
- Segurança em Recursos Humanos.
- Segurança Física e do Ambiente.
- Gestão das Operações e Comunicações.
- Controle de Acesso.
- Aquisição, Desenvolvimento e Manutenção de Sistemas de
- Informação.
- Gestão de Incidentes de Segurança da Informação.
- Gestão da Continuidade do Negócio.
- Conformidade.

Complementando essa parte sobre normas e padronizações de Segurança da Informação, existem legislações que tratam especificamente deste assunto no âmbito da Administração Pública Federal (APF), e todas elas estão citadas na Estratégia de Segurança da Informação e Comunicações e de Segurança Cibernética da Administração Pública Federal 2015-2018: versão 1.0. Este documento estabelece objetivos e metas estratégicas de SIC e Defesa Cibernética para os órgãos públicos federais até 2018. Dentre todas as legislações citadas na Estratégia, duas merecem destaque, são elas o Decreto nº 3.505, de 13 de junho de 2000, que institui a Política de Segurança da Informação nos órgãos e nas entidades da Administração Pública Federal, e a Instrução Normativa (IN) GSI/PR nº 1, de 13 de junho de 2008, que disciplina a Gestão de Segurança da Informação e Comunicações na Administração Pública Federal. Em linhas gerais, o Decreto nº 3505 determina a implantação da POSIC em todos os órgãos e entidades da APF, com o objetivo básico de garantir o direito à inviolabilidade da intimidade das pessoas e do sigilo das suas comunicações, desenvolvendo e empregando meios de segurança da informação, como forma de manter a soberania do Estado Brasileiro; e a IN nº 1 veio para regulamentar a Gestão de Segurança da Informação e Comunicações (GSIC) da APF, padronizando procedimentos e atribuindo responsabilidades e competências a órgãos específicos. A IN tem ainda várias Normas Complementares (NC) que definem procedimentos específicos em relação à SIC na APF, por exemplo, a NC nº 2, que trata da Metodologia de Gestão de Segurança da Informação e Comunicações.

Como vimos, existem as normas ABNT que padronizam procedimentos em relação à SIC, como forma de apontar as melhores práticas nessa atividade, mas não são de cunho obrigatório; e existem legislações que tratam do assunto no âmbito da Administração Pública Federal e estas sim são determinações que devem impositivamente serem cumpridas por esses órgãos.

Agora que conhecemos algumas normas e padronizações, faremos uma abordagem sobre as ameaças mais comuns. Como dito anteriormente, a SIC será comprometida sempre que uma ameaça conseguir explorar uma vulnerabilidade da informação, violando seus atributos de segurança.

De forma geral, existem quatro formas de ataque à segurança da informação (Figura abaixo):

- **Interrupção**: deixa a informação indisponível, não sendo possível acessá-la.
- **Modificação**: quando a informação sofre algum tipo de alteração não autorizada, violando sua integridade.
- **Interceptação**: quando o sigilo da informação é quebrado, ou seja, quando usuários não autorizados acessam a informação.
- **Fabricação**: quando uma informação é “plantada” por uma fonte ilícita, fazendo se passar por uma fonte fidedigna.

[![](https://ampli-images.s3.amazonaws.com/production/a51ba381-88e5-44e9-b34f-cdcf84b9972a/original)](https://ampli-images.s3.amazonaws.com/production/a51ba381-88e5-44e9-b34f-cdcf84b9972a/original)

Tipos de ataques. Fonte: elaborada pelo autor.

Quando se fala em ameaças à segurança da informação aparece um emaranhado de palavras que, por si só, parecem assustadoras, como: vírus, _worms,_ spam_, bots, botnets, exploits, backdoors, brute force, trojan, spywares, malware, keyloggers, screenloggers, sniffers, spoofing, phishing, DoS, DDoS_. Na verdade, tudo isso tem a ver com ataques cibernéticos, desde simples furtos de senhas de usuários comuns até importantes investidas contra bancos de dados de informações críticas de grandes empresas.

_______

**💭 Reflita**

E você, estudante, já pensou em como todas essas ameaças, e outras, podem agir sobre suas informações? Quais são suas informações mais valiosas? Elas estão seguras? Quais são as vulnerabilidades delas? Você toma alguma medida para protegê-las? Hoje em dia, nós temos que nos preocupar com essas questões. Você não acha?

_______

No entanto, uma coisa é certa, esse tipo de violação da segurança da informação vem crescendo e se diversificando bastante com o passar dos anos e, sinceramente, já está difícil conseguir identificar todo tipo de ameaça que existe por aí. O que se faz atualmente e tem se mostrado uma boa prática é acompanhar quais são as ameaças que mais estão agindo no espaço cibernético e planejar a SIC de acordo com essas tendências. É relativamente fácil identificar essas ameaças, podemos consultar estatísticas de incidentes de segurança da informação no portal do Centro de Estudos, Respostas e Tratamento de Incidentes de Segurança no Brasil (CERT.br). Neste sítio, podemos identificar, por exemplo, que as ameaças mais comuns, em 2015, foram os _**worms**_, tipo de verme cibernético muito pior que os vírus porque se propagam rapidamente pelas redes, infectando computadores e executando seus códigos maliciosos; os _**DoS**_, ataques de negação de serviço (Denial of Service), impedindo a transmissão de informações; as **invasões**, acessos não autorizados a uma rede ou sistema computacional; os **web**, ações de desfigurar uma página ou comprometer um sítio na internet; os _**scan**_, ações de caçar, por varredura, as vulnerabilidades existentes em redes de computadores para selecionar possíveis alvos; e as **fraudes**, tentativas de obter vantagem lesando pessoas e organizações (Gráfico abaixo) (CERT.BR, 2015).

[![](https://ampli-images.s3.amazonaws.com/production/d1aea489-42c4-438e-a400-d9a525bf4426/original)](https://ampli-images.s3.amazonaws.com/production/d1aea489-42c4-438e-a400-d9a525bf4426/original)

Incidentes reportados ao CERT.br por tipos de ataque. Fonte: Cert.br

# **Mecanismos de segurança**

[![](https://ampli-images.s3.amazonaws.com/production/145f854a-84d1-4144-ae81-d1d6290a36b2/original)](https://ampli-images.s3.amazonaws.com/production/145f854a-84d1-4144-ae81-d1d6290a36b2/original)

Realmente não está fácil manter uma informação segura neste ambiente tão hostil e impiedoso no qual vivemos atualmente. Mas sempre existe uma forma de conseguir vencer esses adversários invisíveis e astuciosos. É o que passaremos a estudar a partir de agora, isto é, as defesas e os mecanismos de segurança da Segurança Pública e Privada. O setor público combate às ameaças, normalmente, criando leis que criminalizam as práticas de ataque à informação; já o setor privado se encarrega de desenvolver ferramentas para combater as ameaças. Os mecanismos de defesa mais utilizados são sempre os mesmos, tanto faz se no âmbito da coisa pública ou privada. Vejamos, portanto, alguns deles.

- **Política de segurança da informação**: é o documento mestre de toda estratégia de segurança, porque prevê que informação deve estar segura, como deve ser feita a segurança, que meios serão empregados e, principalmente, dispõe sobre a atitude das pessoas em relação à SIC, prevendo, muitas vezes, punições em caso de não cumprimento do previsto.
- **Atualização de softwares**: é muito importante para a SIC que a infraestrutura na qual a informação circula esteja sempre livre de bugs e vulnerabilidades. Dessa forma, deve-se atualizar periodicamente o sistema operacional e os aplicativos de computador.
- **Controle de acesso**: medida que visa evitar acesso não autorizado à informação, pode ser físico, determinando quem pode acessar as dependências da organização; e lógico, implementado por meio de contas, senhas e privilégios de acesso.
- **Antivírus, AntiSpam e AntiSpyware**: são softwares que protegem o sistema computacional de ataques desses malwares, evitando problemas diversos com a SIC.
- **Cópias de segurança (backup)**: previnem contra a perda de dados e informações decorrentes tanto de ataques intencionais quanto de falhas de hardware, software e peopleware.
- **Firewall**: é o dispositivo que aplica as regras da POSIC na rede interna da organização, protegendo a transmissão de informações entre a rede privada da empresa e a pública (internet).
- **Criptografia**: além de ser uma técnica de ocultação da informação, a criptografia vem se mostrando como uma das mais poderosas ferramentas para a SIC, sendo empregada para garantir de forma muito eficaz a integridade, confidencialidade e autenticidade das informações, através do uso de certificados e assinaturas digitais, protegendo praticamente todos os atributos de violação da informação.
- **Biometria**: é a técnica de usar características físicas únicas (impressão digital, íris, pressão arterial, voz, DNA) para identificar um indivíduo no controle de acesso, eliminando a possibilidade de uma pessoa utilizar a senha ou o cartão de acesso de outrem; também vem sendo bastante empregada na SIC, particularmente, contra a irretratabilidade.
- **Registro de eventos (Log)**: é a prática de registrar os fatos ocorridos em um sistema computacional e armazená-los em arquivos, chamados logs, mantendo-se um histórico de tudo que aconteceu com a informação durante sua circulação pela infraestrutura de TIC, possibilitando o monitoramento das atividades dos sistemas de informação e a averiguação dos eventos e incidentes de segurança.

A despeito de todos esses mecanismos de defesa, deve se ter especial atenção com o principal responsável pelo comprometimento da segurança da informação em uma organização, qual seja, o usuário. Já foi comprovado por diversas pesquisas e estatísticas que o **usuário** é a maior falha de segurança que existe, por isso, atuar sistematicamente sobre ele é uma ótima prática no contexto da SIC. Devemos manter uma rotina constante de conscientização do usuário sobre a segurança da informação, promovendo campanhas e workshops que realmente tragam esse assunto para seu dia a dia, alertando-o sobre os riscos de deixar uma porta aberta, um documento em cima da mesa, largar o smartphone em qualquer lugar, divulgar dados pessoais na internet (e-mail, telefone, endereço, nome de familiares, rotina diária, viagens, etc.), acessar links de e-mails ou sites escusos na internet, compartilhar senhas de acesso com colegas de trabalho, tratar de assuntos de trabalho em ambiente inadequado (ônibus, táxi, bar, academia) e muitos outros.

_______

**📝 Exemplificando**

A título de ilustração da importância do usuário na segurança da informação, podemos citar o caso do vazamento das informações da Agência de Segurança Nacional Norte-Americana (NSA) pelo site WeakLeaks, que ganhou repercussão mundial, inclusive, com reflexos no Brasil, por causa do acesso às mensagens eletrônicas da Presidente Dilma. O responsável pela publicação das informações secretas foi o ex-técnico da CIA, Edward Snowden, que burlou todos os mecanismos de defesa da NSA, contando apenas com a contribuição de um funcionário da agência que acessou fisicamente as informações em seu local de trabalho.

_______

Assim, após termos passado por todo esse conteúdo, encerramos mais uma aula da nossa unidade de ensino e podemos partir para a próxima atividade.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/f1b351e2-f3e4-4993-b379-d2cf7ca25bc1/original)](https://ampli-images.s3.amazonaws.com/production/f1b351e2-f3e4-4993-b379-d2cf7ca25bc1/original)

Com os conhecimentos adquiridos nesta aula, podemos agora ajudar Fernando e o Flávio a manter seus sistemas e informações em segurança, não é mesmo? Vamos a solução da nossa SP, lembrando que, ao responder os questionamentos, você estará realizando uma análise dos de alguns problemas vivenciados na Segurança Pública e Privada sobre a ótica da Segurança da Informação. Assim como ocorreu a invasão no sistema de controle de acesso do Condomínio de Escritórios Gallery, violando, com certeza, a confidencialidade das informações, também poderia ocorrer uma invasão aos sistemas da SSPMG. Você se lembra que, segundo as estatísticas do CERT. br, a invasão é uma das ameaças mais comuns no Brasil? Esse tipo de ataque acontece simplesmente porque não existe sistema totalmente seguro ou segurança 100% eficaz, isto é, não existe sistema sem informações de valor, ou sem vulnerabilidades, ou sem estar exposto a nenhuma ameaça. Mas, as invasões acontecem, principalmente, porque existem sistemas sem uma Segurança da Informação e Comunicações - SIC adequada, ou com uma SIC mal dimensionada, deixando de lado as recomendações e a padronização que vimos nas normas ABNT e legislações correlatas. E, é claro, que algumas ações desse tipo acabam refletindo no aumento da criminalidade, tanto na criminalidade cibernética quanto na criminalidade comum, materializada na forma de sequestros de executivos e assaltos às empresas que tiveram suas informações vazadas ou expostas. Mediante essa situação e na intenção de prevenir suas organizações contra esse tipo de infortúnio, Fernando e Flávio devem adotar um Sistema de Gestão da Segurança da Informação, conforme descrito na ABNT NBR ISO/IEC 27001:2013, para garantir o planejamento, a implementação, a manutenção e a melhoria constante da SIC sob sua responsabilidade. Para tanto, devem analisar criteriosamente quais são as informações sensíveis das suas organizações, levantando as vulnerabilidades na manipulação dessas informações e que tipos de ameaça podem explorar essas vulnerabilidades.

Dessa forma, devem planejar a segurança física, lógica, da rede e de armazenamento, empregando mecanismos de defesa, como: firewall, controle de acesso, backup, logs e outros, tudo para manter essas informações seguras. Por fim, devem descrever isso tudo em uma Política de Segurança da Informação a ser adotada na organização e seguida por todos seus integrantes e colaboradores, assim como prevê a ABNT NBR ISSO/IEC 27002:2013. Não esqueçamos que para Flávio tudo isso não passa de diretrizes, recomendações e melhores práticas que a empresa dele pode optar por seguir; mas para Fernando é diferente, porque a SSPMG é um órgão de Segurança Pública e, apesar de ser do Estado de Minas Gerais e não Federal, também tem de seguir suas legislações próprias, sendo bom que ele se informe sobre elas para não deixar de cumprir alguma imposição legal no desempenho de suas atividades.

Feito isso, formate as respostas anteriormente dadas aos questionamentos apresentados no Diálogo Aberto, e fique consciente de que podemos, sim, proteger nossos sistemas, mantendo a disponibilidade, integridade, confidencialidade e autenticidade das nossas informações. Com o mínimo de vulnerabilidades e resguardadas das ameaças, podemos avançar na nossa prática, resolvendo mais uma situação-problema.