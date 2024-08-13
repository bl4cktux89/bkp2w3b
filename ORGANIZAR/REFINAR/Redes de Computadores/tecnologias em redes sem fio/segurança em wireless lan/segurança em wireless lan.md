### Objetivo:

Neste tópico iremos estudar os frames de controle das redes wireless Lan, bem como sua segurança e os mecanismos que protegem as informações transmitidas.

### Introdução

Para que uma estação possa se comunicar com outras estações em uma rede wireless é necessário a princípio ser autenticada e depois associada a esta rede. Este processo de autenticação, consiste na utilização do mesmo SSID configurado previamente no _**Access Point**_, portanto, todos os equipamentos que estão conectados na mesma rede precisam ter a mesma identificação, ou o mesmo SSID.

O BSSID – _**Basic Service Set Identifier**_ - é um endereço de 48 bits que identifica cada _**Access Point**_ numa configuração BSS. O valor desse campo no modo infraestrutura é o endereço MAC do próprio AP. No modo ad-hoc – IBSS o valor do BSSID é o endereço local formado por 46 bits gerados aleatoriamente com o objetivo de prover alta possibilidade de selecionar um único BSSID.

### _Frames_ _Beacon_

São pequenos _**frames**_ enviados do _**Access Point**_ para as estações quando na topologia infraestrutura – BSS, ou de estações para estações quando na configuração IBSS – ad-hoc, de maneira a organizar e sincronizar a comunicação em uma rede sem fio. O frame _**Beacon**_ tem as seguintes funções:

1. Configuração dos parâmetros de modulação FHSS e DSSS: O _frame Beacon_ envia informações especificas para a tecnologia de modulação que está sendo utilizada. Na tecnologia DSSS, o _beacon_ contém informações sobre o canal a ser utilizado pelos sistemas e no modelo FHSS, o _beacon_ carrega informações sobre o canal e os parâmetros de salto bem como a sequência destes.
2. Informações de SSID: A estação procura no frame _beacon_ o SSID da rede à qual se deseja conectar, quando esta informação é encontrada, a estação envia um pedido de autenticação ao _Access Point_ que o transmitiu e, aguarda pela associação.
3. Sincronização: Quando o cliente recebe um _beacon_, ele ajusta seu _clock_ interno ao _clock_ do _Access Point_, assegurando que as funções sensíveis ao tempo não sejam comprometidas.
4. _Traffic Indication_ MAP – TIM: O TIM é usado para indicar qual estação está no modo adormecido, com a intenção de economia de baterias e tem pacotes enfileirados no _Access Point_. Esta informação é passada em cada _beacon_ para todas as estações da rede que estejam associadas.
5. Suporte a taxas de transmissão: É no _frame beacon_ que estão as informações sobre a taxa de transmissão suportada pelo _Access Point_ e a indicação de diminuição ou de aumento desta velocidade.

A interação dos _**frames beacon**_ enviados pelos _**Access Points**_ às estações da rede wireless são feitas pelo processo de escaneamento. Há duas modalidades neste processo: Escaneamento Passivo e Ativo. (SANTOS JUNIOR, 2005)

### Escaneamento Passivo

O escaneamento passivo acontece quando a estação detecta o meio na intenção de verificar se está no raio de alcance de um Access Point. Neste sentido também, a estação consegue checar se está apta a se autenticar em alguma rede que ela sintonize, pois é no _**frame**_ _**beacon**_ que são carregadas informações da rede como exemplo, o próprio SSID.

A estação então compara o SSID sintonizado no meio com os que têm registrado em sua memória de configuração e caso encontre tal informação, a estação se autenticará automaticamente na referida rede. Portanto, o processo de escaneamento passivo ocorre quando a estação encontra a rede e em redes com múltiplos _**Access Points**_, o _**beacon**_ é enviado por mais de um equipamento. A estação irá se conectar ao AP que tiver a maior intensidade de sinal chegando a sua antena e a menor taxa de erro de transmissão. (RAPPAPORT, 2009)

