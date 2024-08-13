**Considerações iniciais**

A modelagem de dados faz parte de uma etapa muito importante do desenvolvimento de sistemas, na qual se desenha toda a estrutura dos dados que envolvem uma atividade humana a ser informatizada. O estudo feito sobre a modelagem de dados serve tanto para uma pequena atividade comercial como para uma grande organização.

A modelagem de dados antecede a construção do banco de dados em um meio computacional, ela mostra a estrutura do banco de dados, seja do ponto de vista do usuário como da sua forma física.

**Introdução ao banco de dados**

Um banco de dados é um conjunto de elementos extraídos a partir de informações do mundo real. Esses dados são organizados, classificados e relacionados de forma que possam gerar novas informações para o mundo real. O nome **banco de dados** teve sua origem na tradução da palavra inglesa **data banks** e mais tarde foi modificada por **database**, que significa **base de dados**.

O século XXI está marcado pela "Era da Informação Digital". O mundo dos negócios, o sucesso das empresas, o comércio e a educação de um país dependem de um elemento vital: a **informação**. As informações podem justificar fatos que contribuem para a formação do conhecimento e a tomada de decisões.

A informática se preocupa em gerar a informação por meio de tecnologia ágil e eficaz para que esteja ao alcance de todos. O banco de dados é um grande responsável pelo processo. A montagem adequada, seguida de regras e métodos permite que os dados extraídos sejam corretos e as informações geradas sejam espelho da realidade.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121575/a01i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121575/a01i01_md80_100.jpg)

**Dado e informação, qual a diferença?**

O dado identifica ou quantifica algo, é absoluto e objetivo. A informação tem um significado para o mundo real, tem valor relativo ou é uma qualificação do dado. A informação pode ter um ou mais dados. Quando um dado lembra um fato associado, ele vira informação. Certos nomes de pessoas ou lugares que ficaram famosos pelos seus fatos se tornaram ícones e agregam valores, por exemplo, Ronaldinho.

Exemplos de informações:

O aluno Mario Silva é casado com Laura, mora na Rua Abraão Lins, 230. Ele nasceu no bairro da Bela Vista em São Paulo e sua profissão é vendedor.

Estas informações possuem vários dados envolvidos e o seu conjunto tem um significado para o mundo real.

Examinando a frase, quais os dados que poderiam ser extraídos?

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121576/a01i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121576/a01i02_md80_100.jpg)

Se misturarmos os dados poderá não significar nada para nós que estamos lendo a frase.

Laura Bernardes, vendedor, Mario Silva, Rua Abraão Lins 230, São Paulo, Bela Vista.

Para que esses dados possam ser resgatados de um banco, é necessário classificá-los, organizá-los e relacioná-los; caso contrário, teremos um "banco de dados insignificante".

Classificando os dados, teremos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121577/a01i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121577/a01i03_md80_100.jpg)

Vamos analisar agora outro exemplo:"O inverno do Canadá é mais frio que o inverno brasileiro."

Essa é uma informação que pode ter significado para o mundo real. Nela está implícita a comparação das temperaturas mínimas dos dois países. Se criarmos uma tabela de países e suas temperaturas mínimas em um determinado ano, teremos os seguintes dados:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121578/a01i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121578/a01i04_md80_100.jpg)

A tabela contém dados: Canadá, Brasil, França; e a palavra países é apenas uma classificação desses dados, bem como - 3 º C, - 43 º C e + 8 º C, que também são dados classificados como temperatura mínima. A informação é uma mensagem significativa que nos leva a associar fatos do mundo real. O dado, por si só, não tem significado algum, ele apenas identifica algo. As comparações e as conclusões que tiramos dos dados geram informações. A afirmativa acima poderia ser concluída por um turista que sentiu na pele o frio dos dois países, mas se quisermos saber se realmente é verdadeira, precisamos comparar os dados da tabela ou repetiremos a mesma experiência de quem passou a informação. O banco de dados é formado por um conjunto de elementos organizados em forma de tabelas e relacionados entre si, de acordo com o significado que eles têm no mundo real. Se os dados e os seus relacionamentos são verdadeiros, as informações que obtemos deles também serão verdadeiras.

Saiba por que os dados são um importante recurso corporativo.

