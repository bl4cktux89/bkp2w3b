### Introdução

Com o crescente número de dispositivos na rede, sistemas, celulares, e vários tipos de tecnologias, aparecem várias falhas, falhas em vários aspectos, falhas estas, que são exploradas por hackers. Essas falhas podem aparecer em todos os níveis, na rede, no sistema computacional, no armazenamento, na segurança física do Data Center, entre vários outros aspectos. A segurança da informação é uma área muito rápida, e por mais que tenha sua base sempre está em mudança.

Quando essas falhas são exploradas muitos problemas podem acontecer, informações podem ser roubadas, apagadas, o sistema pode ser modificado, ou indisponível. Como podem ver, isso abre um leque de possibilidades, por isso temos que entender cada parte da nossa rede muito bem.

Os pilares da segurança da informação são Confidencialidade, Integridade e Disponibilidade.  Seu objetivo é manter esses três pontos sempre funcionando, para fazer isso é feita uma análise de risco, testes de segurança, atualizações, controles de acesso, autenticação e muitas outras coisas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/9/1/19148/i03_1746.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/9/1/19148/i03_1746.jpg)

Controle de Acesso

### Soluções para segurança da informação

Para resolver problemas de segurança de rede e de segurança da informação, temos que analisar o problema como um todo, dessa forma, fica mais fácil se dividirmos em partes e em processos, essa divisão pode ser classificada como soluções para problemas administrativos e técnicos:

Administrativos: Medidas que visam proteger informações com treinamentos e políticas para seus funcionários, além de reforçar a segurança física do local do Data Center, por exemplo a validação de pessoas autorizadas para entrar na edificação, através de sistemas, sensores e alarmes tais como: câmeras, catracas e dispositivos biométricos.

Técnicos: Em relação aos problemas técnicos, podemos dividi-los em camadas:  rede, computação e armazenamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/9/1/19150/i04_1746.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/9/1/19150/i04_1746.jpg)

Controle de catracas

### Soluções para a infraestrutura de Segurança da Informação

Uma das formas de manter a infraestrutura de rede operacional e disponível, é a criação de controles de acesso aos equipamentos físicos e a estrutura lógica, representada pelos perímetros que compreendem as instancias de _**intranet, extranet e internet**_, significa então, que devemos implementar politicas controles de acesso físico e lógicos a essas instancias, de modo a garantir que os recursos de redes estejam disponíveis quando solicitados pelos usuários.

De acordo com a EMC Corporation (2015), destacam-se as seguintes camadas da infraestrutura de segurança de dados:

**Rede:** Envolve todos os elementos de rede, switches fabrics, roteadores, hubs, etc… E como eles são configurados. Estabelecer políticas entre os dispositivos de rede de maneira que os dispositivos se conectam e também analisar o tráfego da rede, buscando anomalias. Algumas das medidas de segurança em redes envolvem firewalls, que são analisadores de pacotes de rede e aplicam regras e filtros a eles, podem ser implementados tanto no sistema quanto fisicamente com um dispositivo específico para isso quanto no nível de virtualização. Outro elemento na defesa é o IPS, que é o sistema de prevenção de intrusão,  e IDS que é o sistema de detecção de intrusão, os dois funcionam bem similarmente, mas basicamente o IDS somente alerta uma intrusão, enquanto o IPS interrompe a mesma. Outra coisa que pode ser feita são VLANs, que são redes locais virtuais, o que separa a rede em grupos, dessa forma aumenta a segurança já que cada um fica isolado um do outro.

**Computação:** Ao que diz respeito ao servidores, sistemas computacionais, algumas das medidas para tornar esse ponto mais seguro é a correta configuração de permissões no linux, ou ACL, como são chamadas no Windows. Outro fator muito importante é sempre manter os sistemas atualizados, dessa maneira os atacantes não terão acesso a falhas antigas. Outro erro comum que ocorre nessa parte são sistemas mal programados, por exemplo sua empresa cria um sistema para se comunicar com a matriz mas não requer nenhum tipo de autenticação. O que pode ser arrumado implantando um protocolo que faça isso.

