[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/3/253330/9869.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/3/253330/9869.png)

Campos de controle do HDLC

**Protocolo** _**High Level Data Link Control**_ **(HDLC)**

**1. Introdução**

No período em que não havia regras definidas de comunicação nas redes de computadores, alguns fabricantes produziam seus próprios sistemas e, com isso, criavam suas próprias regras de funcionamento e operação.

Com a inexistência da interoperabilidade entre sistemas, não havia a menor possibilidade de equipamentos de marcas diferentes comunicarem-se e trocar informações. O princípio da comunicação foi caótico e levou muitos anos até ser encontrado um modelo único de conectividade e troca de protocolos igualmente compatíveis para uma comunicação entre sistemas diferentes.

O consenso geral para diversos computadores interagirem de forma satisfatória e interligada em redes, deveriam seguir determinados “protocolos” e como estes eram extremamente complexos de se estabelecer, surgiu a necessidade de criar regras comuns a todos os fabricantes então existentes.

Diante da situação acima, a ISO definiu uma arquitetura de redes de computadores chamada Interconexão de Sistemas Abertos ou _**Open Systems Interconections**_ (OSI), que dividiu todas as operações da interligação de forma hierárquica em sete camadas, denominado Modelo de Referência OSI.

Este modelo permitiu que as organizações tratassem a informação a ser transmitida em sete níveis diferentes e com isso, especificassem e padronizassem cada nível com determinados protocolos e procedimentos. A camada ou o nível mais elementar é a ligação física entre os equipamentos da rede, tratando dos aspectos elétricos e mecânicos. (SOARES 1995)

A partir da camada física, foram introduzidos outros níveis sucessivos a essa arquitetura, de tal forma que camadas superiores utilizavam serviços oferecidos pela camada imediatamente inferior, às quais se acrescentam novas funções que são oferecidas à camada superior, tornando esta arquitetura uma forma bem definida, oferecendo serviços mais sofisticados.

A grande maioria das Redes de Longa Distância se utiliza das três primeiras camadas para executar sua função de encaminhar de forma confiável a informação sem atrasos. As três camadas primárias são:

1 – Física

Regulamenta a transmissão dos bits através de um canal de comunicação, ou seja, define voltagens e tempos de duração de bits, tipo de transmissão _**(half-duplex ou full-duplex),**_ código de linhas e demais serviços mecânicos.

2 – Enlace

Garante a transmissão sem erros dos dados, através da camada física, fazendo a transmissão dos bits em quadros (grupo de bits definidos) e executando a confirmação do quadro recebido pelo receptor sem erros. Também é responsável pelo controle do fluxo para regular a velocidade relativa dos processos e da transmissão dos bits na linha.

3 – Rede

Responsável pelo controle interno da rede, regulamentando a comunicação entre os computadores e as centrais de comutação por pacotes, o encaminhamento dos mesmos, o controle de congestionamento, a contabilidade e a localização do destinatário dentro de uma rede complexa. (STARLIN 2004)

**2. High Level Data Link Control (HDLC)**

_**High Level Data Link Control**_ (HDLC) é um protocolo antigo, da época dos computadores de grande porte da IBM, denominados de _**Main Frames**_.

O HDLC originou-se do _**Synchronous Data Link Control**_ (SDLC) da IBM, sofrendo modificações pela ISO, como o protocolo de enlace de dados de alto nível e posteriormente foi novamente alterado pelo _**Comittee Consultative for International Telephone and Telegraphy**_ (CCITT) transformando-o em seu LAPB utilizado como parte padrão de interface de rede X. 25. (ERICSSON 2000)

O HDLC é um protocolo de nível 2 do modelo de referencia OSI orientado a bits, que utiliza a técnica de inserção de bits para a transferência de dados. A grande maioria dos protocolos orientados a bits utilizam a estrutura de quadros apresentada na figura 1.

Apesar de o HDLC ser considerado um protocolo antigo, ainda é largamente utilizado na conexão de computadores de grande porte a terminais sem processamento e também muito utilizado nas conexões de redes de longa distância, devido à sua simplicidade e eficiência no transporte de datagramas.