A estação continuará a detectar os _**beacons**_ mesmo depois de estar autenticada e associada a uma rede. Este processo agiliza a reconexão à rede em caso de perda do sinal ou se a estação for desconectada ou desassociada do _**Access Point**_ ao qual estiver conectada. Com este procedimento é mantido uma lista das características dos APs de toda a rede, como canal, intensidade do sinal, SSID e demais informações que permitirão à estação localizar rapidamente o melhor equipamento para se associar novamente. A figura 1 ilustra o escaneamento passivo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/1/294181/18432.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/1/294181/18432.png)

Figura 1 - Escaneamento passivo

### Escaneamento Ativo

No escaneamento ativo, a estação que deseja se conectar a uma rede envia um _**frame**_ chamado _**(Probe Request)**_ procurando uma específica rede para se conectar.

Este frame especial contém o referido SSID da rede à qual ela deseja se conectar ou um SSID _**broadcast.**_

No primeiro caso, somente o _**Access Point**_ com o SSID especificado irá responder ao _**frame Probe Request**_ com um segundo frame chamado _**(Probe Response).**_

No segundo caso, todos os APs responderão, e a estação iniciará o processo de autenticação e associação ao _**Access Point**_ com a maior intensidade de sinal chegando a sua antena e com a menor taxa de erro de transmissão. A figura 2 ilustra os dois processos de escaneamento ativo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294256/18433.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294256/18433.png)

Figura 2 - Escaneamento ativo.

### _Load Balance_

Nos sistemas wireless a tecnologia empregada é a de compartilhamento de banda entre as estações que estão conectadas a um _**Access Point**_, o que significa que caso tenhamos uma rede com velocidade de sinalização de 11Mbps e nesta rede estejam conectadas 22 estações, teremos como resultante um _**throughput**_ médio teórico de apenas 500Kbps por estação. Para melhorar esta situação pode-se instalar mais de um AP, cada um num canal diferente conforme já vimos em outros tópicos  (canal 1, 6 e 11).

Assim, as estações agora irão procurar se associar aos _**Access Points**_ com a melhor intensidade de sinal que chega a sua antena e com a menor taxa de erro de transmissão. Com isso a carga da rede toda será dividida por AP, com menor quantidade de estações a eles conectados, portanto, haverá um aumento do _**throughput**_ médio teórico por estação, numa relação de três vezes ao anterior, fornecendo agora 1,5Mbps por estação de trabalho.

### Gerenciamento de Energia

A economia de energia é assunto que merece uma especial atenção nas redes wireless porque os transmissores podem drenar uma considerável quantidade de energia das baterias e com isso diminuir drasticamente a autonomia da estação quando estas não estão em modo de energia elétrica conectadas. Para amenizar está dificuldade de autonomia de baterias, o padrão 802.11 criou uma metodologia de economia de energia para estes dispositivos que, por pequenos e breves períodos de tempo, os transmissores são desligados para poupar as baterias.

As estações podem operar em um dos dois modos de gerenciamento de energia, notificando o _**Access Point**_ sobre qual modo irá operar. Esta informação está vinculada ao campo “controle do frame”, no quadro do 802.11.

Estes dois modos são: _**Active Mode – AM**_ (modo ativo) e o _**Power Save Polling Mode – PSP**_ (modo de economia de energia). No modelo AM, as estações wireless estão conectadas à fonte de energia constante e desta forma podem receber frames a qualquer instante. No modelo AM o processo de economia de energia está desligado.

No modelo PSP, o _**Access Point**_ não poderá enviar frames arbitrariamente para as estações que estiverem operando no modo de economia de energia. O AP armazenará os _**frames**_ que são destinados às estações que estiverem no estado desligado e só transmitirão estes _**frames**_ em tempos designados e sincronizados com a estação que voltar a ligar os seus transmissores. O processo de economia de energia PSP nas estações que estão operando numa configuração de topologia BSS segue os seguintes passos:

