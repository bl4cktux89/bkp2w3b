[![](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)

Nesta aula você conheceu alguns comandos Docker e aprendeu a fazer uma configuração de cluster e de nós para servidor web.

Vamos retomar a situação apresentada na introdução desta aula?

Mais um passo e a tão cobiçada vaga naquela grande empresa será sua! O coordenador está gostando de seu desempenho nos testes e diz que, caso você consiga orquestrar o servidor web Apache em um cluster simples, será contratado! Desta forma:

1. Crie um cluster com cinco réplicas do servidor web Apache utilizando o Docker Swarm.
2. Verifique em quais nós do cluster esse serviço está rodando.
3. Acesse a página de boas-vindas desse servidor Apache através do(s) endereço(s) IPv4 de cada nó onde esse serviço web estiver rodando.

Para resolver esse desafio, primeiramente você deve estar logado na plataforma de playground do Docker, conforme orientações já apresentadas anteriormente. Uma vez que obteve acesso à plataforma, você deverá seguir os passos abaixo:

1. Como não foi especificada a quantidade de nós do cluster, crie o mesmo com 3 nós, que serão suficientes para analisar o cluster sem comprometer a usabilidade da plataforma de testes do Docker. Sendo assim, adicione 3 nós, que farão parte do cluster, através do botão _Add new instance_.
2. No nó que você deseja que seja o mestre, digite o seguinte comando:`**docker swarm init --advertise-addr**`Este comando define o nó como manager do cluster. Repare que, ao executá-lo, é apresentada uma saída com a mensagem: “Para adicionar um _worker_ ao _swarm_, execute o seguinte comando”, conforme pode ser visto (em inglês) na figura abaixo. Sendo assim, copie a saída que foi apresentada a você (que vai ser diferente da destacada em amarelo na figura abaixo), pois esse comando deverá ser executado em cada um dos demais nós do cluster, adicionando-os como _workers_ desse cluster.

[![](https://ampli-images.s3.amazonaws.com/production/a2e12112-862b-4c29-a424-c9f26b3b5907/original)](https://ampli-images.s3.amazonaws.com/production/a2e12112-862b-4c29-a424-c9f26b3b5907/original)

Saída do comando docker swarm init. Fonte: captura de tela elaborada pelo autor.

1. Agora que os nós estão criados e seus papéis definidos, para criar o serviço que estará rodando (de maneira distribuída, replicada) do servidor web Apache, digite o seguinte comando no nó mestre:

`**docker service create --name WEB --publish 80:80 --replicas=5 httpd**`

Esse comando cria 5 instâncias de um servidor web Apache, que responderá na porta mapeada (80, nesse caso) e, para facilitar sua monitoração, demos um nome “amigável” a este serviço: WEB.

1. Para saber em quais nós as 5 réplicas desse serviço estão sendo executadas, digite o seguinte comando:

`**docker service ps WEB**`

No caso da figura abaixo, podemos ver que 2 instâncias estão rodando no nó 1, e as outras 3 estão rodando no nó 2.

[![](https://ampli-images.s3.amazonaws.com/production/1cbcb84b-825e-405a-a8a5-698dab85106c/original)](https://ampli-images.s3.amazonaws.com/production/1cbcb84b-825e-405a-a8a5-698dab85106c/original)

Porta mapeada aparece como um hyperlink. Fonte: captura de tela elaborada pelo autor.

1. Por fim, precisamos acessar a página de boas-vindas desse servidor Apache através do(s) endereço(s) IPv4 de cada nó onde esse serviço web estiver rodando. Reparou que, ao criar o serviço, a porta que você mapeou aparece na parte superior, como um hyperlink? Caso não tenha percebido, veja a porta 80, destacada em vermelho na figura abaixo. Para acessar a página de boas-vindas, basta clicar nessa porta, em cada um dos nós onde esse serviço está rodando (no caso, nós 1 e 2 do cluster), para vermos a famosa mensagem “_It works!_” do Apache.

[![](https://ampli-images.s3.amazonaws.com/production/bb5103d2-13db-484d-96d0-f9d2d0cbd5a3/original)](https://ampli-images.s3.amazonaws.com/production/bb5103d2-13db-484d-96d0-f9d2d0cbd5a3/original)

Porta mapeada aparece como um hyperlink. Fonte: captura de tela elaborada pelo autor.