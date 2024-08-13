**Introdução à comutação**

Com a invenção do telefone por Alexander Graham Bell, em 1876, foi necessário o desenvolvimento de centrais telefônicas que pudessem interligar os usuários. Para que a conexão fosse estabelecida era necessário que uma telefonista intercambiasse alguns fios, conforme mostrado na Figura 1. Com o aumento da quantidade de usuários com telefone, esse processo tornou-se extremante exaustivo para as telefonistas e tecnologicamente incapaz de atender a uma demanda crescente. Para resolver esse problema foram desenvolvidos os comutadores. Os **comutadores** são dispositivos capazes de estabelecer conexões temporárias entre dois ou mais dispositivos conectados ao comutador (Forouzan, B. A, 2007).

O surgimento dos comutadores se justifica também pela impossibilidade de estabelecer uma ligação ponto-a-ponto, ou seja, uma ligação direta e permanente entre os usuários finais. Isso levaria a um desperdício de recursos, já que o link poderia ficar ociosa grande parte do tempo, além de exigir que a infraestrutura fosse consideravelmente maior, principalmente, em relação a quantidade de links de comunicação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/0/299089/19784.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/0/299089/19784.jpg)

Central Telefônica antiga.

Os principais métodos de comutação são: A **comutação por circuito**, a **comutação por pacote** e a **comutação por mensagem**. A comutação por pacote e a comutação por circuito são extensivamente utilizadas nos dias de hoje, entretanto, a comutação por mensagem é uma técnica antiga e pouco utilizada, sendo substituída pela comutação por pacotes, e por esse motivo, não será estudada nesse tópico. As redes comutadas por pacote ainda podem ser subdivididas em comutação por datagrama e comutação por circuitos virtuais, conforme mostrado na Figura 2. A seguir serão descritos em detalhes tais métodos de comutação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/0/6/350620/27373.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/0/6/350620/27373.png)

Taxonomia das redes comutadas

Fonte: Forouzan, A. B, 2007

### Comutação por circuito

Na comutação por circuito, antes de enviar qualquer tipo de informação há a necessidade de se estabelecer uma ligação ponto-a-ponto entre os dispositivos terminais que desejam se comunicar. Neste processo, é estabelecido um caminho físico entre origem e destino por meio de comutadores localizados nas centrais telefônicas, como mostrado na Figura 3. Cada um dos comutadores (retângulos) da Figura 3 possui três linhas de entrada e três linhas de saídas. Quando uma chamada é solicita, cada um dos comutadores estabelece a ligação interna (linha pontilhada) com o meio de transmissão (linha sólida). Cabe acrescentar que o meio físico (óptico, metálico ou micro-ondas) será utilizado de forma compartilhada por meio várias ligações simultâneas por meio de processos de multiplexação (Ex: TDM e FDM). Sem a utilização da multiplexação, o meio transmissão suportaria apenas uma ligação entre origem e destino (TANENBAUM, A. S).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/6/240634/9222.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/6/240634/9222.jpg)

Figura 3 - Comutação por circuito.

**Fases da comutação por circuito**

1. Estabelecimento do circuito: Nesta etapa há uma reserva de banda antes que os terminais comecem a transmissão. Essa reserva de banda pode ser feita por processos de multiplexação.
2. Transferência de dados: Com o estabelecimento do circuito, os dados podem ser enviados. No caso de ligações telefônicas, isso significa que os usuários podem se comunicar.
3. Encerramento do circuito: Ao fim da comunicação entre os terminais, a largura de banda é liberada para que possa ser utilizada por outra ligação.

**Vantagens e desvantagens da comutação por circuito**

As vantagens e desvantagens da comutação por circuito são resumidas na Tabela 1. A principal vantagem da comutação por circuito está associada com a garantia de recursos, uma vez estabelecido o circuito não existe a disputa da largura de banda por outros usuários. Entretanto, essa característica pode levar a um desperdício de largura de banda (no caso de transmissão de dados) durante períodos de inatividade do link.

|Vantagens|Desvantagens|
|---|---|
|[[Largura de banda dedica]]|Desperdício de banda em caso de link ocioso|
|[[Não há processamento nos dispositivos intermediários]]|Não há correção de erros|
|[[A disputa pelo meio de transmissão existe apenas na fase estabelecimento de conexão]]|Pode ocorrer bloqueios (linha ocupada)|

  
  

### Comutação por pacote

A comutação por pacote, diferentemente da comutação por circuito, não necessita que um circuito seja estabelecido entre origem e destino antes de iniciar a comunicação, não exigindo nenhuma configuração antecipada, fazendo com que não haja a reserva da largura de banda do link, como na comutação por circuito. Assim que o primeiro desses pacotes estiver disponível a transmissão pode ser iniciada.

Na comutação por pacote uma mensagem é dividida em pequenos datagramas com tamanho limitado chamados de pacotes. Devido a essa característica a comutação por pacote permite que cada pacote utilize caminhos diferentes até o destino. Isso permite que a comutação por pacote tenha maior tolerância a falhas caso um determinado link esteja indisponível. Caso ocorra alguma falha no link ou em algum dispositivo, o sistema se encarrega de encontrar uma nova rota. Em contrapartida, na comutação por circuito, se houver qualquer falha, a ligação precisa ser reestabelecida (TANENBAUM, A. S).. Na Tabela 2 é mostrada a comparação entre comutação por pacote e circuito.

|Item|Comutação por circuito|Comutação por pacote|
|---|---|---|
|[[Configuração de conexão]]|Obrigatória|Não necessária|
|[[Caminho físico dedicado]]|Sim|Não|
|[[cada pacote segue a mesma rota]]|Sim|Não|
|[[Os pacotes chegam em ordem]]|Sim|Não|
|[[A falha de um comutador é fatal]]|Sim|Não|
|[[Largura de banda disponível]]|Fixa|Dinâmica|
|[[Momento de possível congestionamento]]|Durante a configuração da conexão|Em todos os pacotes|
|[[Largura de banda potencialmente desperdiçada]]|Sim|Não|

  
  

Outra característica importantíssima da comutação por pacote é a possibilidade da multiplexação das aplicações. A multiplexação das aplicações ou da conversação permite que diversas aplicações sejam utilizadas simultaneamente, sem alocar o link ou o sistema para uma determinada aplicação em detrimento de outra, como pode ser notado na Figura 4. O computador “Origem” pode enviar ou receber diversas aplicações simultâneas a diferentes destinos como, por exemplo, um aluno da Uninove, envia uma solicitação de página para o site Uninove.br (carta 1), o mesmo aluno envia um E-mail para o seu colega de sala (carta 2) e também se conecta a uma rede social (carta 3).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/0/9/350920/27420.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/0/9/350920/27420.png)

Processo de comutação por pacote e multiplexação das aplicações.

**Tipos de Comutação por Pacote**

A comutação por pacote ainda pode ser subdivida em comutação por **datagrama e circuitos virtuais**. Na **comutação por circuitos virtuais** existe sempre um caminho fixo previamente estabelecido entre origem e destino, garantido a entrega e de forma ordenada dos pacotes. Frame Relay é um exemplo desse tipo de rede. A **comutação por datagram**a, cada pacote recebe um tratamento individual, contendo um número de sequência de cada pacote e o endereço do destinatário e de origem, sendo que cada pacote pode passar por caminhos diferentes, garantido dessa forma, que este tipo de comutação se adeque a modificações e falhas da rede. Este tipo de comutação é empregado, principalmente, por redes IPs (Internet Protocolo, Protocolo de Internet).