1. A estação envia um _frame_ ao AP informando que irá desligar temporariamente seus transmissores.
2. O _Access Point_ registra o estado desta estação.
3. O _Access Point_ passa a armazenar os _frames_ destinados à estação. O tráfego das outras estações continua chegando e sendo transmitido normalmente, somente os _frames_ destinados à estação que está no modo desligado serão acumulados no AP.
4. O _Access Point_ identifica qual estação possui frames armazenados através do _Traffic Indication Map – TIM_, que é incluído em todos os frames _beacon._
5. Como a estação está sincronizada com o AP, ela detecta exatamente o momento de receber um _beacon._ Então é religado o transmissor para recepção do _beacon_ e da verificação da existência de _frames_ registrados na lista do TIM.
6. Caso existam registros na listagem do TIM, ela enviará uma notificação ao AP, que o informará que está apta a receber os _frames._
7. _O Access Point_ por sua vez envia os frames destinados à estação.
8. Quando a estação terminar de receber os frames, ela enviará uma notificação para o AP, que irá novamente desligar o transmissor.

No processo de economia de energia em uma topologia IBSS, os frames destinados às estações são anunciados durante um período conhecido como _**ATIM –  Ad-hoc Traffic indication Message**_. Como no modo IBSS não existe APs para armazenar os frames para as estações que estão com os transmissores desligados, estes frames são então armazenados nas próprias máquinas que desejam transmiti-los. Nos momentos de tempo ATIM, cada estação estará apta a receber estes frames pré-armazenados.

### Questões de Segurança nas Redes Wireless - Lan

Um dos grandes desafios das redes que utilizam a tecnologia de ondas eletromagnéticas diz respeito à proteção dos dados que são transmitidos no espaço. Como o meio é o ar e este não tem nenhuma barreira física de proteção entre os dados e quem quiser “ouvir” estes dados, as redes wireless têm criado novos desafios para os profissionais de redes, na intenção de proteger a integridade das informações para além das fronteiras físicas de uma empresa, onde uma estação não autorizada poderá se conectar à rede e capturar todos os dados desta. Em redes cabeadas, as restrições físicas de acesso ao meio, que são cabos e demais equipamentos podem prevenir que alguém não autorizado conecte-se à rede, mas nas redes sem fio, isso é praticamente impossível.

As facilidades de instalação de redes sem fio também tem sido exploradas por pessoas mal intencionadas, pois a grande maioria das pessoas que adquirem equipamentos _**Access Point**_ são para uso residencial, na perspectiva do compartilhamento do acesso à Internet e, muitas destas pessoas não têm ou não dispõem dos conhecimentos básicos sobre segurança, criptografia e melhores práticas na configuração de suas redes, deixando-as, muitas vezes completamente abertas, bastando apenas que de posse de um notebook e uma placa de rede sem fio, qualquer um consiga o compartilhamento da rede local. (RAPPAPORT, 2009)

Diversos mecanismos de segurança implementados pelo padrão IEEE 802.11 buscam garantir a segurança do meio wireless, como exemplos pode-se citar: WEP e filtro de _**MAC Address**_, porém estes mecanismos propostos são antigos e extremamente vulneráveis a ataques. Existem softwares disponíveis na Internet que já conseguem quebrar senhas do WEP e, endereços MAC podem ser manipulados pelo invasor para conseguir se passar por máquinas devidamente autorizadas à conexão. Novas metodologias de segurança vêm sendo criadas para melhorar as fraquezas detectadas no primeiro modelo. São elas o WPA, o 802.1x e o 802.11i, que vem aprimorando a parte wireless no tangente à segurança dos dados trafegados.

### Definição Básica do Padrão IEEE 802.11

O padrão 802.11 especifica duas metodologias de segurança para as redes wireless:

1. Autenticação: Pelo uso do SSID, que verifica a identidade da estação que deseja se conectar à rede;
2. Privacidade: Através da cifragem dos dados pelo WEP – _Wired Equivalent Privacy,_ que busca a mesma privacidade alcançada pelas redes cabeadas.

A autenticidade pelo uso do SSID permite somente estações que tenham o mesmo SSID se conectarem ao _**Access Point**_ e consequentemente à rede, porém, este método de segurança é muito fraco, pois o SSID é distribuído no _**frame Beacon**_ de forma aberta e qualquer pessoa mal intencionada poderá capturar o SSID e com isso ganhar acesso à rede.

Uma forma de dificultar um pouco o trabalho deste hacker é adotar alguns procedimentos simples que podem auxiliar nas defesas da rede. São eles:

