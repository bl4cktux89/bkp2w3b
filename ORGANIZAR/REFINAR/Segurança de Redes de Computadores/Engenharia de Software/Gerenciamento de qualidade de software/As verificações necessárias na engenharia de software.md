# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/e8d24387-d774-44a3-bc0d-b9d4a12cb87f/original)](https://ampli-images.s3.amazonaws.com/production/e8d24387-d774-44a3-bc0d-b9d4a12cb87f/original)

### **Qual é o foco da aula?**

Nesta aula, você terá contato com o conceito de métrica e medição, com algumas formas de medições de um produto de _software_, além de revisões e inspeções.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- distinguir métrica e medição;
- analisar os pontos por função;
- Examinar as revisões e inspeções do _software._

**Situação-problema**

Chegamos à última aula desta unidade! Depois de diagnosticar como a qualidade era tratada pela equipe, avaliar seus principais indicadores em um produto e implementar o modelo padrão consagrado, a _XAX-Sooft_ mantém passo firme rumo à excelência em seus processos e na busca pela maior qualidade possível em seus produtos.

Como você está lembrado, o desafio da última aula foi justamente escolher o padrão de qualidade que a _XAX-Sooft_ adotaria. No entanto, você ainda pode incluir providências na rotina _XAX-Sooft_ que certamente implicarão retorno positivo à empresa.

Que tal adotar formalmente um processo de detecção de defeitos rigorosos e bem definidos nos produtos? Será possível e viável quantificar algumas características do _software_, tal como complexidade funcional? Em outras palavras: conseguimos medir alguns atributos do programa? Entenda atributos como, por exemplo, número de funções e tamanho do código. Não é difícil imaginar o benefício que tais ações trariam aos produtos.

Pois bem, é hora de formalizar os procedimentos de qualidade do produto. Sua missão é justamente criar relatório contendo o processo de implantação de inspeções, medições e métricas de _software_. Dessa forma, poderá conhecer e conduzir processos de qualidade de _software_, aplicados a um projeto de desenvolvimento de _software_.

Conforme já tratamos, uma das consequências direta dessas ações é melhoria da qualidade do produto. Mas é certo que, indiretamente, ela é obtida pelo aprimoramento das estimativas de prazo, custo e esforço relacionadas ao produto. Estamos diante de algo a ser experimentado, não acha?

Bom trabalho e siga em frente com os estudos.

# **Métrica e medição**

