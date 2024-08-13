### Introdução

Imagine, hoje, você tendo de ir para a faculdade em seu próprio carro sem consultar um aplicativo de GPS (Sistema Global de posicionamento) ou o Waze®. Em uma cidade como São Paulo a utilização de tais aplicativos se tornou comum e essencial para evitarmos congestionamentos em virtude de problemas na via ou simplesmente excesso de automóveis. Como você conhece muito bem o caminho para a faculdade não seria difícil chegar, mas em virtude de problemas alheios a sua vontade, poderia passar horas no transito e, consequentemente, chegar atrasado na faculdade.

Essa situação não deixa de ser diferentes de nossas redes de computadores, principalmente na internet. Imagine, agora, um pacote que sai do seu computador contendo uma solicitação de uma página web. Ao entrar na internet ele deve ser encaminhado, ou melhor, roteado até o servidor de destino, passando por diferentes caminhos ou rotas. A escolha do caminho fica a cargo dos roteadores e para tanto, utilizam o que é chamado protocolos de roteamento ou rotas definidas estaticamente.

### Rotas estáticas e dinâmicas

Continuando com a nossa analogia anterior, imagine que você para ir à faculdade utilize sempre o mesmo caminho por não existir rotas adicionais ou porque você conhece bem o caminho e já determinou que não há escolha, aquele sempre será o melhor caminho. Essa analogia a gente pode empregar para compreensão do que é conhecido como **Rotas estáticas.** Uma rota estática é defina manualmente pelo administrador da rede quando ele conhece muito bem o caminho até o destino ou porque aquele é único caminho possível. Por outro lado, se para ir a faculdade você pode passar por diferentes caminhos e tais caminhos são influenciados pelo congestionamento seria mais interessante utilizar um GPS ou do Waze. O GPS utiliza normalmente o caminho mais curto em termos de quilometragem, não levando em consideração o estado do caminho, em termos de congestionamento, vias interditadas ou confiabilidade. Esta última situação é comparável ao que ocorre com os **protocolos d**e **roteamento dinâmico**, que determina o melhor caminho por meio de diferentes variáveis conhecidas como **métrica.** A **métrica** é o **custo** para envio do pacote da origem até o destino, normalmente o melhor caminho possui o menor custo. O custo para uma determinada rede de destino pode conter diferentes informações, tais como (Filippetti, Marco. A., 2017):

- **Largura de banda (em bits por segundo – bps)**
- **Contagem de salto**
- **Atraso**
- **Confiabilidade**

### Comparação entre roteamento estático e dinâmico

O roteamento estático e dinâmico deve avaliado de acordo com os critérios mostrados na tabela abaixo. Em linhas gerais, o roteamento estático pode ser utilizados em topologias pequenas e quando há apenas um caminho para chegar as demais rede, como é o caso das redes Stub, mostrada na figura abaixo. Deve ser evitado em topologias complexas e que mudam com frequência. Por outro lado, os protocolos de roteamento dinâmico são empregados em topologias com caminhos redundantes e geralmente independe do tamanho da rede. Em contrapartida, o roteamento dinâmico requer mais recursos de hardware, como memória e processador.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/4/2/3/1642384/38607.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/4/2/3/1642384/38607.png)

Fonte:

### Tabela de roteamento e tomada de decisão

A tabela de roteamento consiste de um arquivo armazenado na memória RAM (memória volátil) do roteador contendo as informações para se chegar a rede de destino. Dentre essas informações temos:

- **Redes ou rotas diretamente conectadas:** redes diretamente conectadas, como o próprio no já diz, são as redes ligas ao roteador, como as redes 192.168.10.0, 192.168.11.0 e a rede 209.165.200.224 ligadas diretamente ao roteador R1, conforme figura abaixo.
- **Redes ou rotas remotas:** São as redes alcançadas apenas passando por outro roteador. Em outras palavras, são aquelas redes que não estão diretamente conectadas, como as redes 10.1.1.0 e 10.1.2.0 ligadas ao roteador R2 da figura abaixo. As rotas remotas podem ser aprendidas por meio de rotas manualmente configuradas (rotas estáticas) ou por meio de protocolos de roteamento dinâmico.
- **Associação de rede e próximo salto:** Consiste do mapeamento entre a rede de destino e o endereço IP do próximo roteador (próximo salto) que permite chegar até o destino. Na figura abaixo, para se chegar as redes remotas 10.1.1.0 e 10.1.2.0, a tabela de roteamento de R1 indicará como próximo salto o endereço IP 209.165.200.226.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632792/38519.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632792/38519.png)

### Decisão de roteamento

Quando um pacote chega a interface do roteador, o mesmo procura uma correspondência na tabela de roteamento entre o endereço IP de destino e a rede de destino. Essa rede de destino pode ser uma rede diretamente conectada, uma rede remota aprendida estaticamente ou dinamicamente ou definida através de um gateway de último recurso conforme apresentado na figura abaixo. Abaixo detalhamos as possíveis decisões que um roteador pode tomara a partir do momento que um pacote chega a sua interface (Filippetti, Marco. A., 2017).

