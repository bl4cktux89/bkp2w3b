**Introdução**

Nas grandes redes, por exemplo, a internet, possuem um grande desafio para integrar diferentes tráfegos e prover serviços adequados para tratar tanto o tráfego de dados como o de tempo real, como voz e vídeo. O serviço tradicional é baseado no menor esforço, que se torna adequado para grande número de aplicações envolvendo transporte de dados, não tão sensíveis ao tempo. Porém a sensibilidade ao tempo (atrasos e variação de atrasos) é uma característica do transporte de voz e vídeo, e outros modelos de serviço tornam-se necessários para viabilizar esse tipo de tráfego.

Por essa razão, para garantir qualidade de serviço para um determinado tipo de tráfego, em redes convergentes, deve-se conhecer antes suas principais características que permitam desenvolver técnicas capazes de evidenciar e diferenciar o tráfego de modo a garantir maior prioridade na rede.

Assim, o IETF apresentou duas técnicas para aplicações em redes convergentes, baseadas em modelos de serviços: o modelo de Serviços Integrados (IntServ) e o modelo de Serviços Diferenciados (DiffServ). Cada um desses modelos possui características apropriadas a situações distintas, sendo a combinação de ambos o caminho para a obtenção da qualidade de serviço procurada.

O DiffServ possui em seu tráfego a divisão em classes de serviço e os recursos da rede passam a ser compartilhados dando um tratamento para cada uma dessas classes. Algumas características principais do _**Diffserv:**_

- Baseia-se em agregação de fluxos em classes de serviços (leia o RFC 2475).
- Possui a abordagem de marcação e classificação de pacotes.
- Os pacotes são marcados quando ingressam na rede.
- O campo do datagrama IP tem seu layout redefinido, especificando como é feito o encaminhamento de pacotes nos roteadores.

### Classes de serviços DiffServ

### Envio Expresso (RFC 2598)

- Também denominado de Premium Service ou EF PHB.
- Fornece o equivalente a uma linha privada virtual, com largura de banda fixa, entre dois hosts. Indicado para telefonia sobre IP, videoconferência e criação de VPNs.
- Oferece garantias absolutas de perda, atraso e jitter.
- Requer alguma forma de isolamento de tráfego entre as classes.
- Tráfego que não esteja de acordo com o perfil contratado é descartado.
- Tem implementação mais simples que o serviço garantido do IntServ.
- Os pacotes dessa classe são os primeiros a serem encaminhados, em qualquer situação. Há baixa probabilidade de descarte para o tráfego em conformidade com o perfil contratado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258994/14815.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258994/14815.jpg)

Arquitetura DiffServ

### Envio assegurado (RFC 2597)

- Também denominado de Assured Service ou AF PHB.
- Fornece um serviço melhor que o de melhor esforço, mas sem garantias rígidas de QoS.
- Não oferece limites superiores para o atraso e jitter.
- Tráfego é dividido em N classes, cada uma com M mínimo garantido de largura de banda e M níveis de precedência de descarte (atualmente, N=4, M=3).
- Serviço fornecido por uma classe independe do serviço das demais, sendo função dos recursos alocados àquela classe.
- Pacotes do serviço AF são os últimos a ser descartados em situações de congestionamento.

Outras características do princípio de funcionamento do DiffServ que valem a pena ressaltar a você, caro aluno:

- A qualidade de serviço na solução DiffServ é garantida por meio de mecanismos de priorização de pacotes na rede.
- DiffServ **não** utiliza qualquer tipo de mecanismo de reserva de recursos.
- Nessa solução, os pacotes são classificados, marcados e processados pelo rótulo _Differentiad Service Code Point_ – DSCP.
- Redução do nível de processamento dos roteadores com a definição de poucas "Classes de Serviços". É realizado nos roteadores BACKBONE, aliviando o trabalho dos roteadores intermediários.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/4/3/234365/4626.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/4/3/234365/4626.png)

Protocolos da Camada de transporte

### Real-Time Transport Protocol (RTP)

O protocolo RTP, é o principal protocolo utilizado pelos terminais, em conjunto com o RTCP, para o transporte fim-a-fim em tempo real de pacotes de mídia (Voz) através de redes de pacotes.

Cenários de aplicação do RTP:

