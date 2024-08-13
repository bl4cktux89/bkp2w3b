**Introdução**

Para garantir a qualidade das instalações e o desempenho desejado é necessário ter certeza de que a obra foi realizada dentro das normas. Para tanto, a obra é submetida à realização de testes, que analisarão, por meio de equipamentos especiais, todas as medidas. Tais equipamentos são conhecidos no mercado como certificadores de cabos.

Os certificadores de cabos são equipamentos eletrônicos de alta tecnologia que possuem em seu banco de memória todas as especificações da norma contida na versão 568 C.2 e suas atualizações, referentes a todos os aspectos físicos e comportamentais para as aplicações de rede.

Em resumo, a certificação acontece ao aplicar o equipamento em todos os cabos instalados, um a um, até sua totalização, e a cada cabo certificado será aplicado também outra série de testes individuais. Se todos os testes estiverem em conformidade com a normativa pertinente, o cabo será declarado aprovado.

Os testes que compõem a certificação estão relacionados na sequência:

1. Wire Map – Configuração de terminação.
2. Comprimento.
3. Perda de inserção – atenuação.
4. Diafonia – Crosstalk.
5. PS-NEXT – powersum NEXT.
6. ACR – attenuation to crosstalk ratio.
7. PS-ELFEXT – powersum ELFEXT.
8. ELFEXT – Equal level for end crosstalk.
9. Perda de retorno.
10. Atraso de propagação.
11. Delay Skew – Desvio de atraso de propagação.

Em termos bem simples, a certificação dos cabos consiste em submeter cada ponto a todos os testes relacionados acima. O equipamento certificador irá aplicar a cada um deles, em cada frequência em que uma dada categoria de cabos foi projetada, e comparar essas medições nas várias frequências com os parâmetros estabelecidos pela norma.

Porém, antes do início efetivo dos testes, alguns parâmetros precisam ser ajustados no certificador, dependendo do tipo e fabricante dos cabos a serem testados, bem como sua categoria de transmissão.

Esses parâmetros de ajuste são: categoria do cabo submetido ao teste que poderá ser categoria 5e, categoria 6 e categoria 6A e o fator da NVP – Nominal Velocity of Propagation ou Velocidade Nominal de Propagação.

O certificador de cabos utiliza a técnica de reflectometria no domínio do tempo (TDR– "Time Domain Reflectometry"), que consiste basicamente em enviar um sinal por meio de uma das extremidades do cabo. O sinal se propagará até a outra extremidade, e se houver uma mudança de impedância (cabo aberto ou em curto circuito), ele será refletido.

Medindo-se o tempo desde o envio do sinal até o retorno da onda refletida e sabendo-se a velocidade nominal de propagação ou o NVP do sinal no cabo, têm-se os dados para calcular o comprimento dele.

A velocidade nominal de propagação é determinada a partir do desenho do cabo e da frequência do sinal a ser propagado. A NVP é fornecida pelo fabricante de cada cabo, expressa em fração da velocidade da luz no vácuo, que é de 300.000 quilômetros por segundo.

**Teste de Wire Map – configuração de terminação**

O teste de WIRE MAP verificará a correta conexão de cada um dos quatro pares, de cada cabo UTP de 100?, e verificará para cada um dos oito condutores nas seguintes condições:

1. Continuidade, imagem 01.
2. Curto circuito entre dois ou mais fios.
3. Pares transpostos: ocorre quando os dois condutores de um par estão conectados na posição de um par diferente, imagem 02.
4. Pares invertidos: acontece quando a polaridade de um par é invertida em uma das extremidades, imagem 03.
5. Pares espalhados: ocorre quando pino a pino a conexão está correta, porém os pares estão fisicamente separados, imagem 04.
6. Qualquer outro erro de conexão.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104896/a15i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104896/a15i01_cabestru80_100.jpg)

Ocorrendo um dos problemas listados, o certificador de cabos irá interromper a ação, indicando o local em que se encontra o problema, que poderá ser na tomada instalada na work área ou nas tomadas do patch panel, localizado no interior da sala de telecomunicações (TR) ou mesmo na sala de equipamentos (ER).

**Teste de comprimento do cabo**

O comprimento pode ser físico ou elétrico. No primeiro momento, têm-se a soma dos comprimentos medidos de cada cabo envolvido no link basic ou link permanente, no segundo utiliza-se o tempo de propagação do sinal elétrico e multiplica-se pela velocidade nominal de propagação (NVP), que possui uma margem de 10 % de erro.

Conforme determinado pela normativa, o comprimento máximo admissível para a configuração de link basic é de 90 metros e para link permanente é de 100 metros.

Caso o cabo que está sendo medido acuse mais de 90 metros, imediatamente o certificador irá interromper seu teste, informando a não conformidade segundo a normativa ANSI/TIA 568 C.2.

**Teste de perda de inserção – Insertion Loss**

A perda de inserção é a atenuação causada pelos componentes de resistência, capacitância e impedância desenvolvidas no canal. Essa atenuação é a perda da potência de um sinal em razão de sua propagação por um meio físico qualquer.

