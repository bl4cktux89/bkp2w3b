  

O processo de transição do IPv4 para o IPV6, está acontecendo de modo gradual, ou seja, está sendo  implantado o IPv6 (_**Internet Protocol version 6**_) conforme o IPv4 continua sendo usado e com o devido cuidado para que o usuário final não perceba a presença deste processo ou seja impactado pela migração.

A principal motivação para o início da criação do IPv6, em 1990, foi o esgotamento de endereços disponíveis no IPv4, devido à grande demanda de dispositivos encontrada atualmente na rede mundial (internet). Um fator determinante para este crescimento exacerbado foi o surgimento da IOT (Internet das coisas) que trouxe uma gama de dispositivos novos que têm a possibilidade de se conectarem a internet. Além disso, o IPv6 traz uma promessa de otimização da segurança sobre os equipamentos e dispositivos que utilizarem a nova versão do protocolo.

  

![[Untitled 8.png|Untitled 8.png]]

  

Em 1993, o prazo estipulado para que o IPv6 viesse à tona e tivesse em uso por grande parte dos dispositivos, foi de 10 anos, mas algumas empresas como a Google, o Facebook e o Yahoo! saíram na frente e começaram de antemão implantar o novo protocolo em suas redes.

No processo de transição entre os protocolos, são adotadas técnicas para se obter a compatibilidade entre os protocolos, podendo ser classificadas de acordo com suas funcionalidades:

- **Pilha dupla:** IPv4 e do IPv6 ativos no mesmo equipamento, sendo considerada uma técnica padrão e utilizada sempre que possível.
- **Túneis:** São utilizados como método para permitir que diferentes equipamentos e ou redes distintas se comuniquem com diferentes versões do protocolo IP.
- **Tradução:** o processo de conversão de pacotes, permite que equipamentos usando IPv6 "conversem" com outros dispositivos que usam IPv4.

Em um primeiro momento o IPv6 era denominado SIPP (_**Simple Internet Protocol Plus**_) e só depois de receber atributos de outros candidatos à vaga de novo protocolo, passou a ter o nome usado atualmente.

O IPv6 carrega uma solução definitiva para os problemas de endereçamento, suportando a demanda mundial de dispositivos usando apenas uma pequena parte de sua capacidade total, em contrapartida com o CIDR e o NAT (_**Network Address Translation**_) que eram soluções provisórias para o problema de capacidade do IPv4. O IPv6 ainda trouxe um aumento na quantidade de endereços _**Multicast**_ (que entrega informação a diversos destinos simultaneamente), além de trazer a função de auto-configuração, poupando o usuário de configurar novamente o dispositivo ao conectar-se em uma rede nova.

- Pilha dupla/_**Dual stack**_: Como sugere o nome, este tipo de uso permite que os dois IPs (IPv4 e IPv6) sejam utilizados simultaneamente no mesmo equipamento, ou seja, o nó que trabalha em pilha dupla tem a capacidade de se comunicar com dispositivos de ambos os protocolos. Ao receber o pacote, o equipamento decide qual IP usar no processamento do mesmo, assim como na comunicação com outros dispositivos decide por qual IP irá enviar o pacote;

Uma grande facilidade que o IPv6 traz consigo é a possibilidade de operar simultaneamente com a versão antiga (IPv4) durante o processo de transição entre as versões. E essa operação simultânea é realizada através das técnicas de transição (Pilha Dupla, Tunelamento e Tradução).

- Tradução: Neste tipo os equipamentos que utilizam IPv6 ganham a capacidade de traduzir os dados em IPv4 para que os dispositivos possam lê-los

  

![[Untitled 1 2.png|Untitled 1 2.png]]

  

A quantidade suportada pelo IPv6 é de 340 undecilhões (340.282.366.920.938.463.463.374.607.431.768.211.456) de endereços, em contrapartida com o IPv4 que suportava apenas um pouco mais que 4 bilhões (levando em consideração o fato de que apenas 3,7 bilhões são destinados a usuários finais e de que a terra abriga atualmente mais de 7,5 bilhões de habitantes).

- Tunelamento: Possibilita que redes IPv6 se comuniquem utilizando uma rede IPv4 como túnel, ou vice-versa. Esse processo ocorre da seguinte forma: Os pacotes são encapsulados ao sair da rede IPv6, para que possam passar pela rede IPv4 e assim que saem da rede IPv4 com destino à rede IPv6 novamente, são decodificados. Para fazer o tunelamento, deve ser feita a configuração no roteador, após as configurações básicas (IP, Gateway e Máscara). Será criado o túnel de encapsulamento 6in4, possibilitando que os dispositivos IPv6 ligados à rede, possam trafegar via internet IPv4.

