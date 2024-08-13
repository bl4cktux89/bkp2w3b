**Wireshark**

O Wireshark é um analisador de tráfego (também chamado de _**sniffer**_) de código aberto, originalmente desenvolvido por Gerald Combs, em 1998; à época, um aluno graduado cinco anos atrás, em Ciência da Computação, na Universidade do Missouri, no Estado de Kansas (EUA). Atualmente conta com centenas de contribuidores ao redor do mundo, tendo instaladores para MS-Windows© (incluindo uma versão _**portable**_), Unix, GNU/Linux e OSX©: [**https://www.wireshark.org**](https://www.wireshark.org/) download.html. Na página do projeto é possível encontrar a documentação atualizada, incluindo os procedimentos para instalação nos diferentes sistemas operacionais: [**https://www.wireshark.org/docs/**](https://www.wireshark.org/docs/).

Após instalação, deve-se indicar qual a interface de rede que se deseja analisar com um duplo clique do mouse sobre o nome da interface como, por exemplo, a interface de rede _**eno1**_, de uma máquina com sistema operacional GNU/Linux, conforme Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/2/4/2712402/41503.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/2/4/2712402/41503.jpg)

Fonte:

Após essa etapa, o Wireshark inicia automaticamente a captura dos pacotes sendo transmitidos e recebidos por essa interface de rede, e a análise dos mesmos já pode ser realizada, incluindo os tipos de protocolos, endereços IP e portas de comunicação, conforme ilustra a Figura 2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/2/4/2712405/41504.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/2/4/2712405/41504.jpg)

Fonte:

O Wireshark possibilita uma análise detalhada, baseada no modelo de referência ISO/OSI, camadas 1 (física) a 4 (transporte), que são as camadas referentes aos dispositivos de rede, lembrando que as demais camadas – 5 (sessão) a 7 (aplicação) – são inerentes aos programas que utilizam os pacotes das camadas inferiores.

Embora não utilizaremos essa ferramenta na disciplina, pois não há possibilidade de integração com o simulador Packet Tracer®, é importante que você se familiarize com o Wireshark se desejar ampliar seus conhecimentos e se tornar um profissional de redes altamente capacitado.

Que tal praticarmos um pouco agora?

Note que, para realização da atividade sugerida, você deve instalar o Wireshark em seu computador. Verifique os links apresentados anteriormente nesta aula caso tenha dúvidas na instalação, ou ainda, acompanhe algum dos vários vídeos no Youtube demonstrando a instalação: [**https://www.youtube.com/results?search_query=instala%C3%A7%C3%A3o+wireshark**](https://www.youtube.com/results?search_query=instala%C3%A7%C3%A3o+wireshark)

Siga as etapas abaixo:1. Abra o navegador de internet no seu PC (por exemplo, o Google Chrome).2. Abra o Wireshark.2.1 Selecione então a opção _**Interfaces**_ do menu _**Capture**_.2.2. Na janela que aparece, clique no botão _**Start**_ para iniciar a captura de tráfego de uma interface de rede no seu computador.3. Com o Wireshark em execução, volte ao seu navegador e acesse o site: http://www.uninove.br/4. Depois que a página foi carregada, volte para a tela do programa Wireshark e finalize a captura de pacotes através das teclas Ctrl + E (atalho do Wireshark para encerrar a captura).

Agora, com base na captura realizada, tente identificar:

a) o endereço IP de origem (origem, neste caso, o seu computador). **Dica:** observe a coluna _**Source**_, da tela de captura do Wireshark.b) o endereço IP de destino (destino, neste caso, algum dos servidores que hospedam o website da Uninove). **Dica:** observe a coluna _**Destination**_, da tela de captura do Wireshark.c) a porta TCP de origem (origem, neste caso, o seu computador). **Dica:** observe a coluna _**Info**_, da tela de captura do Wireshark.d) a porta TCP de destino (destino, neste caso, algum dos servidores que hospedam o website da Uninove). **Dica:** observe a coluna _**Info**_, da tela de captura do Wireshark.e) diferença de tempo entre o envio da sua requisição e o recebimento da página, enviada pelo servidor. **Dica:** o tempo é exibido na coluna _**Time**_, por padrão, em segundos.

**Packet Tracer****®**

O Packet Tracer® é um simulador de redes, desenvolvido e disponibilizado gratuitamente pela Cisco. Apesar de, por motivos óbvios, apenas simular equipamentos da própria Cisco, seu uso é muito comum em vários cursos relacionados à rede de computadores, uma vez que, independentemente da sintaxe (estrutura) dos comandos, os conceitos ali empregados são similares dentre vários fabricantes de equipamentos de rede, como HP©, Juniper© e Extreme Networks©, para citar alguns. Assim sendo, essa também é a ferramenta de suporte a esta disciplina, e você deve instalar esse simulador no seu computador, e tentar reproduzir as várias configurações apresentadas em cada tópico, para ter um melhor aproveitamento desse curso.

