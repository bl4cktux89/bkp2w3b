### Introdução

Existe uma vasta literatura que define o que é uma QoS ( Qualidade de Serviço ). De acordo com Pinheiro (2004), podemos dizer que uma QoS é um requisito das aplicações para a qual se exige que determinados parâmetros estejam dentro de limites bem definidos, considerando aí um valor mínimo e um valor máximo. Normalmente, uma QoS é garantida pela rede, seus componentes e equipamentos. Em linhas gerais sobre um aspecto mais administrativo, podemos dizer que "qualidade" é entendida como bem-estar, adequação ao uso e satisfação. Um produto ou serviço de qualidade é aquele que atende perfeitamente, de forma confiável, de forma acessível, de forma segura e no tempo certo às necessidades do cliente. Por exemplo, podemos analisar um determinado projeto, produto ou serviço quando entregue da seguinte maneira:

a) ... que atende perfeitamente ... --> Projeto perfeito

b) ... de forma confiável ... --> Sem defeitos

c) ... de forma acessível ... --> Baixo custo

d) ... de forma segura ... --> Segurança do cliente

e) ... no tempo certo ... --> Entrega no prazo certo, no local certo e na quantidade certa

**Definição de Qualidade de Serviços em Redes de Computadores.**

### Atrasos

De acordo com Pinheiro (2004) Trata-se de um parâmetro importante na utilização de QoS. Em geral, um atraso em rede pode ser definido como a somatória de todos os atrasos impostos pela rede e equipamentos utilizados na comunicação. Em vista da aplicação, o atraso resulta em um tempo de resposta (tempo de entrega da informação, pacotes etc.) para a aplicação. Alguns dos principais fatores que geram um atraso na rede: atraso de propagação (Propagation Delay), velocidade de transmissão e tempo de processamento nos equipamentos. Vale ainda salientar, que possivelmente você irá escutar dois termos que são referenciados em QoS: latência e atraso. Ambos têm o mesmo significado, mas convencionalmente "latência" é utilizado para atrasos em equipamentos e "atraso" está associado com transmissões de dados.

### Jitter (flutuação)

De acordo com Pinheiro (2004), Jitter é definido como uma variação de atraso de entrega de pacotes. Para aplicações como a transmissão de áudio e vídeo, não importa muito se os pacotes demoram 20 ms ou 30 ms para serem entregues, desde que o tempo em trânsito seja constante. A variação (isto é, o desvio-padrão) nos tempos de chegada de pacotes é chamada Jitter. Por exemplo, uma flutuação elevada, na qual alguns pacotes demoram 20 ms e outros demoram 30 ms para chegar, resultará em uma qualidade irregular do som ou do filme. Em contraste, um acordo em que 99% dos pacotes fossem entregues com um retardo no intervalo de 24,5 ms a 25,5 ms poderia ser aceitável. O valor escolhido deve levar em conta o tempo de trânsito na velocidade da luz e o retardo mínimo na passagem pelos roteadores, e talvez deixar uma pequena folga para alguns retardos inevitáveis. Por exemplo, a faixa de frequência (Dial) de um rádio FM, em que encontramos diversas informações diferentes pelas estações, que estão localizadas em frequências diferentes (portadoras: 88,1, 89,1, 90,5, 96,1, 100,9, 101,7 MHz etc.), todas as estações chegam juntas ou estão disponíveis na antena do aparelho, mas o ouvinte escolhe apenas um canal que deseja ouvir. No sistema de voz, para tornar realidade essa interconectividade, foi necessário o uso extensivo da multiplexação desses canais de voz. No primeiro nível de multiplexação FDM, 12 canais de voz são multiplexados, formando o chamado canal de grupo. Cinco canais de Grupo, por sua vez, são multiplexados em um canal de supergrupo, que contém 60 canais de voz. No terceiro nível, cinco canais de supergrupo são multiplexados em um canal de grupo mestre, que carrega 300 canais de voz, e, em seguida, o supergrupo mestre, com 900 canais (ITU-T).

![[Untitled 19.png|Untitled 19.png]]

### Perdas de pacotes

De acordo com a definição dada por (ODOM, 2012), a perda de pacotes pode ser definida como um pacote, que se adentrou à rede e não foi entregue até seu fim, ou seja, se perdeu no trânsito dessa rede. Roteadores e switches podem ser as razões por esses bloqueios. Entretanto, ferramentas de QoS podem influenciar no comportamento dessa perda quando pacotes estiverem para ser perdidos em filas muito extensas. Quando a fila estiver cheia e outro pacote precisar ser endereçado, o descarte ocorrerá automaticamente pelos equipamentos da rede. Em geral, roteadores perdem, bloqueiam ou descartam pacotes por várias razões, em que a maioria das ferramentas QoS ficam sem opção de ação a respeito. Entretanto, outras ferramentas de QoS podem ser utilizadas para minimizar o impacto desses pacotes perdidos.

Duas características sobre perdas de pacotes que valem a pena ressaltar:

