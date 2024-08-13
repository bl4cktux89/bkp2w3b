### Objetivo:

Neste tópico apresentaremos a tecnologia WiMax, que em outras palavras é a extensão das redes wireless LAN. Esta tecnologia aplicada para um ambiente externo, possibilita maior capacidade de transmissão de dados e um alcance superior na sua abrangência.

### Introdução

A tecnologia WiMax – _**Worldwide Interoperability for Microwave Access**_ é o nome genérico utilizado para identificar uma das mais recentes e promissoras redes de abrangência WMAN (redes metropolitanas), com acesso via rádio frequência. No Brasil, atualmente, esta solução seria a forma mais segura e rápida de vencer os desafios referente às questões do _**“last mile”**_ ou última milha, que é o atendimento ao assinante por meios mais eficientes do que os utilizados na rede de telefonia por par metálico.

As tecnologias de acesso existentes via redes telefônicas por par metálico como o xDSL, não têm a capacidade, a qualidade e a escalabilidade necessárias ao atendimento da grande demanda de dados. Por outro lado, as tecnologias que utilizam as ondas de rádio, como o 3G / 4G da telefonia celular, também foram incapazes da tão necessária qualidade para tráfego intenso de dados.

A rede WiMax foi padronizada pelo IEEE no ano de 2001 com a designação IEEE 802.16 e seu principal objetivo é estabelecer conectividade de boa qualidade na parte final _**(last mile)**_ ao atendimento para uso doméstico, empresarial e em hot spot. A proposta do WiMax é suprir as necessidades do mercado com altas taxas de transmissão de dados, maior alcance e uma ampla área de cobertura, fornecendo conectividade a um grande número de usuários.

Por questões políticas, o Brasil navega na contra mão dos principais países emergentes, onde o WiMax é a principal tecnologia fornecedora de conectividade de alta taxa a um grupo muito grande de pessoas em uma cidade, funcionando exatamente como uma rede de telefonia celular, proporcionando rede de acesso fixo ou móvel, conforme veremos na sequência todos os padrões existentes para as redes WiMax.

### O Padrão 802.16 e Sua Família

O padrão 802.16 não é o único a integrar a tecnologia, mas um conjunto de padrões que no decorrer do tempo vem sofrendo constantes atualizações e se aperfeiçoando cada vez mais. Dentre o conjunto de padrões existentes na família, destaca-se o 802.16d e o 802.16e. O primeiro destina-se ao fornecimento de conectividade a assinantes fixos e o segundo à conexão móvel.

O protocolo 802.16 foi desenvolvido para trabalhar com frequências de 10 a 66 GHz, com visada direta, taxas de transmissão de até 134Mbps e um alcance médio de 5Km numa configuração de células abrangendo uma cidade inteira, por isso recebe a designação de redes WMAN ou Redes Metropolitanas sem Fio.

### O Padrão 802.16d

O padrão 802.16d é uma evolução ao padrão que o antecedeu o 802.15a, que foi conhecido como o WiMax fixo ou nórdico. Esta configuração não suporta _**handoffs**_, ou seja, não suporta mudanças da estação móvel de uma célula para outra durante a sua comunicação, portanto, este padrão é destinado a assinantes fixos, como residências ou empresas que através de uma antena conseguem conectividade com visada direta com a estação rádio base – ERB mais próxima.

O padrão 802.16d foi homologado pelo IEEE em 2004 e opera na faixa de frequência de 2 a 11 GHz com linha de visada. As taxas de transferências podem chegar até 75 Mbps utilizando a modulação OFDM. Seu alcance está entre 5 e 10 quilômetros e dependendo do tipo de equipamento utilizado, como uma antena de maior ganho e rádio de maior potência, pode-se alcançar distâncias de até 50 quilômetros tranquilamente, levando sempre em consideração a altura das antenas e o raio de curvatura da Terra.

### O Padrão 802.11e

Este padrão, ao contrário do 802.11d, foi desenvolvido para permitir mobilidade, _**handoffs**_ e otimizações. Foi ratificado em 2005 e opera na faixa de frequência de 2 a 6 GHz, sem a necessidade de visada direta e com taxas de transferência de até 15 Mbps. O alcance ou área de cobertura pode variar entre 2 e 5 quilômetros e trabalha numa configuração de células, com abrangência de grandes áreas ou até mesmo uma cidade inteira.

