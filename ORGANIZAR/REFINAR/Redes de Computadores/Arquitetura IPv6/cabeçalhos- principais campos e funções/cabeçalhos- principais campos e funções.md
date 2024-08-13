O cabeçalho é uma tabela que carrega todas as informações de um pacote IP e nessa tabela contém campos. O cabeçalho do IPv6 trouxe uma gama de mudanças perante o seu antecessor, como a redução de campos, a padronização de tamanho, além de otimizar a performance do roteador.

O cabeçalho no IPv4 é constituído por 12 campos, sujeitos à variação entre 20 e 60 Bytes de tamanho. Nestes campos contém informações como a versão do protocolo, os tipos de dados que estão sendo encaminhados, o tamanho dos dados e do cabeçalho, integridade dos dados que contém no pacote, o remetente e destinatário do pacote, a duração do pacote (tempo de vida) e as informações sobre a fragmentação do pacote.

![[Untitled 10.png|Untitled 10.png]]

Fonte: http://ipv6.br/post/cabecalho/

O IPv6 trouxe inúmeras mudanças no formato de cabeçalho com a finalidade de torná-lo mais simples e prático ao ser processado. Dentre essas mudanças está a redução e padronização do tamanho do cabeçalho que agora passou a ter 40 Bytes. Outra redução foi no número de campos , que agora são 8 no total.

Os campos que constituem o cabeçalho dos pacotes IPv6 são: Versão (ocupando 4 bits de espaço, este campo apresenta a versão de protocolo que foi utilizada), Classe de Tráfego (ocupando 8 bits de espaço, este campo especifica o pacote pela classe de serviço ou prioridade do mesmo), Identificador de Fluxo (ocupando 20 bits de espaço, associa o pacote aos pacotes do mesmo fluxo, gerando uma melhor gestão dos pacotes pelos nós intermediários), Tamanho dos Dados (contendo 16 bits de espaço, mostra o tamanho dos dados encaminhados com o cabeçalho, incluindo os cabeçalhos de extensão e diferentemente do campo correspondente no IPv4, não apresenta mais o tamanho dos dados contidos no pacote), Próximo Cabeçalho (contendo 8 bits de espaço, indica o cabeçalho de extensão que sucederá o cabeçalho atual), Limite de Encaminhamento (contendo 8 bits de espaço, define a quantidade máxima de roteadores o pacote terá a oportunidade de passar antes de ser excluído), Endereço de Origem (contendo 128 bits de espaço, apresenta o endereço IP de origem do pacote) e Endereço de Destino (contendo 128 bits de espaço, apresenta o endereço IP de destino do pacote).

![[Untitled 1 4.png|Untitled 1 4.png]]

### Cabeçalhos de extensão

Os cabeçalhos de extensão são cabeçalhos opcionais que podem ser vinculados ao cabeçalho principal. No IPv4 essas informações opcionais eram colocadas no cabeçalho principal, causando uma demora maior para a leitura do cabeçalho. Os cabeçalhos são acessados de forma sequencial, sequência que é  estipulada através do campo Próximo Cabeçalho.  A ordem dos cabeçalhos pode ser escolhida, mas existe uma sequência recomendável com o fim de reduzir o tempo da chegada do pacote ao seu destino final, fazendo com que os nós intermediários interpretem apenas os cabeçalhos que forem necessários para que o pacote avance para o próximo nó. Esta sequência recomendada é: Hop-by-Hop Options, Routing, Fragmentation, Authentication Header, Encapsulating Security Payload e Destination Options.

![[Untitled 2 5.png|Untitled 2 5.png]]

### Cabeçalho de extensão: Hop-by-Hop (salto por salto)

