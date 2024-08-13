[![](https://ampli-images.s3.amazonaws.com/production/4ad9e6c5-7606-4dcb-af38-25bb899aaf32/original)](https://ampli-images.s3.amazonaws.com/production/4ad9e6c5-7606-4dcb-af38-25bb899aaf32/original)

Uma vez que lhe apresentamos a questão da disponibilidade dos sistemas e que estes podem vir a não funcionar, vamos falar um pouco sobre algumas soluções, como a alta disponibilidade.

A alta disponibilidade é definida como o conjunto de ações tomadas para garantir que, quando um elemento falhar, o sistema continuará funcionando, provendo seus serviços. Isso ocorre quando um sistema não tem pontos únicos de falha, ou seja: é composto de elementos que estão prontos para substituírem uns aos outros em caso de falha de um deles (SCHMIDT, 2006).

A figura a seguir mostra um exemplo de um sistema de computação de alta disponibilidade:

[![](https://ampli-images.s3.amazonaws.com/production/f31e561a-49fa-4dc9-b190-afde29e34745/original)](https://ampli-images.s3.amazonaws.com/production/f31e561a-49fa-4dc9-b190-afde29e34745/original)

Exemplo de Sistema de Alta Disponibilidade. Fonte: Wikipedia.

Na figura apresentada, podemos ver que a alta disponibilidade é atingida por meio de:

- **redundância de rede** – há dois _switches_ criando a rede. Caso um deles esteja indisponível, o outro garante a conectividade dos dispositivos. Além disso, ambos os _switches_ acessam a rede pública (por meio de dois roteadores separados, obviamente) por canais diferentes.

O ideal é que cada canal venha de um provedor diferente, para haver alta disponibilidade também no nível das comunicações remotas.

- **redundância de servidores** – há dois servidores, com os dados sendo guardados em um sistema comum de armazenamento de alta disponibilidade (sistema RAID). Caso um dos servidores venha a falhar, os dados continuarão disponíveis e sendo processados pelo outro servidor.
- **redundância de alimentação** – em que pese o fato de que todos os servidores estejam sendo alimentados pela mesma rede elétrica, há dois _nobreaks_ (UPS), um para cada lado da rede. Caso haja falha na rede elétrica, os _nobreaks_ passam a funcionar, e, como há dois deles, adicionamos mais um nível de alta disponibilidade.

Outros mecanismos de alta disponibilidade a serem considerados são os sistemas de _backup_, que podem ser de dois tipos:

- _backup_ local – por meio de fitas magnéticas, CDs/DVDs ou HDs externos. Útil nos _backups_ do dia a dia e para armazenamento remoto de _backups_, evita que os _backups_ sejam comprometidos em caso de incêndio ou inundação, por exemplo.
- _backup_ remoto – por meio de armazenamento na nuvem. Tende a ser mais caro e a não gerar _backups_ físicos, mas tem disponibilidade garantida, o que nem sempre é verdade para _backups_ locais, que podem se deteriorar e se perder.

______

**➕** **Pesquise mais**A alta disponibilidade é parte de um assunto mais amplo chamado “Tolerância a falhas”. A pesquisadora Taisy Silva Weber, professora do programa de pós-graduação da UFRGS discute o assunto em um artigo bastante didático. [Clique aqui](http://www.inf.ufrgs.br/~taisy/disciplinas/textos/ConceitosDependabilidade.PDF) para acessar o artigo e conferir, em especial as seções 2 e 3.