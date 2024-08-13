### **Banda Base e Banda Larga**

Banda Base (em Inglês baseband) e banda larga (em Inglês Broadband) são duas formas distintas de como utilizar a capacidade do meio de transmissão para transmitir dados que serão descritas em detalhes abaixo.

### Banda Base

Em termos elétricos, a sinalização banda base utiliza toda largura de banda (em MHz) disponível para transmissão de dados digitais, como mostrado na Figura 1. A sinalização em banda base, o valor da frequência máxima é igual a “fmax” e da mínima é fixada em 0. Em outras palavras, quando há a transmissão do bit 0 a frequência utilizada será f=0 Hz, e para transmissão do bit 1, utilizamos a frequência fmax. De maneira simplificada, esse conceito pode ser entendido como: Se existe uma frequência no meio de transmissão, existe uma corrente e, consequentemente, uma tensão.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/7/363737/26732.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/7/363737/26732.png)

Figura 1 - Banda Banda Base e Banda Larga

Fonte: http://4.bp.blogspot.com/-97B5Sckr46U/T-r0_98QpHI/AAAAAAAAAAs/_8Zb_lKh_xk/s1600/baseband_broadband.jpg

De forma geral, uma transmissão em banda base ocorre da seguinte maneira:

- A transmissão é feita em alta velocidade;
- Não utiliza nenhuma técnica de modulação, ou seja, não é necessário que ocorra qualquer variação na frequência, amplitude ou fase da portadora;
- Utiliza a capacidade de todo o canal;
- Na maioria dos casos a transmissão é do tipo digital;
- Tipicamente utilizadas em curtas distâncias;
- Não é possível a multiplexação por divisão de frequência.

**Aplicações da banda base**

A transmissão em banda base é utilizada principalmente em redes de computadores, mas também o seu conceito pode ser utilizado para gravação de dados em meios ópticos e magnéticos. Em redes de computadores, mais especificamente em redes do tipo Ethernet, a transmissão é feita em banda base, isso significa que toda a capacidade do meio de transmissão é utilizada para transmitir bits sem qualquer processo de modulação, fazendo com que apenas um computador tenha a permissão de acessar o meio de transmissão. Algumas tecnologias Ethernet são mostradas na Tabela 1.

Tabela 1 - Diferente Tecnologias Ethernet.

|Tecnologia Ethernet|Denominação|Cabo|Largura de Banda(em Mbps)|Alcance (m)|
|---|---|---|---|---|
|[[10Base-2]]|Ethernet(thin Ethernet)|Cabo coaxial fino|10|185|
|[[10Base-5]]|Ethernet(thickEthernet)|Cabo coaxial grosso|10|500|
|[[10Base-T]]|Padrão Ethernet|Par trançado cat. 3|10|100|
|[[100Base-TX]]|FastEthernet|Par trançado cat. 5|100|100|
|[[100Base-FX]]|FastEthernet|Fibra óptica multimodo  <br>  <br>do tipo (62,5/125)|100|2000|
|[[1000Base-T]]|Gigabit Ethernet|Par trançado (cat. 5)|1000|100|
|[[1000Base-LX]]|Gigabit Ethernet|Fibra óptica monomodo ou multimodo|1000|550|
|[[1000Base-SX]]|Gigabit Ethernet|Fibra óptica multimodo|1000|550|
|[[10GBase-SR]]|10Gigabit Ethernet|Fibra óptica multimodo|10|500|
|[[10GBase-LX4]]|10Gigabit Ethernet|Fibra óptica multimodo|10|500|

  
  

Fonte: Tanenbaum, Andrew S. - 2011.

A nomenclatura acima como, por exemplo, 10Base-T, apresentada na tabela para designar as diferentes tecnologias Ethernet, diz respeito a:

**Xbase-Y**

**X:** Corresponde a taxa de transmissão nominal em múltiplos de bits (Mbps – Megabits por segundo e Gbps – gigabits por segundos);

**Base:** Sinalização Banda Base;

**Y:** Específica o tipo de cabo e o seu comprimento máximo.

Uma transmissão em banda base em redes de computadores utiliza técnicas diferentes de codificação de linha ou codificação em bloco para cada tipo de tecnologia Ethernet, como mostrado na Tabela 2. A codificação de linha consiste em converter dados binários em uma sequência de bits (Figura 2) que possa ser representado por variações de tensão no meio de transmissão.

Tabela 2 - Codificação de linha e de bloco para as diferentes tecnologias Ethernet.

![[Screenshot_from_2021-12-02_22-50-34.png]]

Fonte: Torres, Gabriel. Redes de Computadores - 2014.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223942/7640.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223942/7640.jpg)

Figura 2 - Codificação de linha.

### Banda Larga

