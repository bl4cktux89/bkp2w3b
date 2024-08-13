a camada de aplicação é um termo denominado pela arquitetura OSI para definir a 7º camada de uma estrutura vertical onde uma camada superior utiliza o serviço da camada inferior e a camada inferior presta serviço para a camada superior. é a camada responsável por prover serviços e aplicações que serão utilizados pelos usuários da rede por meio de programas de acesso à WEB (browser), e-mail, transferência de arquivos, jogos em rede, aplicativos sociais, voz sobre IP, entre outras diversas aplicações e serviços. também é a camada de número 5 da arquitetura TCP/IP (quatro do modelo antigo) que engloba a camada de apresentação e sessão. Desta parte em diante vamos tratar apenas da arquitetura TCP/IP uma vez que é a arquitetura mais utilizada no ambiente de redes. as figuras 1 e 2 apresentam a arquitetura OSI e TCP/IP considerando alguns protocolos das camadas que são definidos por as entidades de Hardware e Software. vale lembrar que a camada de transporte e aplicação são somente entidades de software que “rodam” nos sistemas finais, ou seja, nos computadores dos usuários finais em sua maioria.

efetivamente, podemos definir que o encaminhamento das informações ou dados, em uma rede de computadores ocorre apenas nas camadas física, enlace e rede, que formam a estrutura da Internet. as camadas de transporte e aplicação somente são processadas nos pontos finais.

no contexto deste curso estaremos abordando os principais protocolos da camada de aplicação e analisando com o software _**wireshark**_ que permite mostrar a dinâmica destes protocolos (funcionamento do mesmo) em detalhes. Sugerimos aos alunos que instalem este software que funcionará como apoio ao curso no entendimento dos diversos protocolos das camadas de aplicação e transporte.

entre as aplicações da Internet mais populares estão o correio eletrônico (já populares nas décadas de 1970 e 80), o acesso remoto – Telnet, busca na web utilizando DNS, transferência de arquivos, grupos de discussão e as redes sociais como Facebook e vídeos como Netflix, Youtube, entre outros.

estas aplicações são encapsuladas em protocolos da camada de transporte como o TCP que é orientado a conexão e tem garantia de entrega e o UDP não orientado a conexão e não garante a entrega, indicado para aplicações em tempo real como voz e vídeo, por exemplo, no transporte de _**codecs**_ sobre RTP.

![[app_college.jpg]]

![[Untitled 46.png|Untitled 46.png]]

Para entendermos melhor a camada de aplicação faremos uma pequena revisão nas arquiteturas cliente-servidor e par-a-par.

Na arquitetura cliente-servidor temos basicamente 2 elementos:

- O cliente que tem a função de buscar informações ou interagir com o servidor;
- O servidor tem a função de responder as solicitações dos clientes;

![[app_college2.jpg]]

  

no lado do usuário “roda” o processo usuário (software de processo) e no lado do servidor “roda” o processo par (processo servidor) que instancia a busca ou guarda de informações, por exemplo, em banco de dados, conforme apresentado na figura 4.

na arquitetura CS há uma estação sempre em funcionamento, denominado servidor, que atende as requisições de diversos outros elementos de rede ou estações de usuários, denominado cliente. um bom exemplo é o acesso a uma página na web onde se tem um processo cliente (browser ou navegador da internet – Internet Explorer, Chrome, etc.) e um processo servidor que responde enviando o objeto solicitado. Pode-se observar que nesta arquitetura os clientes não se comunicam diretamente uns com os outros.

![[app_college3.jpg]]

  

em uma arquitetura P2P (peer-to-peer) par-a-par, existe uma certa confiança, mesmo que mínima na outra ponta ou no par, que deseja trocar informações. as aplicações se conectam diretamente entre as duplas de elementos de rede que são controlados pelos usuários. muitas aplicações são baseadas em P2P como, por exemplo, o BitTorrent, o Skype entre outras. pode-se dizer que o Skype é uma arquitetura hibrida uma vez que a aplicação consulta um servidor para controle de usuário que estão, por exemplo, _**on-line,**_ mas, durante a conversação a ligação é par-a-par.

o principal objetivo é a transmissão de arquivos entre pares e seu surgimento possibilitou, hoje em dia, o compartilhamento em massa, principalmente de músicas e filmes. Com a crescente utilização da rede P2P para este fim, cada vez mais surgem programas, porém nem sempre eles atendem às expectativas do usuário. Diversas redes operam nestes moldes de compartilhamento, entre elas Kademlia, Gnutela, Kad Network e SoulSeek. Alguns programas valem a pena ser citados quando o assunto é compartilhamento P2P, entre eles o SoulSeek, eMule, LimeWire, Shareaza, DreaMule, iMesh e Morpheus.

Uma vez entendido estas arquiteturas, pode-se concluir que a comunicação na rede é feita por meio de processos sendo um no lado cliente e outro no lado cliente ou servidor dependendo da arquitetura. Uma aplicação consiste em pares de processos que enviam e recebem mensagens uns para os outros por meio de uma rede de comunicação de dados. Por exemplo, na aplicação WEB o software de navegação troca mensagens com o software do servidor (Ex: Apache). No contexto de uma sessão de comunicação, quem inicia a comunicação (primeiro a contatar) é rotulado cliente e o que espera ser contatado e denominado servidor.

### **A interface entre o processo e a rede de computadores**

Na maioria das aplicações existem um par de processos comunicantes enviando mensagens um para o outro. Toda a mensagem enviada deve passar por diversas redes até chegar ao destino referenciado por um endereço lógico. Um processo envia mensagens por meio de uma interface denominada _**socket**_. Mas, o que é um _**socket**_? Um _**socket**_ é um tipo de porta que existe tanto no processo emissor como no processo receptor. A informação ao chegar no destino passa pelo socket que então executa alguma ação sobre a mensagem. A figura 5 apresenta a posição do socket na arquitetura.

![[app_college4.jpg]]

Pode-se se observar que um socket é um processo que envia mensagens para a rede e recebe mensagens dela através de uma interface. Se posiciona entre um processo na camada de aplicação e a camada de transporte e tem a função de identificar o processo receptor que deve ser especificado pelo endereço do elemento de rede e um identificador que especifica o processo receptor no elemento de rede no destino. É a combinação de um endereço IP e um número de porta, muito parecido com o final de uma conexão telefônica que é a combinação de um número de telefone e uma determinada extensão.

Com base nesse endereço, _**sockets**_ de internet entregam pacotes de dados de entrada para o processo ou thread de aplicação apropriado.

Portanto, um protocolo de camada de aplicação define:

- Os tipos de mensagens trocadas.
- A sintaxe dos vários tipos de mensagens, tais como os campos da mensagem e como os campos são delineados.
- A semântica dos campos, isto é, o significado da informação nos campos.
- Regras para determinar quando e como um processo envia mensagens e responde a mensagens.