[![](https://ampli-images.s3.amazonaws.com/production/0e9d80d1-bcf1-4c89-924d-39cc2ef454c9/original)](https://ampli-images.s3.amazonaws.com/production/0e9d80d1-bcf1-4c89-924d-39cc2ef454c9/original)

Você já imaginou como toda a internet funciona? Já pensou que cada dispositivo conectado à internet possui um endereço único, dentro do domínio de sua rede, e que ele pode se comunicar com outro dispositivo localizado do outro lado do mundo? Pois bem, este sistema funciona graças ao protocolo IP e aos critérios de endereçamentos público e privado.

A seguir, desenvolveremos o conhecimento para que possamos realizar o endereçamento de nossas máquinas e nossas sub-redes.

De acordo com Stallings (2016), na maioria dos casos, uma rede local ou uma rede remota não é uma entidade isolada, e necessita de um sistema que possa fazer com que tenha acesso a outras redes.

Nesta aula, trabalharemos o conceito e a aplicação do protocolo IPv4 (Internet Protocol version 4) para a configuração de computadores, impressoras e nós de rede com o famoso endereço IP. A versão IPv6 (Internet Protocol version 6) também será abordada, porém na aula 2 desta unidade.

Conforme relata Forouzan (2010), o IPv4 é um protocolo de datagramas sem conexão e não confiável, ou seja, um serviço de entregas chamado de _best-effort_, o que significa que o IPv4 não possui mecanismos de controle de erros ou de fluxo, com exceção da detecção de erros no cabeçalho. Isto nos remete a relembrar que um protocolo adicional de camada de transporte deverá assumir a responsabilidade de realizar a conexão e a entrega confiável dos dados, tarefa realizada pelo protocolo TCP (_Transmission Control Protocol_). As definições técnicas sobre o protocolo IP estão formalizadas na RFC 791 da IETF.

**Observação**: IETF (_Internet Engineering Task Force_) e RFC (_Request of Comments_). A RFC 791 define as especificações e questões técnicas a respeito do protocolo IP.

[![](https://ampli-images.s3.amazonaws.com/production/a620e89c-7c8b-435c-a2af-dd79e707bbde/original)](https://ampli-images.s3.amazonaws.com/production/a620e89c-7c8b-435c-a2af-dd79e707bbde/original)

Formato do datagrama IPv4. Fonte: Kurose e Ross (2013, p. 246).

A seguir, é apresentada uma breve descrição dos campos do datagrama IPv4.

- Versão: versão do protocolo IP (4 ou 6).
- Comprimento do cabeçalho: tamanho do cabeçalho.
- Tipo de serviço: prioridade do pacote.
- Comprimento do datagrama: tamanho total do pacote (datagrama), com cabeçalho e dados.
- Identificador de 16 bits: fragmento do pacote IP original.
- _Flag_: MF, usado para o deslocamento dos datagramas e sua reconstrução; DF, utilização para autorização de fragmentação.
- Deslocamento de fragmentação: ordem dos pacotes no processo de remontagem.
- Tempo de vida: TLL (_Time to Live_). Indica o “tempo de vida” que o pacote possui a cada salto pelos nós da rede.
- Protocolo da camada superior: repassa os dados para os protocolos das camadas superiores.
- Soma de verificação do cabeçalho: informa os erros no cabeçalho.
- Endereço IP de origem: endereço do remetente.
- Endereço IP de destino: endereço do receptor.
- Opções: implementações opcionais.
- Dados: dados a serem transmitidos.
- Observada a composição do fragmento IP na rede, refletiremos sobre como é feito o endereçamento de cada dispositivo conectado em uma rede de computadores.
- Por exemplo, no sistema telefônico, a composição de um número local é estruturada em um conjunto de números, em que parte do número identifica o país, outra parte a região, outra ainda a central telefônica e outra o número do assinante.
- Exemplo de número telefônico: 55 19 3555 0001
- 55: identifica um país.
- 19: identifica uma região.
- 3555: identifica a central telefônica.
- 0001: identifica o número do assinante (número hipotético).
- A composição do endereço IP também segue esta estrutura, em que parte do número identifica a rede que o dispositivo pertence e parte determina o endereço do próprio dispositivo.
- Exemplo de número IPv4: 192.168.5.114
- 192.168.5: identifica a rede ou sub-rede que o dispositivo pertence.
- 114: identifica o dispositivo dentro da rede em que ele pertence.

Kurose e Ross (2013) definem o IP como um endereço lógico, criado para que um dispositivo em rede possa se comunicar com outro dispositivo em rede. Trata-se de um endereço formado por 32 bits (ou 4 bytes), o que permite que sejam definidos 232 endereços de rede, ou seja, mais de 4 bilhões de endereços, o que pode parecer o suficiente para endereçar todos os dispositivos em rede, mas não é na verdade.

______

**💭Reflita**

O contexto atual de IoT (_Internet of Things_), ou Internet das Coisas, faz com que diversos dispositivos possam ser conectados a uma rede de computadores e à internet. Diamandis e Kotler (2018) sustentam que, no ano de 2020, já deve haver mais de 50 bilhões de dispositivos conectados em rede, e que em dez anos, ou seja, no ano de 2030, o número deverá chegar a 10 trilhões. Todos estes dispositivos precisarão de um endereço IP para seu funcionamento.

______

Um endereço IPv4 é um número binário, formado por quatro conjunto de números, chamados de octetos, que normalmente são representados por notação decimal. Um exemplo de endereços IP é: 192.168.0.15; outro exemplo é: 172.16.15.108; e outro ainda é: 200.204.0.10. Perceba que, se o endereço é formado por 4 bytes, cada 1 byte corresponde a 8 bits. Por exemplo, o endereço IP 200.241.120.25 tem o número decimal 200, equivalente aos 8 primeiros bits do endereço; 241 é o decimal do segundo conjunto de 8 bits; 120 é o terceiro; e 25, o quarto. Este número IP é a representação do número binário: 11000001.00100000.11011000.00001001. A figura abaixo apresenta um exemplo de endereço IPv4 dividido em octetos binários com as devidas representações.

[![](https://ampli-images.s3.amazonaws.com/production/e27b96bb-6f5d-4d19-ab78-4f036bbd2a23/original)](https://ampli-images.s3.amazonaws.com/production/e27b96bb-6f5d-4d19-ab78-4f036bbd2a23/original)

Formato do endereço IPv4. Fonte: elaborada pelo autor.

Um endereço IPv4 é dividido em duas categorias:

- **Pública**, que o identifica como endereço único atribuído e alocado definitivamente e globalmente único para um dispositivo na internet. Para obter um endereço desta categoria, é necessário solicitá-lo a uma instituição de registro de internet.
- **Privada**, na qual um endereço IPv4 deve estar definido dentro de um intervalo de endereços com números limitados a um conjunto de classes e/ou sub-redes que podem ser utilizados livremente em redes privadas, sem acesso direto à internet.

______

**➕****Saiba mais**

Os endereços IP dos _hosts_ de uma rede de computadores podem ser de natureza pública ou privada. Os endereços de natureza pública são atribuídos e controlados pela IANA (_Internet Assigned Numbers Authority_), organização responsável pela atribuição e pelo controle de endereços IPs no mundo. Já os endereços privados são atribuídos utilizando-se de faixas autorizadas dentro das classes de endereços IPs. Você está convidado a visitar o site da IANA. A entidade brasileira correspondente à IANA é a NIC.BR, que também pode ser visitada na internet.