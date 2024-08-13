### **Introdução**

A arquitetura de proteção de uma rede de computadores passa pela adoção mecanismos de isolamento tráfego e monitoramento de atividades com o objetivo de suprimir um possível ataque.

A adoção de DMZ (Zona Desmilitarizada) permite o isolamento do tráfego entre redes locais, públicas e servidores contidos dentro dela. Por outro lado, quando adotamos soluções do tipo Honeypot e Honeynet desejamos conhecer e mais profundidade os possíveis ataque pelos quais uma rede está susceptível, permitindo a interação do atacante com tais elementos.

O conhecimento extraído a partir do monitoramento de honeypots e honeynets pode trazer grandes benefícios para as organizações, favorecendo a adoção de medidas ativas antes do comprometimento da rede real, além de proporcionar uma visão mais abrangente do que se deve proteger e como se proteger, ou seja, auxiliando na orquestração da segurança como um todo (MORAES, 2010).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/1/6/8/0/1168037/17207.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/1/6/8/0/1168037/17207.png)

Diagrama de rede

### DMZ (Zona Desmilitarizada)

Os firewalls são utilizados principalmente para permitir ou negar o tráfego com base na sua origem e/ou destino. Em topologias simples, conforme figura abaixo, são necessárias apenas duas interfaces, uma associada a rede interna e a outra associada a rede pública, estabelecendo, respectivamente, a primeira como confiável e a última como não confiável. Sendo assim, adota-se regras com base no seguinte perfil de tráfego (MORAES, 2010):

- O tráfego originado da rede privada é permitido e inspecionado à medida que viaja em direção à rede pública. O tráfego inspecionado que retorna da rede pública e associado ao tráfego originado da rede privada é permitido.
- O tráfego originado na rede pública e viajando para a rede privada geralmente é bloqueado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/3/8/8353856/60125.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/3/8/8353856/60125.jpg)

Firewall com apenas duas interfaces

Fonte: CCNA Cybersecurity Operations, 2020 (Adaptado).

Uma zona desmilitarizada (DMZ) é um projeto de firewall em que normalmente há uma interface interna conectada à rede privada, uma interface externa conectada à rede pública e uma interface DMZ, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/3/8/8353864/60126.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/3/8/8353864/60126.jpg)

Seletividade do firewall com DMZ em função do perfil do tráfego

Fonte: CCNA Cybersecurity Operations, 2020 (Adaptado).

Nesse cenário os perfis de tráfego são tratados da seguinte forma (CCNA Cybersecurity Operations, 2020):

- O tráfego originado da rede privada é inspecionado à medida que viaja em direção à rede pública ou DMZ. Este tráfego é permitido com pouca ou nenhuma restrição. O tráfego inspecionado de retorno da DMZ ou rede pública para a rede privada é permitido.
- O tráfego originado da rede DMZ e viajando para a rede privada geralmente é bloqueado.
- O tráfego originado da rede DMZ e viajando para a rede pública é permitido seletivamente com base nos requisitos do serviço.
- O tráfego originado na rede pública e em direção à DMZ é permitido e inspecionado seletivamente. Esse tipo de tráfego é normalmente tráfego de e-mail, DNS, HTTP ou HTTPS. O tráfego de retorno da DMZ para a rede pública é permitido dinamicamente.
- O tráfego originado na rede pública e direcionado à rede privada é bloqueado.

### Firewalls baseados em políticas de zona (ZPFs)

Firewalls baseados em políticas de zona (ZPFs) usam o conceito de zonas para fornecer flexibilidade adicional. Uma zona é um grupo de uma ou mais interfaces que possuem funções ou recursos semelhantes. A criação de zonas ajuda a especificar onde uma regra ou política de firewall deve ser aplicada. Esse conceito é aplicado, por exemplo, em firewalls da próxima Atividade

