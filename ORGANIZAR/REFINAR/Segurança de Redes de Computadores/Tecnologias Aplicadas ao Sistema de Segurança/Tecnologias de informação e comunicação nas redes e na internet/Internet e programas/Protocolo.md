[![](https://ampli-images.s3.amazonaws.com/production/bba1d263-1323-409f-8bf1-42aa452087ec/original)](https://ampli-images.s3.amazonaws.com/production/bba1d263-1323-409f-8bf1-42aa452087ec/original)

As tecnologias de rede englobam, ainda, os protocolos utilizados para que ocorra a troca dos dados. Tanenbaum (2011) compara os protocolos de redes de computadores com as línguas que nós, seres humanos, utilizamos para nos comunicar.

Usamos palavras e expressões diferentes, e mesmo caracteres diferentes, em muitos casos, quando nos comunicamos em uma ou em outra língua; contudo, conseguimos passar as mesmas mensagens, os mesmos significados.

Os protocolos digitais de comunicação entre computadores estabelecem como as mensagens devem ser codificadas de maneira que sejam compreendidas por todos os computadores que por meio deles se comunicam.

Historicamente há vários protocolos que, ao longo das várias décadas, vêm conectando computadores, muitos dos quais já estão em desuso, ou rapidamente sendo substituídos por protocolos mais amplamente adotados.

Dois exemplos de protocolos em desuso evidenciam a necessidade de padrões abertos em comunicação de dados. Os padrões abertos são, é importante frisar, aqueles cujas especificações estão disponíveis para implementação sem custo para as empresas.

Diferentemente dos padrões proprietários ou dos padrões disponibilizados por seus criadores por meio do pagamento de _royalties_ (taxas cobradas periodicamente para uso de propriedade intelectual protegida), os padrões abertos têm suas especificações publicadas e podem ser utilizados por qualquer empresa que os queira utilizar.

Observemos dois protocolos que não são considerados abertos (TANENBAUM, 2011):

**SNA (**_**Systems Network Architecture**_**)**Criado pela IBM em 1975, o SNA é, até os dias de hoje, o protocolo utilizado para integrar os _mainframes_ da IBM. Trata-se de um protocolo proprietário cuja especificação é de conhecimento público, mas que sempre foi estritamente controlado pela IBM.

**IPX/SPX (**_**internetwork packet exchange**_**/**_**secure packet exchange**_**)**Criado pela Novell em 1986 e batizado comercialmente de _Netware_, o IPX/SPX foi responsável pela proliferação de redes locais em uma época em que a interconexão de computadores em um escritório ainda era pouco divulgada.

Com a proliferação do modelo Ethernet e o consequente barateamento dos equipamentos de rede local (em especial dos _hubs_ e _switches_), o _Netware_ caiu em desuso e a empresa passou a atuar em outras áreas de TI.

Com a proliferação de protocolos proprietários, a ISO (_International Organization for Standardization_, ou Organização Internacional para a Padronização), criou, em 1978, o modelo OSI (_Open Systems Interconnection_, ou _Interconexão Aberta de Sistemas_).

O modelo OSI surgiu para padronizar a comunicação entre computadores conectados em uma rede. Tanenbaum (2011) mostra-nos que o modelo divide a comunicação entre computadores em sete camadas de protocolos, dando origem às “7 camadas OSI”, demonstradas na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/e326ea0f-0230-46c4-bdcb-8166e37f42bf/original)](https://ampli-images.s3.amazonaws.com/production/e326ea0f-0230-46c4-bdcb-8166e37f42bf/original)

As 7 Camadas da OSI. Fonte: adaptada de Tanenbaum (2011).

A ideia da pilha de protocolos proposta pela OSI é a de que cada camada converse, dentro do mesmo computador, apenas com as camadas superior e inferior, adicionando complexidade e mais informações quanto mais para cima caminhamos.

Entre os computadores, apenas camadas de mesmo nível se “conversam”. As 7 camadas do modelo OSI servem apenas para referência didática, uma vez que nunca foram implementadas na prática.

______

**🔁** **Assimile**Um protocolo digital de comunicação estabelece o formato da comunicação entre dois dispositivos computacionais.

______

Na prática, o modelo que prevalece é o modelo TCP/IP, no qual as camadas física e enlace são agrupadas, bem como também são agrupadas as camadas de sessão, apresentação e aplicação.

A figura a seguir mostra a correspondência entre as pilhas OSI e TCP/IP, bem como os protocolos de cada camada, atualmente em uso:

[![](https://ampli-images.s3.amazonaws.com/production/a6c07e63-f4af-4b89-adb3-b3204a28eaf0/original)](https://ampli-images.s3.amazonaws.com/production/a6c07e63-f4af-4b89-adb3-b3204a28eaf0/original)

Correspondência entre os Modelo OSI (teórico) e TCP/IP (implementado na Prática). Fonte: adaptada de Tanenbaum (2011).

São os protocolos que fazem as comunicações entre computadores, dispositivos móveis e todos os aparelhos conectados em rede. São eles as línguas com que os computadores falam entre si quando se comunicam.