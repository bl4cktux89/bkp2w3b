A camada de transporte situa-se entre a camada de aplicação e rede da arquitetura TCP/IP, como uma entidade de software que é processado apenas nos sistemas finais, com duas principais funções:

- Multiplexação.
- Controle de fluxo.

A multiplexação tem a função de encaminhar a informação para a aplicação correspondente por meio de um identificador conhecido como porta e o controle de fluxo tem a função de efetuar o estabelecimento de chamada, controle no envio e recebimento de segmentos e finalização de uma chamada.

Trataremos neste capítulo os dois protocolos mais conhecidos da arquitetura TCP/IP referente a camada de transporte sendo o TCP (Transmission Control Protocol) e o UDP (User Datagram Protocol), além das funções da camada de transporte. Também estaremos analisando as mensagens por meio do software _**wireshark**_ para verificação destas funções.

A figura 1 ilustra o transporte lógico fim-a-fim e não físico entre entidades de software da camada de aplicação que se mostra como uma peça central da arquitetura TCP/IP, ou seja, a comunicação se processa como se um elemento de rede estivesse ligado diretamente a outro elemento de rede par.

A figura 1 também mostra que no encaminhamento dos segmentos entre entidades pares, o caminho natural é a Internet, que trata apenas as camadas física, enlace e rede, desta forma o processamento da camada de transporte acontece apenas nos elementos de rede finais, por isto, também conhecido como transporte lógico fim-a-fim.

Um protocolo da camada de transporte fornece sempre uma comunicação lógica entre os processos de aplicação que "rodam" nos equipamentos finais aqui chamados de elementos de rede e transportam protocolos de aplicação que se situa logo acima na estrutura de camadas da arquitetura TCP/IP.

Como forma de transportar aplicações os desenvolvedores criaram dois modelos de protocolos sendo um com funções para tráfego de arquivos que necessitam de garantia de entrega e que seja confiável como é o caso do TCP e outro sem garantia de entrega, mais simples, muito voltado a aplicações em tempo real como voz e vídeo ao vivo que é o caso do UDP.

![[dale.png]]

Tanto o TCP como o UDP fornecem verificação de integridade ao incluir campos de detecção de erros ou checksum no cabeçalho de seus segmentos, sendo a responsabilidade fundamental do UDP e do TCP é ampliar o serviço de entrega IP entre dois sistemas finais para um serviço de entrega entre dois processos que rodam nos sistemas finais

### **Multiplexação**

Tanto TCP como o UDP efetuam a função de multiplexação, ou seja, o encaminhamento dos dados para a aplicação correspondente, conforme a figura 2.

O trabalho de reunir, no elemento de rede de origem, partes de dados provenientes de diferentes sockets, encapsular cada parte de dados com informações de cabeçalho para criar segmentos, e passar esses segmentos para a camada de rede é denominada **multiplexação**.

A tarefa de entregar os dados contidos em um segmento da camada de transporte ao socket correto e este a aplicação correspondente é denominada **demultiplexação**.

![[dale2.png]]

---

### **O Protocolo TCP**

Para tratarmos o protocolo TCP, vamos analisar as partes do protocolo e suas funções, depois vamos capturar com o wireshark e analisar uma sequência real do protocolo. Uma conexão TCP provê:

- Um **serviço** _**full-duplex**_.
- É sempre **ponto a ponto**.
- Uma vez estabelecida uma conexão TCP, dois processos de aplicação podem enviar dados um para o outro.
- O TCP combina cada porção de dados do cliente com um cabeçalho TCP, formando, assim, **segmentos TCP**.

A figura 3 mostra o formato do protocolo.

Os primeiros 2 campos tratam das funções de multiplexação e são conhecidas como porta com tamanho de 16 bits, ou seja, o protocolo permite 216  ou 65.535 portas na origem e 65.535 portas no destino de 1 a 65535.