1. Não utilizar somente o SSID como metodologia de segurança, porque conforme explicado, o SSID é distribuído em texto puro no _frame beacon_ e de fácil captura.
2. Não utilizar o nome da empresa como SSID ou o _default_ que já vem pré-configurado no equipamento, porque sem muito esforço um hacker poderá deduzir o SSID começando pelo próprio nome da companhia.
3. Desabilitar o envio do SSID no _frame beacon_ é uma medida inteligente, pois alguns rádios permitem esta função deixando a rede totalmente invisível a softwares de captura e até mesmo ao sistema operacional das estações. Neste caso, a cada primeira conexão das estações a rede, o SSID deverá ser digitado manualmente pelo administrador.

O padrão IEEE 802.11 especifica duas metodologia de autenticação das estações no _**Access Point**_. São elas:

1. Autenticação por sistema aberto;
2. Autenticação por chave compartilhada.

### Autenticação por Sistema Aberto

A autenticação por sistema aberto significa que a estação se autentica a qualquer _**Access Point**_ que tenha o mesmo SSID, ou seja, o mesmo nome da rede. Portanto, este tipo de autenticação não é recomendado, pois a qualquer instante qualquer estação poderá adentrar à rede e compartilhar os serviços por ela fornecidos. O processo de autenticação por sistema aberto ocorre da seguinte maneira:

1. Uma estação utilizando o mesmo SSID envia um _frame_ de requisição ao _Access Point_, utilizando o endereço de origem MAC.
2. O Access Point processa a requisição e verifica se a estação tem o mesmo SSID. Caso positivo, ele autentica o cliente enviando-lhe uma resposta positiva sem verificar a identidade dele, ou seja, ele assume o endereço MAC transmitido pela estação como uma identificação válida.
3. A estação se conecta à rede passando agora para o processo de associação.

Percebe-se então que utilizar a autenticação por sistema aberto é totalmente contrário a qualquer regra de segurança, pois, expõe a rede e os serviços dela a qualquer pessoa mal intencionada, não oferecendo nenhuma barreira de contenção. Casos assim acontecem quando pessoas não qualificadas assumem a função de instalar o _**Access Point,**_ podendo comprometer totalmente a segurança de uma rede.

### Autenticação por Compartilhamento de Chave

A autenticação por compartilhamento de chave é uma metodologia mais segura do que a autenticação por sistema aberto porque, necessita que seja configurada previamente no _**Access Point**_ e a todas as estações uma senha de segurança de igual teor e conteúdo, ou seja, a senha deve ser igual em todos os equipamentos da rede.

Para o método de autenticação por compartilhamento de chave é necessário o uso do _**WEP – Wired Equivalent Privacy**_ para a criptografia e a descriptografia de um texto desafio que é enviado pelo AP. O processo de autenticação por compartilhamento de chave funciona da seguinte forma:

1. Exatamente igual a autenticação por sistema aberto, uma estação utilizando o mesmo SSID envia um _frame_ de requisição ao AP utilizando o endereço de origem MAC.
2. O _Access Point_, antes de autenticar a estação, prepara um texto desafio utilizando uma sequência aleatória de 128 bytes gerada pelo WEP em texto pleno, ou seja, sem criptografia e, após esta preparação, o frame é encaminhado à estação requisitante.
3. No terceiro _frame_ a estação copia o texto desafio do passo anterior encaminhado pelo AP e executa a criptografia, usando a chave digitada anteriormente na configuração dos equipamentos. Lembre-se que a chave deverá ser a mesma para todos estes e então a estação envia um quarto _frame_ ao _Access Point_, agora criptografado.
4. O AP recebendo este _frame,_ executa a descriptografia utilizando a mesma chave previamente configurada. Caso o texto seja igual ao enviado com texto desafio original, o _Access Point_ autentica a estação à rede.

### Conceituação Básica de Criptografia

O conceito básico de criptografia é, tornar o texto indecifrável para quem o está lendo, sem que este possua uma chave que possa convertê-lo, ficando assim embaralhado, de uma forma ilegível e entendível.

Como exemplo mais básico, podemos dizer que uma criptografia ou cifragem básica, passa por uma operação lógica chamada “Ou exclusiva”. As operações lógicas basicamente aplicam dois sinais binários em uma porta lógica e verificam a sua saída; no caso da porta lógica “Ou exclusivo” teremos a saída com nível lógico 1 apenas quando as entradas tiverem nível lógico diferentes uma da outra (0 ou 1). (MEDEIROS, 2010)

