### Introdução

Em um ambiente de data center onde temos diversos serviços, é extremamente importante que o sistema possua alta disponibilidade. Por isso usa-se a replicação como um artefato, de modo que os serviços estejam sempre disponíveis, mesmo que algum dispositivo ou sistema apresente problemas. O objetivo é criar algo que seja confiável, que os usuários não percebam quando houver falhas, e não perder informações e transações de comunicação de dados.

A replicação local se baseia em criar uma cópia do sistema de algum servidor que está em operação dentro do Data Center. Funcionando geralmente como um balanceamento de carga, onde dois ou mais servidores dividem a carga de trabalho, e caso um apresente falhas, os outros continuam dividindo a carga remanescente, de modo que, caso um servidor precise de realizar alguma manutenção preventiva de hardware, substituição de placas, atualização de software, ou até mesmo apresente problemas corretivos, seus serviços continuem disponíveis aos usuários.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/2/2/2/2922215/43256.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/2/2/2/2922215/43256.png)

### Tipos de replicação local

Essa replicação pode ser feita tanto a nível de rede, armazenamento, ou sistema. Para se criar uma cópia temos algumas possibilidades, para redes, os dispositivos de grande porte como a cisco, oferecem esse tipo de serviços, eles envolvem balanceamento de carga, e muitos outros recursos. Nosso foco aqui será para sistemas computacionais e de armazenamento temos as seguintes opções:

- Imagem do sistema de arquivos: Cria-se um ponto de recuperação, chamado de _snapshot_ (imagem) de FS (_File System_), é baseado em um sistema em um momento específico, conhecido como point-in-time, esses sistemas de arquivos, ou FS(_File System_), é uma cópia idêntica do principal, que continuará se atualizando. Para fazer isso é usado o bitmap, que adivinha o que ele faz? Mapeia os bits! Mapeando os bits, ele consegue saber onde houve uma mudança, e sempre que algo foi escrito ele cria uma cópia, esse princípio se chama princípio de cópia na primeira gravação, ou CoFW(_Copy on First Write_). E por último , temos o _blockmap_, que indica o endereço onde se encontram os dados da imagem que o sistema de arquivos deve ler.
- Imagem de máquina virtual: Cria-se uma imagem similar a de arquivos, porém em uma máquina virtual (VM), e por envolver um sistema computacional completo e não apenas um dispositivo de armazenamento, também é armazenado informações sobre o estado da máquina(ligado/desligado), discos, memórias, interfaces, etc… Toda essa replicação é criada pela pelo _hypervisor_.
- Clone de VM: A clonagem de máquinas virtuais é feita com o objetivo de criar cópias com configurações idênticas, mas com outros endereços MAC, que é o endereço físico de cada dispositivo de rede), isso facilita a implementação de várias máquinas com a mesma configuração e serviços, sem ter que configurar um por um. Temos dois tipos de clones, os Complexos, que criam uma cópia independente da VM, e não têm nenhuma ligação posterior a gravação e não compartilha nada com a mesma. Enquanto o clone vinculado cria uma cópia a partir de uma imagem(_snapshot_) da máquina virtual e pode ser atualizado caso algo mude na imagem.
- Replicação de Virtual Machine (VM): Nesse modelo os dados são enviados por um agente (programa) instalado no sistema, que envia os dados de um sistema para outro.

Um snapshot de VM preserva o estado e os dados de uma VM em um PIT específico ou seja em um point-in-time (PIT) ou contínuas. Isso abrange o estado de alimentação da VM (por exemplo, ligada, desligada ou suspensa).

Os dados incluem todos os arquivos que compõem a VM. Isso abrange discos, memória e outros dispositivos, como placas de interface de rede virtual.

O snapshot dessa VM é útil para restaurar rapidamente a VM. Por exemplo, um administrador pode criar um snapshot de uma VM e fazer alterações, como aplicar patches e upgrades de software à VM. Se algo der errado, o administrador poderá simplesmente restaurar a VM ao estado anterior usando o snapshot da VM.

