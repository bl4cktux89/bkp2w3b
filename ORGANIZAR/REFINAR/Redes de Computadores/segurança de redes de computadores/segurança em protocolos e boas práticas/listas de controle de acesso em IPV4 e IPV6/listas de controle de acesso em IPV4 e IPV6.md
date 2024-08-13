### Introdução

Quando nós pensamos em segurança de redes, provavelmente, os firewalls são os primeiros mecanismos que vem a mente. Os firewalls são constituídos de um conjunto de regras permissivas que permitem ou não a passagem do tráfego que entra ou sai de suas interfaces. Algumas dessas mesmas regras, conhecidas como ACL (Lista de Controle de Acesso) podem ser escritas em roteadores e switches com o objetivo de prevenir o acesso indevido a esses dispositivos. Além disso, através das ACLs é possível filtrar o tráfego baseado nas informações de endereçamento IPv4/IPv6 e protocolos da camada de aplicação.

É importante salientar que as ACLs não são empregadas apenas com o objetivo de proteger o acesso a um determinado de dispositivo ou rede/sub-rede, mas também são empregadas em fluxos de dados que serão tratados por técnicas de NAT (Tradução de endereços de rede) e QoS (Qualidade de Serviço).

### Funcionamento das ACLs

Uma ACL é composta por várias linhas de regras que são comparadas com as informações dos pacotes de dados que entram ou saem de um dispositivo. Sempre que ocorre uma correspondência entre o conteúdo do pacote e a regra da ACL uma ação de PERMIT (permissão) ou DENY (Negação) é executada. Caso não ocorra uma correspondência com a regra daquela linha, os pacotes de dados são testados na próxima linha (esse processo se repete até que exista uma correspondência). Se não houver nenhuma correspondência ao passar por todas as linhas de regras, normalmente, existirá uma regra que negará todo o tráfego. No fluxograma abaixo é mostrado esse processo.

![[Untitled 93.png|Untitled 93.png]]

### Tipos de ACL

Existem basicamente dois tipos de ACL no contexto de equipamentos Cisco: standard (padrão) e extended (estendidas). A diferença está associada com forma de análise dos pacotes de dados durante o processo de filtragem (Filippetti, M. A. 2017):

- ACL standard: Examina apenas o campo de endereço IP de ORIGEM.
- ACL extended: Além de examinar os endereços IPs de origem e destino do pacote, tem a capacidade de analisar também o campo - protocolo - do cabeçalho IP, permitindo dessa forma, avaliar os protocolos ICMP (1), OSPF (89), EIGRP (88). UDP (17), TCP (6) dentre outros. Proporciona também a capacidade de analisar, inclusive, os protocolos da camada de Aplicação, de acordo com as respectivas portas.

As ACLs são identificadas por número ou nomes. As ACLs  padrão e estendidas no formato numerado estão dentro do intervalo mostrado na tabela que segue.

![[Untitled 1 57.png|Untitled 1 57.png]]

Quando se cria uma ACL ela deve ser associada a uma interface do equipamento para analisar o tráfego que entra (inbound) ou sai (outbound). É importante salientar que, quando se aplica uma ACL outibound, o tráfego será analisado após o processo de roteamento, enquanto o tráfego é analisado primeiramente pela ACL de entrada e posteriormente pelo processo de roteamento.

### Diretrizes para criação de ACLs

Segue abaixo algumas recomendações da Cisco para criação e aplicação de ACLs (Cisco System, 2020):

- Use as ACLs em roteadores com firewall posicionados entre a rede interna e uma rede externa como a Internet.
- Use as ACLs em um roteador posicionado entre duas partes da rede para controlar o tráfego que chega ou sai de uma determinada parte da rede interna.
- Configure as ACLs em roteadores de borda, que são roteadores situados nas bordas de suas redes.
- Configure ACLs para cada protocolo de rede configurado nas interfaces do roteador de borda (Cisco System, 2020).
    - **Uma ACL por protocolo:** Uma ACL deve ser definida por interface para cada protocolo ativado na interface.
    - **Uma ACL por direção:** Duas ACLs separadas devem ser criadas para controlar o tráfego de entrada e de saída, ou seja, uma ACL in e out para IPv4 e uma ACL in e out para IPv6.
    - **Uma ACL por interface** - as ACLs controlam o tráfego de uma interface, por exemplo, GigabitEthernet 0/0.

### Posicionamento de ACLs

As ACLs devem ser posicionas onde houver o maior impacto sobre a eficiência. Basicamente as regras são:

ACL padrão: As ACLs padrão avaliam apenas o endereço de origem do tráfego e, por isso, devem ser posicionadas o mais próximo possível do destino, conforme figura abaixo.

![[Untitled 2 45.png|Untitled 2 45.png]]

