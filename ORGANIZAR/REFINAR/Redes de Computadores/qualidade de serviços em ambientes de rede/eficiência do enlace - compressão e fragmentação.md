**A camada de enlace de dados**

A principal tarefa da camada de enlace de dados é transformar um canal de transmissão bruta em uma linha que pareça livre de erros de transmissão não detectados para a camada de rede. Para executar essa tarefa, a camada de enlace de dados faz com que o transmissor divida os dados de entrada em quadros de dados (que, em geral, têm algumas centenas ou alguns milhares de bytes), e transmita-os sequencialmente. Se o serviço for confiável, o receptor confirmará a recepção correta de cada quadro, enviando de volta um quadro de confirmação.

Outra questão que surge na camada de enlace de dados (e na maioria das camadas mais altas) é como impedir que um transmissor rápido envie uma quantidade excessiva de dados a um receptor lento. Com frequência, é necessário algum mecanismo que regule o tráfego para informar ao transmissor quanto de espaço o buffer do receptor tem no momento. Muitas vezes, esse controle de fluxo e o tratamento de erros estão integrados.

Como pode ser observado na figura 01 a seguir, a camada de enlace no modelo de referência OSI é responsável por tratar os quadros dentro de uma transmissão fim a fim.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119246/a11i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119246/a11i01_quasar80_100.jpg)

Fonte: PROGRAMA CISCO NETWORK ACADEMY. CCNA módulo 01. Conceitos básicos de redes. USA: Cisco Press, 2013.

Na camada de enlace temos também o modelo ETHERNET, que opera fazendo uma divisão em 2 (duas) subcamadas dentro da camada de enlace. Essas são conhecidas como LLC (_**Logical Lynk Control**_) e MAC (_**Media Access Control**_). As subcamadas de enlace de dados contribuem significativamente para a compatibilidade da tecnologia e a comunicação entre computadores. A subcamada MAC trata dos componentes físicos que serão usados para comunicar as informações, enquanto que a LLC permanece relativamente independente do equipamento físico que será usado para o processo de comunicação.

**Quadros da camada 2**

Os fluxos de bits codificados (dados) em meios físicos representam uma grande realização tecnológica, mas eles, sozinhos, não são suficientes para fazer com que a comunicação ocorra. O enquadramento ajuda a obter as informações essenciais que não poderiam, de outra forma, ser obtidas apenas com fluxos de bit codificados.

Exemplos dessas informações são:

- Quais computadores estão se comunicando entre si.
- Quando a comunicação entre computadores individuais começa e quando termina.
- Providencia um método para a detecção de erros que ocorreram durante a comunicação.
- De quem é a vez de "falar" em uma "conversa" entre computadores.
- Enquadramento é o processo de encapsulamento da camada 2. Um quadro é uma unidade de dados de protocolo desta camada.
- Todos os quadros contêm informações de identificação, como o nome do nó de origem (endereço MAC) e o nome do nó de destino (endereço MAC).

**Compressão**

As ferramentas de compressão reduzem a quantidade de largura de banda necessária para enviar todos os pacotes, porém o processo de compressão adiciona alguns atrasos por pacote e consomem alguns ciclos a mais da CPU.

Um exemplo é possível ser observado na figura 02 a seguir: um simples efeito de compressão, assumindo a compressão conhecida como 2:1. Sem essa compressão, um link de 80kbps oferecido com somente 64 kbps disponível para a conexão fim a fim irá formar uma fila, e consequentemente, os pacotes do fim dessa fila se perderão. Com a compressão conhecida como proporção 2:1, o link de 80Kbps será exigido em apenas 40kbps para trabalhar em torno deste, efetivamente a metade do link disponível.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119250/a11i02_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119250/a11i02_quasar80_100.jpg)

Fonte: ODOM, W.; CAVANAUGH, M. Cisco QOS Exam Certification Guide (IP Telephony Self-Study), 2 ed. USA: Cisco Press, 2004.

Em resumo, a compressão pode comprimir ambos os payloads ou headers, reduzindo o número total de bits requeridos para transmissão de dados. A compressão pega os pacotes ou pacotes de cabeçalhos (headers) e comprime os dados. A compressão reduz os atrasos de serialização devido ao número de bits usados para envio dos pacotes ser reduzido, entretanto, atrasos podem ser inseridos porque o tempo de processamento requerido para comprimir e descomprimi-lo estão presentes.

Para que você, caro aluno, possa entender um pouco melhor do que se trata uma compressão de _**payload**_ e uma compressão de header, veja a figura 03:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119252/a11i03_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119252/a11i03_quasar80_100.jpg)

Fonte: ODOM, W.; CAVANAUGH, M. J. Cisco QOS exam certification guide, second edition. Cisco Press, Indianápolis, USA, 2012.

Ferramentas de compressão diferem enquanto a CPU é carregada e quais partes de um frame sofrerá compressão. Baseado no carregamento da CPU e o que de fato foi utilizado compressão, você poderá tomar uma boa decisão sobre onde usar cada ferramenta.

**Fragmentação**

O tempo requerido para a serialização de um pacote no link é uma função ligada à velocidade do link e também ao tamanho do pacote. Quando um roteador decide iniciar o envio do primeiro bit de um pacote, ele continua até que todo o pacote seja transmitido. Entretanto, se um pacote sensível ao atraso se apresenta logo após um pacote grande já estar com sua transmissão iniciada na interface, ele terá que esperar até que o pacote maior seja todo transmitido.

Por exemplo: vamos supor que dois pacotes chegam ao roteador R1. O primeiro tem 1500 bytes e o segundo tem 200 bytes. O pacote menor é sensível ao atraso. Devido justamente pelo pacote 2 chegar ao roteador depois que o primeiro bit do pacote 1 já iniciou sua transmissão, o pacote 2 terá que esperar 214 milissegundos para se serializar (iniciar o envio) pelo link. Se o link estiver com a aplicação da fragmentação realizada pelo LFI (Link Fragmentation and Interleaving), o pacote 1 poderá sofrer uma quebra em três pacotes menores, cada um com 500 bytes, e o pacote 2 poderá ser inserido e enviado pelo link logo após o primeiro fragmento de 500 bytes terminar sua transmissão, ou seja, não precisará mais esperar os 214 milisegundos para ser inserido no link. A figura 4 exemplifica o funcionamento do LFI:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119254/a11i04_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119254/a11i04_quasar80_100.jpg)