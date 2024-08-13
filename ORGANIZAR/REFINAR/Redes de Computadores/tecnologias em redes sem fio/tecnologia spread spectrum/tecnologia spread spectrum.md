### Objetivo:

Neste tópico iremos estudar a tecnologia _**Spread Spectrum**_ que é a técnica utilizada nos rádio _**wireless**_ e nas comunicações digitais transmitidas por ondas eletromagnéticas.

Também aprenderemos as diferentes técnicas de modulação empregada pelo _**Spread Spectrum**_ e como estes procedimentos modificam tanto a velocidade de transmissão como a sua qualidade.

### INTRODUÇÃO - TECNOLOGIA SPREAD SPECTRUM

A técnica _**Spread Spectrum**_ foi desenvolvida nos anos de 1940, em plena Segunda Grande Guerra, por uma atriz austríaca chamada Hedy Lamarr (Hedwig Eva Maria Kiesler – 1913 - 2000) e pelo músico compositor britânico George Antheil (1900 -1959). (RAPPAPORT, 2009)

A idéia surgiu a ambos quando brincavam de dueto em frente a um piano. Ela repetindo em outra escala as notas que ele tocava, experimentando o controle dos instrumentos, ou seja, duas pessoas podem conversar entre si mudando frequentemente o canal de comunicação, bastando para tanto que façam isso simultaneamente e de forma coordenada. Juntos, Antheil e Lamarr, submeteram a idéia ao Departamento de Guerra Norte-Americano que, a princípio, recusou em junho de 1941. Apesar disso, em agosto de 1942, ambos patentearam a idéia, sendo que a versão inicial consistia na troca de 88 frequências e era feito para despistar radares, porém a idéia pareceu difícil de colocar em prática naquela época.

Vinte anos depois, ou seja, apenas em 1962, passou a ser utilizada por tropas militares dos Estados Unidos em Cuba, quando a patente já havia expirado e a empresa _**Sylvania**_ adaptou a invenção. Ficou desconhecida ainda até 1997, quando a _**Electronic Frontier Foundation**_ deu a Lamarr um prêmio por sua contribuição.

A idéia do aparelho de frequência de Lamarr e Antheil serviu de base para a moderna tecnologia de comunicação, tal como o FHSS, o DSSS e o OFDM utilizados atualmente nas comunicações de WIFI, CDMA em telefonia celulares e nos modernos sistemas de Rádio Enlace Digital. (MEDEIROS, 2010)

Portanto, a técnica _**Spread Sprectrum**_ consiste basicamente em se escolher uma informação de canal estreito, dividir esta informação em pequenas partes e dentro de um canal largo transmiti-la na íntegra. Um sinal é chamado _**Spread Spectrum**_ quando a largura de banda é maior do que a requerida para enviar a informação e sua potência de pico de sinal é baixa.

Entre as vantagens desta técnica, pode-se citar a sua imunidade às interferências, pois uma tentativa de obstruir um sinal _**Spread Sprectrum**_ utilizando uma transmissão de canal estreito será frustrada, uma vez que apenas uma pequena porção da informação cairá nesta faixa de banda estreita e será perdida. A maior parte do sinal será recebida livre de erros. A transmissão em banda larga faz aparecer aos rádios de banda estreita um ruído de fundo. Ao mesmo tempo em que esta técnica reduz a interferência entre sistemas, pela utilização das mesmas frequências pelo salto de canais para a transmissão de cada um, conforme ilustrado na figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/6/292693/17584.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/6/292693/17584.png)

Figura 1 - Comparativo sinal banda larga e banda estreita

Fonte: (Felice, 2005 p. 30)

TECNOLOGIA _**FREQUENCY HOPE SPREAD SPECTRUM**_ - FHSS

O sistema FHSS modula o sinal de dados em um sinal de banda estreita, que salta de frequência em frequência, como uma função no tempo sobre uma ampla faixa de frequência. Tanto o transmissor como o receptor são previamente ajustados para uma sincronização de saltos e sintonia de frequências dos canais que estão sendo transmitidos.

O transmissor usa a sequência de saltos para selecionar a frequência de transmissão e a portadora irá permanecer em certa frequência por um tempo especificado chamado _**“dwell time”**_ e então utilizará uma pequena quantidade de tempo _**“hop time”**_ para saltar para a próxima frequência até a lista terminar e retornar a primeira, repetindo novamente a sequência e permitindo até 79 saltos com canais de 1MHz cada um, conforme ilustrado na figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292833/17586.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/8/292833/17586.png)

Figura 2 - Técnica FHSS - Salto de Frequências

Fonte: (Santos Junior, 2005 p.IV 17)