Como explicação básica do protocolo HDLC, vamos esclarecer a função de cada campo, a começar pelo campo de Endereço, que na época dos grandes computadores era de extrema importância, pois por intermédio deste campo que se identificava cada um dos terminais conectados e ativos. No caso de links ponto a ponto, às vezes o campo de endereços é utilizado para fazer a distinção entre comandos e respostas.

O campo que antecede o de Endereços é denominado campo _**Flag**_, formado por um conjunto de 8 bits (1 byte), sempre com o mesmo valor igual a 01111110. O campo _**Flag**_ inicializa e termina o protocolo HLDC precedido pelo campo Total de Verificação.

O campo Controle é usado para número de sequência, confirmações e demais finalidades discutidas nos três tipos de quadros HDLC existentes. O campo Controle será amplamente estudado posteriormente, com uma maior riqueza de detalhes.

O campo _**Payload**_ pode conter qualquer informação, curta ou longa, embora a eficiência do Total de Verificação diminua com o aumento do comprimento do _**Payload**_, pois seu tamanho está ligado diretamente à maior probabilidade de ocorrer erros.

O campo Total de Verificação é uma variação do código de redundância cíclica cuja função principal é a verificação de que todos os dados chegaram corretamente no destinatário, sem erros ou perdas.

E finalizando mais uma sequência de 8 bits de _**Flag**_ para concluir o quadro. Nas linhas ponto a ponto, a sequência de _**Flags**_ são transmitidos continuamente quando estiverem ociosas, ou seja, sem dados para a transmissão.

O campo Controle é responsável pela formação e informação dos três tipos de quadros existentes no HDLC, que são: Quadros de Informação, Quadros de Supervisão e Quadros não numerados, conforme figura 2 que demonstra os 8 bits do campo Controle e suas funções específicas. (ERICSSON 2000)

**2.1 Quadro de Informação**

A figura 2 A demonstra o campo de Controle para um Quadro de Informação. Este Quadro inicia-se com um bit “0” no local do primeiro bit do Campo de Controle (bit 1) e utiliza os três bits subsequentes para descrever o tamanho da janela deslizante do campo Seq. Isso significa que a qualquer momento, pode haver até sete quadros não confirmados pendentes. O campo Seq traz o número de sequência dos quadros.

O campo Próximo, também com a utilização de três bits, mostra a confirmação do último quadro recebido corretamente, trazendo em seu espaço o número do próximo quadro não confirmado, ou seja, é o próximo quadro esperado.

O campo P/F significa _**Poll**_/_**Final**_, ou seja, tem o bit P/F definido como P e o quadro final definido como F. Quando utiliza o “P” o computador está convidando o terminal a enviar dados, incluindo todos os quadros encaminhados pelo terminal, com exceção do quadro final. É utilizado quando um computador de grande porte está consultando um grupo de terminais.

**2.2 Quadro de Supervisão**

O Quadro de supervisão começa com os bits 1 e 2 do campo de Controle sendo 1 e 0. Nesta sequência, os bits 3 e 4 são utilizados para descrever os quatro tipos de Quadros de supervisão existentes. São eles:

- Quadro de Confirmação – _**Receiver Ready**_

- Quadro de Confirmação Negativa – _**Reject**_

- Quadro de Confirmação com Interrupção – _**Receiver Not Ready**_

- Quadro de Transmissão Seletiva – _**Selective Reject**_

**3. Descritivo da Funcionalidade dos Quadros de Supervisão.**

Como descrito no item 2.2 existem quatro tipos de Quadros de Supervisão, que são diferenciados pelos valores encontrados no campo Tipo (bits 3 e 4), conforme ilustrado na figura 2.2 B, portanto os diferentes Quadros de supervisão recebem também a denominação de Tipos de Quadros de Supervisão.

**3.1 Tipo 0**

O Quadro de supervisão Tipo 0 contém os valores nos bits 3 e 4 igual a 0 e 0, recebendo o nome de _**Receiver Ready**_ e é usado para indicar o próximo quadro esperado. O campo Próximo, portanto, deverá conter o próximo quadro não confirmado. Exemplificando: Imaginemos que foi enviado quatro quadros de informação e que todos foram recebidos corretamente, então, o quadro de supervisão trará a indicação _**Receiver Ready**_ (0 e 0 nos bits 3 e 4 do campo Tipo) e no campo Próximo deverá trazer o número em binário 0101 indicando que o próximo quadro a ser transmitido deverá ser o de número 5.

