_**Fibre Channel**_ é um sistema que permite que vários servidores acessem dispositivos de armazenamento em rede. Uma rede de área de armazenamento permite a transmissão de dados de alto desempenho entre vários dispositivos de armazenamento e servidores. A Tecnologia FC é essencial para a implementação de SAN e estabelece conectividade de acordo com exigências.

**Topologia:**

A arquitetura _**Fibre Channel**_ é implementada em três tipos de topologias de transporte: ponto a ponto, laço arbitrado, e _**fabric**_. Na configuração da topologia ponto a ponto, a conexão entre dois dispositivos é dedicada. Já na topologia laço arbitrado_**,**_ o meio é compartilhado, permitindo que dois ou mais dispositivos possam se comunicar. Um conjunto especial de comandos é empregado para controlar o acesso do meio pelos dispositivos. A topologia _**Fibre Channel fabric**_ permite múltiplas e coexistente conexões ponto a ponto via comutação nível 2, provendo maior desempenho e escalabilidade.

Topologia Ponto a ponto

A topologia _**p**_onto a ponto (_**point-to-point**_) é simplesmente uma conexão direta entre duas Portas_N. Este esquema cria uma banda dedicada entre os pontos interconectados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261567/14534.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261567/14534.jpg)

Topologia FC Ponto-a-Ponto

Fonte: Cisco Networkers - Introduction to Storage Area Networking

Topologia Laço Arbitrado

Comparado com a topologia ponto a ponto_**,**_ laço arbitrado _**(arbitrated loops)**_ permite maior flexibilidade e suporte para mais dispositivos.

_**Arbitrated loop**_ é laço ou anel físico, na qual os dados são transmitidos de um Nó_NL para outro Nó_NL até alcançar o Nó_NL de destino. Sendo assim, existe um caminho contínuo de dados através dos Nós_NL do laço, permitindo que qualquer dispositivo possa acessar outro dispositivo no laço, como ilustrado na figura 2

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261573/14536.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261573/14536.jpg)

Topologia Laço Arbitrado

Fonte: Cisco Networkers - Introduction to Storage Area Networking

Na Figura 2, os nós do laço estão ligados serialmente. Se ocorrer algum problema em apenas um nó, o laço inteiro será desfeito. Com isso, foi desenvolvido _**arbitrated loop hubs**_.

A topologia física do laço arbitrado com _**hub**_ é do tipo anel-estrela, figura 3, onde cada Porta_NL transmite e recebe para um lugar comum. Um dos benefícios advindos do uso de um centralizador é o atalho para cada porta. Se um nó estiver desabilitado, um caminho secundário será usado. Portanto, o laço não será mais desfeito. O HUB será o ponto único de falha.

Topologia anel-estrela

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261577/14537.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261577/14537.jpg)

Topologia Anel-estrela

Fonte: Cisco Networkers - Introduction to Storage Area Networking

No laço arbitrado é permitido conectar 127 dispositivos (126 Portas_NL e 1 Porta_FL) em um laço. A Porta_FL é a porta do _**fabric switch**_ que funciona como interface entre o segmento de laço e os outros _**fabric**_ componentes.

Laço arbitrado é um transporte compartilhado e por este motivo, o acesso ao meio é ordenado por um protocolo de arbitração. Uma Porta_NL arbitra e ganha o controle do transporte, esta terá a toda largura de banda disponível para transação. Ao término da transação, a Porta_NL fecha a conexão liberando o meio. Esta mesma porta poderá arbitrar logo após o término de sua transação se não houver pedido sendo feito por outro dispositivo. A Porta_NL é justa, este esquema permite que dispositivos com baixa prioridade consiga ganhar a arbitração. Contudo, as Portas_FL não são portas justas. Se a Porta_FL fosse justa, poderia haver um congestionamento de quadros no switch. Esta maior prioridade da Porta_FL assegura o acesso do _**fabric switch**_ quando for preciso acessar o loop.

_**Topologia Fabrics**_

_**Fibre Channel fabric**_ é uma topologia em que um ou mais _**fabric switches**_ são utilizados na configuração de uma rede _**Fibre Channel**_. _**Fabrics**_ fornecem a largura de banda máxima por porta. Como mostrado na figura 4, um _**fabric switch**_ é otimizado para conexões diretas entre as Portas_F do switch e as Portas_N dos dispositivos

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261770/14538.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261770/14538.jpg)

