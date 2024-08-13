### **Introdução à modulação**

A maioria dos sinais não pode ser transmitida através do meio de transmissão sem perder suas características, principalmente em longas distâncias. Por exemplo, a voz humana não pode ser transmitida a longas distâncias por espaços livres sem o processo de modulação, o sinal da voz humana “enfraquece” quando dois interlocutores estão separados por grandes distâncias. Para transmitir a voz humana, em longas distâncias é necessário modificar esse sinal através de uma onda eletromagnética chamada de **portadora**. Dessa forma, a onda portadora terá o seu sinal modulado pela onda do sinal a ser transmitido, que é conhecido com sinal **modulante**, conforme mostrado na Figura 1. Na Figura 1 é mostrado a transmissão de um sinal de áudio (sinal modulante) sobre uma onda portadora e a resultante é o sinal modulado em AM (Modulação de amplitude) ou FM (modulação de frequência).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/7/362767/28814.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/7/362767/28814.png)

Figura 1 - Modulação AM e FM

Uma onda senoidal, conforme Figura 1, pode ter suas características de frequência, amplitude e fase alteradas para criar uma versão diferente da mesma onda. A **modulação**, portanto, é uma técnica que altera essas características para transmissão de informações. Entre outros aspectos, o processo de modulação permite adaptar o sinal a ser transmitido às características do canal.

A transmissão de áudio, vídeo e dados podem ser feitas sem a utilização de portadora (transmissão do tipo banda base) ou utilizando técnicas de modulação (com portadora). Os antigos telefones e os telégrafos, por exemplo, não utilizavam portadoras. Entretanto, a distância e quantidade de dados a serem transmitidos serão baixos.

### Técnicas de Modulação

As técnicas de modulação são divididas em dois grandes grupos: Técnicas destinadas para transmissão analógica e técnicas destinadas à transmissão digital de sinais. Da mesma forma, as portadoras podem ser digitais e analógicas, assim como a informações. Na Figura 2 abaixo são mostradas as diferentes formas com que os dados podem ser transmitidos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/4/354411/28787.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/4/354411/28787.png)

ClassificaÃ¿Â§Ã¿Â£o das modulaÃ¿Â§Ã¿Âµes digitais e analÃ¿Â³gicas

Fonte:

### Modulação Analógica

A transmissão de sinais analógicos (com portadora analógica) são normalmente utilizadas por rádios e TVs e consiste na modulação do sinal da portadora por meio das técnicas de Modulação de Amplitude (AM – do Inglês Amplitude Modulation) ou Modulação de frequência (FM – do Inglês frequency modulation), descritas abaixo:

- Modulação de Amplitude (AM): A amplitude da portadora analógica de um transmissor é modificada pelo sinal modulante (sinal de interesse), conforme Figura 1, enquanto que a frequência e a fase são mantidas constantes. Transmissões AMs têm como característica a susceptibilidade a interferência eletromagnética e estática.
- Modulação de Frequência (FM): diferentemente da AM, a FM mantem a amplitude constante, enquanto que a frequência é alterada pelo sinal pelo sinal modulante, conforme mostrado na animação abaixo. A FM é menos susceptível a interferência do que a AM e são mais adequadas para transmissão de sinais de áudio e televisão.

### Tipos de modem

Os modens são dispositivos que executam transformações nos sinais que trafegam por um meio de transmissão. Esses modens podem ser do tipo analógico e digital. Os **modens analógicos** realizam a modificação por modulação, convertendo o sinal digital em analógico; enquanto que os **modens digitais** realizam a transformação por codificação, convertendo o sinal digital para outro padrão, também digital, adaptado para o meio de transmissão. Dentre os modens analógicos podemos citar os modens internos ao computador; já os modens ISDN (**Rede Digital de Serviços Integrados) e ADSL (**Linha Digital Assimétrica para Assinante) são considerados do tipo digital (Casagrande, J. H. B, 2008).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/2/224222/7684.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/2/224222/7684.jpg)

Figura 4 - Modem digital e analógico.

Os modens podem ser classificados também como interno e externo, conforme mostrado na Figura 5 (o modem a esquerda é interno e a direita é externo). Na transmissão via telefone utilizamos **modens internos** ao computador, que transformam os dados digitais em um sinal inteiramente analógico, já que as linhas telefônicas são analógicas . Essa modulação ocorre em uma faixa contínua de valores, e dessa forma, são transmitidos através da linha telefônica até a central de telefonia de seu bairro. De forma técnica, o modulador recebe os sinais digitais e convertem em pulsos de tensão em sinais de áudio (analógico) sobre um tom contínuo na faixa de 1000 a 2000 Hz, denominada portadora de onda senoidal (Tanenbaum, A. S. 2011), que então é transmitido até a central telefônica. Na central telefônica, por meio de um segundo modem, o sinal é demodulado na sua forma original, conforme mostrado na Figura 6. O problema na transmissão por modens deste tipo é que a linha fica ocupada e a taxa de transferência de dados é limitada a 56 Kbps. Existem também os **modens externos**, utilizados principalmente em transmissões do tipo banda larga, como é o caso do ADSL. Neste caso, a tecnologia ADSL aproveita a largura de banda não utilizada na transmissão de voz e estabelece um link totalmente digital com a central do bairro. Portanto, com o modem digital não é necessário fazer a conversão de digital em analógico na central do bairro, o sinal é apenas decodificado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363532/untitled-1.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363532/untitled-1.jpg)

Figura 5 - Modem interno (a esquerda) modem externo ADSL (a direita).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/7/362781/28819.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/2/7/362781/28819.png)

Figura 6 - transmissão de dados através de um modem

Fonte: http://www.pcs.usp.br/~labdig/pdffiles_2012/modem.pdf