Na figura abaixo, as políticas de segurança para LAN 1 e LAN 2 são semelhantes e podem ser agrupadas em uma zona para facilitar a configurações de firewall. Por padrão, o tráfego entre interfaces na mesma zona não está sujeito a nenhuma política e passa livremente. No entanto, todo o tráfego de zona a zona é bloqueado. Para permitir o tráfego que entra nas zonas deve ser configurada uma política que inspecione ou permita o tráfego (CCNA Cybersecurity Operations, 2020).

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/4/6/8354636/60131.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/4/6/8354636/60131.png)

Firewall com política de zona (ZPF)

Fonte: CCNA Cybersecurity Operations, 2020. (Adaptado)

A única exceção a esse padrão de negar qualquer política é a própria zona do firewall ou zona _**self**_, que inclui todos os seus endereços IPs. As configurações de política que incluem a zona própria se aplicam ao tráfego destinado e originado no firewall. Por padrão, não há política para este tipo de tráfego e, por isso, deve ser considerado O tráfego de gerenciamento e o tráfego do plano de controle como SSH, SNMP e protocolos de roteamento.

### **Honeypots e Honeynets**

Os **honeypots** (potes de mel) e os **honeynets** são sistemas criados para ?aprisionar? o atacante, permitindo que eles sejam comprometidos com o objetivo monitorar o invasor a partir de sua interação com o sistema. Dessa forma, as ações do atacante podem gerar alertas e ao mesmo tempo enganá-lo.

Um honeypot é constituído de um único dispositivo a ser comprometido, conforme mostrado na figura abaixo. Normalmente, firewalls, sistemas de detecção de intrusão (IDS) e sistemas de prevenção de intrusão estão operando com conjunto com o objetivo de monitorar e prevenir ataques a rede real.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/3/5/353521/29058.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/3/5/353521/29058.png)

Posicionamento do Honeypot

As **honeynets**, por sua vez, são redes de pesquisa compostas por vários honeypots, conforme ilustrado na figura que segue. Dentro dela podem ser instalados diferentes sistemas operacionais e sistemas de monitoramento, o que permite ao administrador do sistema identificar possíveis riscos a rede real em operação. A partir das informações extraídas pela interação do atacante é possível que as organizações possam produzir seus próprios mecanismos de defesa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/4/9/2/7/8492741/60145.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/4/9/2/7/8492741/60145.png)

Topologia de uma honeynet.

As primeiras honeynets eram construídas a partir de dispositivos físicos, no entanto, eram extremamente complexas e custosas financeiramente. Atualmente, as honeynets podem ser virtualizadas em uma única máquina alcançado os mesmos objetivos, tendo em um único computador um gateway que Controla e Captura Dados e dos honeypots. No exemplo da figura a seguir ilustra uma honeynet com dispositivos reais. Observe que existe um IDS monitorando o tráfego de ambas as redes.

### Níveis de interação

O nível de atividade do atacante com o honeypot ou com a honeynet define o nível de interação. Existem honeypots de baixa interação e de alta interação. Os honeypots de baixa interação permitem que o atacante realize interação apenas com serviços emulados como, a pilha de protocolos TCP/IP e poucos aspectos de uma máquina real. Por outro, os honeypots de alta interação permitem a interação do atacante com um sistema real.

Os honeypots de alta interação são difíceis de configurar e, se comprometido, podem ser usados para ataques a outros pontos da rede, mas permitem que capturar um maior número de informações sobre o ataque.

**SAIBA MAIS...**

Ferramentas como [**Glastopf**](https://www.honeynet.org/projects/old/glastopf/) permite simular uma aplicação WEB com diversas vulnerabilidades. A ferramenta [**HoneyMap**](https://www.honeynet.org/2012/10/01/honeymap-visualizing-worldwide-attacks-in-real-time/) mostra um mapa em tempo real de ataques usando dados de honeypots vinculados ao [**Honeynet Project**](https://www.honeynet.org/).