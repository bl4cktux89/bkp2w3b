**Tempos de atraso**

Consideremos um segmento UDP, que é encapsulado em um datagrama IP. Enquanto o datagrama viaja pela rede, ele passa por _**buffers**_ nos roteadores, para poder alcançar o enlace de saída. É possível que um ou mais buffers na rota entre o remetente e o destinatário estejam lotados e não possam aceitar o datagrama IP. Nesse caso, o datagrama IP será descartado e nunca chegará à aplicação receptora.

Isso pode ser melhorado simplesmente enviando pacotes por TCP, pelo simples fato de ele tentar retransmitir pacotes que por ventura não chegaram ao seu destino. Entretanto, mecanismos de retransmissão frequentemente são inaceitáveis para aplicações interativas de áudio em tempo real, por exemplo, voz sobre IP, porque aumentam o atraso fim a fim. Além disso, por causa do controle de congestionamento do TCP, após a perda de pacote, a taxa de transmissão no remetente pode ser reduzida a uma taxa mais baixa do que a taxa de reprodução no receptor, o que pode causar um forte impacto sobre a voz no receptor. Por isso essas aplicações massivas em tempo real trabalham com o UDP, não se preocupando com a retransmissão de um pacote perdido. Pacotes com taxas de perdas entre 1 e 20 por cento são toleradas por essas aplicações.

Os tempos de atraso podem ser resumidos da seguinte forma:

- Atraso fim a fim: que é o acúmulo de atrasos de processamento, de transmissão e de formação de filas nos roteadores e atrasos de processamento em sistemas finais. Por exemplo: para aplicações de áudio altamente interativas (VOIP), atrasos fim a fim menores do que 150 milissegundos não são percebidos pelo ouvido humano; atrasos entre 150 e 400 milissegundos podem ser aceitáveis, mas não são o ideal, e atrasos maiores que 400 milissegundos podem atrapalhar seriamente a interatividade em conversações por voz. Normalmente, o lado receptor da aplicação acaba desconsiderando o pacote que possua um tempo maior de 400 milissegundos de resposta, ou seja, esse pacote é descartado.
- Variação de atraso: um componente crucial são os atrasos aleatórios de fila nos roteadores. Por causa desses atrasos variáveis dentro da rede, o tempo decorrido entre o momento em que um pacote é gerado na fonte e o momento em que é recebido no destinatário pode variar de pacote para pacote.

Para uma maior compreensão, uma referência que trata mais amplamente sobre tempos de atraso está em KUROSE, 2010, o qual recomendamos a leitura, em especial, do capítulo 07.

**O que é PPS**

Em redes de comunicação, PPS significa Pacotes por Segundo (do inglês: _**Packets per Second**_), que é a taxa média de entrega de mensagem de sucesso ao longo de um canal de comunicação. Esses dados podem ser entregues por meio de uma ligação física ou lógica, ou passar por intermédio de um nó de rede. A taxa de transferência é normalmente medida em bits por segundo (bit / s ou bps), e, às vezes, em pacotes de dados por segundo ou pacotes de dados por intervalo de tempo. Essa medida também é conhecida como _**"throughput"**_.

O rendimento do sistema ou throughput total é a soma das taxas de dados que são entregues a todos os terminais de uma rede.

O rendimento pode ser analisado matematicamente por meio de teoria de filas, em que a carga de pacotes por unidade de tempo é denotado ? – taxa de chegada – e a taxa de transferência de pacotes por unidade de tempo é denotado ? – taxa de partida.

**Exemplo de aplicação**

O Iperf é um software livre, do tipo "client/server", desenvolvido pelo _**National Laboratory for Applied Network Research – NLANR.**_ Com ele, podemos:

- Testar/medir o throughput da rede.
- Medir múltiplas conexões simultâneas usando os protocolos UDP e TCP.
- Latência (ou RTT): o tempo de resposta pode ser medido com o comando ping.
- Jitter (variação de latência): pode ser medido com testes usando o protocolo UDP.
- Datagram loss (Perda de datagrama): pode ser medido com testes usando o protocolo UDP.

Iperf utiliza as diferentes capacidades de TCP e UDP para fornecer estatísticas sobre as ligações de rede.

Finalmente, Iperf pode ser instalado facilmente em qualquer sistema Unix / Linux ou sistema Microsoft Windows. Um host tem de ser definido como o cliente, o outro como servidor.

O programa para versão windows pode ser baixado no link [**<https://publishing.ucf.edu/sites/itr/cst/Pages/IPerf.aspx>**](https://publishing.ucf.edu/sites/itr/cst/Pages/IPerf.aspx).

Um artigo legal que recomendamos é o descrito pelo autor André Ortega: ORTEGA, André. Testando a Rede com o Iperf. Brainwork, 2010. Disponível em: [**<http://www.brainwork.com.br/blog/2010/06/21/testando-a-rede-com-o-iperf-gerador-de-trfego/>**](http://www.brainwork.com.br/blog/2010/06/21/testando-a-rede-com-o-iperf-gerador-de-trfego/), que explica o funcionamento da ferramenta Iperf.