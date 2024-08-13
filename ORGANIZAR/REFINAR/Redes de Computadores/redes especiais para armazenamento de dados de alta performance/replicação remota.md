### Introdução

Quando pensamos em um Data Center e suas tecnologias podemos pensar sobre o backup e a replicação local, uma técnica importante que precisamos compreender, que é a replicação remota. Ela nos permite copiar informações para outras localizações geograficamente afastadas. Isso é uma ótima vantagem em relação a replicação local, já que dessa forma, o servidor remoto possuirá uma cópia do servidor local.

Replicação é o ato de replicar, reproduzir ou criar uma cópia, ela pode ser feita localmente ou remotamente, neste tópico veremos sobre a replicação remota, que consiste basicamente em copiar uma informação de um lugar para outro lugar geograficamente separado.

Desastres naturais ou de causas humanas, como tempestades, tsunamis, furacões, guerras, ataques terroristas, podem representar um ponto de falha para a replicação local, uma vez que se o seu Data Center for destruído os dois ou mais servidores de replicação ficarão fora do ar. Nesses casos é extremamente útil a solução de replicação remota. Em termos de segurança podemos dizer que é uma medida bastante efetiva.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/9/3/2/2993263/43248.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/9/3/2/2993263/43248.png)

Fonte: EMC Corporation.ISM (2015)

### Tipos de replicação remota

As principais maneiras de se criar uma solução remota são replicações síncronas ou assíncronas, mas temos outras variações que também serão explicadas neste tópico. O uso de cada um vai depender do tipo de implementação que melhor se encaixar com suas necessidades.

**Síncrona:** A replicação remota síncrona é realizada entre dois dispositivos de armazenamento de maneira que cada  dado enviado de um dispositivo para outro envie uma confirmação de que o dado não está corrompido.

Essa abordagem é muito boa quando queremos assegurar a integridade dos dados, já que por estarem sempre sincronizados e se conversando não têm perda de dados durante a transmissão. Porém em relação à distância e tempo não é muito eficiente, já que é um pouco lento por enviar confirmações a cada envio, em relação a distância pois quanto maior a distância, maior a latência, que é o intervalo de tempo entre o envio e recebimento de uma informação.

**Assíncrona:** A replicação remota assíncrona é realizada entre dois dispositivos de armazenamento de maneira que os dados são enviado de um dispositivo para outro sem enviar  confirmações, diferente da síncrona.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/3/8/2953865/43251.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/3/8/2953865/43251.png)

Fonte: EMC Corporation.ISM (2015)

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/2/8/2952816/43252.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/2/8/2952816/43252.png)

Fonte: Dell Corporation (2015)

O principal motivo para o dispositivo funcionar assim é que agora pode se replicar a longas distâncias, já que a latência não será um problema por ele ser mais rápido, e será uma abordagem menos demorada do que a síncrona. Essa rapidez se dá devido a não confirmação dos dados. Porém isso pode acarretar perda de dados, caso um dos lados pare de funcionar, já que o outro continuará enviando os dados  mesmo assim.

Cabe aos administradores escolherem qual tipo de replicação usar dependendo de cada caso, e também temos combinações dos dois e variações.

Medidas como o CDP podem ser implementadas, CDP significa Continuous Data Protection, ou em português, proteção contínua de dados. Se baseia na ideia que nenhum dado deve se perder sob circunstância alguma. É implementado um intermediário entre o armazenamento e os sistemas computacionais que se chama Appliance. O appliance pode ser implementado por software ou hardware.

Esse appliance duplica os dados por meio de um dispositivo chamado _**splitter**_, que envia os dados para duas redes, geralmente remotas, dessa maneira assegurando que os dados sempre sejam íntegros.

Outra solução para replicação remota é o uso de _**SNAPSHOTS,**_ que é a criação de uma imagem do sistema, funciona como se fosse uma foto, que registra um determinado momento. Um Snapshot ocupa menos espaço de armazenamento do que sua origem. Diferente de um backup normal, na qual a cópia possui o mesmo tamanho da origem. Uma implementação muito comum de snapshots é a criação de um snapshot Inicial completa, e depois apenas as mudanças, que é a cópia diferencial. Dessa maneira se gasta menos tempo para copiar os arquivos, e prioriza às alterações, dessa maneira as perdas são menores em caso de uma interrupção no sistema.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/3/2/2953243/43253.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/5/3/2/2953243/43253.png)

Fonte: Dell Corporation (2015)

### Revisão

A replicação remota é um recurso muito ágil e flexível, o que nos garante mais facilidade para gerenciar as informações. O acesso às informações é um fator importante uma vez que diversos servidores podem ter a capacidade de balancear a disponibilidade das informações. A estratégia de replicação remota e backups(cópias de dados em casos de desastres) é uma prática bastante efetiva e executada por administradores de rede, preocupados em manter a continuidade dos negócios, sem afetar as operações de tecnologia da informação.

A replicação remota pode trazer algumas vantagens, entre elas, temos o aumento de velocidade de acesso para seus usuários, já que diversos servidores geograficamente espalhados, os usuários poderão se conectar ao servidor mais próximo,diminuindo o custo computacional, o que gastará menos tempo, e  distribuirá a carga de trabalho entre vários servidores, dessa forma, haverá uma menor possibilidade de servidores sobrecarregados. O importante é sempre analisar a melhor estratégia para cada caso.