O hipervisor oferece a opção de criar e gerenciar vários snapshots. Criar vários snapshots oferece vários pontos de restauração a uma VM. Embora mais snapshots aumentem a resiliência da infraestrutura, é importante considerar o espaço de armazenamento que eles consomem.

Quando um snapshot é criado para uma VM, um disco virtual secundário (arquivo de disco delta) é criado a partir da imagem de base ou do disco virtual principal. O mecanismo do snapshot impede que o sistema operacional guest faça gravações na imagem de base ou no disco virtual principal. Em vez disso, ele direciona todas as gravações ao arquivo de disco delta. Snapshots sucessivos geram um novo disco virtual secundário a partir do último disco virtual principal na cadeia.

Os snapshots retêm apenas blocks alterados. Considere um exemplo no qual três snapshots de uma VM são criados, como mostrado na imagem abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/6/6/0/2966035/43258.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/6/6/0/2966035/43258.png)

Fonte: EMC Corporation.ISM (2015)

Neste exemplo, o disco virtual secundário 1 armazena todas as alterações feitas na VM principal depois que o snapshot 1 foi criado. De modo semelhante, o disco virtual secundário 2 e o disco virtual secundário 3 armazenam todas as alterações feitas após a criação do snapshot 2 e do snapshot 3 respectivamente.

Quando o snapshot 3 é confirmado para a VM, os dados nos arquivos dos discos virtuais secundários 1 e 2 são confirmados antes da confirmação dos dados do disco virtual secundário 3 no arquivo de disco virtual principal.

Depois da confirmação dos dados, os discos virtuais secundários 1, 2 e 3 são excluídos. No entanto, durante a reversão para o snapshot 1 (PIT), o arquivo de disco secundário 1 é retido e os snapshots 2 e 3 são descartados.

Às vezes, pode ser necessário reter um snapshot por um período mais longo, mas é importante observar que snapshots maiores demoram mais para serem confirmados e podem afetar o desempenho. A origem (VM principal) deve estar íntegra a fim de usar o snapshot para reversão.

### Armazenamento

A replicação é executada dentro do sistema de armazenamento. Geralmente, a replicação local possibilita executar a recuperação operacional em caso de perda de dados e também dá suporte a outras operações de negócios, como _**backup**_. A replicação local com base no sistema de armazenamento pode ser implementada como replicação de volume completo (_**clone**_) e replicação virtual com base no indicador (_**snapshot**_).

Replicação de volume completo: Permite a criação de um clone completo de um volume de armazenamento, é feita uma sincronização entre a origem e a réplica, às alterações podem ser configuradas para acontecer com certa frequência predefinida. Dessa maneira permite que depois seja feito apenas a atualização do que for alterado, e o clone sempre terá o mesmo tamanho do original.

Replicação baseado em indicador: A replicação por identificador se diferencia da completa por não copiar todos os dados, ele cria uma imagem(_**snapshot**_) que é uma representação virtual do sistema por meio de referências lógicas, dessa maneira nenhum dado é realmente copiado nessa replicação, mas com a imagem criada é possível restaurar dados. E essa imagem ocupa menos espaço do que o original.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/2/4/5/2924517/43257.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/2/4/5/2924517/43257.png)

Fonte: EMC Corporation.ISM (2015)

### Conclusão

Com replicação é possível criar algo que funcione de maneira transparente para seus usuários, e com melhor desempenho. O objetivo disso é diminuir ao máximo os pontos de falhas únicas, que são partes do sistema que se apresentarem problemas poderão parar os serviços.

É importante criar replicações em todos os níveis do data center, dessa maneira se diminui ou anula os pontos de falha única, que se falharem, seu sistema cai. A solução adequada vai depender do tipo de dados e infraestrutura que estiver usando.

Muitas pessoas ficam confusas entre qual a diferença entre backup e replicação, mas é simples. Os dois se tratam de fazer cópias, porém o backup é para recuperação de dados em casos de falhas ou desastres, enquanto a replicação têm como objetivo primário fornecer disponibilidade, e não armazenar dados. Podem ser usadas juntas, todas para evitar pontos de falhas únicas.