O sistema FHSS é um método no qual transmissor e receptor saltam de uma frequência para outra ao longo de padrões acertados entre ambos. Pode-se considerar que o FHSS é resistente às interferências, mas não inume, pois caso ocorra uma interferência num determinado canal, somente aquela pequena parte da informação será perdida, enquanto o restante permanecerá intacto. (SANTOS JUNIOR, 2005)

TECNOLOGIA _**DIRECT SEQUENCE SPRED SPECTRUM**_ - DSSS

Nesta técnica o sinal de rádio de banda estreita original é processado matematicamente e sua amplitude é “achatada” ao longo de uma banda de frequência relativamente maior, conforme ilustrado na figura 3. Nesta técnica tem-se uma verdadeira proteção contra ruídos, pois, conforme declarado por Santos Junior (2005, p. IV 22) “ruídos tendem a ter uma forma de pulsos relativamente estreitos, que não produzem efeito coerente através da banda de frequência, desprezando o ruído ao longo da banda pela correlação entre ruído e sinal de informação que é muito mais largo”. A correlação dá ao DSSS a devida proteção contra qualquer sinal de interferência que possa modular na mesma frequência do DSSS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/9/292905/17587.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/2/9/292905/17587.png)

Figura 3 - Correlação de sinais de alto pico e espalhados

Fonte: (Santos Junior, 2005)

Na técnica de _**Spread Spectrum**_, empregando a tecnologia de Sequência Direta – DSSS, o sinal de informação é multiplicado por um sinal codificador, com característica pseudorrandômica, conhecido como _**“chip code”,**_ onde para cada bit transmitido é gerada uma sequência de bits redundantes de alta taxa, a qual espalha a largura de banda antes da transmissão. No receptor, o sinal de informação é recuperado através de um processo complementar, utilizando um gerador de código local similar e sincronizado com o código gerado na transmissão.

Em razão da utilização de uma grande largura de banda para transmissão, os sistemas em sequência direta dispõem de poucos canais dentro da banda. Estes canais são totalmente separados de forma a não gerar interferência entre eles. Exemplificando, uma transmissão em DSSS, caso o sistema tenha de transmitir uma sequência de bits como, **1101**, neste caso, o sistema terá um circuito que irá substituir cada bit a ser transmitido por uma sequência, como demonstrado a seguir:

_**“Chip code”**_

Para bit 1 de informação = sequência de transmissão = 00110011011

Para bit 0 de informação = sequência de transmissão = 11001100100

Assim a informação a ser transmitida será:

00110011011     00110011011     11001100100     00110011011

1                          1                         0                         1

A técnica de sequência direta é também utilizada pelo sistema CDMA _**(Code Division Multiple Access)**_ de telefonia celular.

As vantagens desta técnica são:

- O circuito gerador de frequência (sintetizador) é mais simples, pois não tem necessidade de trocar de frequência constantemente como no padrão FHSS.
- O processo de espalhamento é simples, pois é realizado através da multiplicação do sinal de informação por um código.
- Maior capacidade de transmissão, da ordem de 11Mbit/s.

As desvantagens desta técnica são:

- Maior dificuldade para manter o sincronismo entre o sinal _“chip code”_ gerado e o sinal recebido.
- Maior dificuldade para solução dos problemas de interferências.
- Equipamentos de maior custo.

A figura 4 ilustra o processo da formação de um chip de códigos a ser transmitido em virtude da informação que a ele chega e consequentemente o alargamento do canal, que antes era de 2MHz passando depois da utilização do _**“chip code”**_ para 22MHz, canal este utilizado nos equipamentos wireless.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295012/17588.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295012/17588.png)

Figura 4 ¿ Processo utilizando Chip Code em DSSS

Fonte: (Santos Junior, 2005 p.IV 24)

CANALIZAÇÃO EM _**DIRECT SEQUENCE SPRED SPECTRUM**_ ? DSSS

No sistema sequencial direto (DSSS) temos a possibilidade de ter 14 canais na banda de 2,4GHz. Cada canal tem em sua banda contínua uma largura de 22MHz, sendo afastados dos canais adjacentes em 5MHz.

Portanto, iniciando do canal 1 temos a frequência de 2,401GHz e termina 22MHz para frente, ou seja, 2,423GHz, como temos um afastamento de 5MHz entre canais o canal 2 então começará em 2,406GHz e terminará 22MHz a frente, ou seja, 2,428GHz e o mesmo raciocínio aplica-se a todos os demais, num total de quatorze canais, conforme ilustrado na figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294027/17590.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294027/17590.png)

Figura 5 - Canais em DSSS

Fonte: (Santos Junior, 2005 p. IV 28)

Pela observação e matematicamente falando, vemos que existe uma interferência por sobreposição entre os canais e isso consiste num grave problema na configuração DSSS.