[**ANIMAÇÃO**](https://ead.uninove.br/ead/disciplinas/web/_g/md80_100/a01v01_md80_100.htm)

**Formas de armazenamento de dados**

Podemos armazenar os dados de uma aplicação de duas maneiras:

1. **Sistema de armazenamento em arquivos**

O que é um arquivo? É uma forma que os sistemas operacionais utilizam para armazenar e organizar os dados em meio permanente. Um arquivo é composto por uma identificação e um conjunto de dados agrupados em forma de registros.

Cada registro é formado por campos em que esses dados são armazenados, por exemplo, imagine um arquivo para armazenar os dados de funcionários. Cada funcionário tem seus dados dentro de um registro do arquivo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121579/a01i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121579/a01i05_md80_100.jpg)

Os arquivos são criados e mantidos pelos programas desenvolvidos em uma linguagem que o programador escolhe para desenvolvê-los. Os dados somente podem ser acessados em um programa da mesma linguagem em que foram gerados ou algum programa compatível.

Os arquivos são dependentes da linguagem em que foram criados. Em uma organização, os sistemas baseados em arquivos apresentam as seguintes **desvantagens**:

- **Inconsistência e redundância de dados**:

Uma vez que os arquivos são mantidos por aplicações feitas por vários programadores, ao longo do tempo, com as mudanças que as empresas enfrentam, é comum haver alteração dos formatos e criação de arquivos para novas implementações. Assim, os dados se repetem, pois cada aplicação possui a sua forma de armazenamento.

- **Dificuldade de acesso aos dados**:

Toda vez que o usuário necessita de outra forma de acesso aos dados, diferente da que o sistema oferece, o programador precisa mudar o programa ou, muitas vezes, desenvolver outro para atender ao usuário. Isso tem um custo elevado de desenvolvimento para as empresas, além do tempo gasto para elaborá-lo, na maioria das vezes, há urgência em receber os dados, retardando a tomada de decisões.

- **Isolamento dos dados**:

Como os dados estão armazenados em arquivos independentes, é possível que, ao tentar acessá-los de outro arquivo com formato diferente, não seja possível ou haja necessidade de criar novas aplicações para compatibilizá-los.

- **Falta de integridade**:

Uma aplicação de usuário geralmente é feita por vários arquivos e existe sempre uma dependência e uma relação entre os dados de um arquivo para outro. Se o programador não se preocupar, ou não conhecer essa dependência, correrá o risco de criar programas que, ao buscar dados, resultem em uma pesquisa errada, ocasionando danos à empresa.

- **Falta de atomicidade**:

Transação atômica – em computação – significa que, em uma interrupção qualquer no sistema por falha técnica, essa transação deve ser completada ou  abortada, ou seja, todos os arquivos devem ser atualizados automaticamente ou retornados à situação anterior. No sistema baseado em arquivos, esta preocupação recai na mão dos programadores, que devem criar mecanismos de tratamento a falhas. Se a empresa não possui uma política de padronização das ações a serem tomadas, o programador pode errar no processo, afetando os dados.

- **Falta de segurança**:

Os sistemas baseados em arquivos dependem da proteção do sistema operacional e das permissões de acesso ao dispositivo onde estão armazenados. O programador poderá ter se lembrado de criar senha na sua aplicação, mas se outro programador tentar criar um programa para acessar o mesmo arquivo, sem proteção alguma, este fica vulnerável a modificações indesejadas, que normalmente são feitas pelos usuários.

1. **Sistema de banco de dados**

Um Sistema de Gerenciamento de Banco de Dados (SGBD) consiste em uma coleção de dados inter-relacionados e um conjunto de programas que fazem acesso aos dados. Os SGBDs são concebidos para gerenciar desde um pequeno conjunto de dados até um grande volume. Oferecem as estruturas para armazenamento e todos os mecanismos para manipulação, ou seja, inclusão, alteração, exclusão, seleção e busca dos dados.

A estrutura é criada pelos analistas de banco de dados ou pelos desenvolvedores de sistemas aplicativos para o usuário final ter fácil acesso.

**Por que usar um sistema de banco de dados?**

Os primeiros sistemas de armazenamento de dados eram baseados em arquivos. Os SGBDs surgiram para eliminar todos os problemas apontados como desvantagens na utilização dos sistemas baseados em arquivos.

Os sistemas de gerenciamento de banco de dados possuem as seguintes **vantagens**:

- Integridade dos dados.
- Segurança de acesso aos dados.
- Atomicidade nas transações.
- Concentração dos dados em um repositório, geralmente em um servidor de dados.
- Independência de linguagem de programação.
- Impõem regras de utilização para toda e qualquer aplicação que se conectar ao banco de dados.