- **Audioconferência multicast:** Técnica de entregar informações aos usuários um para vários ou vários para vários. Dispositivos como hubs, switches devem participar das trocas de informação. O desempenho do sistema inteiro depende do desempenho da rede.
- **Videoconferência:** Discussões em grupo ou de vários para vários como se estivessem no mesmo local. Os dados de áudio e vídeo são transportados separadamente em sessões RTP. A separação é necessária para permitir que cada participante da conferência receba apenas um tipo de mídia a sua escolha.
- **Tradutores:** O protocolo RTP suporta o uso de tradutores e mixers para modificar o pacote do fluxo RTP. Tradutores são usados para mudar o tipo de payload (formato do arquivo). Se o usuário mantiver uma videoconferência em MPEG com 1.5Mbit/s e o outro participante está conectado a 1Mbit/s talvez essa largura de banda seja insuficiente para a transmissão em tempo real sendo necessária a troca do formato de vídeo para outro de tamanho menor (h.261, com 256Kbit/s).
- **Mixers:** A função do mixer e ressincronizar pacotes de áudio para reconstruir seqüências que foram enviadas, ou seja, converter várias rajadas de dados em uma só rajada e codificar os dados com um padrão mais apropriado a baixas velocidades.

O RTP não reserva recursos de rede e nem garante qualidade de serviço para tempo real. O transporte dos dados é incrementado através do RTCP (protocolo de controle) que monitora a entrega dos dados e provê funções mínimas de controle e identificação. No caso das redes IP este protocolo faz uso dos pacotes UDP, que estabelecem comunicações sem conexão.

Real-Time Transport Control Protocol (RTCP)

O protocolo RTCP, do IETF, é baseado no envio periódico de pacotes de controle a todos os participantes da conexão (chamada), usando o mesmo mecanismo de distribuição dos pacotes de mídia (Voz). Desta forma, com um controle mínimo é feita a transmissão de dados em tempo real usando o suporte dos pacotes UDP (para Voz e controle) da rede IP.

Session Initiation Protocol (SIP)

O protocolo SIP, estabelece o padrão de sinalização e controle para chamadas entre terminais que não utilizam o padrão H.323, e possui os seus próprios mecanismos de segurança e confiabilidade.

Estabelece recomendações para serviços adicionais tais como transferência e redirecionamento de chamadas, identificação de chamadas (chamado e chamador), autenticação de chamadas (chamado e chamador), conferência, entre outros.

Algumas características do SIP:

- Estabelecimento, modificação e encerramento de chamadas e sessões multimídia além de poder convidar pessoas e máquinas como servidores de armazenamento.
- Utiliza endereçamento através de e-mail, podendo localizar o estilo definido pelo usuário.
- O proxy SIP (servidor SIP) pode ramificar o INVITE (convite) para múltiplos endereços, envolvendo múltiplos usuários. Desta forma há uma redução e economia no tempo de estabelecimento de uma chamada.
- No caso do SIP sobre o protocolo UDP, o esquema de transmissão é usado para otimizar a confiabilidade do protocolo.
- Suporta tanto sessão multicast como unicast.
- Pode iniciar chamadas usando os recursos do MCU (mutipoint control unit).
- Gateways de telefonia sobre internet que conectam RPTC e podem usar o SIP para estabelecer chamadas entre elas.

Sua utilização é similar ao conjunto H.323, embora utilize como suporte para as suas mensagens os pacotes UDP da rede IP.

Fonte: TELECO, Disponível em: Acesso em: 14.Mai.2016

(TELECO )

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298944/18875.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298944/18875.png)

RTP no modelo OSI

**Para garantir a qualidade e a transmissão do fluxo de dados, voz e imagens algumas técnicas são empregadas, vamos destacá-las nessa citação do material divulgado pelo site TELECO, vale a pena ler ...**

Para que se tenha uma boa qualidade da voz faz-se necessário mecanismos para o controle dessa qualidade. Os principais problemas são:

- Atraso fim-a-fim
- Variação do atraso
- Perdas e erros em pacotes

As redes de VoIP usam cinco pilares básicos para conservar a largura de banda e melhorar a prioridade, que são:

