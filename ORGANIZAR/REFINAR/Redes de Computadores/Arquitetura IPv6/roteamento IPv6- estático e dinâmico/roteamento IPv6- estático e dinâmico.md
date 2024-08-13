### Introdução

Nesse tópico serão apresentados os processos de roteamento utilizados por roteadores que usam uma rede com o protocolo IP.

O Roteamento é o mecanismo que permite a comunicação entre dois dispositivos ou mais disposiitvos, interligado através de uma LAN ( Local Area Network ) ou através da WAN ( Wide area network ). O roteamento, pode ser entendido como :

- A aprendizagem e seleção de caminhos alternativos através da Rede.
- Adoção e escolha dos melhores caminhos para redes distintas.

### Definição de Roteamento

São regras e configurações usadas para definir como os dados gerados em uma determinada rede devem alcançar outras, ou seja, se for necessário transmitir um pacote de dados de um dispositivo de uma rede para outro, em outra rede, teremos de efetuar o processo de roteamento.

Para verificar o "Roteamento" entre redes distintas, podemos seguir em um prompt de comando com a  digitação do comando "tracert", em um equipamento passa a rastrear o caminho realizado na rede e alcançar o endereço de destino solicitado (www.uninove.com.br). Foram realizados oito saltos desde o destino até cada um dos pontos. A cada salto a rede muda quando um novo ponto é alcançado. Assim, se as redes se alteram, os endereços listados no final de cada linha são roteadores, encaminhando pacotes de uma rede à outra. Consequentemente, para os dados saírem de uma rede e alcançar outra, um roteador estará executando essa tarefa.

![[Untitled 21.png|Untitled 21.png]]

### Tipos de roteamento

O papel do roteador é direcionar o tráfego para todas as redes selecionadas, e para isso deve conhecer algumas informações, como endereço de destino, rotas existentes nas redes remotas, roteadores vizinhos e qual é a melhor rota a ser selecionada.

Como podemos observar, para um pacote de dados gerado em uma rede alcançar outra, temos de preparar certo tipo de roteamento. Existem três tipos básicos: o estático, o dinâmico e o default.

Brevemente, veremos cada um deles:

- Roteamento estático: essa é uma das tarefas do administrador da rede que, manualmente, cria as tabelas de rotas (routing tables).
- Roteamento default: no tipo de roteamento default, o roteador já possui o conhecimento sobre a existência das redes que estão diretamente conectadas.
- Roteamento dinâmico: nesse processo, o roteador utiliza-se de protocolos de roteamento para fazer a comunicação com os roteadores vizinhos e, automaticamente, gera sua tabela.

Vamos nos prender um pouco mais nas características do "roteamento dinâmico", uma vez que ele apresenta diversos tipos de protocolos. Veremos alguns, como RIP, OSPF e BGP.

O processo de roteamento utiliza protocolos para encontrar e atualizar tabelas, definindo regras que serão utilizadas para a comunicação com roteadores vizinhos.Existem duas categorias de protocolos de roteamento utilizados em internetworks_**:**_ o IGP e o EGP.

- IGP (Interior Gateway Protocol): usado para a troca de informações entre roteadores que pertencem a uma coleção de redes sob um mesmo domínio administrativo.
- EGP (Exterior Gateway Protocol): protocolo usado para possibilitar a comunicação entre roteadores que estejam em redes distintas.v

### Tipos de Protocolo de Roteamento Dinâmico

### Protocolo RIP - versão 1 – RIPv1

Esse tipo de protocolo envia a tabela de roteamento completa a cada 30 s para todas as interfaces conectadas. É um roteamento do tipo "classful" em que todos os dispositivos que estiverem conectados à rede deverão estar sob a mesma máscara.

A configuração desse tipo de roteador é bastante simples. Devemos, em primeiro lugar, excluir as rotas estáticas que por ventura tenham sido estabelecidas. Depois, por meio do comando "config", acessamos o modo de configuração de roteamento e informamos qual rede deve ser propagada.

Vejamos um rápido exemplo:

Roteador x\#config t           Roteador x (config) \#no ip route 192.168.10.0 255.255.255.0 192.168.20.1          Roteador x (config) #no ip route 192.168.50.0 255.255.255.0 192.168.40.2          Roteador x (config) \#router rip          Roteador x (config) \#network 192.168.0.0          Roteador x (config) #^z

Efetuada a configuração, o protocolo RIPv1 identificará as sub-redes existentes utilizando-se das máscaras configuradas no roteador, contudo, por ser "classful", não irá propagar as informações da máscara para a rede.v