Diferentemente da transmissão em Banda Base, a transmissão em Banda Larga consiste na transmissão simultânea de múltiplos tipos de sinais e tráfego. Apesar de ser um termo empregado para designar um método de transmissão, o termo “Banda Larga” se popularizou como método de acesso à internet, entretanto, o conceito de Banda Larga pode ser utilizado em diferentes situações, não apenas para aplicações de acesso à Internet. A transmissão em banda larga possui as seguintes características gerais:

- Utiliza sinalização analógica;
- Os sinais fluem na forma de ondas eletromagnéticas ou ópticas;
- Vários tipos de transmissão são suportados simultaneamente como, por exemplo, transmissão de dados, TV a cabo e telefonia. Cada um ocupando uma frequência diferente, como mostrado na Figura 3;
- A transmissão é unidirecional, isso significa que há a necessidade de alocar um canal para recepção e outro para transmissão; também é possível ligar cada dispositivo a dois cabos, um usado para transmissão outro para recepção.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261481/13867.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261481/13867.png)

Figura 3 - Banda POST de telefonia, banda de Upstream utilizado para upload e a banda Downstream utilizada para download em uma rede banda larga do tipo ADSL.

**Aplicações de Banda Larga**

As maiores aplicações para Banda Larga, como já comentado, estão associadas com o fornecimento de acesso à Internet, tanto residenciais quanto para redes empresariais. Atualmente, existe uma série de tecnologias xDSL (Digital Subscriber Line) que aproveitam a infraestrutura de telefonia fixa de cabos de pares trançado já existente para disponibilizar acesso à Internet de Banda Larga.

Aproveitar a infraestrutura de telefonia já existente permite baratear o fornecimento dos serviços de Banda Larga para o usuário final. Existe uma enormidade de tecnologias xDSL, as principais delas são ADSL, ADSL2, HDSL e VDSL.

**Componentes de uma rede xDSL**

A infraestrutura básica de uma rede DSL é composta de cabos par trançados e equipamentos específicos do lado do usuário e da operadora. Em relação aos equipamentos dos usuários, existe um dispositivo que conecta o modem e o telefone, chamado de POST splitter (mostrado na Figura 4), tendo como finalidade separar os sinais de dados digitais e o canal de voz. Do lado da operado de telecomunicações, o cabo proveniente do cliente conecta-se a central telefonia a um dispositivo conhecido como multiplexador DSLAM (Digital Subscriber Line Access Multiplexer), que separa novamente o trafego de voz e dados digitais. Após a separação, os dados digitais são enviados para uma rede, por exemplo ATM, enquanto que o sinal de voz é enviado para comutador telefônico do POST (Fígura 5).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261482/13870.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261482/13870.jpg)

Figura 4 - Interligação típica de uma instalação DSL residencial.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/7/363754/26780.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/7/363754/26780.png)

Figura 4 - Infraestrutura DSL

**Cable Modem**

Da mesma forma do que a tecnologia xDSL utiliza a rede de telefonia para transmitir dados digitais, a tecnologia Cable Modem aproveita a infraestrutura de transmissão de televisão para disponibilizar acesso à Internet. Entretanto, existe uma diferença fundamental entre as tecnologias xDSL e Cable Modem, a tecnologia Cable Modem utiliza normalmente cabo coaxial, além disso, a banda é compartilhada entre todos os usuários de uma mesma vizinhança, podendo chegar a 2000 usuários. Atualmente, também é possível fornecer o serviço de telefonia IP (VoIP – Voz sobre IP) por meio da tecnologia Cable Modem (dos Santo, Marçal, 2011).

Em uma transmissão via Cable Modem típica, cada canal de TV ocupa uma largura de banda de 6MHz, permitindo assim que seja possível a transmissão de centenas de canais. Um desses canais, de 6MHz ou superior, é reservado para transmissão de dados: Um canal de downstream (download) e um canal de 2MHz (ou superior) para upstream (upload), como mostrado na Figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/8/347858/26789.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/8/347858/26789.png)

Divisão de frequência para uma transmissão via cable modem

Fonte:

**Infraestrutura de uma rede Cable Modem**

Nas centrais de distribuição da operadora de telecomunicações existe um Sistema da Terminação de Cable Modem (CMTS ou Head End) são utilizados esquemas de modulação que adiciona ao meio de transmissão (coaxial ou fibra) todos os canais de TV, assim como os dados de downstream e upstream. Quando o sinal chega ao cliente, um separador (splitter) e interligado ao cable box (Popularmente conhecido com decodificador ou Sintonizador de TV) e ao cable modem que fornece o acesso à Internet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/8/9/348925/26790.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/8/9/348925/26790.png)

Fonte: http://www.ccuec.unicamp.br/revista/images/image9a.gif