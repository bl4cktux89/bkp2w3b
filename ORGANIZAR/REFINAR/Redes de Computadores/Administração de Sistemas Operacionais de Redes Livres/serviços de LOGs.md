### Introdução aos Logs do Linux

Um arquivo de log, em um ambiente computacional, é a documentação produzida automaticamente e com data e hora de eventos relevantes para um sistema em particular. Praticamente todos os aplicativos e sistemas de software produzem arquivos de log. A palavra ?log? vem do termo ?lag?, que antigos noruegueses usavam como registro da passagem por algum lugar, uma árvore derrubada. Mais tarde já com o nome ?log? aplicado ao registro de velocidade e posição de navios feitas pelos marinheiros e chamando-se de log-book (livro de registros) [1].

### Exemplos de logs

Em um servidor Web, um log é uma lista de acesso individual de todos os arquivos e páginas que as pessoas solicitaram de um site. Esses arquivos incluirão os arquivos HTML e suas imagens gráficas incorporadas e quaisquer outros arquivos associados que sejam transmitidos. A partir dos arquivos de log do servidor, um administrador pode identificar números de visitantes, os domínios a partir dos quais eles estão visitando, o número de solicitações para cada página e os padrões de uso de acordo com variáveis como as horas do dia, semana, mês ou ano, etc [2].

Há uma grande quantidade de informações disponível para você dentro de seus logs, embora nem sempre seja tão fácil, quanto você gostaria, de extraí-lo. Neste tópico, vamos abordar alguns exemplos de análise básica que você pode fazer com seus logs imediatamente (basta pesquisar o que está lá). Também abordaremos uma análise mais avançada que pode levar algum esforço inicial para configurar corretamente, mas você economizará tempo no dia a dia. Exemplos de análise avançada que você pode fazer com os dados analisados incluem: gerar resumo de contagens, filtragem de valores de campo e muito mais.

Vamos mostrar a você primeiro como fazer isso sozinho na linha de comando usando várias ferramentas diferentes e, em seguida, mostrar como uma ferramenta de gerenciamento de log pode automatizar muito do trabalho braçal e torná-lo muito mais simplificado.

### Logs disponíveis em sistemas Linux

As logs são divididas em logs do sistema e logs de aplicações. Exemplos de logs do sistema são: syslog, auth.log, dmesg, etc. e, exemplos de logs de aplicações são: samba, squid, etc. (aqui, arquivos de log que recebem o mesmo nome da aplicação).

Se você navegar pelo diretório /var/log, vai verificar uma infinidade de nomes de log. Veja um print de tela abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839018/36545.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839018/36545.png)

Se você olhar bem, vai perceber que algumas logs tem o nome repetido, mas com uma numeração em ordem crescente após um ponto (.). Isto ocorre porque algumas logs, principalmente do sistema, que fecha o arquivo de log de cada dia e geram um novo no dia seguinte. Então a syslog (principal log do sistema) de ontem é chamada syslog.1 e assim por diante.

O monitoramento de arquivos de log ajudará a detectar o seguinte:

- Problemas de equipamento, como falhas no disco rígido ou falhas de energia.
- Problemas do usuário, como repetidas falhas de login.
- Violações/ataques de segurança externos ao sistema.

Estes são os arquivos de log mais importantes que você deve manter o controle em seu sistema. Aqui temos algo Ubuntu. Estas logs diferenciam-se por distribuição.

- syslog - Registra a maioria das mensagens e erros do sistema.
- auth.log - As mensagens de autenticação, os serviços xinetd etc são registados aqui.
- cron - As atividades de trabalho do Cron (sistema de agenda de atividades) são registradas neste arquivo.
- maillog - Transações de correio.
- dmesg - Contém tudo que ocorre no boot do sistema.

Esses arquivos de log contêm informações detalhadas sobre as respectivas funções monitoradas.

### Pesquisando por Filtros

A maioria dos sistemas de log linux gravam suas logs no diretório /var/log. Procurar por texto é a maneira mais básica de encontrar o que você está procurando. A ferramenta mais comum para pesquisar texto é grep. Esta ferramenta de linha de comando, disponível na maioria das distribuições Linux, permite pesquisar seus logs usando expressões regulares. Uma expressão regular é um padrão escrito em uma linguagem especial que pode identificar o texto correspondente. O padrão mais simples é colocar a string que você está procurando entre aspas.

Veja um exemplo para localizar logs de abertura de seção "c1 of user luckygav" em um sistema Ubuntu:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839019/36546.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839019/36546.png)

Pode ser difícil construir expressões regulares que sejam precisas. Por exemplo, vamos dizer que eu quero saber quando o Network Manager atualizou o IP do servidor de domínio (nameserver). No exemplo abaixo para o Ubuntu, fiz a consulta usando a expressão regular “Network Manager”. Veja como vieram várias coisas indesejáveis. O filtro foi ruim.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839021/36547.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839021/36547.png)

