### Objetivo:

Para se entender o funcionamento das redes wireless é necessário conhecer os fundamentos da radiofrequência que torna a sua aplicação viável.

Nesta aula vamos conhecer as propriedades da radiação de radiofrequência e como seu comportamento pode afetar o desempenho das redes sem fio. Também vamos exercitar um pouco os cálculos pelas equações matemáticas que são aplicadas aos projetos de sistemas de radiofrequência, em particular, aos enlaces de rádio.

### 1. Introdução

Conhecer a ciência por trás das comunicações sem fio será útil ao profissional quando este desenhar seus projetos e entender que o comportamento dos sinais de rádio são totalmente diferentes dos sinais aprisionados nos cabos de redes e, por este motivo, conhecer as relações entre sinal/ruído, atenuação, canalização, propagação e desempenho fornecerá o perfeito conhecimento a este objetivo.

O entendimento da propagação das ondas é essencial ao profissional de redes wireless, uma vez que as perdas de sinal causadas por barreiras ou atenuações limitam a força do sinal podendo causar a paralisação de uma rede ou causar tanta degradação nos níveis de sinal que praticamente a rede fica inoperante.

### 2. Definição de Radiofrequência

Basicamente os sinais de radiofrequência são correntes alternadas de alta velocidade que passam através dos cabos e então são irradiadas pelo ar através das antenas.

As antenas por sua vez são elementos mecânicos, que convertem os sinais de alta frequência provenientes dos cabos em sinais eletromagnéticos que serão irradiados pelo ar e vice-versa, ou seja, podem receber sinais eletromagnéticos viajando pelo espaço e convertê-los em sinais elétricos. Os sinais de radiofrequência ou ondas de rádio propagam-se pelo espaço afastando-se da antena em todas as direções.

O gerador destes sinais alternados de alta frequência são os rádios, que por um processo de modulação vão conseguir transportar as informações através das ondas eletromagnéticas.

Por sua vez, a modulação é o processo de modificar as propriedades básicas do sinal elétrico de alta frequência a fim de ser impresso um código ou uma informação neste para depois ser transportado. O processo de modulação poderá alterar simultaneamente as propriedades do sinal elétrico como: Amplitude, Frequência ou Fase.

### 3. Propriedades do Sinal Elétrico Fundamental

Os rádios transmitem e recebem sinais através de longas distâncias na forma de ondas eletromagnéticas (EM), a figura 1 ilustra as principais propriedades de uma onda senoidal, usada para representar todas as formas de onda conhecidas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/7/4/1/1/741145/16531.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/7/4/1/1/741145/16531.jpg)

Figura 1 - Anatomia de um Sinal Elétrico

Podemos entender na ilustração que um ciclo é a menor parte da forma de onda. A repetição do ciclo representa a forma de onda inteira, onde as propriedades são distribuídas a seguir como sendo:

- Amplitude = α: Uma medida na forma de onda acima da referência, cujos valores poderão ser expressos em volts ou em watts.
- Velocidade de Propagação = C: Velocidade da onda ao se propaga no meio que pode ser representada em metros por segundo. A velocidade da onda eletromagnética (EM) é relativamente constante. Para efeitos práticos, equivale à velocidade da luz no vácuo que está expressa em 300.000 quilômetros por segundo.
- Período = t: Tempo que a onda gasta para completar um ciclo completo mensurado em segundos.
- Comprimento da onda = λ: Distância que a onda percorre em um ciclo, sendo medida em metros. Também recebe o nome de lambda.
- Frequência = f: Número de ciclos que a onda completa no espaço de tempo de um segundo, mensurada em ciclos por segundo ou Hertz (Hz).

As propriedades descritas são relacionadas entre si com exceção da amplitude através da seguinte equação:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/8/2/288255/16532.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/8/2/288255/16532.png)

Propriedades do sinal elétrico

### 4. Comprimento de Onda

Comprimento de onda é o parâmetro que demonstra matematicamente a distância que a onda percorre em um ciclo. Como o período t é o inverso de tempo em que um ciclo se repete, pode-se afirmar que no período t a onda terá se deslocado exatamente seu comprimento. Se a velocidade de propagação da onda é medida pela distância percorrida no intervalo de tempo, teremos:

C = distância percorrida / tempo gasto ou C = λ / t

Como a frequência é o inverso do período (f = 1/t), teremos a seguinte equação:

C = λ * f

Pela relação, observa-se que o comprimento da onda é inversamente proporcional à frequência, ou seja, quanto maior for à frequência menor será o comprimento de onda.

Para ondas eletromagnéticas, pode-se considerar C como sendo a velocidade da luz no vácuo, ou seja, C = 300.000Km/s o que nos remete a formula final:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/8/2/288257/16533.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/8/8/2/288257/16533.png)

Formula para cálculo de lambda

### 5. Espectro Eletromagnético

O espectro eletromagnético não compreende somente as ondas de rádio, mas apenas uma das várias bandas existentes. A gama de frequência de ondas EM se estende de alguns hertz logo acima da corrente contínua até as ondas de radiação cósmica, que podem atingir aproximadamente até 10²²Hz.

Conforme demonstrado por Santos Junior (2005) o espectro tem as seguintes categorias:

- Espectro de rádio: 3Khz - 300Ghz
- Espectro de micro-ondas: 100Mhz – 500Ghz
- Luz infravermelha: 500Ghz – 400Thz (Terahertz ou 10¹² Hz)
- Luz visível: 400 THz – 750 THZ
- Luz ultravioleta: 750 THZ – 30 PHz (Petahertz ou 1015Hz)
- Raios-X ≈ 30 PHz: - ≈ 10 UHz (Exahertz ou 1018 Hz)
- Raio Gama: ≈ 10 Hz - ≈ 10 ZHz (Zetahertz ou 10²¹ Hz)
- Raios cósmicos: > 10²¹ Hz.

Para prevenir a sobreposição no uso de ondas de rádio, as frequências são divididas e alocadas em bandas, que são faixas de frequências disponíveis para aplicações específicas conforme demonstrado na tabela 1.

Tabela 1 – Distribuição das frequências e suas faixas

![[Untitled 70.png|Untitled 70.png]]

Dentro de cada faixa existem características específicas de mecanismos de propagação, assim resumidos:

- Faixa ELF – Faixa de frequência cujas ondas penetram razoavelmente no solo ou na água, portanto possui aplicações em comunicação com submarinos e escavações de minas. As aplicações operam nesta faixa com transmissores de alta potência e grandes antenas;
- Faixa VLF – O mecanismo de propagação utilizado nesta faixa é a reflexão ionosférica, sendo considerado um ótimo condutor, pois induz pequena atenuação na onda refletida;
- Faixa LF – Até os 100 kHz nesta faixa, que vai até os 300 kHz, a reflexão ionosférica é utilizada, embora a atenuação na onda seja maior que a da faixa de VLF;
- Faixa MF – Acima de 100 kHz, o mecanismo de propagação utilizado é o de ondas de superfície com menor atenuação que o da reflexão ionosférica;
- Faixa HF – Nesta faixa de frequência aparece o mecanismo da refração ionosférica, visto que em regiões mais próximas do transmissor ainda permanece a presença das ondas de superfície;
- Faixa de VHF em diante – Nestas faixas não se utiliza mais à refração ionosférica, pois as ondas refratadas não atingem o ângulo necessário até os limites da ionosfera para retornar à superfície terrestre. Acima de VHF são usadas antenas diretivas que concentram a energia em feixes mais estreitos, estabelecendo as ligações por meio da onda espacial direta entre as duas antenas – transmissora e receptora, formando sistemas em visada direta.

### Revisão:

- Radiofrequência são sinais alternados de alta frequência que aplicados às antenas propagam-se pelo espaço em todos os sentidos.
- As antenas são elementos passivos que transformam correntes elétricas de alta frequência em ondas eletromagnéticas e vice-versa.
- Comprimento de onda é o parâmetro que demonstra matematicamente a distância que a onda percorre em um ciclo cujo valor é expresso em metros.
- Modulação é o processo de modificar as propriedades básicas do sinal elétrico de alta frequência para que seja impresso um código ou uma informação. O processo de modulação poderá alterar simultaneamente as propriedades do sinal elétrico como: Amplitude, Frequência ou Fase.