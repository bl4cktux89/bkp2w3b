Esse laboratório tem o objetivo de demonstrar a configuração de uma rede para a utilização de IPsec em modo de Transporte. O IPsec será configurado nos hosts n1HostABCD e n4Host1234, garantindo que todo tráfego entre eles seja protegido.Para o presente exercício será usada a topologia de rede descrita no arquivo: 3-03-IPsec-transport.imn.

**COMO OBTER OU TER ACESSO AO LIVRO LABORATÓRIO DE IPV6: APRENDA NA PRÁTICA USANDO UM EMULADOR DE REDES DO NICBR**

Este laboratório faz parte do livro Aprenda na prática usando um emulador de redes do NicBr.

Para a realização deste exercício será utilizada a topologia descrita no arquivo: 3-03-IPsec-transport.imn. que está disponível no site do NicBR, gratuitamente.

Siga os procedimentos indicados e vamos praticar !

Para saber mais, acesse faça o Download das máquinas virtuais e do livro em http://ipv6.br/pagina/livro-ipv6/

Ou ainda disponível, na versão física, em uma das Bibliotecas dos Campis da Universidade Uninove ! Confira !Venha nos visitar !

### Introdução 

Destinado principalmente a interligar redes de pesquisa acadêmicas, o projeto original do IPv4 não apresentava nenhuma grande preocupação com questões relacionadas à segurança das informações transmitidas. No entanto, o aumento da importância da Internet para a realização de transações entre empresas e consumidores, por exemplo, fez com que um nível maior de segurança passasse a ser exigido, como identificação de usuários e criptografia de dados, tornando necessário anexar novos mecanismos ao protocolo original, que garantissem tais serviços.

O IPsec foi criado para suprir esta deficiência. Ele é uma suíte de protocolos que atua como extensão do protocolo IP e oferece serviços de segurança para prover autenticidade, integridade e confidencialidade aos pacotes IP. Os serviços são providos na camada de rede e, portanto, também oferecem proteção às camadas superiores. Há dois modos de operação no IPsec, o modo de transporte e o modo túnel. O primeiro é usado para proteger a conexão entre apenas duas máquinas, enquanto que o segundo pode ser configurado entre roteadores de borda em redes diferentes, protegendo assim todo o tráfego entre estas duas redes.

(Santos, Moreiras (2015))

A estrutura do IPsec baseia-se em dois cabeçalhos:

Authentication Header (AH)Provê autenticação e integridade dos pacotes.

Encapsulated Security Payload (ESP)Adiciona confidencialidade por meio da criptografia dos dados a serem enviados.

()

Outro ponto fundamental para o funcionamento do IPsec é o compartilhamento das chaves utilizadas para autenticação e criptografia. Recomenda-se a utilização do protocolo IKE (Internet Key Exchange) para garantir um meio seguro para a troca das chaves entre os dispositivos que utilizam IPsec e essa troca pode ocorrer de dois modos: mediante o uso de chaves pré-compartilhadas; e da utilização de certificados X.509.O protocolo IKE trabalha em duas fases:1. Por meio de uma série de mensagens trocadas, a autenticidade dos dispositivos é verificada e uma chave ISAKMP SA (Internet Security Association Key Management Security Association) é gerada.2. A partir da chave ISAKMP SA, as chaves para o AH e ESP para esta comunicação são geradas e o IPsec começa a ser utilizado.

(Santos, Moreiras (2015))

Fonte: Santos,Moreiras (2015)

### Roteiro experimental

1. Inicie o CORE e abra o arquivo 3-03-IPsec-transport.imn localizado no diretório lab, dentro do Desktop. A topologia da rede, representada pela Figura 3.19, deve aparecer.

![[Untitled 26.png|Untitled 26.png]]

