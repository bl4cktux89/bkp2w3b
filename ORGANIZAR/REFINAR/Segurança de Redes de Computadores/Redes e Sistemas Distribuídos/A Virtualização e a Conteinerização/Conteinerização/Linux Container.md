[![](https://ampli-images.s3.amazonaws.com/production/88d8b790-16bd-402a-a983-eff933082783/original)](https://ampli-images.s3.amazonaws.com/production/88d8b790-16bd-402a-a983-eff933082783/original)

Existem implementações que podem ser consideradas contêineres de sistema, por exemplo, os Linux. Essas tecnologias têm um comportamento muito parecido ao de uma máquina virtual, mas, na verdade, são equivalentes a novas instâncias do sistema utilizando todas as técnicas disponíveis para isso. Os contêineres Linux funcionam compartilhando o kernel da máquina real onde estão em funcionamento. Uma limitação encontrada nos contêineres é que, quando estão compartilhando o kernel da máquina física ou até mesmo virtual em que estão hospedados e em execução, tratam-se de contêineres Linux rodando em máquinas Linux com o mesmo kernel do host, ou seja, mesmo que você substitua todas as bibliotecas e frameworks utilizados pelo seu contêiner, o kernel será sempre o mesmo do host que o hospeda.

Segundo Linux Container (2018), o projeto Linux container é o guarda-chuva por trás do Linux Containers, que possuem as gerações LXC, LXD e LXCFS. O LXC é uma interface de espaço de usuário para os recursos de contenção de kernel do Linux. Por meio de uma API poderosa e ferramentas simples, permite que usuários do Linux criem e gerenciem facilmente contêineres de sistema ou aplicativo. O LXD é um gerenciador de contêineres de próxima geração, que oferece uma experiência de usuário semelhante às máquinas virtuais, mas usando contêineres do Linux. Já o LXCFS é um sistema de arquivos simples do userspace projetado para contornar algumas limitações atuais do kernel do Linux.

______

**📝****Exemplificando**

Podemos até mesmo testar um ambiente com contêineres Linux pelo Portal _Linux Containers_ (LINUX CONTAINER, [s.d.]). Esse portal disponibiliza toda a documentação com comandos utilizados no LXC e no LXD. Conforme mencionado, podemos praticar alguns comandos e testar ambos os ambientes através do menu “_try it online_”, como podemos observar na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/d64ca7a3-86cc-4a3a-8891-dc906ef9c7d3/original)](https://ampli-images.s3.amazonaws.com/production/d64ca7a3-86cc-4a3a-8891-dc906ef9c7d3/original)

Área de treinamento do portal Linux Containers. Fonte: captura de tela do portal Linux Containers.

Dentro da opção de treinamentos, é possível usar o “_Terminal_”, disponível para executar alguns comandos e observar seu comportamento. Utilizamos o comando abaixo para criar o contêiner através da implementação Linux Containers:

`**lxc launch ubuntu MeuPrimeiroConteiner**`

Pode-se observar o contêiner com o nome “_MeuPrimeiroConteiner_” sendo criado no terminal e dando o retorno conforme é mostrado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/5f70732b-2400-4a47-9cc1-5b93e2b018d5/original)](https://ampli-images.s3.amazonaws.com/production/5f70732b-2400-4a47-9cc1-5b93e2b018d5/original)

Criando um contêiner por meio do portal Linux Containers. Fonte: captura de tela do portal Linux Containers.

Feito isso, é possível consultar a lista de contêineres criados no terminal utilizando o comando abaixo:

`**lxc list**`

Pode-se observar na figura a seguir que o contêiner criado anteriormente já aparece como resultado em nossa listagem. Além disso, informações como o status da máquina e os números de seus respectivos IPV4 e IPV6 também aparecem, como podemos ver a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/c3b348f2-d7f8-442d-8d32-939e53826067/original)](https://ampli-images.s3.amazonaws.com/production/c3b348f2-d7f8-442d-8d32-939e53826067/original)

Listando os contêineres criados através do portal Linux Containers. Fonte: captura de tela do portal Linux Containers.

É possível executar comandos dentro de um contêiner utilizando o comando abaixo:

`**lxc exec nomedocontainer – comando**`

Há opções de iniciar, parar e excluir contêineres usando os comandos:

`**lxc start**`

`**lxc stop**`

`**lxc delete**`

Além das informações do contêiner exibidas através da listagem que foi vista anteriormente, podemos observar uma série de informações sobre nosso contêiner como consumo de memória RAM, consumo de redes, entre outros dados. Para isso, utilizamos o comando de sintaxe a seguir:

`**lxc info nomedocontainer**`