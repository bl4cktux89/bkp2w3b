### Introdução aos tipos de ligação

Quando pensamos na interligação de redes podemos ter diferentes padrões de meios, protocolos e serviços de comunicação de dados. Por este motivo, não podemos pensar na comunicação de dados entre diferentes redes de forma homogênea, contendo os mesmos protocolos e dispositivos de interconexão que funcionam da mesma forma entre a rede de origem e uma rede de destino, principalmente, quando esses dados viajam por meio das grandes redes. A arquitetura da Internet é um típico exemplo dessa complexidade e heterogeneidade na interconexão, podendo operar de forma **dedicada** e **comutada**, conforme descrita abaixo tendo como base a Figura 1.

- **Ligação comutada:** uma rede comutada permite o compartilhamento de recursos, permitindo dessa forma, por exemplo, que qualquer pessoa que detenha uma linha telefônica se comunique com qualquer outro usuário. Este tipo de ligação é conhecido como **comutação por circuito** e utiliza os comutadores presentes nas centrais telefônicas estabelecer um circuito entre origem e destino. Apesar de existir um circuito único entre origem, ele não é dedicado, uma vez que, ao fim da ligação, o circuito é desfeito. Quando estabelecemos uma conexão à Internet via modem, estamos também utilizando um serviço comutado por circuito com a operadora de telecomunicações. Entretanto, quando os dados chegam a operadora de telecomunicações utilizamos uma técnica diferente, conhecida como **comutação por pacote.** Na comutação por pacote, as informações são segmentadas em pacotes e podem passar por diferentes caminhos até o destino, utilizando. Na Figura 1 é mostrado um dispositivo chamado de DSLAN (Multiplexador de Acesso à Linha Digital do Assinante) que permite a concentração de diversas linha telefônicas e oferecer internet banda larga por meio da tecnologia xDSL (transmissão digital de dados via rede de telefonia).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261483/13871.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261483/13871.jpg)

Figura 1 - DSLAN

- **Ligação dedicada:** uma ligação dedicada, por sua vez, como o próprio no já diz, utiliza uma ligação dedicada (exclusiva), sem o compartilhamento dos recursos, como acontece em uma central telefônica. Uma ligação dedicada ou link dedicado normalmente é utilizado por grandes corporações que necessitam de garantia na entrega da largura de banda exigida por aplicações críticas, tais como, e-commerce, instituições financeiras e datacenters. Embora a ligação até a operadora aconteça de forma dedica, quando os dados provenientes dessas redes chegam a grande rede, a Internet, podem passar por redes comutadas. Ligações dedicadas, normalmente, possuem equipamentos dedicados chamados Data Terminal Equipment (DTE – Equipamento Terminal de Dados) pertencente ao cliente e um modem conhecido como Data communication Equipment (DCE – Equipamento de comunicação de dados) da operadora, conforme mostrado na Figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/2/0/242047/8511.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/2/0/242047/8511.jpg)

Figura 2 - Ligação CDE e DTE.

### Tipos de processamento

Após a transmissão de dados por um meio de transmissão há a necessidade de realizar o seu processamento por algum nó. Esse processamento pode estar relacionado com a decisão pelo qual um roteador, por exemplo, deve tomar para enviar um pacote entrou por uma de suas interfaces e encaminha-lo para uma interface de saída e, após “viajar” novamente pelo meio de transmissão, é necessário realizar o processamento por um dispositivo fim. Para entender como são realizados os diferentes tipos de processamento, devemos conhecer como funciona o ciclo de operações básicas de qualquer sistema computacional. As operações básicas são:

1. Leitura dos dados por meio de uma interface de ENTRADA;
2. ARMAZENA os dados lidos;
3. Efetua-se o PROCESSAMENTO necessário;
4. Fornece o resultado de SAÍDA.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/3/9/5/339598/24046.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/3/9/5/339598/24046.jpg)

Figura 3- Etapas de processamento.

Portanto, podemos diferencia os tipos de processamento de acordo como essas operações básicas são executadas a partir do momento em que os dados entram em uma interface. Dessa forma, podemos classificar os tipos de processamento em:

- **Processamento em Lotes (BATCH):** no processamento em BATCH as informações não são processadas imediatamente. As informações são coletadas e armazenadas para um processamento posterior. Esse tipo de processamento é comum ser utilizado por concessionárias de serviços de abastecimento de água, leitura dos pagamentos de crédito e débito para o comerciante.
- **Processamento On-line:** no processamento on-line as informações são processadas no mesmo instante em que são registradas, é um processamento atualizado. Normalmente, esse tipo de processamento é utilizado quando um nó (cliente) encaminha dados a outro nó (servidor) ou vice-versa. Este tipo de processamento é muito comum atualmente como, por exemplo, quando realizamos o pagamento de uma compra via cartão de débito, o desconto é realizado de imediato no servidor do cartão. Outro exemplo de processamento on-line é a operação de compra através de um E-commerce, mostrado na animação abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/6/314694/20879.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/6/314694/20879.gif)

Figura 4 - Processamento on-line - E-commerce.

- **Processamento Real Time:** o processamento Real Time é bem parecido com o on-line, entretanto, a diferença reside na disponibilidade dos resultados, no Real Time os dados são disponíveis imediatamente, não permitindo o menor intervalo de tempo de ação. Este tipo de processamento é voltado para controle de missão crítica, onde o tempo de resposta deve ser imediato. Exemplos desse tipo de processamento são: simuladores, controles de foguete e sistemas de posicionamento global (GPS) da Figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/7/270747/15840.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/7/270747/15840.jpg)

Figura 5 - Sistema de posicionamento geográfico (GPS). Típico exemplo de processamento Real Time

**Processamento On-line versus Real Time**

O processamento **Real Time** é sempre **on-line**, mas o inverso não é verdadeiro. No processamento Real Time existe uma garantia no tempo de resposta, enquanto que no on-line, o tempo de resposta depende de condições da rede, como por exemplo, a quantidade de usuários em um determinado período.