Nos rádios wireless para tornar a mensagem camuflada à leitura, utiliza-se a criptografia descrita acima em uma entrada e aplica-se os dados a serem transmitidos e em outra porta, aplica-se a chave de criptografia. Ambas as entradas produzirão uma saída, com os dados originais completamente embaralhados. No _**Access Point**_ o administrador da rede digita uma chave secreta de 40 bits, e os rádios irão gerar mais 24 bits chamados “Vetor de Inicialização”. Com a união da chave de 40 bits com o vetor de inicialização de 24 bits têm-se agora uma chave de 64 bits, conhecida como máscara.

Quando se deseja transmitir uma informação, o rádio transmissor faz uma operação lógica “ou exclusiva” entre a sequência de dados e a máscara, gerando a sequência que será realmente transmitida, totalmente cifrada, ou seja, embaralhada, dificultando a leitura por algum hacker que venha a capturar as informações no meio. A figura 3 ilustra o conceito básico da cifragem.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294264/18435.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294264/18435.png)

Figura 3 - Processo de Criptografia

### A Criptografia WEP – _Wired Equivalent Privacy_

O _**Wired Equivalent Privacy**_ é um algoritmo de cifragem desenvolvido com a intenção de oferecer segurança através da rede wireless 802.11 enquanto os dados são transmitidos de um ponto a outro. O WEP pretende proporcionar segurança física para leitura indevida dos dados no momento da transmissão por ondas de rádio na mesma proporção que as redes cabeadas protegem as informações pelo envoltório dos cabos UTPs. Esta proteção inclui estações não autorizadas a “escutar” o tráfego de dados, fornecendo assim confiabilidade e integridade nas informações por não permitir modificações.

O WEP é um algoritmo simples, que utiliza a geração de números pseudorrandômicos e a cifragem RC4. O motivo da escolha deste algoritmo foi sua rapidez nas sequências de criptografia e descriptografia, o que economiza ciclos de CPU, minimizando os impactos no processamento das informações pelo _**Access Point.**_ O segredo da segurança da criptografia WEP está na dificuldade em descobrir a chave secreta digitada pelo administrador da rede, isso se relaciona com o tamanho da chave e com que frequência ela muda. (SANTOS JUNIOR 2005)

### O Processo WEP

O processo de criptografia WEP é apresentado na figura 4, onde temos todos os circuitos e funções necessárias para a formação do _**frame**_ wireless. O processo de criptografia inicia-se com uma chave secreta, que deverá ser inserida pelo administrador da rede em todos os APs e todas as estações que farão parte da mesma rede. Observe que todas as estações e _**Access Points**_ devem possuir o mesmo SSID e no caso da utilização de mais de um AP na rede, estes devem ser configurados em canais diferentes (canal 1, 6 e 11), para evitar a interpolação de um canal sobre o outro. O processo da cifragem WEP ocorre da seguinte forma:

1. Uma chave secreta de 40 ou 104 bits deverá ser digitada pelo administrador em todos os equipamentos que vão compor a rede.
2. Para a formação da chave em definitivo, que será fornecida para a cifragem, um gerador interno ao rádio chamado de 24 bits, irá gerar um complemento que será somado à chave digitada pelo administrador com a prerrogativa da chave criptográfica nunca se repetir. Os 24 bits gerados aleatoriamente pelo VI obterá um valor máximo de 16.777.216 de combinações válidas que não se repetirá até terminarem todos os valores. Para cada frame transmitido é gerado uma nova chave com a combinação dos valores digitados inicialmente acrescidos dos gerados pelo VI.
    
    Vetor de Inicialização – VI
    