ACLs estendidas: Como as ACLs estendidas possuem a capacidade de avaliar os endereços de origem e destino, assim como o protocolo, elas devem ser posicionadas o mais próximo possível a origem do tráfego a ser filtrada, conforme mostrado na figura que segue.

![[Untitled 3 31.png|Untitled 3 31.png]]

Criação de ACLs padrão IPv4

A sintaxe para criação de uma ACL padrão numerada IPv4 é a seguinte:

`1.` `access-list [número] [permit | deny] [rede | host de origem] [máscara curinga] [log]`

A opção log registra a ocorrência de correspondência do pacote de dados com a regra. A seguir é mostrado uma ACL padrão numerada, com base na anterior, que bloqueia todo o tráfego que tenha origem na rede 192.168.10.0 /24 aplicada com outbound na interface g0/0 de R3. O parâmetro remark é utilizado para fazer a descrição de uma ACL

`1.` `R3(config)# access-list 1 remark Bloqueia o tráfego da rede 192.168.10.0 para a rede 192.168.30.0` `2.` `R3(config)# access-list 1 deny 192.168.10.0 0.0.0.255`

Após a criação de uma ACL ela deve ser aplicada a uma interface. A sintaxe é mostrada abaixo.

`1.` `access-group [número] [ in | out ]`

Para o exemplo a configuração fica:

`1.` `R3(config)# int g0/0` `2.` `R3(config)# ip access-group 1 out`

### Máscara curinga

A máscara curinga (ou wildcard) são utilizadas para informar qual a parte do endereço IP de origem ou destino deve ser considerada ou ignorada no processo de filtragem. Inicialmente, podemos considerar que as máscaras curingas representam o inverso da máscara de sub-rede. Em outras palavras substituindo "1s" por "0s" (Filippetti, M. A. 2017).

Tendo em mente o exemplo anterior, desejávamos bloquear todo o tráfego da rede 192.168.10.0 que possui máscara 255.255.255.0 (/24), a sua máscara curinga fica 0.0.0.255. isso significa que a parte do endereço IP a ser considerada pela ACL corresponde aos três primeiros octetos da máscara curinga, e não importa quais sejam os bits do quarto octeto. Portanto, a seguinte regra pode ser adotada (Cisco System, 2020):

- **Se o bit da Máscara curinga for igual a 0 faça a correspondência com o valor do bit correspondente ao endereço IP.**
- **Se o bit da Máscara curinga for igual a 1 ignore o valor do bit correspondente no endereço IP.**

**Exemplo 1: Endereço IP 192.168.0.1 e wildcard 0.0.0.0**

![[Untitled 4 25.png|Untitled 4 25.png]]

Exemplo 2: Endereço IP 192.168.0.1 e wildcard 255.255.255.255

![[Untitled 5 22.png|Untitled 5 22.png]]

Exemplo 3: Endereço IP 192.168.0.1 e wildcard 0.0.0.255

![[Untitled 6 15.png|Untitled 6 15.png]]

Exemplo 4: Endereço IP de sub-rede 192.168.16.0 e wildcard 0.0.15.255.

![[Untitled 7 13.png|Untitled 7 13.png]]

**DICA!!!**

**Calcular as máscaras curinga pode ser um desafio. Um método de atalho é subtrair a máscara de sub rede de 255.255.255.255. Ex: máscara de Sub-rede /26 = 255.255.255.192. A máscara curinga é:**

**255.255.255.255 _****255.255.255.192**  **0  .  0  .  0  . 63 -> Máscara curinga**

### Palavras chave de máscara curinga

As palavras chaves **any** e **host** podem ser substituídas pelas máscaras curingas 255.255.255.255 e 0.0.0.0 respectivamente. O efeito prático é o mesmo em uma ACL. Veja os exemplos abaixo:

**Exemplo 5:** Permitir o endereço IP 192.168.1.1. A regra faz a correspondência de todos os bits do endereço.

access-list 2 permit 192.168.1.1 **0.0.0.0**

ou

access-list 2 permit **host** 192.168.1.1

**Exemplo 6:** Permite qualquer (any) endereço. A regra ignora todos os bits do endereço

access-list 3 permit **0.0.0.0 255.255.255.255**

ou

access-list 3 permit **any**

### Simulação 1 - ACL Padrão

Para executar a simulação que segue você deve ter instalado o Packet tracer 7.3. ou superior. Baixe o arquivo com extensão .pka e o roteiro em .pdf.

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/2/9/3/5/8293532/59446.rar)

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/2/9/3/5/8293532/59446.rar)

### ACLs numeradas IPv4 estendidas

Como já comentado, as ACLs estendidas têm a capacidade de avaliar os endereços IPs de origem e destino do pacote, assim como os número de porta TCP e UDP (de origem e destino). Elas são muito mais específicas e nos permitem criar regras que permitem um maior controle sobre o tráfego. A sintaxe para sua escrita é mostrada abaixo:

