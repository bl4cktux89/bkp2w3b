### Introdução

A adoção de um protocolo de roteamento, deve considerar, diversos aspectos da estrutura de rede, entre eles a Topologia e a finalidade da Rede, esses apectos são importantes, pois ao eleger um protocolo de roteamento, devemos observar suas caracteristicas de escalonamento, crescimento futuro, as características de vantagens e limitações do protocolo implementado.

Aqui apresentaremos os processos de roteamento utilizados por roteadores que usam uma rede com o protocolo IP.

Mas o que é um processo de roteamento?

São regras e configurações usadas para definir como os dados gerados em uma determinada rede devem alcançar outras, ou seja, se for necessário transmitir um pacote de dados de um dispositivo de uma rede para outro, em outra rede, teremos de efetuar o processo de roteamento.

Observe a seguir a resposta apresentada pelo comando "tracert" usado na linha de comando do DOS.

![[Untitled 27.png|Untitled 27.png]]

No exemplo acima, após a digitação do comando "tracert", o equipamento passou a rastrear o caminho realizado na rede para alcançar o endereço de destino solicitado (www.uninove.com.br). Foram realizados nove saltos desde o destino até cada um dos pontos. A cada salto a rede muda quando um novo ponto é alcançado. Assim, se as redes se alteram, os endereços listados no final de cada linha são roteadores, encaminhando pacotes de uma rede à outra. Consequentemente, para os dados saírem de uma rede e alcançar outra, um roteador estará executando essa tarefa.

### Tipos de roteamento

O papel do roteador é direcionar o tráfego para todas as redes selecionadas, e para isso deve conhecer algumas informações, como endereço de destino, rotas existentes nas redes remotas, roteadores vizinhos e qual é a melhor rota a ser selecionada.

Como podemos observar, para um pacote de dados gerado em uma rede alcançar outra, temos de preparar certo tipo de roteamento. Segundo Tanenbaum (2011) Existem três tipos básicos: o estático, o dinâmico e o default.

Brevemente, veremos cada um deles:

- Roteamento estático: essa é uma das tarefas do administrador da rede que, manualmente, cria as tabelas de rotas (routing tables).
- Roteamento default: no tipo de roteamento default, o roteador já possui o conhecimento sobre a existência das redes que estão diretamente conectadas.
- Roteamento dinâmico: nesse processo, o roteador utiliza-se de protocolos de roteamento para fazer a comunicação com os roteadores vizinhos e, automaticamente, gera sua tabela.

Vamos nos prender um pouco mais nas características do "roteamento dinâmico", uma vez que ele apresenta diversos tipos de protocolos. Veremos o RIPng que estamos estudando.

O processo de roteamento utiliza protocolos para encontrar e atualizar tabelas, definindo regras que serão utilizadas para a comunicação com roteadores vizinhos.Existem duas categorias de protocolos de roteamento utilizados em internetworks_**:**_ o IGP e o EGP.

- IGP (Interior Gateway Protocol): usado para a troca de informações entre roteadores que pertencem a uma coleção de redes sob um mesmo domínio administrativo.
- EGP (Exterior Gateway Protocol): protocolo usado para possibilitar a comunicação entre roteadores que estejam em redes distintas.

### Tipos de Protocolo de Roteamento Dinâmico

### Protocolo RIP - versão 1 – RIPv1

Esse tipo de protocolo envia a tabela de roteamento completa a cada 30 s para todas as interfaces conectadas. É um roteamento do tipo "classful" em que todos os dispositivos que estiverem conectados à rede deverão estar sob a mesma máscara.

A configuração desse tipo de roteador é bastante simples. Devemos, em primeiro lugar, excluir as rotas estáticas que por ventura tenham sido estabelecidas. Depois, por meio do comando "config", acessamos o modo de configuração de roteamento e informamos qual rede deve ser propagada.

Vejamos um rápido exemplo:

Roteador x\#config t           Roteador x (config) \#no ip route 192.168.10.0 255.255.255.0 192.168.20.1          Roteador x (config) #no ip route 192.168.50.0 255.255.255.0 192.168.40.2          Roteador x (config) \#router rip          Roteador x (config) \#network 192.168.0.0          Roteador x (config) #^z

Efetuada a configuração, o protocolo RIPv1 identificará as sub-redes existentes utilizando-se das máscaras configuradas no roteador, contudo, por ser "classful", não irá propagar as informações da máscara para a rede.

### Protocolo RIP – versão 2 – RIPv2

O protocolo RIPv2, uma vez que continua sendo um protocolo "distance vector", utiliza a distância existente na rede remota para definir o melhor caminho e também envia sua tabela de roteamento de forma periódica.

A diferença entre o RIPv1 e o RIPv2 está no aumento da escalabilidade, o que o torna o segundo adequado para atender redes de grande porte. Outro ponto diferente é que o protocolo RIPv2 propaga as informações de máscara de rede em suas atualizações.

Vejamos alguns comandos, entre muitos existentes, que permitem verificar as configurações usadas no protocolo RIP:

- sh running – Apresenta toda a configuração do roteador.
- sh ip route – Mostra a tabela completa de roteamento.
- sh ip route rip – Mostra as rotas informadas pelo protocolo RIP.
- sh ip rip database – Mostra o conteúdo da base de dados do protocolo RIP.

### O RIPng

De acordo com o Malkin (2017) na RFC 2080,  O RIPng, (RIP next Generation) é um protocolo de Roteamento dinâmico, IGP( _**Internet Gateway Protocol**_ ) baseado  no Algoritimo Bellman-Ford (_**distance vector**_) de vetor de distância que permite que Roteadores troquem informações sobre as suas rotas/prefixos IPv6 dentro do domínio RIPng, utilizando-se da contagem de saltos como custo para cada prefixo (rede).

