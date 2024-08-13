**Introdução**

Através do processo do comitê IETF, vários recursos foram adicionados à especificação IPv6, além de 128-bits de endereçamento. Isso inclui níveis de serviço assegurados e aumento de segurança e confiabilidade.

Qualidade de serviço (QoS) é um termo importante e uma característica emergente de redes modernas. Um sistema com base em IPv4 não tem como diferenciar entre dados que são sensíveis ao tempo, como streaming de vídeo ou áudio, e aquelas que não são sensíveis ao tempo, como relatórios de status e transferência de arquivos.

O IPv6 fornece uma maneira para aplicações de solicitar tratamento imediato em toda a WAN. O termo frequentemente usado para descrever isso é "baixa latência". Streaming de áudio e vídeo requer baixa latência através de alta prioridade. Para evitar uma quebra no sistema, a aplicação pode compartilhar a conexão através de nível de prioridade, por exemplo, atribuindo os seguintes níveis de prioridade:

0 - Sem prioridade especificada.

1 - O tráfego de background (notícias).

2 - Transferência de dados autônoma (e-mail).

3 - Reservado.

4 - Transferência em massa assistida (FTP).

5 - Reservado.

6 - O tráfego interativo (Telnet, Windowing).

7 - Controle de tráfego (roteamento, gerenciamento de rede).

A fragmentação do pacote é uma importante fonte de atrasos de pacotes, ou alta latência, sob IPv4.Cada dispositivo conectado a uma rede tem uma carga de dados limite, estabelecida dentro do pacote Ethernet. Se o programa está gerando fluxo de dados, como vídeo ou áudio, o fluxo de dados será dividido em uma série de pacotes, cada um carregando a carga útil máxima.

Com diferentes dispositivos, estes tamanhos de carga são definidos de forma diferente e é possível que, entre as fontes de origem e destino, um caminho de transmissão, em particular um modo de transferência assíncrono (ATM, por exemplo), possa ser encontrado, gerando assim um tamanho menor de carga útil.

Assim, o equipamento ATM vai cortar o fluxo já fragmentado de dados em pedaços ainda menores. Um comutador ATM poderia dividir os dados transportados em um único pacote Ethernet em 20 células ATM. Em algum lugar na divisão e reconstrução ou de todos os dados, é provável que uma célula, e não um pacote, seja descartada ou adiada.

Já o IPv6 usa uma abordagem mais sofisticada para lidar com dados de programas solicitando tratamento prioritário. O dispositivo de origem terá consultas ao destino a fim de determinar o tamanho máximo da carga que a chamada será tratada em toda a rota completa. Em seguida, ele ajusta os próprios parâmetros e não vai carregar os pacotes originários com mais dados que os menores quadros ou células da rede pode manipular.

Esta abordagem reduz fragmentação e latência, mas também pode resultar em utilização ineficiente.

A funcionalidade QOS terá que ser incluída em todos os dispositivos de rede a fim de ser aplicado. Sem a funcionalidade disponível em determinados dispositivos, fará com que ele retorne a um tratamento padrão com apenas uma camada adicional para passar, gerando, assim, atrasos e utilização ineficiente.

**Restrições para implementação****de QoS em IPV6**

Os seguintes recursos de QoS não são suportados para gerir o tráfego IPv6:

- Compressed Real-Time Protocol (CRTP).
- Reconhecimento de aplicação baseada em rede (NBAR).
- Taxa de acesso comprometida (CAR).
- Filas de prioridade (PQ).
- Custom Queuing (CQ).

Pacotes IPv6 são direcionados por caminhos diferentes daqueles utilizados quando se usa a versão do IPv4. Recursos de QoS para IPv6 suportam ambientes que incluem classificação de pacotes, filas, traffic shaping, detecção aleatória ponderada (WRED) baseadas em classes de pacotes de marcação e policiamento de pacotes IPv6.

Todos os recursos de QoS disponíveis para ambientes IPv6 são gerenciados a partir da interface do QoS MQC (linha de comando modular). O MQC permite definir classes de tráfego, criar e configurar políticas de tráfego e, em seguida, anexar as políticas de trânsito para interfaces.

Para implementar QoS em redes IPv6 em execução, você deve seguir os mesmos passos utilizados para fazê-lo em redes que executam apenas IPv4. Os passos básicos para implementação de QoS em uma rede IPV6 são os seguintes:

