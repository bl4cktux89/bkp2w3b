[![](https://ampli-images.s3.amazonaws.com/production/cac5c23d-f21b-43aa-82cc-273712d4b3ae/original)](https://ampli-images.s3.amazonaws.com/production/cac5c23d-f21b-43aa-82cc-273712d4b3ae/original)

O Docker é uma famosa plataforma genérica de conteinerização. Conforme já estudamos, o conceito de conteinerização é parecido com virtualização, porém é considerado “mais leve”. Contêineres são muito populares atualmente devido à facilidade e à flexibilidade que advêm de seu uso. Portanto, agora chegou a hora de colocar a mão na massa e aprender a utilizar essa famosa ferramenta.

### **Instalação do Docker**

Vamos fazer a instalação do Docker em uma das distribuições populares GNU/Linux, o sistema operacional Ubuntu, cuja versão utilizada foi a 14.04.5 LTS. Para isso, devemos seguir os passos a seguir. Todo o procedimento deve ser feito com um usuário com permissões de administrador. Nesse caso, utilizaremos o root através do comando sudo su.

Você também pode instalar o Docker no sistema operacional Windows, fazendo o download da versão mais atual no Portal Docker (DOCKER, [s.d.]). O processo de instalação é bem simples, é preciso somente avançar as etapas do instalador.

______

**🔁Assimile**

Todos os procedimentos utilizados para instalação foram retirados da documentação oficial do Docker, (DOCKER, [s.d.]). As ferramentas de tecnologia atualizam-se a tal velocidade que somente acompanhando a documentação oficial é possível manter-se atualizado. Portanto, como um profissional engajado, procure sempre pelas fontes oficiais das ferramentas.

______

Antes de instalar a ferramenta, devemos remover versões anteriores do Docker que possam estar instaladas, usando o comando:

`**sudo apt-get remove docker docker-engine docker.io**`

Caso não tenha nenhuma versão instalada, será exibida a mensagem que foi impossível encontrar o pacote _docker-engine_.

Antes de instalar o Docker CE pela primeira vez em uma nova máquina host, você precisa configurar o repositório do Docker, atualizando os pacotes de sua máquina. Depois, você pode instalar e atualizar o Docker do repositório. Portanto, execute os comandos que vão atualizar a máquina:

`**sudo apt-get update**`

O comando acima tem o objetivo de realizar uma atualização de pacotes do Ubuntu. Na execução desse comando, o tempo pode variar de acordo com os pacotes que precisam ser atualizados, da velocidade da máquina e da conexão com a internet.

Através do comando abaixo atualizamos os pacotes necessários para a instalação do Docker. Para obter uma instalação bem-sucedida, é bom ter os programas utilizados nela em suas últimas versões:

`**sudo apt-get install \ apt-transport-https \ ca-certificates \ curl \ software-properties-common**`

Após atualizar os repositórios, vamos adicionar o repositório de instalação do Docker, usando o seguinte comando:

`**curl -fsSL https://download.docker.com/linux/ubuntu/gpg| sudo apt-key add -**`

Nesse comando, estamos fazendo o apontamento do caminho de instalação oficial do Docker que o Ubuntu deve acessar quando queremos efetuar a instalação. Após o apontamento da URL indicando o local para download o Docker para Ubuntu, será possível adicionar o repositório no próximo comando:

`**sudo add-apt-repository \ "deb [arch=amd64]https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) \ stable"**`

O comando utiliza a permissão considerada **admin** nos sistemas operacionais da família Linux, através da palavra sudo. Depois de usar a permissão de usuário do sudo, utilizamos o add-apt-repository para adicionar o repositório, que pode ser comparado a uma loja de aplicativos, responsável pelo download do Docker na versão Ubuntu. O restante do comando é o caminho do repositório.

Após adicionar o repositório para download do Docker, como mostra a figura a seguir, devemos mais uma vez atualizar o apt-get, conforme o comando seguinte para aplicar as alterações:

`**sudo apt-get update**`

[![](https://ampli-images.s3.amazonaws.com/production/50ac2934-0e51-42fd-82a4-20af29d968a5/original)](https://ampli-images.s3.amazonaws.com/production/50ac2934-0e51-42fd-82a4-20af29d968a5/original)

Saída do comando que adiciona o repositório de instalação do Docker. Fonte: captura de tela elaborada pelo autor.

Agora vamos utilizar o comando de instalação do Docker. Lembrando que, para que esse comando funcione, devemos seguir as etapas de apontar o repositório em que o Docker está disponível e adicionar esse repositório em nossa lista. No comando utilizamos o **sudo** para usar a permissão **admin** do sistema e o **apt-get install** para a fazer a instalação, por último o nome do programa que vamos instalar, no caso, o Docker (**docker-ce**).

`**sudo apt-get install docker-ce**`

Com todas as configurações feitas para atualizar os pacotes necessários e adicionar o repositório que contém o Docker, agora é possível fazer a instalação. Veja na figura abaixo o comando sendo aplicado no terminal e também o início da sua execução.

[![](https://ampli-images.s3.amazonaws.com/production/2e4d998b-5f82-4257-ac36-b8a8cbb31696/original)](https://ampli-images.s3.amazonaws.com/production/2e4d998b-5f82-4257-ac36-b8a8cbb31696/original)

Saída do comando que faz a instalação do Docker. Fonte: captura de tela elaborada pelo autor.