O processo de transição do IPv4 para o IPV6, não se deu de forma instantânea, mas de modo gradativo, ou seja, foi implantado o IPv6 (Internet Protocol version 6) conforme o IPv4 continuou sendo usado e com o cuidado para que o usuário final não sofresse qualquer impacto durante esse processo.

Em 1993, o prazo estipulado para que o IPv6 viesse à tona e estivesse em uso por grande parte dos dispositivos, foi de 10 anos, mas algumas empresas como a Google, o Facebook e o Yahoo! saíram na frente e começaram de antemão implantar o novo protocolo em suas redes.

No processo de transição entre um protocolo e outro, são adotadas técnicas para se obter uma certa compatibilidade entre os protocolos, entre elas:

- Pilha dupla/Dual stack: Como sugere o nome, este tipo de uso permite que os dois IPs (IPv4 e IPv6) sejam utilizados simultaneamente no mesmo equipamento, ou seja, o nó que trabalha em pilha dupla tem a capacidade de se comunicar com dispositivos de ambos os protocolos. Ao receber o pacote, o equipamento decide qual IP usar no processamento do mesmo, assim como na comunicação com outros dispositivos decide por qual IP irá enviar o pacote;
- Tradução: Neste tipo os equipamentos que utilizam IPv6 ganham a capacidade de traduzir os dados em IPv4 para que os dispositivos possam lê-los;
- Tunelamento: Possibilita que redes IPv6 se comuniquem utilizando uma rede IPv4 como túnel, ou vice-versa. Esse processo ocorre da seguinte forma: Os pacotes são encapsulados ao sair da rede IPv6, para que possam passar pela rede IPv4 e assim que saem da rede IPv4 com destino à rede IPv6 novamente, são decodificados. Para fazer o tunelamento, deve ser feita a configuração no roteador, após as configurações básicas (IP, Gateway e Máscara). Será criado o túnel de encapsulamento 6in4, possibilitando que os dispositivos IPv6 ligados à rede, possam trafegar via internet IPv4.

A necessidade dessas transições se dá pelo fato de que o IPv6 não é a continuidade do IPv4 e sim uma solução para o esgotamento de endereços presente no mesmo, por isso os dois não tem compatibilidade direta.

Quando o IPv4 foi criado, não se tinha ideia da proporção que a internet tomaria. Outro ponto que também pouco foi levado em consideração foi a segurança da rede.

![[Untitled 11.png|Untitled 11.png]]

Após o processo de transição, onde o IPv6 já estará devidamente implantado, o IPv4 deixará de ser utilizado vagarosamente pelos dispositivos.

O surgimento das tecnologias móveis, foi o principal motivo do esgotamento dos endereços do IPv4, onde uma grande quantidade de pessoas tem acesso à internet, além do surgimento do conceito de IOT (Internet das coisas) onde diversos equipamentos utilizados no nosso dia-a-dia se conectam à internet, entre eles: Carros, TVs, geladeiras, entre outros.

![[Untitled 1 5.png|Untitled 1 5.png]]

Considerando que a quantidade de habitantes da terra ultrapassam os 7,5 bilhões, que o IPv4 suporta apenas 4 bilhões e que boa parte dos habitantes conectados obtém mais de um dispositivo (considerando o conceito de IOT), a necessidade de acelerar este processo de transição é visível, tendo em vista que o IPv6 suporta cerca de 79 octilhões vezes mais endereços que o IPv4, além de ser superior ao IPv4 em segurança e desempenho. O IPv6 utiliza 128 bits para endereçamento enquanto o IPv4 utiliza apenas 32 bits.

No período de implantação do novo protocolo é necessário utilizar-se dessas técnicas para conectar redes IPv6 à internet, que em sua predominância ainda é IPv4. Desta forma o processo de transição entre um protocolo e outro é relativamente simples, porém o uso do IPv6 ainda não é tão grande como deveria ser e o esgotamento do IPv4 é iminente à medida em que a demanda de dispositivos é cada vez maior em contrapartida com a quantidade de endereços disponíveis.

Durante este processo de transição é usada uma técnica de tradução chamada CGN (Carrier Grade NAT), que é aplicada a nível de operadora (grande porte). A principal desvantagem é a redução da velocidade, seguida da defasagem no controle da segurança da rede, gerando dificuldade de identificar IPs na rede. Porém o não uso desta técnica causaria ainda mais dificuldades no processo de transição entre as versões de IP.

Uma outra técnica utilizada neste processo é a 6Over4 que embute o IPv6 em um pacote IPv4, conforme explicada pelo NicBr (2017).

Túneis 6over4 (IPv6-over-IPv4)

Quando a utilização de pilha dupla não é possível, uma das alternativas é a utilização de túneis. As técnicas de tunelamento fazem o encapsulamento de pacotes IPv6 em pacotes IPv4. Este encapsulamento é conhecido como 6in4 ou IPv6-in-IPv4 (RFC 4213). Ele consiste em colocar o pacote IPv6 dentro de um pacote IPv4, adequar os endereços de origem e destino para o IPv4 e colocar no cabeçalho o tipo 41 (29 em hexadecimal). Esse tipo de encapsulamento é conhecido por 6in4,  ou como “protocolo 41”. Quando o destino receber o pacote com tipo 41 ele irá remover o cabeçalho IPv4 e tratar o pacote como IPv6. A figura 4.1 ilustra esse comportamento. Também é possível, de forma análoga, encapsular pacotes IPv4 em pacotes IPv6, técnica conhecida como 4in6. Algumas das técnicas de transição estudadas mais à frente fazem isso.

