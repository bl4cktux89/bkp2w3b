### Objetivo:

Neste tópico daremos foco às redes sem fio para uso pessoal, com larga utilização nos dispositivos de celulares, controle remoto, mouse e teclado sem fio, notebooks, impressoras, câmeras digitais, vídeo game e equipamento de som. A tecnologia Bluetooth consegue interligar todos estes equipamentos sem a necessidade de cabos, fornecendo conectividade em alta velocidade.

### Introdução

Para pequenas redes e aplicações pessoais, o IEEE especificou a tecnologia _**Bluetooth**_ ou IEEE 802.15 para atendimentos às redes PAN – _**Personal Area Network**_ com distâncias de até 100 metros, dependendo da classe de operação, sem a necessidade de visada direta e nem da utilização de um _**Access Point**_.  As especificações do padrão _**Bluetooth**_ foi desenvolvida em 1994 por Sven Mattisson e Jaap Haartsen e padronizada em 1998 pelo _**Bluetooth SIG**_ _**(Special Interest Group),**_ com a participação de grandes empresas como a IBM, Nokia, Microsoft, Motorola, Toshiba e Lucent e hoje conta com mais de 8.000 empresas trabalhando no aperfeiçoamento desta tecnologia. (MEDEIROS, 2010)

### Especificações da Tecnologia Bluetooth

A tecnologia Bluetooth opera na faixa de frequência ISM de 2,450Ghz, padronizada com um protocolo de comunicação de camada 1, de baixo consumo e com alcance variando de 1 a 100 metros. Os dispositivos são classificados de acordo com o consumo e a potência irradiada e tem o alcance dos rádios divididos em três níveis mostrado na tabela 1.

### Tabela 1 – Classe da Tecnologia Bluetooth

![[Untitled 78.png|Untitled 78.png]]

A tecnologia _**Bluetooth**_ permite a comunicação entre dispositivos sem visada direta utilizando a modulação FHSS – _**Frequency Hope Spread Spectrum**_, com largura de banda de 1MHz em 79 canais que são alternados 1.600 vezes por segundo. As versões iniciais da tecnologia foram implementadas como sendo 1.1 e 1.2 e possuíam taxas de transferência de até 723 Kbps por segundo. As versões mais recentes (2.0 e 3.0) permitem taxas de transferência de dados na ordem de 2,1 Mbps e 480 Mbps, respectivamente. Como mais recente requisição da tecnologia _**Bluetooth**_ foi o lançamento da versão 4.0 que mantem as mesmas características da versão 3.0 porém, com ultra baixíssimo consumo de energia das baterias quando em uso sem fonte de alimentação direta. Portanto, se você tiver um dispositivo 4.0, acredite! você tem o que é de mais moderno nesta tecnologia, além de ser possível a interoperabilidade com as redes WIFI. Para um panorama mais ilustrativo, assista o _**link**_ na sequência, onde é demonstrado as principais características da tecnologia _**Bluetooth.**_

**ASSISTA AO VÍDEO**

[**https://www.youtube.com/watch?v=xA7VsamOzYw**](https://www.youtube.com/watch?v=xA7VsamOzYw)?

Os dispositivos Bluetooth podem ser associados em uma formação de rede na topologia IBSS ou ad-hoc para a troca de informações digitais entre suas estações. Quando temos a associação de até oito dispositivos _**Bluetooth**_ (no máximo), temos a rede denominada Piconet. A união de várias redes Piconet dentro de uma mesma área pode formar outra rede, conhecida como Scatternet,

### Redes Piconet

Uma rede na topologia Piconet pode ser formada de no máximo oito dispositivos que podem se comunicar através de um elemento central denominado de Mestre. Os outros sete dispositivos desta rede são denominados Escravos. A comunicação é iniciada sempre pela estação Mestre que assume a responsabilidade por controlar a utilização do canal de comunicação. A largura de banda é multiplexada no tempo e alocada para os demais dispositivos Escravos, utilizando a modulação FHSS com uma taxa de saltos de 1.600 vezes por segundo, conforme ilustrado na figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/5/293565/18694.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/5/293565/18694.png)

Figura 1 - Rede Piconet

### Redes Scatternet

As redes denominadas Scatternet são formadas pela união de duas ou mais redes Piconet distribuídas em duas topologias.

A primeira topologia ocorre quando um dos dispositivos é Escravo de uma rede Piconet e Mestre de outra, esta topologia é ilustrada na figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/5/293594/18695.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/5/293594/18695.png)