Para obter o Packet Tracer, você precisará acessar o seguinte link: [**https://www.netacad.com/pt-br/courses/packet-tracer/introduction-packet-tracer**](https://www.netacad.com/pt-br/courses/packet-tracer/introduction-packet-tracer)

Nesta tela, você precisará passar o mouse sobre a mensagem “Inscreva-se hoje mesmo”, e clicar no botão “English” (uma vez que as próximas telas apenas estarão disponíveis neste idioma), conforme Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/5/6/2715635/41505.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/5/6/2715635/41505.jpg)

Fonte:

Na tela seguinte, você precisará preencher o formulário de cadastro para obter suas credenciais de login, conforme Figura 4.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/5/6/2715641/41506.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/5/6/2715641/41506.jpg)

Fonte:

Após realizado o cadastramento, e confirmado seu e-mail, você já terá acesso ao NetAcad. Agora basta acessar o seguinte link: [**https://www.netacad.com/group/offerings/packet-tracer/**](https://www.netacad.com/group/offerings/packet-tracer/), onde você poderá efetuar o _**download**_ do Packet Tracer e instalá-lo no seu PC:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/5/6/2715646/41507.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/1/5/6/2715646/41507.jpg)

Fonte:

Uma vez instalado, você já poderá utilizá-lo para configurar os equipamentos no simulador, como se estivesse com os equipamentos fisicamente na sua frente! Mas vá com calma, antes de mais nada, você precisará entender os modos de operação do IOS (sistema operacional da Cisco®, que roda nos equipamentos de rede, simulados no Packet Tracer).

**Modos de operação do IOS**

Existem, essencialmente, três modos de operação nos switches e roteadores da Cisco: o de usuário, o de usuário privilegiado e o de configuração. Você precisará reconhecer e saber como navegar entre esses modos, para poder configurar os equipamentos.

A dica é simples; basta analisar os elementos no _**prompt**_ (parte que aparece ao lado direito da tela, antes da parte em que é possível digitar alguma coisa), destacado em negrito, conforme segue:

a) Modo de usuário: _**nome_do_equipamento**_ **>**

b) Modo privilegiado: _**nome_do_equipamento**_ **#**

c) Modo de configuração: _**nome_do_equipamento**_ **(config)#**

**GNS3**

O GNS3 é um programa gratuito e de código aberto, que também serve para simularmos equipamentos de rede em um computador, porém um pouco mais completo e fiel ao equipamento real, uma vez que ele é, na verdade, um emulador.

Um simulador é um sistema que se comporta de maneira **similar** ao sistema simulado – em nosso caso, switches, roteadores, etc. Geralmente disponibiliza várias funcionalidades do sistema real, mas não todas. Um emulador é um sistema que se comporta de maneira **idêntica** ao sistema emulado – em nosso caso, switches, roteadores, etc. Por essa razão, disponibiliza todas as funcionalidades do sistema real (inclusive _**bugs**_).

Entretanto, por conta disso, para utilizá-lo você precisará ter acesso ao equipamento real para obter o _**firmware**_ (instruções de software implementadas diretamente no hardware e que, por conta disso, são específicas para cada hardware), além de exigir muito recurso computacional (memória RAM e processamento) do PC onde o GNS3 estiver rodando. Esses são os motivos pelo qual não utilizaremos o mesmo nessa disciplina mas, caso tenha curiosidade, tempo e paciência, você poderá consultar o seguinte link, que possui as informações necessárias para instalá-lo e configurá-lo: [**https://docs.gns3.com/11YYG4NQlPSl31YwvVvBS9RAsOLSYv0Ocy-uG2K8ytIY/index.html**](https://docs.gns3.com/11YYG4NQlPSl31YwvVvBS9RAsOLSYv0Ocy-uG2K8ytIY/index.html)

Acredito que cabe uma nota aqui: não estamos dizendo que é uma ferramenta ruim. Pelo contrário: o GNS3 é uma ferramenta excelente e extremamente poderosa; porém acreditamos que não é a ferramenta de apoio ideal em relação aos propósitos dessa disciplina.

**Conclusão**

Neste capítulo apresentamos:

- Principal uso do analisador de tráfego Wireshark;
- Principal uso do simulador Packet Tracer;
    
    ®
    
- Vídeo tutorial sobre o uso e configurações básicas dos principais dispositivos disponíveis no Packet Tracer;
    
    ®
    
- Conceitos sobre simuladores e emuladores;
- Principal uso do emulador GNS3.