O IPv6 proporciona mais mobilidade ao usuário pelo fato de ser autoconfigurável e ser prático na alternância entre redes. Um exemplo disso é um notebook que quando desconectado do cabo de rede (RJ-45), conecta-se automaticamente na rede Wireless que já tenha uma senha cadastrada, poupando tempo do usuário.

Outro fato que coloca o IPv6 na frente é o de que seu espaço de endereçamento corresponde à 128 bits, contra 32 bits do IPv4.

O IPv6 ainda conta com um formato mais simples de cabeçalho (identificador do pacote, origem e destino). Conta também com uma otimização de roteamento tendo como princípio a hierarquização da rede.

No IPv6 traz nativamente o uso do IPSec (_**IP Security Protocol**_), uma extensão do IP e ao mesmo tempo, um controle padronizado que zela pela segurança dos dados, pela privacidade do usuário final e também pela integridade das informações.

O IPv6 promove uma otimização de funções que trabalham em tempo real, como as chamadas de voz e de vídeo, além de transmissões ao vivo. Foi selecionado para suceder o IPv4, pois foi o que menos apresentou diferenças perante o mesmo, além de ter uma estratégia de transição melhor que a dos outros candidatos. Ao final todas as boas características desses tais candidatos foram implementadas também ao IPv6.

Após o processo de transição, onde o IPv6 já estará devidamente implantado, o IPv4 deixará de ser utilizado vagarosamente pelos dispositivos.

A necessidade dessas transições se dá pelo fato de que o IPv6 não é a continuidade do IPv4 e sim uma solução para o esgotamento de endereços presente no mesmo, por isso os dois não tem compatibilidade direta.

  

![[Untitled 2 3.png|Untitled 2 3.png]]

  

Quando o IPv4 foi criado, não se tinha ideia da proporção que a internet tomaria. Outro ponto que também pouco foi levado em consideração foi a segurança da rede.

No Windows, todas as versões superiores ao Vista e Server 2008, já obtém o IPv6 como protocolo padrão. No IPv6, os endereços são criados de forma automática pelos roteadores que operam com as duas versões de protocolo.

O novo protocolo proporciona uma otimização na QoS (_**Quality of Service**_, qualidade de serviço em português), onde é proporcionada uma garantia maior na largura de banda.

O surgimento das tecnologias móveis, foi o principal motivo do esgotamento dos endereços do IPv4, onde uma grande quantidade de pessoas tem acesso à internet, além do surgimento do conceito de IOT (Internet das coisas) onde diversos equipamentos utilizados no nosso dia-a-dia se conectam à internet, entre eles: Carros, TVs, geladeiras, entre outros.

No período de implantação do novo protocolo é necessário utilizar-se dessas técnicas para conectar redes IPv6 à internet, que em sua predominância ainda é IPv4. Desta forma o processo de transição entre um protocolo e outro é relativamente simples, porém o uso do IPv6 ainda não é tão grande como deveria ser e o esgotamento do IPv4 é iminente à medida em que a demanda de dispositivos é cada vez maior em contrapartida com a quantidade de endereços disponíveis.

Considerando que as quantidades de habitantes da terra ultrapassa os 7,5 bilhões, que o IPv4 suporta apenas 4 bilhões e que boa parte dos habitantes conectados obtém mais de um dispositivo (considerando o conceito de IOT), a necessidade de acelerar este processo de transição é visível, tendo em vista que o IPv6 suporta cerca de 79 octilhões vezes mais endereços que o IPv4, além de ser superior ao IPv4 em segurança e desempenho. O IPv6 utiliza 128 bits para endereçamento enquanto o IPv4 utiliza apenas 32 bits.

Durante este processo de transição é usada uma técnica de tradução chamada CGN (Carrier Grade NAT), que é aplicada a nível de operadora (grande porte). A principal desvantagem é a redução da velocidade, seguida da defasagem no controle da segurança da rede, gerando dificuldade de identificar IPs na rede. Porém o não uso desta técnica causaria ainda mais dificuldades no processo de transição entre as versões de IP.

Uma outra técnica utilizada neste processo é a 6over4 que envia pacotes IPv6 através de pacotes IPv4.

Outra técnica utilizada é o _**Dual Stack Lite**_. Esta técnica pode ser usada em casos em que a operadora oferece IPV6 nativo aos usuários. A implantação desta técnica requer um equipamento chamado AFTR (Adress Family Transition Router) que implementa um CGN (_**Carrier Grade NAT**_) na rede da operadora e então, é criado um túnel IPv4 entre o AFTR e o CPE (_**Customer Premise Equipment**_, termo utilizado para definir um equipamento que se localiza dentro das instalações do cliente) para que os dados em IPv4 possam trafegar dentro da rede IPv6.

De acordo com o LACNiC, a fase de esgotamento dos blocos IPV4, começaram em 15 de Fevereiro de 2017.