Figura 2 - Rede Scatternet

Em outra modalidade de topologia temos um dispositivo Escravo de uma rede Piconet que também é elemento Escravo de outra, ou seja, este dispositivo é Escravo de duas redes Piconet também ilustrada na figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/6/293607/18696.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/6/293607/18696.png)

Figura 3 - Rede híbrida

Na topologia Scatternet sempre vai existir mais de um dispositivo Mestre e não haverá sincronização das frequências da modulação FHSS, portanto, poderão ocorrer colisões quando dois dispositivos transmitem na mesma frequência. A solução neste caso será a retransmissão da informação de dados e o descarte do frame corrompido.

### Estabelecimento da Comunicação

No padrão _**Bluetooth**_ a comunicação entre os dispositivos e aplicações segue uma sequência de passos bem distintos a saber: primeiro acontece a criação de um canal físico, depois do estabelecimento do enlace físico é realizado a criação de um canal lógico e por final a conexão entre as aplicações.

### Estabelecimento do Canal Físico

O canal físico é estabelecido por uma sequência aleatória de saltos de frequência. A comunicação sempre é feita pelo dispositivo Mestre, que define a sequência dos saltos e o sincronismo dos dispositivos Escravos que fazem parte da rede. Quando os dispositivos Escravos solicitam uma conexão com o Mestre, estes recebem as informações de sincronização e o endereço do Mestre para seguir e gerar os saltos de frequência.

### Estabelecimento do Enlace Físico

Para o estabelecimento do enlace físico podem ser escolhidas duas modalidades, a primeira é a SCO – _**Synchronous Connection Oriented Link**_ onde, o enlace é ponto a ponto entre o Mestre e Escravo. O Mestre usa este enlace para reservar _**slots**_ de tempo para a comunicação com o Escravo. Na segunda modalidade chamada de ACL – _**Assynchronous Connection Less Link**_ é realizado um enlace ponto multiponto entre o dispositivo Mestre e todos os dispositivos Escravos.

### Estabelecimento de um Canal Lógico

Após a realização do enlace físico com uma das duas modalidades descritas, faz-se necessário a criação do canal lógico. O canal lógico é configurado quando um iniciador envia uma requisição de estabelecimento de uma conexão com o receptor. Esta solicitação é feita pela camada L2CAP – _**Logical Link Control and Adaptation Protocol**_, responsável por multiplexar os dados das camadas superiores e converter diferentes tamanhos dos frames.

### Conexão entre Aplicações

A conexão entre as aplicações é efetuada após a criação do canal lógico e pode-se obter diversas conexões de aplicações através de um mesmo canal lógico. Quando um dispositivo _**Bluetooth**_ deseja se comunicar, ele envia um quadro de pesquisa chamado _**Inquiry**_ em diferentes frequências de saltos. Os dispositivos habilitados a responder enviam um quadro FHSS contendo todas as informações necessárias ao estabelecimento de um canal físico, como classe, tipo do dispositivo, endereço e sincronização de relógio. Todas estas informações enviadas são denominadas de _**paging.**_

Quando os requisitos para a conexão física forem satisfatórios, o dispositivo selecionado para a comunicação responde com as informações necessárias para o estabelecimento do canal físico, e após o recebimento das informações de _**paging**_, o dispositivo inicia a criação de uma conexão entre as camadas superiores do modelo de referencia OSI, finalizando assim todo o processo de conexão e então os dispositivos estarão aptos a se comunicar. (SANTOS JUNIOR, 2005)

### Revisão:

- A tecnologia _Bluetooth_ recebeu a padronização 802.15 do IEEE.
- A tecnologia _Bluetooth_ foi desenvolvida para aplicações PAN – _Personal Área Netwok_ e está disponível em diversos equipamentos como notebooks, celulares, PDAs, Vídeo Games, teclado e mouse sem fio.
- O _Bluetooth_ trabalha através de três classes que determinam sua potência irradiada e sua distância de alcance.
- Pode-se montar uma rede com dispositivos _Bluetooth_ na configuração IBSS ou ad-hoc sem a necessidade de um _Access Point_ como nas configurações BSS do padrão IEEE 802.11.
- O padrão _Bluetooth_ trabalha na modulação FHSS e não necessita de visada direta entre dispositivos.
- As redes montadas com dispositivos _Bluetooth_ recebem o nome de Piconet formada por até oito dispositivos ou Scatternet que é uma associação de duas ou mais redes Piconet.