O objetivo desta topologia de rede é demonstrar que a implantação do IPsec em modo de transporte independe da topologia de rede, isto é, que o IPsec consegue autenticar e criptografar pacotes que são roteados por diversos nós até chegarem ao destino. Neste exemplo, o IPsec será configurado nos hosts n1HostABCD e n4Host1234. Note que há dois roteadores intermediando a comunicação entre os hosts.

Primeiro serão enviados pacotes de echo request sem o IPsec estar configurado.A seguir, será configurada uma conexão com somente autenticação entre os dois hosts. Depois disto, irá configurar uma conexão com autenticação e criptografia, capturando pacotes a cada alteração da configuração.

Ao final, serão analisados os pacotes capturados nas três situações.

Fonte: Santos,Moreiras (2015)

Inicialize a simulação e verifique a configuração de endereços IPv6 nos nós n1HostABCD e n4Host1234.

3. Faça a captura de pacotes transmitidos entre os hosts sem a configuração do IPsec.

4. Em paralelo, efetue:

(a) A coleta dos pacotes trafegados na interface eth1 de n2RouterABCD.

(b) A verificação de conectividade IPv6 entre n1HostABCD e n4Host1234.

Após efetuar a verificação de conectividade IPv6, encerre a coleta de pacotes trafegados do n2RouterABCD, por meio da combinação de teclas Ctrl+C no terminal em que o tcpdump estiver sendo executado.

5. No terminal do n1HostABCD, gere a chave de autenticação AH executando o comando a seguir. Este comando gerará a chave AH, criará o arquivo chave-ah-h1 e armazenará nele a chave gerada.

# dd if=/dev/random count=16 bs=1 | xxd -ps > chave-ah-h1

O resultado do comando é representado pela Figura 3.20.

Fonte: Santos,Moreiras (2015)

![[Untitled 1 16.png|Untitled 1 16.png]]

6. Gere a chave de criptografia ESP para o mesmo host, executando o comando a seguir no terminal. Este comando gerará a chave ESP, criará o arquivo chave-esp-h1 e armazenará nele a chave gerada.

# dd if=/dev/random count=24 bs=1 | xxd -ps > chave-esp-h1

O resultado do comando é representado pela Figura 3.21.

Fonte: Santos,Moreiras (2015)

![[Untitled 2 14.png|Untitled 2 14.png]]

Após a execução dos comandos anteriores, verifique o conteúdo do arquivo chave-ah-h1 por meio do comando cat e anote o valor apresentado.

# cat chave-ah-h1

O resultado deve ser similar ao representado na Figura 3.22. Note a extensão da chave AH e os caracteres hexadecimais que a compõem. A  chave gerada durante a experiência deve conter a mesma quantidade decaracteres, mas será diferente da chave apresentada na Figura 3.22.

![[Untitled 3 9.png|Untitled 3 9.png]]

7. No terminal do n4Host1234, gere a chave de autenticação AH executando o comando a seguir:

# dd if=/dev/random count=16 bs=1 | xxd -ps > chave-ah-h2

O resultado deve ser similar ao representado na Figura 3.23.

8. Gere a chave de criptografia ESP para o mesmo host, executando o comando a seguir no terminal:

# dd if=/dev/random count=24 bs=1 | xxd -ps > chave-esp-h2

Fonte: Santos,Moreiras (2015)

O resultado deve ser similar ao da Figura 3.23 e Figura 3.24

Fonte: Santos,Moreiras (2015)

![[Untitled 4 9.png|Untitled 4 9.png]]

Após a execução do comando anterior, execute o comando cat para verificar o conteúdo do arquivo chave-ah-h2. Anote o valor apresentado:

# cat chave-ah-h2

O resultado deve ser similar ao representado na Figura 3.25.

![[Untitled 5 8.png|Untitled 5 8.png]]

9. Escreva o arquivo de configuração do IPsec para o n1HostABCD.

(a) Abra um terminal de n1HostABCD com um duplo-clique e crie o arquivo de configuração do IPsec:

