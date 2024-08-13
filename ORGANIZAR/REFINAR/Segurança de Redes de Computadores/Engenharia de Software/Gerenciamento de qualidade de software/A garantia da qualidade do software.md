# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/05c640f3-9737-44c8-8095-b1f773461233/original)](https://ampli-images.s3.amazonaws.com/production/05c640f3-9737-44c8-8095-b1f773461233/original)

### **Qual é o foco da aula?**

Nesta aula, você terá compreensão dos mecanismos envolvidos num processo de qualidade que passa agora pela Garantia da Qualidade do _Software_ (SQA) e pelo estudo mais aprofundado dos fatores que exercem influência sobre a qualidade de um produto de _software_.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- identificar que torna um programa bom;
- examinar quais são os parâmetros de qualidade;
- esclarecer os fatores que incluenciam na qualidade.

**Situação-problema**

Olá, estudante! Em nossa última aula, tivemos a oportunidade de fazer o primeiro contato com um assunto que nos acompanhará até o final do curso: a qualidade relacionada ao produto de _software_, ou seja, a um programa.

Mesmo depois da introdução ao tema, muitas questões ainda ficaram para serem respondidas. Por ora, as que mais nos interessam são as seguintes: o que torna o programa um bom programa? Quais são os parâmetros de qualidade? O entendimento da importância desse tema é bem fácil de ser alcançado. Basta você considerar que, se a dependência das organizações tem aumentado em relação ao uso de _software_, é de se esperar que a exigência sobre a qualidade dos produtos tenha aumentado na mesma proporção.

A _XAX-Sooft_, claro, não deixará de dispensar atenção adequada a essa demanda. Seu corpo gerencial sabe que a implantação de estratégia de qualidade não é apenas uma opção a ser cogitada, mas uma ação necessária à sua própria sobrevivência. Visando a adoção de procedimento formal de qualidade, você foi chamado a ser o responsável por dar início ao processo de mudança, levantando e relatando o que de efetivo tem sido feito em prol da excelência dos programas criados pela empresa.

Com esse diagnóstico em mãos, o próximo passo será realizar a apuração do nível dos indicadores de qualidade dos programas. Para que esse desafio seja superado com a excelência de sempre, você terá à disposição na aula o conteúdo sobre os fatores que afetam a qualidade de um produto e os procedimentos de garantia da qualidade de um _software_.

Por meio deles, você poderá criar um relatório contendo o nível em que se encontra cada um dos fatores que afetam a qualidade dos produtos da _XAX-Sooft_. Por meio dessa prática, você desenvolverá competência para identificar, uma a uma, as características a serem aprimoradas em um programa, meio pelo qual será possível torná-lo integralmente adequado ao seu propósito, e dessa forma, poderá conhecer e conduzir processos de qualidade de _software_. Eis o desafio.

Bom trabalho!

# **Garantia da Qualidade de Software (SQA)**

