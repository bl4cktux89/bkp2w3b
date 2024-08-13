**Definição**

As _**Virtual LANs**_ (VLANs) são redes virtuais que permitem segregar interfaces físicas de um switch gerenciável em mais de uma de LAN (_**Local Area Network**_ – Rede Local), de maneira lógica, em diferentes grupos. Essencialmente, uma VLAN divide um switch físico, em um ou mais switches, com quantidade de portas igual ou menor que a quantidade total de portas do switch físico.

**Aplicação**

A separação das interfaces físicas de um switch (e, por consequência, dos dispositivos conectados a elas) em diferentes grupos beneficia:

- A segurança, uma vez que, naturalmente, as VLANs são isoladas umas das outras.
- A aplicação de regras específicas para uma determinada VLAN.
- A diminuição de custos, por diminuir a quantidade de switches físicos.
- O desempenho da rede, por criar mais domínios de _broadcast_.

_**Broadcast**_ refere-se a comunicação originada por um dispositivo que necessita ser replicada a todos os dispositivos daquela rede local. Vários protocolos só funcionam por causa da existência desse tipo de comunicação como, por exemplo, o DHCP (_**Dynamic Host Configuration Protocol**_), que atribui endereços IP de maneira automática a qualquer cliente (_**host**_) que solicite esse tipo de serviço, em uma rede de computadores.

Domínio de _**broadcast**_ refere-se a quantidade de “regiões” (domínios) em que uma mensagem _**broadcast**_ pode ser propagada. Em switches não-gerenciáveis (switches que não possuem parâmetros de configuração), existe um único domínio de _**broadcast**_, ao passo que, em switches gerenciáveis, cada VLAN representa um domínio de _**broadcast**_. Assim, no exemplo da Figura 1, temos dois domínios de _**broadcast**_.

**Funcionamento**

Considere o exemplo apresentado na Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/5/5/6/2455682/40728.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/5/5/6/2455682/40728.png)

No exemplo da Figura 1, temos um edifício comercial onde uma empresa possui dois andares, e temos PCs do departamento de Engenharia e do departamento de Vendas nos dois andares. Por uma série de questões, o pessoal de Engenharia não pode acessar os mesmos recursos do pessoal de Vendas e vice-versa. Como resolvemos essa questão?

Esse é um perfeito caso de uso de VLANs: basta dividirmos as portas dos switches gerenciáveis SW1 e SW2 (por meio da configuração destes) em dois grupos distintos: Engenharia e Vendas (identificados na configuração dos switches como VLAN10 e VLAN 50, respectivamente).

Importante lembrar que cada VLAN se comportará como sendo um switch separado (como pode ser observado no exemplo anterior). Portanto, caso haja necessidade de troca de informações entre portas de um mesmo switch físico, porém que pertençam a VLANs diferentes, haverá necessidade de um roteador (ou que o switch seja _**Layer**_ 3).

**Conclusão**

Neste capítulo apresentamos a definição de VLAN, seu princípio de funcionamento, principais aplicações, bem como as vantagens e cuidados no seu uso.