Na verdade, precisamos conhecer bem o que queremos pesquisar para não poluir nossa pesquisa. Eu queria saber sobre nameserver e apareceram outras coisas, além do nameserver. Agora veja como ficou a pesquisa “nameserver”.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839022/36585.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839022/36585.png)

Outra técnica útil é você fazer pesquisa surround com grep. Surround significa, para este contexto, pesquisar ao entorno do foco de pesquisa. Isso mostrará o que aconteceu algumas linhas antes ou depois de um evento. Ele pode ajudá-lo a depurar o que levou a um determinado erro ou problema. A opção B (before) mostra-lhes linhas antes, e A (after) mostra-lhes linhas depois. Por exemplo, meu servidor está executando um DNS Server, um servidor de domínio, mas percebi que a zona de DNS não foi devidamente carregada com a mensagem “not loaded”. Se fizer a pesquisa na syslog.1 (syslog de ontem) com esta expressão regular, vai aparecer o seguinte resultado:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839025/36587.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839025/36587.png)

Ótimo, mas para que serve esta consulta Confirmo que o erro ?not loaded? ocorreu, mas não sei a causa. Então uso o surround 3 linhas antes e duas linhas depois. Veja como agora eu descubro que o problema é que faltou o registro NS na configuração do servidor de DNS (Bind9).

**grep -B 3 -A 2 "not loaded" syslog.1**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839028/36588.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839028/36588.png)

Você também pode limitar o grep com o tail para obter as últimas linhas de um arquivo de log, ou para acompanhar os logs e imprimi-los em tempo real. Isso é útil se você estiver fazendo alterações interativas como iniciar um servidor novo ou testar uma alteração de código ou configuração.

Veja o exemplo acima, onde aparecem muitas linhas sobre o assunto, mas só precisávamos ver algumas. O tail seria útil.

Sistemas de gerenciamento de registros log têm maior desempenho e capacidades de pesquisa muito poderosas. Eles geralmente indexam seus dados e otimizam consultas para que você possa pesquisar rapidamente gigabytes ou terabytes de logs em segundos. Em contraste, isso levaria minutos ou em casos extremos horas com grep. Os sistemas de gerenciamento de registros também usam linguagens de consulta como o Lucene, que oferecem uma sintaxe mais fácil para pesquisar números, campos e muito mais.

O comando cut permite analisar campos de registros delimitados. Os delimitadores são caracteres como sinal de igual ou vírgulas que dividem campos ou pares de valores-chave. Você pode colocar qual é a ordem no sinal em cada registro, por exemplo, você procura por campos definidos pelo sinal de igual (=), mas apenas a oitava ocorrência delimitada por (=). Vamos dizer que queremos analisar se houve alguma tentativa de acesso não autorizado e qual o usuário. Primeiro sem o cut vem toda a informação:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839030/36589.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839030/36589.png)

Agora com a delimitação vem apenas o campo que eu quero.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839031/36591.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839031/36591.png)

Alternativamente, você pode usar o awk, que oferece recursos mais poderosos para analisar os campos. Ele oferece uma linguagem de script para que você possa filtrar quase tudo o que não é relevante.Por exemplo, digamos que temos a seguinte linha de log em um sistema Ubuntu e queremos extrair o nome de usuário que falhou no login:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839033/36592.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839033/36592.png)

Mas quero apenas ver o nome do usuário para ver que está tentando acessar via ssh o meu servidor. Veja como você pode usar o comando awk. Primeiro, coloque uma expressão regular /sshd.*invalid user / para corresponder às linhas de usuário sshd inválido. Em seguida, imprima o nono campo usando o delimitador padrão de espaço usando {print $ 9}. Isso exibe os nomes de usuário.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839035/36594.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839035/36594.png)

Você pode direcionar a saída deste comando para um arquivo e contar quantas vezes o Pedro tentou logar via ssh. Não preciso dizer quanto isto é útil em termos de segurança de redes.

Os sistemas de gerenciamento de registros tornam a análise mais fácil e permitem aos usuários analisarem rapidamente grandes coleções de arquivos de log. Eles podem analisar automaticamente os formatos de log padrão, como logs comuns do Linux ou logs do servidor web. Isso economiza muito tempo porque você não precisa pensar em escrever sua própria lógica de análise ao solucionar um problema do sistema.

Aqui você pode ver um exemplo de mensagem de log do sshd que tem cada um dos campos da máquina remota e o usuário analisado. Esta é uma captura de tela do Loggly, um serviço de gerenciamento de log baseado em nuvem.

Podemos ver um resultado da aplicação do Loggly.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839036/36595.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/0/839036/36595.png)

Fonte: www.loggly.com

### Conclusão

Estes são exemplos que podem ser úteis, mas a exploração de logs é uma arte à parte. Você pode criar shell scripts que ficam analisando as entradas nas logs para achar alguma ameaça de invasão. Pode controlar um sistema remoto quanto ao fato de algum disco começar a apresentar defeitos e tomar alguma ação antes da falha. São infinitas as possibilidades.