**Definição**

O _**Spanning Tree Protocol**_ (STP) é um protocolo de Camada 2 no modelo de referência ISO/OSI responsável por bloquear links redundantes, que causariam a interrupção das comunicações em uma rede local (LAN), automaticamente, mesma na ocorrência de uma mudança na topologia.

**Aplicação**

O protocolo STP, estabelecido pelo padrão IEEE 802.1D – assim como suas variações, o _**Rapid Spanning Tree Protocol**_ (RSTP) e o _**Multiple Spanning Tree Protocol**_ (MSTP) – é um padrão _**de jure**_ essencial para evitarmos um fenômeno chamado _**broadcast storm**_, que ocorre quando algum dispositivo envia mensagens em _**broadcast**_ em uma LAN que possua links redundantes, ou seja, dois ou mais links de conexão entre mesmos dispositivos.

Caso não houvessem mecanismos de proteção na ocorrência desse fenômeno (ou esses protocolos estejam desabilitados na configuração do equipamento), a rede ficaria “inundada” de _**frames**_ (nome dado as mensagens que trafegam na Camada 2), causados por mensagens em _**broadcast**_, fazendo com que, frequentemente, os dispositivos de rede “travem” devido a saturação do processador do switch, por exemplo, pelos processos internos associados ao envio e recebimento desses _**frames**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/1/297124/SEQUENCIA-Broadcasting--PSD.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/1/297124/SEQUENCIA-Broadcasting--PSD.gif)

Exemplo de mensagem em broadcast

São exemplos de mensagens em _**broadcast**_ as requisições do _**Address Resolution Protocol**_ (ARP), protocolo responsável por obter endereços IP em função de endereços MAC; e as requisições do _**Dynamic Host Configuration Protocol**_ (DHCP), protocolo responsável pela configuração automática de endereço IP (e outras configurações relativas associadas a esse endereço IP) em dispositivos finais.

**Funcionamento**

Conforme Donahue (2011), switches gerenciáveis enviam sinais, conhecidos como _**Bridge Protocol Data Units**_ (BPDU), para encontrar caminhos redundantes (_**loops**_) na rede. Através desses BPDUs, o protocolo STP elege um “mestre” da rede (chamado de _**Root Bridge**_), cujo switch tiver menor valor de _**Bridge ID**_ (BID).

De maneira simplificada, podemos entender que o _**Bridge ID**_ é um parâmetro composto por duas partes: um campo chamado de _**Bridge Priority**_, contendo um número de prioridade, e outro contendo o endereço físico da interface de rede do equipamento (MAC address).

Esse parâmetro é utilizado no processo de eleição do _**Root Bridge**_. O campo de _**Bridge Priority**_ – se não tiver sido alterado através dos parâmetros de configuração do switch – vem com um valor padrão de 32769.

**Designação das portas dos switches**

Cada porta conectada, de cada um dos switches, terá uma nomenclatura, determinada dinamicamente pelo algoritmo do STP, e essa nomenclatura serve para entendermos o papel específico de cada uma dessas portas no funcionamento do STP. Essa nomenclatura é listada abaixo:

- _**Root**_ _**P**__**ort**_ **(RP)**: portas mais próximas ao _Root Bridge_. Portas com esse papel permitem o tráfego de dados, ou seja, seu status é o de _**fowarding**_ (FWD).
- _**Designated**_ _**P**__**ort**_ **(DP)**: portas que encaminham os _frames_ para os demais switches na rede. Só existe 1 (uma) _designated port_ por _link_ (nome dado a uma conexão de um ponto a outro; tipicamente, de uma porta de um switch para outra porta, de outro switch).Portas com esse papel permitem o tráfego de dados, ou seja, seu status é o de _**fowarding**_ (FWD).
- _**Alternat**__**e**_ _**Port**_ **(****A****P)**: portas que não permitem o tráfego de dados (exceto de BPDUs), caso contrário causariam _loop_ na rede. Portas com esse papel possuem status de _**blocking**_ (BLK).

Caso ocorra alguma alteração na topologia da rede, o algoritmo do STP se encarregará de atualizar os papéis das portas de todos os switches que estiverem com o protocolo habilitado.

Remoção física de um switch da rede, falha de algum switch na rede; conectar ou desconectar dispositivos em uma rede são exemplos de alterações na topologia que podem ocorrer em uma rede em funcionamento.

**Processo de designação das portas dos switches**

Para entendermos o processo de designação dos papéis das portas dos switches, considere o exemplo apresentado na Figura 1, que apresenta o _**Bridge ID**_ de cada switch, no formato **prioridade:endereçoMAC**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/6/2387678/40954.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/6/2387678/40954.png)

Figura 1 - Cenário de exemplo.

Como o STP é um protocolo extremamente importante, em geral, independentemente do fabricante, desde que o equipamento seja um switch gerenciável (switches não gerenciáveis não dão suporte ao STP), esse protocolo, ou alguma de suas variações, já vem habilitado por padrão.

Assim, com os links devidamente conectados, o processo de atribuição dos papéis das portas, em se tratando do STP, é dado pelas seguintes etapas, nessa ordem:

