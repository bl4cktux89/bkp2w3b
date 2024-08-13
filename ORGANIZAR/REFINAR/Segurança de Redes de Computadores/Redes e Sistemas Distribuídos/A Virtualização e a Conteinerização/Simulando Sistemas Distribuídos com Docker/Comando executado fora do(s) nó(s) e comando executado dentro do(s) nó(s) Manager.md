[![](https://ampli-images.s3.amazonaws.com/production/f5cfe713-f05c-4af4-83d2-fdca9252ce1b/original)](https://ampli-images.s3.amazonaws.com/production/f5cfe713-f05c-4af4-83d2-fdca9252ce1b/original)

Agora vamos ver alguns comandos que são executados fora dos nós do ambiente Docker. Um dos mais importantes é o de criação de um novo manager para o cluster. Através do comando, criamos um manager chamado de mestre:

`**docker-machine create --driver virtualbox mestrext**`

O começo desse comando significa que estamos criando uma nova máquina através do Docker. Utilizaremos **docker-machine create** como driver no VirtualBox e daremos o nome de mestre para nossa máquina.

Agora, vamos fazer a criação de uma nova máquina: o comando segue o mesmo padrão do anterior, mas desta vez vamos chamar a máquina de “escravo1”. Ela será um _worker_ para o cluster, conforme comando abaixo:

`**docker-machine create --driver virtualbox escravo1**`

Podemos verificar o IP de qualquer uma das máquinas de nosso cluster utilizando o comando **docker-machine ip** e, a seguir, consultamos o IP de nossa máquina chamada “mestre”:

`**docker-machine ip mestre**`

Um dos comandos Linux mais populares utilizados para acesso de máquinas/servidores é o ssh, que significa “Secure Shell”, em que fazemos um acesso ou uma conexão através desse protocolo de rede criptográfica, que aplica mais segurança aos serviços de redes. Na utilização do Docker o mesmo comando é usado com o objetivo de acessar os nós criados que, em nosso ambiente, possuem os nomes “mestre” e “escravo1”.

`**docker-machine ssh mestre**`

`**docker-machine ssh escravo1**`

É possível verificar os nós (nodes) criados através do comando “ls”. Podemos criar um escravo para o cluster com hardware diferente do padrão. Também pode-se ver no comando a seguir que a máquina chamada “escravo5” que definimos a memória com o valor de 512 MB através da instrução **virtualbox-memory** “512” e um disco rígido de 5 GB através da instrução **virtualbox-disk-size “5000”****:**

`**docker-machine create --virtualbox-memory "512" --virtualbox-disk-size "5000" --driver virtualbox escravo5**`

### **Comando executado dentro do(s) nó(s) Manager**

Vamos ver os alguns comandos executados dentro do manager de nosso ambiente Docker. O comando a seguir pode ser utilizado para iniciar o cluster através do framework _Swarm_, de gerenciamento de contêineres.

`**docker swarm init --advertise-addr**`

Podemos consultar os nós que fazem parte do cluster utilizando o comando node ls: docker node ls

Às vezes precisamos verificar informações sobre um nó específico. Para isso, utilizamos o comando Docker inspect. O exemplo a seguir contém informações sobre o nó chamado “escravo1”:

`**docker inspect escravo1**`

A seguir, é possível observar um exemplo de criação de um novo serviço (tarefa) para o cluster. Nesse caso, criamos um serviço Web através do popular servidor web nginx, que contém 3 réplicas:

`**docker service create --name WEB --publish 85:80 --replicas=3 nginx:1.12.1**`

No parâmetro name definimos um nome para a execução do serviço, em nosso caso, WEB. Através do parâmetro **publish** definimos uma porta de execução para o Docker e uma para o servidor web Nginx, no caso, “85” e “80” e, por último, definimos que o serviço terá 3 réplicas e utilizará o Nginx na versão 1.12.1.

Agora que criamos nosso serviço de internet chamado WEB, podemos utilizar o comando ps seguido do nome do serviço para verificar suas informações. Portanto, o comando a seguir mostra informações sobre um serviço específico aqui denominado como WEB:

`**docker service ps WEB**`

É possível usar os comandos a seguir para alterar a versão das instâncias do Nginx. No primeiro comando atualizamos, através do comando update, a versão do Nginx para 1.13.5 (anteriormente estávamos com a versão 1.12.1). Após isso, utilizamos o comando ps com o parâmetro -f que significa _filter_ ou _find_, que pode ser considerado um filtro para a busca, em que usamos a palavra-chave _Running_ para descobrir qual serviço está em execução e se sua versão foi mesmo atualizada. O resultado dos comandos está ilustrado na figura a seguir.

`**docker service update --image nginx:1.13.5 WEB**`

`**docker service ps -f "desired-state=Running" WEB**`

[![](https://ampli-images.s3.amazonaws.com/production/f7d45730-1931-494a-87d6-f2289b051b47/original)](https://ampli-images.s3.amazonaws.com/production/f7d45730-1931-494a-87d6-f2289b051b47/original)

Plataforma Play With Docker. Fonte: captura de tela elaborada pelo autor.

Caso quiséssemos desfazer nossa atualização de versão das instâncias do Nginx, podemos utilizar o comando update como parâmetro rollback aplicado sobre o serviço WEB. Com isso, teremos a volta da versão das instâncias do Nginx para a versão anterior. Que pode ser consultado através do mesmo comando ps utilizado no exemplo anterior, conforme a seguir:

`**docker service update --rollback WEB**`

`**docker service ps -f "desired-state=Running" WEB**`

Caso seja necessário parar algum nó e seus serviços, podemos utilizar o comando update seguido do parâmetro **availability drain** e o nome do nó que desejamos parar, como em nosso exemplo, o nó denominado como escravo2:

`**docker node update --availability drain escravo2**`

Quando executamos esse comando, tanto o nó quanto os serviços que estão em execução serão parados.