(NiC BR IPV6)

**Técnicas de Transição IPv6 - Tunelamento**

[https://www.youtube.com/watch?v=81PCOyxUHh4](https://www.youtube.com/watch?v=81PCOyxUHh4)

Túneis 6over4 (IPv6-over-IPv4)

Quando a utilização de pilha dupla não é possível, uma das alternativas é a utilização de túneis. As técnicas de tunelamento fazem o encapsulamento de pacotes IPv6 em pacotes IPv4. Este encapsulamento é conhecido como 6in4 ou IPv6-in-IPv4 (RFC 4213). Ele consiste em colocar o pacote IPv6 dentro de um pacote IPv4, adequar os endereços de origem e destino para o IPv4 e colocar no cabeçalho o tipo 41 (29 em hexadecimal). Esse tipo de encapsulamento é conhecido por 6in4,  ou como “protocolo 41”. Quando o destino receber o pacote com tipo 41 ele irá remover o cabeçalho IPv4 e tratar o pacote como IPv6. A figura 4.1 ilustra esse comportamento. Também é possível, de forma análoga, encapsular pacotes IPv4 em pacotes IPv6, técnica conhecida como 4in6. Algumas das técnicas de transição estudadas mais à frente fazem isso.

(IPV6.BR. Transição. Disponível em: . Acesso em: 23 out. 2017.)

Outra técnica utilizada é o Dual Stack Lite. Esta técnica pode ser usada em casos em que a operadora oferece IPV6 nativo aos usuários. A implantação desta técnica requer um equipamento chamado AFTR (Adress Family Transition Router) que implementa um CGN (Carrier Grade NAT) na rede da operadora e então, é criado um túnel IPv4 entre o AFTR e o CPE (Customer Premise Equipment, termo utilizado para definir um equipamento que se localiza dentro das instalações do cliente) para que os dados em IPv4 possam trafegar dentro da rede IPv6.

**CGNAT NAT444**

[https://www.youtube.com/watch?v=dRIOPyf6Tx8](https://www.youtube.com/watch?v=dRIOPyf6Tx8)

O NAT444 tem sido usado na tentativa de prolongar a vida útil do IPv4 na Internet. Este mecanismo fere o princípio de comunicação fim a fim da Internet e seu uso deve ser evitado ao máximo. Alternativas que levem as redes na direção de redes somente IPv6 são preferíveis, assim como alternativas que usem métodos stateless e que mantenham a complexidade nas extremidades da rede.

Se usado, o NAT444 deve acompanhar a implantação do IPv6 nativo para os usuários. Não deve ser usado isoladamente.

O NAT444 é descrito no em draft-shirasaki-nat444-05 e também é conhecido como LSN (Large Scale NAT) ou CGN (Carrier Grade NAT). Este mecanismo atribui um IPv4 privado para cada um dos usuários de um ISP, de forma semelhante ao que já é normalmente feito em redes domésticas e em diversas redes corporativas. Ou seja, os usuários conviverão, nesse caso, com duas camadas de NAT.

A utilização desta técnica resolveria, de forma provisória, o problema da falta de endereços IPv4, já que eles seriam largamente reutilizados, mas o custo seria comprometer as conexões fim a fim e possivelmente a “quebra” de diversas aplicações hoje existentes.

Pode-se argumentar que o NAT já é usado normalmente e que não há prejuízo na utilização da Internet por conta disso. Isso não é verdade. O NAT, na rede dos usuários, por si só, já é prejudicial, embora tenha desempenhado um importante papel nos últimos anos para a conservação dos endereços IPv4 na Internet. Técnicas como servidores STUN, uPnP e outras foram desenvolvidas para restaurar, parcialmente, a comunicação fim a fim perdida com uma camada apenas de NAT. Com o uso de NAT444 elas deixarão de funcionar.

Outro ponto a considerar é que essa técnica é cara, exigindo equipamentos com grande poder de processamento. Investimentos altos tendem a ser politicamente conservados dentro de grandes corporações, o que pode levar a um atraso na adoção do IPv6.

Do ponto de vista estritamente técnico, é importante considerar a escolha do bloco de IPs a ser usado no NAT. Como o uso dos blocos da RFC1918 é comum nas redes dos usuários, qualquer bloco escolhido dentre os disponíveis pelo provedor fatalmente colidirá com o bloco de algum de seus clientes. Existe uma proposta em estudo para a reserva de um novo bloco, exclusivo para a utilização em situações onde houver duplo NAT. O ARIN prontificou-se a ceder o bloco em questão e a proposta está sendo analisada pelo IETF: draft-weil-shared-transition-space-request-15.

Devido ao rapido esgotamento do IPv4, podem existir situações em que essa técnica terá de ser utilizada. Seu uso muitas vezes é incentivado por fabricantes de equipamentos, talvez devido ao alto custo dos equipamentos necessários para sua implementação.

**NAT64, DNS64 e 464XLAT**

[https://www.youtube.com/watch?v=ZUWcLoK1gSQ](https://www.youtube.com/watch?v=ZUWcLoK1gSQ)

As técnicas de transição são importantes para garantir a interoperabilidade entre as duas versões do protocolo IP , durante a fase de transição adotar técnicas para a coexistencia entre os "dois mundos" é de suma importancia, deixando o processo transparente para o usuário.