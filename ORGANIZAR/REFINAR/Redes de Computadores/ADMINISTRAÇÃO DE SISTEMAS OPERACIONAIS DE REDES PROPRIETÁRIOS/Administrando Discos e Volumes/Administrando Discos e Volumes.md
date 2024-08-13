### **Introdução**

O gerenciamento de armazenamento mudou muito nos últimos anos, assim como o modo que o Microsoft Windows Server trabalha com discos. Embora as técnicas tradicionais de gerenciamento de armazenamento referem-se a unidades físicas localizadas dentro do servidor, muitos servidores atualmente utilizam armazenamento e discos virtuais. Geralmente, quando trabalhamos com unidades fixas internas, devemos executar procedimentos de configuração de disco avançadas, tais como a criação de um conjunto de volumes ou a criação de uma matriz redundante de discos independentes (Redundant Array of Independent Disks, RAID). Nessa aula iremos entender e criar volumes e conceituar RAID.

### **Usando volumes e discos dinâmicos**

Com um conjunto de volumes, ou discos dinâmicos, podemos criar um único volume que abrange várias unidades de discos. Desse modo, os usuários podem acessar este volume como se fosse uma única unidade, independentemente de quantas unidades o volume utiliza. Um volume que está em uma única unidade é referido como um volume simples e um volume que abrange várias unidades é referido como um volume expandido. Podemos criar e gerenciar volumes da mesma maneira que criamos e gerenciamos partições, isso porque, um volume é uma seção de uma unidade que pode ser usado para armazenar dados diretamente.

### **Compreendendo Disco Básico**

O armazenamento básico utiliza tabelas de partições normais que são usadas por todas as versões do sistema operacional Windows. Um disco que é inicializado para armazenamento básico é chamado de disco básico e um disco básico pode conter partições básicas, como partições primárias e partições estendidas.

Através do gerenciamento de disco códigos é possível verificar e gerenciar volumes e partições. A Figura 1, exibe as seguintes propriedades:

- Layout: Incluem layouts simples, estendidos, espelhados, distribuídos, paridade.
- Tipo: Os volumes sempre têm o tipo dinâmico.
- Sistema de Arquivos: Exibe a partições do sistema, e cada volume pode ter um tipo de sistema de arquivos diferente, como FAT ou NTFS.
- Status: Exibe o estado da unidade, apresentando como Integro, Falha de Redundância, e assim por diante.
- Capacidade: O tamanho total de armazenamento da unidade.
- Espaço Livre: A quantidade total de espaço disponível no volume.
- % Livre: A porcentagem de espaço livre, em relação ao tamanho de armazenamento total do volume.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/1/266132/14905.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/1/266132/14905.jpg)

Figura 1: Gerenciamento de disco

Uma vantagem importante de volumes dinâmicos em relação a volumes de básicos é que eles permitem que alterações em volumes e discos sem ter que reiniciar o sistema na maioria das vezes.

Utilizando volumes, podemos fazer o seguinte:

- Atribuir letras de unidade e caminhos de unidade.
- Criar qualquer quantidade de volumes em um disco, desde que exista espaço livre.
- Criar volumes que abrangem dois ou mais discos e, se necessário, configurar a tolerância a falhas.
- Estender volumes para aumentar a capacidade dos volumes.

### **Entendendo Disco dinâmico**

Um disco dinâmico contém volumes dinâmicos e podemos realizar o seu gerenciamento, como por exemplo, criando volumes que abrangem várias unidades. Para fazer isso, devemos utilizar o espaço livre em unidades diferentes e criar o que os usuários acessam como um único volume. Os arquivos são armazenados no Disco dinâmico segmento por segmento, onde o primeiro segmento com espaço livre será usado para armazenar os arquivos. Quando o primeiro segmento enche, o segundo segmento é utilizado, e assim por diante.