- As perdas ocorrem por fatores como erros e congestionamentos.
- As perdas ocorrem por causa de erros ocorridos durante a transmissão.

Por isso, o que deve ser feito para minimizar essas perdas, do ponto de vista da QoS, é especificar e garantir limites razoáveis (taxas de perdas) que permitam uma operação adequada da aplicação.

### Técnicas de Enfileiramente - Filas

As filas têm um papel importantíssimo quando se trata de uma qualidade de serviços em redes de computadores. O comprimento das filas (também conhecido como Buffer) atua diretamente na boa qualidade do serviço. Podemos conceituar uma fila com um exemplo: quando um roteador possui, em sua entrada, mais dados (ou pacotes) do que ele é capaz de liberar, automaticamente precisa criar um processo para a liberação desses pacotes. Esse processo de liberação é o que pode ser definido como "fila". Fazendo uma analogia, uma fila que ocorre numa rede é como uma fila que ocorre em um caixa de supermercado, por exemplo. A vazão, ou seja, a quantidade de pessoas que precisa passar pelo caixa encontra a barreira de ter apenas um atendente, que irá proporcionar o atendimento de apenas uma pessoa por vez. Logo, se o tempo de passagem dessa pessoa pela fila foi inferior ao tempo que outras pessoas chegaram para passar nesse mesmo caixa, automaticamente se formará uma fila. É assim também que ocorre com os equipamentos (roteadores) que precisam liberar o trafégo dos pacotes de dados na rede.De acordo com Tanenbaum (2006), podem ser classicadas como  "fila do tipo tail (FIFO)",  "fila do tipo red", "fila do tipo WFQ".

É por isso que atualmente existem diversas ferramentas de QoS que tratam especificamente desse processo de gerenciamento de filas, sendo eles:

FIFO (First-In, First-Out) ou “Primeiro a Entrar, Primeiro a Sair”.

RED ( Random Early Detection ) Distribuição randomica

WFQ (Weighted Fair Queueing) - O Algoritimo escalona o tráfego, priorizando o de maior (Importancia) peso na sequencia .

Traduzindo de um dicionário puro, o termo "transmissão" pode ser entendido como: Ação ou efeito de transmitir: transmissão de um direito. Comunicação do movimento de um órgão mecânico a outro por meio de engrenagens, polias, correias etc.; instrumento próprio para transmitir movimento. Corpo ou serviço encarregado da construção e manutenção dos meios de comunicação entre as forças armadas (telefone, rádio etc.).

(Dicionário online de Português, 2017)

Já para o termo "propagação", diretamente pode ser definido como:

Ação ou efeito de propagar, de multiplicar por meio de reprodução: a propagação do gênero humano. Fig. Extensão, difusão, desenvolvimento: a propagação das idéias. Física. Modo de transmissão das ondas sonoras ou luminosas.

( Dicionário online de Português, 2017)

Desse modo, em redes de computadores,  de acordo com Tanenbaum (2006), podemos entender transmissão como a transmissão de sinais, sob a forma de ondas eletromagnéticas, sendo suportada em meios de transmissão, que podem ser:

- Guiados (par de cobre entrançado, cabo coaxial, fibra óptica)
- Não guiados (ar, vácuo)

Assim, transmissão é o meio físico e a propagação é como será o comportamento desses dados no meio físico disponibilizado, sempre tendo em mente que essa propagação está diretamente ligada ao tempo que vai levar para que um determinado dado (ou pacote) percorra um caminho específico até chegar ao seu destino.

Em um exemplo simples, de acordo com Tanenbaum (2006), numa transmissão por rádio a velocidade de propagação é próxima da velocidade da luz (300.000 Km/s). Usando cabos, as velocidades de propagação são inferiores. A fibra óptica monomodo permite atingir 70% da velocidade da luz, ou seja, cerca de 210.000 Km/s. A velocidade de propagação nos cabos de cobre situa-se entre 40% e 60% da velocidade da luz, ou seja, 120.000 Km/s a 180.000 Km/s. Portanto, caro aluno, pare e pense um pouco: já imaginou o tamanho da influência que existe num meio de transmissão, quando esse apresenta alguma irregularidade, como um cabo mal conectado, um conector mal feito ou algo assim. Por isso, na construção física de uma rede de transmissão de dados, isso é de grande importância, e certificações que atualmente existem no mercado (como certificação de cabeamento estruturado) são de suma importância para a boa qualidade do meio de transmissão.

Qualidade de serviço (QoS), também conhecido como CoS em ambientes Cisco (_**Class of Services**_) desempenha um papel crucial nas redes modernas, com o objetivo de classificação da banda através de sua priorização, garantindo assim que aplicações sensíveis a atraso, como atividades em tempo real, estejam protegidos.

(Hansen (2013))