`1.` `access-list [número] [permit | deny] [protocolo] [host de origem | rede de origem] [wildcard] [host de destino | rede de destino] [wildcard] [parâmetro do protocolo]`

**Exemplo 7:** Com base na figura abaixo, a seguinte regra deve ser criada:

1. O acesso HTTP será permitido a todos os hosts da rede 192.168.1.0 /24 ao servidor localizado em 192.168.2.100.
2. O Acesso ao serviço FTP localizado no mesmo servidor http será permitido apena ao PC-1 192.168.1.10 /24.
3. Qualquer outro tráfego deverá ser negado.

**Solução:**

`1.` `access-list 150 permit tcp 192.168.1.0 0.0.0.255 host 192.168.2.100 eq 80` `2.` `access-list 150 permit tcp host 192.168.1.10 host 192.168.2.100 eq 21` `3.` `access-list 150 permit tcp host 192.168.1.10 host 192.168.2.100 eq 20` `4.` `access-list 150 deny ip any any`

### Simulação 2 - ACL estendida

Baixe o arquivo com extensão .pka e execute a simulação de acordo com o roteiro presente dentro do mesmo arquivo. Para realizar essa simulação você deve ter o Simulador Packet Tracer 7.3 ou superior.

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/1/9/2/4/8192418/59449.rar)

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/1/9/2/4/8192418/59449.rar)

### ACLs nomeadas

Existe também a possibilidade de configuração de ACLs nomeadas que substituem a numeração das ACLs padrão e estendida. Veja os exemplos abaixo

**Exemplo 8:** ACL nomeada IPv4 padrão que bloqueia o acesso da rede 192.168.10.0 /24 (Rede ADM) e permite todos os demais tráfegos. A ACL é aplicada a interface g0/0 como **in**.

`1.` `R3(config)# ip access-list standard bloqueia_ADM` `2.` `R3(config-std-nacl)# deny 192.168.10.0 0.0.0.255` `3.` `R3(config-std-nacl)# permit any` `4.` `R3(config-std-nacl)\#exit` `5.` `R3(config) # int g0/0` `6.` `R3(config-if) # ip access-group bloqueia_ADM in`

**Exemplo 9:** **ACL estendida rescrita com base no exemplo 7**

`1.` `R3(config)# ip access-list extented acesso_privado` `2.` `R3(config-ext-nacl)# permit tcp 192.168.1.0 0.0.0.255 host 192.168.2.100 eq 80` `3.` `R3(config-ext-nacl)# permit tcp host 192.168.1.10 host 192.168.2.100 eq 21` `4.` `R3(config-ext-nacl)# permit tcp host 192.168.1.10 host 192.168.2.100 eq 20` `5.` `R3(config-ext-nacl)# deny ip any any` `6.` `R3(config-std-nacl)\#exit` `7.` `R3(config) # int g0/0` `8.` `R3(config-if) # ip access-group acesso_privado in`

**SAIBA MAIS...**

Após a escrita de uma ACL é possível editá-la, excluindo, adicionando ou modificando. Para saber como realizar esse procedimento acesse: [**https://www.cisco.com/c/pt_br/support/docs/security/ios-firewall/23602-confaccesslists.html**](https://www.cisco.com/c/pt_br/support/docs/security/ios-firewall/23602-confaccesslists.html)

### ACL IPv6

Os mesmos princípios de funcionamento das ACLs IPv4 se aplicam as ACLs IPv6. No entanto, existem algumas pequenas diferenças:

- ACL IPv6 são sempre nomeadas
- ACL IPv6 são sempre estendidas.
- Não existe máscara curinga (wildcard).
- Para aplicar a regra a interface se utiliza o comando ipv6 traffic-filter [nome da lista] [ in | out ].

**Exemplo 10: Aplicação de ACL IPv6 de acordo com o cenário do exemplo 7.**

`1.` `R3(config)# ipv6 access-list acesso_privado_ipv6` `2.` `R3(config-ipv6-acl)# permit tcp 2001:cafe:1:1::/64 host 2001:cafe:1:2::100 eq 80` `3.` `R3(config-ipv6-acl)# permit tcp host 2001:cafe:1:1::10 host 2001:cafe:1:2::100 eq 21` `4.` `R3(config-ipv6-acl)# permit tcp host 2001:cafe:1:1::10 host 2001:cafe:1:2::100 eq 20` `5.` `R3(config-ipv6-acl)# deny ip any any` `6.` `R3(config-ipv6-acl)\#exit` `7.` `R3(config) # int g0/0` `8.` `R3(config-if) # ipv6 traffic-filter acesso_privado_ipv6 in`

### Simulação 3 - ACL IPv6

Baixe o arquivo com extensão .pka e execute a simulação de acordo com o roteiro presente dentro do mesmo arquivo. Para realizar essa simulação você deve ter o Simulador Packet Tracer 7.3 ou superior.