[![](https://ampli-images.s3.amazonaws.com/production/3824695d-d5fb-4dee-bbe0-0df95aac1705/original)](https://ampli-images.s3.amazonaws.com/production/3824695d-d5fb-4dee-bbe0-0df95aac1705/original)

Agora vamos ver um dos comandos que são executados dentro dos nós escravos (_worker_) do ambiente Docker. O comando a seguir pode ser utilizado para adicionar um _worker_ ao nosso cluster (figura abaixo). Para isso, devemos acessar o nó escravo que queremos adicionar a um cluster e executar o comando a seguir, passando o _token_ de segurança e o IP do nó mestre (_manager_) seguido por porta, conforme a sintaxe representada no comando:

`**docker swarm join --token**`

[![](https://ampli-images.s3.amazonaws.com/production/960c0af4-a7d3-4d42-a48f-d01a0c6b1e73/original)](https://ampli-images.s3.amazonaws.com/production/960c0af4-a7d3-4d42-a48f-d01a0c6b1e73/original)

Plataforma Play With Docker. Fonte: captura de tela elaborada pelo autor.

### **Comando executado dentro de cada um dos nós (Managers e Workers)**

Agora vamos ver um dos comandos executados dentro dos nós tanto _worker_, quanto _managers_ de nosso ambiente Docker. Quando executamos o comando Docker system prune com o parâmetro all dentro de um nó, ele será responsável por apagar/deletar tudo o que foi feito dentro do mesmo. Observamos a seguir sua utilização:

`**docker system prune --all**`

Agora que já conhecemos alguns comandos, vamos através da plataforma _Play With Docker_ orquestrar um servidor web Apache em um cluster simples. Primeiramente, você deve estar logado na plataforma de _playground_ do Docker, conforme orientações já apresentadas anteriormente. Uma vez que obteve acesso à plataforma, você deverá:

1. Criar um cluster com 3 nós, que serão suficientes para analisarmos nosso cluster sem comprometer a usabilidade da plataforma de testes do Docker. Sendo assim, você deve adicionar 3 nós, que farão parte do cluster, através do botão _Add new instance_.
2. No nó que você deseja que seja o mestre, digite o seguinte comando:`**docker swarm init --advertise-addr**`Este comando define o nó como manager do cluster. Repare que, ao executá-lo, é apresentada uma saída com a mensagem: “Para adicionar um _worker_ ao _swarm_, execute o seguinte comando”, conforme pode ser visto (em inglês) na próxima figura. Sendo assim, é necessário copiar a saída apresentada a você (que vai ser diferente da destacada em amarelo na figura abaixo), pois esse comando deverá ser executado em cada um dos demais nós do cluster, adicionando-os como _workers_ desse cluster.

[![](https://ampli-images.s3.amazonaws.com/production/6feb4fcf-620f-4923-8ae8-10b207f174b8/original)](https://ampli-images.s3.amazonaws.com/production/6feb4fcf-620f-4923-8ae8-10b207f174b8/original)

Saída do comando docker swarm init. Fonte: captura de tela elaborada pelo autor.

1. Agora que os nós estão criados e seus papéis definidos, para criar o serviço que estará rodando (de maneira distribuída, replicada) do servidor web Apache, digite o seguinte comando no nó mestre:

`**docker service create --name WEB --publish 80:80 --replicas=5 httpd**`

Esse comando cria 5 instâncias de um servidor web Apache, que responderá na porta mapeada (80, nesse caso) e, para facilitar sua monitoração, demos um nome “amigável” a este serviço: WEB.

1. Para saber em quais nós as 5 réplicas desse serviço estão sendo executadas, digite o seguinte comando:

`**docker service ps WEB**`

No caso da figura abaixo, podemos ver que 2 instâncias estão rodando no nó 1, e as outras 3 estão rodando no nó 2.

[![](https://ampli-images.s3.amazonaws.com/production/9e6514ee-6e83-449b-820b-a9f255edfcdc/original)](https://ampli-images.s3.amazonaws.com/production/9e6514ee-6e83-449b-820b-a9f255edfcdc/original)

Porta mapeada aparece como um hyperlink. Fonte: captura de tela elaborada pelo autor.

1. Por fim, precisamos acessar a página de boas-vindas desse servidor Apache através do(s) endereço(s) IPv4 de cada nó em que esse serviço web estiver rodando. Reparou que, ao criar o serviço, a porta que você mapeou aparece na parte superior, como um hyperlink? Caso não tenha percebido, veja a porta 80, destacada em vermelho na figura 24. Para acessar a página de boas-vindas, basta clicar nessa porta, em cada um dos nós onde esse serviço está rodando (no caso, nós 1 e 2 do cluster), para vermos a famosa mensagem “_It works!_” do Apache.

[![](https://ampli-images.s3.amazonaws.com/production/a5e62ca8-d1ab-4581-a489-3c73290560f8/original)](https://ampli-images.s3.amazonaws.com/production/a5e62ca8-d1ab-4581-a489-3c73290560f8/original)

Porta mapeada aparece como um hyperlink. Fonte: captura de tela elaborada pelo autor.

Esta sequência de comandos que utilizamos para orquestrar um servidor web Apache em 3 nós é a configuração utilizada em sistemas distribuídos, para que os acessos a um website sejam balanceados e, caso ocorra algum problema em um dos nós que mantêm a aplicação, o outro nó assume a execução.

______

**💭Reflita**

Parou para pensar em quantas aplicações esses conceitos podem ser aplicados? E quantas melhorias as implantações desses conceitos podem trazer a um sistema web?