- _**Prioritization**_: os pacotes de dados são divididos em segmentos pequenos, permitindo que os pacotes de voz de uma prioridade mais elevada sejam emitidos primeiro. Em cada _gateway_ , a fila da voz é verificada, e o tráfego da Internet é emitido somente quando a fila da voz está vazia. O protocolo que foi usado inicialmente para reservar recursos da rede foi RSVP (protocolo do reserva de recurso). RSVP requer uma aplicação para pedir uma reserva para recursos da rede, e pode negar a admissão se os recursos forem insuficientes.
- _**Jitter**_: são as irregularidades de intervalos de tempos entre a chegada da voz, ou seja, é a variação no intervalo entre as chegadas de pacotes introduzidos pelo comportamento aleatório na rede. Para evitar os efeitos do _jitter_ , o equipamento deve segurar os pacotes que chegam por um tempo especificado, dando tempo subseqüente dos pacotes chegarem e caber ainda em uma compressão natural da voz. Um método para controlar esse problema é adicionar um buffer na recepção que acrescenta um atraso determinado, de tal forma que o atraso total experimentado pelo pacote, incluindo o atraso extra gerado pelo buffer seja igual ao máximo atraso possível na rede.
- _**Voice Compression**_: permite que a rede de _switching_ de pacote seja carregada mais eficazmente em uma combinação da voz e dos dados sem qualidade, comprometendo a qualidade da voz. Entretanto, o maior sinal de voz é comprimido a menor qualidade.
- _**Silence Compression**_: em uma conversação por telefone, somente aproximadamente 50% das conexões são usadas em todo o tempo. Isto é porque, normalmente, somente uma pessoa fala quando a outra pessoa escuta. Os pacotes da voz não são emitidos durante pausas de conversação. A banda é usada para outra voz ou para transmissão de dados. Na aplicação de técnicas de detecção e supressão de silêncio nas transmissões de VoIP o objetivo não é conseguir aumentar a banda de transmissão ou romper os seus limites, mas sim, fazer com que se aproveite melhor o espaço existente na mesma.
- _**Echo Cancellation**_: melhorar a qualidade da transmissão de voz para eliminar o eco que resulta na reflexão de sinal da telefonia atrás de quem está fazendo a chamada. Um cancelador de eco é um componente de um _gateway_ de voz que reduz o nível de eco retornado através do caminho do receptor (vindo do _gateway_ de fora para o circuito) para o caminho do transmissor (vindo do circuito para o _gateway_ ).

Os principais mecanismos que fazem o controle da qualidade da voz são:

- _**FEC (Forward Error Correction)**_: trabalham adicionando dados extras ao fluxo original para que o receptor possa recuperar dados perdidos na transmissão.
- _**CodificadoresBufferização**_ : Procura eliminar o efeito causado pelo _jitter_ na transmissão.
- _**Intercalação**_: Redução do efeito de perdas. Nessa técnica, as unidades de mídia são ressequencializadas antes de serem transmitidas, separando-se em unidades adjacentes para garantir que estarão distantes dentro do fluxo de pacotes, dispersando o efeito da perda. Essa técnica é utilizada quando o tamanho da unidade da mídia é menor do que o pacote de dados.
- _**Retransmissão de pacotes**_: A retransmissão dos pacotes é utilizada somente quando há uma rede com disponibilidade elevada.
- _**Ressequenciamento**_: Procura evitar que segmentos contíguos de voz sejam perdidos devido ao congestionamento da rede.
- _**Inserção**_: Preenchimento do tempo quando os pacotes são perdidos (com ruídos gaussianos ou com "silêncio").
- _**Interpolação**_: Desempenho superior aos anteriores, porém, requer mais processamento pelo fato de basear-se no uso da similaridade de padrão entre pacotes e interpolação de unidades de dados, para obter um pacote semelhante ao perdido.
- _**Regeneração**_: São técnicas dependentes de _Codecs_ , valendo-se de conhecer o algoritmo de compressão da voz para derivar parâmetros de Codec, sintetizando o áudio de um pacote perdido.

A codificação da voz é feita a partir de equipamentos denominados CODEC (coder/decoder), este equipamento além de converter sons analógicos em digitais e vice-versa, também efetua compressão e descompressão do sinal digital.

Os codificadores classificam-se em:

- **Codificadores de forma de onda** : codifica o sinal considerando apenas a sua forma de onda, desprezando qualquer outra característica. Possuem uma qualidade muito boa, mas uma taxa de transmissão muito alta.
- **Codificadores de fonte ou paramétricos** : codifica o sinal considerando apenas a fonte como este foi gerado. No caso da voz, a fonte é o próprio trato vocal da pessoa que fala. Possuem uma qualidade muito ruim, mas uma taxa de transmissão muito baixa.

Fonte: TELECO.Disponível emAcesso em 14.Mai.2016