**3.2 Tipo 1**

O Quadro de supervisão Tipo 1 contém os valores nos bits 3 e 4 iguais a 0 e 1, recebendo o nome de _**Reject**_.

Este quadro é uma confirmação negativa, utilizado para indicar a detecção de um erro de transmissão. Por sua vez, o campo Próximo deverá indicar o primeiro quadro da sequência não recebido corretamente. O transmissor é solicitado a retransmitir todos os quadros pendentes a partir do valor encontrado no campo Próximo.

**3.3 Tipo 2**

O Quadro de supervisão Tipo 2 contém os valores nos bits 3 e 4 iguais a1 e 0, recebendo o nome de _**Receiver Not Ready**_.

A função deste quadro é a confirmação recebida de todos os quadros, mas solicitando que o transmissor interrompa o envio de quadros por algum tempo até o receptor enviar novamente um quadro Tipo 0.

O Quadro Tipo 2 tem como objetivo informar a existência de algum problema temporário com o receptor, tal como insuficiência de _**buffers**_ de memória ou lentidão no processamento dos quadros.Um problema temporário que logo será resolvido sem a necessidade da interrupção da transmissão.

**3.4 Tipo 3**

O Quadro de supervisão Tipo 3 contém os valores nos bits 3 e 4 iguais a 1 e 1, recebendo o nome de _**Selective Reject**_.

O objetivo do quadro do Tipo 3 é informar a retransmissão apenas do quadro especificado no campo Próximo. Esta atitude economiza tempo de máquina na retransmissão de todos os quadros, uma vez que apenas um foi danificado ou perdido na transmissão original e com isso apenas um quadro poderá ser solicitado novamente.

**Para não esquecer:**

O protocolo HDLC foi desenvolvido pela ISO a partir de modificações do original protocolo SDLC da IBM.

O protocolo HDLC é um protocolo de nível 2 do modelo de referência OSI.

É um protocolo simples, de alta eficiência, orientado a bits na sua transmissão.

O protocolo HDLC poderá a qualquer momento ter três tipos de quadros: Quadros de Informação, Quadros de Supervisão e Quadros não Numerado.

O protocolo HDLC poderá encapsular qualquer outro protocolo de nível 3 ou até mesmo outro de nível 2, como por exemplo, o _**Point to Point Protocol**_  (PPP).

Agora que você já estudou esta aula, resolva os exercícios e verifique seu conhecimento. Caso tenha alguma dúvida, participe do Fórum e discuta com seus colegas e professor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/1/253142/9883.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/3/1/253142/9883.jpg)

Figura 1 - Quadro Básico HDLC

**Protocolo** _**High Level Data Link Control**_ **(HDLC)**

**Objetivo**: Nesta aula continuaremos a estudar o protocolo HDLC_**,**_ destacando os quadros não numerados e sua utilização.

### **1. Introdução**

Quadros não Numerados são formados quando no campo de Controle, os bits um e dois tiverem o valor 1 e 1, conforme demonstrado na figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258536/9906.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258536/9906.jpg)

Figura 1 - Campo de controle do quadro não numerado HDLC

Quadros não Numerados não tem uma função especifica. Às vezes são utilizados para fins de controle e outras para funções de transporte de dados, nesse caso, quando o serviço utilizado não é confiável ou não é orientada a conexão.

No campo de controle dos Quadros não Numerados existem cinco bits para indicar o tipo de quadro, sendo que nem todas as trinta e duas possibilidades são utilizadas (bits 3, 4, 6, 7 e 8 do quadro de controle). Conforme apresentado no quadro 1.

Quadro 1. Representação dos principais Quadros não Numerados:

|Comando(C)Resposta (R)|Bits3, 4, 6, 7 e 8|Descrição|
|---|---|---|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SNRM (C)]]|00-001|_**Set Normal Response Mode**_ - É enviado pelo nó primário ao secundário, indicando que deve entrar em modo de ligação normal, com campo de controle de 8 bits.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SNRME (C)]]|11-011|_**Set Normal Response Mode Extended**_ - Idêntico ao anterior, mas com campo de controle de 16 bits.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SARM (C)]]|11-000|Set Asyncronous Response Mode - Idêntico ao SNRM, para o modo assíncrono.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SARME (C)]]|11-010|_**Set Asyncronous Response Mode**_ _**Extended**_ - Idêntico ao SNRME, para o modo assíncrono.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SABM (C)]]|11-100|_**Set Asyncronous Balanced Mode**_ - Idêntico ao SNRM, para o modo assíncrono balanceado.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SABME (C)]]|11-110|_**Set Asyncronous Balanced Mode Extended**_ - Idêntico ao SNRME, para o modo assíncrono balanceado.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SIM (C)]]|10-000|_**Set Initialization Mode**_ - É enviado pelo nó primário ao secundário para que este inicie um procedimento de inicialização.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/DISC (C)]]|00-010|_**Disconnect**_ - Informa o destinatário que a estação emissora deixará de estar ativa.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/UA (R)]]|00-110|_**Unnumbered Acknowledgment**_ - Indica a aceitação do comando enviado.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/DM (R)]]|11-000|_**Disconnected Mode**_ - Resposta enviada sempre que outro nó envia um comando a indicar que o nó não está em ligação. Esta resposta é igualmente usada para indicar a não aceitação de um comando.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/RD (R)]]|00-010|_**Request Disconnect**_ - Esta resposta é usada para pedir a quebra da ligação estabelecida.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/RIM (R)]]|10-000|_**Request Initialization Mode**_ - Esta resposta é usada quando o nó não está pronto e vai ser reinicializado.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/UI (C-R)]]|00-000|_**Unnumbered Information**_ - Usados para troca de informação entre nós (status, etc).|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/UP (C)]]|00-100|_**Unnumbered Poll**_ - Usado para pedir informações a nós, a resposta será um UI.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/RSET (C)]]|11-001|_**Reset**_ - Este comando é usado para a recuperação de erros graves (FRMR), indica que o nó reinicializou o seu número de sequência de envio, o destinatário deve também reinicializar o seu número de sequência de resposta.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/XID (C-R)]]|11-101|_**Exchange Identification**_ - Usado para a troca de informação sobre endereços e características entre dois nós.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/TEST (C-R)]]|10-111|_**Test**_ - Permite efetuar um teste da ligação com outro nó, que deve responder o mais brevemente possível.|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/FRMR (R)]]|10-001|_**Frame Reject**_ - Indica que a trama recebida tem um erro que não pode ser recuperado por ARQ.|

  
  

Como exemplo de comandos podemos citar o SNRM, SARM e SABM que são utilizados para estabelecer a ligação lógica. O computador que as recebe responde com UA ou DM conforme aceitar ou não a ligação.

O comando DISC é usado para quebrar a ligação lógica. O computador que a recebe responderá com UA.

Outro comando bem interessante é o SNRM e o SNRME, onde a letra “E” significa estendido, ou seja, o campo de Controle poderá ser de 8 bits com a primeira opção ou de 16 bits na segunda opção. Com esta alternativa se aumenta a possibilidade da janela de envio de quadros sem confirmação, passando de 7 para até 127 quadros, aumentando a eficiência da transmissão em linhas de alta velocidade com baixa perda de dados.

### 2. Controle de Fluxo

O controle de fluxo é uma função fundamental, pois assegura a ligação lógica. É um mecanismo que evita que um computador receba mais dados do que pode absorver e processar. Um computador ou receptor utiliza um banco de memória denominado _**buffer**_ finito para armazenar temporariamente os dados até que os níveis superiores os processem entrando assim numa fila de espera. Como o _**buffer**_ é finito, ou seja, de pequena capacidade de armazenamento, existe sempre a possibilidade de sua capacidade ficar saturada e a consequente perda de dados.

Para evitar esta situação o receptor informa ao emissor o estado do seu banco de memória. O mecanismo mais simples para este controle é informar ao transmissor sua situação atual, conhecido por _**stop & wait,**_ que funciona da seguinte maneira:

- O emissor envia um pacote de cada vez e aguarda por um _**acknowledgment**_ (ACK) do receptor como um sinal de permissão de nova transmissão, portanto o receptor só retransmitirá outro pacote com o recebimento de um ACK.

