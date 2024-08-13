# **Modelos e etapas do processo de software**

[![](https://ampli-images.s3.amazonaws.com/production/251e6d1f-a4be-41c2-83f2-ecbc921e8f86/original)](https://ampli-images.s3.amazonaws.com/production/251e6d1f-a4be-41c2-83f2-ecbc921e8f86/original)

### **Qual é o foco da aula?**

Nesta aula, caminharemos juntos pelos detalhes das fases de requisitos e de projeto, de modo a prepará-lo para aplicar seus conhecimentos.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer quais são os requisitos do _software_;
- analisar detalhadamente os requisitos;
- examinar os aspectos fundamentais de um projeto.

**Situação-problema**

Para iniciarmos a terceira aula desta unidade, vale uma breve retomada de como a situação da _XAX-Sooft_ tem evoluído. Ao receber demanda de grande cliente especializado em venda de games, a empresa viu-se na necessidade de deixar o modo artesanal de produção de _software_ e buscar aplicação de metodologia formal. Como primeiro passo, fez levantamento da situação atual e, ato contínuo, esboçou processo uniforme de desenvolvimento.

Então, na condição de ator do processo, chegou o momento de você iniciar trabalho relacionado aos requisitos e de esboçar o projeto do _software_, com base nos estudos desenvolvidos nesta aula e com base no processo previamente definido.

Na resolução dessa atividade, esperamos que você aplique as práticas adequadas para levantamento dos requisitos e para sua classificação. Será necessário também esboçar os módulos que comporão o sistema. Ao final, você deverá gerar documento de especificação de requisitos devidamente revisado e os módulos do sistema.

Você pode observar que sem a competente descoberta, análise, documentação e conferência dos requisitos, a perfeita adequação do produto ao seu propósito ficará comprometida. Da mesma forma, sem a criação de desenho correto da solução, a implementação será feita com base em dados incorretos. Pois é, esses desafios nos remetem a outro de igual importância: você deverá dominar os conceitos de requisitos e de projeto de _software_, que formam justamente os objetivos de aprendizagem desta aula. O entendimento teórico e a habilidade prática para utilizar as diversas formas de levantamento dos requisitos farão toda a diferença no correto cumprimento de parte da sua tarefa. Da mesma forma, a capacidade de sintetizar os requisitos em uma solução de implementação viável garantirá seu sucesso.

Não podemos nos esquecer que o estudo dos conteúdos desta primeira unidade tem construído, passo a passo, sua capacidade de avaliar e adequar a metodologia tradicional de desenvolvimento às situações que certamente encontrará em seu futuro profissional.

Seu crescimento nesse tema lhe possibilitará, inclusive, comparar essa metodologia com outras mais atuais, além de capacitá-lo no entendimento das normas de qualidade e dos processos de teste de _software_.

O desafio está novamente lançado. Seja bem-vindo e vamos adiante!

# **Requisitos de software**

[![](https://ampli-images.s3.amazonaws.com/production/7489b641-ff48-474c-b096-8c715b1e9166/original)](https://ampli-images.s3.amazonaws.com/production/7489b641-ff48-474c-b096-8c715b1e9166/original)

É importante você observar que a abordagem dos requisitos e a elaboração do projeto constituem, normalmente, as duas primeiras etapas dos modelos de _software_ tradicionais. Não por acaso, são tidas também como as mais críticas no processo.

Roger Pressman, em sua clássica obra “Engenharia de _Software_”, destaca que não importa o quão bem codificado seja, mas um programa mal analisado e mal projetado desapontará o usuário e trará aborrecimentos ao desenvolvedor (PRESSMAN, 1995).

A área de requisitos de _software_ preocupa-se com o levantamento, análise, especificação e validação das propriedades que devem ser apresentadas para resolver tarefas relacionadas ao _software_ em desenvolvimento.

Requisitos são a expressão mais detalhada sobre aquilo de que o usuário ou cliente precisa em termos de um produto de _software_ (WAZLAWICK, 2013).

Além das funcionalidades, eles relacionam-se também aos objetivos, restrições e padrões do sistema. Em outras palavras, os requisitos de _software_ expressam as necessidades e restrições colocadas num produto de _software_ que contribuem para a solução de algum problema do mundo real. São subetapas da fase de requisitos, vamos conhecê-las!

# **Levantamento e análise de requisitos**

[![](https://ampli-images.s3.amazonaws.com/production/40d3dc79-fb06-4722-a942-d74a6dbc5e6a/original)](https://ampli-images.s3.amazonaws.com/production/40d3dc79-fb06-4722-a942-d74a6dbc5e6a/original)

Schach (2008) aponta ações que devem nortear o trabalho de levantamento de requisitos. A primeira é determinar o que o cliente precisa, em vez do que o cliente quer. No entanto, é muito comum que os clientes não saibam do que precisam ou que tenham dificuldade em expressá-lo.

É necessário também que o grupo destacado conheça o campo de aplicação, ou seja, a área geral em que o _software_ será aplicado. Incluem exemplos de campos de aplicação o setor bancário, o comércio varejista e o setor acadêmico, entre tantos outros.

Por fim, é indispensável que o engenheiro de requisitos conheça as regras (ou modelo) de negócios do cliente. Trata-se da descrição dos processos que compõem o negócio da organização.

**Técnicas de levantamento de requisitos**

O levantamento de requisitos é atividade essencialmente humana, que requer habilidade em trabalhar com especialistas humanos e com o conhecimento tácito, que é trivial para quem conhece a informação, mas não é trivial para quem procura obtê-la.

O documento “_Guide to the Software Engineering Body of Knowledge_” (IEEE, 2004) aborda algumas técnicas que facilitam esse trabalho.

**Entrevista**

Antes da sua aplicação, a entrevista deve ser planejada. Seus objetivos devem ser fixados, seu local e roteiro definidos e os entrevistados criteriosamente escolhidos.

A interação entre entrevistado (especialista do conhecimento) e entrevistador (engenheiro de requisitos) deve buscar revelar conceitos, objetos e a organização do domínio do problema, além de buscar soluções ou projeções de soluções que comporão o domínio da solução (SCHACH, 2008).

______

**🔁 Assimile**

As entrevistas mais usuais são as tutoriais, informais e estruturadas. Nas entrevistas tutoriais, o entrevistado fica no comando, praticamente lecionando sobre um determinado assunto.

Nas entrevistas informais ou não estruturadas, o entrevistador age espontaneamente, perguntando ao entrevistado, sem obedecer a nenhuma organização. Já as entrevistas estruturadas são preparadas pelo entrevistador, que define previamente o andamento do procedimento de aquisição de conhecimento.

______

**Aplicação de questionário**

O questionário geralmente é aplicado em formulário distribuído para os futuros usuários do sistema. Seu elaborador deve utilizar questões diretas e objetivas, dispostas preferencialmente na mesma ordem para todos os participantes e que consigam extrair deles respostas sobre o procedimento atual adotado (SCHACH, 2008).

Análise de documentos, observações pessoais e reuniões estruturadas são outras três técnicas utilizadas na fase de levantamento de requisitos.

Concluída a fase de levantamento, tem início a análise de requisitos. Aqui os requisitos serão analisados e classificados e, como resultado, serão divididos principalmente em requisitos funcionais e não funcionais.

Os primeiros descrevem as funções que o _software_ irá executar. Por exemplo, formatar algum texto ou imprimir um relatório de vendas. Os requisitos funcionais definem a funcionalidade que o _software_ deve prover com o objetivo de capacitar os usuários a realizar suas tarefas. Eles descrevem o comportamento planejado do sistema, podendo ser expressos como os serviços, tarefas ou as funções que o sistema irá executar.

Requisitos não funcionais são aqueles que restringem a solução de um problema. Não se referem às funções específicas do sistema, mas sim a propriedades, tais como tempo de resposta, requisitos de armazenamento, restrições de entrada e saída, memória, entre outras.

# **Especificação dos requisitos de software**

[![](https://ampli-images.s3.amazonaws.com/production/13c4fb84-afd2-40e8-9c2a-50536313bc2a/original)](https://ampli-images.s3.amazonaws.com/production/13c4fb84-afd2-40e8-9c2a-50536313bc2a/original)

Refere-se a produção de um documento contendo os requisitos levantados e analisados, que podem ser sistematicamente revistos, avaliados e aprovados. Ele estabelece um contrato entre cliente e desenvolvedor. Geralmente escrito em linguagem natural, forma base realista para estimativas de custos, riscos e cronograma.

Uma boa especificação de requisitos de _software_ pode propiciar diversos benefícios aos clientes e demais envolvidos no projeto, a saber:

1. estabelece a base para a concordância entre clientes e fornecedores, naquilo que o _software_ deve produzir;
2. reduz o esforço para o desenvolvimento. Uma revisão cuidadosa dos requisitos na ERS pode trazer à tona omissões e falhas em fases iniciais no ciclo de desenvolvimento quando esses problemas são mais fáceis de corrigir;
3. fornece base para estimativa de custos e agendas. A descrição do produto a ser desenvolvido é uma base realista para a estimativa dos custos do projeto e pode ser usada como referência de preço do produto;
4. fornece uma linha de base para validação e verificação. As organizações podem desenvolver seus planos de validação e verificação de forma muito mais produtiva a partir de uma boa ERS (IEEE, 2004).

______

**🔁 Assimile**

A IEEE padronizou o formato do ERS por meio da norma IEEE 830:1998, substituída posteriormente pela ISO/IEC/IEEE 29148:2011.

# **Validação dos requisitos e projeto de software**

[![](https://ampli-images.s3.amazonaws.com/production/08e836b0-e86e-4023-9699-1c635acab981/original)](https://ampli-images.s3.amazonaws.com/production/08e836b0-e86e-4023-9699-1c635acab981/original)

Como última etapa da fase do processo, a **validação** deve incidir sobre o documento de especificação.

Validação: "Aquilo que fiz é o que deveria ser feito? Aquilo que fiz corresponde aos requisitos?"

A validação serve para assegurar que o engenheiro compreendeu os requisitos e se estes são compreensíveis, consistentes e completos. No processo de validação a participação do cliente é fundamental. A revisão é feita por profissionais designados para assegurar que não há no documento falta de clareza, sentido dúbio e desvio dos padrões.

Uma maneira eficaz de validar os requisitos é pela prototipação. Trata-se da criação de versão simplificada de determinadas funções do sistema, indicada para capturar a real compreensão do engenheiro em relação aos requisitos levantados. O comportamento de uma interface de usuário também pode ser mais bem compreendida através de um protótipo (IEEE, 2004).

O **projeto** é o primeiro passo da fase de desenvolvimento de qualquer produto ou sistema de engenharia. Sua meta é produzir modelo ou representação do produto a ser construído. Para tanto, o projetista deve lançar mão de sua experiência, intuição e metodologias consagradas. Modelos ou representações podem ser analisados quanto a sua qualidade e são base para as etapas de codificação, teste, validação e manutenção (PRESSMAN, 1995).

Projeto é o processo pelo qual os requisitos são traduzidos numa representação do _software_.

A avaliação da qualidade de um projeto implica que ele deve exibir uma organização hierárquica do _software_, deve ser modular e que deve haver distinção entre dados e procedimentos.

O nível de detalhamento deve ser suficiente para permitir sua realização física e, de acordo com o modelo de processo tradicional, o projeto se inicia depois de levantados, analisados e especificados os requisitos.

# **Aspectos fundamentais de projeto**

[![](https://ampli-images.s3.amazonaws.com/production/7ea0f2f2-0c5f-4c2e-b473-ad35c8e20c5b/original)](https://ampli-images.s3.amazonaws.com/production/7ea0f2f2-0c5f-4c2e-b473-ad35c8e20c5b/original)

Pressman (1995) destaca os aspectos fundamentais de um projeto de _software_:

1. **abstração**: solução modular leva a vários níveis de abstração. Abstrair é concentrar-se em certos aspectos relevantes ao ambiente do problema. Cada passo da Engenharia de _Software_ diminui o nível de abstração em direção à solução do problema. O nível mais baixo de abstração é o código-fonte. A abstração procedimental refere-se à sequência de instruções com funções específicas.

_____

**📝 Exemplificando**

Como exemplo, têm-se dois níveis de abstração procedimental para programa de esboço de CAD:

- **abstração 1** - O _software_ terá uma interface gráfica que possibilitará acesso a função de desenhos de linhas retas e curvas. Os desenhos serão armazenados numa pasta de desenhos.
- **abstração 2** - Tarefas do _software_ CAD:

início tarefa

interação com o usuário

criação de desenhos

gerenciamento de arquivos de desenho

fim tarefa

_____

1. **abstração de dados**: coleção de dados que descreve um objeto. Exemplo: contracheque contém o nome do beneficiado, quantia bruta, imposto de renda, contribuição sindical (conjunto de dados). Assim, referencia-se o conjunto de dados pelo nome da abstração (contracheque).
2. **modularidade**: divisão do _software_ em componentes chamados módulos. Permite a administração intelectual do _software_, já que um grande _software_ monolítico (composto por apenas um módulo) é praticamente incompreensível. O desafio do projetista, no entanto, é dimensionar a quantidade de módulos a serem construídos. Quantitativamente, há que se comparar o esforço em se construir interface para um módulo comparado ao benefício em poder contar com ele.

Qualitativamente, a noção de qualidade passa pelos conceitos de coesão e acoplamento. De forma simplificada, coesão é o grau de interação dentro de um módulo e o acoplamento é o grau de interação entre dois módulos.

1. **procedimento de** _**software**_: focaliza os detalhes de processamento de cada módulo da hierarquia. O procedimento oferece especificação precisa do processamento do módulo.

_____

**📝 Exemplificando**

A classificação dos requisitos não se resume apenas na separação entre funcionais e não funcionais. Requisitos voláteis, estáveis, de usuário, de sistema e inversos são outros tipos de classificação. Imagine que você tenha recebido a incumbência de classificar requisitos apresentados da seguinte maneira:

1. o sistema deve ser capaz de cadastrar um cliente;
2. o sistema não emite nota fiscal;
3. o cálculo da taxa de juros varia de acordo com a lei vigente.

Tendo como base os tipos estudados, classificamos o primeiro como um requisito funcional puro. O segundo se trata de requisito inverso, justamente aquele que não deve ocorrer no produto. Por último, o cálculo da taxa de juros não deixa de ser um requisito funcional, mas que também deve ser subclassificado como um requisito volátil, pois varia conforme evento externo.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/23c096b0-f980-444a-8e0d-09b31c229785/original)](https://ampli-images.s3.amazonaws.com/production/23c096b0-f980-444a-8e0d-09b31c229785/original)

Na condição de dirigente da _XAX-Sooft_, você sabe que a atenção empreendida nas fases de requisitos e projeto será fundamental para a continuidade do trabalho. O cliente espera que tudo sobre o seu programa de manutenção de clientes seja descoberto e documentado nesta etapa e frustrá-lo não seria boa ideia.

O processo se inicia pela tarefa de descoberta dos requisitos que, uma vez terminada, possibilitará que você classifique os requisitos em funcionais e não funcionais. Depois disso, você deverá criar documento de especificação de requisitos, que deverá ser devidamente revisado.

Tal documento é, afinal, um dos objetivos finais dessa tarefa. Findada essa fase e, com base nos requisitos funcionais, você deverá descrever os principais módulos do sistema.

O documento de especificação de requisitos poderá ter o seguinte conteúdo:

1. **breve descrição do sistema**: o sistema a ser desenvolvido deverá possibilitar a manutenção dos clientes da empresa, viabilizando o agrupamento por área de interesse nos games por ela comercializados, o que deverá possibilitar contatos mais assertivos e direcionamentos seguros de campanhas.
2. **requisitos funcionais**: (i) em relação aos novos clientes, o sistema deverá permitir o cadastramento, alteração de dados, exclusão e consulta aos seus detalhes. (ii) O sistema deverá emitir relatórios das preferências dos clientes por tipo de games. (iii) O sistema deverá enviar mensagens de e-mails à sua base de clientes com lançamentos e atualizações de games.
3. **requisitos não funcionais**: (i) o sistema deverá fazer uso da base de clientes já mantida pelo sistema de vendas. (ii) O sistema deverá ser desenvolvido para a plataforma web.
4. **considerações gerais de projeto**: (i) fica decidido que, pelo perfil do cliente e do produto a ser gerado, serão utilizadas as técnicas de reuniões e de aplicação de questionários para a descoberta dos requisitos. (ii) O cliente irá indicar seus representantes para atuarem como fontes de informações.

Para efeito de esboço do projeto do _software_, deverão ser previstos os módulos de manutenção do cliente, emissão de relatório de preferências de clientes por tipo de games e módulo de envio de mensagens via e-mail.

_____

**➕ Pesquise mais**

Você poderá incluir mais itens em sua especificação, tais como a descrição do modelo de negócio da empresa, requisitos de _hardware_ do novo sistema, layouts de tela e descrição das funções em linguagem natural. Pode ser uma boa fonte de consulta é o [SAT](https://portal.fazenda.sp.gov.br/servicos/sat/Paginas/Sobre.aspx).

_____

**⚠️ Atenção**

O documento de especificação de requisitos pode se tornar base para contrato entre o desenvolvedor e o cliente, o que reforça a necessidade de cuidado em sua elaboração.