Podemos criar um volume definido e utilizando o espaço livre em até 32 unidades de disco rígido. A vantagem do Disco dinâmico é que eles permitem utilizar espaço livre e criar um sistema de arquivo utilizável. A desvantagem principal é que se qualquer unidade de disco rígido no conjunto de volume falhar, o conjunto de volume não pode mais ser usado, o que significa que praticamente todos os dados do conjunto de volume é perdido.

A tabela a seguir exibe os volumes dinâmicos que estão disponíveis no Windows Server:

![[Screenshot_from_2022-03-31_01-03-37.png]]

### **Criando volumes e disco dinâmico**

Podemos formatar volumes simples com os sistemas de arquivos exFAT, FAT, FAT32 ou NTFS. Para facilitar o gerenciamento, devemos formatar volumes que abrangem vários discos com o NTFS, isso porque, podemos expandir o volume, se necessário.

Para criar volumes e conjuntos de volumes, realize os passos a seguir:

1. Em Gerenciamento de Disco, pressione o botão direito do mouse uma área não alocado e, em seguida, clique em Novo volume estendido ou conforme a necessidade e em seguida, clique em Avançar.

2. Devemos ver a página Selecionar Discos, nesse momento selecione os discos que devem fazer parte do volume e o tamanho dos segmentos de volume nesses discos.

3. Selecione um disco na lista e, em seguida, especifique o tamanho do volume no disco, a quantidade de espaço em MB. O espaço máximo disponível na caixa MB mostra a maior área de espaço livre disponível no disco.

4. Especifique se deseja atribuir uma letra de unidade ou caminho para o volume, e depois clique em Avançar

5. Especificar se o volume deve ser formatado. Clique em Avançar e, em seguida,

6. Clique em Concluir.

### **Melhorar o desempenho e tolerância a falhas com RAID**

Muitas vezes quereremos implementar maior proteção contra falhas nas unidades que mantemos os dados. Para fazer isso, podemos utilizar a tecnologia RAID e adicionar tolerância a falhas de seus sistemas de arquivos. Com a utilização de Matriz Redundante de Discos Independentes (Redundant Array of Independent Disks, RAID), aumentamos a integridade e disponibilidade de dados através da criação de cópias redundantes dos dados, além de melhorar o desempenho de seus discos. Diferentes implementações de tecnologia RAID estão disponíveis, atualmente, os níveis de RAID 0 a 5 são os definidos e cada nível de RAID oferece características diferentes. O Windows Server 2012 suporta os níveis de RAID 0, 1 e 5. Segundo a Microsoft (MICROSOFT, 2012) a Tabela 2 fornece uma visão geral dos níveis de RAID suportados.

|Nível|Descrição|Desempenho|Utilização do espaço|Redundância|Comentários|
|---|---|---|---|---|---|
|[[RAID 0]]|Conjunto dividido sem paridade ou espelhamento  <br>  <br>Os dados são escritos sequencialmente em cada disco|Alto desempenho de leitura e gravação|Todo o espaço nos discos está disponível|Uma única falha de disco resulta na perda de todos os dados|Use apenas em situações nas quais você precisa de alto desempenho e pode tolerar a perda de dados|
|[[RAID 1]]|Conjunto espelhado sem paridade ou divisão  <br>  <br>Os dados são gravados nos dois discos simultaneamente|Bom desempenho|Só pode usar a quantidade de espaço disponível no menor dos discos|Pode tolerar uma falha de apenas um disco|Usado frequentemente para volumes do sistema e de inicialização com RAID de hardware|
|[[RAID 5]]|Conjunto dividido com paridade distribuída  <br>  <br>Os dados são gravados em blocos em cada disco com paridade espalhada entre todos os discos|Bom desempenho de leitura, fraco desempenho de gravação|Usa o equivalente a um disco para paridade|Pode tolerar uma falha de apenas um disco|Normalmente usado para armazenamento de dados, quando o desempenho não é crítico, mas é importante maximizar o uso do disco|