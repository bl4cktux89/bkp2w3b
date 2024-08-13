### Introdução

Quando se fala de novas tecnologias e o crescimento delas na atualidade temos que pensar em como fornecer os serviços nos Data Centers, logo acaba-se usando muitos equipamentos(hardware) e sistema(softwares), e consequentemente temos problemas para gerenciar de modo centralizado. Claro que para esses problemas existem soluções que funcionam tanto a nível de equipamento como de sistema.

Para facilitar o gerenciamento de sistemas ultilizamos softwares capazes de coletar informações dos dispositivos, softwares como Nagios, Zabbix, Wireshark, coletam informações de status dos equipamentos na rede.

As soluções de monitoramento de Data Centers é uma tendência, dada a facilidade de administrar toda a rede, ela também nos dá a liberdade de usar qualquer tipo de hardware, de qualquer fabricante que ainda será possível as administrar, o que não é possível em soluções de hardware, já que muitos funcionam apenas para dispositivos da mesma marca.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/2/0/4/20448/shutterstock_113314987.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/2/0/4/20448/shutterstock_113314987.jpg)

Dashboard - Painel de Controle - Gerenciamento

### Principais objetivos e métodos de monitoramento e gerência

Temos vários motivos para monitorar uma rede, e logo temos vários métodos de fazer isso. Os métodos de monitoração envolvem a análise da rede, e a geração de alertas, que são notificações com informações sobre algum evento, ou relatórios, que podem apresentar diferentes informações. Os principais métodos de monitoramento serão descritos a seguir:

- Monitoramento de configuração: Analisa a infraestrutura de uma rede de armazenamento, a fim de achar mudanças em configurações de dispositivos, e verificar se elas se enquadram nas políticas pré estabelecidas pelo administrador da rede.
- Monitoramento de disponibilidade: Analisa a infraestrutura de uma rede de armazenamento, a fim de achar qualquer falha ou indisponibilidade em serviços ou dispositivos.
- Monitoramento de capacidade: Analisa os volumes de armazenamento para garantir que sempre haverá espaço para armazenamento para atender a demanda, quando chega próximo de um limite máximo de armazenamento, uma notificação é enviada ao administrador, que por sua vez, pode adicionar mais dispositivos de armazenamento,
- Monitoramento de desempenho: Analisa a performance e desempenho dos dispositivos e serviços de uma infraestrutura. Verifica a taxa de transmissão de dados, e busca por qualquer queda de desempenho.
- Monitoramento de segurança: Analisa possíveis quebras de segurança, acessos não autorizados, e mudanças de sistemas, para impedir que aconteçam incidentes que afetem às informações.

O que podemos entender disso, é que primeiro se estabelece os monitoramentos que sua rede necessita, caso algum desses sistemas encontrar algo, ele gerará um alerta, que pode ser de vários níveis, desde uma advertência, até alertas com níveis de urgência maior. Uma vez que um alerta é gerado, o mesmo aparece nos relatórios posteriormente, relatórios que contenham informações como espaço em armazenamento, capacidade total de armazenamento, número de clientes na rede e é a taxa de transmissão, etc…

### Gerenciamento de infraestrutura

Podemos criar um tipo de ciclo para definir como esse gerenciamento deve ser feito. Primeiro temos o Desenho, que é a elaboração da arquitetura necessária. Após isso temos o Planejamento, que consiste em planejar os componentes. Depois temos a implementação, que é a instalação e disponibilização dos componentes, após a implementação, temos a Operação, que é operar de fato a tecnologia implantada, e todos seus recursos, e finalmente, temos o Suporte, que consiste em resolver qualquer problema ou anormalidade no funcionamento dos componentes.

Os principais objetivos desse gerenciamento é poder garantir e aumentar a disponibilidade da infraestrutura de tecnologia da informação, reduzir o custo das falhas, diminuir o custo dos serviços, permitir flexibilidade no atendimento da demanda, entre muitos outros.Um ponto muito importante ao planejar o gerenciamento é a AVALIAÇÃO DE TCO.

TCO significa **Total cost of ownership,** ou custo total da posse, com isso conseguimos escolher alternativas viáveis para o quanto está no nosso orçamento.

### Softwares de monitoração

Temos vários softwares que nos ajudam a monitorar uma rede e seu tráfego, a mais conhecida é o Wireshark, mas temos outras opções, tanto pagas e livres, alguns exemplos são o trafip, tcpdump, netcat, e muitas outras.As principais funcionalidades dessas ferramentas são analisar o tráfego de rede, eles oferecem recursos para filtrar tipos de tráfegos específicos, analisá-los, e muitas vezes criar um tipo de representação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875455/36823.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875455/36823.png)

Tabela de Tráfego por IP do Bandwidthd

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/4/7/2954754/42110.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/4/7/2954754/42110.jpg)

### Metodologia ITIL

