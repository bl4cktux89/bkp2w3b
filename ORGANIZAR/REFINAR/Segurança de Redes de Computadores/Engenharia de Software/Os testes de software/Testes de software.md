# **Introdução da unidade**

[![](https://ampli-images.s3.amazonaws.com/production/aa422dec-2a6f-45cb-ade6-cf7e23f3aceb/original)](https://ampli-images.s3.amazonaws.com/production/aa422dec-2a6f-45cb-ade6-cf7e23f3aceb/original)

### **Objetivos da Unidade**

Ao longo desta Unidade, você irá:

- examinar os fundamentos da atividade de teste de _software_, teste funcional e estrutura;
- discutir os conceitos e de que forma se dá a execução do Test-Driven Development (TDD);
- esclarecer o que são e como implementar o teste de release e teste de usuário;
- compreender como a manutenção se aplica em meio à evolução do _software_.

### **Introdução da Unidade**

Olá, estudante! Iniciamos à quarta unidade de Engenharia de _software_. Nas próximas quatro aulas serão tratados com mais profundidade temas relacionados ao teste e à evolução de um _software_.

O objetivo geral desta unidade é que você domine conceitos e práticas associadas à atividade de teste.

Como consequência do alcance desse objetivo, você deverá desenvolver a competência técnica de conhecer e conduzir processos de teste de _software_.

Você atingirá os objetivos e desenvolverá as competências desta unidade por meio da resolução dos desafios que serão colocados em cada aula da unidade, descritas aqui:

1. selecionar e registrar os casos de teste que serão utilizados na aplicação de teste funcional num dos programas da _XAX-Sooft_.
2. aplicar teste funcional em um dos programas da _XAX-Sooft_, com relato das atividades desempenhadas.
3. relatar a avaliação dos resultados obtidos com a aplicação do teste de _software_.
4. aplicar modelo de estimação de esforço de manutenção de um produto da _XAX-Sooft_.

A seguir será detalhada a primeira parte de nossa missão, proposta de conteúdo teórico sobre teste de _software_ e novas abordagens da situação-problema. Bom trabalho!

# **Introdução da aula**

[![](https://ampli-images.s3.amazonaws.com/production/18a5a37e-4c50-4f04-9336-1d8b22472ac2/original)](https://ampli-images.s3.amazonaws.com/production/18a5a37e-4c50-4f04-9336-1d8b22472ac2/original)

### **Qual é o foco da aula?**

Nesta aula, você terá contato com conceitos ligados ao tema e à apresentação de duas técnicas bastante usadas para a realização de testes.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer os fundamentos do teste de _software;_
- examinar os casos de teste, bem como se dá o defeito, falha e erro;
- identificar como ocorre a depuração e as técnicas de teste funcional e estrutural.

**Situação-problema**

É notável a evolução pela qual a _XAX-Sooft_ tem passado. Desde seu início, como uma empresa que sequer tinha um procedimento definido para desenvolvimento de seus produtos, até sua consolidação como uma organização reconhecidamente apta a entregar _software_ de qualidade, a _XAX-Sooft_ experimentou a ascensão que só uma empresa liderada por gente competente é capaz de ter. Todos os modelos e procedimentos adotados já fazem parte da rotina da empresa e a equipe sente-se à vontade com eles.

Afinal, o que mais a _XAX-Sooft_ deveria incluir em seu dia a dia para manter sua evolução? Qual aspecto do seu modelo de desenvolvimento ainda pode ser melhorado? Ao tratar das questões introdutórias de teste de _software_, esta aula propõe-se a responder essas questões e esclarecer como a atividade de teste pode contribuir de forma decisiva para a qualidade do produto final e para a consequente redução do investimento de tempo em atividades de retrabalho.

Usando como apoio os conceitos que serão tratados nesta aula, você deverá superar o desafio que se apresenta. É sua missão planejar e registrar os casos de teste que serão utilizados na aplicação de teste funcional num dos programas da _XAX-Sooft_. Resumidamente, um caso de teste é um dado de entrada que leva o programa a executar partes de seu código e a respectiva saída esperada para essa entrada. A evolução da aula dará a você melhores condições para entender e aplicar esse conceito.

Bons estudos!

# **Fundamentos**

[![](https://ampli-images.s3.amazonaws.com/production/085fc569-efb2-4dbc-9327-66a2bdbc59b7/original)](https://ampli-images.s3.amazonaws.com/production/085fc569-efb2-4dbc-9327-66a2bdbc59b7/original)

Um teste – ou um **processo de teste** – consiste em uma sequência de ações executadas com o objetivo de encontrar problemas no _software_, o que aumenta a percepção de qualidade geral do _software_ e garante que o usuário final tenha um produto que atenda às suas necessidades (PINHEIRO, 2015).

É sempre bom destacar que o objetivo do teste é encontrar problemas no _software_, e não garantir que o programa é livre de defeitos. Se o processo de teste não revelar defeitos, há que se aprimorar os casos de teste e o processo empregado. Não se pode acreditar que o sistema não possui problemas se o teste não os revelar. O processo de teste é normalmente separado em quatro grandes etapas:

- **planejamento**: nesta etapa deve ser definido quem executa os testes, em que período, com quais recursos (ferramentas de teste e computadores, por exemplo) e qual será a técnica utilizada (técnica estrutural ou técnica funcional, por exemplo).
- **projeto de casos de teste**: aqui são definidos os casos de teste que serão utilizados no processo. No próximo item, este conceito será detalhado.
- **execução do programa com os casos de teste**: nesta etapa, o teste é efetivamente realizado.
- **análise dos resultados**: aqui verifica-se se os testes retornaram resultados satisfatórios. Na sequência, um item muito importante para a resolução do problema proposto será abordado.

# **Casos de teste**

[![](https://ampli-images.s3.amazonaws.com/production/8fa0586a-9219-4ed2-845b-91383047f310/original)](https://ampli-images.s3.amazonaws.com/production/8fa0586a-9219-4ed2-845b-91383047f310/original)

Um caso de teste é o par formado por uma entrada no programa e a correspondente saída esperada, de acordo com os requisitos do sistema. Entenda o conceito de entrada como o conjunto de dados necessários para a execução do programa. A saída esperada é o resultado de uma execução do programa ou função específica.

Imagine que estejamos colocando sob teste um programa que valida datas inseridas pelo usuário. Um caso de teste possível seria (25/12/2016; válida). Ao receber a entrada 25/12/2016, o programa de validação de data deveria retornar “data válida”.

É certo que a boa escolha dos casos de teste é fundamental para o sucesso da atividade. Um conjunto de casos de teste de baixa qualidade pode não exercitar partes críticas do programa e acabar não revelando defeitos no código. Se o responsável pelos testes usasse apenas datas válidas como entradas, a parte do programa que trata das datas inválidas não seria executada, o que prejudicaria a confiabilidade do processo de teste e do produto testado. Observe os casos de teste que seguem:

t1= {(13/2/2016;válida), (30/2/2004;inválida); (25/13/2000;inválida); (29/2/2016;válida), (29/2/2015;inválida), (##/1/1985;inválida)}. Com esse cenário, certamente a maior parte do código será coberta e a chance de detecção de defeitos aumentará.

Parece claro que o procedimento de testes está diretamente relacionado à boa escolha e ao bom uso dos casos de teste. Idealmente, cada conjunto de casos de teste deverá estar associado a um grande requisito diferente a ser testado. Para que não se corra o risco de definilos incorretamente, é necessário planejamento e o bom conhecimento da aplicação. Uma boa forma de se abordar o problema é a que segue (PINHEIRO, 2015):

- definir o ambiente no qual o teste será realizado;
- definir a entrada deste caso de teste;
- definir a saída esperada para cada entrada;
- definir os passos a serem realizados para executar os testes.

Quando um caso de teste é executado, o seu resultado deve ser coletado. Podemos assumir diferentes abordagens para definir o resultado da aplicação de um caso de teste específico. A mais comum define as seguintes opções (PINHEIRO, 2015):

- passou: todos os passos do caso de teste foram executados com sucesso para todas as entradas;
- falhou: nem todos os passos foram executados com sucesso para uma ou mais entradas;
- bloqueado: o teste não pôde ser executado, pois o seu ambiente não pôde ser configurado.

Pois bem, dessa forma definimos casos de teste. Há, no entanto, três conceitos especialmente importantes no contexto de teste e que são frequentemente confundidos entre si. Vamos a eles.

# **Defeito, falha e erro**

[![](https://ampli-images.s3.amazonaws.com/production/b5097725-c3ba-4574-bec8-ad15138faf1b/original)](https://ampli-images.s3.amazonaws.com/production/b5097725-c3ba-4574-bec8-ad15138faf1b/original)

Que expressão que você usa quando um programa simplesmente trava ou não produz o resultado que se espera dele? Tudo o que acontece de incomum em um programa pode ser chamado de erro? Observe os conceitos:

- **defeito**: trata-se de deficiência algorítmica que, se ativada, pode levar a uma falha. Vamos a um exemplo. Observe o trecho que segue, escrito em pseudocódigo:

a = -1;

b = 0;

enquanto a < 0 faça

b = b + 1;

imprima (b);

imprima (a);

fim_enquanto;

Em algum momento o valor da variável deixará de ser menor que zero? Estamos diante de um defeito, mais precisamente um laço infinito. Se o caso de teste escolhido for capaz de exercitar esse trecho do código, o defeito se manifestará e então teremos uma falha observável. O programa provavelmente será interrompido.

- **falha**: é tida como um não funcionamento do programa, provavelmente provocada por um defeito. No entanto, uma falha também pode ser atribuída a uma queda na comunicação ou a um erro na leitura do disco, por exemplo.
- **erro**: ocorre quando o resultado obtido em um processamento e o que se esperava dele não são coincidentes. Um erro também está associado a uma violação nas próprias especificações do programa. Por exemplo, um usuário não autorizado consegue acessar determinado módulo do programa (esse é o resultado obtido), sendo que seu nível de privilégios não deveria permitir que o fizesse (esse era o resultado esperado).

_____

**➕ Pesquise mais**

Os conceitos de defeito, falha e erro não são uniformes nas referências. Outros conceitos básicos também podem variar entre autores. Uma boa fonte introdutória e conceitual pode ser obtida no artigo “[_Invista em você! Saiba como a DevMedia pode ajudar sua carreira_](https://www.devmedia.com.br/introducao-aos-diferentes-tipos-de-teste/29799)[”](https://www.devmedia.com.br/introducao-aos-diferentes-tipos-de-teste/29799).

_____

Embora estejamos diante de conceitos com diferenças sutis e que frequentemente são confundidos, a devida separação em três certamente facilitará o entendimento de outros conceitos e procedimentos mais adiante.

# **Depuração**

[![](https://ampli-images.s3.amazonaws.com/production/0ced73cb-69f0-493e-8b90-7e18cb94f4ac/original)](https://ampli-images.s3.amazonaws.com/production/0ced73cb-69f0-493e-8b90-7e18cb94f4ac/original)

Enquanto testar significa executar o _software_ para encontrar defeitos desconhecidos, a depuração é a atividade que consiste em buscar no código a localização desses erros. O fato de saber que o programa não funciona não implica, necessariamente, já se saber também em qual ou quais linhas o problema está.

Os ambientes de programação atuais oferecem recursos para depuração do programa. Durante esse processo, o valor assumido pelas variáveis sob inspeção em cada passo do algoritmo pode ser observado. Além disso, alguns pontos de parada da execução do programa podem ser inseridos no código. Tudo para possibilitar que o testador identifique e isole o defeito no código.

______

🔁 **Assimile**

O término bem-sucedido do processo de compilação significa que o código apresenta correção sintática e semântica e, portanto, pode ser executado pelo computador. No entanto, isso não garante, definitivamente, que o programa esteja livre de erros de lógica ou de cálculo.

______

Como todo processo desenvolvido com base científica, a atividade de teste também inclui maneiras estruturadas e consagradas para a sua realização. Dependendo da disponibilidade do código-fonte, da ferramenta de teste escolhida e das características do programa a ser testado, a técnica funcional ou a técnica estrutural podem ser aplicadas.

Imagine o programa como uma caixa. Quando o testador não tem acesso ao código-fonte, ele está lidando com uma caixa preta, cujo interior não se consegue ver. Daí o teste funcional também ser conhecido como caixa preta. A técnica estrutural, por sua vez, é também conhecida como caixa branca, cujo interior se pode ver. Essa comparação é feita justamente pela disponibilidade do código-fonte e das estruturas internas do programa. Veremos a seguir uma descrição mais aprofundada dessas técnicas.

# **Técnica de teste funcional**

[![](https://ampli-images.s3.amazonaws.com/production/cac5c23d-f21b-43aa-82cc-273712d4b3ae/original)](https://ampli-images.s3.amazonaws.com/production/cac5c23d-f21b-43aa-82cc-273712d4b3ae/original)

Esta técnica baseia-se nas especificações do _software_ para derivar os requisitos de teste. O teste é realizado nas funções do programa, daí o nome funcional. Não é seu objetivo verificar como ocorrem internamente os processamentos, mas se o algoritmo inserido produz os resultados esperados (BARTIÉ, 2002).

Uma das vantagens dessa estratégia de teste é o fato de ela não requerer conhecimento de detalhes da implementação do programa. Sequer o código-fonte é necessário. Observe uma representação dessa técnica na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/7ac1427b-e7eb-4656-bf65-58c3640ee59f/original)](https://ampli-images.s3.amazonaws.com/production/7ac1427b-e7eb-4656-bf65-58c3640ee59f/original)

Visão de teste de caixa preta. Fonte: Bartié (2002, p. 105).

O planejamento do teste funcional envolve dois passos principais: identificação das funções que o _software_ deve realizar (por meio da especificação dos requisitos) e a criação de casos de teste capazes de checar se essas funções estão sendo executadas corretamente.

Apesar da simplicidade da técnica e apesar de sua aplicação ser possível em todos os programas cujas funções são conhecidas, não podemos deixar de considerar uma dificuldade inerente: não se pode garantir que partes essenciais ou críticas do _software_ serão executadas, mesmo com um bom conjunto de casos de teste.

_____

**📝 Exemplificando**

Imagine uma função que valida nomes de identificadores em uma linguagem de programação criada por você. As condições para validação são: tamanho do identificador entre 1 e 6 caracteres, primeiro caractere necessariamente deve ser letra e caracteres especiais não são permitidos. A tabela abaixo resume as condições de validade do identificador e a aplicação do teste.

[![](https://ampli-images.s3.amazonaws.com/production/33b3cca8-2ab1-48d1-acd6-09aac75d4420/original)](https://ampli-images.s3.amazonaws.com/production/33b3cca8-2ab1-48d1-acd6-09aac75d4420/original)

Resultado da aplicação da técnica funcional com os casos de teste dados. Fonte: elaborada pelo autor.

Exemplo de Conjunto de Casos de Teste:

T0 = {(a1,Válido), (2B3, Inválido), (Z-12, Inválido), (A1b2C3d, Inválido)}

(1, 3, 5) (4) (6) (2)

_____

Conheça agora uma técnica de teste bastante eficiente na descoberta de defeitos.

# **Técnica de teste estrutural**

[![](https://ampli-images.s3.amazonaws.com/production/534aba4f-5395-4278-a0e8-5261b89243e3/original)](https://ampli-images.s3.amazonaws.com/production/534aba4f-5395-4278-a0e8-5261b89243e3/original)

Os testes estruturais (ou de caixa branca) são assim conhecidos por serem baseados na arquitetura interna do programa. De posse do código-fonte (ou do código-objeto) e, se for o caso, das estruturas de banco de dados, o profissional designado para a atividade submete o programa a uma ferramenta automatizada de teste.

A ferramenta constrói uma representação de programa conhecida como grafo de programa. No grafo, os nós equivalem a blocos indivisíveis, ou seja, não existe desvio de fluxo do programa para o meio do bloco e, uma vez que o primeiro comando do bloco é executado, os demais comandos são executados sequencialmente. As arestas ou arcos representam o fluxo de controle entre os nós.

Observe o trecho de código a seguir, escrito em linguagem C. Ele valida identificadores de acordo com os critérios dados no quadro Exemplificando (DELAMARO, 2004). Os números à frente de cada linha representam os nós do grafo que vem logo a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/5dd36530-d235-41f7-a0e3-a8520d735682/original)](https://ampli-images.s3.amazonaws.com/production/5dd36530-d235-41f7-a0e3-a8520d735682/original)

[![](https://ampli-images.s3.amazonaws.com/production/d68c1e22-2ba7-40e6-a97e-6e1b87e0803f/original)](https://ampli-images.s3.amazonaws.com/production/d68c1e22-2ba7-40e6-a97e-6e1b87e0803f/original)

A submissão do código a uma dada ferramenta de teste criará a representação vista na figura a seguir. Note que cada trecho identificado com um número no código é reproduzido em um nó do grafo.

[![](https://ampli-images.s3.amazonaws.com/production/37159641-03bb-4b39-84a1-db7632ef10d9/original)](https://ampli-images.s3.amazonaws.com/production/37159641-03bb-4b39-84a1-db7632ef10d9/original)

Representação em grafo de código sob teste. Fonte: Delamaro (2004, p. 11).

A função do testador, então, é encontrar casos de teste que, durante uma execução do programa, sejam capazes de exercitar os caminhos, nós e arcos do grafo. Um caminho simples, por exemplo, seria dado por (2,3,4,5,6,7). O caminho completo é representado por (1,2,3,4,5,7,4,8,9,11). Aí está, resumidamente, colocada a técnica funcional. Apesar de ser mais eficiente em encontrar defeitos no código, sua aplicação é mais dispendiosa e complexa.

_____

**💭 Reflita**

Se é certo que um teste, por melhor que seja executado, não conseguirá assegurar que o programa é 100% livre de defeitos, qual a indicação de que é chegado o momento de interromper os testes? Pois é justamente durante o planejamento do teste que os critérios de parada da atividade são definidos.

_____

Pois bem, a devida introdução ao teste de _software_ foi dada. Existem outras tantas técnicas e métodos de aplicação de teste cuja abordagem extrapolaria os objetivos desta aula. Embora de difícil execução e de custo relativamente alto, a atividade de teste é fundamental no processo de criação de programas. É certo que desenvolvedores têm investido em ferramentas e em material humano para conferir graus elevados de qualidade aos seus produtos. E é importante que seja assim.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

A atividade de teste, quando tratada de modo correto e profissional, deve ser bem planejada e estruturada antes de ser executada. Não se pode conceber que uma empresa que busque a excelência em seus produtos negligencie essa etapa tão importante do desenvolvimento.

A preparação da atividade não pode deixar de prever os recursos que serão utilizados nos testes, o prazo para sua execução, a técnica a ser utilizada e, em estágio mais avançado de planejamento, os casos de teste a serem utilizados.

A _XAX-Sooft_, na condição de organização que busca constante aprimoramento em seus processos e produtos, não poderia deixar de investir boa energia no teste dos seus produtos. Como desafio proposto, é sua missão planejar e registrar os casos de teste que serão utilizados na aplicação de teste funcional num dos programas da XAXSooft. Com a finalidade de dar suporte a você, as duas funções do programa a serem testadas são descritas na sequência:

- **função 1**: validação de CPF do cliente, segundo seu estado de origem. O terceiro dígito da direita para a esquerda identifica a unidade federativa na qual a pessoa foi registrada, de acordo com o quadro abaixo. Exemplo: o CPF 000.000.008-00 é de alguém cujo estado de origem é São Paulo.

[![](https://ampli-images.s3.amazonaws.com/production/c12f19e6-0f86-4d75-9e1a-92e67db2adc0/original)](https://ampli-images.s3.amazonaws.com/production/c12f19e6-0f86-4d75-9e1a-92e67db2adc0/original)

Unidade Federativa de registro do CPF. Fonte: Gerador de CPF.

- **função 2**: verifica atraso no pagamento e aplica acréscimo de 1 ponto percentual sobre cada dia de atraso verificado no pagamento. Uma solução possível para esse desafio é a que segue.

Exemplo de conjunto de casos de teste da Função 1:

1. formato geral: (número_do_cpf, estado_de_origem; saída_ esperada):

t1={(937.599.133-42, Ceará; válido), (831.469.521-14, Tocantins; válido), (858.178.888-23, São Paulo; válido), (300.168.443-78, Rio Grande do Sul; inválido)}

Exemplo de conjunto de casos de teste da Função 2:

Formato geral: (data_do_vencimento, data_do_pagamento, valor_ do_debito; valor_a_ser_pago)

t2 ={(10/2/2016, 14/2/2016, 500; 520), (5/2/2016, 2/2/2016,125;125), (15/2/2016, 5/2/2016, 68; 68)}.

_____

**⚠️ Atenção**

A conferência da saída obtida pela aplicação do caso de teste é que indicará a existência de problema no código ou não.

_____

**📌Lembre-se**

Quanto maior a qualidade do conjunto de casos de teste, maiores serão as chances de o teste detectar defeitos.