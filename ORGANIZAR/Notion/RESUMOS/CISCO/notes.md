# Propriedades do Cabo UTP

No tópico anterior, você aprendeu um pouco sobre o cabeamento de cobre de par torcido não blindado (UTP). Como o cabeamento UTP é o padrão para uso em LANs, este tópico entra em detalhes sobre suas vantagens e limitações e o que pode ser feito para evitar problemas.

Quando usado como meio de rede, o cabeamento UTP consiste em quatro pares de fios de cobre com código de cores que foram torcidos juntos e depois envoltos em uma bainha de plástico flexível. Seu tamanho reduzido pode ser vantajoso durante a instalação.

O cabo UTP não usa blindagem para contrabalançar os efeitos de EMI e RFI. Em vez disso, os projetistas de cabos descobriram outras maneiras de limitar o efeito negativo da diafonia:

- **Cancelamento -** os designers agora emparelham os fios em um circuito. Quando dois fios de um circuito elétrico são colocados próximos um do outro, seus campos magnéticos serão opostos. Assim, os dois campos magnéticos cancelam um ao outro e também podem cancelar sinais externos de EMI e RFI.
- **Variando o número de torções por par de fios -** Para aumentar ainda mais o efeito de cancelamento de fios de circuito emparelhados, os projetistas variam o número de torções de cada par de fios em um cabo. O cabo UTP deve seguir especificações precisas que orientam quantas tranças são permitidas por metro (3,28 pés) do cabo. Observe na figura que o par laranja/laranja e branco é menos trançado do que o par azul/azul e branco. Cada par colorido é trançado um número de vezes diferente.

O cabo UTP depende exclusivamente do efeito de cancelamento produzido pelos pares de fios trançados para limitar a degradação de sinal e fornecer efetivamente a autoblindagem para cabos trançados na mídia de rede.

A Camada de Rede

Fornece serviços para permitir que dispositivos finais troquem dados entre redes.

Para realizar comunicações de ponta a ponta, os protocolos de camada de rede executam quatro operações básicas:

- endereçamento de dispositivos finais: os dispositivos finais devem ser configurados com um endereço IP exclusivo para identificação de rede.
- encapsulamento: a camada de rede encapsula a unidade de dados de protocolo (PDU) da camada de transporte em um pacote. Nesse processo adiciona informações de cabeçalho IP com os endereços de origem e destino, o processo de encapsulamento é executado na origem.
- roteamento: a camada de rede fornece serviços para direcionar os pacotes para um host