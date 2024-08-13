### Objetivo:

Neste tópico vamos estudar as topologias de conexão das redes wireless, assim como a forma correta da implementação de projetos usando tais topologias. Também veremos os serviços lógicos fornecidos pela estrutura 802.11 e como estes serviços interagem com as estações para produzir uma conectividade complexa e bem estruturada.

### Introdução

A arquitetura wireless IEEE 802.11 é formada por diversos equipamentos interagindo uns com os outros para que haja o fornecimento de conectividade às estações, sejam elas fixas ou móveis, tornando as redes wireless praticamente transparente para as camadas superiores igual a uma rede cabeada.

Existem três formas de configurar uma rede wireless LAN. Cada uma delas fornece uma série de serviços e consequentemente requerem diferentes componentes de hardware, possibilitando assim aplicações e capacidades maiores para atendimento a muitas estações. As topologias empregadas nas redes wireless são:

- Topologia IBSS – _Independent Basic Server Set._
- Topologia BSS – _Basic Server Set._
- Topologia ESS – _Extended Service Set._

### Modelo IBSS – _Independent Basic Server Set_ ou _Ad-Hoc_

O modelo _**ad-hoc**_ ou IBSS funciona como um conjunto de estações que se comunicam entre si sem a necessidade de um ponto de acesso (_**Access Point**_ ou Rádio) para gerenciar a rede e oferecer serviços. As estações se comunicam diretamente umas com as outras. Essa rede atende a maioria das necessidades de usuários, ocupando uma pequena área que desejam trocar arquivos de suas estações, conforme ilustrado na figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298907/18373.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298907/18373.jpg)

Figura 1 - Topologia IBSS

### Modelo BSS _– Basic Server Set_ ou Infraestrutura

O modelo _**Basic Server Set**_ ou Infraestrutura utiliza apenas um _**Access Point**_ para que as estações possam trocar informações. O Access Point neste caso exerce a função de mediador para todo o tráfego da rede e não há comunicação direta entre as estações, o que é feito somente através do rádio.

Se uma estação precisa se comunicar com outra, ela encaminhará o frame para o _**Access Point**_ que, por sua vez, o transmitirá para a estação destino que esteja dentro da sua área de cobertura.

Neste caso de topologia, o _**Access Point**_ funcionará como um portal para a rede cabeada e também contribuirá para a economia de energia das estações, pois ele detectará quando uma estação entrou em modo de economia de energia e armazenará os frames destinados à referida estação. Estações operando em modo bateria podem desligar o transmissor wireless e religá-lo apenas para transmitir e recuperar frames armazenados pelo _**Access Point**_. A figura 2 ilustra uma rede em topologia BSS. (MEDEIROS, 2010)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298910/18374.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298910/18374.jpg)

Figura 2 - Topologia BSSS

### Modelo ESS – _Extended Server Set_

No modelo ESS - _**Extended Server Set**_ é definido como dois ou mais BSSs conectados por um sistema de cabeamento. Neste modelo, os usuários podem se movimentar livremente de um BSS e sua área de cobertura a outro sem perder a conexão lógica com a rede. Este processo é conhecido como _**“Roaming”**_ exatamente igual aos sistemas de telefonia celular. Esse tipo de configuração atende as necessidades de grandes áreas de cobertura conforme ilustrado na figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/0/299025/18376.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/0/299025/18376.jpg)

Figura 3 - Topologia ESS

Quando um frame necessita ser enviado a uma estação que se encontra na área de cobertura de outro _**Access Point**_, ele é encaminhado à rede cabeada que fará a transição de um rádio para outro automaticamente e também fornecerá conexão à Internet e servidores da rede.

Portanto, numa configuração ESS, todos os _**Acess Points**_ utilizados na montagem da rede devem estar conectados por cabos UTPs a um equipamento _**Switch**_ e todos eles executaram o processo de portal para a rede cabeada. Um portal é um ponto lógico no qual estações fixas, não 802.11, têm acesso à rede wireless e vice versa. (MEDEIROS, 2010)

