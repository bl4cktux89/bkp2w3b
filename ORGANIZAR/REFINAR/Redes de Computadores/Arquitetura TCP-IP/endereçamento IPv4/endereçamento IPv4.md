### Introdução

O endereço IPv4 (Internet Protocol Versão, Protocolo de Internet versão 4) durante muito tempo foi o endereço de rede (camada de internet) mais utilizado para identificar os nós em uma rede. No entanto, devido a limitações de sua arquitetura, associada, principalmente, a incapacidade de suprir a necessidade sempre crescente de endereços e resolução de endereços (NAT), tem sido substituído gradativamente pelo endereçamento IPv6 (versão 6 do Protocolo de Internet. Mas não será do dia para noite que o IPv4 cairá em desuso, pelo contrário, ainda vai levar um bom tempo para que as redes, sejam elas, locais (LAN) e WAN (longa distância) migrem completamente. Por esse motivo devemos compreender muito bem como é tal endereço funciona para que possamos garantir que o processo adoção do IPv6 seja feita sem grandes sobressaltos (KUROSE, James F e Ross, W. Keith, 2013).

### Atribuição de endereços IPs

O endereço IP é o identificador numérico associado a cada dispositivo de uma rede. Enquanto que o endereço MAC é considerado o endereço Físico, o endereço IP é considerado o endereço lógico, que possibilita a comunicação fim-a-fim ocorra. A arquitetura do endereçamento foi criada de forma independente em relação as tecnologias da camada de enlace de dados (Ethenet, Frame-relay, PPP, etc), ou seja, o hardware envolvido no processo de comunicação é irrelevante.

Ante de tratar do endereçamento IP propriamente dito, devemos compreender muito bem alguns conceitos fundamentais (Filippetti, Marco. A., 2017):

- Bit: é a menor porção da informação – sempre terá o valor 0 ou 1;
- Byte ou octeto: corresponde a uma porção de 8 bits;
- Endereço de broadcast: Endereço utilizado quando se deseja transmitir uma mensagem para todos os dispositivos da rede, de forma simultânea (de 1 para todos). Uma analogia a esse tipo de transmissão é encontrada na transmissão de TV aberta. Todos as TVs conseguem receber o sinal de um canal aberto.
- Endereço de Multicast: O endereço de multicast, por sua vez, é utilizado quando se deseja enviar uma mensagem para um grupo específico (de 1 para muitos). A mesma analogia anterior pode ser feita, neste caso, podemos comparar com o sistema de TV por assinatura – apenas os assinantes da operadora podem recebe um canal fechado.
- Endereço Unicast: Endereço usado na comunicação de um nó com apenas um nó (de 1 para 1). Seguindo a analogia, o unicast corresponde a uma transmissão de TV a cabo por demanda (pay-per-view). Somente o assinante que comprou o programa que poderá assistir aquela transmissão.

### Notação Decimal e Binária

A notação binária é base de qualquer sistema comunicação digital. No nosso dia a dia usamos o sistema decimal (base 10), chamado dessa forma pois utiliza 10 símbolos (de 0 a 9). A base indica a ordem da variação do número, em outras palavras, qualquer número decimal pode ser representado elevando-se a base 10 a algum número. Por exemplo, o número **123**:

- Ele possui três ordens decimais de grandeza (uma centena, duas dezenas, e três unidades), que corresponde a 1x10+ 2x10+3.10.
- A notação, portanto, usa a base 2. Isso significa que, se quisermos representar qualquer número, devemos manter a ordem 2 elevado a qualquer número. Sabendo-se disso, é possível converter qualquer número binário em decimal de acordo com a posição do dígito binário e a respectiva ordem de grandeza do mesmo.
- Por exemplo, o número binário 10101101 pode ser representado por: 1x2+ 0x2 + 1x2+ 0x2+ 1x2 +1x2 + 0x2+ 1x2 = 173. Outra forma de exibir esse processo é mostrado na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/1/6/1631621/38286.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/1/6/1631621/38286.jpg)

**Portanto, o binário 10101101****bin** **= 128 + 32 + 0 +8 + 4 + 1 =173****dec**

A sequência abaixo é muito importante para a conversão dos endereços IPv4 e deve ser memorizada. A memorização não é difícil, basta dobrar o valor em relação a posição anterior (da direita para esquerda).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/4/8/1574861/38287.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/4/8/1574861/38287.png)

**Exemplo 1: Qual é o endereço decimal quando todos os bits estão ligados (11111111) e desligados (00000000)?**

**Todos os bits ligados:** Quando os 8 bits estão ligados (bits 1): 11111111, corresponderá a um endereço decimal igual a 255:

