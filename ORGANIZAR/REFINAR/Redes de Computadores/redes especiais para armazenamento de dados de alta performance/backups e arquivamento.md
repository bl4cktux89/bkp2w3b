### Introdução

Com o rápido crescimento do volume de dados atualmente, surgem preocupações com a integridade dos dados, disponibilidade e muitos outros. E qual a solução para isso? Criar cópias (_**backups**_) para que seja possível uma restauração em caso de perda ou corrupção de dados. Os principais arquivos salvos geralmente são arquivos de configurações ou de aplicativos, bancos de dados, entre outros. Mas um _**backup**_ pode ter também o objetivo de guardar informações a longo prazo que não podem ser descartadas, como registros de transações, por exemplo.

Os _**backups**_ podem ser feitos em discos ou em fitas magnéticas, similar a um rolo de filme. Essa é uma boa opção para armazenar dados a longo prazo, porém por ser uma fita contínua, é mais devagar para se recuperar dados específicos

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267708/13244.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267708/13244.jpg)

O que é Backup ?

### Motivações para realização de Backup

Os principais motivos para se fazer backup incluem:

- Desastres: Casos como tornados, furacões, tempestades, ou qualquer tipo de desastre natural, ou até mesmo causas humanas, como um atentado terrorista, como ocorreu no 11 de setembro nas torres gêmeas no Estados Unidos, onde muitas empresas faliram por perder todos seus dados. Caso se faça _backup_ pode-se recuperar os dados após o desastre.
- Erros: Todos nós erramos, isso não é novidade, e já é de se esperar que erros humanos possam acontecer, então caso algum dado seja corrompido, ele pode ser recuperado caso haja um backup.
- Invasores/Funcionários mal intencionados: Caso um invasor, ou um funcionário que está descontente com a empresa, consiga acessar seu sistema e apagar tudo você precisa ter um backup para que seja possível dar continuidade aos seus negócios.
- Armazenamento a longo prazo(Arquivamento): Alguns dados precisam ser guardados por um bom tempo, e não podem se perder, como dados de compras, ou transações em um banco, ou na Nasa, onde armazenam informações sobre o universo todo, e talvez eles precisem depois para alguma experiência ou análise. Muitas dados desse tipo são salvos em dispositivos mas baratos como fitas magnéticas ou HDs, ao invés de SSDs, por exemplo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/9/9/359998/28513.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/9/9/359998/28513.png)

Motivações para Backup

### Granularidade de backup

Diz respeito às divisões de algum tamanho de sistema, por exemplo, um quadrado dividido em 2 partes têm uma granularidade menor que um dividido em 8 partes. Na computação pode se tratar de divisões lógicas ou físicas, algumas vezes trata de sistemas ou a descrição deles, mais como uma representação. Para nós, o que importa agora é a granularidade de backup, que é a quantia de tempo estipulada para realizar backup dos dados. A seguir veremos as mais usadas:

- Completo: Faz uma cópia completa de todos os dados, é usado mas ocasionalmente, já que gasta mais espaço de armazenamento e tempo.
- Incremental: Faz uma cópia apenas dos dados que foram modificados desde o último backup. Dessa forma ele economiza espaço e tempo.
- Sintético: Mescla um backup completo com um backup incremental, dessa maneira se cria um novo backup completo sem interromper a produção.
- Incremental para sempre: Cria-se apenas um backup completo inicialmente, e depois realiza apenas backups incrementais, o diferencial desse tipo de granularidade de backup é que ele automaticamente já combina os dois. Dessa maneira, não é preciso mais fazer backups completos novamente.
- O RPO (Recovery Point Objective) e RTO (Recovery Time Objective) são os principais pontos a escolher um método. RPO é o intervalo de tempo entre os backups, e RTO é o tempo preciso para se fazer um backup.

Destaca-se que muitas outras soluções e misturas de técnicas, como as apresentadas podem ser implementadas em conjunto.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267712/13246.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267712/13246.jpg)

Restauração a partir do backup incremental.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267713/13248.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267713/13248.jpg)

Restauração a partir do backup cumulativo.

### Principais métodos

