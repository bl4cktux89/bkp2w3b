**Protocolo IP**

O protocolo IP é o protocolo da camada de rede da arquitetura TCP/IP. É responsável pelo encaminhamento dos pacotes desde a origem até o destino, além de ser um protocolo não orientado a conexão, pois não garante a entrega até seu destino. Esse protocolo é o responsável por definir um esquema de endereçamento.

Com relação aos datagramas, o protocolo IP é considerado não confiável, pois não garante a entrega até o destino. Não existe confirmação de que os datagramas foram entregues; eles podem chegar na ordem diferente daquela que foi enviada.

Uma grande característica é quanto à função de roteamento, que escolhe o caminho pelo qual os dados serão enviados.

Observando a figura 1 a seguir, pode-se ter uma ideia melhor dessa comunicação virtual ao qual o protocolo IP é responsável:

Figura 01: Exemplo de uma comunicação virtual

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/1/119188/a01i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/1/119188/a01i01_quasar80_100.jpg)

Fonte: Adaptado de: TANENBAUM, A. S. Redes de Computadores. Rio de Janeiro: Campus, 2006.

Na figura 2 vamos observar o cabeçalho do protocolo IP. Uma atenção especial para o campo "TOS", o qual iremos detalhar um pouco mais adiante.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/1/119190/a01i02_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/1/119190/a01i02_quasar80_100.jpg)

Fonte: Adaptado de: TANENBAUM, A. S. _Redes de Computadores_. Rio de Janeiro: Campus, 2006.

Os endereços IP, também conhecidos como IPV4, são expressos como números decimais com pontos: dividem-se os 32 bits do endereço em quatro octetos (um octeto é um grupo de 8 bits). O valor decimal máximo de cada octeto é 255 (o maior número binário de 8 bits é 11111111, e esses bits, da direita para esquerda, têm os valores decimais 1, 2, 4, 8, 16, 32, 64 e 128, totalizando 255).

Na internet, cada host e cada roteador possui um endereço IP exclusivo, que codifica seu número de rede e número de host. Todos os endereços IP têm 32-bits e são usados nos campos Endereço IP Origem/Destino.

A cada host de uma interligação em redes TCP/IP é atribuído um endereço de interligação em redes único de 32 bits que é usado em todas as comunicações com aquele host.

Os bits dos endereços IP para todos os hosts de uma rede dada compartilham um mesmo prefixo. Conceitualmente, cada endereço é um par (netid, hostid) em que netid identifica uma rede e hostid identifica um host naquela rede. Dado um endereço IP, seu tipo pode ser determinado a partir de três bits de alta ordem, em que dois são suficientes para distinguir entre as três classes principais:

- Endereços do tipo A: são usados pelas numerosas redes. Dedicam sete bits para netid e 24 bits para hostid. Todos os endereços IP da classe A iniciam com o bit 0.
- Endereços do tipo B: são usados para redes de tamanho médio, alocam 14 bits para o netid e 16 bits para o hostid. Todos os endereços IP da classe B iniciam com os bits 10.
- Endereços do tipo C: alocam 21 bits para o netid e somente 8 bits para hostid. Todos os endereços IP da classe A iniciam com os bits 110.
- Endereços do tipo D e E: são usados para endereçamento multicast e reservas.

O endereço IP foi definido de tal modo que é possível extrair as partes do **netid** ou do **hostid** rapidamente. Os roteadores, que usam a parte **netid** de um endereço ao decidir qual o destino de um pacote, dependem de uma extração eficiente para alcançar velocidade alta.

**Notação para endereços IP**

Então, para que possamos reforçar, repassamos novamente como funciona os endereços IP´s.

São representados com quatro algarismos decimais separados por ponto decimal.

w . x . y . z

Exemplo:

10000000.00001010.00000010.00011110

128      .       10       .         2       .        30

Classe A: w varia de 1 até 126           w identifica a rede           x.y.z identificam o host           Exemplo: 10.1.2.3

Classe B: w varia de 128 a 191           w. x identificam a rede           y.z identificam o host           Exemplo: 129.1.2.3