- **Rede diretamente conectada:** Caso o PC1, com IP 192.168.10.10, deseje enviar uma mensagem para o PC2, com IP 192.168.11.10, ele deve encaminhar essa mensagem ao roteador, que por sua vez, verificará a sua tabela de roteamento. Como o endereço de IP de destino pertence a uma rede diretamente conectada (192.168.11.0), o roteador verificará a sua tabela ARP (Protocolo de resolução de Endereço) se há uma correspondência entre o endereço IP e o MAC de PC2. Caso haja uma correspondência, ele enviará o pacote diretamente para PC2, senão ele enviará uma solicitação ARP para PC2 solicitando o seu endereço MAC.
- **Rede remota:** Agora vamos imaginar que PC1 deseje enviar uma mensagem para PC3 localizado na rede 10.1.1.0. Neste caso, o roteador ao consultar a sua tabela de roteamento verificará que o endereço IP de destino contido no pacote não pertence a uma rede de diretamente conectada a ele e sim a uma rede remota. Neste caso, ele encapsulará o quadro para sua interface de saída s0/0/0. Esse pacote chegará ao roteador R2 que verificará que o endereço IP de destino do pacote pertence uma rede diretamente conectada, e executará a solicitação ARP, conforme comentado anteriormente.
- **Gateway de último recurso:** O gateway de último recurso é usado quando a rede de destino não é diretamente conectada ou não foi aprendida nem estática nem dinamicamente. Isso acontece porque R1 e R2 só conhecem as redes diretamente conectas e as rotas não diretamente mostras na topologia. Qualquer outra rede que não esteja nessa topologia deve ser encontrada por um roteador que está na Internet. Em outras palavras, os seus roteadores só conhecem o que está sobre sua administração, as redes que não estão sob sua administração devem ser tratadas pelo gateway de último recurso. Para o exemplo da topologia, imagine que o pacote que sai de PC1 tenha como destino o endereço IP 200.20.20.20. Como não existe entrada na tabela de roteamento de R1 para esse destino, mas R1 sabe que R2 possui uma rota de último recurso, ele encaminhará o pacote para R2 que por sua vez encaminhará para a roteador ligado a Internet.
- **Descarte de pacote:** Caso a rede de destino não seja uma interface diretamente conectada, nem esteja marcada como rede remota e não exista um gateway de último recurso, o roteador R1 descartará o pacote e enviará uma mensagem ICMP para PC1 informando que a rede de destino é inalcançável.

### Protocolos de roteamento dinâmicos

Os protocolos de roteamento dinâmicos são classificados em IGPs (Protocolos Internos de Gateways) e protocolos de roteamentos EGPs (Protocolos Externos de Gateways), conforme figura que segue.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632793/38524.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632793/38524.png)

Fonte: Cisco Systens

- **IGPs** são usados dentro de um mesmo Sistema Autônomo (AS). Um AS de acordo com a RFC1930 do IETF, é um grupo de redes IP, abaixo de uma única gerência técnica e que compartilham uma mesma política de roteamento. O administrador do AS tem autonomia sobre qual protocolo IGP ele irá utilizar. Como protocolos IGPs podemos citar o RIP, OSPF, EIGRP e IS-IS. Cada AS recebe uma identificação única global de 32 bits, variando de 0 a 4.294.967.295
- **EGPs:** são usados para conectar os diferentes AS. O protocolo BGP é o protocolo oficial utilizado pela internet para interconectar os diferentes AS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632795/38530.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632795/38530.png)

Fonte: Cisco Systens

### Protocolos IGPs

Os protocolos de roteamento IGPs podem ser classificados em três classes de acordo com a métrica utilizada:

**Distance vector (vertor de distância):** Protocolos dessa categoria utilizam a contagem de salto como métrica para determinar o melhor caminho. Quanto menor for o número de saltos, ou seja, quanto menor for número de roteadores que o pacote irá passar até o destino, melhor será a rota. O protocolo RIP (Protocolo de Informação de roteamento) pertence a essa classe. O RIP é um protocolo limitado em virtude da sua métrica, já que ele não leva em consideração outras métricas, tais como largura de banda ou congestionamento, mas apenas a contagem de salto. Imagine que para chegar a rede de destino 10.0.0.0, da figura abaixo, o pacote que chega ao router A tem dois caminhos para chegar ao destino, mas como a topologia está configurada com RIP, o router A escolherá como melhor caminho passando diretamente por C. Perceba que o enlace A-C tem largura de bandas de 1 mbps e o enlace formado por A-B-C possui largura de banda igual 100 mbps. Apesar de ter maior largura de banda o enlace A-B-C ficará inutilizado, entrando em operação apenas em caso de queda do enlace A-C.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632794/38529.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/7/1632794/38529.png)

