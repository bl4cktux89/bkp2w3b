### Introdução

O protocolo SNMP, tem como finalidade a captura de estatisticas da rede, composto  por três partes; o gerente SNMP, o agente SNMP e MIB.

A fim de demosntrar a funcionalidade do SNMP no Packet Tracer é possível configurar um agente SNMP e utilizar um Computador ( PC ou Laptop) e coletar informações aramazenadas na MIB ( Management Information Base ), nesse cenário proposto, vamos utilizar roteadores e Switches que podem fornecer informações Read Only - RO ( Apenas leitura) ou Read and Write - RW ( Leitura e escrita ) utilizando  um PC ou laptop para  navegador na MIB.

O SNMP possui um conjunto de gerencia formado por:  gerente SNMP,  agente SNMP e MIB. Nesse cenário propomos, configurar dois roteador e dois switch como um agente SNMP e usar um PC - computador  como gerente (NMS- Network Management System ) com a finalidade de navegar a MIB dos dispositivos gerenciáveis.

**Cenário proposto - SNMP e Gerência NMS ( Network Management Systems )**

O cenário proposto, apresenta uma ferramenta importante no gerenciamento de rede, que tem como finalidade, configurar a rede de maneira remota, bem como, gerenciá-la, aumentando o controle e a performance da rede, já que so controle da MIB ( Management Information Base) pode apresentar informações importantes dos dispositivos, auxiliando na gerência da Rede.

O cenário é composto por 2 Roteadores modelo 1841, 2 Switches 2950-24 e 4 máquinas PC.

**Configurações dos Dispositivos** **IP nas Interfaces Roteador SP**

**IP nas Interfaces Roteador RJ**

**Habilitar SNMP nos roteadores**

`1.` `enable` `2.` `configure terminal` `3.` `snmp-server community testro ro` `4.` `snmp-server community testrw rw` `5.` `do write` `6.` `exit` `7.`   `8.` `testro ro = apenas leitura` `9.` `testrw rw = leitura e gravação`

**Configuração dos PC´s**

`1.` `Computadores SP:` `2.`   `3.` `User_SP_A = 2001:DB8:CAFE:1::5/64` `4.` `User_SP_B = 2001:DB8:CAFE:1::6/64` `5.`   `6.` `Computadores RJ:` `7.` `User_RJ_A = 2002:DB8:CAFE:1::5/64` `8.` `User_RJ_B = 2002:DB8:CAFE:1::6/64`

**Configuração  Laboratório prático SNMP**

![[Untitled 18.png|Untitled 18.png]]

![[Untitled 1 11.png|Untitled 1 11.png]]