**Armazenamento:** A segurança em armazenamento engloba todos os dispositivos de armazenamento, como HDs, SSDs, fitas, etc… A segurança vai desde o momento que a informação é gerada, e armazenada corretamente, o que envolve criptografia e um transporte seguro, até a destruição de dados antes de vender ou jogar fora dispositivos antigos, como é possível recuperar dados apagados é muito importante que sempre os dados sejam eliminados, muitas vezes isso é feito desmagnetizando o disco, ou o destruindo completamente, ou até sobrescrevendo seu conteúdo várias vezes com informações inválidas.Para alinhar todos esses pontos é criado uma governança de TI, que determina objetivos e regras operacionais. Também é feita uma análise de risco, na qual busca-se achar pontos críticos e isolar as falhas. Outro ponto importante na gestão é a conformidade, que seria o ato de aderir, acatar e seguir ordens e regras. Por último mas não menos importante, temos a auditoria, que é o processo de determinar a confiabilidade de um determinado sistema, ela pode ser feita por funcionários internos a empresa, ou externos.

Uma maneira muito utilizada para a criação de políticas de segurança de dados e  acesso a infraestrutura de tecnologia da informação é a criação de ACL´s (Access Control Lists) que discutiremos a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/2/318223/19019.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/2/318223/19019.jpg)

Segurança Lógica

### Conceito de ACL (Access Control List)

Um dos grandes desafios do administrador de redes de uma empresa é, sem dúvida alguma, manter seu ambiente seguro e, principalmente, estabelecer um controle de tráfego de pacotes, daí a necessidade de utilizarmos as Listas de Controle de Acesso.

Os roteadores fornecem uma filtragem básica de pacotes, por exemplo, o bloqueio de acesso a determinados recursos na internet. Uma ACL nada mais é que uma sequência de instruções que permitem ou negam acesso à determinada rede ou recursos disponíveis em outras.

As listas de controle de acesso (ACL) são responsáveis por controlar e filtrar o tráfego de acesso ou saída de pacotes IP´s, podendo ainda funcionar como regras de firewall associadas a segurança da rede. Quando um host, ou um usuário solicita um acesso à um roteador via Telnet, por exemplo, essa solicitação pode ser negada (Deny) ou permitida (Permity) de acordo com as regras e políticas associadas a este perfil de usuário.

Existem vários protocolos da camada de rede, de modo que podemos criar listas de acesso com diversos protocolos, tais como IPX e IP.

A ordem da aplicação da ACL é muito importante, a análise de instrução do IOS ( Internetwork Operating System) é executada de cima para baixo, ou seja, a cada etapa de comandos ou instruções encontradas em sua lista, haverá uma instrução correspondente à uma negação (_**Deny**_) ou permissão (_**permity**_), se houver uma instrução deny all , negar tudo, as demais instruções na sequência abaixo da lista, não serão lidas ou verificadas.

Caso não possua nenhuma relação de correspondência na verificação de ACLs, existe por padrão, implícita, uma instrução _**Deny Any.**_ Essa instrução é nativa no equipamento e tem como finalidade descartar o tráfego que passa na interface do roteador.

Vamos considerar o seguinte exemplo, se desejarmos liberar todo trafego ICMP para uma determinada rede ou interface, criamos uma linha de instrução para essa liberação e logo após estará implícito um _**Deny any**_ no final da instrução, logo, todo trafego restante será descartado, já que não é liberado por linha de comado explicito. Então concluímos que devemos ter linhas de comando declarando as condições de trafego na rede de modo bastante claro e objetivo.

Exemplo de Lista de Controle de Acesso Padrão

O funcionamento básico da ACL Padrão, consiste em permitir ou negar o IP de origem ou destino de um pacote, realizando uma averiguação das regras adotadas pelo administrador de rede.

router(config)\#access-list 100 deny ip 192.168.1.0 0.0.0.255 192.168.4.0 0.0.0.255

router(config)\#access-list 100 permit ip 192.168.2.0 0.0.0.255 192.168.4.0 0.0.0.255

