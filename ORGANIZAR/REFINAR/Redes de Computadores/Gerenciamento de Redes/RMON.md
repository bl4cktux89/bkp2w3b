**Introdução**

Olá! Seja bem-vindo à décima terceira aula! Nela, falaremos sobre o protocolo de gerenciamento RMON.

O RMON é um padrão definido pelo IETF sob a RFC 1757. Tendo em vista que o SNMP não define sucintamente causas de um problema nem sua gravidade ou recursos para investigação, o IETF decidiu que era necessário um padrão de gerenciamento de redes mais sofisticado a fim de para promover e facilitar expansões das tecnologias de rede.

Dessa forma, o RMON tornou-se padrão em 1990. Recentemente, para atender às novas tecnologias e estender suas capacidades, foi publicada uma atualização: o RMON II, sob as RFCs 1757 e 1531, que também apresentam informações de redes Ethernet.

**Características**

As características do padrão RMON são:

- Interoperabilidade, independentemente de fabricante.
- Capacidade de fornecer informações precisas a respeito das causas de falha no funcionamento normal da rede, assim como de sua severidade.
- Oferecer ferramentas para diagnóstico da rede.
- Oferecer mecanismos proativos sobre alertas e métodos automáticos para coleta de dados.

**O padrão RMON e seus objetivos**

Conforme a RFC1757, o RMON não é uma pilha de protocolos nem um protocolo por si só: trata-se de uma extensão de MIB (_**Management Information Base**_) para ser utilizada com protocolos de gerenciamento de rede na internet com base em TCP/IP. Os objetos definidos nessa RFC são interfaces entre agentes RMON e aplicações de gerenciamento RMON, contudo, alguns são específicos para redes Ethernet.

Os dispositivos de gerenciamento remoto são chamados de monitores ou sondas (probes), utilizados apenas para o gerenciamento de redes e são independentes (standalone), direcionando seus recursos ao gerenciamento da rede que estão conectados. Uma empresa pode usar vários dispositivos, sendo um por segmento, entretanto, podem-se adicionar monitores para que um provedor possa gerenciar uma rede cliente geograficamente separada.

**Objetivos**

O RMON procura resolver problemas que outros protocolos não são capazes. Dessa forma, devem-se observar:

- Operação offline: Para situações de monitoramento em que uma estação de gerenciamento não mantém contato contínuo com seus dispositivos gerenciados. Essas situações ocorrem quando se quer reduzir custo com a comunicação ou por falha na rede. Isso acarreta a perda de qualidade do monitor.
- Monitoramento proativo: para a execução de rotinas de diagnósticos que acumulam dados sobre a rede. Nessa situação, o monitor notifica imediatamente o gerenciamento de falhas, caso uma falha ocorra, além de armazenar informações estatísticas sobre os eventos de modo que sejam analisados para diagnosticar eventuais problemas.
- Detecção e notificação de problemas: o monitor pode ser configurado para verificar erros continuamente, além de registrá-los e notificar as estações de gerenciamento.
- Valor agregado aos dados: indica quais equipamentos têm maior tráfego ou geram mais erros, fornecendo informações preciosas para a resolução de toda uma classe de problemas.
- Gerenciamento múltiplo: o equipamento que gerencia a rede deve ser capaz de monitorar múltiplos dispositivos, independente de sua localização física ou arquitetura.

**Convenções**

Nessa nova MIB, duas novas convenções textuais foram introduzidas como tipos de dados: OwnerString e EntryStatus. Elas servem gerar documentos claros e concisos, não permitindo ambiguidades.

A sintaxe não sofre qualquer alteração nos objetos gerenciados, já que seu uso é um artifício explicativo sobre um método utilizado, codificado por meio de regras que definem um tipo de dado primitivo.

**A estrutura da MIB**

Os grupos definidos na extensão RMON da MIB são:

- Estatísticas Ethernet: define o objeto _etherStatsTable_ que contém as estatísticas coletadas por um monitor para cada interface Ethernet de determinado dispositivo.
- Histórico de controle: define o objeto _historyControlTable_ que contém informações sobre amostragem estatística dos dados de vários tipos de rede.
- Histórico Ethernet: define o objeto _etherHistoryTable_ que registra amostras periódicas da rede Ethernet e as armazena para análise posterior.
- Alarme: define o objeto _alarmTable._ Coleta amostras estatísticas das variáveis do monitor e as compara aos limites previamente configurados: se uma variável ultrapassa o limite estabelecido, um evento é gerado.
- Host: neste grupo há três objetos: _hostControlTable, hostTable_ e _hostTimeTable._ Ele armazena dados estatísticos a respeito de cada um dos _hosts_ descobertos na rede. Tal descoberta é feita através da captura de pacotes recebidos promiscuamente da rede e, com eles, monta-se uma lista dos endereços MAC da origem e destino.
- _HostTopN:_ neste grupo há dois objetos: _hostTopNControlTable_ e _hostTopNTable._ Ele elabora relatórios descritivos dos hosts que ocupam o topo da lista de determinada estatística. As estatísticas disponíveis são amostras capturadas num intervalo de tempo especificado pelo monitor. Além disso, deve-se, também, determinar no monitor a quantidade de equipamento a ser analisado. Este grupo requer a implementação do grupo de host_._
- Matriz: neste grupo estão definidos três objetos: _matrixControlTable, matrixSDTable_ e _matrixDSTable._ Ele armazena dados das conversas entre conjuntos de dois endereços. Quando um dispositivo detecta uma nova comunicação, é criada uma nova entrada em suas tabelas.
- Filtro: este grupo possui dois objetos: _filterTable_ e _channelTable._ Sua função é identificar pacotes que satisfazem critérios estabelecidos através de uma equação de filtragem. Quando ocorre tal estabelecimento, são gerados fluxo de dados para criar eventos ou capturar o pacote.
- Captura de pacotes: este grupo tem dois objetos: _bufferControlTable_ e _captureBufferTable_. Nele, pacotes são capturados após passar por determinado canal ou filtro. Ele requer a implementação do grupo de filtro.
- Evento: controla a geração e notificação de eventos de determinado dispositivo. É composto por _eventTable_ e _logTable_

Esses grupos são as unidades básicas de conformidade e, portanto, se um monitor remoto usa determinado grupo, deverá usar todos os objetos definidos naquele grupo.

Os grupos nesta MIB são opcionais, contudo a implementação deles exige o uso do grupo de sistema e interfaces definidos na MIB-II e, esta, por sua vez, poderá exigir o uso de grupos adicionais.

Essa forma de uso permite que exista um mecanismo adequado para identificar cada objeto no ambiente gerenciado e para o gerenciamento adequado do conjunto de objetos do funcionamento do esquema.