# touch ipsec-h1.conf

O resultado do comando é representado pela Figura 3.26.

Fonte: Santos,Moreiras (2015)

![[Untitled 6 7.png|Untitled 6 7.png]]

(b) Ainda no terminal de n1HostABCD, edite o arquivo de configuração do IPsec, localizado em ipsec-h1.conf, de modo a inserir as seguintes linhas:

#!/usr/sbin/setkey -fflush;spdflush;add 2001:db8:1234::2 2001:db8:abcd::2 ah 0x300-A hmac-md5 0x[chave-ah-h1];add 2001:db8:abcd::2 2001:db8:1234::2 ah 0x301-A hmac-md5 0x[chave-ah-h2];spdadd 2001:db8:1234::2/64 2001:db8:abcd::2/64 any-P in ipsec ah/transport//require;spdadd 2001:db8:abcd::2/64 2001:db8:1234::2/64 any-P out ipsec ah/transport//require;

Lembre-se de trocar a parte [chave-ah-h1] e a parte [chave-ah-h2], sem os colchetes, pelas chaves reais, que estão armazenadas nos arquivos chave-ah-h1 e chave-ah-h2.A primeira linha define o setkey como o interpretador das linhas seguintes no arquivo. Já o comando flush limpa todas as entradas existentes no SAD (Security Association Database), enquanto o spdflush limpa todasas entradas do SPD (Security Policy Database).

(c) Logo em seguida há o comando de criação de SA (Security Association), uma linha para cada uma das duas SAs (identificado pelo comando add) de autenticação do n1HostABCD. Lembre-se que as SAs são unidirecionais, isto é, cada SA é definida para apenas um sentido da comunicação entre dois pontos de rede, o que torna necessário criar duas SAs para cada comunicação bidirecionalmente segura. As SAs definem também qual o protocolo a ser usado (nestes exemplos, ou AH ou ESP), um índice único maior que 255 (o índice também pode ser escrito em hexadecimal, usando o prefixo 0x), o algoritmo usado na criação da chave (os grupos de algoritmos possíveis são diferentes para autenticação e para criptografia) e a chave AH da máquina com o IP de origem. A estrutura do comando que cria uma SA é apresentada a seguir:

add [ip_origem] [ip_destino] [protocolo] [indice] [algoritmo] [chave];

Nesta experiência, haverá apenas a autenticação entre os hosts n1HostABCD e n4Host1234, portanto será necessário definir apenas duas SAs: uma para a autenticação dos pacotes enviados desta máquina para o n4Host1234 e outra para a autenticação dos pacotes enviados do n4Host1234 para esta máquina. Os parâmetros usados serão:

Fonte: Santos,Moreiras (2015)

[ip_origem]          2001:db8:1234::2[ip_destino]         2001:db8:abcd::2[protocolo]           ah[indice]                0x300 (o valor foi escolhido aleatoriamente)[algoritmo]           -A hmac-md5[chave]                 chave AH presente no arquivo chave-ah-h1, gerado anteriormente. Como este valor é hexadecimal, é necessário colocar o prefixo 0x antes do valor.

Fonte: Santos,Moreiras (2015)