1) Um _**Root Bridge**_ é eleito, conforme mencionado anteriormente, através do parâmetro _**Bridge ID**_ (o switch na rede, que tiver o menor _**Bridge ID**_, será eleito como _**Root Bridge**_). No nosso exemplo, como o número de prioridade não foi alterado e, portanto, todos são iguais (32769), o _**Root Bridge**_ é o SW3, devido ao seu endereço MAC ser o menor, conforme Figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/6/2389631/40955.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/6/2389631/40955.png)

É uma boa prática definir manualmente (através da configuração dos switches gerenciáveis) o _**Root Bridge**_, caso contrário, o switch a ser eleito como _**Root Bridge**_ será sempre aquele que tiver menor endereço MAC o que, para switches de um mesmo fabricante, será o switch mais antigo, e tipicamente, com menor capacidade de processamento e velocidade.

2) Todas as portas do _**Root Bridge**_ são denominadas _**Designated**_ _**Ports**_ (RP).

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/6/2389620/40956.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/6/2389620/40956.png)

3) Portas conectadas diretamente às portas do _**Root Bridge**_ são denominadas _**Root Ports**_ (RP).

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/6/2389646/40957.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/6/2389646/40957.png)

4) Os demais switches procuram o melhor caminho (_**link**_) até o _**Root Bridge**_, e as portas que pertençam a esse melhor caminho são denominadas _**Designated Ports**_ (DP). O critério de decisão de qual é o melhor caminho, por sua vez, segue as regras abaixo e, se a primeira regra resultou em um empate, a próxima regra será utilizada como critério de desempate, e assim sucessivamente:a) O link com menor custo: dependendo da velocidade das portas, são atribuídos valores numéricos, inteiros, ao _**link**_. Esses valores são chamados de custo do _**link**_. Quanto menor esse valor, melhor será esse link (segundo o algoritmo do STP), a saber:

Para _**links**_ de 10 Mbps, o custo associado a esse _**link**_ é 100.

- Para _links_ de 100 Mbps, o custo associado a esse _link_ é 19.
- Para _links_ de 1 Gbps, o custo associado a esse _link_ é 4.
- Para _links_ de 10 Gbps, o custo associado a esse _link_ é 2.

Em nosso caso, todos os links possuem mesma capacidade, portanto teremos de passar para o próximo critério de desempate.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/6/2392662/40958.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/6/2392662/40958.png)

b) Switch com menor _**Bridge ID**_.Em nosso exemplo, dentre os switches restantes (no nosso exemplo, o SW1 e o SW2), como o número de prioridade não foi alterado e, portanto, todos são iguais (32769), o switch com menor Bridge ID, devido ao seu endereço MAC ser o menor, é o SW2, conforme Figura 6.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/6/2392688/40959.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/6/2392688/40959.png)

Desta forma, atribuímos o papel de _**Designated Port**_ às portas restantes do SW2, em nosso exemplo, conforme Figura 7.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/7/2392734/40960.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/7/2392734/40960.png)

c) O menor número de porta: uma porta identificada como Fa0/2 de um switch é prioritária (em se tratando desse critério de desempate, para o STP) em relação a uma porta identificada como Fa0/3.Em nosso exemplo, não precisamos utilizar esse critério de desempate, pois o critério anterior já foi suficiente.

5) Por fim, todas as demais portas que restaram são bloqueadas (_**Alternate**_ _**Ports**_ – AP).

Em nosso exemplo, sobrou apenas a porta Fa0/1 do SW1, conforme Figura 8.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/7/2392739/40961.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/2/7/2392739/40961.png)

Uma vez concluído esse processo, todas as portas de todos os switches gerenciáveis na rede, que estão com o protocolo STP (ou alguma de suas variações) habilitado, possuem os papéis descritos acima, evitando assim, loops na rede e, consequentemente, a possibilidade de ocorrência do _**broadcast storm**_. A partir de então, BPDUs são enviados de tempos em tempos para checar se ocorreram mudanças na rede. Caso ocorra alguma mudança na rede (como aquelas exemplificadas anteriormente), todo o processo de designação das portas dos switches é repetido.

Na Figura 9 podemos confirmar, através do comando _**show spanning-tree**_, em cada um dos switches, que os papéis (na Figura 9, campo “Role”) e estados (na Figura 9, campo “Sts”) foram, de fato, atribuídos conforme processo descrito anteriormente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/5/2387584/40962.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/5/2387584/40962.png)

Note que, dependendo do fabricante do equipamento, podem existir também protocolos proprietários como, por exemplo, o _**Per-VLAN Spanning Tree**_ (PVST), da própria Cisco.

O protocolo PVST permite criar diferentes instâncias de STP para cada VLAN configurada na rede. VLANs são redes virtuais que permitem segregar interfaces físicas de um switch gerenciável em mais de uma de LAN (_**Local Area Network**_ – Rede Local), de maneira lógica, em diferentes grupos. Essencialmente, uma VLAN divide um switch físico, em um ou mais switches, com quantidade de portas igual ou menor que a quantidade total de portas do switch físico.Dessa forma, como cada VLAN será tratada como uma rede diferente, é possível atingir um balanceamento de carga com o PVST (em termos de _**links**_ na Camada 2), uma vez que poderemos ter mais de um _**Root Bridge**_ na rede.

**Conclusão**

Neste capítulo apresentamos a definição de VLAN, seu princípio de funcionamento, principais aplicações, bem como as vantagens e cuidados no seu uso.