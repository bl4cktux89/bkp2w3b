[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Retomando a situação apresentada na introdução desta aula, considere que você está participando de um processo seletivo para uma oportunidade como trainee na área de DevOps da maior empresa nacional de portal de notícias, cujos clientes que consomem o conteúdo disponibilizado por essa empresa são bancos, em sua maioria. Na entrevista, você será submetido a algumas atividades práticas sobre virtualização, definidas pelo Coordenador de Infraestrutura.

Sua primeira atividade é criar uma máquina virtual. Crie uma máquina virtual com o software VirtualBox, com sistema operacional GNU/Linux, distribuição Ubuntu Desktop, nas configurações padrão, e acesse o website glassdoor (GLASSDOOR, 2021), a partir da máquina virtual recém-criada, utilizando o navegador Firefox, da Mozilla. A primeira coisa que devemos fazer é realizar o download do sistema operacional Ubuntu na versão Desktop que foi solicitada, pode ser feito no site do Ubuntu (UBUNTU, 2019). Agora, no VirtualBox, devemos ir até a opção “Novo”, conforme a figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/b05164fa-5d74-4b71-8cbe-056bac9ecaf0/original)](https://ampli-images.s3.amazonaws.com/production/b05164fa-5d74-4b71-8cbe-056bac9ecaf0/original)

Criando uma máquina virtual. Fonte: captura de tela do VirtualBox, elaborada pelo autor.

Agora, devemos definir um nome para nossa máquina virtual, o tipo de sistema operacional e a versão. É necessário também estabelecer a quantidade de memória RAM que será usada pela máquina virtual. O próximo passo é selecionar a criação de um novo disco virtual. Caso existam discos virtuais prontos, também podemos utilizá-los. Na próxima figura criamos um novo:

[![](https://ampli-images.s3.amazonaws.com/production/08963b67-3c35-45c7-a020-b12a5c111aa7/original)](https://ampli-images.s3.amazonaws.com/production/08963b67-3c35-45c7-a020-b12a5c111aa7/original)

Criando um disco virtual. Fonte: captura de tela do VirtualBox, elaborada pelo autor.

Agora que as configurações estão definidas e a máquina virtual já aparece na lista, vamos até a opção “_Configurações_”, representada pelo ícone de uma engrenagem, para apontar o caminho de nossa imagem (iso) que contém o sistema operacional. Podemos observar na figura abaixo que a opção “_Configurações_” está habilitada:

[![](https://ampli-images.s3.amazonaws.com/production/cebfb713-5781-4aa2-91a3-cddb6d02dd2f/original)](https://ampli-images.s3.amazonaws.com/production/cebfb713-5781-4aa2-91a3-cddb6d02dd2f/original)

Definindo as configurações da máquina virtual. Fonte: captura de tela do VirtualBox, elaborada pelo autor.

A figura abaixo mostra como apontamos o caminho da imagem de instalação do sistema operacional. Para isso ocorrer, devemos criar um leitor de CD virtual e indicar a imagem como se fosse um CD-ROM. Acessamos o menu “_Armazenamento_”, depois “_Vazio_” e, então, o ícone de um novo CD para localizar nossa imagem.

[![](https://ampli-images.s3.amazonaws.com/production/72791b3c-426e-47b9-9d20-b58ada3f31b3/original)](https://ampli-images.s3.amazonaws.com/production/72791b3c-426e-47b9-9d20-b58ada3f31b3/original)

Caminho da imagem de instalação do sistema operacional. Fonte: captura de tela do Ubuntu, elaborada pelo autor.

Após a seleção, o local em que estava escrito “_Vazio_” passa ter o nome da imagem do Ubuntu. Depois do apontamento do caminho da imagem, devemos pressionar o botão “_OK_” e, então, o botão “_Iniciar_”, representado pelo ícone de uma seta na cor verde. Feito isso, será aberta uma nova janela de execução da máquina virtual. Agora, devemos pressionar a tecla “_Enter_” do teclado para iniciar nossa máquina via CD, assim, teremos a opção de instalar nossa máquina, seguindo as etapas de instalação até a conclusão. Depois de finalizar a instalação, podemos ver a execução da máquina virtual. Agora, só resta ir até o site do Mozilla Firefox, realizar o download e a instalação e acessar o site _glassdoor_, conforme solicitado.