![[Untitled 35.png|Untitled 35.png]]

**Todos os bits desligados:** Seguindo o mesmo raciocínio, um endereço em decimal igual 0 corresponderá a 00000000. Portanto, todo endereço IPv4 pode varia de 0 a 255 em cada um de seus octetos, como veremos na sequência.

### O Endereço IPv4

O endereço IPv4 possui como característica geral (Filippetti, Marco. A., 2017):

- O endereço IPv4 é formado por 32 bits;
- Os bits são agrupados em 4 grupos de oito bits, chamados de octeto ou byte;
- Utiliza-se a notação decimal separadas por pontos. Ex: 200.10.1.8;
- Cada octeto pode variar de 0 a 255, o que resulta em 256 possibilidades (2);
    
    8
    
- Se os oitos bits estão desligados (bits 0s) o decimal será 0. Caso a sequência seja de oito 1s o endereço em decima será 255.

### IPv4 – Um Endereço Hierárquico

O endereço IPv4, como já comentado, possui 32 bits, isso permite que tenhamos 4.294.967.296 (232), aproximadamente 4,29 bilhões de possíveis endereços. Parece muito, mas, como já dito anteriormente, não existem mais endereços IPv4 disponíveis. Para agravar essa situação, utilizamos um esquema hierárquico com o objetivo de usar de forma mais coerente os endereços e proporcionar maior desempenho para os roteadores. Se não utilizássemos o esquema hierárquico todos os roteadores teriam que ter conhecimento de todos os endereços IPs de todos os nós. Isso implicaria em um roteamento ineficaz.

O esquema hierárquico consiste em dividir o endereço IP em uma porção de REDE e uma porção de HOST. Ainda podemos definir uma outra porção conhecida como SUB-REDE. Isso é feito para que os roteadores encaminhem os pacotes baseados na porção de REDE/SUB-REDE. Podemos fazer uma analogia com o sistema de numeração de um telefone, conforme mostrado na figura abaixo. A primeira parte do endereço identifica o país, passando pela cidade, central e o número da assinante (Kurose, James F e Ross, W. Keith, 2013).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/4/8/1574896/38291.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/4/8/1574896/38291.png)

A hierarquia de endereçamento IPv4 é mostrada na figura abaixo. Os provedores de serviço de internet (ISPs) de camada 1 interconectam os principais links da internet. Tais link são de alta velocidade e são poucos ao redor do planeta. Eles conectam as principais redes e se conectam também aos ISP de segundo nível, que normalmente são os provedores locais empresariais, que por sua vez são ligados ao de terceiro nível.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/4/9/1574933/38293.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/4/9/1574933/38293.png)

### Endereçamento Classful – Classe Cheia

Quando a arquitetura de endereçamento IPv4 foi definida, os cientistas de rede decidiram criar cinco classes de endereçamento, capazes de suportar uma quantidade distinta de endereços IPs de rede e de hosts. As classes de endereçamento são mostradas na figura abaixo. As três primeiras classes (A, B e C) podem ser utilizadas por qualquer instituição, enquanto que as faixas D e E são de uso restrito para multicast e experimental, respectivamente. Por esse motivo falaremos em detalhes das classes A, B e C.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/5/3/1575371/38295.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/5/7/5/3/1575371/38295.png)

**Classe A:**  para identificar um endereço de classe A basta olharmos para o primeiro octeto. Todo endereço de classe A começa com **1**.0.0.0 e vai até **127**.255.255.255. Sendo a faixa do 127 destinado ao endereço de Loopback, também conhecido como local host. Como pode ser observado na tabela abaixo, a porção de Rede (N) corresponde a apenas ao primeiro octeto, o segundo, terceiro e quarto octetos são destinados a Hosts (H) – **R**.**H.H.H**. Na mesma tabela podemos observar que a máscara padrão é 255.0.0.0. Isso significa que temos 128 redes  (27) e em cada rede é possível ter 16.777.214 hosts (224 – 2). O “-2” significa que o primeiro e último não podem ser utilizados já que o primeiro identifica a rede e o último o broadcast da rede. Veja os exemplos abaixo:

**Exemplo 2:** Determine os endereços de rede e broadcast para o endereço classe A 100.45.39.8.

**Resposta:** Como o endereço é de classe A, apenas o primeiro octeto corresponde a rede (R.H.H.H). Sendo assim, o endereço 100.0.0.0 é de rede (primeiro endereço IP) e o broadcast corresponde ao último endereço, 100.255.255.255. Portanto o endereço de host 100.45.39.8, está localizado na rede 100.0.0.0 e todos que estão nessa rede quando necessitam enviar para todos utilizarão o IP de broadcast 100.255.255.255.