A linha de comando para gerar a segunda SA, no sentido oposto de comunicação, será muito similar à linha anterior, porém com as seguintes diferenças: primeiro, os IPs serão trocados de posição (o IP abcd::2será a origem e o IP 1234::2 será o destino); segundo, o índice terá que ser diferente (por exemplo, 0x301) e; terceiro, a chave AH também será diferente (neste exemplo, a chave será o conteúdo do arquivo chave-ah-h2.

Não se deve esquecer de colocar o prefixo 0x antes da chave.

(d) Depois da definição de SAs, são definidas as políticas de segurança desta máquina. Neste exemplo, será utilizado o seguinte formato simplificado para a política:

spdadd [ips_origem] [ips_destino] [protocolo_camada_superior] [politica];

Fonte: Santos,Moreiras (2015)

As políticas também são unidirecionais e precisam ser definidas aos pares se for preciso uma segurança IPsec nos dois sentidos de comunicação. Os dois primeiros parâmetros são iguais aos das SAs, porém aqui eles podem definir tanto um único IP quanto um intervalo de IPs (por exemplo, pode-se definir como IPs de origem um prefixo como 2001:db8::/64). O terceiro parâmetro, [protocolo_camada_superior], define em quais protocolos das camadas superiores do TCP/IP o IPsec será aplicado (neste caso se usará any, o que significa que esta política será aplicada aos pacotes de todos os protocolos cabíveis). O último parâmetro ([politica]) define o que será feito com os pacotes enviados de [ips_origem] para [ips_destino] e que possuem o protocolo definido em [protocolo_camada_superior]. O campo começa com o parâmetro -P, depois define a direção da comunicação (as opções são out, in e fwd, que significa forward); a seguir define-se as opções de tratamento dos pacotes, que são discard, none e ipsec (será usada esta última) e, por fim, define-se a regra pela qual os pacotes serão processados.

Neste exemplo, a regra será ah/transport//require.

Assim, os parâmetros usados para a primeira política serão:[ips_origem]                                       2001:db8:1234::2[ips_destino]                                      2001:db8:abcd::2[protocolo_camada_superior]            any[politica]                                             -P in ipsec ah/transport//require

A linha de comando para gerar a segunda política, no sentido oposto de comunicação, será muito similar à linha anterior, porém com as seguintes diferenças: primeiro, os IPs serão trocados de posição (o IP abcd::2 será a origem e o IP 1234::2 será o destino) e segundo o campo [politica] terá o sentido out no lugar de in.

(e) Exiba o conteúdo do arquivo:

# cat ipsec-h1.conf

O resultado do comando é representado pela Figura 3.27, exceto pelos valores das chaves.

Fonte: Santos,Moreiras (2015)

![[Untitled 7 6.png|Untitled 7 6.png]]

10. Escreva o arquivo de configuração do IPsec para o n4Host1234.

(a) Abra um terminal de n4Host1234 com um duplo-clique e crie o arquivo de configuração do IPsec. Execute o seguinte comando:

# touch ipsec-h2.conf

O resultado do comando é representado pela Figura 3.28.

![[Untitled 8 6.png|Untitled 8 6.png]]

(b) Ainda no terminal de n4Host1234, edite o arquivo de configuração do IPsec, localizado em ipsec-h2.conf, de modo a inserir as seguintes linhas:

#!/usr/sbin/setkey -fflush;spdflush;

add 2001:db8:1234::2 2001:db8:abcd::2 ah 0x300

- A hmac-md5 0x[chave-ah-h1];add 2001:db8:abcd::2 2001:db8:1234::2 ah 0x301A hmac-md5 0x[chave-ah-h2];

spdadd 2001:db8:1234::2/64 2001:db8:abcd::2/64 any -P out ipsecah/transport//require;spdadd 2001:db8:abcd::2/64 2001:db8:1234::2/64 any -P in ipsecah/transport//require;

Fonte: Santos,Moreiras (2015)

Lembre-se de trocar a parte [chave-ah-h1] e a parte [chave-ah-h2], sem os colchetes, pelas chaves reais, que estão armazenadas nos arquivos chave-ah-h1 e chave-ah-h2.

Observando os parâmetros anteriores, perceba como as SAs do n4Host1234 serão exatamente iguais às SAs do n1HostABCD. De fato, a SA de saída de pacotes do n1HostABCD é exatamente igual à SA de entrada de pacotes do n4Host1234 e a de entrada de pacotes do n1HostABCD é igual à de saída de pacotes do n4Host1234. Porém, como a ordem de declaração das SAs não importa e as SAs não deixam explícito se o sentido é de entrada ou de saída, basta copiar as SAs do n1HostABCD para o arquivo de configuração de sufixo .conf de n4Host1234.

(c) Observe também que, ao contrário das SAs, as políticas de segurança SPD dizem explicitamente se o sentido de comunicação é de saída (out) ou de entrada (in). Tal declaração está dentro do parâmetro [politica].Observe também que, com exceção deste detalhe, as duas políticas do n4Host1234 serão iguais às duas políticas do n1HostABCD. A diferença estará exatamente neste sentido de comunicação, que deve ser trocado nas duas políticas do n4Host1234. Portanto, para definir as políticas do n4Host1234 neste exemplo, basta copiar as políticas do n1HostABCD e inverter o sentido de comunicação (mudar para out onde for in e mudar para in onde for out).

Fonte: Santos,Moreiras (2015)

(d) Exiba o conteúdo do arquivo:

# cat ipsec-h2.conf

O resultado deve ser similar ao representado na Figura 3.29.

(d) Exiba o conteúdo do arquivo:

# cat ipsec-h2.conf

O resultado deve ser similar ao representado na Figura 3.29.

Fonte: Santos,Moreiras (2015)

![[Untitled 9 5.png|Untitled 9 5.png]]

Atente-se para as diferenças entre este arquivo e o arquivo ipsec-h1.conf. As únicas diferenças são o sentido de comunicação in/out explicitado nas políticas de comunicação. Isto significa que o processo de escrita dos dois arquivos de sufixo .conf se limita a compor apenas um deles, copiá-lo para a outra máquina e alterar o in/out nas políticas spdadd.

11. Abra o terminal do n1HostABCD e carregue as configurações do arquivo ipsec-h1.conf com o comando a seguir:

# setkey -f ipsec-h1.conf

Se o arquivo for carregado corretamente, nenhuma mensagem será impressa após a execução do comando setkey -f, como mostra a Figura 3.30.

![[Untitled 10 4.png|Untitled 10 4.png]]

Caso surja alguma mensagem, o arquivo possivelmente terá algum erro de sintaxe. Neste caso, verifique novamente os comandos descritos nos passos anteriores.

Para verificar se as chaves foram carregadas, execute o seguinte comando:

# setkey -D

Este comando exibe as SAs que a máquina possui. Caso as SAs tenham sido corretamente carregadas, o resultado do comando deve ser similar ao representado pela Figura 3.31.

Fonte: Santos,Moreiras (2015)

![[Untitled 11 3.png|Untitled 11 3.png]]

Já o comando a seguir exibe as políticas de segurança configuradas:

# setkey -DP

O resultado do comando é representado pela Figura 3.32.

Fonte: Santos,Moreiras (2015)

![[Untitled 12 3.png|Untitled 12 3.png]]

12. Abra o terminal do n4Host1234 e carregue as configurações do arquivo ipsec-h2.conf. Para isto o seguinte comando deve ser utilizado:

# setkey -f ipsec-h2.conf

Verifique se nenhum erro ocorreu, como mostra a Figura 3.33.

![[Untitled 13 3.png|Untitled 13 3.png]]

Para verificar se as chaves foram carregadas, execute os seguintes comandos:

# setkey -D# setkey -DP

O resultado deve ser similar ao representado na Figura 3.34.

Fonte: Santos,Moreiras (2015)

![[Untitled 14 3.png|Untitled 14 3.png]]

13. Em paralelo, efetue:

(a) A coleta dos pacotes trafegados na interface eth1 de n2RouterABCD. As instruções de coleta de pacotes utilizando tcpdump ou Wireshark se encontramno Apêndice C.

(b) A verificação de conectividade IPv6 entre n1HostABCD e n4Host1234. Após efetuar a verificação de conectividade IPv6, encerre a coleta de pacotes trafegados do n2RouterABCD, por meio da combinação de teclas Ctrl+C no terminal em que o tcpdump estiver sendo executado.Agora será configurada a criptografia entre os dois terminais, em adição à autenticação feita anteriormente. Para isto, altere os arquivos de sufixo .conf já gerados e os recarregue. Em seguida, faça uma terceira captura de pacotes, para análise posterior.

14. Exiba e anote as chaves ESP geradas anteriormente para os hostsn1HostABCD e n4Host1234:(a) No terminal do n1HostABCD, exiba a chave ESP armazenada no arquivo chave-esp-h1:

# cat chave-esp-h1

O resultado deve ser similar ao representado na Figura 3.35.

Anote o valor apresentado. Perceba como o valor é consideravelmente maior que o valor da chave AH. Contudo, o valor também é hexadecimal, e deverá ter o prefixo 0x dentro do arquivo de sufixo .conf.

Fonte: Santos,Moreiras (2015)

![[Untitled 15 3.png|Untitled 15 3.png]]

(b) No terminal do n4Host1234, exiba a chave ESP armazenada no arquivo chave-esp-h2 e anote o valor apresentado.

# cat chave-esp-h2

O resultado deve ser similar ao representado na Figura 3.36, exceto pelo valor da chave.

![[Untitled 16 3.png|Untitled 16 3.png]]

15. Altere o arquivo de configuração ipsec-h1.conf para incluir a configuração da criptografia:

(a) No terminal do n1HostABCD, edite o arquivo de configuração ipsec-h1.conf. No Apêndice C são apresentados alguns editores de texto disponíveis, p.ex. nano.Crie mais um par de SAs correspondentes ao processo de criptografia para o n1HostABCD, inserindo, após o segundo comando add já presente no arquivo, mais duas linhas de comando add:add 2001:db8:1234::2 2001:db8:abcd::2 esp 0x302 -E 3des-cbc 0x[chave-esp-h1];add 2001:db8:abcd::2 2001:db8:1234::2 esp 0x303 -E 3des-cbc 0x[chave-esp-h2];Explicando os parâmetros usados:

[ip_origem] 2001:db8:1234::2[ip_destino] 2001:db8:abcd::2[protocolo] esp[indice] 0x302 (deve ser diferente dos valores já existentes)[algoritmo] -E 3des-cbc[chave] chave ESP presente no arquivo chave-esp-h1, gerado anteriormente. Este valor também é hexadecimal, logo é necessário colocar o prefixo 0x antes da chave.

Fonte: Santos,Moreiras (2015)

A linha de comando para gerar a segunda SA, no sentido oposto de comunicação, será muito similar à linha anterior, porém com as seguintes diferenças: primeiro, os IPs serão trocados de posição (o IP abcd::2 será aorigem e o IP 1234::2 será o destino), segundo, o índice terá que ser diferente (por exemplo, 0x303) e, terceiro, a chave ESP também será diferente (neste exemplo, a chave será o conteúdo do arquivo chave-esp-h2).O arquivo ipsec-h1.conf apresentará, neste momento, um conteúdo similar ao representado na Figura 3.37.

Fonte: Santos,Moreiras (2015)

![[Untitled 17 3.png|Untitled 17 3.png]]

16. Atualize o arquivo de configuração do IPsec para o n4Host1234 para incluir a criptografia.

(a) No terminal do n4Host1234, edite o arquivo de configuração ipsec-h2.conf. No Apêndice C são apresentados alguns editores de texto disponíveis, p.ex. nano.Após o segundo comando add já presente no arquivo, insira mais duas linhas de comando add, que definirão o novo par de SAs para a criptografia.

Lembrando que o par de SAs é idêntico para os dois hosts, copie as SAs de criptografia apresentadas no passo anterior (que serão reapresentadasa seguir):

add 2001:db8:1234::2 2001:db8:abcd::2 esp 0x302-E 3des-cbc 0x[chave-esp-h1];add 2001:db8:abcd::2 2001:db8:1234::2 esp 0x303-E 3des-cbc 0x[chave-esp-h2];

Fonte: Santos,Moreiras (2015)

(b) A seguir, atualize as políticas de segurança desta máquina para incluir a criptografia. Ao contrário dos comandos add, que definem apenas uma SA cada, os comandos spdadd podem definir mais de um protocolo de segurança como parte da política, numa única linha de comando. Para isto edite as linhas que começam com spdadd para que fiquem:

spdadd 2001:db8:1234::2/64 2001:db8:abcd::2/64 any -P in ipsecesp/transport//requireah/transport//require;spdadd 2001:db8:abcd::2/64 2001:db8:1234::2/64 any -P out ipsecesp/transport//requireah/transport//require;

Lembrando a estrutura do comando spdadd:

spdadd [ips_origem] [ips_destino] [protocolo_camada_superior] [politica];

A política é definida após o parâmetro [protocolo_camada_superior] e apresenta a seguinte forma no arquivo:-P in ipsecah/transport//requirePara incluir um segundo protocolo de segurança, basta definir o protocoloadicional antes do primeiro, o que fará com que o parâmetro [politica]assuma a seguinte forma:-P in ipsecesp/transport//requireah/transport//requireA ordem em que os protocolos ESP e AH são declarados é importante e deve ser respeitada, isto é, o protocolo ESP deve ser declarado primeiro e em seguida o protocolo AH.(c) Exiba o conteúdo do arquivo:

# cat ipsec-h1.conf

O resultado deve ser similar ao representado na Figura 3.38, exceto pelo valor das chaves.

Fonte: Santos,Moreiras (2015)

![[Untitled 18 3.png|Untitled 18 3.png]]

(b) A seguir, atualize as políticas de segurança desta máquina para incluir a criptografia. Altere os comandos spdadd para incluir o texto esp/transport//require antes do texto ah/transport//require. Da mesmamaneira, troque o parâmetro out por in no primeiro comando e troque o parâmetro in por out no segundo. Aplique as diferenças marcadas em negrito no arquivo de configuração, confome a seguir:

spdadd 2001:db8:1234::2/64 2001:db8:abcd::2/64 any -P out ipsecesp/transport//requireah/transport//require;spdadd 2001:db8:abcd::2/64 2001:db8:1234::2/64 any -P in ipsecesp/transport//requireah/transport//require;

(c) Exiba o conteúdo do arquivo:

# cat ipsec-h2.confO resultado deve ser similar ao representado na Figura 3.39, exceto pelo valor das chaves.

![[Untitled 19 3.png|Untitled 19 3.png]]

Perceba mais uma vez que a única diferença entre o conteúdo do ipsec-h2.conf e o conteúdo do ipsec-h1.conf é a inversão da direção de comunicação nas políticas de segurança (onde era out torna-se in e onde

era in torna-se out).

17. Abra o terminal do n1HostABCD e recarregue as configurações do arquivo ipsec-h1.conf com o comando a seguir:

# setkey -f ipsec-h1.conf

Para verificar se as chaves foram carregadas, execute o seguinte comando:

# setkey -D

O resultado deve ser similar ao representado na Figura 3.40.

Execute também o seguinte comando:

# setkey -DP

O resultado do comando é representado pela Figura 3.41.

18. Abra o terminal do n4Host1234 e recarregue as configurações do arquivo ipsec-h2.conf com o comando a seguir:

# setkey -f ipsec-h2.conf

Para verificar se as chaves foram carregadas, execute os seguintes comandos:

# setkey -D

# setkey -DP

O resultado deve ser similar ao representado na Figura 3.34, visto anteriormente.

Fonte: Santos,Moreiras (2015)

![[Untitled 20 3.png|Untitled 20 3.png]]

![[Untitled 21 3.png|Untitled 21 3.png]]

19. Em paralelo, efetue:

(a) A coleta dos pacotes trafegados na interface eth1 de n2RouterABCD. As instruções de coleta de pacotes utilizando tcpdump ou Wireshark se encontramno Apêndice C.(b) A verificação de conectividade IPv6 entre n1HostABCD e n4Host1234. Após efetuar a verificação de conectividade IPv6, encerre a coleta de pacotes trafegados do n2RouterABCD, por meio da combinação de teclas Ctrl+C no terminal em que o tcpdump estiver sendo executado.

20. Analise agora os pacotes capturados nas três situações:

- Topologia sem IPsec
- Topologia somente com autenticação
- Topologia com autenticação e criptografia

Fonte: Santos,Moreiras (2015)

21. Veja se os dados contidos nos pacotes conferem com o que foi passado na teoria.

(a) Abra o arquivo contendo a captura da topologia sem IPsec e efetue a análise dos pacotes coletados. Aplique o filtro icmpv6 no Wireshark e procure pelo pacote echo reply, conforme apresentado na Figura 3.42.

![[Untitled 22 3.png|Untitled 22 3.png]]

(b) Analise um pacote ICMPv6 de echo reply de 2001:db8:1234::2 para 2001:db8:abcd::2. Note que, é possível analisar todo o conteúdo do pacote,inclusive o conteúdo do campo data. Caso o pacote echo request fosse falsificado, com o dono se fazendo passar pelo dispositivo 2001:db8:1234::2,a resposta seria enviada mesmo assim.

(c) Abra o arquivo contendo a captura da topologia somente com autenticação, e efetue a análise dos pacotes coletados. Aplique o filtro icmpv6 no Wireshark e procure pelo pacote echo reply. A estrutura do pacote será similar ao apresentado na Figura 3.43.

Fonte: Santos,Moreiras (2015)

![[Untitled 23 2.png|Untitled 23 2.png]]

(d) Analise um pacote de 2001:db8:1234::2 para 2001:db8:abcd::2. Note o cabeçalho de extensão AH que aparece no final do cabeçalho IPv6. Embora o conteúdo do pacote esteja visível para qualquer um que consiga capturá-lo (seja o destinatário do pacote, seja um sniffer no meio da rede), o destinatário só responderá o pacote se o remetente possuir a chave de autenticação. Isto significa que, embora os dados não sejam confidenciais, eles são confiáveis e íntegros (garante-se que a origem do pacote não foi forjada e que o pacote não foi modificado). A utilização somente de autenticação se justifica nos casos em que o conteúdo nãonecessita ser protegido, mas é preciso garantir que o pacote foi enviado por um dispositivo autorizado. Utilizar somente autenticação também é uma técnica utilizada por dispositivos com capacidade de processamentolimitada, que não seriam capazes de processar pacotes criptografados em tempo hábil, uma vez que os algoritmos de criptografia necessitam de bastante processamento.

(e) Abra o arquivo referente a topologia com autenticação e criptografia, conforme representado na Figura 3.44. Aplique o filtro icmpv6 no Wireshark e procure pelo pacote echo reply.

![[Untitled 24 2.png|Untitled 24 2.png]]

(f) Note que não é possível analisar todo o conteúdo do pacote. Inclusive, é impossível saber que o pacote em questão é um pacote de echo reply. Neste exemplo, sabe-se o tipo do pacote apenas porque força-se a geração dos mesmos por meio de ping6. Outro ponto interessante é que para a camada de aplicação a criptografia dos pacotes é transparente e não afeta seu funcionamento, pois elas recebem e enviam pacotes sem qualquer criptografia ou autenticação, uma vez que estas são geradas e removidas pela camada IP. Note também a existência do cabeçalho de autenticação AH, impedindo que um pacote falsificado seja tratado e respondido pelo destino. Portanto, os dados deste pacote são confidenciais, confiáveis e íntegros.

22. Encerre a simulação.

Fonte: Santos,Moreiras (2015)