Topologia Fibre Channel fabric

Fonte: Cisco Networkers - Introduction to Storage Area Networking

O número máximo de _**switches**_ interconectados possíveis numa rede _**Fibre Channel**_ é 239, tal fator está ligado a capacidade máxima do endereçamento único de cada switch pelo modelo _**Fibre Channel**_.

**Zoneamento**

O zoneamento _**(Fabric zoning**_) permite a separação de dispositivos baseados: na função, separação de departamentos, ou potenciais conflitos entre sistemas operacionais. De forma simplicada, o zoneamento restringe o acesso a certos nós/recursos.

Na Figura 5, temos um exemplo de um zoneamento.

Exemplo de um Zoneamento

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261765/14540.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261765/14540.jpg)

Exemplo de zoneamento

Fonte: http://fibrechannel.org

O diagrama da Figura 6 facilita a visualização do zoneamento citado acima.

Exemplo de um Zoneamento

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261713/14541.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261713/14541.jpg)

Divisão por zonas

Fonte: http://fibrechannel.org

O zoneamento pode ser configurado de duas maneiras:

- Estaticamente, configuração por portas
- Dinamicamente, configuração baseada em _World-Wide Name_ (WWN)

Zoneamento por portas

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262483/14542.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/4/262483/14542.jpg)

Figura 7 - Zoneamento por portas

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

Zoneamento por porta é mais seguro que zoneamento baseado em WWN, pois o intruso não consegue enganar a porta manipulando as informações do quadro _**Fibre Channel**_. Entretanto, a zona permanece com a porta e não com o dispositivo. Se houver uma mudança de um servidor de uma porta para outra, o servidor não mais pertencerá a zona que era designado. No zoneamento baseado em WWN, a zona é designada ao dispositivo. Isso facilita o translado dos dispositivos, mas é mais vulnerável a intrusões.

_**Fibre Channel**_ **SAN** **–** Protocolos

A figura 8 apresenta a pilha de protocolos da arquiteta FC  ou pilha de _**Storage Area Network**_, o iSCSI. O iSCSI não será abordado, pois esta tecnologia, que utiliza redes TCP/IP para comunicação origem-destino, é uma solução alternativa ao _**Fibre Channel**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261712/14543.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/7/261712/14543.jpg)

Protocolos FCSAN

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

Protocolo FCP

O _**Fibre Channel Protocol**_ (FCP) é um Protocolo de Transporte SCSI e que foi desenvolvido para facilitar a comunicação de blocos de dados entre origem-destino em redes FC, Figura 9. No modelo de redes FC, FCP é um protocolo da camada FC-4. Além disso, para o uso do FCP nenhuma modificação especial é necessária no FC e no SCSI, pois utiliza o mesmo formato de quadro e de serviços definidos pelas especificações do FC e a arquitetura SCSI já existente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267954/14544.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267954/14544.jpg)

Figura 9 - FC-SAN Tradicional

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

Na Figura 10, os comandos SCSI e dados são encapsulados no FCP antes do encapsulamento do FC. Este é o fator pelo qual o Fibre Channel tem um menor _**overhead**_.

Pilha do FCP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267955/14545.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267955/14545.jpg)

Figura 10 - Encapsulamento SCSI

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

FCIP

_**Fibre Channel over IP**_ (FCIP) permite a conexão de dois FC-SANs interligando _**switches**_ através de TCP/IP. Um túnel ponto a ponto é criado através de uma rede IP, e o tráfego _**Fibre Channel**_ é encapsulado e desencapsulados nos terminais. Quando um túnel é estabelecido, dois FC-SANs se juntam para formar um só FC-SAN virtual. Todos os switches em cada lado do túnel ver os outros switches como se fossem locais. A Figura 11 ilustra o túnel FCIP ligando dois SANs.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267959/14546.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267959/14546.jpg)

Figura 11 - FCIP SAN

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

Todos os dispositivos Fibre Channel nas extremidades do túnel compartilham o mesmo endereço, podendo implementar conexão de Portas_E, um virtual _**inter-switch link**_ (VISL), à longa distâncias, protocolos _**Fibre Channel switch-to-switch**_ são passados via WAN. Permitindo aplicações a longas distâncias, como o espelhamento de dados de uma empresa para outra localização geográfica, onde os dados possam ser recuperados caso aconteça algum desastre na empresa.