Outra deficiência dessa classe de protocolo está associado com atualizações de roteamento. A atualização de roteamente ocorre em periodos de tempo predeterminando, independente se houve ou não modificação na topologia. Além disso, a atualização é feita enviando toda a tabela de roteamento em **broadcast, enviando a atualização para todas as interfaces ativas sem se preocupar se o roteador ao qual ele está conectado será beneficiado com essa atualização.**

**Link State:** os protocolos dessa classe são consideravelmente mais eficientes tendo em vista que usam metricas mais complexas que resultarão em um entendimento mais confiável da rede, pois são baseados no conceito de estado de link (link state). todos os roteadores que participam do processo de roteamento, antes de enviarem suas informações de rede, aprendem o estado de suas interfaces diretamente conectadas (largura de banda, endereço IP da interface e da rede). após descobrir o estado da interface, as informações de roteamente são trocadas apenas com os roteadores com os quais ele estabelece o que chamado de **vizinhaça (neighbor).** O processo de vizinhança permite uma maior confiabilidade e evita que as atualizações sejam feitas em broadcast, como é o caso do RIP, em vez disso, as atualizações são feitas em multicast para os roteadores pertencentes a mesmas área, conforme mostrado na figura abaixo. A figura mostra as áreas pertecentes ao processo OSPF. A área 0 é chamada de backbone (espinha dorsal) e sempre deve existir em um roteamento com OSPF (Kurose, James F e Ross, W. Keith, 2013).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/6/6/1636603/38531.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/6/6/1636603/38531.png)

Fonte:

Protocolos do tipo link state operam ainda não só com uma tabela roteamento, eles possuem outras duas: uma tabela de todos os vizinhos diretamente conectados; a outra, é composta da topologia lógica de toda a rede, contendo, por exemplo, o estado de todos os links. adicionalmente, outra vantagem desse tipo de protocolo, é que as atualizações são feitas apenas quando há modificação na topologia e não envia toda a tabela de roteamento, ou seja, apenas atualizações incrimentais.

Protocolos que usam essa classe são o OSPF (Open Shotest Path first, melhor caminho primeiro) e o IS-IS (Intermediate System to Intermediate System, Sistema entermediario para sistema intermediario).

**Hybrid:** protocolos hibridos utilizam o que ha de melhor das duas classe anteriores, como é o caso do protocolo EIGRP (Enhanced Interior Gateway Routing Protocol, Protocolo de roteamento de gateway interior) desenvolvido pela Cisco Systens. O EIGRP é um protocolo vetor de distância, que após aprender o caminho seta o próximo salto. Mas além disso, ele matem características como multiplas tabela, de roteamento (tabela de topologia, tabela de vizinhos e tabela de roteamento propriamente dita. Adicionalmente, a escolha do melhor caminho pode levar em consideração, além da largura de banda, também a carga, o atraso e confiabilidade.

A melhor rota e a manutenção da tabela de roteamento é mantida através de um algoritmo conhecido como DUAL (Diffusing Upadate Algorithm, algoritmo de atualização difusa). As principais funções de algoritmo são:

- Determinar rotas principais e secundárias (se possível) para uma rede remota
- Procura rotas alternativas caso o algoritmo não seja capaz de determinar uma rota a partir das informações enviadas pelos roteadores vizinhos.

Na tabela abaixo é mostrada uma comparação entre os diferentes protocolos de roteamento.

### Distância Administrativa

Em um roteador pode existir diferentes protocolos de roteamento configurados. Mas como você pode perceber ao longo deste tópico, existem diferentes protocolos de roteamento, com características distintas, conforme mostrado na tabela acima. A Distância Administrativa vem a estabelecer de forma quantitativa qual protocolo de roteamento é mais confiável, representado por um número inteiro compreendido de 0 a 255, conforme tabela abaixo. Sendo 0 a rota mais confiável e 255 a menos confiável. Como pode ser observado na tabela a rota mais confiável é uma rota proveniente de uma interface diretamente conectada. Isso significa que não há necessidade e de se utilizar um protocolo de roteamento dinâmico para comutar um pacote da interface de entrada para a de saída de um roteador, ja que a rede está diretamente conectada ao próprio roteador (Filippetti, Marco. A., 2017).

Em relação aos protocolos dinâmicos podemos perceber que o EIGRP é o protocolo Interior mais confiável (IGRP interno igual 90). Isso se deve a sua métrica composta por diferentes parâmentros (largura de banda, carga, atraso e confiabilidade), enquanto que o RIP apresenta a menor confiabilidade em virtude também da sua métrica não tão confiável (contagem de salto).

Tabela 1: Distância Administrativa dos diferentes protocolos de roteamento (Cisco Systems).

![[Untitled 38.png|Untitled 38.png]]