[![](https://ampli-images.s3.amazonaws.com/production/9acc8383-b951-4353-a4df-8a68f922a7a6/original)](https://ampli-images.s3.amazonaws.com/production/9acc8383-b951-4353-a4df-8a68f922a7a6/original)

É muito difícil concebermos uma atividade desempenhada profissionalmente que não inclua maneiras de se medir o que é produzido. Essas medidas, sejam relacionadas a tamanho físico, a complexidade funcional ou a desempenho, visam assegurar algo indispensável em um ambiente produtivo: o controle.

A medição é o processo pelo qual os números são atribuídos aos atributos de entidades do mundo real. Na medição, atribui-se um valor numérico a uma grandeza física. Por exemplo, quando medimos a distância entre dois pontos e obtemos 5 metros, estamos atribuindo o valor 5 à grandeza física chamada distância. Usaremos o termo medição tanto para descrever um processo como um valor de atributo.

A **medição** é tipicamente uma quantificação direta, que envolve um único valor, ao passo que **métrica** é uma quantificação indireta, que envolve o cálculo e o uso de mais de uma medida. Vamos a um exemplo de métrica: considerando a medida de número de linhas de código de um programa e a medida de número de defeitos encontrados em todo o programa, podemos estabelecer a métrica de quantidade de defeitos por linha de código.

É desejável que as métricas sejam capazes de fornecer informação relevante para a tomada de decisão e para a comparação de desempenhos. É necessário que você tenha em mente um fato importante: existem métricas referenciais, usadas normalmente de forma padronizada pelos desenvolvedores. No entanto, uma métrica pode ser baseada no objetivo da organização e na sua necessidade de informação para a tomada de uma decisão.

Devemos considerar também que uma métrica deve ser calculada com facilidade, que ela tenha condições de ser repetida quantas vezes forem necessárias, que sua unidade seja compreensível e universal e que, por fim, seu processamento possa ser automatizado.

**_____**

**📝 Exemplificando**

Observe este exemplo do uso de métrica. Se você quer comprar um carro – e procura por eficiência – você não levará em conta a quantidade de quilômetros que ele é capaz de rodar, nem a quantidade de combustível que ele consegue armazenar no tanque. Na verdade, o que você quer saber é quanto ele consegue rodar com um litro de combustível. Assim, pelo uso de uma métrica, conseguimos chegar a um dado relevante e apto a te ajudar na tomada da sua decisão de compra do carro.

**_____**

Imagine que dois projetos de _software_ – com alguma similaridade funcional entre eles – estejam em construção. Se você quiser saber qual dos dois projetos está sendo mais produtivo, você deve realizar a medição do tamanho do projeto e do esforço para produzi-lo. Contudo, sem uma métrica, a comparação não seria viável, tampouco útil (MOORTHY, 2013).

No âmbito da construção de um _software_, as medidas podem ser categorizadas em (SWEBOK, 2004):

- **medidas de processo**: a expressão “medida de processo” que usamos aqui significa a coleta, análise e interpretação de informações quantitativas sobre o processo utilizado pelo desenvolvedor. A medição é usada para identificar os pontos fortes e deficiências do processo, além de avaliar o processo após sua implementação ou mudança. Por exemplo, a introdução de inspeções de _software_ no processo pode reduzir o esforço para realização de testes. No entanto, pode haver aumento de tempo até a entrega do produto, caso as reuniões de inspeção sejam extensas demais. A decisão de se investir mais tempo nas inspeções do que nos testes, por exemplo, deverá ser tomada com base em métrica aplicada no processo.
- **medidas de produto**: as medidas de um produto incluem o tamanho do produto, sua estrutura e sua qualidade. Trataremos melhor dessas medidas e algumas das métricas correspondentes no decorrer desta aula. Outras duas medidas também devem ser consideradas neste contexto (MOORTHY, 2013).
- **medidas de projeto**: usadas para quantificar o desempenho de um projeto de _software_. Por exemplo, uma métrica comumente usada neste contexto é a porcentagem de variação no cronograma do projeto, assim expressa: (data real de término – data planejada de término *100) / (data planejada de término – data real de início).
- **medidas de recursos**: usadas para quantificar a utilização de recursos em um projeto de _software_. Imagine que estejamos tratando de recursos humanos, ou seja, pessoas. Uma boa medida de efetividade seria dada pela quantidade de tarefas cumpridas por unidade de tempo, considerando tarefas de complexidade e duração semelhantes.

**_____**

**➕ Pesquise mais**

Como uma organização pode definir qual conjunto de métricas é adequado aos seus objetivos? Existe um modelo que ajude a definir e implantar as métricas? O GQM, acrônimo para Goal/Question/Metric (Objetivo/Questão/Métrica) é uma abordagem orientada a metas para a mensuração de processos e produtos de _software_. Para que você saiba mais sobre o assunto, leia os artigos listados abaixo:

1. "[Análise de Custos e Benefício de Mensuração Baseado em GQM- Um Estudo de Caso Replicado](http://www.inf.ufsc.br/~c.wangenheim/download/cits99.pdf)”
2. “[GQM Goal–Question‐ Metric](https://www.cin.ufpe.br/~scbs/metricas/seminarios/GQM_texto.pdf)”

**_____**

Já sabemos que, feitas as medições, podemos (e devemos) utilizá-las para gerar as métricas. Para fins de classificação, algumas métricas são geradas a partir de medidas obtidas diretamente, geralmente por contagem do atributo observado.

Às métricas geradas damos o nome de **métricas diretas**. Outras métricas, porém, são obtidas indiretamente. A elas damos o nome de **métricas indiretas**.

**_____**

**📝 Exemplificando**

Exemplos de métricas diretas: custo, esforço, quantidade de linhas de código, quantidade de erros, velocidade de execução do programa, entre outras. Em relação às métricas indiretas, os exemplos mais referenciados são funcionalidade, confiabilidade e manutenibilidade.

**_____**

Vale a pena analisarmos uma dessas métricas tomadas como exemplo. Na sequência, você conhecerá uma métrica de esforço, muito usada para medir o tamanho funcional de um _software_ com o objetivo de obter boa estimativa de custo, antes mesmo da sua efetiva construção.

# **Análise de pontos por função**

[![](https://ampli-images.s3.amazonaws.com/production/6cfc39f8-c8df-4ba4-973a-658af41fe958/original)](https://ampli-images.s3.amazonaws.com/production/6cfc39f8-c8df-4ba4-973a-658af41fe958/original)

Essa técnica se baseia nos requisitos do _software_ para a obtenção da métrica. Por isso, ela é aplicável a partir do momento em que os requisitos funcionais do programa (ou as histórias) tenham sido definidos. Esses requisitos (ou funções – daí o nome de Pontos por Função) são convertidos em valores numéricos que, depois de calculados e ajustados, proverão excelente ideia do esforço necessário para desenvolver o sistema (WAZLAWICK, 2013).

Você deve se lembrar de que uma medida direta se baseia geralmente em contagem feita em algum atributo do sistema. Os atributos relevantes neste nosso contexto são os requisitos.

Devemos considerar que os resultados obtidos pela aplicação dessa métrica não se prestam apenas para estimar esforço de desenvolvimento. Dependendo da intenção de uso da métrica, a contagem dos pontos de função também pode ser usada para:

- **melhoria de um produto** – neste caso, são contadas as funcionalidades alteradas, suprimidas ou adicionadas durante a manutenção adaptativa.
- **contagem de aplicação** – técnica usada para contar pontos de aplicações já existentes.

_____

**💭 Reflita**

Quais as razões que justificam investimento de tempo e dinheiro para medir processos, produtos, projetos e recursos? Imagine que, por meio das medições, você poderá avaliar as atividades em curso, estimar em qual estágio tais atividades estarão no futuro e controlar o uso de recursos destinados ao projeto.

Em outras palavras, as vantagens derivadas de um processo estruturado de medições poderão oferecer claras indicações sobre a qualidade do produto, servirão de avaliação da produtividade da equipe e determinarão se um novo método ou ferramenta implementados estão sendo efetivos.

_____

Pois bem, falta-nos então conhecer o procedimento de contagem das funções e do cálculo da métrica. Antes de você chegar a qualquer explicação textual, observe a figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/112d0653-6049-4f12-bb4f-d5f48938c876/original)](https://ampli-images.s3.amazonaws.com/production/112d0653-6049-4f12-bb4f-d5f48938c876/original)

Diagrama do processo de contagem de pontos de função. Fonte: Mecenas; Oliveira (2005, p. 4).

A fase de identificação da fronteira do aplicativo serve, por exemplo, para determinar se a contagem estará concentrada em um ou mais sistemas. Ela serve para estabelecer um divisor entre os componentes do aplicativo e os componentes de outro aplicativo.

Na sequência do processo, vem a contagem das funções do sistema. Vejamos o procedimento (MECENAS; OLIVEIRA, 2005):

- **funções do tipo dados**: representam as necessidades de dados dos usuários, de acordo com sua visão de negócio. Divide-se em:

1. Arquivo Lógico Interno (ALI): trata-se de um elemento percebido pelo usuário e mantido internamente pelo sistema. Exemplos: arquivos de cadastro de clientes, cadastro de funcionários, arquivos de mensagens de auxílio e arquivos de mensagens de erros.
2. Arquivo de Interface Externa (AIE): representa as necessidades de dados externos à aplicação, ou seja, são dados armazenados fora da fronteira da aplicação, mas que não sofrem manutenção internamente.

- **funções do tipo transação**: representam as funcionalidades de processamento de dados identificados pelos usuários. Existem três funções deste tipo:

1. entrada externa (EE): função que obtém dados informados pelo usuário ou por outra aplicação e os inserem no sistema. A função deve ter como objetivo armazenar, alterar ou remover dados no sistema. O nome de um cliente e seu endereço são exemplos de entradas externas.
2. saída externa (SE): função que obtém dados do sistema e apresentam ao cliente ou enviam a outras aplicações, sendo que pelo menos um valor obtido por cálculo deve existir para que seja considerada saída externa. Exemplo: fatura de um cliente, relação de clientes inadimplentes.
3. consulta externa (CE): função que apresenta dados da mesma forma que foram armazenados, sem cálculos ou transformações. Configura uma consulta externa, por exemplo, informar o CPF de uma pessoa ao sistema para se obter seus dados cadastrais completos.

Uma vez identificadas e contadas as funções, as quantidades apuradas são classificadas como complexidade alta, média e baixa, conforme a tabela abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/0b72b237-0227-40ec-912a-96cf548c841b/original)](https://ampli-images.s3.amazonaws.com/production/0b72b237-0227-40ec-912a-96cf548c841b/original)

Fatores de complexidade. Fonte: Waslawick (2013, p. 161).

______

**🔁 Assimile**

Para efeito de contagem, um requisito do sistema equivale a uma função. No entanto, essa regra não deve ser tomada de forma absoluta. Apenas funções visíveis para o usuário devem ser consideradas. Um cálculo interno, por exemplo, não deve ser contado. Se apenas um requisito trata de cadastro de clientes e de produtos, então teremos aí duas funções. Em resumo, deve-se tomar os requisitos, eliminar os que são funções internas e subdividir aqueles que representam mais do que uma função (WAZLAWICK, 2013).

______

Determinadas as complexidades das funções do tipo dados e transação, a soma dos pontos obtidos é chamada de pontos de função não ajustado. Nessa etapa, já temos o tamanho funcional do aplicativo (MECENAS; OLIVEIRA, 2005).

# **14 características gerais do sistema**

[![](https://ampli-images.s3.amazonaws.com/production/bf7caeac-508a-4390-93b2-78cdcec66fb9/original)](https://ampli-images.s3.amazonaws.com/production/bf7caeac-508a-4390-93b2-78cdcec66fb9/original)

Ocorre que, para que a métrica possa ser útil de fato, há que se levar em consideração a real complexidade técnica dessas funções. Por exemplo, um sistema de controle de uma loja de locação de vídeo tende a possuir funções mais simples e estruturadas do que um sistema bancário.

O método, então, prevê a aplicação de ajuste neste valor obtido em função de 14 características gerais do sistema, aplicáveis a todo o projeto. Seguem:

1. Comunicação de dados: em que grau a comunicação de dados é requerida?
2. Processamento de dados distribuído: em que grau o processamento distribuído está presente?
3. Performance: o desempenho é fator crítico na aplicação?
4. Uso do sistema: o usuário deseja executar a aplicação em um equipamento já existente ou comprado e que será altamente utilizado?
5. Taxa de transações: qual o volume de transações esperado?
6. Entrada de dados on-line: são requeridas entrada de dados online?
7. Eficiência do usuário final: as funções interativas fornecidas pela aplicação enfatizam um projeto para o aumento da eficiência do usuário final?
8. Atualização on-line: há arquivos atualizados on-line?
9. Processamento complexo: qual o grau de complexidade do processamento interno?
10. Reusabilidade: em que grau o código é reutilizável?
11. Facilidade de instalação: em que grau o sistema é fácil de ser instalado?
12. Facilidade de operação: em que grau o sistema é fácil de ser operado?
13. Múltiplos locais: o sistema é projetado para múltiplas instalações em diferentes organizações?
14. Facilidade para mudanças: a aplicação é projetada de forma a facilitar mudanças?

Como cada um receberá uma nota de 0 a 5, o somatório desses fatores ficará entre 0 e 70. Assim, finalmente, a fórmula para o cálculo dos pontos por função ficará como segue:

[![](https://ampli-images.s3.amazonaws.com/production/ef7088b5-456e-4234-bfe7-ea3b240359e2/original)](https://ampli-images.s3.amazonaws.com/production/ef7088b5-456e-4234-bfe7-ea3b240359e2/original)

Onde: VAF = Value Adjustment Factor ou Fator de Ajuste da Função;

GSC = General Systems Characteristics ou Características Gerais do Sistema.

Por fim, tendo sido obtido os pontos não ajustados, que chamaremos de UFP (_Unadjusted Function Points_, ou pontos por função não ajustados), basta aplicar a fórmula que segue para o número de pontos por função ajustado:

[![](https://ampli-images.s3.amazonaws.com/production/0f756fda-3a21-4407-a37a-52274cdc6da9/original)](https://ampli-images.s3.amazonaws.com/production/0f756fda-3a21-4407-a37a-52274cdc6da9/original)

Vamos a um exemplo simples de cálculo de pontos por função. Suponha um projeto de programa que gerou as seguintes contagens:

[![](https://ampli-images.s3.amazonaws.com/production/3cbb52e2-5193-4b9a-a6ec-f1872331cfc4/original)](https://ampli-images.s3.amazonaws.com/production/3cbb52e2-5193-4b9a-a6ec-f1872331cfc4/original)

Cálculo de pontos por função. Fonte: Wazlawick (2013, p. 161).

Teremos então o valor 79 como contagem dos pontos por função não ajustados. Supondo que tenhamos obtido 55 na soma das características gerais do sistema, a fórmula de cálculo do Fator de Ajuste da Função ficaria como segue: VAF=0,65+0,55 VAF=1,2 Ao aplicarmos a fórmula dos pontos ajustados, obteremos: AFP=79*1,2. Portanto, os pontos por função ajustados para esse caso é 94,8.

# **Revisões e inspeções de software**

[![](https://ampli-images.s3.amazonaws.com/production/bdf5c23b-91c8-4195-9eb9-bf809dff1630/original)](https://ampli-images.s3.amazonaws.com/production/bdf5c23b-91c8-4195-9eb9-bf809dff1630/original)

Como você bem se recorda, revisões técnicas e inspeções foram apresentadas na primeira aula desta unidade. Dada a importância de ambos e a intenção de introduzir desde já temas relacionados a teste de _software_, uma nova abordagem será feita aqui.

Uma inspeção típica apresenta cinco etapas formais (SCHACH, 2008):

1. uma visão geral do documento a ser inspecionado (histórias, projeto, código ou outro) é dada e, logo após, é distribuído aos presentes na sessão;
2. por meio de uma lista de imperfeições detectadas em inspeções recentes, a equipe deverá analisar e entender o presente documento;
3. um participante escolhido deve percorrer o documento e conduzir a equipe de inspeção, garantindo que cada item seja verificado, em busca de falhas. A missão é encontrar falhas, não as corrigir. No prazo de um dia, o líder da equipe dever gerar relatório do que foi discutido;
4. no processo chamado **reformulação**, o responsável resolve as imperfeições encontradas;
5. no acompanhamento, o responsável deve garantir que cada questão levantada tenha sido adequadamente resolvida.

Para determinar a eficácia de uma inspeção, você pode usar a métrica da **taxa de inspeção**. Quando, por exemplo, a especificação dos requisitos (ou histórias) passam por inspeção, o número de páginas inspecionadas por hora pode ser medido. Se a inspeção recair sobre o código, uma métrica interessante é a de quantidade de linhas de código inspecionadas por hora.

______

📌**Lembre-se**

Formalmente, Inspeção e _Walkthroughs_ (passo a passo) são processos diferentes. Este último é um processo de duas etapas apenas: uma de preparação e outra de análise de documento pela equipe.

______

**💪 Faça você mesmo**

Considere um sistema que você conheça bem e separe, classifique e pontue suas funções de acordo com o estipulado para o cálculo de pontos por função. Na sequência, aplique os fatores de ajuste e obtenha o valor ajustado das funções, conforme a fórmula dada.

______

No próximo item será aplicado o conteúdo que acabamos de abordar com o objetivo de resolver o desafio proposto.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)

A busca da _XAX-Sooft_ pela excelência em seus processos e produtos continua. Com a sua intervenção, a empresa expandiu o conceito de qualidade e agora mira nas medições dos atributos de seus programas para obter controle sobre aquilo que produz. A implantação de medições e as métricas que delas derivam servirão para inspirar ainda mais a equipe na demanda pela qualidade.

No item anterior a este, você teve a oportunidade de absorver um pouco do conteúdo relacionado a métrica de **Pontos por Função**, juntamente com os conceitos de medição e métrica de _software_. Tais conhecimentos, aliados à sua crescente habilidade em planejar implantações de novos procedimentos, permitirá a você superar o desafio que ora é proposto.

Conforme já discutido, você deverá relatar seu planejamento para implantar processo de obtenção de métricas de _software_ no cotidiano da XAX-Sooft. Vamos então a uma possível solução para o desafio, utilizando a métrica de pontos por função como objeto.

1. Você deverá definir que o resultado obtido pela aplicação da métrica de Pontos por Função servirá para estimar o esforço para criação dos novos produtos. Em outras palavras, o procedimento deverá ser aplicado antes que o produto fique pronto.
2. A equipe responsável pela coleta e tratamento das histórias ou dos requisitos deverá ser orientada para que prepare as funções para serem processadas, excluindo cálculos internos da contagem e dividindo mais de uma função no mesmo contexto em duas funções distintas.
3. A equipe responsável pela aplicação da métrica deverá, então, contar as funções, obter os pontos por função não ajustados. Com utilização de critérios próprios e baseados na natureza de cada projeto, a equipe deverá estipular os valores que serão aplicados a cada um dos 14 fatores de ajuste, a fim de obter os pontos por função ajustados.
4. Após sua obtenção, o resultado deverá ser encaminhado para avaliação e análise, de forma que o esforço para criação daquele programa seja quantificado.

Com esse planejamento e com o bom aproveitamento do conteúdo ministrado, você inicia sua preparação para gerenciar processos de aplicações de medições e métricas em sua vida profissional. Dependendo de certas demandas, você poderá também incluir a aplicação de outras métricas no cotidiano da _XAX-Sooft_.

_____

**⚠️ Atenção**

A aplicação dos fatores de ajuste nos pontos obtidos não é procedimento obrigatório. Em, por exemplo, uma organização que produz programas com graus de dificuldade homogêneos, a prática poderá ser dispensada.

_____

**📌Lembre-se**

A métrica de Pontos por Função não se aplica apenas aos programas em fase de planejamento. Ela poderá ser aplicada também em processos de manutenção, permitindo a estimativa do esforço necessário para se fazer certa alteração no programa.

# **Referências bibliográficas**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

ABNT – Associação Brasileira de Normas Técnicas. **NBR ISO/IEC 9126- 1**: engenharia de _software_ – qualidade de produto – parte 1: modelo de qualidade. Rio de Janeiro: ABNT, 2003.

BARTIÉ, A. **Garantia da qualidade de** _**software**_: as melhores práticas de Engenharia de _Software_ aplicadas à sua empresa. 5. ed. São Paulo: Elsiever, 2002.

CMMI INSTITUTE. **Who uses CMMI**? Disponível em: https://cmmiinstitute.com/who-uses-cmmi . Acesso em: 17 mar. 2021.

CROSBY, P. B. **Quality is free**: the art of making quality certain. New York: New American Library, 1979.

DENNIS, R. G; DIANE, L. G. **Demonstrating the impact and benefits of CMMI**: an update and preliminary results. 2003. Disponível em: https://resources.sei.cmu.edu/asset_files/SpecialReport/2003_003_001_14117.pdf . Acesso em: 17 mar. 2021.

DEVMEDIA. **CMMI**: uma visão geral. Disponível em: https://www.devmedia.com.br/cmmi-uma-visao-geral/25425\#ixzz3yBwjcLs1 . Acesso em: 17 mar. 2021.

GOVERNO ELETRÔNICO. **ePING – Padrões de interoperabilidade de Governo Eletrônico**. Disponível em: http://eping.governoeletronico.gov.br/. Acesso em: 17 mar. 2021.

HUMPHREY, W., KITSON, D., KASSE, T. _The state of software engineering practice: a preliminary report. In:_ _**proceedings of the 11th international conference on software Engineering**__._ 1989, p. 277-288.

ISO. **About ISO**. Disponível em: https://www.iso.org/about-us.html. Acesso em: 17 mar. 2021.

LEÃO, A. **Aplicação de técnicas de ITIL e CMMI em pequenas e médias empresas de** _**software**_. Disponível em: http://www.techoje.com.br/site/techoje/categoria/detalhe_artigo/1734. Acesso em: 17 mar. 2021.

MECENAS, I.; OLIVEIRA, V. **Qualidade em** _**software**_: uma metodologia para homologação de sistemas. [s. l.]: Alta Books, 2005.

MOORTHY, V. _**Jumpstart to software quality assurance**_. [S.I. : s.n.], 2013.

PRESSMAN, R. S. Engenharia de _software_. São Paulo: Makron Books, 1995. ______. São Paulo: Pearson Prentice Hall, 2009. 1056 p

QUALITY CONSULT. **O que muda na versão 2015 da norma ISO 9001**. Disponível em: http://www.qualityconsult.com.br/index.php/iso-9001-versao-2015/. Acesso em: 17 mar. 2021.

REISS, E. **Usable usability**: simple steps for making stuff better. Indianapolis: John Wiley & Sons, 2012.

REZENDE, D. A. **Engenharia de** _**software**_ **e sistemas de informação**. 3. ed., rev. Rio de Janeiro: Brasport, 2005.

ROCHA, A. R.; MALDONADO, J. C.; WEBER, K. C. **Qualidade de** _**software**_: Teoria e Prática. São Paulo: Pearson, 2001.

RODRIGUES, A. N. et al. **Qualidade de** _**software**_ – parte 1. Disponível em: https://www.devmedia.com.br/_qualidade-de-software_/9408. Acesso em: 17 mar. 2021.

SCHACH, S. **Engenharia de** _**Software**_: os paradigmas clássico e orientado a objetos. 7. ed. São Paulo: McGraw-Hill, 2008.

SEEAR, D. J. **ISO 9001: 2015** _**Back to the future**_. A review of the new ISO Annex SL structure for Certification Standards using the draft ISSO 9001: 2015 to explain the changes. USA: Author House, 2015.

SHAFFER, S. C. **A brief introduction to** _**software**_ **development and quality assurance management**. [S.l.: s.n.], 2013.

SOFTEX. MPS.BR. Disponível em: https://softex.br/mpsbr/. Acesso em: 17 mar. 2021.

WAZLAWICK, R. S. **Engenharia de** _**Software**_: conceitos e práticas. Rio de Janeiro: Elsiever, 2013.