A técnica de modulação é a SOFDMA – _**Scalable Orthogonal Frequency Multiplexing Access**_ que transmite através de múltiplas portadoras com sub canalizações. A tabela 1 mostra um resumo dos principais padrões definidos pela tecnologia WiMax. (MEDEIROS, 2010)

**Tabela 1 – Resumo da Tecnologia WiMax**

![[Untitled 79.png|Untitled 79.png]]

### Desenvolvimento e Aplicação

A tecnologia WiMax vem sendo desenvolvida e estudada por um fórum, o wimaxforum – http://www.wimaxforum.org, constituído de 230 empresas e participantes líderes no segmento como a Intel, Motorola, AT&&T, Alcatel, Nokia, Fujitsu, France Telecom, Siemens entre outras e tem em seus estatutos uma organização sem fins lucrativos. O objetivo principal é tornar um padrão de equipamentos compatíveis com o 802.16 para alcançar a sonhada interoperabilidade. O WiMax é indicado para ambientes urbanos. Isso traz uma dificuldade extra para uma rede sem fio comum, pois o sinal refletido em edifícios deve ser o suficiente para que o receptor recupere o sinal transmitido sem erros.

Apesar desta dificuldade, nas questões financeiras, a implantação de uma rede celular WiMax tem um custo muito menor, se comparada à tecnologia de telefonia celular, e aproveitando as ERBs já instaladas da telefonia celular, o custo fica ainda menor, pois a infraestrutura primária já existe: o local, a torre, a eletrificação e o canal SDH em cabeamento óptico já foram instalados e se encontra operacionais ao atendimento da estação de telefonia celular, portanto, a implementação dos equipamentos e antenas WiMax é teoricamente bastante simplificada. A visão de uma estrutura WiMax é demonstrada na figura 1 criando um atendimento WMAN.

A tecnologia WiMax poderia então não só conectar as redes de computadores ou os equipamentos ditos computadores, mas poderia servir de principal meio de acesso a qualquer mídia digital por uma infonidade de equipamentos, como exemplo: smartphones, tablets, PDAs, notebooks e as que ainda viram com o decorrer do tempo e os avanços da tecnologia. A figura 2 ilustra este parque de equipamentos a serem conectados.

### Qualidade de Serviços e Segurança

A Tecnologia 802.16 apresenta qualidade de serviço que permite a transmissão de voz e vídeo que requerem baixa taxa de latência. O MAC _**(Media Access Control)**_ do 802.16 provê níveis de serviço _**"Premium"**_ para clientes corporativos, assim como um alto volume de serviços em um padrão equivalente aos hoje oferecidos pelos serviços de xDSL e de _**Cable Modem**_, tudo dentro da mesma estação rádio base – ERB. A segurança do padrão WiMax suporta a autenticação com certificado x.509 e criptografia de dados utilizando o protocolo DES – _**Data Encryption Standard**_ podendo transportar sem problemas, tanto o IPV4 como o IPV6 ou ainda, o Ethernet simultaneamente com QoS – Qualidade de Serviços. (RAPPAPORT, 2009)

### Revisão:

- A Tecnologia WiMax – IEEE 802.16 foi desenvolvida para o atendimento às WMAN ou fornecimento de conectividade sem fio para áreas metropolitanas.
- O 802.16 possui dois padrões que se destacam para aplicações fixas e móveis. São eles: 802.16d para aplicações fixas com pequena mobilidade. 802.16e para aplicações móveis.
- O padrão 802.16d necessita de visada e utilização de antena direcional focada para uma ERB mais próxima ao endereço do assinante.
- O padrão 802.16e não requer visada e é aplicado para estações móveis ou em trânsito.
- A distância de alcance para o padrão 802.16d está em torno de 5 quilômetros e para o padrão 802.16e em 2 quilômetros.
- O padrão 802.16e utiliza o mesmo esquema de telefonia celular, chegando conforme a localidade, a alcançar toda uma cidade, pois permite o _roaming_ quando em deslocamento e taxas de transmissão de até 15 Mbps.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/3/312363/18738.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/3/312363/18738.jpg)

Figura 1 - Topologia Metropolitana em tecnologia WiMAX

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/3/312364/21533.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/2/3/312364/21533.jpg)

Figura 2 - Conectividade com a WiMax

Fonte: Teleco