3. Para que o receptor possa recuperar os dados, ou seja, executar a descriptografia do dado transmitido, o Vetor de Inicialização é transmitido no _frame_ de forma clara, sem criptografia, para que o receptor possa uni-lo à sua própria chave secreta digitada pelo administrador e compor a nova informação.
4. Após a junção da chave digitada mais o VI, perfazendo 64 ou 128 bits (40 ou 104 digitados + 24 bits do VI), são encaminhados ao circuito PRNG, que será responsável pela geração de uma sequência chave do tamanho igual ao dado a ser transmitido, acrescidos de 4 bits usados para a proteção dos dados. Portanto, para cada frame a ser transmitido será gerado uma sequência chave com tamanhos diferentes.
5. Para a proteção dos dados contra modificações não autorizadas, um algoritmo de integridade atua sobre ele para produção de um vetor de integridade – ICV com tamanho de 4 bits que será somado ao dado a ser transmitido.
6. A criptografia então é concluída através de uma operação lógica , gerando assim, em definitivo, o texto cifrado.
    
    Ou Exclusiva
    
7. Observe que apenas os dados serão cifrados, pois o endereçamento MAC _Address_ do _frame_ e o Vetor de Inicialização de 24 bits são transmitidos em texto pleno, ou seja, sem nenhuma cifragem.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/7/294734/18436.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/7/294734/18436.png)

Figura 4 - Processo de criptografia WEP

Fonte: SANTOS JUNIOR, 2005

Conforme apresentado na sequência acima, o processo do WEP apresenta algumas dificuldades referente à proteção dos dados, que são:

1. Reutilização da chave WEP: O WEP utiliza a mesma chave secreta digitada e diferentes valores de VI para a criptografia dos dados. Como a VI possui 24 bits possibilitando 16.777.216 valores distintos, uma vez vencidos estes valores, as novas combinações serão repetidas, o que implicará na reutilização de uma mesma sequência chave; o que poderá abrir caminho para um hacker a descobrir a chave secreta digitada.
2. Número de bits para criptografia insuficientes: O padrão WEP oferece uma chave secreta digitada de 40 bits apenas, que somados ao VI de 24 totalizam 64 bits. Alguns fabricantes oferecem uma chave de 104 bits que somados aos 24 do VI, equivalem a 128 bits. Porém isso não garante uma maior segurança e, por outro lado, pode significar uma falta de interoperabilidade entre fabricantes.
3. Gerenciamento manual das chaves secretas: A chave utilizada é única para todos os equipamentos, o que pode representar uma falta de segurança. Imagine a situação onde um ex-funcionário conheça a referida chave? Portanto, a cada mudança do quadro de funcionários ou manutenção de equipamentos, a chave necessita ser trocada gerando muito trabalho.

### O processo WPA

O uso do WEP e do SSID como medidas de segurança provaram ser muito fracos para as redes wireless, por isso, novos métodos foram criados para melhorar a segurança e permitir maior liberdade aos administradores das redes sem fio.

O WPA – _**WiFi Protected Access**_ surgiu no início de 2003 como um esforço da indústria para melhorar as vulnerabilidades do padrão WEP. O WPA é em realidade uma subsérie do padrão 802.11i, criado em 2002 com a função de produzir especificações de melhoria para as redes wireless – LAN no critério de segurança. O padrão IEEE 802.11i criou modificações profundas nas questões de segurança nos rádios wireless, que os equipamentos existentes não suportariam tais implementações, precisando assim uma mudança significativa em seu hardware.   Como a indústria não poderia esperar o término das modificações e nem arcar com os custos de uma mudança global em seus produtos, preferiu aderir em partes às resoluções do 802.11i.

O WPA então é baseado em uma parte dos trabalhos desenvolvidos pelo grupo IEEE 802.11i. As principais características destes trabalhos são:

1. Autorização do usuário baseado no protocolo 802.1x, que faz uso de um servidor de autenticação RADIUS, provendo assim flexibilidade para a autenticação mútua entre usuários e a rede. O 802.1x é baseado no _Extensible Authentications Protocol_ – EAP.

O uso do 802.1x requer três componentes na rede para efetuar uma autenticação de usuários. São eles:

- Um requisitante – estação de trabalho que deseja se conectar à rede.
- Um autenticador - que neste caso é o próprio _Access Point_, que irá trabalhar como um intermediário entre o requisitante e o servidor de autenticação.
- Um servidor de autenticação RADIUS – _Remote Authentications Dial-in Use Service_ que é responsável pela validação do usuário que deseja se conectar aos serviços da rede.

