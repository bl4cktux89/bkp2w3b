### Introdução

Os sistemas de armazenamento e compatilhamento de arquivo apresentam estrutura hierárquica, e servem para conectar não apenas servidores, mas também outros dispositivos que acessam os dados. Os sistemas de armazenamento e compartilhamento de dados, utilizam protocolos como o SMB ou NFS, e por funcionar na camada de aplicação, ele consomem mais tempo para a transmissão de dados entre um cliente e um servidor. Outros protocolos como FTP e DFS podem ser usados também, conforme apresentaremos nesse tópico.

**EXEMPLOS DE PROTOCOLOS CLIENTE-SERVIDOR: SMB OU NFS**

O CIFS é um protocolo de aplicativo client-servidor que permite que programas client façam solicitações de arquivos e de serviços nos computadores remotos por TCP/IP. Ele é uma variação pública, ou aberta, do protocolo de SMB (Server Message Block).

Exemplo de consulta ao _**File System:**_

\\servidor\compartilhamento ou \\nomedoservidor.domínio.sufixo\compartilhamento

NFS (Network File System)

CIFS (Common Internet File System)

### NAS(_Network-Attached Storage_)

O _**Network-Attached Storage**_ é um dispositivo responsável pelo armazenamento de dados de alta densidade e desempenho, que funciona através da pilha de protocolos TCP/IP, oferecendo conectividade ao armazenamento. Fazendo uso de seu próprio sistema operacional e recursos de hardware. Seu principal objetivo é funcionar como um _**file serving,**_ ou seja um servidor de armazenagem de arquivos, que é capaz de lidar com grandes cargas de trabalho, permitindo que os clientes possam compartilhar seus arquivos através da rede IP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/5/5/2825536/41822.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/5/5/2825536/41822.jpg)

Fonte:

Os seus principais componentes são a controladora, que seria um computador com acesso aos storages, que cria LUNs, gerencia as RAIDs, etc. E o armazenamento, claro. O NAS pode seguir dois tipos de arquitetura, a scale-out e a scale-up.

**Scale-up:** Nos permite dimensionar o tamanho e capacidade do storage. Dentro dessa arquitetura, temos dois modelos de implementação.

1)**NAS integrado:** Possui um ou mais NAS heads e storage em um único sistema.

2)**NAS gateway:** Possui um ou mais NAS heads e storage externo ou gerenciado de forma separada.

**Scale-out:** Cria-se um cluster com os nós do NAS, cada nó pode ser ou o NAS head, ou armazenamento, ou os dois. Isso torna nosso sistema muito mais escalável e flexível, pois para adicionar mais armazenamento é só criar outro nó no cluster.

### Métodos de acesso

Para acessar o NAS, como dito antes, temos alguns protocolos, a seguir, veremos alguns deles com mais detalhes.

- CIFS(Common Internet File System): Utiliza uma variação do protocolo SMB(server message block), funciona sobre a pilha TCP/IP.
- NFS(Network file System): Protocolo que trabalha na camada de transporte, algumas versões funcionam por TCP e outras por UDP, Porém sua criação para seu uso original no linux foi baseada em UDP. Faz o uso de chamadas RPC para se comunicar.
- HDFS(Hadoop Distributed File System): Sistema de arquivos distribuídos da Apache, que permite scale-out, criando nós no cluster, toda comunicação ocorre por meio da pilha TCP/IP. Um cluster HDFS possui um NameNode, que seria o servidor mestre, e ele mantém um mapa de todo o sistema. E temos os DataNodes, que são os escravos que realizam as operações de E/S

A principal diferença nesse caso do _**scale-up**_ e scale-out, são o quanto elas podem se expandir, e a maneira de buscar/gravar dados, no _**scale-out**_ a solicitação é enviada diretamente ao cluster, onde os outros dispositivos também têm acesso, diferente do _**scale-up**_, onde a solicitação têm de ser enviada diretamente ao NAS _**head**_.

O NAS permite a virtualização de aplicativos, o que é ótimo, já que dessa forma não existe mais a dependência de desenvolver apenas onde estão seus arquivos, por exemplo. Dessa maneira se usa-se o caminho lógico em vez de usar o físico.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267295/11867.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267295/11867.jpg)

Sistema comum de arquivo Internet.

O NAS pode realizar um técnica chamada de Tiering, que é categorizar os dados. Como no armazenamento em block, ele podem prover as informações entre os níveis.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/9/4/239477/6128.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/9/4/239477/6128.png)

Protocolo FTP

### Resumo

Como vimos, o NAS é uma ótima alternativa para quem busca criar um storage sem ter que implementar soluções específicas de hardware, já que tudo é administrado por protocolos de níveis mais altos. Vale sempre lembrar sobre as arquiteturas de escalonamento antes de construir sua rede de armazenamento, pois deve-se pensar como vai ser se um dia tiver que ampliar sua capacidade. A flexibilidade é um ponto chave em redes NAS.