Classe C: w varia de 192 a 223           w.x.y identificam a rede           z identifica o host           Exemplo: 192.1.2.3

Para que o roteamento funcione corretamente, os computadores precisam saber qual a classe de endereçamento do número de IP elas são, ou seja, ao qual rede um host pertence. Isso é feito pela máscara de sub-rede.

- Classe A - Máscara de Sub-rede: 255.0.0.0.
- Classe B - Máscara de Sub-rede: 255.255.0.0.
- Classe C - Máscara de Sub-rede: 255.255.255.0.

**Endereços privativos**

Há alguns endereços em cada classe de endereços IP que não são atribuídos. Esses endereços são chamados de endereços privativos, que podem ser usados por hosts que utilizam a network address translation (NAT) ou um servidor proxy, para se conectar a uma rede pública; ou por hosts que não estão conectados à internet.

Muitos aplicativos exigem conectividade dentro de apenas uma rede e não necessitam de conectividade externa. Em redes grandes, o TCP/IP é frequentemente usado, mesmo quando não é necessária a conectividade da camada de rede fora da rede. Os bancos são um bom exemplo. Eles podem usar o TCP/IP para se conectar aos caixas automáticos (ATMs). Essas máquinas não se conectam à rede pública e, portanto, os endereços privativos são ideais para elas. Os endereços privativos também podem ser usados em uma rede em que **não** haja endereços públicos suficientes.

Os endereços privativos podem ser usados com um servidor de conversão do endereço de rede (NAT) ou um servidor proxy para fornecer conectividade a todos os hosts em uma rede que tenha, relativamente, poucos endereços públicos disponíveis. Conforme estabelecido, todo o tráfego com um endereço de destino dentro de um dos intervalos de endereços privativos não serão roteados na internet.

Seguem os números privativos de acordo com a classe:

- Classe A: 10.0.0.0 a 10.255.255.255.
- Classe B: 172.16.0.0 a 172.31.255.255.
- Classe C: 192.168.0.0 a 192.168.255.255.

**O campo TOS**

O campo "TOS" significa "Tipo de Serviço" e é composto por 8 bits. Ele fornece uma indicação dos parâmetros da qualidade desejada (qualidade? Opa, é isso que nos interessa, afinal, estamos falando de qualidade de serviços em ambiente de redes, portanto, caro aluno, é por isso que o campo TOS merece uma atenção especial). Observe na figura 3, a seguir, um detalhe maior desse campo e a sua constituição de bits:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/1/119193/a01i03_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/1/119193/a01i03_quasar80_100.jpg)

Fonte: Adaptado de: TANENBAUM, A. S. _Redes de Computadores_. Rio de Janeiro: Campus, 2006.

Os três bits de precedência especificam a precedência dos pacotes, isto é, a importância destes, sendo 0 = pacotes normais e 7 = controle de rede.

Os bits D, T e R indicam o tipo de transporte desejado pelo pacote:

- O bit D solicita para minimizar atraso.
- O bit T solicita para maximizar o throughput.
- O bit R solicita para maximizar confiabilidade.

Normalmente, os bits de TOS são ignorados pelos roteadores e hosts. Se todos os roteadores e hosts respeitassem estes bits, o TOS poderia ser utilizado como um mecanismo para dar prioridade aos dados. Por isso que atualmente muitos algoritmos de congestionamento estão sendo implementados, para que se possa aproveitar melhor esse campo do cabeçalho, sem afetar realmente os tipos de dados que estão sendo controlados.

Se um roteador conhecer mais de um caminho para um mesmo destino, ele pode utilizar o TOS para selecionar um caminho com as características que mais se assemelha ao desejado. Por exemplo, um roteador pode selecionar entre uma linha privada de baixa capacidade, porém com pouco atraso, e uma conexão via satélite de alta capacidade com grande atraso. Pacotes com caracteres digitados podem ser enviados com D=1 para que sejam entregues o mais rápido possível, enquanto que, pacotes transferindo um arquivo podem ter bit T=1 para que sejam enviados via satélite.