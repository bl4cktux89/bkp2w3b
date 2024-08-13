**Introdução**

As novas tecnologias de alta velocidade de transmissão de sinais digitais por meio de cabos metálicos obrigam os pesquisadores a utilizar mais de um par dos cabos UTPs para o aumento da velocidade.

Essas transmissões são muitas vezes simultâneas e bidirecionais, ocasionando uma nova série de perturbações no decorrer do espectro de frequências que o cabo deverá suportar.

Uma questão importante diz respeito ao tempo que esses sinais vão percorrer o referido cabo e como estamos dividindo a informação em mais de um par do mesmo cabo. É fundamental que todos os sinais consigam chegar ao seu extremo num tempo razoável, a fim de recompor a informação original.

A normativa ANSI/TIA 568-C.2 inclui nos testes de certificação mais dois parâmetros, que são os testes de atraso de propagação (_**propagation delay**_) e o teste de atraso de propagação relativa (_**skew delay**_), que têm como objetivo determinar o tempo gasto para que o sinal elétrico possa percorrer o cabo de uma extremidade a outra, em todas as frequências do espectro correspondente da sua categoria.

Lembre-se que cada categoria demonstrada na tabela abaixo precisa atender na sua plenitude a largura de banda, ou seja, o cabo deverá comportar todos os sinais e frequências no intervalo determinado por essa banda.

O atraso dos sinais nos diferentes pares do mesmo cabo poderá prejudicar sensivelmente a recomposição da informação, portanto os testes de tempo são fundamentais à certificação de uma obra em tecnologia de cabeamento estruturado.

![[Untitled 61.png|Untitled 61.png]]

**Teste de atraso de propagação –** _**propagation delay**_

O tempo de propagação é o tempo que o sinal elétrico leva para ir de uma extremidade a outra do cabo.

O tempo máximo permitido para todas as categorias na configuração de teste de link canal é de no máximo 555 ns (nanosegundos), medidos a uma frequência de 10 MHz, e para o link "basic" ou permanente é de 498 ns medidos na mesma frequência.

Para relembrar o link "basic" ou permanente, trata-se daquela configuração do cabeamento horizontal formada apenas pelo cabo rígido mais a tomada de telecomunicações, instalada na _**work área**_, e a conexão desse cabo no _**patch panel**_ correspondente, totalizando no máximo uma extensão de 90 metros.

Já o link canal ou "channel" é formado pelo link permanente mais os dois cabos flexíveis de manobra, conhecidos como _**patch cords**_, que somados ao link permanente podem totalizar no máximo a extensão de 100 metros.

**Teste de atraso de propagação relativo –** _**skew delay**_

O _**skew delay**_ ou atraso de propagação relativo compara as diferenças no tempo de propagação dos sinais em cada par individualmente, informando a maior diferença.

O valor máximo permitido de _**delay skew**_ para todas as categorias na configuração de teste de canal é 50 ns e, no link permanente, 44 ns.

Esse teste é muito importante para o perfeito funcionamento dos cabos nas aplicações de alta velocidade, pois nas configurações de rede acima de 100 Mbits, ou seja, acima do _**fast ethernet**_, costuma-se utilizar mais de um par para a transmissão digital, e essas ocorrem simultaneamente.

Essa técnica de transmissão de alta velocidade utiliza a divisão da informação digital em grupos separados de bit, portanto, se o atraso for demasiadamente grande dos sinais de chegada na outra extremidade do cabo, a informação que foi dividida não poderá ser reconstruída, ocasionando a perda do dado.

Num cabo UTP existem quatro pares de fios que são trançados dois a dois, o passo de trançamento, que é a quantidade de voltas por unidade de comprimento, é diferente para cada par e tem o objetivo de evitar o acoplamento indutivo entre eles.

Assim, no par que houver menor distanciamento no passo de trancamento, maior será o seu comprimento e, consequentemente, maior será o tempo gasto para o sinal elétrico percorrer esse par.

Outro fator que também pode afetar a velocidade de propagação do sinal elétrico refere-se à pigmentação utilizada para colorir a capa dos pares para sua identificação, portanto o _**skew delay**_ é de suma importância ao pleno funcionamento das redes, principalmente nas altas velocidades, como no caso do _**gigabit ethernet**_ e do dez _**gigabit ethernet**_. A imagem, disponível abaixo, ilustra o teste de _**skew delay**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104972/a17i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104972/a17i01_cabestru80_100.jpg)

**Testes de desempenho de transmissão em fibra óptica**