Ainda de acordo com a RFC 2080 RIPng é para IPv6 apenas assim como RIPv2 é apenas para IPv4. O RIPv2 e RIPng devem ser considerados dois protocolos independentes sem interação entre eles.

**No exercício abaixo, devemos configurar RIPng (RIPv6) para a seguinte topologia:**

![[Untitled 1 17.png|Untitled 1 17.png]]

Abaixo está a tabela de endereçamento completa:

![[Untitled 2 15.png|Untitled 2 15.png]]

Abaixo estão as Configurações do Roteador. Observe que o comando "ipv6 rip" é usado para habilitar o RIP em uma interface específica. Observe também que "net1" no comando "ipv6 rip net1 enable" é apenas uma nomenclatura atibuida pelo administrador, podendo utilizar qualquer nome. Este comando habilita o processo RIPv6 na interface correspondente.

**Roteador 0**

`1. Router0>en 2. Router0\#configure terminal 3. Router0(config)\#ipv6 unicast-routing 4. Router0(config)\#interface fastEthernet 0/0 5. Router0(config-if)#ipv6 address 2000:1::1/64 6. Router0(config-if)\#no shutdown 7. Router0(config-if)\#exit 8. Router0(config)#interface fastEthernet 0/1 9. Router0(config-if)#ipv6 address 2001::10/64 10. Router0(config-if)#no shutdown 11. Router0(config-if)#exit 12. Router0(config)#ipv6 route 2000:2::/64 2001::20`

**Roteador 1**

`1.` `Router1>enable` `2.` `Router1\#configure terminal` `3.` `Router1(config)\#ipv6 unicast-routing` `4.` `Router1(config)\#interface fastEthernet 0/0` `5.` `Router1(config-if)#ipv6 address 2000:2::1/64` `6.` `Router1(config-if)#ipv6 rip net1 enable` `7.` `Router1(config-if)#ipv6 enable` `8.` `Router1(config-if)\#no shutdown` `9.` `Router1(config-if)\#exit` `10.` `Router1(config)#interface fastEthernet 0/1` `11.` `Router1(config-if)#ipv6 address 2001::20/64` `12.` `Router1(config-if)#ipv6 rip net1 enable` `13.` `Router1(config-if)#ipv6 enable` `14.` `Router1(config-if)#no shutdown` `15.` `Router1(config-if)#exit` `16.` `Router1(config)#interface fastEthernet 1/0` `17.` `Router1(config-if)#ipv6 address 2001:1::10/64` `18.` `Router1(config-if)#ipv6 rip net1 enable` `19.` `Router1(config-if)#ipv6 enable` `20.` `Router1(config-if)#no shutdown` `21.` `Router1(config-if)#exit`

**Roteador 2**

`1.` `Router2>enable` `2.` `Router2\#configure terminal` `3.` `Router2(config)\#ipv6 unicast-routing` `4.` `Router2(config)\#interface fastEthernet 0/0` `5.` `Router2(config-if)#ipv6 address 2000:3::1/64` `6.` `Router2(config-if)#ipv6 rip net1 enable` `7.` `Router2(config-if)#ipv6 enable` `8.` `Router2(config-if)\#no shutdown` `9.` `Router2(config-if)\#exit` `10.` `Router2(config)#interface fastEthernet 0/1` `11.` `Router2(config-if)#ipv6 address 2001:1::20/64` `12.` `Router2(config-if)#ipv6 rip net1 enable` `13.` `Router2(config-if)#ipv6 enable` `14.` `Router2(config-if)#no shutdown` `15.` `Router2(config-if)#exit`

Uma vez que RIP esteja configurado em todos os roteadores, use as ferramentas de diagnóstico usuais, como ping, tracert para verificar a conectividade, conforme mostrado abaixo:

`1.` `PC>tracert 2000:3::2` `2.`   `3.` `Tracing route to 2000:3::2 over a maximum of 30 hops:` `4.`   `5.` `1 2 ms 2 ms 2 ms 2000:1::1` `6.` `2 4 ms 4 ms 4 ms 2001::20` `7.` `3 6 ms 6 ms 6 ms 2001:1::20` `8.` `4 8 ms 8 ms 8 ms 2000:3::2` `9.`   `10.` `Trace complete.`

`1.` `Você também pode ver o banco de dados RIP nos roteadores correspondentes através do seguinte comando:` `2.`   `3.` `Router\#sh ipv6 rip database` `4.` `RIP process "net1" local RIB` `5.` `2000:3::/64, metric 3, installed` `6.` `FastEthernet0/1/FE80::230:F2FF:FEAB:4902, expires in 164 sec` `7.` `2001::/64, metric 2` `8.` `FastEthernet0/1/FE80::230:F2FF:FEAB:4902, expires in 164 sec` `9.` `2001:1::/64, metric 2, installed` `10.` `FastEthernet0/1/FE80::230:F2FF:FEAB:4902, expires in 164 sec` `11.` `2001:2::/64, metric 2, installed` `12.` `FastEthernet0/1/FE80::230:F2FF:FEAB:4902, expires in 164 sec` `13.` `Router#`

**Material Complementar****Cenário prático do RIPng**

_**Saiba mais sobre o cenário prático do RIPng:**_

[**https://www.youtube.com/watch?time_continue=153&v=WrwloYbCl8M**](https://www.youtube.com/watch?time_continue=153&v=WrwloYbCl8M)