**SAIBA MAIS EM BLOG DO JÚLIO BATTISTI** **E CISCO SYSTEMS**

https://www.juliobattisti.com.br/tutoriais/luisepedroso/acl001.asp

https://www.cisco.com/c/pt_br/support/docs/security/ios-firewall/23602-confaccesslists.html

Tipos de ACLs

Existem especificamente três tipos de Listas de Acesso:

- Listas de acesso IP padrão.
- Listas de acesso IP estendidas.
- Listas de acesso com nome.

### Listas de acesso IP padrão

Esse é um tipo de Lista de Acesso baseado no endereço IP de origem. A ACL permite ou nega o tráfego de um conjunto inteiro de protocolos a partir dos endereços da rede, sub-rede ou host.

Toda configuração de uma ACL em um roteador é seguida de um número que corresponde a um intervalo. Esse número indica o tipo de Lista de Acesso definida. Para Listas do tipo Padrão o intervalo vai de 1 a 99.

Na versão 12.0.1 do IOS foi adicionado mais um intervalo que vai de 1300 a 1999. Com esse adicional podemos ter até 798 Listas de Acesso IP Padrão.

Primeiramente, deve-se definir as instruções de uma ACL e logo em seguida aplicar em uma interface, definindo o seu destino. Conceitualmente as listas de acesso IP Padrão devem ser aplicadas mais próximas do destino.

### Listas de acesso IP estendidas

Esse é um tipo de lista de acesso bem mais utilizado, pois baseia todo o controle em endereços de rede de origem e destino, sub-rede, host, conjunto de protocolos e portas. Isso torna esse tipo de ACL bem mais flexível e completa do que uma lista padrão.

É possível configurar várias instruções para uma mesma lista de acesso, basta conservar o mesmo número da lista. A quantidade de instruções definidas em uma lista de acesso é limitada pela capacidade de memória do roteador.

O intervalo de uma lista de acesso estendida vai de 100 a 199 e também existe um intervalo adicional para versões de IOS mais recentes que vai de 2000 a 2699.

No final da ACL estendida temos a opção de definirmos o tipo de porta a ser utilizada. É possível especificar operações lógicas na configuração dessas portas como:

- eq – igual.
- neq – diferente.
- gt - maior do que.
- lt – menor do que.

Essas operações lógicas são utilizadas em determinados protocolos.

### Listas de acesso com nome

Esse tipo de lista de acesso foi introduzido na versão 11.2 do Cisco IOS. Ela permite que sejam atribuídos nomes ao invés de números às listas de acesso. A principal vantagem desse tipo de configuração está na identificação da lista, ou seja, podemos atribuir um nome que seja relacionado diretamente a sua função, mas, além disso, pode-se destacar:

- Quantidade ilimitada de listas de acesso, visto que não fica na dependência da quantidade de números disponíveis nos intervalos.
- Permite a inserção de instruções no final da lista.

Temos, porém, que considerar que nesse tipo de lista não deve existir nome repetido, nem se o tipo de lista for diferente. Por exemplo:

Não é possível existir uma lista de acesso padrão e uma lista de acesso estendida com o nome UNINOVE.

Definimos uma lista de acesso com nome através do comando ip Access list.

Considerações sobre o posicionamento das listas de acesso

Para o bom funcionamento de uma lista de acesso devemos saber exatamente como e onde posicioná-las, pois isso fará com que a rede seja muito mais eficiente.

Para listas de acesso IP padrão, posicione-a o mais próximo do destino, pois elas baseiam-se nos endereços de origem. Para as listas de acesso IP estendidas posicione mais próximo da origem, pois como essa lista baseia-se em endereços de origem, destino, tipo de protocolo e porta, o tráfego é analisado antes de sair da rede.

Para exemplificar, consideraremos os dois exemplos a seguir, eles têm o mesmo resultado:

Exemplo 1: access-list 101 permit ip 10.1.1.0 0.0.0.255 172.16.1.0 0.0.0.255