[![](https://ampli-images.s3.amazonaws.com/production/7adc0662-5cd0-4e5a-8aa2-0dc0f5abf78d/original)](https://ampli-images.s3.amazonaws.com/production/7adc0662-5cd0-4e5a-8aa2-0dc0f5abf78d/original)

Na aula anterior, foram discutidos conceitos e temas introdutórios da qualidade, indispensáveis para a formação da sua percepção sobre o tema.

Nos próximos parágrafos, estudaremos mais sobre Garantia da Qualidade do _Software_ (SQA) e fatores que influenciam a qualidade do _software_, serão abordados de maneira objetiva e dirigida ao melhor aproveitamento do tema para fins de torná-lo apto a transformar o desafio e as questões propostas em missões cumpridas.

Uma definição aceitável para a SQA (_Software Quality Assurance_) é expressa como:

> "padrão planejado e sistemático de ações que são exigidas para garantir a qualidade do software” (PRESSMAN, 1995, p. 733).

Em outras palavras, são as providências tomadas pela equipe para assegurar a qualidade do seu produto, de maneira vinculada ao processo que o cria. Como a abrangência temporal de tais providências se estende das fases iniciais do processo até a finalização do _software_, é esperado que a responsabilidade das equipes do projeto e demais envolvidos também seja extensa. Por exemplo, os engenheiros de _software_, o profissional que gerencia o projeto, o grupo de SQA e o próprio cliente, todos eles são responsáveis pela garantia da qualidade.

**Atividades SQA**

A definição de SQA inclui a expressão “padrão planejado e sistemático de ações”, não é mesmo? Pois bem, vamos então às ações.

Assegurar a qualidade de um _software_ envolve algumas tarefas, três das quais são descritas na sequência (PRESSMAN, 1995):

- **aplicação de métodos técnicos**: a SQA começa a ser aplicada desde a especificação e o desenho do sistema. Uma especificação malfeita – ou uma história mal escrita pelo cliente ou mal interpretada pela equipe – certamente irão comprometer a qualidade do produto final. Assim que uma especificação, protótipo ou release de um sistema tiverem sido criados, será apropriado avaliá-los quanto à qualidade.
- **realização de revisões técnicas formais**: esta é a atividade central no contexto da avaliação da qualidade de um produto. Uma revisão técnica formal é um encontro no qual uma equipe (de 3 a 5 pessoas, normalmente) destacada para o trabalho, concentra-se na busca por problemas de qualidade no produto ou, mais comumente, numa parte específica dele. Elas são aplicadas em momentos variados do processo e são também usualmente referenciadas como walkthrough (passo a passo). Se você é fã de games, então já ouviu ou leu essa expressão.
- **atividades de teste de** _**software**_: por melhor que seja sua técnica, por maior que seja sua capacidade de fazer bons programas e por mais que você siga uma metodologia, submeter seu programa a um processo de teste nunca sairá de moda. O motivo é simples: errar é humano.

O teste é uma atividade desempenhada para avaliar a qualidade do produto e para sua melhoria, por meio da identificação de defeitos e problemas. O teste de _software_ consiste na verificação dinâmica do comportamento de um programa em um conjunto finito de casos de teste, adequadamente selecionado a partir de um número geralmente infinito de execuções do programa (SWEBOK, 2004).

Parece complicado? Trataremos aqui apenas de alguns elementos essenciais do teste.

O processo de teste envolve quatro etapas: planejamento, projeto de casos de teste, execução e avaliação dos resultados, que devem ser conduzidas ao longo de todo o processo de desenvolvimento (ROCHA; MALDONADO; WEBER, 2001). Testar, não se trata, portanto, de vasculhar o código, linha por linha procurando falhas no programa. Tampouco é executar o programa algumas vezes procurando por erros.

# **Fatores que influenciam na qualidade do software**

[![](https://ampli-images.s3.amazonaws.com/production/173277ac-f5cd-4b76-ac72-6969c261cae7/original)](https://ampli-images.s3.amazonaws.com/production/173277ac-f5cd-4b76-ac72-6969c261cae7/original)

Já que temos tratado de processos formais de qualidade na construção do nosso conhecimento sobre o tema, nada mais apropriado do que a busca por um modelo de qualidade consagrado para definirmos as características desejáveis em um programa.

O modelo de qualidade ISO/IEC 25010:2011 estabelece um conjunto de oito características internas e externas de um _software_, divididas em outras tantas subcaracterísticas. Para facilitar a compreensão global da norma e facilitar sua síntese, a tabela abaixo apresenta tais características de qualidade, separadas entre próprias do produto e próprias do uso, conforme será explicado na sequência.

[![](https://ampli-images.s3.amazonaws.com/production/acab256d-b3b6-4a51-ab65-2aa353fb0d8d/original)](https://ampli-images.s3.amazonaws.com/production/acab256d-b3b6-4a51-ab65-2aa353fb0d8d/original)

[![](https://ampli-images.s3.amazonaws.com/production/9d930843-e373-4190-ae5d-f04278ae6f4b/original)](https://ampli-images.s3.amazonaws.com/production/9d930843-e373-4190-ae5d-f04278ae6f4b/original)

Modelo de qualidade da ISO 25010:2011. Fonte: Wazlawick (2013, p. 233).

Os parâmetros de qualidade normalmente são segmentados entre os que possuem mais afinidade com o processo, com o produto percebido pelo usuário ou com o produto sob o ponto de vista da equipe. As medidas de qualidade internas, por exemplo, servem para avaliar aspectos que usualmente são percebidos apenas pelos desenvolvedores. A capacidade de manutenção e a facilidade em se aplicar testes são bons exemplos dessas medidas.

As medidas de qualidade externas alcançam características avaliadas pela equipe do ponto de vista do usuário. Por exemplo, a eficiência e capacidade de operação de um programa.

O modelo ISO/IEC 25010:2011, cujas características foram resumidas na tabela acima, agregou as características internas e externas num único grupo e o chamou de **características do produto**. Elas podem ser avaliadas no ambiente de desenvolvimento, ao passo que as características do _**software**_ **em uso** podem apenas ser avaliadas durante o efetivo uso do sistema.

Parece bastante desafiador construir um produto que tenha boa adequação a todas essas características, não acha?

_____

**➕ Pesquise mais**

A ISO (Organização Internacional para Padronização ou Organização Internacional de Normalização) é uma organização independente e não governamental, presente em 162 países. Por meio de seus membros, ela desenvolve padrões internacionais aplicáveis em diversas áreas da atividade humana. Pesquise mais sobre a ISO em seu [site oficial](https://www.iso.org/about-us.html).

# **Características de qualidade**

[![](https://ampli-images.s3.amazonaws.com/production/2f8bb345-8634-47bb-ad7e-3cf786aa4b47/original)](https://ampli-images.s3.amazonaws.com/production/2f8bb345-8634-47bb-ad7e-3cf786aa4b47/original)

Para que você possa adquirir preparo para superar o desafio proposto, vale conhecer melhor algumas das características de qualidade mencionadas na tabela.

1. **adequação funcional**: antes conhecida como funcionalidade apenas; ela se refere à existência de um conjunto de funções que satisfazem às necessidades previamente estabelecidas, quando o produto é usado sob condições específicas. Duas de suas subcaracterísticas são a Completude Funcional (o _software_ apresenta todas as funções necessárias ao usuário?) e a Corretude Funcional ou Acurácia (o _software_ gera dados e consultas corretos segundo o que foi definido?) (WAZLAWICK, 2013).
2. **confiabilidade**: se um _software_ é capaz de manter comportamento consistente com o que se espera dele ao longo do tempo, então ele pode ser considerado confiável. A confiabilidade tem a ver com o funcionamento do programa em situações incomuns. Ela pode ser medida diretamente e estimada usando-se dados históricos e de desenvolvimento, ou seja, um computador poderá ser considerado livre de falhas quando não tiver alguma incidência em um determinado ambiente e num determinado período (MUSA et al., 1987 apud PRESSMAN, 1995). Desta definição, o que ainda não temos claro é o que significa falha. Quando tratarmos de teste de _software_ com mais detalhes, esse conceito será abordado.

Vale aqui também destacar duas de suas subcaracterísticas: a Disponibilidade (avalia o quanto o _software_ está operacional e livre para uso quando necessário) e a Tolerância a Falhas (avalia a forma como o _software_ reage em situação anormal).

_____

**💭 Reflita**

Qual é o real interesse de um usuário? Quando ele pensa em qualidade do _software_, em geral, ele se lembra da confiabilidade. No caso de o produto já ser relativamente confiável, a usabilidade é que fará diferença nele.

_____

3. **usabilidade**: de forma simplificada, podemos entender essa característica como a facilidade em se usar um programa, do ponto de vista do usuário. Em linhas gerais, o programa é fácil de usar se ele é (REISS, 2012):

- funcional – ele realmente funciona? responsivo – ele me fornece respostas adequadas? ergonômico – eu posso facilmente ver, clicar, arrastar e girar as coisas?conveniente – tudo está bem onde eu preciso que esteja? “À prova de tolos” – o projetista me ajuda a não cometer erros ou quebrar coisas?

A usabilidade também apresenta subcaracterísticas, incluindo (WAZLAWICK, 2005):

- operabilidade – o produto é fácil de usar e controlar?proteção contra erro do usuário – o programa consegue evitar que o usuário cometa erros? acessibilidade – avalia o grau em que o produto foi projetado para atender usuários com necessidades especiais.

______

**🔁 Assimile**

> “Não é possível conceber um processo de garantia de qualidade de um software sem integrá-lo com o ciclo de desenvolvimento de software.” (BARTIÉ, 2002, p. 35)

______

4. **segurança**: se um programa consegue proteger os dados e as funções de acessos não autorizados, então ele tem um bom nível de segurança. Algumas de suas subcaracterísticas devem ser destacadas. Entre elas:

- Confidencialidade – mede o grau em que os dados e funções ficam disponíveis para quem, de fato, tem autorização para acessá-los; Rastreabilidade de uso – mede o grau em que as ações realizadas por uma pessoa ou por um sistema podem ser rastreadas de forma a ser efetivamente comprovado que, de fato, foi essa pessoa ou sistema que realizou tais ações.

5. **capacidade de manutenção**: trata de uma característica que atrai interesse direto apenas da equipe de desenvolvimento, já que não afeta a percepção do usuário em relação ao sistema. Como você certamente já inferiu, trata-se da capacidade do sistema em passar por manutenção. Assim como todas as outras características apresentadas, essa também conta com divisões. Vamos a elas:

- modularidade – o sistema é bem dividido em módulos? Mudanças em um dos módulos deve causar mínimo impacto nos outros.reusabilidade – há partes do sistema que podem ser usadas na construção de outro sistema? analisabilidade – o sistema permite que se faça depuração com facilidade?

_____

**📝 Exemplificando**

Ainda em dúvida sobre a importância da qualidade em um produto? Em 4 de junho de 1996, o Foguete Ariane 5, construído pela empreiteira _EADS SPACE Transportation_, explodiu 37 segundos após seu lançamento. A comissão responsável pela apuração dos fatos concluiu que houve erro no Sistema Referencial Inercial (SRI). Do relatório, consta o seguinte: “A anomalia interna de _software_ do SRI ocorreu durante a execução de uma conversão de dados de um número de 64 bits em ponto flutuante para um inteiro de 16 bits com sinal. O valor do número em ponto flutuante era maior do que poderia ser representado pelo inteiro de 16 bits com sinal. O resultado foi um operando inválido. A instrução de conversão de dados não estava protegida contra erros de operando”.

_____

No âmbito das características de qualidade do _software_ em uso, vale destacar (WAZLAWICK, 2013):

1. **efetividade**: capacidade que o produto tem de proporcionar ao cliente o atingimento de seus objetivos de negócio.
2. **satisfação**: capacidade que o produto tem de satisfazer o cliente em ambiente de uso. Pode ser dividida em Utilidade, Prazer, Conforto e Confiança.
3. **uso sem riscos**: o uso do _software_ não pode implicar riscos para pessoas, negócios ou ambiente. Divide-se em mitigação do risco econômico, mitigação do risco ambiental e mitigação do risco à saúde e segurança.

_____

**💪 Faça você mesmo**

O método Cleanroom (sala limpa) é uma maneira bastante difundida de se desenvolver _softwares_ com qualidade. O método foi publicado pela primeira vez em 1987 por Mills, Dyer e Linger, e tem como princípio básico que os programas devem ser vistos como regras para funções ou relações matemáticas. A atividade aqui proposta é a criação de um relatório de uma página contendo os princípios básicos do modelo. Vale a pena conhecê-lo.

_____

Na sequência, nosso desafio será retomado e uma solução viável para ele será discutida.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

Os ventos da mudança passaram novamente pela _XAX-Sooft_ carregando o desejo – e a real necessidade – de implantação de procedimento formal de qualidade na empresa. A primeira providência tomada foi o levantamento do que já tem sido feito em prol da qualidade. Convenhamos, nada melhor que iniciar uma mudança entendendo como as coisas funcionam atualmente.

No entanto, apenas essa providência não basta. Mesmo que em pequenos passos, a implantação da qualidade demanda ações contínuas, tanto processuais como culturais. Ela requer a conscientização de que sempre haverá por onde melhorar um produto ou um processo e que a excelência é um bem que, embora intangível, produz efeitos palpáveis e duradouros no crescimento e na boa imagem da empresa.

Pois bem, o desafio agora é tratar da avaliação dos fatores que afetam a qualidade dos produtos da _XAX-Sooft_. Com base no conteúdo estudado nesta aula, você deve produzir relatório contendo a sua avaliação de algumas características de um _software_ produzido pela _XAX-Sooft_. Como esse _software_ não chegou a ser efetivamente construído, devemos considerar que as avaliações devam ser apenas estimadas, de acordo com os critérios que definem cada uma delas. Vejamos:

1. o relatório deve ser iniciado com a descrição de seu objetivo, que é o de avaliar as principais características de qualidade de um programa produzido pela empresa.
2. na sequência, você deverá descrever a avaliação das seguintes características do sistema, buscando responder a perguntas relacionadas a cada uma delas:

- **capacidade de manutenção**: o programa favorece a manutenção? O sistema possui boa divisão de módulos? É fácil de ser testado? **segurança**: o programa permite acesso apenas de pessoas autorizadas? Ele oferece condições de rastrear seu uso? **usabilidade**: o programa é fácil de ser usado? Sua operação é de fácil assimilação? **adequação funcional**: o _software_ apresenta todas as funções necessárias ao usuário? Ele gera dados e consultas corretos segundo o que foi definido?

Com esse levantamento, você terá um bom panorama da qualidade do produto e poderá direcionar esforços de melhoria com mais precisão.

_____

**⚠️ Atenção**

A característica conhecida como “Uso sem riscos” não deve ser confundida com a característica “Segurança do _software_”.

_____

**📌Lembre-se**

Alguns dos objetivos das Revisões Técnicas Formais são:

1. descobrir erros de implementação em qualquer representação do _software_;
2. verificar se o _software_ atende seus requisitos;
3. garantir que o _software_ tenha sido representado de acordo com os padrões definidos (PRESSMAN, 1995).