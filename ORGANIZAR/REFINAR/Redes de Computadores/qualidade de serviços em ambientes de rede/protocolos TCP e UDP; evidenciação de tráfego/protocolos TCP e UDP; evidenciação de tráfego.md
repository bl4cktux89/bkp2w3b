**Protocolos da camada de transporte**

Os protocolos TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são protocolos localizados na camada de transporte do modelo OSI usados pelas aplicações na internet para enviar e receber dados.

Diferentemente do protocolo IP, que entrega dados de um computador ao outro, os protocolos da camada de transporte entregam dados de uma aplicação para outra. O destino final de uma mensagem é uma aplicação, isto é, um processo (programa em execução que está rodando em uma determinada máquina). Esses processos são identificados por um número, denominado **porta de protocolo.**

Antes fazer qualquer comunicação, as aplicações devem se associar a uma porta. O sistema operacional local fornece uma interface por meio da qual os processos podem associar-se a uma porta. Em geral, as portas possuem buffers para que os dados fiquem armazenados até que sejam retirados pelos processos.

Para se comunicar com uma aplicação, a aplicação remetente precisa conhecer:

- O endereço IP da máquina de destino.
- O número da porta dentro desta máquina, na qual a aplicação de destino está associada.

Cada segmento carrega:

- O número de porta da máquina-destino para onde a mensagem deve ser enviada;
- O número de porta da máquina origem para onde as respostas devem ser endereçadas.

Segue a tabela 1, com algumas portas normalmente usadas na internet :

![[Screenshot_20220202_221240.png]]

**Protocolo UDP**

O protocolo UDP (User Datagram Protocol) tem como principal característica fornecer um serviço de entrega não confiável aos protocolos de aplicação. Outras características que merecem destaque para esse protocolo:

- Protocolo não orientado a conexão.
- Transferência não confiável de dados, isto é, as mensagens podem se perder e chegar fora de ordem.
- Não possui controle de fluxo.
- As aplicações que usam UDP devem fornecer serviço de entrega confiável.
- A figura 01 a seguir ilustra como é a formatação do cabeçalho UDP. Observe, caro aluno, que os campos de controle são bastante reduzidos.

![[Untitled 81.png|Untitled 81.png]]

- Na figura 02, segue a ilustração do processo de encapsulamento do protocolo UDP.

![[Untitled 1 45.png|Untitled 1 45.png]]

**Protocolo TCP**

O protocolo TCP (Transfer Control Protocol) tem como principal característica fornecer um serviço de entrega confiável de dados aos programas de aplicação. Outras características que merecem destaque para esse protocolo são:

- Protocolo orientado a conexão.
- Transferência confiável de dados.
- Transferência orientada a cadeia (stream) de bytes.
- Sequencialização.
- Controle de fluxo (janela deslizante).
- Multiplexação.
- Transmissão full-duplex.
- Termina conexão num sentido.

**Funcionamento TCP**

- Protocolo orientado a conexão: antes de efetuar a transmissão de dados, o aplicativo deve solicitar o estabelecimento de uma conexão com o outro aplicativo.
- Transferência confiável de dados: o protocolo TCP usa números de sequência e reconhecimento positivo com retransmissão para entrega confiável de dados. Números de sequência são usados para determinar a ordem dos dados que chegam e para detectar pacotes que estão faltando. O reconhecimento positivo com retransmissão exige que o receptor envie uma mensagem de reconhecimento ao remetente sempre que recebe um dado.
- Transferência orientada a cadeia (stream) de bytes: protocolo orientado a stream de bytes são aqueles projetados para enviar bytes individuais, e não blocos, frames ou datagramas.
- Sequencialização: cada byte possui um número sequencial, o qual pula conforme a quantidade de bytes existentes dentro dos pacotes. O TCP põe na ordem correta os segmentos que chegam fora de ordem e descarta os duplicados, bem como reconhece apenas o maior número contíguo dos segmentos recebidos sem erro.
- Controle de fluxo: o TCP efetua o controle de fluxo enviando um valor de "janela" ao transmissor, o qual envia o número especificado de bytes dentro dessa janela, sem esperar pelos reconhecimentos destes. A janela desliza à medida que chegam os reconhecimentos. Quando essa janela é fechada (janela = 0), o transmissor para de enviar os dados.
- Multiplexação: o TCP permite multiplexar várias sessões de usuários dentro de um único host. Esse mecanismo é baseado em portas e sockets.
- Transmissão full-duplex: fornece transmissão simultânea nos dois sentidos.
- Termina conexão num sentido: permite encerrar (fechar) a conexão assegurando que todos os dados foram reconhecidos antes de remover a conexão.

O TCP define um ponto final da internet por meio do par endereço IP, número de porta. Cada par é único na internet e um par de pontos finais define uma conexão. Como o TCP identifica uma conexão por um par de pontos finais, uma porta TCP pode ser compartilhada por múltiplas conexões.

Segmento é a unidade de transferência de dados trocada entre estações usando protocolo TCP. Segmentos são usados para:

- Estabelecer conexões.
- Transferir dados.
- Enviar reconhecimentos.
- Dar aviso do tamanho da janela.
- Fechar conexões.

Segue a figura 3, ilustrando o cabeçalho TCP :

![[Untitled 2 35.png|Untitled 2 35.png]]

**Evidenciando um tráfego**

Do ponto de vista da rede, o conceito de qualidade de serviço é caracterizado pela capacidade de tratar de forma diferenciada fluxos ou classes de tráfego e providenciar diferentes níveis de garantia de entrega dos dados (largura de banda, atraso, perdas) de forma consistente e previsível. Deve ser possível medir e quantificar o comportamento de uma rede de forma objetiva com base num conjunto de parâmetros de desempenho.

A qualidade de um serviço é suportada em uma rede quando dispõe de um conjunto de mecanismos que lhe permita satisfazer diferentes requisitos de tráfego. Os parâmetros de QoS (Quality of service – Qualidade de serviços) devem ser observáveis, mensuráveis e controláveis. Com isso, é possível classificar as garantias de QoS de várias maneiras, inclusive, fazendo pequenas comparações entre elas. Vejamos algumas delas:

**Absolutas X relativas**

Absolutas: as garantias dadas a uma classe são expressas de uma maneira que é independente das garantias oferecidas a outras classes.

Relativas: as garantias dadas a uma classe são expressas em termos relativos, por exemplo: uma classe recebe melhor serviço que outra(s) classe(s) do ponto de vista de um ou mais parâmetros de QoS.

**Quantitativas X qualitativas**

Quantitativas: as garantias quantitativas são expressas em termos numéricos, de forma determinística ou estatística.

Qualitativas: as garantias qualitativas são expressas de forma imprecisa (garantias vagas – _loose guarantees_), por exemplo: atraso pequeno, taxa de perdas reduzida, melhor que _best effort._

**Determinísticas X estatísticas**

Determinísticas: garantias quantitativas expressas sob a forma de limites precisos (garantias fortes – hard guarantees).

Estatísticas: garantias quantitativas expressas em termos estatísticos (garantias brandas – soft guarantees).

> [!info]  
>  
> [https://paginas.fe.up.pt/~jruela/Apontamentos/QoS_intro_v0910_RBL_2slides.pdf](https://paginas.fe.up.pt/~jruela/Apontamentos/QoS_intro_v0910_RBL_2slides.pdf)