Já em ambientes IPv6, o QoS atua de maneira diferenciada para que as aplicações façam suas solicitações evitando uma demora desnecessária no link de WAN. O termo frequentemente utilizado para descrever este fenômeno é baixa latência. Streaming de áudio e vídeo são ótimos exemplos de aplicações que requerem baixa latência através de alta prioridade. A fim de evitar uma quebra do sistema, um aplicativo pode compartilhar várias conexões a partir da utilização de níveis de prioridade.

(Hansen (2013))

A redes em IPV6 apresentam,de acordo com Hansen (2013) maior sofisticação , uma vez que a  sua distribuição pode ser feita em até sete níveis, da seguinte forma:

- Nível 0 - Sem prioridade de especificar;
- Nível 1 - O tráfego secundário (notícias);
- Nível 2 - de transferência de dados automática (email);
- Nível 3 - Reservado;
- Nível 4 - Com a presença de transferência em massa (FTP);
- Nível 5 - Reservado;
- Nível 6 - O tráfego Interativo (Telnet, janela);
- Nível 7 - Controle de tráfego (roteamento, gerenciamento de rede).

O IPv6 utiliza uma abordagem mais sofisticada para lidar com dados de aplicações solicitando tratamento prioritário. O dispositivo de origem fará uma consulta o destino, a fim de determinar o tamanho máximo da carga que exige ser tratada através de todo o caminho determinado pela conexão, ou seja, é feita uma análise ponto a ponto, para garantir que não haja pontos de congestionamento, o que pode aumentar o tempo de resposta de um sistema ou eventualmente causar a perda de um pacote. Uma vez feita esta checagem, o IPv6 ajusta os seus próprios parâmetros de modo a não gerar pacotes com um volume de dados superior a menor célula por onde este pacote trafegará (com o cuidado de não sub utilizar os recursos).

(Hansen (2013))

### Tempos de atraso

Segundo Pinheiro (2004) ao considerarmos um segmento UDP, que é encapsulado em um datagrama IP. Enquanto o datagrama viaja pela rede, ele passa por buffers nos roteadores, para poder alcançar o enlace de saída. É possível que um ou mais buffers na rota entre o remetente e o destinatário estejam lotados e não possam aceitar o datagrama IP.

Nesse caso, o datagrama IP será descartado e nunca chegará à aplicação receptora. Isso pode ser melhorado simplesmente enviando pacotes por TCP, pelo simples fato de ele tentar retransmitir pacotes que por ventura não chegaram ao seu destino. Entretanto, mecanismos de e transmissão frequentemente são inaceitáveis para aplicações interativas de áudio em tempo real, por exemplo, voz sobre IP, porque aumentam o atraso fim a fim. Além disso, por causa do controle de congestionamento do TCP, após a perda de pacote, a taxa de transmissão no remetente pode ser reduzida a uma taxa mais baixa do que a taxa de reprodução no receptor, o que pode causar um forte impacto sobre a voz no receptor. Por isso essas aplicações massivas em tempo real trabalham com o UDP, não se preocupando com a retransmissão de um pacote perdido. Pacotes com taxas de perdas entre 1 e 20 por cento são toleradas por essas aplicações.

Ainda em Pinheiro (2004) os tempos de atraso podem ser resumidos da seguinte forma:

- Atraso fim a fim: que é o acúmulo de atrasos de processamento, de transmissão e de formação de filas nos roteadores e atrasos de processamento em sistemas finais. Por exemplo: para aplicações de áudio altamente interativas (VOIP), atrasos fim a fim menores do que 150 milissegundos não são percebidos pelo ouvido humano; atrasos entre 150 e 400 milissegundos podem ser aceitáveis, mas não são o ideal, e atrasos maiores que 400 milissegundos podem atrapalhar seriamente a interatividade em conversações por voz. Normalmente, o lado receptor da aplicação acaba desconsiderando o pacote que possua um tempo maior de 400 milissegundos de resposta, ou seja, esse pacote é descartado.
- Variação de atraso: um componente crucial são os atrasos aleatórios de fila nos roteadores. Por causa desses atrasos variáveis dentro da rede, o tempo decorrido entre o momento em que um pacote é gerado na fonte e o momento em que é recebido no destinatário pode variar de pacote para pacote.

### O que é PPS

Segundo Tanenbaum (2006) em redes de comunicação, PPS significa Pacotes por Segundo (do inglês: Packets per Second), que é a taxa média de entrega de mensagem de sucesso ao longo de um canal de comunicação. Esses dados podem ser entregues por meio de uma ligação física ou lógica, ou passar por intermédio de um nó de rede. A taxa de transferência é normalmente medida em bits por segundo (bit / s ou bps), e, às vezes, em pacotes de dados por segundo ou pacotes de dados por intervalo de tempo. Essa medida também é conhecida como "throughput". O rendimento do sistema ou throughput total é a soma das taxas de dados que são entregues a todos os terminais de uma rede.

### Resumindo ...

Foram apresentados os principais conceitos e principais parâmetros de medidas de qualidade de serviços em ambientes de redes, destacando que esses são parâmetros que devem controlados para promover um bom tráfego de transmissão de redes.