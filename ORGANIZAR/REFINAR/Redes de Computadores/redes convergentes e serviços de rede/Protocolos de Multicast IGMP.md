**Introdução**

Nas redes de transmissão de sinas, existem três tipos de tráfego: Unicast, Broadcast e Multicast, sendo que o Unicast tem a função de enviar dados da origem para o destino de modo ponto a ponto, o Broadcast envia de um para muitos dentro de uma mesma rede ou su-brede ou LAN e o Multicast tem como finalidade o envio das informações para mais de um endereço indistintamente, a diferença entre Broadcast e Multicast é o que o envio é seletivo e pode ser enviado em uma WAN, utilizando o minimo de banda possível.

Um breve revisão do modelo TCP/IP destaca a camadas que são baseadas em 4 níveis:Host/Rede;Inter-Rede;Transporte e Aplicação, sendo que as camadas de destaque para a adoção do IGMP são as camadas de Enlace, Rede transporte e aplicação.

**Transmissão Unicast => direcionada, destino bem conhecido**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/0/3/220386/6636-01.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/0/3/220386/6636-01.jpg)

Tráfego Unicast

**Transmissão Broadcast =>para todos que estão no mesmo domínio**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/7/222760/6638-01.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/7/222760/6638-01.jpg)

Tráfego Broadcast

**Transmissão Multicast =>para um grupo**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/7/222759/6637-01.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/2/7/222759/6637-01.jpg)

Tráfego Multicast

Em resumo:

Transmissão Unicast => direcionada, destino bem conhecido

Transmissão Multicast =>para um grupo

Transmissão Broadcast =>para todos que estão no mesmo domínio

**INTRODUÇÃO AO ROTEAMENTO DE PACOTES IP**

https://www.youtube.com/watch?v=y9Vx5l-th9Y

_**O protocolo IGMP permite maior aproveitamento de recursos de uma rede IPTV e descarta tráfego excessivo, mas exige que os equipamentos funcionem nesse modelo**_

Esse tipo de protocolo assimétrico é utilizado pela TV digital como meio de transporte de seu conteúdo.

O IGMP é utilizado em IPTV pois,em sistema, em que um canal é transmitido, somente a um grupo de _**set-top-box**_ que está sintonizado recebe as transmissões, indisponibilizando a distribuição para os canais ociosos, que não estão sintonizados, resultando em um melhor aproveitamento da rede, uma vez que as transmissões são enviadas de modo reservado,  o que acaba otimizando a utilização da rede, já que o fluxo das transmissões são enviadas exclusivamente aos sintonizados.

Um protocolo IGMP garante que o _**set-top-box**_ informe aos equipamentos de rede que ele deseja assistir a determinado conteúdo. No entanto, para funcionar bem, todos os equipamentos devem suportar esse tipo de protocolo - aspecto que os provedores que ofertam TV digital devem estar atentos.

Do contrário, o equipamento de rede (_**switch**_, OLT ou ONU), deixa de ser _**multicast**_ para tornar-se _**broadcast**_. Isso resulta em uma transmissão em que todos os canais são enviados para todos e, consequentemente, há uma geração excessiva de tráfego de rede.

Torna-se necessário também, o controle dos membros de um grupo de _**multicast**_ IP, que modo que este gerencie os grupos e monitore a entrada e a saída dispositivos participantes. Trata-se de um requisito básico de implementações para _**estes dispositivos**_ que desejam enviar e receber pacotes _**multicast**_. As mensagens IGMP são encapsuladas em datagramas IP, com um número de protocolo IP igual a 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/8/304828/20081.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/8/304828/20081.jpg)

Um Set-top box digital é um dispositivo necessário para a recepção de transmissões de TV Digital em televisores que não disponham de conversores integrado. O Set-top box é também conhecido como de IRD ( integrated receiver/decoder).

O IGMP é definido pela RFC 4604, sendo um protocolo de comunicação utilizado por dispositivos finais e roteadores em uma rede IP. Faz parte de um grupo de especificações IP Multicast, muito utilizado para streaming de jogos e vídeos sob demanda.

**OS ENDEREÇOS IP NÃO SÃO TODOS IGUAIS - PARTE 1 DIFERENÇAS ENTRE IPV4 E IPV6**

[**https://www.youtube.com/watch?v=jnuHODaLcO8**](https://www.youtube.com/watch?v=jnuHODaLcO8)

**OS ENDEREÇOS IP NÃO SÃO TODOS IGUAIS - PARTE 2 ENTENDENDO MELHOR ... UNICAST, MULTICAST E BROADCAST :)**

[**https://www.youtube.com/watch?v=63M61wttuMk**](https://www.youtube.com/watch?v=63M61wttuMk)

Funcionamento do IGMP

O primeiro passo é a criação de um grupo, esse processo pode solicitar que seu host se conecte a um grupo específico, e também pode solicitar que seu host saia do grupo. Quando o último processo de um host deixa um grupo, o grupo passa a não mais existir no host. Cada host controla os grupos a que pertencem seus processos atuais. A multidifusão é implementada por rotead ores de multidifusão especiais, que podem ou não ser colocados com os roteadores padrão. Cerca de uma vez por minuto, cada roteador de multidifusão envia um processo de hardware de multidifusão (ou seja, da camada de enlace de dados) para os hosts de sua LAN (endereço 224.0.0.1) solicitando que eles informem os grupos aos quais seus processos pertencem atualmente. Cada host envia respostas a todos os endereços da classe D nos quais está interessado. Esses pacotes de consulta e resposta utilizam um protocolo chamado IGMP (Internet Group Management Protocol), que é um pouco semelhante ao ICMP. Ele tem apenas dois tipos de pacotes: consulta e resposta, cada um com um formato fixo simples, contendo algumas informações de controle na primeira palavra do campo de carga útil, e um endereço da classe D na segunda palavra. O IGMP é descrito na RFC 1112.11 O roteamento por multidifusão é feito com base no uso de árvores de amplitude. Cada roteador de multidifusão troca in formações com seus vizinhos usando um protocolo de vetor de distância modificado. Dessa forma, cada um dos vizinhos é capaz de construir uma árvore de amplitude que abrange todos os membros do grupo. Várias otimizações são usadas para podar a árvore, a fim de eliminar roteadores e redes que não interessam a determinados grupos. O protocolo faz uso intenso do recurso de tunneling para não incomodar os nós que se encontram fora da árvore de amplitude.

(Redes de Computadores Andrew Samuel Tanenbaum,)

**PARA CONHECER SOBRE OS DISPOSITIVOS QUE COMPÕEM A TRANSMISSÃO DIGITAL PARA IPTV E CONFIGURAÇÃO DO TRAFEGO MULTICAST, VISITE OS SITES:**

https://www.youtube.com/watch?feature=player_detailpage&v=ydNuz7rGJ2A

https://www.youtube.com/watch?v=Gfe7mE-f4HQ

http://www.cisco.com/c/en/us/td/docs/switches/datacenter/nexus1000/sw/4_0_4_s_v_1_3/troubleshooting/configuration/guide/n1000v_t