- Saiba quais as aplicações em sua rede precisam de QoS.
- Compreenda as características dos aplicativos para que você possa tomar decisões sobre quais características QoS são mais apropriadas.
- Conheça a sua topologia de rede para que você saiba como tamanhos de cabeçalhos da camada de ligação são afetados por mudanças e encaminhamento.
- Crie classes com base nos critérios definidos para a sua rede. Em particular, se a mesma rede possui os tráfegos IPv4 e IPv6, você deve decidir se quer tratar os dois da mesma forma ou tratá-los separadamente, especificando critérios. Se você quer tratá-los igualmente, use métodos de precedência e DSCP. Se você quiser tratá-los separadamente, adicione combinações de mapas de classes para cada um.
- Crie uma política para marcar cada classe.
- Construa a política para tratar o tráfego.
- Aplique a política.

**Classificação de pacotes em IPv6**

A classificação pode ser baseada em IPv6 precedence, ponto de controle de serviços diferenciados (DSCP), e outros valores específicos do protocolo IPv6 que podem ser especificados no acesso da lista IPv6, além de outros valores de protocolos específicos, como COS, tamanho do pacote e grupo QOS. Depois de determinar quais aplicações precisam de QoS, você pode criar classes com base nas características delas. Pode-se usar uma variedade de combinações de critérios para classificar o tráfego além de combinar vários critérios de correspondência para segregar, isolar e diferenciar o tráfego.

Para compreender melhor as diferenças entre cabeçalhos IPV4 e IPV6, as figuras a seguir ilustram esses dois cabeçalhos. Observe que no cabeçalho IPV4 temos o campo "TOS", que trabalha a marcação dessas classificações QoS. Já para o cabeçalho IPV6, temos o campo "Traffic Class", que auxilia a marcação QoS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119296/a17i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119296/a17i01_quasar80_100.jpg)

Figura 1: Cabeçalho IPV6. Fonte: TANENBAUM, A. S. Redes de Computadores. Rio de Janeiro: Campus, 2006.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119297/a17i02_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119297/a17i02_quasar80_100.jpg)

Figura 2: Cabeçalho IPV4. Fonte: TANENBAUM, A. S. Redes de Computadores. Rio de Janeiro: Campus, 2006.

**Considerações finais**

O campo "Traffic class" do IPV6 é usado para fazer distinção entre pacotes com diferentes requisitos de entrega em tempo real. O campo "Flow label" ainda está em fase de experiência, mas será usado para permitir que uma origem e um destino configurem uma pseudoconexão com propriedades e necessidades específicas. Por exemplo, um fluxo de pacotes entre um processo de um determinado host de origem e certo processo de um host de destino específico pode ter severas restrições em termos de retardo e, por essa razão, necessitar de uma largura de banda reservada. O fluxo pode ser configurado com antecedência e ter um identificador atribuído a ele. Quando um pacote com o campo "Flow label" com valor diferente de zero aparece, todos os roteadores podem verificar nas tabelas internas que tipo de tratamento especial ele exige. Na prática, os fluxos são uma tentativa de se ter a flexibilidade de uma sub-rede de datagramas, juntamente às garantias de uma sub-rede de circuitos virtuais.

O campo "Payload length" também do cabeçalho IPV6 determina o número de bytes que seguem o cabeçalho de 40 bytes.O nome desse campo, que no IPv4 era "Total length", foi alterado devido à pequena mudança de significado a que foi submetido: os 40 bytes do cabeçalho deixaram de ser contados como parte do tamanho, como acontecia até então. O campo "Next header" revela um segredo: o cabeçalho pode ser simplificado porque existe a possibilidade de haver outros cabeçalhos de extensão (opcionais). Esse campo informa quais dos seis cabeçalhos de extensão (atuais) seguem esse cabeçalho se houver algum. Se esse cabeçalho for o último cabeçalho do IP, o campo "Next header" revelará para qual tratador de protocolo de transporte (por exemplo, TCP, UDP) o pacote deverá ser enviado.

O campo "Hop limit" é usado para impedir que os pacotes tenham duração eterna. Na prática, ele é igual ao campo "Time to live" do IPv4, ou seja, um campo que é decrementado a cada hop. Teoricamente, no IPv4 ele denotava um tempo em segundos, mas nenhum roteador o utilizava dessa maneira. Por esse motivo, seu nome foi alterado para refletir o modo como de fato ele é usado.

Em seguida, vêm os campos "Source address" e "Destination address". utilizando endereços de 16 bytes.