O FCIP apresenta um overhead muito maior que o FCP, como pode ser analisado na Figura 12. Além do _**overhead**_ do Ethernet, IP e TCP, deve ser considerado o overhead do _**Fibre Channel Frame Encapsulation**_ (FC-FE) e do quadro FC.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267960/14548.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267960/14548.jpg)

Figura 12 - Pilha do FCIP

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

iFCP

O _**Internet Fibre Channel Protocol**_ (iFCP) é um protocolo _**gateway-to-gateway**_ que interliga dispositivos do Fibre Channel através da rede IP/Ethernet. O iFCP pode ser implementado de duas formas.

A primeira forma é os iFCP _**Gateways**_ ligarem-se aos FC _**switches**_, Figura 2.20. Esta é a maneira mais empregada do uso do iFCP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267971/14549.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267971/14549.jpg)

Figura 13 - Principal implementação de iFCP

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

Na outra forma, os iFCP _**Gateways**_ substituem os FC _**switches**_, e são ligados diretamente aos dispositivos _**Fibre Channe**_l, Figura 14. Com isso, é possível criar soluções SAN baseada em IP que usem dispositivos do _**Fibre Channel**_, mas que não requerem _**FC Fabric**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267970/14550.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267970/14550.jpg)

Figura 14 - Conceito original no projeto do iFCP

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

O iFCP apresenta desafios para sua adoção, pois para as suas formas de implementação, há outras soluções concorrentes similares. No caso em que os iFCP Gateways são implementados em conjuntos com os FC switches, o iFCP compete contra o FCIP. Nesta questão o FCIP é uma solução mais barata e de menor complexidade. No outro caso, em que os dispositivos terminais do Fibre Channel são ligados diretamente via IP/Ethernet, o custo é menor, mas a solução é semelhante à solução proposta pelo iSCSI. O iSCSI, que será abordado mais a frente, foi desenvolvido para ser um solução alternativa para FC-SAN. Portanto, o iSCSI fornece uma solução mais elegante e econômica.

Na camada iFCP, os 24-bit de endereço do dispositivo FC é mapeado para um endereço de IP único de 32-bit, fornecendo endereçamento nativo de IP para cada cliente e alvo que compõem a rede FC. O iFCP substitui a camada FC-2 pelas camadas TCP/IP para uma transmissão confiável pela rede IP.

O endereçamento único de IP para cada dispositivo _**Fibre Channel**_ permite a comunicação de qualquer ponto a qualquer ponto, como mostra a Figura 15. A comunicação não está restrita aos túneis como no FCIP e pode ser roteada para o destino que desejar. Permitindo a convergência das aplicações de armazenamento SAN, LAN, e WAN usando as qualidades do Fibre Channel.

iFCP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267975/14551.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267975/14551.jpg)

Figura 15 - IFPC

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267976/14552.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267976/14552.jpg)

Figura 16 - Pilha do iFCP

Fonte: Cisco Networkers 2006 - SAN-1501 - Introduction to Storage Area Networking

FCoE

Fibre Channel over Ethernet (FCoE) foi desenvolvido com a intenção de manter o modelo _**Fibre Channel**_. No FCoE, o quadro nativo do FC é mapeado no quadro do _**Ethernet**_. Permitindo que tráfegos FC sejam transmitidos através da rede _**Ethernet**_.

Atualmente, as empresas mantém duas redes, uma para LAN, baseada no _**Ethernet**_, e outra para SAN, baseada no _**Fibre Channe**_l. Convergir as duas redes em uma única infra-estrutura Ethernet permitirá a consolidação I/O. Num mesmo cabo físico poderá passar tráfegos poderá passar tráfegos FC e da Ethernet, figura 17.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/0/268020/14553.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/0/268020/14553.png)

Figura 17 -Implementação da convergência

Fonte: http://fibrechannel.org

Para o entendimento de como é possível essa convergência, três características do FCoE devem ser analisadas: encapsulamento, formato do quadro e congestionamento do _**Ethernet**_.

**Encapsulamento**

