**Definição**

O termo _**trunking**_ é uma terminologia adotada pela Cisco (outros fabricantes geralmente utilizam o termo _**tagged VLAN**_, ou simplesmente _**uplink ports**_) utilizada para se referir a porta de um switch configurada de tal forma que permita o tráfego de _**frames**_ – nome dado a comunicação que ocorre na Camada 2 do modelo de referência ISO/OSI – de várias VLANs (_**Virtual**_ LANs) por essa mesma porta.

**Aplicação**

Um _**link**_ (conexão entre duas interfaces de equipamentos diferentes) do tipo _**trunk**_ permite a interligação entre dois switches, de maneira que dispositivos (PCs, impressoras, servidores, etc.) que pertençam a uma mesma VLAN como, por exemplo, a VLAN10, possam “conversar” entre si, mesmo estando fisicamente conectados a switches diferentes.

**Funcionamento**

Considere o exemplo apresentado na Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/5/5/6/2455685/40728.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/5/5/6/2455685/40728.png)

No exemplo da Figura 1, temos um edifício comercial onde uma empresa possui dois andares, e temos PCs do departamento de Engenharia e do departamento de Vendas nos dois andares. Por uma série de questões, o pessoal de Engenharia não pode acessar os mesmos recursos do pessoal de Vendas e vice-versa, motivo pelo qual dividimos as portas de cada um dos switches gerenciáveis SW1 e SW2 (por meio da configuração destes) em dois grupos distintos: Engenharia e Vendas (identificados na configuração das interfaces Fa2/1 e Fa1/1 dos switches como VLAN10 e VLAN 50, respectivamente). Até aqui tudo bem, certo?

Mas e quando o PC de um vendedor no 1º andar precisar comunicar com o PC de outro vendedor no 2º andar, por exemplo? Como o switch SW2 saberá para qual porta enviar a mensagem?

A resposta é: através do protocolo de _**trunking**_ mais utilizado atualmente, o IEEE 802.1Q.

**IEEE 802.1Q**

O IEEE 802.1Q é um protocolo _**de facto**_ em que as VLANs são “tageadas” (como se tivessem um adesivo, indicando a qual VLAN aquele _**frame**_ pertence).

Mais especificamente, são adicionados 4 bytes ao _**frame**_ Ethernet pelo switch que está enviando a mensagem (no exemplo anterior, o switch SW1), e removida pelo switch que está recebendo a mensagem, depois que este identifica a qual VLAN essa mensagem pertence (no exemplo anterior, o switch SW2). Seu funcionamento é também baseado em um esquema de priorização de frames, definido pelo padrão IEEE 802.1p.

Dispositivos finais, como PCs, telefones IP e impressoras; também chamados de clientes, ou ainda _**hosts**_, não sabem identificar VLANs, motivo pelo qual a informação da VLAN é sempre removida quando o frame “sai” do switch em direção ao dispositivo final.

**Conclusão**

Neste capítulo apresentamos a definição do termo _**trunking**_, sua aplicação, bem como seu princípio de funcionamento.