### Serviços Lógicos de Distribuição

O padrão 802.11 não detalha como deve ser o sistema de distribuição, mas define os serviços lógicos que ele deve prover para a interligação dos dispositivos. São definidos nove serviços para o sistema de distribuição, divididos em dois grupos: Quatro serviços da estação e os demais são do sistema de distribuição. Ambas as categorias de serviços são usadas pela subcamada MAC.

Os serviços de distribuição são fornecidos pelos _**Access Points**_ e lidam com a mobilidade das estações à medida que elas entram e saem das células, conectando–se e desconectando–se dos pontos de acesso e estendem a rede cabeada para a rede wireless fornecendo o portal. Os serviços de distribuição são os seguintes:

1. Associação: usado para a estação móvel se conectar aos pontos de acesso. A estação móvel anuncia sua identidade e seus recursos e se o ponto de acesso aceita–lá passará pelo processo de autenticação;
2. Desassociação: a estação móvel usa para se desligar ou sair do ponto de acesso;
3. Reassociação: utilizado para alteração de ponto de acesso; se usado corretamente não há perda de dados;
4. Distribuição: determina como rotear quadros enviados ao ponto de acesso;
5. Integração: responsável pela conversão do formato 802.11 para o formato exigido pela rede destino, por exemplo, o formato 802.3 das redes cabeadas.

Os serviços da estação são descritos a seguir:

1. Autenticação: o ponto de acesso envia um quadro de desafio especial à estação móvel, se esta estação tiver o conhecimento da chave secreta (senha), ela executará a descriptografia do texto desafio, responderá a este texto e novamente irá criptografar o quadro de desafio e executará a transmissão do mesmo de volta ao _Access Point_. Se o resultado for correto, a estação móvel será registrada.
2. Desautenticação: quando uma estação autenticada quer deixar a rede.
3. Privacidade: este serviço administra a criptografia e a descriptografia, isso é, para que todas as informações enviadas pela rede sem fio se mantenham confidenciais utilizando para isso o algoritmo de criptografia RC4.
4. Entrega de Dados: transmissão efetiva de dados, modelada com base no padrão Ethernet. Assim como em redes cabeadas, a transmissão dos dados não é totalmente confiável, então camadas mais elevadas devem assegurar a integridade das informações através de detecção e correção de erros.

### Autenticação e Associação de uma Estação a um _Access Point_

O padrão 802.11 provê a habilidade de controlar o acesso à LAN através do serviço de autenticação no qual estações de trabalho informam sua identificação ao _**Access Point**_ numa topologia BSS ou ESS.

Um dispositivo wireless pode se autenticar em mais de um _**Access Point**_ ao mesmo tempo. Esse tipo de pré-autenticação permite que o dispositivo prepare outros APs para que possam entrar no espaço deles em um processo de _**roaming**_, em outras palavras, outros _**Access Points**_ respondem a um pedido de conexão de uma estação caso a mesma esteja saindo de uma área de cobertura e entrando em outra, atendida por outro rádio chamado de célula.

O processo de autenticação de uma estação é iniciado quando a estação envia a um _**Access Point**_ um frame de autenticação contento o mesmo SSID – _**Service Set Identifier**_, que em outras palavras é o nome da rede onde a estação deseja se comunicar.

Uma estação deve se autenticar e se associar a um AP antes de enviar a ele um dado. Para o _**Access Point**_ permitir a autenticação e a associação da estação, ela deve ter o mesmo identificador que o AP, ou seja, o mesmo SSID.

O SSID é um valor alfanumérico de 2 a 32 caracteres usados pela rede wireless como um nome da rede. Este nome é usado para segmentar a rede, como uma medida rudimentar de segurança e no processo de união à rede. (SANTOS JUNIOR 2005)

Uma vez que a estação esteja devidamente autenticada na rede, ela irá se associar ao _**Access Point**_ e a parir daí estará apta a enviar dados dentro desta rede.