O primeiro cabeçalho, representado pelo número 00 no campo Próximo Cabeçalho, o Hop-by-Hop, tem que, obrigatoriamente, ser lido por todos os nós intermediários. Caso o cabeçalho Hop-by-Hop não seja inserido no pacote, os nós lerão apenas o cabeçalho principal, o que otimiza o envio do pacote ao próximo nó. Os campos presentes neste cabeçalho são: Próximo cabeçalho (com o tamanho de 1 Byte, define o próximo cabeçalho a ser lido), Tamanho do Cabeçalho (com o tamanho de 1 Byte, como o próprio nome sugere, indica o tamanho do cabeçalho) e Opções (tem o tamanho indefinido). Nas opções, o primeiro passo é definir um procedimento para o nó tomar caso não consiga interpretar as informações descritas. Este procedimento é constituído por 1 Byte onde os dois primeiros bits indicam que: 00 (o nó deve ignorar as opções e dar continuidade ao processamento), 01 (excluir o pacote), 10 (excluir o pacote e mandar uma mensagem ICMP Parameter Problem reportando o erro ao remetente do pacote), 11 (excluir o pacote e mandar uma mensagem ICMP Parameter Problem reportando o erro ao remetente do pacote, somente se o destinatário não for um multicast). O terceiro bit mostra se a informação opcional pode ter sua rota alterada: 1 (sim) e 0 (não). Há dois tipos de cabeçalho Hop-by-Hop, sendo eles: Router Alert (em português Alerta do roteador, avisa aos nós intermediários se a mensagem a ser enviada precisa de um tratamento especial) e Jumbogram (comunica que o pacote IPv6 contém mais de 64KB).

### Cabeçalho de extensão: Destination Options (Opções de destino)

O segundo cabeçalho, representado pelo número 60 no campo Próximo Cabeçalho, o Destination Options, é lido apenas pelo destinatário final. Os seus campos são idênticos aos do Hop-by-Hop e tem a finalidade de oferecer assistência ao serviço de mobilidade que o IPv6 oferece com a opção Home Address que armazena o endereço da rede de origem do nó móvel.

### Cabeçalho de extensão: Routing (encaminhamento)

O terceiro cabeçalho, representado pelo número 43 no campo Próximo Cabeçalho, o Routing, num primeiro momento foi designado para comunicar, quantos e quais nós deveriam ser visitados antes de chegar ao seu destino final. Porém, por questões de segurança foi alterado, gerando o seu Type 2 que agora faz parte do serviço de mobilidade do IPv6. Ele armazena o endereço local do remetente móvel e anexa ao pacote. Este cabeçalho apresenta os seguintes campos: Próximo cabeçalho (contendo 1 Byte de tamanho, indica qual é o próximo cabeçalho a ser lido), Tamanho do cabeçalho (contendo 1 Byte, apresenta o tamanho do cabeçalho atual), Routing Type (contendo 1 Byte, mostra o tipo de Routing que está sendo utilizado, atualmente utiliza-se o Type 2), Saltos restantes (para uso exclusivo do Type 0, mostra quando saltos ainda devem ser efetuados para que o pacote chegue ao seu destino final), Endereço de origem (apresenta o endereço local de um dispositivo móvel).

### Cabeçalho de extensão: Fragmentation (Fragmentação)

O quarto cabeçalho, representado pelo número 44 no campo Próximo Cabeçalho, o Fragmentation, é aplicado geralmente quando o pacote é superior em tamanho quanto ao limite do Path MTU. Os seus campos são: Próximo Cabeçalho (com 1 Byte de tamanho, indica o cabeçalho sucessor), Deslocamento do fragmento (contendo 13 bits de tamanho, este campo posiciona o fragmento que contém no pacote perante o dado completo), Flag M (contendo 1 bit de tamanho, com o valor 0 indica que não há mais fragmentos restando, enquanto o valor 1 afirma a existência de outros fragmentos), Identificação (contendo 4 Bytes, armazena informações sobre o pacote original e sobre qual fragmento se encontra no pacote atual).

### Cabeçalho de extensão: Authentication Header (Cabeçalho de autenticação) e Encapsulating Security Payload

Respectivamente, o quinto e sexto cabeçalho de extensão, de números 51 e 50, são elementos do IPSec. E apresentam informações de autenticação e integridade dos dados do pacote.