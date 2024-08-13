**Introdução**

Para acompanhar e entender os princípios da compressão,  temos que estudar as técnicas de compressão que são essenciais para a área de comunicação e entretenimento e as aplicações nos sistemas multimídias, as razões são simples, ainda é grande demanda para armazenamento dos dados multimídias, e muitas vezes a velocidade é lenta nos dispositivos de armazenamento mesmo os mais modernos, sua transmissão ocupa uma largura de banda de rede limitada que é compartilhada por muitos outros dispositivos.

Caso estes requisitos de armazenamento não fossem utilizados para compressão, uma aplicação multimídia típica o armazenamento em disco seria  algo próximo a meia hora de vídeo igual a 50 GB, 2000 imagens ocuparia 15 GB e 40 minutos de  áudio em som estéreo ocuparia 400 mega.

**Abaixo um exemplo de Compressão de imagem**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/9/265933/13873.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/5/9/265933/13873.png)

1ª imagem JPEG com menor taxa de compressão - 2ª a mesma imagem, mais com maior compressão .

A taxa de transferência de dados entre dispositivos seria insuficientes, um dispositivo de armazenamento deveria ter uma taxa de aproximadamente de 30MB/s para apresentar um vídeo 620x560, 24bits por pixel a 30 (Frames por segundo ) fps, a tecnologia de CD-ROM de hoje fornece uma taxa de transferência de até 7,8MB/s (52x).

Para tanto, se faz necessário a compactação para armazenar, apresentar e transmitir dados multimídias utilizando as técnicas de compressão modernas que reduzam os requisitos de armazenamento, os requisito de largura de banda da rede e a velocidade de transferência de dados entre dispositivo.

### Redundância.

A redundância de áudio digital (voz) mesmo sem percebermos nos comunicamos o tempo todo, mas  entre uma frase e outra ou para podermos respirar mantemos silencio, a técnica de compressão atua na remoção do silêncio, entre uma frase e outra há instantes de silêncio.

Para a imagem digital existe algo similar a técnica de compressão a Redundância Espacial e ela pode ser removida usando codificação preditiva ou outras técnicas, e em  se tratando de vídeo é bem parecido pois o vídeo é uma sequência de imagens dentro de um tempo, também possui a redundância espacial acrescida de redundância temporal utiliza-se a mesma técnica.

A classificação das técnicas e desempenho da compressão está relacionada como percebemos as informações, pois propriedade da percepção humana através dos órgãos dos sentidos não é tão apurada assim, pois aceitamos erros de informações ou perdas sem afetar a qualidade da informação decodificada em nosso cérebro, nossa visão não necessita reconhecer exatamente a informação original como foi criada, somos enganados pela nossa visão para aceitarmos o que vemos, com a rara exceção de dados alfanuméricos, pois algumas informações são importantes para a percepção humana e as técnicas de compressão podem remover informações desnecessárias ou que não irão mudar a percepção da informação, é como se nosso cérebro preenchesse as lacunas vazias.Assim podemos classifica-las em:

Compressão sem perdas a codificação por entropia são dados que podem ser reconstruídos exatamente como o construído  originalmente. Para tanto faz-se a utilização de programas para comprimir os documentos legais ou médicos, essa técnica trata as cadeias de bits sem levar em conta seu significado exploram apenas estatística de dados (redundância de dados) com baixa taxa de compressão, como ex. run-length, Huffman e Lempel Ziv.

Compressão com perdas aceitáveis, essa técnica utilizada em dados multimídias onde erros e perdas são aceitáveis, levando-se em consideração a semântica dos dados, removendo dados irrelevantes e compactando o dado original considerando como parâmetro a percepção humana, neste caso existe uma alta taxa de compressão.

Codificações híbridas, como o nome sugere ela combina técnicas com perdas e sem perdas, técnicas que agrupadas formam uma nova técnica de codificação, onde temos uma alta taxa de compressão, descarta dados irrelevantes para a percepção (com perdas) e elimina a redundância (sem perdas).

### Resumidamente ....

Para a taxa de compressão, temos, tamanho do dado original e o tamanho do dado após compressão, para a técnica sem perda, quanto maior a taxa melhor é a técnica e para a técnica com perda, quanto maior a taxa pior é técnica a qualidade da mídia a ser reconstituída.

SNR (signal-to-noise ratio ou RSR em português)

Medida em SNR (razão sinal/ruídos) quanto maior a SNR melhor é a qualidade, normalmente usado em videoconferências é importante a compressão e descompressão acontecer em tempo-real, a compressão onde ocorre a captura e apresentação das informações devem ser simultâneas ou na pior das hipóteses que se tenha a velocidade de compressão não mas a descompressão é importante ser rápida.

A codificação por Entropia ou Run-length ou sem perda é um método aplicado em formatos de padrões como, PCX, BMP, (RLE) e Photoshop, nesse caso a parte das informações dos dados de imagens, áudios e vídeos podem ser compactados através da supressão de sequências de símbolos que se repetem como por exemplo: AEEEEIMMG1223 assim as sequências idênticas são substituídas por um símbolo especial, com o número de ocorrências e os símbolos repetidos:. A!4EIMMG1223

A compressão sem perda, codificação RLE depende do dado de entrada e essa técnica deve ser utilizada para sequências maiores do que 4 repetições. A sequencia A!4EIMMG1223 é o máximo de compactação, quando esse símbolo ocorre “!” é acontece no dado de entrada, ou deve ser substituído por dois símbolos idênticos desta forma A!BCCCCD na saída: A!!B!4CD.

Assim podemos ainda criar um algoritmo que pode ser otimizado e substituindo em sequências maiores que um byte, o que requer que o tamanho da sequência seja codificado ou possa utilizar um caractere especial de fim, quando  houver grande quantidade de grupos de símbolos como no exemplo:

Entrada: ABCDEFGEFGEFGEFGEFGMNO

Saída: ABCD!5EFG$MNO

Compressão sem perda: Codificação RLE

Essa técnica é usada em imagens bitmap que possuem espaços envolvendo só uma cor ou em imagens geradas pelo computador agrupadas de forma definida geograficamente.

**EXERCÍCIO RESOLVIDO**

Com base no aprendizado, vamos compactar a sequência de símbolos apresentadas a seguir sabendo que cada número símbolo corresponde a cores associadas em uma determinada imagem.

1) 36583333333455555558764222227877777774444444231

R.  3658!734!758764!5278!77!74231

2) 54324324324324324328888888676767676722222828282828

R. 5!6432$!78!567$!42!528$ ou 5!6432$!78!567$!52!482$8

Existem outras formas de compressão sem perda é a codificação de Huffman onde a codificação é estatística, ao atribuir menos bits a símbolos que aparecem mais frequentemente e mais bits a símbolos que aparecem menos podemos por exemplo em um arquivo de 1.000 caracteres: e, t, x, z estimar a probabilidades: e=0.8; t=0.16; x=00.2; z=00.2 assim é necessário 2 bits para representar cada um dos 4 símbolos exemplo:

e=00; t=01; x=10; z=11 o arquivo terá o tamanho de 2*1.000 = 2.000bits.

A codificação de Huffman é usada uma quantidade de bits diferentes para representar estes mesmos símbolos de acordo com a probabilidade:

Ex:. e=1; t=01; x=001; z=000

ficando dessa forma, 1.000  (1*0.8+2*0.16+3*0.02+3*0.02)  = 1.240bits ou apesar de x e z terem sido representados por mais bits, o número será menor pois eles ocorrem menos vezes. A ideia aqui é criar uma arvore binária.