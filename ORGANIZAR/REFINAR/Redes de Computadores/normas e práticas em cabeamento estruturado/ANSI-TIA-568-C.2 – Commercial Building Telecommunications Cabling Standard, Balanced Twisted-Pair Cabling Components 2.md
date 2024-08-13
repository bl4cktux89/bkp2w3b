**Introdução**

O cabo UTP, como elemento principal de uma rede em tecnologia de cabeamento estruturado, está sujeito a várias modificações do seu comportamento físico e elétrico conforme as aplicações de rede necessitem de maiores velocidades. Dessa maneira, cabos que têm sua banda passante menor não suportam serviços com velocidades maiores, como é o caso do giga bit e o de 10 giga bit.

Conforme a velocidade da rede aumenta, modificam-se também os valores nominais das características elétricas dos fios utilizados na construção dos cabos, como a impedância, capacitância e indutância.

O resultado desse avanço foi desenvolver e estabelecer novos parâmetros de testes, com o objetivo de garantir a real performance dos cabos instalados.

Esta aula se destina ao estudo dos seguintes testes realizados nos cabos UTP:

1. [**ACR**](https://ava.uninove.br/seu/AVA/topico/topico.php) – Relação Atenuação – Diafonia/ PSACR – Power Sum ACR;
2. PS-NEXT – [**Power Sum NEXT**](https://ava.uninove.br/seu/AVA/topico/topico.php);
3. ELFEXT – Equal Level for end Crosstalk e PS-ELFEXT; e
4. Perda de retorno

**ACR – Relação Atenuação – Diafonia e PSACR – Power Sum ACR**

A relação de Atenuação – Diafonia ou ACR – é o melhor indicador de verificação das condições de transmissão de um cabo de par trançado, pois representa o espectro de frequências que podem ser transportadas pelo cabo, sem sofrerem distorções que impossibilitem o correto entendimento do sinal no seu receptor.

Para tanto, esse parâmetro é calculado ao se subtrair o pior caso de perda de inserção, que é a atenuação medida, do pior caso de NEXT, ambos os valores em decibéis, sendo que o valor conseguido será utilizado como critério para determinar a banda passante disponível do cabo submetido no teste.

Como vimos na aula 15, o valor de NEXT será medido para um conjunto de frequências, que representa a relação entre o sinal transmitido e o ruído gerado, porém o valor medido da intensidade do ruído levará em conta todos os ruídos existentes no ambiente e não só o causado pelo par do cabo que será alimentado com sinal, ou seja, esse valor de NEXT não representará somente a interferência causada pelo par próximo.

Quando se subtrai a atenuação do valor do NEXT, como é feita nos cálculos de ACR, obtém-se o valor correto do sinal que chega até o receptor na outra extremidade do canal sem sofrer essa influência do meio.

Assim como o NEXT, o ACR pode ser determinado por ambos os métodos, que são ACR par a par e o ACR Power Sum.

Com o surgimento das transmissões simultâneas e bidirecionais, foi necessário esse novo teste, que engloba o ruído produzido pelos outros pares influenciando o quarto par, exatamente como no teste de [**Power Sum NEXT**](https://ava.uninove.br/seu/AVA/topico/topico.php).

**PSNEXT – Power Sum NEXT**

A metodologia do teste de NEXT foi a primeira a ser estabelecida. Ditava o referido teste que um par, sendo aplicado sinal, poderia ocasionar problemas pela transferência eletromagnética aos demais pares.

Esse teste classifica todos os testes sempre de dois em dois pares, sendo um o que se aplica o sinal e o outro o que se mede essa interferência.

Quando se iniciaram as discussões de um novo padrão com velocidades muito superiores à existente, como foi o caso do Fast Ethernet, que começou a operar a 100 Mbits, e do Giga Bit Ethernet, deslumbrou-se a possibilidade da utilização ao mesmo tempo de mais de um par, tornando o simples teste do NEXT par a par ineficiente, sendo que agora os novos padrões começavam a operar em full duplex.

A partir dessas definições e conclusões, os organismos normatizadores substituíram os testes simples de NEXT par a par por outro teste mais sofisticado, em que a metodologia era aplicar sinais de interferência em três pares e medir no quarto par a somatória dessa interferência, ficando conhecido como teste de Power Sum NEXT.

Como resultados práticos nos dias de hoje, os equipamentos de certificação não fazem essa medição retratada nas normas, mas, sim, o valor do PS-NEXT é calculado com base nos valores obtidos das medições do teste de NEXT par a par por um algoritmo de cálculo aprovado pela norma vigente.

Concluímos então que o teste de PS-NEXT não é medido, e sim calculado com base nos valores do simples teste de NEXT par a par, levando-se em consideração o crosstalk provocado por todos os pares em um, operando simultaneamente conforme ilustrado na imagem que poderá ser visualizada na página seguinte.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104913/a16i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104913/a16i01_cabestru80_100.jpg)

**ELFEXT – Equal level for end crosstalk – e PS-ELFEXT – Power Sum ELFEXT**

Como já foi estudado na aula passada, o teste de FEXT (Far-end-crosstalk) ou telediafonia mede o acoplamento de um sinal indesejado do transmissor na ponta próxima do par medido na extremidade afastada.

Esse teste é medido fisicamente aplicando-se sinal par a par e mensurando os valores da interferência por acoplamento no par testado.

Quando se utiliza o cabeamento para aplicações de baixa velocidade, como as redes de 10 Mbits Ethernet, o simples teste de FEXT é bastante eficiente, pois tais redes utilizam apenas dois pares do cabo na sua comunicação, porém, quando se trabalha com velocidades maiores, como é o caso do Fast Ethernet de 100 Mbits, em que se opera com os quatro pares de forma full duplex, o simples teste de FEXT perde o sentido por não conseguir mensurar os valores de todos os sinais trabalhando simultaneamente no mesmo cabo e interferindo em um par.

Para tanto foi desenvolvido o teste do ELFEXT, que mede a diferença entre o FEXT e a perda de inserção do par perturbado, realizado par a par, diferente do teste de FEXT, que mede o valor interferido ou acoplado par a par.

Como realizado igualmente nos testes de NEXT e PS-NEXT, também é definido o Power Sum ELFEXT (PS-ELFEXT), que é a somatória das contribuições de ELFEXT de três pares do cabo UTP influenciando o quarto par, portanto, o teste de Power Sum ELFEXT leva em consideração todos os sinais da extremidade próxima em que se aplica o sinal, influenciando simultaneamente o par da extremidade afastada conforme ilustrado na figura a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104914/a16i02a_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104914/a16i02a_cabestru80_100.jpg)

**Perda de Retorno – Return Loss**

Um dos grandes problemas encontrados nas comunicações digitais com a utilização de cabos metálicos diz respeito à [**perda de retorno**](https://ava.uninove.br/seu/AVA/topico/topico.php). Esse teste é realizado pela medição da energia refletida em virtude das variações de impedância no sistema de cabeamento.

Um sistema de cabeamento sofre várias alterações de impedância no percurso de um cabo por causa das conectorizações entre cabos e tomadas, nos painéis do tipo patch panel e nos próprios cordões de adaptação, os partch cords.

Cada conexão é um fator de atenuação e, se não forem realizadas com equipamentos e produtos com as mesmas características de impedância, poderão ocasionar o retorno do sinal à fonte que o está enviando, causando assim a diminuição na resposta final da potência elétrica do sinal digital.

A perda de retorno varia sensivelmente com a frequência e com as pequenas variações no valor da impedância ao longo do segmento do cabo. Tais variações podem causar não só a perda da potência efetiva, mas um efeito de variação aleatória conhecido como [_**jitter**_](https://ava.uninove.br/seu/AVA/topico/topico.php), que faz com que as bordas dos pulsos digitais variem aleatoriamente no tempo em torno de suas posições chamadas ideais.

Esse efeito é responsável pela geração de atrasos não uniformes nos sinais digitais, conhecidos como distorção de fases ou atrasos de grupo, o qual ocasionará uma interferência intersimbólica ou superposição dos pulsos, degradando assim a comunicação digital. A figura a seguir exemplifica o descrito.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104916/a16i03_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/9/104916/a16i03_cabestru80_100.jpg)