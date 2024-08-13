[![](https://ampli-images.s3.amazonaws.com/production/d0e752e2-294d-4eb6-ab83-59687a80e189/original)](https://ampli-images.s3.amazonaws.com/production/d0e752e2-294d-4eb6-ab83-59687a80e189/original)

Conforme define Comer (2016), as principais medidas de desempenho de uma rede de computadores são: latência ou atraso, _throughput_, vazão, capacidade ou taxa de transferência e _jitter_ ou variação da latência. Outros indicadores também são importantes, como perda de pacotes e disponibilidade.

**Latência ou atraso**

A primeira propriedade das redes que pode ser medida quantitativamente é latência ou atraso. A latência especifica quanto tempo leva para os dados viajarem através da rede de um computador para outro, medida em frações de segundo. Ela pode ser também considerada como o intervalo de tempo durante a emissão e a confirmação de recebimento de um pacote na rede. Há diversos fatores que impactam na latência de uma rede. O quadro abaixo a seguir mostra os tipos de atraso em uma rede de computadores.

[![](https://ampli-images.s3.amazonaws.com/production/40078a55-f979-4a92-80ed-50937e318f56/original)](https://ampli-images.s3.amazonaws.com/production/40078a55-f979-4a92-80ed-50937e318f56/original)

Tipos de atraso. Fonte: adaptado de Comer (2016, p. 412).

_**Throughput**_

Comer (2016) define a taxa de transferência ou _throughput_ como uma medida da velocidade na qual os dados podem ser enviados através da rede, em bits por segundo (bit/s). Os fatores que influenciam no _throughput_ da rede são: topologia da rede, número de usuários da rede e taxa de interfaces de rede. A figura abaixo apresenta um exemplo de mensuração de _throughput_ de rede realizado através da ferramenta _Wireshark_.

[![](https://ampli-images.s3.amazonaws.com/production/60c539b0-b880-4f76-bcdb-34ff6a5e5f05/original)](https://ampli-images.s3.amazonaws.com/production/60c539b0-b880-4f76-bcdb-34ff6a5e5f05/original)

Throughput em uma rede medida pela aplicação Wireshark. Fonte: captura de tela da ferramenta Wireshark elaborada pelo autor.

______

**🔁Assimile**

A maioria das redes de comunicação de dados oferece uma taxa de transferência de mais de 1 Mbit/s, e as redes de maior velocidade operam mais rápido do que 1 Gbit/s. Casos especiais surgem quando uma rede tem uma taxa de transferência inferior a 1 kbit/s.

______

_**Jitter**_

O _jitter_ é uma medida de variação no atraso da transferência de dados. Ela se tornou importante mediante as novas tecnologias de comunicação baseadas em streaming, com a transferência de voz e vídeos em tempo real via internet. Duas redes podem ter o mesmo atraso médio, mas diferentes valores de _jitter_. Por exemplo, se todos os pacotes que percorrem uma determinada rede têm o mesmo atraso X de um pacote e Y de outro pacote, a rede não tem _jitter_. Porém, se os pacotes alternam entre atrasos diferentes (com um atraso X de um pacote diferente de um atraso Y de outro pacote), a rede tem a mesma média de atraso, mas tem um _jitter_ diferente.

Como um exemplo da importância da análise de _jitter_, considere que as transmissões de voz ou vídeo via internet devem utilizar um protocolo que compensa o _jitter_. Como o uso de protocolos em tempo real é mais econômico do que a construção de uma rede isócrona (onde há envio de mensagens ininterruptamente com intervalos conhecidos e fixos), as empresas de telefonia estão atenuando os requisitos rigorosos de redes isócronas.

______

**💭Reflita**

Conforme afirma Comer (2016), medir o desempenho da rede pode ser surpreendentemente difícil por quatro motivos:

- As rotas podem ser assimétricas.
- As condições podem mudar rapidamente.
- A própria medição pode afetar o desempenho.
- O tráfego é em rajadas.

Ao contrário do tráfego telefônico de voz, o tráfego de dados ocorre em rajadas.

O desempenho de uma rede de computadores é considerado estável dentro do que se chama de redes convergentes, nas quais redes de dados e redes de telefonia estão operando através de linhas de distribuição de dados unificada?

______

**Perda de pacotes**

A perda de pacotes na rede refere-se à situação em que se encaminham informações pela rede, porém estas não respondem com a totalidade da sua entrega. Pode ocorrer devido à capacidade de armazenamento de pacotes nos roteadores, considerando que estes possuem capacidade de memória limitada. É possível verificar a resposta de perda de 25% dos pacotes enviados através do comando ping 192.168.0.1 no teste de rede apresentado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/5a784ee4-c0ff-4b8e-b8af-fafe905c2d33/original)](https://ampli-images.s3.amazonaws.com/production/5a784ee4-c0ff-4b8e-b8af-fafe905c2d33/original)

Perda de pacotes na rede. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

______

**📝 Exemplificando**

Redes padrão Ethernet (802.3) são baseadas em conexões realizadas através de enlaces físicos por cabos. Os cabos metálicos de par trançado UTP (_Unshield Twisted Pair_) é o tipo mais comum em redes locais e possuem comprimento limitado (100 metros), para garantir a qualidade do sinal eletromagnético. A instalação adequada dos cabos dentro dos limites de comprimento estabelecidos, assim como os graus de curvatura que são submetidos, influenciam na perda de pacotes em uma rede.

Outra medida importante para prevenir a perda de pacotes é a escolha adequada do padrão de rede Wi-Fi (802.11), que possui diversas especificações, com diferentes faixas de frequência e cobertura. Por exemplo, uma rede 802.11ac trabalha na faixa de frequência de 5,8 GHz, velocidade de até 1,3 Gbps e possui menor distância de operação e menor capacidade de transpassar obstáculos, o que pode ocasionar perda de pacotes na rede. Outro padrão recente é o 802.11ad, com frequência de 60 GHz, que possui maior dificuldade para transpassar obstáculos devido à alta frequência.

**Disponibilidade**

Como sustenta Comer (2016), as redes de computadores são compostas por diversos equipamentos, como nodos, computadores, servidores, cabeamentos, entre outros, e todos esses dispositivos podem sofrer algum tipo de falha. A disponibilidade de uma rede é a capacidade que seus equipamentos possuem de manterem-se em operação de forma ininterrupta dentro de um determinado período de tempo.

Alguns conceitos referentes à disponibilidade de uma rede de computadores são:

- _Mean Time Between Failures_ (MTBF): ou tempo médio entre falhas, é uma previsão por modelo estatístico/matemático do tempo médio entre as falhas. É útil para prever as manutenções necessárias dentro de um sistema de redes de computadores. Para o cálculo, utiliza-se a fórmula:

MTBF = ∑ (FINAL – INICIAL) / NÚMERO DE FALHAS

- _Mean Time to Repair_ (MTTR): ou tempo médio para reparos, é uma previsão por modelo estatístico/matemático do tempo médio para se realizar o reparo da rede após a ocorrência de uma falha. Para o cálculo, utiliza-se a fórmula:

MTTR = TEMPO DE PARADA POR FALHA / NÚMERO DE FALHAS

- _Mean Time to Failure_ (MTTF): ou tempo médio para falha, é o tempo de vida de uma rede que compreende os períodos alternados de operação de falhas. Este termo é utilizado para efetuar o cálculo de disponibilidade de uma rede de computadores por meio da função de frequência com que as falhas ocorrem e do tempo necessário para reparo, definido pela fórmula:

D = MTTF / (MTTF + MTTR)

Por exemplo: considere que um sistema de rede de computadores possui um MTTF de 8.760 horas de operação no ano (referente a um sistema que opera 365 dias por 24 horas) e um MTTR de 288 horas anual (com sistema off-line 12 dias por ano). Nesse caso:

D = MTTF / (MTTF + MTTR)

D = 8760 / (8760+288)

D = 96,816

A disponibilidade da rede é de 96,82% ao ano.