Exemplo 2: access-list 102 permit ip 10.1.1.0 0.0.0.255 172.16.1.0 0.0.0.255 access-list 102 deny ip any any

Além de definir a origem e o destino do tráfego, podemos definir portas de origem e destino, tipos de mensagens ICMP e outros parâmetros que ajudam ainda mais a restringir as entradas das listas de acesso que serão aplicadas nas interfaces dos roteadores.

Exemplo 3: access-list 102 permit icmp host 10.1.1.1 host 172.16.1.1 14 - permite todos os tipos de mensagens icmp

access-list 102 permit icmp host 10.1.1.1 host 172.16.1.1 eco-request - permite apenas um tipo de mensagem icmp

As listas de controle de acesso só terão efeito depois de aplicadas a uma interface. Uma boa prática é aplicar a ACL na interface mais próxima da origem do tráfego.

((BATTISTI, 2018).)

Um roteador sem nenhuma lista de acesso (ACLs) deixará todo o tráfego de dados passar normalmente pelas rotas que porventura esteja configurado.

Para o iniciante que está aprendendo ACLs recomenda-se adicionar sempre ao final de uma lista de comandos a instrução deny any reforçando a ideia de que existe um deny implícito no fim de qualquer lista. Com a prática o profissional lembrará que essa negação é sempre implícita.

Os profissionais utilizam as ACLs a fim de parar o tráfego ou permitir apenas o tráfego em suas redes.

Uma ACL é basicamente uma sequência de instruções que permitem ou negam acesso à determinada rede ou recursos disponíveis em outras. Este recurso pode dar suporte a implementação mínima em segurança, controlando o fluxo e pode preservar a largura de banda da rede por meio desse controle.

É possível criar instruções ACL por protocolo, por direção ou interface.

As máscaras de rede são também utilizadas em ACLs-Listas de Acesso e é importante conhecer sobre visto que são utilizadas com os endereços IP nos ACLs de IP para especificar o que deve ser permitido e recusado.

De forma didática podemos dizer que a máscara curinga é o inverso da máscara de rede, por exemplo:

255.0.0.0 é equivalente a curinga 0.255.255.255;

também 255.255.0.0 é equivalente a 0.0.255.255

Mas uma observação! Essa regra não funciona com máscaras do tipo 255.255.255.224 (por exemplo), caso queira utilizar uma máscara desse tipo deve-se subtrair sempre de 255.255.255.255, exemplo 255.255.255.255 - 255.255.255.224 resulta em 0.0.0.31 que será a máscara curinga da máscara proposta.

### Exemplo de Lista de Controle de Acesso estendida

Negar ou permitir qualquer host para qualquer destino na porta 80 (que utilize o protocolo http)

router(config)\#access-list 100 deny tcp any any eq 80

router(config)\#access-list 100 permit tcp any any eq 80

Negar ou permitir qualquer host

router(config)\#access-list 100 deny any any

router(config)\#access-list 100 permit any any

Aplicar a lista de acesso em uma interface de um roteador (de entrada ou saída da rede)

router(config)\#interface fastethernet 0/0

router(config-if)\#ip access-group 100 out

router(config)\#interface fastethernet 0/1

router(config-if)\#ip access-group 100 in

### Resumo

Em um ambiente de segurança da informação, uma das funcionalidades mais importantes é a segurança lógica. Ela é implementada com vários recursos e dispositivos, entre ele firewalls, que são dispositivos específicos para analisar as conexões de uma rede. Porém não é só de dispositivos de redes que se faz a segurança, o uso de câmeras, sensores de movimentos e sistema de alarme, e até mesmo controles de acesso biométricos são essenciais para uma boa segurança. A adoção de recursos de segurança lógica, como as ACL´s ( Listas de controle de acesso) podem limitar acesso de pacotes que entram ou saem da rede, implementar os recursos minimos de segurança, definir a implementação mínima de segurança, definir qual rede será liberada ou bloqueada (suporte a DMZs), zonas desmilitarizadas, além de controlar fluxo de pacotes, preservando a largura de banda da infraestrutura de rede.