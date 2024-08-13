**Introdução**

Olá! Seja bem-vindo à décima aula! Nela, vamos estudar a segunda versão do protocolo SNMP, que é largamente implantado em infraestruturas que necessitam de gerenciamento, especialmente em ambientes como a internet.

![[Untitled 3.png|Untitled 3.png]]

  

Na aula anterior, falamos das operações que podem ser executadas pelo SNMP; elas são executadas pela segunda versão deste protocolo com a diferença de que esta traz mais possibilidades de objetos de gerenciamento, resolvendo falhas da primeira versão.

Esta versão do SNMP – SNMPv2 – está descrita sobre as RFCs 1901, 1905 a 1909 e 2578 até 2580.

**Elementos do SNMPv2**

Assim como a primeira versão, esta é usada para trocar informações de gerenciamento. Cada nó do sistema mantém um banco de dados local de informações para que elas possam ser recuperadas por uma estação de gerenciamento. Neste novo padrão, é possível ter mais de uma dessas estações, descentralizando (distribuindo) a coleta de informações, e um gerente central (um servidor de gerenciamento) para juntar as informações coletadas pelos demais gerentes. Dessa forma, as estações de gerenciamento podem dividir a responsabilidade e a carga de dados. Sendo assim, o SNMPv2 aceita tanto a estratégia de gerenciamento centralizada quanto a distribuída.

Na estratégia distribuída, ou descentralizada, é formada uma hierarquia dividida em níveis. No primeiro nível (de cima para baixo), temos um servidor de gerenciamento, no segundo, os gerentes, ou estações de gerenciamento, e no terceiro, os equipamentos (elementos) ativos da rede. Como já dito anteriormente, todo equipamento de uma rede que possa ativar o protocolo SNMP pode ser gerenciado pela estrutura, independentemente da versão do SNMP, desde que os gerentes possuam versão superior e saibam quais equipamentos da rede possuem versão anterior.