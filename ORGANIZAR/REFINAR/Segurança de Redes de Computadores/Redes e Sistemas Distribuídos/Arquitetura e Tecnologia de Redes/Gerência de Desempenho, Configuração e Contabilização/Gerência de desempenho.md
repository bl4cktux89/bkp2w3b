[![](https://ampli-images.s3.amazonaws.com/production/bac03491-3eed-40e5-91d8-0d7e1313b2bf/original)](https://ampli-images.s3.amazonaws.com/production/bac03491-3eed-40e5-91d8-0d7e1313b2bf/original)

Nesta terceira e última aula da unidade de **Arquitetura e tecnologia de redes**, conheceremos as áreas que formam o gerenciamento de redes e nos aprofundaremos na gerência de desempenho. Trabalharemos conceitos e aplicações da análise e configuração de redes e utilizaremos o protocolo VLAN _Trunk Protocol_ como estratégia para gestão de redes e o SSH (_Secure Shell_) como ferramenta de gestão e acesso remoto em redes de computadores.

Forouzan (2010) define gerenciamento de redes como o monitoramento, o teste, a configuração e o diagnóstico de componentes de rede para atender a um conjunto de exigências definidas por uma organização. As exigências relacionam-se com a operação estável e eficiente da rede que fornece a qualidade predefinida de serviços aos seus usuários.

Ainda de acordo com o autor, o gerenciamento de redes abarca cinco áreas, conforme descritas a seguir:

- **Gerenciamento de configuração**: sistema utilizado para conhecimento sobre o estado de cada entidade da rede e sua relação com as outras entidades. Este gerenciamento pode ser um subsistema de reconfiguração ou de documentação. Na reconfiguração, há o ajuste dos componentes e das características da rede no que se refere ao hardware, ao software e às contas de usuários. Já na documentação há o registro das configurações da rede sobre o hardware, o software e as contas de usuário.
- **Gerenciamento de falhas**: relaciona-se à área do gerenciamento que trata das falhas de rede através de dois subsistemas: um reativo e outro proativo. No subsistema reativo, existe a detecção, o isolamento, a correção e o registro de falhas. No subsistema proativo, o sistema procura impedir a ocorrência de falhas.
- **Gerenciamento de desempenho**: esta área está relacionada ao gerenciamento de falhas e tenta monitorar e controlar a rede para garantir que ela seja executada de forma eficiente. Conforme sustenta Forouzan (2010), esta área busca quantificar o desempenho de uma rede de computadores usando quantidades mensuráveis, como: capacidade, _throughput_ (vazão), tráfego e tempo de resposta (latência). A capacidade da rede deve ser monitorada, porque as redes possuem capacidades de infraestrutura, hardware e software limitadas; o tráfego também necessita de monitoramento interno e externo, medido pelo número de pacotes transmitidos (no tráfego interno) e pela troca de pacotes (no tráfego externo); o _throughput_ de um dispositivo (roteador, por exemplo) pode ser medido para analisar a performance da rede; e o tempo de resposta é medido durante a transmissão e obedece a parâmetros mínimos de retorno. Adicionalmente, o _Jitter_, que é uma medida de variação no atraso da transferência de dados e a perda de pacotes também influenciam no desempenho da rede.
- **Gerenciamento de segurança**: é a área responsável pelo controle de acesso à rede e considera uma política de rede predefinida pela empresa. Tem relação com os sistemas de segurança computacional e prevê a utilização de sistemas de proteção à rede para monitoramento de ameaças e ataques. Neste gerenciamento, são consideradas questões de ameaças, ataques e vulnerabilidade de sistemas e utilizam-se dispositivos, como firewall, _Intrusion Detection Systems_ (IDS), _Intrusion Prevention Systems_ (IPS), sistemas de monitoramento e captura de dados de rede, como os farejadores, ou _sniffers_, e sistemas de monitoramento em geral.
- **Gerenciamento de contabilização**: é a área relacionada à quantificação do acesso e à utilização de recursos de rede pelos usuários, departamentos ou divisões. Este gerenciamento é importante para que usuários não monopolizem recursos da rede, impedir que o sistema seja utilizado de forma ineficiente e para que os administradores da rede possam analisar sua utilização e desenvolver planos sobre o uso da rede, conforme sua demanda. Firewalls, IDS, IPS, sistemas farejadores e monitoramento auxiliam também nesta atividade.

______

**🔁Assimile**

Os princípios do gerenciamento de rede são definidos por Kurose e Ross (2013) através de três atividades:

- Coleta de dados: refere-se à coleta de dados da rede, realizada por um sistema de _sniffig_¸ por exemplo.
- Análise e diagnóstico: refere-se à organização dos dados coletados na rede para tomada de decisão de forma manual ou utilizando softwares específicos.
- Controle: refere-se a ações para a gestão da rede, a fim de cessar, mitigar ou minimizar os impactos de informações trafegadas na rede.

______

**Sniffer**

Um sistema de _sniffig_, ou uma aplicação _sniffer_, é um aplicativo de software que busca realizar a análise e interceptação do registro de dados de um sistema de redes de computadores. São aplicativos que auxiliam os administradores de rede na análise do tráfego da rede e na checagem da sua performance mediante os parâmetros de operação estabelecidos. Estas ferramentas permitem também controlar o tráfego de um dispositivo de rede e capturar dados das transmissões nela realizadas. Os aplicativos que realizam estas atividades são chamados de farejadores e executam um algoritmo que captura fluxos de dados especificados pelos gestores de sistemas da empresa em sua configuração através de e-mail, login, texto e históricos de acesso à internet, por exemplo. A Figura 2.38 apresenta um exemplo de tela de uma ferramenta _sniffig_, o _Wireshark_.

Estas ferramentas representam, por um lado, um aliado ao gestor de redes de computadores, pois analisam e geram relatórios de análise da rede, porém também podem representar um ponto de atenção, porque representam uma ferramenta que impacta a vulnerabilidade de sistemas e trazem questões contra a segurança da rede.

______

**📝****Exemplificando**

Alguns programas estão disponíveis para download e implantação de aplicativos de _sniffig_ de forma livre. A seguir, apresenta-se dois exemplos de aplicativos que podem ser utilizados para análise e captura de dados da rede.

A figura abaixo demonstra uma tela inicial da interface gráfica da ferramenta Wireshark. A ferramenta permite que se filtrem informações clicando nas interfaces ou informando-as.

[![](https://ampli-images.s3.amazonaws.com/production/8e25fd39-5c63-4de5-8ab8-3a5272b601b3/original)](https://ampli-images.s3.amazonaws.com/production/8e25fd39-5c63-4de5-8ab8-3a5272b601b3/original)

Tela de informações do Wireshark. Fonte: Wikimedia Commons.