O site do IANA [**http://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml**](http://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) traz a estrutura da listagem das portas que são:

- De 1 a 1023 - portas bem conhecidas;
    - 1 a 255 - portas públicas
    - 256 a 1023 - portas designadas a empresas
- 1024 a 49151 - portas registradas (utilizadas pelos clientes para iniciar uma sessão);
- 49152 a 65535 - Portas dinâmicas ou privadas.

![[dale3.png]]

---

Ao todo, é possível usar 65.535 portas TCP e UDP, começando em 1. Tanto no protocolo TCP como no UDP, é comum o uso das portas de 1 a 1024, já que a aplicação destas é padronizada pela IANA (**I**nternet **A**ssigned **N**umbers **A**uthority). De acordo com essa entidade, eis algumas das portas TCP mais utilizadas:

Algumas portas TCP / UDP que usamos no dia a dia.

![[Untitled 47.png|Untitled 47.png]]

Em uma solicitação a um serviço no destino, por exemplo, uma página web a aplicação utiliza a porta de destino padronizada de número 80 conforme tabela 1 mas, a porta de origem ou elemento de rede que inicia a sessão, tem uma porta alocada dinamicamente pelo sistema operacional da rede e, no caso da captura com wireshark, na figura 4, alocou a porta de número 54.113 que é uma porta dinâmica.

A aplicação sempre responde para a porta de origem que solicitou a informação, ou seja, um servidor recebeu na porta 54.113, responde para o solicitante na porta 54.113.

No exemplo da figura 4 e 5, com wireshark, temos:

- Solicitação - _source porte_ (porta de origem 54.113) e _destination port_ (porta de destino 80)
- Resposta _source porte_ (porta de origem 80) e _destination port_ (porta de destino 54.113)

![[dale4.png]]

![[dale5.png]]

---

### **Controle de fluxo**

O protocolo TCP efetua o controle de fluxo utilizando os seguintes campos que serão vistos de forma detalhada:

- Número de sequência - 32 bits;
- Número de reconhecimento - 32 bits;
- Flags de SYN, FIN, ACK, RST, URG e PSH - 1 bit cada;
- Janela de recepção - 16 bits.

O número de sequência para um segmento é o número do primeiro byte do segmento.

O número de reconhecimento que o elemento de rede atribui a seu segmento é o número de sequência do próximo byte que ele estiver aguardando elemento de rede do destino.

Como o TCP somente reconhece bytes até o primeiro byte que estiver faltando na cadeia, dizemos que o TCP provê reconhecimentos cumulativos.

O TCP cria um serviço de transferência confiável de dados sobre o serviço de melhor esforço do IP que garante que a cadeia de bytes é idêntica à cadeia de bytes enviada pelo sistema final que está do outro lado da conexão.

Os procedimentos recomendados no [RFC 6298] para gerenciamento de temporizadores TCP utilizam apenas um único temporizador de retransmissão.

O TCP provê um serviço de controle de fluxo às suas aplicações, para eliminar a possibilidade de o remetente estourar o buffer do destinatário, ou seja, é um serviço de compatibilização de velocidades e oferece serviço de controle de fluxo fazendo que o remetente mantenha uma variável denominada janela de recepção.

Explicando o explanando acima conforme figura 6.

![[dale6.png]]

  

O processo TCP recebe os dados vindo da camada de rede por meio do protocolo IP. O processo de recepção tem um espaço para guarda dos segmentos conhecido como buffer de recepção (RCVBuffer). O processo de aplicação, dependendo da máquina, pode ser mais lento do que o processo de fluxo de dados vindo do IP, o que faz com que o buffer comece a encher e diminua o espaço disponível no buffer conhecido como janela de recepção (rwnd).

Voltaremos a este detalhe mais tarde.

Como dissemos anteriormente, o protocolo TCP é orientado a conexão, ou seja, antes de iniciar a conexão o elemento de rede de origem (host 1) envia um flag (1 bit) no campo flag do protocolo TCP conhecido como SYN (Figura 7a) com um número de sequência (x) alocado pela entidade de software TCP para o destino ou um servidor ( host 2).

Assim que o datagrama IP contendo o segmento TCP SYN chega ao elemento de rede no destino (host 2), o servidor extrai o segmento TCP SYN do datagrama, aloca buffers e variáveis TCP à conexão e envia um segmento de aceitação de conexão ao TCP cliente, ACK = x+1, onde x refere-se ao número de sequência enviado pela origem ( host 1).

Como a conexão e bidirecional, o host 2 aproveita o envio do ACK para enviar também a solicitação de conexão SYN com número de sequência y.

Da mesma forma o host 1 devolve o ACK = y +1 e o número de sequência x acrescido de + 1.

![[dale7.png]]

  

Ao receber o segmento SYNACK, o cliente também reserva buffers e variáveis para a conexão.

Completadas as três etapas, conhecido como _**three-way-handshake**_, o elemento de rede de origem e o servidor podem enviar segmentos contendo dados um ao outro.

Durante a vida de uma conexão TCP, o protocolo TCP que roda em cada elemento de rede faz transições pelos vários estados do TCP.

Obs: o caso b mostra o estabelecimento de conexões TCP simultâneas de ambos os lados.

A figura 8 apresenta os estados de conexão e finalização com o TCP explicado na sequência, mas, antes vamos a algumas nomenclaturas, conforme tabela a seguir.

![[Untitled 1 31.png|Untitled 1 31.png]]

A figura 8 mostra os estados da conexão TCP considerando que as linhas sólidas grossas são os percursos comuns ao cliente. As linhas tracejadas são os percursos comuns ao servidor. As linhas suaves são eventos incomuns. Cada transição é rotulada pelo evento que a produziu e ação resultante separada por barra.

![[dale8.png]]

---

### Solicitação de conexão

Na solicitação de conexão o protocol TCP envia um flag de SYN, conforme captura realizada com wireshark na figura 9.

![[dale9.png]]

A estação de destino responde com o flag ACK e, como a conexão é bidirecional, a estação de destino também solicita a conexão por meio de um flag SYN, conforme figura 10.

![[dale10.png]]

Fechando a conexão em 3 vias ou three-way-handshake a estação de origem confirma a solicitação de conexão com um flag ACK, conforme figura 11.

![[dale11.png]]

A figura 12 apresenta a sequência da conexão em 3 vias.

![[dale12.png]]

O mesmo processo ocorre na finalização da conexão, conforme figura 13, com a estação de origem enviando um flag FIN e estação de destino respondendo com um flag ACK e também finalizando a conexão uma vez que o fechamento é bidirecional.

![[dale13.png]]

Durante a conexão o controle de fluxo é feito pelo campo Janela utilizando o mecanismo de janela deslizante com tamanho de 16 bits (65.535).

O controle de fluxo é feito utilizando duas formas, conforme figura 6:

- Tamanho do buffer de recepção;
- Tamanho da janela de recepção.

O início da conexão o tamanho da janela é igual a 1 (um segmento) e dobra a cada retorno de confirmação (ACK) de quadro até o patamar (ssthresh) conforme figura 14 e 15.

![[dale14.png]]

![[dale15.png]]

Para cada segmento enviado, o protocolo mede o valor médio do RTT (tempo de ida e volta do segmento) figura 16. Caso um quadro não chegue ao destino ou o valor de RTT seja maior que a média, a rodada de transmissão inicia novamente em 1 e o patamar retorna a 50% do máximo conseguido na última rodada (chegou a um máximo de 12, com novo patamar igual a 6). Pode-se verificar na figura 15 que o tamanho da janela dobra até o patamar e, após, é somente incrementado de 1.

A figura 16 apresenta a captura efetuada com _**wireshark**_ com a captura do valor do RTT e o tamanho da janela (258).

![[dale16.png]]

Finalizando o transporte a figura 17 apesenta o número de sequência e reconhecimento de cada um dos segmentos enviados mostrando o número de sequência que se soma ao tamanho da informação criando um número de sequência subsequente.

O número de reconhecimento é o próximo número de segmento que a estação espera receber.

![[dale17.png]]