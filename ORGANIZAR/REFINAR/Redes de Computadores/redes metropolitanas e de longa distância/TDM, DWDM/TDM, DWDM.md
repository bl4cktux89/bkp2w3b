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
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SNRM (C)\|SNRM (C)]]|00-001|_**Set Normal Response Mode**_ - É enviado pelo nó primário ao secundário, indicando que deve entrar em modo de ligação normal, com campo de controle de 8 bits.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SNRME (C)\|SNRME (C)]]|11-011|_**Set Normal Response Mode Extended**_ - Idêntico ao anterior, mas com campo de controle de 16 bits.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SARM (C)\|SARM (C)]]|11-000|Set Asyncronous Response Mode - Idêntico ao SNRM, para o modo assíncrono.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SARME (C)\|SARME (C)]]|11-010|_**Set Asyncronous Response Mode**_ _**Extended**_ - Idêntico ao SNRME, para o modo assíncrono.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SABM (C)\|SABM (C)]]|11-100|_**Set Asyncronous Balanced Mode**_ - Idêntico ao SNRM, para o modo assíncrono balanceado.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SABME (C)\|SABME (C)]]|11-110|_**Set Asyncronous Balanced Mode Extended**_ - Idêntico ao SNRME, para o modo assíncrono balanceado.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/SIM (C)\|SIM (C)]]|10-000|_**Set Initialization Mode**_ - É enviado pelo nó primário ao secundário para que este inicie um procedimento de inicialização.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/DISC (C)\|DISC (C)]]|00-010|_**Disconnect**_ - Informa o destinatário que a estação emissora deixará de estar ativa.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/UA (R)\|UA (R)]]|00-110|_**Unnumbered Acknowledgment**_ - Indica a aceitação do comando enviado.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/DM (R)\|DM (R)]]|11-000|_**Disconnected Mode**_ - Resposta enviada sempre que outro nó envia um comando a indicar que o nó não está em ligação. Esta resposta é igualmente usada para indicar a não aceitação de um comando.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/RD (R)\|RD (R)]]|00-010|_**Request Disconnect**_ - Esta resposta é usada para pedir a quebra da ligação estabelecida.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/RIM (R)\|RIM (R)]]|10-000|_**Request Initialization Mode**_ - Esta resposta é usada quando o nó não está pronto e vai ser reinicializado.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/UI (C-R)\|UI (C-R)]]|00-000|_**Unnumbered Information**_ - Usados para troca de informação entre nós (status, etc).|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/UP (C)\|UP (C)]]|00-100|_**Unnumbered Poll**_ - Usado para pedir informações a nós, a resposta será um UI.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/RSET (C)\|RSET (C)]]|11-001|_**Reset**_ - Este comando é usado para a recuperação de erros graves (FRMR), indica que o nó reinicializou o seu número de sequência de envio, o destinatário deve também reinicializar o seu número de sequência de resposta.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/XID (C-R)\|XID (C-R)]]|11-101|_**Exchange Identification**_ - Usado para a troca de informação sobre endereços e características entre dois nós.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/TEST (C-R)\|TEST (C-R)]]|10-111|_**Test**_ - Permite efetuar um teste da ligação com outro nó, que deve responder o mais brevemente possível.|
|[[ORGANIZAR/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/TDM, DWDM/Untitled Database/FRMR (R)\|FRMR (R)]]|10-001|_**Frame Reject**_ - Indica que a trama recebida tem um erro que não pode ser recuperado por ARQ.|

  
  

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

![[Untitled 64.png|Untitled 64.png]]

**Frequências e Comprimentos de Onda das Sub bandas.**

**Fonte:** **(SANTOS, 2008)**

Como considerações finais, podemos considerar que a tecnologia DWDM permite transmitir volumes de dados até então inimagináveis, tudo isto em uma única fibra óptica, o que é muito importante para um mercado que cada vez mais exige maiores largura de banda em suas aplicações. Com tantas vantagens técnicas, econômicas e logísticas, a tecnologia DWDM está preparando o mercado para as redes fotônicas.

**5. Para refletir.**

As técnicas de TDM são largamente utilizadas nas redes ópticas, pois com esta técnica, consegue-se transmitir maior quantidade de informação com uma quantidade menor de meios.

Para otimizar mais ainda está transmissão com economia, as técnicas de multiplexação WDM e DWDM conseguem agora a transmissão de vários canais com diferentes comprimentos de luz. Todos estes canais trafegam na mesma fibra óptica sem atrapalhar ou prejudicar qualquer um deles e podendo transmitir uma grande quantidade de canais com um mínimo de espaçamento entre as lambdas e com também, uma gigantesca quantidade de dados num mínimo de fibras ópticas.