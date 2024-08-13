### Introdução a redes de dados

Uma rede de dados é definida como um conjunto de nós (um nó pode ser um computador, roteador, switch, impressora, etc) capazes de enviar e receber através de um meio de comunicação, como mostrado na Figura 1. Criar redes de dados tem como objetivo permitir o compartilhamento de recursos, tais como programas e equipamentos, tornando-os ao alcance de todos os usuários. Um ambiente em rede proporciona, principalmente, o compartilhamento de informações importantes para o funcionamento das corporações como, por exemplo, o registro de clientes, fornecedores e folhas de pagamento, e em muitos casos, esse compartilhamento é feito de forma on-line para que possa ser acessada a partir de qualquer dispositivo conectado a internet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/1/6/8/0/1168037/17207.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/1/6/8/0/1168037/17207.png)

Figura 1 - Redes de dados

### Critérios para seleção de redes

Para se criar redes de dados podemos levar em consideração os seguintes critérios. Os mais importantes são desempenho, confiabilidade e segurança (Forouzan, B. A, 2007):

- **Desempenho**: O desempenho de uma rede pode ser medido de várias formas, dentre elas, podemos citar a largura de banda (taxa de transferência de bits por segundo), também conhecido por throughput. Mesmo que capacidade da rede, em termos de throughput seja elevada, o desempenho pode ser afetado pelo congestionamento. Portanto, devemos considerar essas duas variáveis em conjunto a fim de avaliar o desempenho de uma rede.
- **Confiabilidade**: Este critério está associado, por exemplo, com a capacidade da rede em suportar níveis elevados de tráfego sem que haja falhas que impeçam o seu funcionamento e também pelo tempo necessário para que o link volte em operação caso uma falha ocorra. Um bom sinônimo para a confiabilidade é a robustez. Normalmente nos perguntamos acerca de quão robusto é um determinado equipamento, como por exemplo, um celular, uma TV e, principalmente os equipamentos constituintes de uma rede.
- **Segurança**: Atualmente, a segurança dos dados que trafegam nas redes de computadores é fator de grande preocupação. Não existe nenhum sistema 100% seguro e, por isso, os métodos de prevenção de incidentes físicos, de acesso não autorizado e da proteção de dados devem ser levados em consideração durante a construção de políticas de segurança por parte das corporações. Na Figura 2 é mostrado uma topologia de rede contendo Sistemas de Detecção de Intrusão (IDS), além do Firewall, que permite interromper o tráfego com base em regras permissivas, ou seja, permite apenas o tráfego explicitamente declarado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/8/0/8023/i02_549.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/8/0/8023/i02_549.jpg)

Figura 2 - Sistemas de detecção de intrusão.

### Linha local e Remota

Podemos classificar um link de rede de duas formas: o primeiro deles, chamado de **link local**, que possui uma ligação praticamente que direta entre o transmissor e o receptor, não necessitando que a informação passe pela rede da operadora de telecomunicações, portanto, o tráfego fica restrito a rede local (LAN), conforme Figura 1. Neste caso, utilizam-se os recursos locais da corporação, sem a necessidade de que o tráfego vá para fora. Em contrapartida, um **link remoto**, é utilizado quando desejamos conectar duas redes ou nós geograficamente separados. Neste caso, normalmente, há a necessidade de se utilizar a infraestrutura da operadora de telecomunicações, e por esse motivo, o transporte de dados passará por alguma tarifação. Este tipo de link é muito utilizado quando se deseja interligar a sede de uma empresa com a sua filial. Na Figura 3 é mostrado um link remoto entre um usuário residencial por meio da internet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293469/18426.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293469/18426.jpg)

Figura 3 - ilustração de uma conexão remota via VPN

### Ponto-a-ponto e Multiponto

As redes **ponto-a-ponto** são aquelas que interligam dois nós através do mesmo link de comunicação, como, por exemplo, a interligação entre uma matriz e filial por meio de duas antenas de rádio frequência, ou até mesmo, por um link de fibra óptica (dedicado), como mostrado na Figura 4 (a). Por sua vez, quando uma matriz possui diversas filiais consideramos que essa ligação é do tipo **multiponto,** como mostrado na Figura 4 (b). Na multiponto a capacidade do link é compartilhada entre os diferentes nós.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363107/28403.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363107/28403.png)

Figura 4 - (a) ligação ponto-a-ponto e (b) multiponto

Fonte: Elaborado pelo professor conteudista.

### Linha discada

Popular, por volta dos anos 2000, o acesso à internet via conexão discada, atualmente, é pouco utilizada devido a sua baixa taxa de transferência de dados, em torno de 56 Kbps (Kilobits por segundo). Apesar disso, a conexão discada, também conhecida como dial-up, tem importância histórica para a comunicação de dados. A conexão dial-up proporciona a conexão de acesso à Internet por meio de linhas telefônicas entre a conexão do usuário e o provedor de telecomunicações.

Para estabelecer essa comunicação o computador do usuário necessita de um modem interno ou externo. O modem tem a função de modular (converter os dados em sinal de áudio) e demodular (converte o sinal de áudio para dados). Justamente por utilizar todo o canal de voz, em uma conexão discada não é possível utilizar a mesma conexão para transportar dados e realizar uma chamada telefônica e, além disso, como a banda utilizada para transmissão de voz é baixa (de 4KHz), a taxa de transferência dados também é baixa, de 56 Kbps, como comentado anteriormente. Na Figura 5(a) é mostrado um modem interno para computador e na Figura 5 (b) um modem externo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/1/357196/28406.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/1/357196/28406.jpg)

Figura 5 (a) modem interno e (b) modem externo

Fonte: https://upload.wikimedia.org/wikipedia/commons/b/bb/External_rs232_serial_dialup_fax_modem.jpg

### Fluxo de dados

O sentido de troca de informações entre dois nós pode de forma simplex, half-duplex e full-duplex, conforme descrito a seguir tendo como base a Figura 6.

- **Simplex:** No modo simplex, a comunicação é feita em uma única direção (unidirecional). Controle-remotos e os teclados são exemplos de uma comunicação em modo simplex. Neste modo de transmissão toda a banda é utilizada para enviar dados em uma única direção.
- **Half-duplex:** Uma transmissão em modo half-duplex ocorre de forma bidirecional, mas não de forma simultânea. Na transmissão entre dois nós, apenas um deles pode transmitir, enquanto que outro nó fica no aguardo. As antigas redes Ethernet do tipo 10base-2 e 10base-5 (redes com cabo coaxial) são exemplos de redes half-duplex. Em tais redes, toda a capacidade do meio de transmissão é utilizada por apenas um nó, caso dois nós enviassem simultaneamente ocorria o que é conhecido como colisão de dados. Em virtude destes problemas, tais redes foram substituídas por redes do tipo full-duplex.
- **Full-duplex:** diferentemente do modo half-duplex, o modo full-duplex permite que dois nós enviem dados de forma simultânea. Como analogia, podemos imaginar esse modo de transmissão como rodovia de mão dupla fluindo em ambas as direções. As de computadores do tipo 100base-T e telefônicas são exemplos deste tipo de rede. No sistema telefônico tradicional ou por meio de uma chamada via Internet são exemplos de full-duplex, já que permitem que duas possam ouvir e conversar simultaneamente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/1/0/351071/28160.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/1/0/351071/28160.png)