Como foi dito, uma estação poderá estar autenticada a vários _**Access Point**_, mas associada a apenas um. Quando a estação se submete a autenticação, a mesma é repassada aos outros APs da rede através da rede cabeada onde a identificação será mantida numa relação de autenticação de estações, mas ela fica associada só em um AP, no qual a força do sinal de rádio frequência é o mais forte sentido em sua antena.

Quando uma estação se move dentro da sua célula de abrangência, o sinal de rádio frequência que chega à sua antena irá sofrer reduções na mesma proporção em que a estação se afasta do Access Point, e é neste momento que perceberá o sinal de outro _**Access Point**_ aumentar em sua antena. Então a estação poderá se desassociar do primeiro AP e se associar ao segundo sem que a rede perca nenhum dos frames encaminhados àquela estação, tal ação é denominada de salva guarda destes frames no AP, enquanto a estação troca sua associação num processo de _**roaming**_, conforme ilustrado na figura 4. (RAPPAPORT, 2009)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/9/301969/18377.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/9/301969/18377.png)

Figura 4 - Fluxo de Associação

### Fluxo de Dados em uma Topologia BSS

O processo de troca de dados entre estações no modelo de topologia infraestrutura ocorre da seguinte forma:

Primeiro as estações devem estar autenticadas e associadas ao AP e, portanto fazem parte das tabelas deste. Quando a estação 1 precisa enviar dados à estação 2, ela o fará enviando o frame ao _**Access Point**_ que responderá com um ACK, que é a confirmação de recebimento do frame. Então o AP procederá ao encaminhamento do frame à estação 2, que por sua vez responderá com um ACK de confirmação positiva do recebimento do frame e o processo então estará completo, conforme ilustrado pela figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/9/301986/18378.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/1/9/301986/18378.png)

Figura 5 - Fluxo na topologia BSS

### Fluxo de Dados em uma Topologia ESS

Na topologia ESS pode-se ter dois ou mais BSS com os _**Access Points**_ conectados através de uma rede cabeada.

Quando se utiliza está topologia e seja necessário transmitir um frame entre estações que estão conectadas a APs diferentes, o procedimento é o seguinte:

Primeiro as estações devem estar autenticadas e associadas aos respectivos _**Access Points**_. Como estes estão conectados através de uma rede cabeada, suas tabelas estão sendo constantemente trocadas pelo protocolo _**Inter Access Point Protocol**_ – IAPP - que tem a função de manter atualizados os dados. Portanto, todos os APs sabem exatamente quais estações estão associadas a ele e aos outros APs que compõem a rede.

O procedimento de ações e fluxo de dados tem os seguintes passos:

1. A estação 1 envia para o AP-1 um frame destinado à estação 2.
2. O AP-1 responde o recebimento do frame com um ACK.
3. O AP-1 envia o frame para o AP-2 através da rede cabeada.
4. O AP-2 envia o frame para a estação 2.
5. A estação 2 responde ao AP-2 com ACK confirmando o seu recebimento, conforme ilustrado na figura 6.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302224/18379.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302224/18379.png)

Figura 6 - Fluxo de dados na topologia ESS

### Revisão:

Nas redes wireless pode-se ter três tipos de configurações de topologias, sendo:

- Topologia IBSS – _Independent Basic Server Set_, onde não existe a utilização de um _Access Point_ e as estações estão conectadas entre si.
- Topologia BSS – _Basic Server Set_, onde existe apenas um _Access Point_ e as estações estão conectadas entre si através do AP.
- Topologia ESS – _Extended Service Set_, onde existe mais de um _Access Point_ e estes estão conectados entre si através da rede cabeada.

Na topologia ESS, com o emprego de mais de um Access Point, cada um deverá ocupar um canal diferente (canal 1, 6 e 11) e cada área de abrangência (celular) deverá estar 30% sobreposta para que possa permitir o _**roaming**_ das estações móveis, sem a perda de conexão com a rede.

Cada frame encaminhado numa rede wireless necessita da confirmação do seu recebimento pelo envio de um ACK.