ITIL significa Information Technology Infrastructure Library, em inglês, ou “Biblioteca de Infraestrutura de Tecnologia da Informação” em português, surgiu nos anos 80 pelo governo britânico. É uma biblioteca de conhecimentos sobre gerenciamento de sistemas de TI, ela reúne as melhores práticas. Não só reúne como administra e desenvolve uma metodologia exemplar para se usar em gerenciamento de TI.A ideia da metodologia ITIL é sempre atender bem os clientes de uma forma integrada, para isso é importante que todos os processos sejam extremamente controlados, preferencialmente de uma maneira centralizada, de maneira a desenvolver um gerenciamento eficiente.Com isso é possível obter resultados melhores, ter um melhor atendimento, redução de custos, entre muitas outras melhorias.

Na rede de dados em uma organização e mesmo na Internet é preciso conhecer os equipamentos, como eles se interconectam, seu desempenho, entre outras métricas, para garantir seu funcionamento correto. Por isso, o gerenciamento de redes é tão importante. Esta é a primeira parte do video "Introdução ao Gerenciamento de Redes" feito pelo NIC.br.

Administradores de redes precisam de ferramentas que os ajudem na organização do endereçamento IP de uma rede, permitindo uma rápida identificação de computadores e usuários e um planejamento estruturado das sub-redes. Esta é a segunda parte do video "Introdução ao Gerenciamento de Redes" feito pelo NIC.br e aborda ferramentas IPAM (IP Address Management).

Nenhum contribuinte quer cair na "malha fina" do Leão, mas para detectar crimes fiscais a Receita Federal precisa realizar uma série de análises procurando por inconsistências nas declarações do Imposto de Renda. Em redes de computadores também existem sistemas que atuam de forma semelhante, analisando o tráfego de pacotes e gerando alertas caso este tráfego apresente algum comportamento fora dos padrões normais daquela rede. Esta é a terceira parte do vídeo "Introdução ao Gerenciamento de Redes" feito pelo NIC.br.

Todos podemos concordar que o controle de tráfego aéreo atualmente é muito eficiente. Ele só funciona assim porque utiliza uma série de ferramentas e sistemas que monitoram o espaço aéreo e permitem controlar as rotas e as posições das aeronaves. Nas redes de computadores também precisamos de ferramentas que facilitem seu gerenciamento e permitam monitorá-la para manter a qualidade de seu funcionamento. Nas redes, as tarefas mais complexas de gerenciamento são realizadas pelo SNMP, ou Simple Network Management Protocol, que é o protocolo padrão para gerenciar dispositivos em redes IP.

Administrar uma rede de computadores sem o uso de ferramentas de monitoramento, em particular daquelas baseadas em SNMP, é como pilotar um avião sem instrumentos. Entenda nesse vídeo a utilidade de ferramentas como o MRTG, RRDTool, Cacti, Icinga, Nagios, Zabbix, entre outras.

### O que é o Protocolo SNMP?

É um Protocolo Simples de Gerenciamento de Redes - SNMP (Simple Network Management Protocol) foi desenvolvido para permitir que os dispositivos de uma infraestrutura de redes e que utilizam o protocolo IP (Internet Protocol) possam ser gerenciados remotamente, através de um conjunto de “simples” operações. O SNMP utiliza o modelo Gerente/Agente que consiste num servidor operando uma função denominada NMS (“Gerente”, Network Management System) que se comunica com o agente de gerência de rede. Esse agente é um software instalado no dispositivo a ser gerenciado através do protocolo de gerência, que suporta o protocolo SNMP, tais como Zabbix e Nagios.

**GERENCIAMENTO DE DISPOSITIVOS EM UMA REDE E A ADOÇÃO DO PROTOCOLO SNMP**

Abaixo o vídeo apresenta o laboratório prático com o uso do Packet Tracer do fabricante Cisco, que ilustra o funcionamento do Gerenciamento de dispositivos em uma rede e a adoção do protocolo SNMP(Simple Network Management Protocol) ou “Protocolo Simples de gerenciamento de redes”.

O Vídeo destaca que é possível alterar remotamente o nome de um roteador ou seja administrar os dispositivos alterando o _**hostname,**_ ou seja o nome do equipamento.

### Resumo

Temos vários outros tipos de monitoramento, vai depender do que você quer ver no momento da análise, mas é sempre importante saber o que você precisa ver, e ter como fazer isso, o conjunto desses métodos de monitoramentos, com alertas e relatórios torna a infraestrutura mais sólida como um todo.Monitoramento é todo o processo de gerência de um sistema ou conjunto de dispositivos, com a análise de dados em tempo real, para criar relatórios compreensíveis por humanos, que facilitam muito a nossa vida. É sempre bom lembrar que a gerência abrange todas as partes do Data Center, e não apenas partes específicas.

Como vimos neste tópico, é importante gerenciar todas as partes de um Data Center, e a importância de softwares de monitoramento de redes, como o wireshark, Cacti e MRTG, que oferecem um plano de controle para o gerenciamento de Redes.