### Protocolo RIP – versão 2 – RIPv2

O protocolo RIPv2, uma vez que continua sendo um protocolo "distance vector", utiliza a distância existente na rede remota para definir o melhor caminho e também envia sua tabela de roteamento de forma periódica.

A diferença entre o RIPv1 e o RIPv2 está no aumento da escalabilidade, o que o torna o segundo adequado para atender redes de grande porte. Outro ponto diferente é que o protocolo RIPv2 propaga as informações de máscara de rede em suas atualizações.

Vejamos alguns comandos, entre muitos existentes, que permitem verificar as configurações usadas no protocolo RIP:

- sh running – Apresenta toda a configuração do roteador.
- sh ip route – Mostra a tabela completa de roteamento.
- sh ip route rip – Mostra as rotas informadas pelo protocolo RIP.
- sh ip rip database – Mostra o conteúdo da base de dados do protocolo RIP.

### Protocolo OSPF

O protocolo OSPF (Open Shortest Path First) é um protocolo aberto, de domínio público, independente de proprietários.

Outra característica é que ele utiliza o algoritmo SPF (Shortest Path First), que significa "menor rota primeiro", no qual os cálculos realizados usam a largura de banda para localizar a melhor rota.

Esse protocolo foi criado para atender redes de grande porte. Trabalha com propagação via "multicast", o que significa que somente os roteadores que estão no protocolo OSPF recebem as atualizações necessárias.

Outra vantagem da utilização do protocolo OSPF é que, quando uma nova rede for detectada, somente a informação dela será divulgada via "multicast" entre os roteadores vizinhos, o que gera economia de largura de banda e mais agilidade.

OSPF possui diversas outras características que o tornam um protocolo de roteamento rápido, robusto e confiável, utilizado em milhares de redes pelo mundo.

Vejamos alguns comandos usados na configuração do protocolo OSPF em um roteador:

- router ospf ? – Para ativar o protocolo OSPF.
- showm ip route – Apresenta as redes identificadas pelo protocolo OSPF.
- sh ip ospf data – Mostra o link ID, o RID do router e o processo OSPF ativo.

![[Untitled 1 13.png|Untitled 1 13.png]]

### Protocolo BGP (Border Gateway Protocol)

Trata-se de um protocolo usado nos roteadores que trabalham com os Prestadores de Serviços de Internet (ISPs). É um protocolo destinado às grandes redes. BGP significa Protocolo de Gateway Externo.

Construído visando à confiabilidade, escalabilidade e controle dos pacotes que trafegam entre uma rede e outra, O BGP não objetiva velocidade, o que o torna diferente dos outros protocolos de roteamento, como o RIP e o OSPF.

O BGP é um protocolo extremamente robusto e que necessita de inúmeros ajustes (atributos) para se tornar um protocolo confiável, caso contrário vai parecer um RIP. O seu funcionamento utiliza o algoritmo vetor de distância.

A regra de sincronização do BGP exige que, quando ele recebe  informações sobre uma rede vizinha, não a use até que uma rota correspondente seja aprendida através de uma rota estática. Também não anuncia essa rota a nenhum vizinho, a menos que uma rota correspondente esteja na tabela de roteamento.

O BGP escolhe a melhor rota para um destino com base na seguinte ordem: escolhe a rota com o maior peso; verifica o maior "Local Preference"; analisa as rotas de origem; o próximo salto; o caminho mais curto e a comunidade.

Suporta autenticação utilizando o algoritmo MD5 para criptografia da senha; ambos os roteadores devem compartilhar a mesma senha para que a relação seja formada. A configuração é feita dentro do modo de roteamento.

Vejamos alguns comandos usados no protocolo BGP:

- neighbor 192.168.10.2 password xxxx – Ativa a autenticação no roteador.
- neighbor remote – Para adicionar vizinhos estaticamente.
- router-id – Adiciona o IP da interface loopback.
- neighbor router-reflector-client – Para configurar os roteadores centrais e adicionar os demais roteadores como clientes.
- address-family ipv4 – Para configurar as vizinhanças, router-reflector, community, route-map etc.

![[Untitled 2 11.png|Untitled 2 11.png]]

### Considerações Finais

Outros protocolos estão disponíveis para auxiliar os administradores de rede na tarefa de configurar seus roteadores. Cabe lembrar que, dependendo do tipo de rede e das suas necessidades, vários outros protocolos poderão ser utilizados.