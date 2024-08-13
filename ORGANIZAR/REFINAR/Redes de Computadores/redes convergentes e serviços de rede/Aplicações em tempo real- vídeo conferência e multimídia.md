### Introdução

O protocolo de transporte mais utilizado para aplicações é o TCP. Este tem mostrado o seu valor ao longo do tempo, porém, para aplicações em tempo real, o TCP não possui as características desejadas. No caso de aplicações distribuídas em tempo real, ou seja, as máquinas envolvidas geram um fluxo de dados a bit constante, e um ou mais destinos devem receber esses dados e passar as suas aplicações a essas mesmas taxas constantes.

Exemplos desses tipos de aplicação incluem conferência de voz e vídeo, distribuição de vídeo ao vivo (ou seja, não para gravação, mas para visualização imediata), áreas de trabalho compartilhadas, diagnóstico médico a distância, telefonia, sistema de controle e comando, simulações interativas distribuídas, jogos e monitoração em tempo real.

Outro protocolo de transporte largamente usado é o UDP, mas da mesma forma que o TCP, não provê informações de temporização. Só o UDP também não provê todas as ferramentas de propósito geral para as aplicações de tempo real.

Assim o IETF definiu um protocolo chamado RTP (Real Time Transport Protocol), para o transporte da aplicação e um protocolo chamado RTCP (Real Time Control Protocol) para o controle do RTP.

### Funcionamento do RTP

À medida que o rádio da internet, a telefonia da internet, a música por demanda, a videoconferência, o vídeo sob demanda e outras aplicações de multimídia se tornaram mais comuns, as pessoas descobriram que cada aplicação estava reinventando aproximadamente o mesmo protocolo de transporte em tempo real. Aos poucos, ficou claro que seria uma boa ideia ter um protocolo de transporte

de tempo real genérico para várias aplicações. Desse modo, foi criado o RTP (Real-time Transport Protocol). Ele é descrito na RFC 1889 e agora está em uso difundido.

No início da criação do RTP, decidiu-se que ele deveria ser inserido no espaço do usuário e, desse modo, ser (normalmente) executado sobre o UDP. A aplicação de multimídia consiste em vários fluxos de áudio, vídeo, texto e possivelmente outros fluxos. Esses fluxos são armazenados na biblioteca RTP, que se encontra no espaço do usuário, juntamente à aplicação. Essa biblioteca efetua a multiplexação dos fluxos e os codifica em pacotes RTP, que são então colocados em um soquete.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298944/18875.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298944/18875.png)

RTP no modelo OSI

Na outra extremidade do soquete (no núcleo do sistema operacional), os pacotes UDP são gerados e incorporados a pacotes IP. Se o computador estiver em uma rede Ethernet, os pacotes IP serão inseridos em quadros Ethernet para transmissão.

Como consequência dessa estrutura, é um pouco difícil dizer em que camada o RTP está. Como ele funciona no espaço do usuário e está vinculado ao programa aplicativo, certamente parece ser um protocolo de aplicação. Por outro lado, ele é um protocolo genérico e independente das aplicações que apenas fornecem recursos de transporte, e assim também é semelhante a um protocolo de transporte. Talvez a melhor descrição do RTP seja como um protocolo de transporte implementado na camada de aplicação.

A função básica do RTP é multiplexar diversos fluxos de dados de tempo real sobre um único fluxo de pacotes UDP. O fluxo UDP pode ser enviado a um único destino (unidifusão) ou a vários destinos (multidifusão). Como o RTP utiliza simplesmente o UDP normal, seus pacotes não são tratados de maneira especial pelos roteadores, a menos que alguns recursos de qualidade de serviço normais do IP estejam ativos. Em particular, não há nenhuma garantia especial sobre entrega, flutuação etc...

