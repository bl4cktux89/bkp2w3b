# **Introdução da unidade**

[![](https://ampli-images.s3.amazonaws.com/production/209bdad5-4212-4d87-85a7-270a1ebc375e/original)](https://ampli-images.s3.amazonaws.com/production/209bdad5-4212-4d87-85a7-270a1ebc375e/original)

### **Objetivos da Unidade**

Ao longo desta Unidade, você irá:

- esclarecer os aspectos gerais da _engenharia de software_;
- explicar os conceitos, objetivos e paradigmas da Engenharia de _software_,
- analisar os fatos históricos do tema e a crise pela qual o desenvolvimento de _software_ passou.

### **Introdução da Unidade**

Iniciamos nossa disciplina de introdução à Engenharia de _software_! Você sabia que as boas práticas associadas à Engenharia de _software_ têm servido como apoio para todos os envolvidos no processo de desenvolvimento de um produto de _software_? Pois é! Porém, essas práticas não se consolidaram da noite para o dia. Ao contrário, foram sendo construídas e estruturadas conforme as experiências em projetos se acumulavam entre as equipes. Em nossos dias, o desafio do desenvolvimento de um produto de _software_ não pode ser enfrentado sem condutas estruturadas e padrões mínimos de procedimentos.

Esta primeira unidade será um dos passos para que você seja capaz de conhecer as principais metodologias de desenvolvimento de _software_, normas de qualidade e processos de teste de _software_.

Para esta unidade foi preparado conteúdo que vai colocar você diante dos tópicos iniciais da Engenharia de _Software_, apresentados na medida certa para proporcionar seu primeiro contato com o tema. Estudaremos juntos os conceitos iniciais da disciplina, seus paradigmas e objetivos, sempre com foco na sua preparação para transitar com naturalidade pelas novas metodologias de desenvolvimento e pelos padrões de qualidade que o desenvolvimento moderno impõe.

Os próximos parágrafos apresentam situação comum a muitas organizações que assumiram a missão de automatizar processos por meio de programas de computador. Tal situação dará base para nossa caminhada pelas demais unidades da disciplina.

Vamos iniciar pela seguinte situação: você é sócio-proprietário de uma startup de desenvolvimento de _software_, chamada _XAX-Sooft_. Um grande cliente, especializado em venda de games, solicitou um projeto de _software_ para cadastro de clientes por interesse, o que vai possibilitar contatos mais assertivos e direcionamentos seguros de campanhas.

Acontece que para atender esse cliente com a qualidade que ele demanda, mudanças nos processos de desenvolvimento da _XAX-Sooft_ deverão ser implementadas. Não há metodologia formal de desenvolvimento implantada na empresa e as atividades são executadas sem acompanhamento e validação.

Para que sua tarefa seja cumprida você deverá apresentar:

1. levantamento do cenário atual do processo de desenvolvimento utilizado na _XAX-Sooft_.
2. proposta de melhoria do processo de _software_ utilizado pela _XAXSooft_.
3. levantamentos dos requisitos do _software_ e esboço do projeto.
4. definição do processo de implantação do _software_.

Nas aulas seguintes você terá à disposição textos estruturados em formatação padronizada que o levarão a conhecer as motivações da existência da Engenharia de _Software_. Na “Situação-problema", as situações da realidade profissional serão problematizadas e, na sequência, será abordada a teorização que nos dará base para os exercícios e o desenvolvimento das outras situações do dia a dia que se seguirão.

Vale a pena, de fato, investir tempo em aplicação de metodologia? Temos feito a divisão correta das etapas de desenvolvimento de um produto de _software_? Ao aprofundar-se nos temas aqui abordados, você será capaz de responder a essas e outras tantas questões.

# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/bdcf0007-e1c4-4298-9c56-263eb9fa8143/original)](https://ampli-images.s3.amazonaws.com/production/bdcf0007-e1c4-4298-9c56-263eb9fa8143/original)

### **Qual é o foco da aula?**

Nesta aula, serão descritos conceitos, objetivos e paradigmas relacionados à Engenharia de _software_ que embasarão temas mais avançados e pavimentarão o caminho para metodologias mais adequadas ao cenário atual de demandas dos clientes.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer o conceito de engenharia de _software_;
- examinar os pilares da engenharia de _software_;
- explicar o que foi a crise do _software_.

**Situação-problema**

Nossa empresa _XAX-Sooft_ cresceu! Agora bons contratos são fechados e clientes importantes estão sendo conquistados.

Temendo a perda de controle sobre os projetos e buscando bom atendimento à demanda do cliente de venda de games, os dirigentes da _XAX-Sooft_ resolvem que os processos de desenvolvimento e o gerenciamento dos projetos devem ser repensados.

Após algum tempo de discussão, constatam que os processos de desenvolvimento que adotam são caóticos e que o início da solução passa pelo levantamento de como os procedimentos são executados atualmente.

Sua tarefa é fazer o levantamento dos procedimentos de desenvolvimento atuais adotado na _XAX-Sooft_. Utilize os conhecimentos que serão abordados nesta aula, principalmente os relacionados às características do período chamado “crise do _software_”.

Será que uma nova metodologia deve ser discutida com todos os envolvidos antes de sua adoção? Assumindo que a empresa hoje cumpre com a maioria dos prazos e tem clientes minimamente satisfeitos, qual o motivo de mudar o que está dando certo? Essas questões terão suas respostas direcionadas nas próximas aulas.

# **Conceito de Engenharia de software**

[![](https://ampli-images.s3.amazonaws.com/production/97d5f585-1168-4225-a8cc-e7f95e7595e1/original)](https://ampli-images.s3.amazonaws.com/production/97d5f585-1168-4225-a8cc-e7f95e7595e1/original)

Ensina Schach (2008), em sua obra “Engenharia de _software_: os paradigmas clássico e orientado a objetos”, que:

> “Engenharia de software é uma disciplina cujo objetivo é produzir software isento de falhas, entregue dentro do prazo e orçamentos previstos, e que atenda às necessidades do cliente. Além disso, o software deve ser fácil de ser modificado quando as necessidades dos usuários mudarem”.

Alternativamente, para uma melhor definição do conceito de Engenharia de _software_, faz-se necessária a explicação isolada dos termos que o compõem.

De forma genérica, pode-se definir _software_ como:

(i) instruções que, quando executadas, produzem a função desejada,

(ii) estruturas de dados que possibilitam que os programas manipulem a informação;

(iii) documentação relativa ao sistema.

Engenharia diz respeito ao projeto e manufatura, circunstâncias nas quais os requisitos e as especificações do produto assumem importância crítica na qualidade final do produto.

Trata-se da definição clássica de Engenharia. Por ser imaterial, um programa de computador não passa por um processo de manufatura como se conhece no meio industrial de produtos complexos. Fica claro também que, apesar da semelhança com a engenharia tradicional, a produção de programas de computador possui situações particulares.

A IEEE Computer Society (2004) define Engenharia de _software_ como:

> “A aplicação de uma abordagem sistemática, disciplinada e quantificável de desenvolvimento, operação e manutenção do software, além do estudo dessas abordagens".

Fica claro, então, que o objetivo da Engenharia de _Software_ é a entrega de produto de qualidade, respeitados os prazos e os limites de dispêndio de recursos humanos e financeiros.

______

**🔁 Assimile**

Por se tratar de assunto amplamente abordado na literatura, a Engenharia de _software_ acumulou várias definições durante seus anos de existência como disciplina. Vale a pena conhecer mais uma:

> “Engenharia de Software é a profissão dedicada a projetar, implementar e modificar software, de forma que ele seja de alta qualidade, a um custo razoável, manutenível e rápido de construir.“ (LAPLANTE, 2007, p. 39).

# **Pilares e categorias de software**

[![](https://ampli-images.s3.amazonaws.com/production/441ebbed-9f24-4dc7-8193-c5ee3ef8267e/original)](https://ampli-images.s3.amazonaws.com/production/441ebbed-9f24-4dc7-8193-c5ee3ef8267e/original)

Como toda disciplina, a nossa também apresenta aspectos que a norteiam, comumente referenciados como princípios ou paradigmas. Vale a menção de alguns deles:

- **abstração**: para resolver um problema, deve-se separar os aspectos que estão ligados a uma realidade particular, visando representá-lo em forma simplificada e geral.
- **formalidade**: significa seguir uma abordagem rigorosa e metódica para resolver um problema.
- **dividir para conquistar**: resolver um problema complexo dividindo-o em um conjunto de problemas menores e independentes que são mais fáceis de serem compreendidos e resolvidos.
- **organização hierárquica**: organizar os componentes de uma solução em uma estrutura hierárquica tipo árvore. Assim, a estrutura pode ser compreendida e construída nível por nível, cada novo nível com mais detalhes.
- **ocultação**: esconder as informações não essenciais. Permitir que o módulo "veja" apenas a informação necessária àquele módulo.
- **localização**: colocar juntos os itens relacionados logicamente (o usuário não pensa como o analista!).
- **integridade conceitual**: seguir uma filosofia e arquitetura de projeto coerentes.
- **completeza**: checar para garantir que nada foi omitido.

Agora que você já teve contato com os pilares da Engenharia de _Software_, vale a pena focar naquele que é seu produto final. Conheça algumas das principais categorias de _software_, classificadas segundo sua aplicação:

1. _**software**_ **básico**: apoio a outros programas. Forte interação com o hardware. Exemplos: compiladores, device drivers, componentes de sistema operacional.
2. _**software**_ **em tempo real**: trata-se de um tipo de _software_ que monitora eventos por meio de coleta e análise de dados, tais como temperatura, pressão, vazão, entre outros. Usa-se a expressão “tempo real” por conta da resposta imediata (um segundo ou menos) que o _software_ deve fornecer.
3. _**software**_ **comercial**: caracteriza-se pela manipulação de grande volume de dados e uso em aplicações comerciais. Exemplos: folha de pagamento, estoque, recursos humanos. Forte interação com banco de dados.
4. _**software**_ **científico**: algoritmos de processamento numérico. Usados na astronomia, mecânica e projeto auxiliado por computador.
5. _**software**_ **de computador pessoal**: forte interação com o ser humano. Deve ser fácil e amigável. Exemplos: Planilhas, editores de texto, browsers, entre outros.

______

**🔁 Assimile**

A maioria dos programas com os quais temos contato são de computador pessoal. Nesta categoria de programas podemos destacar ainda o _software_ on-line, que necessita de conexão com a internet para funcionar. Ele normalmente é executado em um computador distante fisicamente do usuário, mas usa a máquina local para apresentação das entradas e saídas de dados.

# **Crise do Software**

[![](https://ampli-images.s3.amazonaws.com/production/3d9c0953-ee06-457b-bd4d-63ff2aa57ad3/original)](https://ampli-images.s3.amazonaws.com/production/3d9c0953-ee06-457b-bd4d-63ff2aa57ad3/original)

Em algum momento da sua vida profissional você estará envolvido com o desenvolvimento de um ou mais desses tipos de programas de computador. Aliás, desenvolver _software_ é uma atividade que tem deixado de ser artesanal e empírica para se tornar sistemática e organizada. No entanto, logo em seus primeiros anos, a produção de _software_ enfrentou tempos turbulentos, nos quais a chance de insucesso nos projetos era grande.

Na década de 1960, alguns atores do processo de desenvolvimento de _software_ cunharam a expressão “Crise do _Software_“ na intenção de evidenciar o momento adverso que a atividade atravessava. Em seu sentido literal, crise indica estado de incerteza ou declínio e, de fato, esse era o retrato de um setor inapto a atender demanda crescente por produção de _software_, que entregava programas que não funcionavam corretamente, construídos por meio de processos falhos e que não podiam passar por manutenção facilmente. Além disso, a incerteza causada pela imprecisão nas estimativas de custo e prazo afetava a confiança das equipes e principalmente dos seus clientes.

A precária – e muitas vezes ignorada – comunicação entre cliente e equipe de desenvolvimento contribuía para que a qualidade do levantamento dos requisitos fosse perigosamente baixa, acarretando consequente incorreções no produto final.

O cenário era agravado pela inexistência de métricas que retornassem avaliações seguras – fossem qualitativas ou quantitativas – dos subprodutos gerados nas fases de requisitos, projeto, implementação e testes. Nas aulas seguintes trataremos em detalhes dessas fases.

Não havia, ainda, dados históricos de outros projetos que ajudassem nas estimativas para os projetos atuais e na adequada avaliação da eficácia da aplicação de uma ou outra metodologia no desenvolvimento. Quando, apesar das adversidades, o programa era entregue, o processo de implantação tendia a ser turbulento, já que raramente eram considerados os impactos que o novo sistema causaria na organização.

Treinamentos aos usuários após a implantação não era atividade prioritária e o fator humano era ignorado com frequência, gerando insatisfações nos funcionários impactados. Por fim, há que se considerar a dificuldade e o alto valor em se empreender manutenção nos produtos em funcionamento, normalmente ocasionados por projetos mal elaborados.

Estava claro que algo deveria ser feito. Ações que aprimorassem e dessem segurança ao processo de desenvolvimento deveriam ser tomadas. Sob pena de verem seu negócio naufragar, empreendedores de TI deveriam a todo custo entrar em sintonia com seus clientes, trazendo-os para dentro do processo e dando voz ativa a eles.

_____

**💭 Reflita**

Em 2002, uma empresa global de pesquisa em Tecnologia da Informação chamada Cutter Consortium, constatou que 78% das empresas de TI pesquisadas fizeram parte de ações judiciais motivadas por desavenças relacionadas a seus produtos.

Na maioria desses casos (67%), os clientes reclamavam que as funcionalidades entregues não correspondiam à suas demandas. Em outros tantos casos, a alegação era que a data prometida para entrega havia sido por várias vezes desrespeitada e, por fim, em menor quantidade, a reclamação se originava do fato de o sistema ser tão ruim que simplesmente se podia utilizá-lo.

Estarrecedor, não acha?

_____

**➕ Pesquise mais**

O texto “[_Uma breve história da Engenharia de Software_](https://github.com/DrWaleedAYousef/Teaching/blob/master/SoftwareEngineeringI/Wirth2008BriefHistorySWE.pdf)” foi publicado pelo renomado professor suíço Niklaus Wirth, em 2007.

_____

📝 **Exemplificando**

Certa equipe de desenvolvimento construiu um processador de texto. Ao planejar o menu da ferramenta, a funcionalidade de classificação por ordem alfabética acabou ficando no menu "_Layout_ de página". Tempo depois, a mesma equipe foi chamada a construir um sistema acadêmico. Para a fase de análise, a equipe escolheu a metodologia da Análise Estruturada e, para o projeto, a metodologia de Projeto Orientado a Objeto.

A Engenharia de _Software_ norteia-se por princípios que devem ser respeitados para que sua prática leve ao cumprimento de seus objetivos. No caso apresentado, dois desses princípios foram ignorados pela equipe de João.

Ao pensar no menu, a equipe não considerou que a localização dos elementos no programa final é de suma importância para que o usuário o utilize com desenvoltura. Quando um menu de programa é identificado como “_Layout_ de página”, não se espera que a funcionalidade de classificação por ordem alfabética esteja localizada.

No segundo projeto, a equipe simplesmente ignorou que o projeto deve respeitar o princípio da integridade conceitual ao não considerar a adoção de uma metodologia do início ao fim do desenvolvimento

_____

**💪 Faça você mesmo**

A fim de prepará-lo para as próximas aulas desta dsici, um breve exercício é proposto: se você recebesse a missão de construir o sistema de controle acadêmico de uma faculdade recém-aberta por um conhecido seu, por onde você começaria o desenvolvimento? Qual seria o seu primeiro passo? Responda em no máximo cinco linhas de texto.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Todos na _XAX-Sooft_ concordam que o momento é apropriado para a implantação de novos procedimentos. Nunca antes haviam se preocupado com a formalização de seus procedimentos, nem com a documentação relativa a eles. Nem sequer um treinamento foi disponibilizado à equipe até então. Objetivamente, o cenário descrito demanda quebra de paradigmas, com o consequente aumento do esforço empreendido que toda mudança acarreta.

No entanto, as coisas podem começar a ser mudadas por meio do levantamento da situação atual. Este levantamento deve responder às seguintes questões:

Como as funções do sistema a ser desenvolvido são descobertas? Como são coletadas? Quem as informa?

O que a equipe faz depois que entende o que deve ser feito? Inicia imediatamente a programação?

Durante o desenvolvimento do programa, o cliente é novamente chamado em caso de dúvida da equipe? Com o sistema pronto, a equipe simplesmente o disponibiliza ao cliente? Treinamentos são previstos?

Não lhe parece, que estamos diante de uma situação em que os projetos são desenvolvidos unicamente ao sabor da experiência da equipe? Caso um membro da equipe deixe a empresa, seu substituto será capaz de continuar seu trabalho da forma como era feito?

Pois é, a situação demanda providências e você é chamado a tomá-las.

O levantamento dos procedimentos de desenvolvimento atuais adotados na _XAX-Sooft_ apontou que:

1. quando a equipe de desenvolvimento recebe um novo projeto, um de seus membros – normalmente o que se encontra com carga de trabalho menor no momento – é destacado para visitar o cliente e reunir-se com ele. Durante a reunião, todos os requisitos do sistema são discutidos e anotados. Em suma, a única fonte dos requisitos é o cliente e a coleta que se faz pela anotação em uma folha de papel.
2. uma vez coletados os requisitos, o membro da equipe que o fez os repassa a dois ou mais colegas para que sejam imediatamente traduzidos em uma linguagem de programação. A quantidade de profissionais que cuidarão do projeto e as tecnologias a serem utilizadas são determinadas por um dos sócios da _XAX-Sooft_.
3. caso ocorram dúvidas durante o desenvolvimento da solução, uma ligação ou alguns e-mails enviados ao cliente servirão como meios para saná-las. Caso o cliente não seja encontrado ou não seja capaz de resolver o questionamento da equipe, o caso é decidido pelo programador mesmo. Há consenso na equipe que, embora o cliente não tenha solicitado determinadas funções, elas serão desenvolvidas por precaução e para o caso de serem solicitadas no futuro.
4. terminado o desenvolvimento, agenda-se a implantação do sistema e a equipe aguarda novos contatos do cliente.

_____

**⚠️ Atenção**

Nosso objetivo, no momento, é iniciar a colocação da nossa empresa no caminho da criação de produtos de qualidade e que estejam perfeitamente adequados ao seu propósito. Não nos cabe, por ora, fornecer a solução completa para o caso, pois isso demandaria outros conhecimentos que ainda não temos.

______

**🔁 Assimile**

A criação de conteúdos compartilhados tem crescido nas empresas. Ferramentas do pacote Office e do Google possuem funcionalidades que permitem a criação de wiki corporativa.