- O receptor só enviará um ACK ao transmissor se possuir espaço suficiente em seu _**buffer**_ e após o processamento do pacote anterior.

Este procedimento apesar de funcional é demasiadamente lento, pois os dados terão de ser transmitidos um a um e a cada pacote transmitido é necessária uma confirmação de recebimento.

As redes locais não são muito afetadas neste aspecto pelo atraso de transmissão, devido ao alto valor com que estas redes processam os pacotes, ou seja, na ordem de 100 Mbits ou 1000 Mbits por segundo, fornecendo normalmente uma eficiência entre 83% e 98%.

Porém, para as ligações de longa distância, este fenômeno torna-se mais pesado, devido à baixa velocidade, chegando a casos extremos nas ligações por satélite, onde a eficiência se situa muitas vezes abaixo de 10%.

A solução para este problema consiste no envio do ACK de pacotes em conjunto. O emissor começa a enviar um número de pacotes “_**w**_” que designaremos de "tamanho da janela". O _**w**_ é o número de pacotes que podem ser enviados sem que o receptor envie sequer um ACK.

O _**w**_ é conhecido tanto pelo emissor quanto pelo receptor, mesmo porque este último precisa reservar inicialmente um _**buffer**_ com capacidade para _**w**_ pacotes, com o _**stop & wait**_ necessitava apenas de reservar espaço para um pacote.

Para garantir o funcionamento do mecanismo, tanto os pacotes como os ACKs são numerados de 0 a _**w**_. Esta numeração evita que o receptor tenha de enviar ACKs individuais para todos os pacotes.

Compreende-se facilmente o funcionamento sabendo que a regra base é de que o número de pacotes que podem ser enviados sem ACK do receptor é “_**w**_”, sendo este um número combinado entre as partes antes do início da transmissão dos dados.

Por exemplo: Se o receptor envia ACK igual a 8 quer dizer que já retirou do _**buffer**_ todos os pacotes até o pacote 8. Nesta situação o emissor entende que pode manter sem ACK os “_**w**_” pacotes depois do pacote 8.

Este mecanismo foi designado como “janela deslizante”, porque dependendo do valor que o receptor receba do ACK ele poderá aumentar ou diminuir sua taxa de transmissão, aumentando ou diminuindo a quantidade de “_**w**_” que em realidade é a quantidade de pacotes enviados de uma única vez. Esta quantidade de pacotes também pode ser considerada como tamanho da rajada de dados.

### 3. Controle de Erro

Os erros podem ser detectados recorrendo a diversas técnicas, tais como o CRC ou o FCS, porém, uma vez que o erro é detectado, é necessário tomar providências para correção. A solução mais comum consiste na retransmissão do pacote danificado. Este mecanismo é conhecido por _**Automatic Repeat Request**_ (ARQ)_**.**_

A implementação mais simples é o _**stop & wait - ARQ**_ que em tudo se assemelha ao esquema adotado para o controlo de fluxo. A grande diferença é que a informação enviada ao emissor pode ser ACK ou _**Negative Acknowledgment**_ (NAK):

- ACK indica ao emissor que o pacote foi recebido sem erros e pode enviar o seguinte.

- NAK indica ao emissor que o pacote foi recebido com erros e deve ser enviado novamente.

Este esquema simples é insuficiente, uma vez que o pacote pode nem sequer chegar ao destino. A solução é usar um temporizador no emissor, se após algum tempo do envio não é recebido nenhum ACK ou NAK, o emissor volta a enviar o pacote remontando o esquema anterior continuamente.

### Para refletir:

Quadros não Numerados são utilizados às vezes para fins de controle e outras para funções de transporte de dados, nesse caso quando o serviço utilizado não é confiável e está sem conexão.

Existem trinta e duas opções de Quadros não Numerados, porém os mais importantes e usuais são os que estabelecem e finalizam a conexão e os que determinam o tamanho do campo de Controle, mudando assim a eficiência do link por permitir, no caso do campo estendido, janelas deslizantes de até 127 quadros enviados sem a necessidade de um ACK.

Esta eficiência só é possível em links de alto desempenho, com baixo índice de erros de bits.