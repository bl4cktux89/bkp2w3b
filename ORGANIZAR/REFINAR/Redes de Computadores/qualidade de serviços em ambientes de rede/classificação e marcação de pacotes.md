**DSCP**

O significado da sigla DSCP é _**Differentiated Services Code Point**_ Consiste em um campo num pacote IP que permite a atribuição de diferentes níveis de serviço ao tráfego de rede. Isso é conseguido através da marcação de cada pacote na rede com um código DSCP, aplicando a ele o nível de serviço correspondente, ou seja, existem duas opções de marcações no cabeçalho IP mais comumente utilizados. São eles:

- IP Precedence.
- Campo DSCP.

O que iremos tratar, neste momento, é do campo DSCP.

Para trabalhar com routers _**legacy**_, que suportam apenas a precedência IP, os valores DSCP são utilizados porque são compatíveis com os campos de precedência IP. Caso necessite de mais informações, consulte o RFC 2474 na internet.

Os programas ativados por Qualidade do serviço (QoS – _**Quality of Service**_) pedem um tipo de serviço específico para um fluxo de tráfego através da interface de programação de aplicações (API – _**Application Programming Interface**_) da QoS genérica (GQoS – _**Generic QoS**_). Os tipos de serviços disponíveis são:

- **Serviço garantido:** fornece qualidade elevada, garantias quantificáveis com latência limitada (mínimo garantido);
- **Serviço de carga controlada:** O serviço de carga controlada fornece qualidade elevada, garantias quantificáveis sem latência limitada.

Na Figura 1, a seguir, é possível visualizar uma construção de rede simples, com ferramentas de enfileiramento ativadas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119226/a07i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119226/a07i01_quasar80_100.jpg)

Figura 1: Exemplo da ação de ferramentas de enfileiramento. Fonte: Odom e Cavanaugh, 2012.

**COS**

Muitos switches de camada 2 atualmente utilizam 3 bits no campo do cabeçalho Ethernet para realizar a marcação utilizando COS (_**Class of Service**_). Ele é um serviço de marcação comumente utilizado em redes locais (LAN), pois age diretamente no cabeçalho Ethernet.

O campo COS existe dentro do frame Ethernet quando o "_**trunking**_" do protocolo 802.1Q ou ISL (_**Inter-Switch Link**_) é utilizado. Vale ressaltar que o padrão 802.1P atualmente define o uso dos bits COS dentro do cabeçalho do padrão 802.1Q.

O campo pode ser utilizado com 8 valores binários diferentes, combinados com IP Precedence ou DSCP.

A atuação do COS pode ser mais bem visualizada na Figura 2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119227/a07i02_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119227/a07i02_quasar80_100.jpg)

Figura 2: Atuação do campo COS em um frame Ethernet. Fonte: Odom e Cavanaugh, 2012.

**CB-Marking (**_**Class Based Marking**_**)**

O CB-Marking pode classificar pacotes dentro das classes de serviços diretamente examinando frames, células, pacotes e segmentos de cabeçalhos. Além disso, pode referenciar uma ACL (Access Control List), para complementar pacotes, por exemplo.

Como qualquer outra ferramenta de configuração QoS que tenha seu nome iniciado por "_**class based**_", você deverá usar os comandos MQC (modular QoS _**Comand-line Interface**_) para configurar. A lógica para uma configuração CB-Marking segue os seguintes passos:

1. Classificar os pacotes dentro das classes de serviços usando o comando "_match_" dentro de um **MQC-policy map**.
2. Marcar os pacotes em cada classe de serviços usando as configurações dentro do **MQC-policy map**.
3. Habilitar a lógica do CB-Marking, como definido no policy-map, utilizando os comandos do **MQC-Service policy** dentro da interface.

**CAR (**_**Committed Access Rate**_**)**

É um mecanismo que provê funções de política de acesso e marcação.

A criação de políticas de acesso, conhecida como "_**policing**_", em sua forma básica, descarta os tráfegos que excederam um contrato de tráfego em particular para determinada rede. Os contratos se baseiam em dois componentes:

- Taxa: determinada em bits ou bytes por segundo.
- Limite de um tamanho: determinado em bits ou bytes.

Se o tráfego excede a taxa ou o tamanho contratado, as políticas criadas bloqueiam o tráfego em excesso. Entretanto, uma política simplesmente possui duas ações rígidas: ou transmite os pacotes, ou os bloqueia.

A função de marcação do **CAR** permite uma ação de política adicional mais justa para enviar os pacotes ou para bloqueá-los.

Considerando um caso típico em que a prática de uma política foi implementada, podemos observar, na Figura 3, que o **ISP1** precisa de uma política de tráfego para proteger seus clientes que possuem um contrato de congestionamento dos que **não** possuem tal contrato.

Se não houver congestionamento, o serviço de tráfego ocorrerá normalmente, em caso contrário, a política criada deverá entrar em ação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119228/a07i03_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119228/a07i03_quasar80_100.jpg)

Figura 3: Realização de uma política de descarte de pacotes. Fonte: Odom e Cavanaugh, 2012.

**PBR (**_**Policy-Based Routing**_**)**

Ele permite, a você, rotear um pacote baseado em outra informação além da informação do endereço IP de destino. Na maioria dos casos, a escolha da rota pelos roteadores através dos protocolos de roteamento é acertada, baseada no endereço IP de cada pacote, entretanto, para alguns casos especiais, alguns pacotes podem solicitar um caminho diferente. Um caminho através da rede pode ser mais seguro para alguns pacotes mesmo que seja longo, por essa razão, o PBR pode classificar os pacotes e escolher uma rota diferente.

Através da Figura 4, a seguir, é possível visualizar a ação de um serviço FTP utilizando tabela de roteamento e uma nova rota desenvolvida pelo **PBR**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119229/a07i04_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119229/a07i04_quasar80_100.jpg)

Figura 4: Exemplo de rota para o serviço FTP. Fonte: Odom e Cavanaugh, 2012.

Vale lembrar que o **PBR** suporta a marcação de pacotes e políticas de roteamento. Também vale lembrar que ele somente processa pacotes entrando nas interfaces, sem a possibilidade de se habilitar a marcação para pacotes saindo da interface. A razão para isso é que ele precisa processar os pacotes antes de uma decisão de rota seja construída. Entretanto, processa pacotes entrando na interface, antecipando uma rota lógica normal baseada em endereço IP de destino. Vale destacar, também, que ele pode gerar uma classificação baseada em informação de rota, diferentemente das outras ferramentas de marcação e classificação, como **CB-Marking** e **CAR**.