A quantidade de canais alocados para cada país depende dos organismos reguladores internos que ditam estas regras. No Brasil, a ANATEL utiliza a mesma quantidade de canais regulamentados pelo FCC – _**Federal Communications Commision**_, órgão norte americano de telecomunicações que determina 11 canais disponíveis.

A utilização dos 11 canais não minimiza o problema da sobreposição de canais do DSSS. Este problema de sobreposição demonstra que se tivermos dois rádios transmitindo, por exemplo, um no canal 1 e outro no canal 2 na mesma área de cobertura, os dois rádios sofrerão interferências, causando degradação do sinal e por consequência a perda da informação, portanto, pela figura 6 que ilustra a canalização em DSSS só teremos três canais sem sobreposição que são os canais 1, 6 e o canal 11. Utilizar canais que não se sobrepõem é a melhor escolha quando planejamos o emprego de dois ou mais rádios trabalhando na mesma rede: deve-se sintonizar cada um deles num canal diferente para minimizar a interferência de sobreposição. (NASCIMENTO, 1992)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294271/17591.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294271/17591.png)

Figura 6 - Canais em DSSS sem sobreposição

Fonte: (Santos Junior, 2005 p. IV 29)

![[Untitled 73.png|Untitled 73.png]]

_**ORTHOGONAL FREQUENCY DIVISION MULTIPLEXING**_ – OFDM

A modulação OFDM utiliza diversas portadoras ortogonais (independentes) para transmitir um sinal. Antes de ser modulado na portadora, este sinal passa por diversas etapas de processamento, que melhoram ainda mais a performance alcançada pelo OFDM.

Primeiro, os dados são submetidos a sistemas de proteção de erro, que consistem na inserção de um código corretor de erros, como por exemplo, o _**Reed - Solomon**_ e embaralhamento _**(scrambling),**_ em que os bits de um mesmo byte são todos misturados. Em seguida, os bits passam por um processo de entrelaçamento, no qual eles são reorganizados de modo que bits subsequentes passam a ser separados no tempo. Desta forma, a informação torna-se mais imune a erros do tipo rajada (erros de _**burst)**_, que atingem bits subsequentes, pois, após este processamento, tais erros passam a atingir bits pertencentes a diversos bytes diferentes, que estão muito distantes na informação original. Isto torna mais fácil a recuperação do sinal original no receptor. (MEDEIROS, 2010)

No processo de modulação OFDM, diversas portadoras em frequências diferentes são utilizadas para modular o sinal digital, sendo que cada portadora transporta apenas alguns bits do sinal original após passar pelos processos de embaralhamento e incluir códigos de correção de erro. Estas portadoras são ortogonais entre si, para evitar que haja interferência entre elas. Isso significa que o espaçamento entre as portadoras é igual ao inverso da duração de um símbolo. A figura 7 ilustra como as portadoras são separadas no tempo e na frequência. As portadoras são ilustradas com cores diferentes mostrando que pedaços de um mesmo bit são transmitidos por portadoras distantes entre si, tanto no tempo quanto na frequência.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294299/17592.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/2/294299/17592.png)

Figura 7 - Modulação OFDM

Fonte: (Malburg, 2004)

Num sistema convencional de transmissão, os símbolos são enviados em sequência através de uma única portadora, cujo espectro ocupa toda a faixa de frequência disponível. No entanto, a OFDM consiste na transmissão paralela de dados em diversas sub portadoras, com modulação QAM ou PSK e com taxas de transmissão por sub portadoras tão baixas quanto maior for o número destas.

Num sistema OFDM, o espaçamento entre sub portadoras é escolhido de forma que cada uma esteja centrada nos zeros das restantes, conforme é mostrado figura 8. Pode-se dizer que neste caso, existem ortogonalidade entre os sinais. Embora exista sobreposição dos espectros das sub portadoras, é possível extrair cada um deles através de tratamento do sinal em banda base. (MALBURG, 2004)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/3/294305/17593.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/3/294305/17593.png)

Figura 8 - Conjunção de sub portadoras em OFDM

Fonte: (Malburg, 2004)

REVISÃO:

- A modulação FHSS – _Frequency Hopping Spread Spectrum_ utiliza a técnica de sequência de saltos para selecionar a frequência de transmissão possibilitando então um total de 79 canais.
- A modulação DSSS – _Direct Sequence Spread Spectrum_ utiliza o alargamento do canal que era de 2MHz para 22MHz utilizando a técnica do _“chip code”,_ onde cada bit transmitido é trocado por uma sequência de 11 bits. Cada canal utilizado no DSSS tem sua largura de banda agora de 22MHz com um total de 14 canais e espaçamento entre canais de 5MHZ.
- O OFDM – _Orthogonal Frequency Division Multiplexing_ é uma técnica de comunicação que usa a largura de banda quebrando em vários sub canais e cada um deles transmitindo uma porção da informação. Todos os canais são então multiplexados e transmitidos.