O FCoE fornece a capacidade de carregar a camada FC-2 sobre a camada _**Ethernet**_, como na Figura 18. Isso permite o Ethernet transmitir as camadas FC-3 e FC-4 através das camadas IEEE 802.3 do _**Ethernet**_. Esse mapeamento feito pelo FCoE que permite o tráfego FC passar pela infraestrutura Ethernet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268321/14554.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268321/14554.png)

Figura 18 - Mapeamento do FCoE

Fonte: http://www.fibrechannel.org

Por encapsular inteiramente o quadro do _**Fibre Channel**_ diretamente no interior do _**payload**_ _**Ethernet**_, o FCoE evita o _**overhead**_ de qualquer protocolo intermediário, Figura 19. Assim, garantindo altos níveis de desempenho e interoperabilidade com as redes SAN já existentes.

Pilha do FCoE

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268187/14555.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268187/14555.png)

Figura 19 - Pilha do FCoE

Fonte: http://fibrechannel.org

**Formato do Quadro**

O quadro Fibre Channel encapsulado é constituído de cabeçalho, os dados a serem transportados e o CRC. A manutenção do cabeçalho original do FC permite a integração do FCoE a redes SANs sem a necessidade de um gateway. A Figura 20 ilustra o formato do quadro.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268188/14556.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268188/14556.png)

Figura 20 - Formato do Quadro Fibre Channel

Fonte: http://fibrechannel.org

**Congestionamento do Ethernet**

Um dos desafios enfrentados no desenvolvimento do FCoE, foi o transporte de dados pelo _**Ethernet**_ sem que haja perdas de quadros. Congestionamento em uma rede onde não pode haver perdas é um problema que deve ser gerenciado.

O Fibre Channel e Ethernet gerenciam o congestionamento, resumidamente, da seguinte forma:

·         **Fibre Channel** gerencia o congestionamento pelo controle de fluxo baseado em créditos que garante, em condições normais, a não perca de informações.

·         **Ethernet** junto com TCP/IP gerencia o congestionamento pelo mecanimos de controle de fluxo descarte de pacotes.

Entretanto, controle de fluxo descarte de pacotes não é aceitável, pois há perdas de informações. Contudo, o IEEE 802.3X Ethernet contém um função conhecida como _**PAUSE**_. Essa função permite que se uma porta receptora estiver ocupada, ela possa enviar um quadro de controle para a porta de transmissão a fim de dar um intervalo na transmissão, figura 21. Essa função _**Pause**_ do Ethernet permite que o tráfego Fibre Channel passe pela rede Ethernet sem que ocorra perdas.

Controle de Fluxo no FC e Ethernet

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268384/14557.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268384/14557.png)

Figura 21 - Controle de Fluxo no FC e Ethernet

Fonte: http://fibrechannel.org

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268386/14558.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268386/14558.png)

Figura 22 - Distancias da tecnologia FC x GbE

Fonte: http://fibrechannel.org

A figura 24 apresenta uma configuração Genérica da tecnologia FC.

Após a inserção ou quando a ligação é ativada pelo dispositivo, a EEPROM é lida. Esta EEPROM contém todas as informações sobre o módulo que fornece as informações específicas sobre o dispositivo acelera os suportes de ligação, que é um DAC ou módulo óptico.

Se é um DAC ele indica se é passivo ou ativo e que ligação e comprimentos dos cabos são suportados. Se é um módulo óptico conectável que indica se suporta Modo multimodo (MM) ou Monomodo (SM) de cabos de fibra óptica. Esta informação ajuda o dispositivo definir sua saída e entrada por meio de configurações para otimizar os sinais para o melhor desempenho.

As configurações de aplicativos de FC são muitos, e são personalizados para atender às necessidades do usuário final. Estas configurações, no entanto, consistem de blocos de construção básicos, tais como servidores, switches e armazenamento.

O número de blocos de construção para os requisitos funcionais semelhantes pode ser exclusivo devido a layouts disponíveis para a planta física exemplo. Outra consideração é se a configuração de instalação é uma nova instalação ou uma adição a um já existente.

Seguem as figuras que representam o DAC

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268192/14561.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268192/14561.png)

Figura 23 - O Direct Attach Cable (DAC) or a pluggable optical module - módulos óptico de ligação.

Fonte: http://fibrechannel.org

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268193/14562.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268193/14562.png)

Figura 24 - Configuração Genérica

Fonte: http://fibrechannel.org