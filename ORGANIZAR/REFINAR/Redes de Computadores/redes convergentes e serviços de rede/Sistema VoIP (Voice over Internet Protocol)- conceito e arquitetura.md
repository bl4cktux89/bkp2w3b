**Introdução**

Um sistema público de telefonia comutada tradicional funciona usando tráfego de voz com um pouco de tráfego de dados aqui e ali. Porém, o tráfego de dados cresceu e cresceu e, por volta de 1999, o número de bits de dados transferidos igualou o número de bits de voz (pois a voz está codificada em PCM nos troncos, e assim pode ser medida em bps). Em 2002, o volume do tráfego de dados era dez vezes maior que o volume do tráfego de voz, e ainda continua a crescer exponencialmente, enquanto o tráfego de voz permanece quase no mesmo nível (crescendo 5% ao ano).

Como consequência desses números, muitas operadoras de redes de comutação de pacotes de repente ficaram interessadas em transportar voz sobre suas redes de dados. O volume de largura de banda adicional exigida para voz é minúsculo, pois as redes de pacotes são dimensionadas para o tráfego de dados. No entanto, a conta telefônica de um consumidor médio provavelmente é maior que sua conta da internet, e assim as operadoras de redes de dados viram na telefonia da internet um modo de ganhar um bom dinheiro extra sem terem de instalar sequer um novo cabo de fibra. Desse modo, nasceu a telefonia da internet (também conhecida como voz sobre IP (VOIP)).

Devemos levar em consideração, inclusive, toda a tendência atual para as redes convergentes, que estimulam ainda mais o uso desse sistema de tráfego de voz, utilizando os mesmos protocolos de dados na internet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/9/292916/17052.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/9/292916/17052.jpg)

Convergência de Redes

**Como funciona uma transmissão VOIP**

Para que a tecnologia VOIP funcione adequadamente alguns procedimentos básicos para o sistema VOIP, são listados abaixo:

- O usuário, com um headset , ouve a sinalização que indica telefone fora do gancho para a parte da aplicação sinalizadora da VoIP no roteador. Esta emite um sinal de discagem e aguarda que o usuário tecle um número de telefone. Esses dígitos são acumulados e armazenados pela aplicação da sessão.
- O gateway compara esses dígitos acumulados com os números programados. Quando há uma coincidência, ele mapeia o número discado com o endereço IP do gateway de destino.
- Em seguida, a aplicação de sessão roda o protocolo de sessão H.245 sobre TCP, a fim de estabelecer um canal de transmissão e recepção para cada direção através da rede IP. Quando a ligação é atendida, é estabelecido, então, um fluxo RTP (Real-Time Transport Protocol, ou Protocolo de Transmissão em Tempo Real) Sobre UDP (User Datagram Protocol, algo como Protocolo de Pacote de Dados do Usuário) entre o gateway de origem e o de destino.
- Os esquemas de compressão do codificador-decodificador (CODECs) são habilitados nas extremidades da conexão. A chamada, já em voz, prossegue utilizando o RTP/UDP/IP como pilha de protocolos.

Nada impede que outras transmissões de dados ocorram simultaneamente à chamada.

Sinais de andamento de chamada e outros indicativos que podem ser transportados dentro da banda cruzam o caminho da voz assim que um fluxo RTP for estabelecido.

Após a ligação ser completada, é possível também enviar sinalizações dentro da banda, como por exemplo, sinais DTMF (frequências de tons) para ativação de equipamentos como Unidade de Resposta Audível (URA).

Quando qualquer das extremidades da chamada desligar, a sessão é encerrada, como em qualquer chamada de voz (ligação telefônica) convencional.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/1/2/11299/i08_546.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/1/2/11299/i08_546.jpg)

Elementos de uma arquitetura VOIP

### Dispositivo Softfone

Trata-se de um aplicativo multimídia oferecido por operadoras, permitindo fazer chamadas do seu PC através da tecnologia VOIP, ou seja, transmissão de voz por canal de dados.

Ao instalar esse aplicativo, permite-se que seu computador transforme-se em um telefone multimídia, com capacidade de voz, dados e imagem. É possível fazer chamadas para telefones locais convencionais (normalmente as operadoras cobram uma pequena taxa) e também chamadas diretas para outro PC, gratuitamente.

Para que esse processo se concretize, é necessário possuir um PC conectado a internet, um microfone, alto-falantes e um softphone oferecido por uma operadora, normalmente de forma gratuita.

Em consequência das características particulares de cada aplicativo softphone dentro das operadoras, isso acarreta na limitação da conexão VOIP gratuita apenas para equipamentos e conexões ligadas a mesma operadora.

### Telefones USB X VOIP ATA

Até aqui estamos tratando de sistemas VOIP, falando em serviços e aplicativos. Mas como podemos imaginar os aparelhos de conexão? Simples, os aparelhos mais modernos atualmente se assemelham aos aparelhos telefônicos convencionais. Por isso, meu caro aluno, é interessante apresentar a você alguns formatos de telefone, caso desperte o interesse em você em construir uma disponibilidade dessas.

Basicamente, existem os telefones USB e os adaptadores ATA. O telefone USB é um aparelho similar ao telefone convencional, que possui uma porta USB que deve ser conectada ao computador. Microfones e fones de ouvidos são imediatamente descartados com esse aparelho. Os telefones USB oferecem uma melhor qualidade de áudio. O telefone USB não possui uma independência de tecnologia VOIP, ou seja, você vai precisar de um computador com software para realizar as ligações.

Já com o VOIP ATA, isso é possível. Ele serve como um adaptador de telefone analógico à telefonia digital de VOIP/IP.

**PARA CONHECER SOBRE ATA - ADAPTADORES DE TELEFONIA ANALÓGICA PARA DIGITAL, VISITE OS SITES:**

http://www.planet.com.tw/en/product/product_list.php?id=373

http://www.intelbras.com.br/empresarial/telefonia/acessorios/para-centrais-pabx/ata-gkm-2210-t

Por meio desse adaptador, seu telefone convencional é conectado ao modem de internet, permitindo assim, a comunicação através de uma rede digital, sem a intermediação de um computador.

### Interfaces FXS e FXO

FXS e FXO são as portas utilizadas nas linhas telefônicas analógicas. FXS significa ‘Foreign eXchange Subscriber’. É a interface que chega ao assinante. É o famoso “plug na parede”, do lado do cliente.

FXO significa “Foreign eXchange Office”, que representa a interface que recebe a linha analógica. É o plug no telefone ou no aparelho de fax.

FXO e FXS sempre estão aos pares disponíveis, caso contrário, não há como realizar uma conexão de telefone convencional. As imagens a seguir representam, respectivamente, uma conexão de telefonia convencional sem usar um PABX e utilizando um PABX.

**PARA CONHECER SOBRE AS INTERFACES FXS E FXO, VISITE OS SITES:**

http://sbkb.cisco.com/CiscoSB/GetArticle.aspx?docid=925d9a06d20a448d9e6bca139a4e33e3_Product_Overview_of_UC540_Series.xml&pid=2&converted=0

http://www.3cx.com/pbx/fxs-fxo/