[![](https://ampli-images.s3.amazonaws.com/production/dee93324-df9d-402f-a832-f9b05a26c2f3/original)](https://ampli-images.s3.amazonaws.com/production/dee93324-df9d-402f-a832-f9b05a26c2f3/original)

Para ver se o Docker foi instalado corretamente, devemos iniciar o serviço do Docker e verificar se ele está em execução. Podemos fazer isso com os seguintes comandos:

`**sudo service docker start**`

`**service docker status**`

O comando sudo utiliza a permissão de usuário administrador para execução do restante da linha, e as instruções **service docker start** iniciam o serviço Docker que foi instalado anteriormente.

Após a inicialização do Docker, utilizamos o comando service docker status que mostra o status do serviço, ou seja, se ele está em execução ou parado.

Caso ocorra algum erro ao iniciar e testar o Docker, você deve executar os dois comandos seguintes e tentar novamente:

`**sudo apt-get update**`

`**sudo apt-get upgrade**`

Esses comandos utilizam a permissão de usuário administrador através do sudo e, além disso, executam uma atualização de pacotes essenciais para o bom funcionamento do sistema operacional, assim como o bom funcionamento dos serviços que rodam através dele, como o Docker.

Agora que instalamos e verificamos seu funcionamento, o sistema está apto a receber as especificidades que queremos criar. Para isso, é possível usar o Docker Swarm. Essa ferramenta é nativa e permite a criação de clusters de Docker. Nesse cenário, é possível agrupar vários hosts em um mesmo pool de recursos, o que facilita o _deploy_ de contêineres (DIEDRICH, 2018). Esse framework é integrado ao Docker Engine a partir da versão 1.12.0, com o chamado “swarm mode”.

______

**⭐****Dica**

Você pode consultar o site, a documentação e todos os repositórios oficiais do Docker no Portal Docker, (DOCKER, [s.d.]).

Uma alternativa à instalação do Docker é o portal _Play With Docker_, plataforma pela qual é possível testar o Docker utilizando seus comandos diretamente via navegador, mediante um cadastro (PLAY WITH DOCKER, [s.d.]).

______

**📝****Exemplificando**

Após a criação do login na plataforma, teremos acesso a uma interface para criação de instâncias como clusters e nós.

Através do botão _Add new instance_, podemos criar nós para o nosso cluster e, então, é possível entrar com comandos na plataforma. Vamos conhecer um dos principais comandos para depois interagirmos com a plataforma. A figura a seguir exibe a interface após a criação de um nó:

[![](https://ampli-images.s3.amazonaws.com/production/4eba96b1-f1fb-454d-a04a-2a538ecd9220/original)](https://ampli-images.s3.amazonaws.com/production/4eba96b1-f1fb-454d-a04a-2a538ecd9220/original)

Plataforma Play With Docker. Fonte: captura de tela elaborada pelo autor.

______

Através dos comandos listados abaixo podemos simular algumas características de sistemas distribuídos com Docker, como criação de nós dos tipos mestre (manager) e escravo (worker) dentro do nosso cluster, gerenciamento de contêiner, réplica de serviços etc.