Cada pacote enviado em um fluxo RTP recebe um número, uma unidade maior que seu predecessor. Essa numeração permite ao destino descobrir se algum pacote está faltando. Se um pacote for omitido, a melhor ação que o destino deve executar é fazer a aproximação do valor que falta por interpolação. A retransmissão não é uma opção prática, pois o pacote retransmitido provavelmente chegaria tarde demais para ser útil. Como consequência, o RTP não tem nenhum controle de fluxo, nenhum controle de erros, nenhuma confirmação e nenhum mecanismo para solicitar retransmissões.

Cada carga útil do RTP pode conter várias amostras, e elas podem ser codificadas de qualquer forma desejada pela aplicação. Para permitir a interoperação, o RTP define vários perfis (por exemplo, um único fluxo de áudio) e, para cada perfil, podem ser permitidos vários formatos de codificação. Por exemplo, um único fluxo de áudio pode ser codificado como amostras PCM de 8 bits a 8 kHz, codificação delta, codificação profética, codificação GSM, MP3 e assim por diante.

O RTP fornece um campo de cabeçalho em que a origem pode especificar a codificação, mas que não tem nenhum outro envolvimento na maneira de realizar a codificação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258946/14800.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258946/14800.jpg)

Inicio do cabeçalho RTP

Outro recurso de que muitas aplicações em tempo real necessitam é a marcação com timbre de hora. Aqui, a ideia é permitir que a origem associe um timbre de hora com a primeira amostra em cada pacote. Os timbres de hora são relativos ao início do fluxo, e assim somente as diferenças entre os timbres de hora são significativas. Os valores absolutos não têm nenhum significado. Esse mecanismo permite ao destino realizar alguma bufferização e reproduzir cada amostra depois de um número correto de milissegundos, contados desde o início do fluxo, independente de quando chegou o pacote contendo a amostra. O uso de timbres de hora não apenas reduz os efeitos da flutuação, mas também permite a sincronização de vários fluxos. Por exemplo, um programa de televisão digital poderia ter um fluxo de vídeo e dois fluxos de áudio. Os dois fluxos de áudio poderiam ser para difusões estereofônicas ou para tratamento de filmes com uma trilha sonora no idioma original e outra dublada no idioma local, dando ao espectador a possibilidade de escolher.

Cada fluxo vem de um dispositivo físico diferente, mas, se eles forem marcados com um timbre de hora baseado em um único contador, poderão ser reproduzidos de modo sincronizado, mesmo que os fluxos sejam transmitidos de maneira um tanto errática.

### O protocolo RTCP

O protocolo RTP tem um controle, chamado RTCP (Real-time Transport Control Protocol). Ele cuida do feedback, da sincronização e da interface do usuário, mas não transporta quaisquer dados. A primeira função pode ser usada para fornecer feedback sobre retardo, flutuação, largura de banda, congestionamento e outras propriedades de rede para as origens.

Essas informações podem ser usadas pelo processo de codificação para aumentar a taxa de dados (e oferecer melhor qualidade) quando a rede estiver funcionamento bem e para reduzir a taxa de dados quando houver problemas na rede. Fornecendo feedback contínuo, os algoritmos de codificação podem ser adaptados continuamente para oferecer a melhor qualidade possível sob as circunstâncias atuais.

Por exemplo, se a largura de banda aumentar ou diminuir durante a transmissão, a codificação pode passar de MP3 para PCM de 8 bits e para codificação delta, conforme necessário. O campo de tipo ‘tipo’, no cabeçalho RTP, como mostra a figura no final deste texto, é usado para informar ao destino qual algoritmo de codificação será empregado no pacote atual, tornando possível variar o algoritmo de acordo com a demanda.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298945/18877.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/9/298945/18877.png)

RTPC - Controle de Mensagens RTP

O RTCP também lida com a sincronização entre fluxos. O problema é que diferentes fluxos podem utilizar clocks distintos, com granularidades e taxas de flutuação diferentes. O RTCP pode ser usado para manter esses elementos sincronizados.