**Exemplo 3:** Determine o número de IPs válido para o endereço de rede 50.0.0.0.

**Resposta:** Como o endereço é de classe A, apenas o primeiro octeto é de rede e os demais são de hosts (R.H.H.H). Lembrando que o primeiro identifica a rede e o último é de broadcast, teremos então 24 bits de hosts. Fazendo 224-2 = 16.777.214 hosts. Isso significa que teremos mais de 16 milhões de endereço disponíveis para colocar em qualquer interface de rede. O primeiro IP válido é 50.0.0.1 e o último válido é 50.255.255.254.

**Classe B:** Seguindo o mesmo raciocínio da classe A, qualquer endereço de classe B também pode ser identificado através do primeiro octeto. Todo endereço de classe B começa com **128**.0.0.0 e vai até **191**.255.255.255. Entretanto, como pode ser observado na tabela abaixo, a porção de Rede (N) corresponde ao primeiro e segundo octetos, o terceiro e quarto octetos são destinados a Hosts (H) – **R.R.H.H.** Na mesma tabela podemos observar que a máscara padrão é 255.255.0.0. Isso implica que teremos 16.384  (214) redes, e em cada rede é possível ter 65.534 hosts (216 – 2).  Cabe acrescentar que o 214 significa que existem 6 bits do primeiro octeto e 8 do segundo, por isso o elevado a 14 (6+8).

**Exemplo 4:** Determine o endereço de rede e de broadcast do endereço 160.65.200.252.

**Resposta:** Como o endereço é de classe B temos o primeiro e segundo octetos correspondentes a rede (R) e os demais para Hosts (H), por isso **R.R.H.H**. Sendo assim, o endereço 160.65.200.252, possui rede **160.65**.0.0 e o broadcast igual a 160.65.255.255.

**Exemplo 5:** Qual a faixa de endereços IPs válidos para o endereço de rede 180.80.0.0?

**Resposta:** O endereço IP corresponde a um endereço IP de rede de classe B. Por isso,  temos o primeiro e o segundo octetos de rede e os demais para host (R.R.H.H). Sendo assim, o primeiro endereço IP válido é logo após o de rede e igual a 180.80.0.1 e o último válido corresponde ao último IP antes do broadcast (180.80.255.255) e por isso ele é igual a 180.80.255.254.

**Classe C:** Qualquer endereço de classe C também pode ser identificado através do primeiro octeto. Todo endereço de classe C começa com **192**.0.0.0 e vai até **223**255.255.255. Entretanto, como pode ser observado na tabela abaixo, a porção de Rede (N) corresponde aos três primeiros octetos, e o quarto octeto é destinado a Hosts (H) – **R.R.R.H**. Na mesma tabela podemos observar que a máscara padrão é 255.255.255.0. Isso implica que teremos 2.097.150 (221) redes, e em cada rede é teremos 254 hosts (28– 2).  Cabe acrescentar que o 221 significa que existem 5 bits do primeiro octeto e 8 do segundo e terceiro, por isso o elevado a 21 (5+8+8).

**Exemplo 6**: Qual o endereço de rede e broadcast para o endereço de host 192.168.1.3 ?

**Resposta:** O endereço é de classe C, já que o primeiro octeto está dentro da faixa de 192 a 223. Por isso, a máscara padrão é 255.255.255.0 que corresponde a R.R.R.H. Sendo assim, os três primeiros octetos são de rede - 192.168.1.x -  e último para host, então o endereço de rede será 192.168.1.0. O broadcast corresponde ao octeto de host marcado com 255, portanto, 192.168.1.255.

**A importância da máscara padrão e de sub-rede**

A máscara padrão possui duas grandes finalidades para o funcionamento das redes. A primeira delas informa a qual rede um determinado endereço IP pertence. Esse processo é importantíssimo e é conhecido como função AND lógico. A função AND lógico corresponde a multiplicação do endereço (em binário) de Host pela sua máscara padrão ou de sub-rede. Veja o exemplo abaixo para o endereço IP 200.150.50.2 com máscara padrão igual 255.255.255.0.

![[Untitled 1 25.png|Untitled 1 25.png]]

Como pode ser observado na tabela acima, o resultado do AND lógico – end. 200.150.50.0 corresponderá ao endereço de rede do host 200.150.50.2.

A segunda finalidade da máscara de padrão ou de sub-rede informará a porção de Rede (R) e Host (H) e, consequente, conhecer a quantidade e faixa de hosts por rede,  conforme já mostrado anteriormente e resumida abaixo.

![[Untitled 2 23.png|Untitled 2 23.png]]