Como um servidor de autenticação RADIUS é um produto de custo elevado e de difícil configuração, o WPA prevê um método alternativo de autenticação para pequenos negócios ou o uso domiciliar. Este método é o _**Pré-Shared Key – PSK**_ que não requer um servidor de autenticação RADIUS, ficando a cargo do Access Point executar esta validação.

1. Confiabilidade através de melhorias na criptografia de dados usando o _Temporal Key Integrity Protocol_ – TKIP que apesar de usar o mesmo algoritmo de criptografia RC4 utilizado pelo WEP, adicionou melhorias técnicas tentando suprimir as deficiências do padrão anterior.

Entre estas novas funções, acrescentou a cada frame transmitido de um vetor de inicialização bem maior que o anterior, que antes era de 24 e agora de 48 bits, que são misturados à chave digitada pelo administrador.

1. Também foi implementado o MIC – _Message Integrity Code_ que é capaz de identificar pacotes alterados entre o transmissor e o receptor, calculando e comparando um valor de 8 bits gerados por uma sofisticada função matemática. Este valor calculado inclui informações de endereço de origem, de destino que anteriormente no padrão WEP não eram protegidos.

O Protocolo TKIP, basicamente, muda a chave de criptografia para cada frame transmitido, eliminando assim uma virtual chance de um hacker capturar as informações e tentar descobrir a chave secreta. Também com o aumento do Vetor de Inicialização que passou dos 24 utilizado pelo WEP para 48 bits, a sequência chave de criptografia poderá ser alterada aproximadamente 281 trilhões de vezes, sem ser repetida, tornando praticamente impossível de um hacker capturar pacotes com chaves repetidas.

Diferente do WEP, o TKIP usado no WPA implementa criptografia por usuário, por sessão e por pacote transmitido, através do embaralhamento do VI com a chave digitada pelo administrador. A adoção do TKIP é uma solução intermediária, enquanto se aguarda a implementação de algoritmos mais fortes prometidos pelo padrão 802.11i. A grande vantagem da utilização do TKIP é a não necessidade da troca de hardware, mas apenas uma atualização de software firmware podendo ser instalado no hardware existente. A figura 5 ilustra o processo WPA de criptografia e seus circuitos relacionados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295000/18437.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295000/18437.png)

Figura 5 - Comparativo entre TKIP e WEP

Fonte: SANTOS JUNIOR, 2005

Com a recente ratificação do padrão 802.11i, criou-se o WPA2, que implementa o AES - _**Advanced Encription Standard**_ no lugar do simples RC4, porém, para esta nova modalidade existe a necessidade de alterações de hardware como a adição de um coprocessador matemático. A tabela 1 demonstra as principais diferenças entre os dois padrões: WEP e o WPA. (SANTOS JUNIOR, 2005)

**Tabela 1 – Comparação entre WEP e WPA**

![[Untitled 75.png|Untitled 75.png]]

### Revisão:

O SSID é a identificação da rede e todos os equipamentos que vão fazer parte da rede precisam ter o mesmo SSID.

O _**frame Beacon**_ é usado para sincronizar todas as estações e nele estão contidas informações sobre taxa de transmissão, tipo de topologia, SSID e listagem TIM e ATIM.

O balanceamento da rede significa instalar mais de um AP e com isso reduzir a quantidade de estações conectadas em cada um, aumentando a performance da conexão a estas estações.

A segurança das redes wireless é conseguida pela utilização da criptografia ou cifragem nas informações transmitidas.

A criptografia é em outras palavras tornar a informação embaralhada com a finalidade de que se for capturada por um hacker, os dados coletados não farão nenhum sentido.

Para a cifragem dos dados utilizam-se os algoritmos WEP e WPA:

- O WEP utiliza um vetor de Inicialização de 24 bits e o WPA de 48 bits.
- A chave secreta é somada ao VI no WEP. No WPA ela é embaralhada.
- O WPA utiliza o MIC para garantir a integridade dos dados, considerando também os endereços de origem e destino. O WEP utiliza o CRC-32 que só faz retratação aos dados.
- O WEP não faz gerenciamento de chaves. O WPA utiliza as versões do EAP para tal gerenciamento.