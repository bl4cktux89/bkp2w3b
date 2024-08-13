[![](https://ampli-images.s3.amazonaws.com/production/523c34a6-392c-4676-8042-a50d7fa0d9d1/original)](https://ampli-images.s3.amazonaws.com/production/523c34a6-392c-4676-8042-a50d7fa0d9d1/original)

Na maioria dos projetos de banco de dados para softwares de médio e grande porte, vários analistas e programadores acabam trabalhando no projeto inteiro ou em parte dele. Projetar e modelar banco de dados requer disciplina. É necessário estabelecer padrões de desenvolvimento, isto é, estabelecer regras para que todos os envolvidos modelem da mesma forma, e é nessa hora que entra em cena a ferramenta CASE.

CASEs (_Computer Aided Software Engeneering_ ou, em português, Engenharia de Software Auxiliada por Computador) são ferramentas que apresentam uma série de serviços que auxiliam no desenvolvimento de software e podem minimizar o tempo de desenvolvimento do software modelado.

De acordo com Navathe e Ramez (2005), as primeiras ferramentas CASEs surgiram na década de 80 e eram classificadas em:

- _**Lower CASE**_: com suporte nas fases de análise e projeto de sistemas.
- _**Upper CASE**_: com suporte nas fases de construção e análise de sistemas.

Hoje em dia as ferramentas CASEs são classificadas como _Integrated CASE_ com a união das ferramentas _Lower CASE_ e _Upper CASE_, atendendo a praticamente todas as fases de um projeto de sistemas.

Todos os tipos de ferramentas CASEs têm em comum a possibilidade da representação gráfica de elementos do projeto, podendo ser: o diagrama de entidade-relacionamentos, os diagramas de classes, casos de usos, etc. Existem várias ferramentas CASEs disponíveis como freeware (com opções básicas) e as proprietárias (pagas) com muitos recursos.

As ferramentas CASEs são utilizadas para automatizar várias  tarefas, por exemplo:

- **Geração de códigos**: de forma automática, os códigos podem ser gerados a partir do diagrama gráfico.
- **Geração de documentação**: permite padronização nos processos.
- **Execução de testes**: possibilita validações nas especificações formais de desenvolvimento.
- **Geração de relatórios**: permite o acompanhamento do planejamento e do gerenciamento do projeto.

_______

**🔁 Assimile**

A geração de códigos automáticos das ferramentas CASEs para banco de dados são conhecidas como scripts, que ajudam a tarefa de criar o banco de dados fisicamente no Sistema de Gerenciamento de Banco de Dados (SGBD), gerando todos os comandos em SQL de criação de tabelas, campos e chaves.

_______

Nas atividades da engenharia de software, a ferramenta CASE   é fundamental, auxiliando em todos os processos. Podemos citar Rational Rose, Astah, Genexus, Multicase, Clarify, entre outras.

As ferramentas mencionadas podem ser utilizadas para a modelagem de banco de dados, porém, existem ferramentas CASEs específicas para criar os diagramas de entidade-relacionamentos, como Oracle Designer, DBDesigner, Erwin, Embarcadero e MySQL Workbench. Uma tendência são as ferramentas CASEs online, como Draw.IO ou Lucidchart. A grande maioria das ferramentas (inclusive as online) possui versões freeware com algumas limitações, ideais para pequenos diagramas. Caso a pessoa ou empresa se interessar, poderá adquirir a versão oficial e com mais recursos. As ferramentas CASEs para banco de dados possuem as seguintes características, conforme Coronel e Rob (2011):

- Suporte à criação de diagramas gráficos.
- Utilização de alguma notação de modelagem de banco de dados.
- Geração de scripts SQL (_Structured Query Language_ – Linguagem de Consulta Estruturada).
- _Forward Engineer_: permite, a partir do DER (modelo gráfico), conectar de forma automática o banco de dados e criar automaticamente o modelo físico.
- _Reverse Engineer_: permite, a partir do modelo físico criado no banco de dados, a geração do modelo gráfico (DER) do banco de dados.
- Documentação: conforme os atributos são criados nas tabelas, a ferramenta CASE já cria o dicionário de dados de forma automática.

O Astah é uma ferramenta CASE para criar diagramas UML e possui as seguintes versões:

- _Community_: gratuita para projetos UML (com algumas limitações).
- _Professional_: versão completa e paga (ou disponível de forma _trial_).

É uma ferramenta ideal para os desenvolvedores Java, pois gera os scripts em Java, acelerando  o  processo  de  desenvolvimento do software. Na versão _Professional_ há a possibilidade de criar diagramas de entidade-relacionamentos, utilizando a notação IDEF1X, conforme a Figura abaixo, cuja bolinha preta representa o _N_ de muitos. Você poderá fazer o download diretamente no [site](https://astah.net/downloads/).

[![](https://ampli-images.s3.amazonaws.com/production/882fc24e-2ea1-4d9b-aaaf-0800023b4e80/original)](https://ampli-images.s3.amazonaws.com/production/882fc24e-2ea1-4d9b-aaaf-0800023b4e80/original)

Exemplo ferramenta CASE Astah. Fonte: captura de tela do Astah, elaborada pela autora

**📝 Exemplificando**

Para criar o diagrama da Figura acima, siga o passo a passo a seguir:

1. Vá ao Menu e escolha _Diagram → ER Diagram_.
2. Selecione a figura da tabela e dê dois cliques. Adicione os campos e insira as chaves primárias e estrangeiras na parte superior da tabela.
3. Para criar o relacionamento, selecione a tabela do lado 1, escolha a linha para relacionar as tabelas, arraste e solte em cima da chave estrangeira.

Uma das vantagens da ferramenta Astah é a possibilidade de criar automaticamente o dicionário de dados, basta exportar para a ferramenta Microsoft Excel, e o dicionário de dados é gerado com todas as tabelas, conforme a Figura abaixo. Para exportar o dicionário de dados, clique no menu  do  Astah, em _Tools_, entre na opção _ER Diagram_ e selecione a quarta opção: _Export Entity Definition Report_. Você deverá escolher as tabelas com que deseja criar o dicionário de dados e salvar com um nome.

[![](https://ampli-images.s3.amazonaws.com/production/64e3c30d-f755-477e-81ff-360274d402cc/original)](https://ampli-images.s3.amazonaws.com/production/64e3c30d-f755-477e-81ff-360274d402cc/original)

Exemplo dicionário de dados gerado no Astah. Fonte: captura de tela do Microsoft Excel, elaborada pela autora.

**➕ Pesquise mais**

Saiba mais sobre a Linguagem Unificada de Modelagem, a UML, nas páginas 505 a 517 do livro:

LEE, R. C.; TEPFENHART, W. M. [UML e C++](https://www.bvirtual.com.br/NossoAcervo/Publicacao/40): guia prático de desenvolvimento orientado a objeto. São Paulo: Pearson eBooks, 2001.