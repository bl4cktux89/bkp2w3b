**Traffic shaping (conformação de tráfego)**

Até o momento, tratamos algumas ferramentas que auxiliam no controle de vazão, fila e congestionamento para uma eficiente qualidade de serviços na rede de computadores. Dentre os assuntos, um item que merece destaque é a formação do tráfego dos dados. Podemos citar dois processos de muita importância:

- Policiamento de tráfego.
- Conformação de tráfego.

Normalmente, o tráfego é condicionado baseado nessas duas principais regras citadas. Uma conformação de tráfego pode causar atrasos por servir filas mais lentas se suas regras não estiverem bem definidas. Por exemplo, um roteador acaba retardando o envio de pacotes, mas sem um motivo especifico. Se há uma modelagem no tráfego (conformação do tráfego), a quantidade máxima permitida numa largura de banda pode ser equilibrada de acordo com a quantidade de bits que devem ser transmitidos, sem sofrer, entretanto, uma perda excessiva nos dados. Nesse caso, pode-se questionar:

É melhor enviar pacotes rapidamente e ter a possibilidade de serem bloqueados ou descartados?

É melhor enviar os pacotes mais lentamente, mas não ter possibilidade de perda?

Como dito, às vezes um motivo pelo qual um pacote pode ser perdido está associado aos roteadores de um site central utilizar um link de acesso rápido enquanto que um site remoto está usando muitos links mais lentos. Por isso, tratar o policiamento e a conformação dos tráfegos é de extrema importância para reduzir o impacto da perda de dados numa transmissão.

Atualmente, um _**traffic shaping**_ incrementa atrasos _**(delay)**_ no esforço de reduzir a chance da perda de pacotes. A ajuda vem através do adicionamento de mais largura de banda. O quadro a seguir compara alguns tipos de ferramentas de QoS e como elas afetam um atraso:

![[Screenshot_20220207_212549.png]]

**Comparando** _**traffic shaping**_ **com** _**policing**_

Pelo fato de traffic shaping e _**policing**_ proverem duas funções diferentes, você pode achar estranho que haja uma relação entre eles, mas, na verdade, redes que usam _**policing**_ tipicamente usam _**shaping**_ à mesma proporção. Deve-se lembrar, aqui, que quando mencionamos "_**policing**_", estamos nos referindo ao gerenciamento de policiamento de acesso e ao nos referirmos a "_**shaping**_", falamos da conformação do tráfego.

**Considerações finais**

A conformação de tráfego pode ser encontrada em diversas referências como sendo:

- FRTS – _Frame Relay Traffic Shaping._
- GTS – _Generic Traffic Shaping._

Para você, caro aluno, o importante é entender que o conformador de tráfego permite o controle de tráfego que sai pela interface para associar a velocidade do fluxo com a interface remota e garantir que o tráfego seja conforme o policiamento contratado. Uma das razões pela qual se utiliza a conformação de tráfego é o controle de acesso para a largura de banda disponível, assegurando que o tráfego esteja de acordo com o contratado e, também, para regular o fluxo do tráfego, de modo a evitar congestionamentos que possam ocorrer quando o tráfego excede a velocidade da interface.

O conformador de tráfego previne perda de pacotes. O seu uso é importante em redes frame-relay porque o switch não pode determinar quais pacotes tem precedência e também não pode prever quais pacotes devem ser descartados quando ocorre um congestionamento.

Também é importante saber quais as principais diferenças entre FRTS e GTS:

- O FRTS suporta compartilhamento baseado em DLCI (canais frame-relay), enquanto o GTS é configurado por interface.
- No GTS, a fila é utilizada baseado na ferramenta WFQ. No caso do FRTS, não há suporte WFQ, sendo possível utilizar o método FIFO neste caso.

> [!important]  
> 1. Fábio Ribas Ardeola é autor de uma tese de mestrado de ciências da computação que descreve em detalhes maiores os processos de conformação de tráfego. Recomenda-se sua leitura. Disponível em <http://www.lume.ufrgs.br/bitstream/handle/10183/2828/000326612.pdf>