[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Um dos clientes da _startup_ de tecnologia que você trabalha mostrou que a aplicação desenvolvida por sua empresa não está funcionando corretamente, porém você notou que isso ocorre pela falta de sincronismo entre os relógios de duas máquinas do cliente. Para que o cliente consiga fazer o procedimento nas máquinas que não estão sincronizadas, seu chefe solicitou a criação de um relatório técnico com os comandos necessários, passo a passo, para que o próprio cliente sincronize a máquina com as demais.

Para ajudá-lo, ele informou que o sistema operacional da nova máquina é Windows. A primeira informação relevante para o relatório é o sistema operacional, pois, dependendo da escolha, o processo de configuração se difere. Nesse caso, você deixará registrado como configurar para o sistema Windows.

A segunda informação importante no seu relatório é o conceito de servidor NTP, portanto, usando suas palavras e ilustrações, inclua esse item no documento.

Agora vem a parte mais desafiadora para quem não tem familiaridade com o mundo da tecnologia: realizar a configuração da data e hora por meio dos comandos necessários. Para que tudo funcione corretamente, é preciso que o servidor NTP esteja instalado em todos os equipamentos, inclusive naquele que fará a configuração. Faça a configuração da seguinte forma:

Abra o Prompt de Comando (CMD).

Na janela do CMD, insira o código a seguir e pressione a tecla “Enter”: `**w32tm /config /syncfromflags:manual /manualpeerlist:0.pool.ntp.org**`.

Utilize os comandos net stop w32time e net start w32time para parar o serviço e iniciar, reiniciando-o.

Force uma sincronização através do comando `**w32tm /resync /rediscover**`.

Com isso, fizemos o apontamento, reiniciamos o serviço e verificamos se a data e a hora estão sincronizadas. Que tal impressionar seu cliente e complementar seu relatório realizando uma pesquisa sobre a configuração para o sistema operacional Linux?

Continue firme em seus estudos, pois ainda vem muita coisa interessante e útil pela frente. Assim finalizamos esta aula. Esperamos que o conhecimento adquirido seja de importância para seu crescimento profissional. Bons estudos e até a próxima!