Essa perda de potência em um cabo de cobre ocorre devido às perdas resistivas dos condutores com o comprimento do lance de cabos, pois quanto maior for esse comprimento, maior será a resistência ôhmica do meio.

A atenuação é medida em dB (decibel) por unidade de comprimento dos pares de um cabo e quanto maior for esse valor, maior será a perda de potência do sinal aplicado a ele, portanto, o certificador irá medir essa relação de perda de potência e comparar com sua tabela interna, de acordo com as normativas vigentes. Caso esse valor seja superior ao estipulado em uma determinada frequência versus sua atenuação, o certificador irá interromper o teste e acusar o local com problemas.

A perda por inserção também pode ser observada nas conexões entre os elementos que formam o link de cabos, como exemplo temos a conexão do cabo à tomada da área de trabalho, a conexão do cabo UTP aos conectores do patch panel ou até mesmo as conexões de um ponto de consolidação ou MUTOA existente nesse link.

Em resumo, a perda por inserção é a diminuição do valor da potência do sinal aplicado a um cabo UTP durante sua passagem por este, conforme ilustrado na imagem 05.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104897/a15i02_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104897/a15i02_cabestru80_100.jpg)

**Diafonia – NEXT – Near End Crosstalk**

A diafonia é o efeito causado pela interferência de um par do cabo UTP, que sendo utilizado para o tráfego de sinal consegue irradiar de forma passiva sinais aos demais pares sem ter realmente um contato direto.

Nos sistemas de telefonia, a diafonia é muitas vezes conhecida como linha cruzada, ou seja, numa conversação entre dois assinantes consegue-se escutar bem ao fundo uma terceira pessoa falando. Esse efeito é a diafonia, ou seja, um sinal consegue, trafegando num par distinto, interferir por meio de ondas eletromagnéticas, nos demais pares que não pertencem àquela comunicação.

Esse efeito é devastador nas comunicações digitais por meio de cabos UTPs, pois essa interferência pode muitas vezes deformar as informações digitais ao ponto de o receptor não conseguir entender qual foi a mensagem transmitida.

No campo da diafonia, esses efeitos podem ser divididos em duas categorias bem distintas, a saber:

1. Paradiafonia.
2. Telediafonia.

**Paradiafonia – NEXT – Near End Crosstalk**

Na paradiafonia a medição dos valores é feita no par interferido (aquele que recebe a interferência), na mesma extremidade em que se encontra o par interferente (aquele que gera a interferência) em que está a fonte de ruído. Denomina-se paradiafonia ou simplesmente NEXT, conforme ilustrado na figura 06.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104899/a15i03_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104899/a15i03_cabestru80_100.jpg)

Da mesma forma, quando se mede a interferência no par interferido na extremidade oposta àquela em que se encontra a fonte de ruído no par interferente, dá-se o nome de telediafonia ou FEXT – Far End Crosstalk, conforme ilustrado na imagem 07.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104902/a15i04_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104902/a15i04_cabestru80_100.jpg)

Do ponto de vista de interferência elétrica, tanto o NEXT como o FEXT são iguais, sendo a única diferença a referência do ponto de medição, ou seja, se a interferência for medida na mesma extremidade em que se aplica o sinal causador da interferência, é NEXT; se a interferência for medida na outra extremidade do cabo em que se aplica o sinal gerador da interferência, é FEXT.

Como resultado desses testes (NEXT e FEXT) obtém-se a melhor condição do cabo, sendo submetido à prova quanto maior for o valor dessa medição. Isso pode até ser considerado um contra-senso, mas na realidade, o que se está medindo é a capacidade dos pares de poder evitar a diafonia e quanto maior for esse valor, mais protegido estará o cabo contra tais interferências.

Outros fatores que podem contribuir para a diafonia encontram-se nos conectores das tomadas, pelo excesso de destrançamento dos pares no momento da conectorização, o estrangulamento do cabo durante sua amarração por abraçadeiras plásticas nos leitos de cabos e o destrançamento dos pares por força excessiva durante a passagem deles por meio dos eletrodutos.

Como já estudado, a capacidade máxima que um cabo UTP pode sofrer de tensão durante seu lançamento é de 11,3Kg, que equivale a 110N ou a 25libras de pressão, aproximadamente. Portanto, a tabela que a norma traz com as capacidades máximas de cabos no interior dos eletrodutos devem ser rigorosamente respeitadas.

Para que se tenha a certeza absoluta que o cabeamento foi instalado respeitando as normativas é necessário submetê-lo a certificação dos cabos. O equipamento responsável por esses testes é o certificador de cabos que vai atuar na categoria correspondente do cabo instalado.Para que todos os testes sejam conclusivos, é necessário antes do início dos trabalhos ajustar a NVP correspondente ao cabo instalado. A NVP é a velocidade nominal de propagação do sinal elétrico no interior do cabo, que corresponde a um percentual da velocidade da luz.Os testes realizados são de conformidade elétrica pino a pino, o teste de atenuação e o teste de diafonia divididos em dois testes, sendo um a paradiafonia (NEXT) e a telediafonia (FEXT).