Agora que já sabemos escolher o intervalo de tempo entre os backups, precisamos escolher agora qual método usaremos, às principais abordagens que os backups são baseados são:

- Agente: É instalado um agente(programa) no sistema computacional que se deseja realizar o backup. O agente envia os dados para os dispositivos de armazenamento.
- Imagem: Cria-se uma imagem do sistema completo, como se fosse uma fotografia do estado atual da máquina(snapshot), é um recurso muito usado em máquinas virtuais.
- NDMP: É um protocolo aberto para realização de backups voltado para NAS(Armazenamento conectado pela rede), a maior vantagem desse método é poder realizar o backup independente da plataforma ou sistema operacional. Funciona como cliente-servidor, onde o cliente envia os dados a serem armazenados pelo servidor NAS. Esse backup pode ser realizado local ou remotamente.
- Direto: Realiza backup direto do sistema de armazenamento principal, dessa forma apenas os arquivos modificado são copiados.

### Desduplicação

Imagine uma empresa como o google, que armazena milhões, talvez bilhões de informações por dia, se eles não se preocuparem com a duplicidade, muito provavelmente esgotariam rapidamente seus recursos de armazenamento. Existem técnicas para evitar que dados repetidos sejam armazenados, backups do tipo incremental é uma solução para isso, basicamente, o processo de desduplicação envolve fragmentar dados, identificar esses fragmentos, e eliminar os fragmentos redundantes.

A desduplicação pode ocorrer em nível de arquivo, onde buscam apenas arquivos iguais. E em nível de subarquivos, que buscam partes iguais em documentos diferentes. Isso seria a granularidade na qual a desduplicação ocorre. A desduplicação pode ocorrer em alguns lugares, os principais são:

- Origem: Os dados são desduplicados no cliente, ou seja, acontece no sistema computacional, antes de enviar para o armazenamento.
- Destino: Os dados são desduplicados no servidor, ou seja, acontece no sistema de armazenamento, ao contrário da abordagem de origem.
- Global: Faz uso de um hash global, hashes são resultados de funções criptográficas, que transformam algo em um código(teoricamente indecifrável). Essas hashes de cada arquivo são armazenadas e comparadas com às hashes dos arquivos que vão ser armazenados, caso ele já exista, o arquivo é ignorado. A taxa de desduplicação desse método é muito alta.
- Primário: Remove dados duplicados no armazenamento primário, isso é feito segmentando os blocos de dados e atribuindo hashes a eles, dessa forma é possível verificar se tiverem dados repetidos, já que é o único jeito de um hash se repetir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267720/13249.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267720/13249.jpg)

Arquitetura do backup.

### Backup na nuvem

Soluções físicas de backup podem ser caras e trabalhosas. Por isso os backups em nuvens têm se tornado uma tendência, uma vez que você usufrui da infraestrutura da nuvem no seu cotidiano. Isso sem contar pelo ponto de vista de segurança, se acontecer algo com seu Data Center, a capacidade de recuperação de desastres é maior.

Atualmente o backup em nuvem têm sido disponibilizado como um serviço, BaaS(Backup as a Service), e vai bem além de apenas servidores, dispositivos móveis, como celulares e tablets também usam backup em nuvem, um exemplo disso é a agenda de telefone do google para sistemas Android, na qual nos permite salvar os contatos na nuvem caso perca o celular seus contatos ainda estarão lá.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268581/13253.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268581/13253.jpg)

Métodos para fazer backup.

### Conclusão

Como podemos ver, backup é algo essencial não só na vida de um administrador de sistemas, mas para todos que têm dados que valem a pena ser guardados. Sem backup você pode ter prejuízos astronômicos, indisponibilidades, e muitos outros problemas.

Lembra quando você está fazendo um trabalho no computador e acaba a luz antes de salvar? Imagine isso com as informações todas de sua empresa, dá para imaginar o dano. Por isso lembre-se sempre de fazer backup e escolher a melhor abordagem, tanto para o backup quanto para a desduplicação de dados, como foi visto nessa aula. o processo de backup e arquivamento se baseiam basicamente em escolher uma granularidade correta, um método para a realização do mesmo. E opcionalmente, porém mais indicado, por nuvem.