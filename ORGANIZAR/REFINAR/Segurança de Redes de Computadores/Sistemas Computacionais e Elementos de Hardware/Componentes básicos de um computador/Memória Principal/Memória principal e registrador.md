[![](https://ampli-images.s3.amazonaws.com/production/c756cee1-bb87-4f86-b531-c47bc930fb2f/original)](https://ampli-images.s3.amazonaws.com/production/c756cee1-bb87-4f86-b531-c47bc930fb2f/original)

Para que um computador possa funcionar e o processador possa executar o processamento dos dados e instruções recebidos é necessário que ele tenha memória. Seguindo o que é proposto na arquitetura de Von Neumann, se nos computadores existisse apenas um tipo de memória, esta deveria ter a mesma velocidade da CPU, esperando por dados que estivessem sendo transferidos para processamento. Na prática, o que acontece, por exemplo, em um computador que processa um dado em 5ns (nano segundos), a memória transfere o dado em 60ns (PATTERSON, 2005).

A memória de um computador não é uma única peça isolada, existem vários tipos de memórias. Por exemplo, a memória onde é executado o processamento dos dados é de um tipo diferente da memória de armazenamento onde os dados são guardados em um computador. A velocidade dos processadores, de suas CPUs e de suas estruturas requerem que existam vários tipos de memórias, cada qual com sua função específica (FÁVERO, 2011). Estas memórias são classificadas em Memória Principal e Memória Secundária. Além destes dois tipos de memória, ainda temos a Memória Cache e os registradores da CPU (MONTEIRO, 2007).

As memórias de um computador podem variar também em sua tecnologia, sua capacidade de armazenamento, velocidade, custo, e elas são interligadas de forma estruturada, compondo um subsistema de memória. Este subsistema organiza os diversos tipos de memória hierarquicamente em ordem decrescente de acordo com a velocidade destas memórias, sendo os registradores as memórias mais rápidas e as secundárias as que apresentam as menores velocidades (FÁVERO, 2011).

[![](https://ampli-images.s3.amazonaws.com/production/1f594850-eb31-4b4e-b822-2af2d9481ef2/original)](https://ampli-images.s3.amazonaws.com/production/1f594850-eb31-4b4e-b822-2af2d9481ef2/original)

Hierarquia de memórias. Fonte: Fávero (2011); Monteiro (2007).

Para que você possa entender melhor a função da Memória Principal de um computador, é necessário também conhecer dois tipos específicos de memórias que auxiliam o gerenciamento dos dados, que são os Registradores e a Memória Cache (FÁVERO, 2011).

Outro conceito importante sobre memórias é que elas podem ser voláteis ou não voláteis. As memórias voláteis requerem energia para funcionar e armazenar dados, ou seja, só funcionam quando o computador está ligado e os dados armazenados nelas são apagados quando o computador é desligado, em geral são as memórias de processamento. As memórias não voláteis gravam os dados de forma permanente em seus dispositivos, não sendo apagadas quando se desliga o computador e seus dados podem ser lidos e recuperados quando for necessário (PATTERSON, 2005).

Temos, assim, uma classificação hierárquica das memórias de acordo com suas características, que são descritas mais claramente de acordo com a Figura abaixo, como segue:

[![](https://ampli-images.s3.amazonaws.com/production/7a545766-00da-41f1-bc2b-0c1d628ee04a/original)](https://ampli-images.s3.amazonaws.com/production/7a545766-00da-41f1-bc2b-0c1d628ee04a/original)

Quadro das características básicas dos tipos de memória. Fonte: Murdocca (2001); Fávero (2011)

**🔁 Assimile**

As memórias podem ser voláteis, que se apagam quando o computador é desligado, e não voláteis, sendo previamente gravadas e não se apagam quando se desliga o computador, o que permite que os dados gravados neste tipo de memória sejam lidos quando for necessário.

________

Uma função básica da memória do computador é armazenar dados que serão processados. O processador recebe os dados e os deposita temporariamente na memória, e os registradores são os locais de memória onde estes dados ficam armazenados para que este processamento aconteça. Os registradores vêm desta necessidade do processador de armazenar dados durante o processamento e eles estão localizados dentro da CPU (MONTEIRO, 2007).

[![](https://ampli-images.s3.amazonaws.com/production/3920ed39-4c25-49c7-893d-a98813e42e6f/original)](https://ampli-images.s3.amazonaws.com/production/3920ed39-4c25-49c7-893d-a98813e42e6f/original)

Registradores em destaque dentro da estrutura de um processador. Fonte: Arquitectura Neumann por David Strigoi.

O registrador é um tipo de memória volátil. Por estar dentro do processador, proporciona uma velocidade de transferência bastante alta e, também, pelo fato de estar dentro do processador, sua capacidade de armazenamento é baixa pelo fato de dividir espaço com as demais unidades do processador.

Como o processador é uma das peças mais caras de um computador, o custo deste tipo de memória é, por consequência, bastante caro. (TANENBAUM, 2007).