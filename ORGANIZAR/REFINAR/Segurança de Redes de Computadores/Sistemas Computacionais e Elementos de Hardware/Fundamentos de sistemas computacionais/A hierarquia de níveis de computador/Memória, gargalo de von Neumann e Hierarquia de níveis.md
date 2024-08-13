[![](https://ampli-images.s3.amazonaws.com/production/31839384-dd5b-4e0a-b0ae-6a7a4602969a/original)](https://ampli-images.s3.amazonaws.com/production/31839384-dd5b-4e0a-b0ae-6a7a4602969a/original)

A memória é o espaço que recebe as informações para serem processadas e, também, após seu processamento, para serem enviadas aos dispositivos de saída. Esse espaço é composto por registradores que são endereçados, ou seja, são os espaços de memória que recebem os dados e são divididos de acordo com a função, como espaço para o sistema operacional, controle de dispositivos de entrada e saída, espaço para a execução de programas e para os dados a serem processados e retornados após o processamento.

Um espaço de memória pode conter uma instrução de um programa ou um dado qualquer, que serão endereçados na memória pela unidade de controle da CPU. Os dados que serão processados pela ULA ficam na memória e a unidade de controle endereça estes dados. Isso permite que a ULA identifique onde estão os dados a serem processados, execute as operações necessárias, e a unidade de controle pode definir onde armazenar os dados resultantes do processamento. A memória que recebe esse endereçamento e é usada para receber as informações da unidade de entrada e as processadas pelo computador é a memória RAM (SOUZA FILHO; ALEXANDRE, 2014).

Nessa arquitetura de computadores estão previstas também as unidades de entrada e saída de dados. Como você já deve ter visto, estas unidades são compostas por diversos dispositivos e podem ser divididos em (SOUZA FILHO; ALEXANDRE, 2014):

- **Dispositivos de Entrada**: nos quais podemos inserir/entrar com dados no computador. Exemplo: teclado, mouse, telas sensíveis ao toque (touch screen).
- **Dispositivos de Saída**: em que os dados podem ser visualizados. Exemplo: telas e impressoras.
- **Dispositivos de Entrada/Saída**: são dispositivos que podem enviar e receber dados, como o disco rígido, pen drives, as conexões de internet via cabo e Wi-Fi, monitores e telas touch screen, dentre outros (FONSECA FILHO, 2007).

A via de transmissão de dados entre a CPU e a memória limita de certa forma a velocidade do processamento de um computador. Os barramentos têm esta função e a troca de dados entre o processador e a memória fica limitada pela taxa de transferência de dados que esses barramentos são capazes de proporcionar, que em geral são bem menores que a capacidade dos processadores, sendo um fator limitador da velocidade atingida no processamento das informações. Esse problema aumenta a cada nova geração e o desenvolvimento de tecnologia com maior número de barramentos é uma das soluções adotadas pelos fabricantes de tecnologia (TANENBAUM, 2006).

_______

**🔁 Assimile**

Nos computadores atuais, podemos observar a divisão da arquitetura de von Neumann, são aparelhos dotados de processadores, memória RAM e dispositivos de entrada e saída, como monitores, teclados, mouse, discos rígidos no caso de computadores e notebooks e, no caso de aparelhos mobile, como smartphones e tablets, temos telas touch screen e cartões de memória. A estrutura de arquitetura continua sendo praticamente a mesma, mudando apenas os dispositivos de acordo com a evolução tecnológica dos aparelhos.

_______

**📝 Exemplificando**

O computador recebe as informações através da unidade de entrada e de seus dispositivos, a CPU processa essas informações e retorna o resultado deste processamento através da unidade de saída e de seus dispositivos. As informações são convertidas pelo processador em sistema binário (0 e 1) no momento da entrada de dados e convertidas para o sistema alfanumérico, usado por nós, usuários, no momento da saída dos dados.

_______

**💪 Faça você mesmo**

Tendo como base a Arquitetura de von Neumann, pesquise e desenvolva um relatório detalhado sobre barramentos de computadores. A pesquisa deverá descrever:

- O que são barramentos e como funcionam.
- Categorias básicas de barramentos.
- Barramento de dados.
- Barramento de endereços.
- Barramentos de sinais de controle.

_______

Para que programas e dados sejam processados, foi criada uma organização em uma hierarquia de níveis de forma hipotética, ou seja, essa hierarquia foi pensada para poder classificar as etapas do processamento que acontece dentro de um computador. Nessa hierarquia temos o nível mais alto, que é percebido pelo usuário e no qual são mostrados os programas e os dados, e os demais são executados internamente pelo computador (NULL; LOBUR, 2011).

[![](https://ampli-images.s3.amazonaws.com/production/8b4cbb22-8052-48b5-9c2e-024684bde527/original)](https://ampli-images.s3.amazonaws.com/production/8b4cbb22-8052-48b5-9c2e-024684bde527/original)

**Máquinas com arquiteturas diferentes da arquitetura de von Neumann** - Embora os computadores tenham seguido a arquitetura proposta por von Neumann, existem máquinas que computam dados e que não foram construídas usando essa arquitetura. Entre essas máquinas encontramos computadores analógicos, computadores com múltiplos processadores funcionando em paralelo e executando programas de forma cooperativa, ou seja, um programa sendo executado por mais de um processador, redes neurais artificiais, usadas principalmente em desenvolvimento de sistemas que envolvam inteligência artificial, e máquinas de fluxos de dados, que realizam suas operações com os dados disponibilizados no momento do processamento, não havendo, nesse caso, uma programação feita antecipadamente (TANENBAUM, 2006).