É denominado link de fibra óptica o cabeamento passivo que inclui o cabo, conectores e as emendas entre dois pontos de terminação em hardwares de conexão de fibra óptica.

Ele pode ser **horizontal**, englobando a tomada de telecomunicações da área de trabalho até o horizontal cross-connect na sala de telecomunicações (TR), ou **centralizado**, que considera o trecho da tomada de telecomunicações até o cross-connect centralizado, situado na sala de equipamentos (ER).

No caso de **backbones**, há três situações distintas: main cross-connect até o intermediate cross-connect; main cross-connect até o horizontal cross-connect; e intermediate cross-connect até o horizontal cross-connect; conforme já estudado em aulas passadas.

**Equipamentos de teste**

Os três principais equipamentos para teste em campo são:

- Fonte de luz visível: poderá ser uma lanterna ou qualquer outra fonte de luz. Esse teste só verifica a continuidade do cabo óptico, não servindo para a certificação.
- _Power Meter:_ equipamento portátil que possui uma fonte luminosa e um medidor de potência com medições em dB (decibel), realizando o teste de continuidade e fornecendo o valor da atenuação do trecho medido. Esse teste deverá ser feito para os comprimentos de onda de 850 nm e 1.300 nm, respectivamente.
- OTDR: Equipamento portátil e de altíssimo custo que fornece medições indiretas à atenuação, através do retroespalhamento de um sinal luminoso emitido no canal. Como informações, tem-se as emendas e as suas perdas ao longo do caminho e variações bruscas de atenuação, que podem representar os Distribuidores Internos âpticos (DIOs), emendas de cabos com características diferentes e ruptura do cabo. Todas essas informações estão relacionadas a distâncias e, sendo assim, pode-se descobrir o ponto no qual ocorreu uma ruptura no cabo.

**Execução dos testes**

No link horizontal, é necessário testar somente um comprimento de onda de 850 nm ou 1.300 nm, numa única direção, tendo em vista que na distância de 90 metros as diferenças entre as atenuações são insignificantes. Os valores devem ser inferiores a 2 dB e, se houver um ponto de consolidação, 2,75 dB.

No link óptico centralizado, deve-se testar somente um comprimento de onda de 850 nm ou 1.300 nm, numa única direção, tendo em vista que na distância máxima de 300 metros as diferenças entre as atenuações são insignificantes. Os valores, considerando a perda de três pares de conectores mais 300 metros de cabo, devem ser inferiores a 3,3 dB e, se houver um ponto de consolidação, 4,1dB.

No caso de certificação de backbone, deve-se testar, pelo menos em uma direção, e nos comprimentos de onda de 850 nm e 1.300 nm para fibras multimodo e 1.310 nm e 1.550 nm para fibras monomodo.

Os equipamentos de certificação foram desenvolvidos para garantir a qualidade das instalações e o desempenho desejado, pois somente a certificação poderá garantir que a obra foi realizada dentro das normas.

Ao terminar uma obra em tecnologia de Cabeamento Estruturado, a certificação deverá ser realizada em todos os pontos, cabos e fibras instaladas no cliente, e essa certificação, depois de impressa, fará parte da documentação de entrega do certame.

Todos esses testes serão realizados através de equipamentos especiais de medidas, que confirmarão o bom trabalho dos profissionais. Os valores e os tipos de testes estão especificados nas Normas ANSI/TIA/EIA 568-C, e todos os parâmetros dessa norma se encontram nas memórias dos equipamentos certificadores, conforme demonstra as imagens abaixo.

### **DTX - 1800 - FLUKE**

[**IMAGEM**](http://www.fluke.com/)

### **FAMÍLIA LANTEK - IDEAL**

[**IMAGEM**](http://www.idealindustries.com/)

Para finalizarmos a nossa aula, não podemos esquecer:

- O teste de atraso de propagação (_propagation delay_) mede o tempo gasto para o sinal percorrer o cabo de uma extremidade a outra, e os valores apurados não podem ser superiores a 555 ns para link canal e 498 ns para link permanente.
- O teste de atraso de propagação relativa mede a diferença dos tempos entre os quatro pares do cabo, sendo medido o tempo individualmente e apresentando o pior resultado. Os valores máximos admitidos são de 50 ns para link canal e 44 ns para link permanente.
- A certificação de cabos ópticos deverá ser realizada com equipamentos do tipo _Power Meter_ ou OTDR, e seus testes devem atender aos comprimentos de onda de 850 nm e 1.300 nm para fibra multimodo e de 1.310 nm e 1.550 nm para fibras monomodo.