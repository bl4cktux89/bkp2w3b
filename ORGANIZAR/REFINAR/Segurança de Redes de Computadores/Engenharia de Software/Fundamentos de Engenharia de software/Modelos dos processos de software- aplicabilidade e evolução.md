# **Modelos dos processos de software: aplicabilidade e evolução**

[![](https://ampli-images.s3.amazonaws.com/production/3d0312cd-0a42-4edb-b9d9-53300f29893d/original)](https://ampli-images.s3.amazonaws.com/production/3d0312cd-0a42-4edb-b9d9-53300f29893d/original)

### **Qual é o foco da aula?**

Nesta aula, você vai conhecer elementos básicos de implementação de _software_, tais como: integração, as melhores práticas de implantação e como se faz a manutenção de _software_.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- esclarecer como ocorre a implementação do _software_;
- examinar a integração e implantação de _software_;
- identificar a necessidade e categorias de manutenção;

**Situação-problema**

Vamos à quarta aula desta primeira unidade da disciplina de Engenharia de _Software_!

Desde a primeira aula, sua ajuda tem sido decisiva na reestruturação do processo da _XAX-Sooft_. Por conta de sua boa intervenção, a empresa passou de um cenário de desenvolvimento indisciplinado e artesanal para um ambiente de procedimentos estruturados, papéis conhecidos e resultados mais previsíveis. Você sabe que as coisas ainda podem ser melhoradas, mas o primeiro passo foi dado. Afinal, o primeiro grande cliente já foi conquistado e, dependendo do sucesso dessa empreitada, outros se seguirão a ele.

Entretanto, a prova de fogo começa agora: sua missão é planejar e gerenciar a execução das fases finais do processo, cuidando para que um produto de qualidade seja entregue ao cliente. Entregue para o seu cliente um relatório de projeto de _software_ para cadastro de clientes por interesse, contendo todas as fases desenvolvidas até o momento.

A tarefa deve ser realizada pela elaboração de um documento que contenha aspectos principais da implementação, incluindo a definição dos programadores, escalonamento das atividades, controle de versão do sistema, treinamento dos usuários, implantação e linhas gerais do processo de manutenção. Vale a sugestão de que ao relatório criado na aula anterior sejam acrescidos os itens ora desenvolvidos, de modo a construir um único documento.

Mãos à obra e bom trabalho!

# **Implementação de software**

[![](https://ampli-images.s3.amazonaws.com/production/6600e366-b644-43f1-8ddc-4c4d56282a40/original)](https://ampli-images.s3.amazonaws.com/production/6600e366-b644-43f1-8ddc-4c4d56282a40/original)

Conforme temos estudado, o modelo tradicional de desenvolvimento de sistemas caracteriza-se pelo aproveitamento do resultado da etapa anterior na construção da etapa seguinte. Por exemplo, é por meio do que foi entregue na etapa de projeto que o pessoal da implementação construirá o programa. Esta aula trará a você conteúdo teórico necessário para se sair muito bem em nosso desafio de estruturar a etapa de implementação do nosso programa de controle de cliente.

Implementação é o processo de converter o projeto detalhado em código. Com as etapas anteriores de requisitos e projeto bem-sucedidas, a implementação tende a ser relativamente bem compreendida. Alguns pontos do processo devem ser alvo de atenção (SCHACH, 2008):

a) **escolha da linguagem de programação**: esta decisão passa pela vontade expressa do cliente, pela experiência da equipe em determinada linguagem e pela necessidade pontual do projeto. Em todos os casos, a escolha deverá ter sido registrada previamente pela equipe e pelo cliente. Caso o cliente não faça menção da linguagem a ser usada e o projeto não demande nada específico, a escolha certamente recairá sobre a linguagem que for de amplo conhecimento da equipe;

b) **práticas de programação adequadas**: o estilo usado no desenvolvimento do _software_ deve obedecer, preferencialmente, a padrões consagrados de codificação.

_____

**➕ Pesquise mais**

Um padrão de codificação pode ser entendido como um conjunto de regras que disciplinam a criação do código. Um padrão pode conter normas para criação de nomes de arquivos, nomes de classes, endentação e quebras de linha, entre outras. Leia mais sobre o assunto no artigo “[_Padrões de Codificação_](https://www.devmedia.com.br/padroes-de-codificacao/16529)” da DevMedia.

_____

Os nomes das variáveis e demais componentes do programa devem ser coerentes com sua real função. Recomenda-se que sejam dados nomes universalmente significativos aos identificadores, ou seja, que façam sentido tanto para o programador que trabalha naquele projeto como para os que eventualmente lhe darão manutenção futura.

Também estão inclusas nessas boas práticas a documentação do código. Ela deve ser objetiva, clara e transmitir dados elementares sobre o programa, que incluem descrição da função principal (ou do módulo), programadores envolvidos, interfaces externas e as últimas alterações feitas no código (SCHACH, 2008).

# **Integração de software**

[![](https://ampli-images.s3.amazonaws.com/production/11a81a2e-6465-4c85-b85f-45e4cccb70fb/original)](https://ampli-images.s3.amazonaws.com/production/11a81a2e-6465-4c85-b85f-45e4cccb70fb/original)

Integrar o _software_ significa combinar em um todo os módulos construídos durante a implementação. A figura abaixo mostra uma típica configuração de comunicação entre módulos de um programa. Uma possibilidade de efetivar a integração do produto é codificar e testar cada um dos artefatos (ou módulo) de código separadamente, unir e testar o produto como um todo.

Também estão inclusas nessas boas práticas a documentação do código. Ela deve ser objetiva, clara e transmitir dados elementares sobre o programa, que incluem descrição da função principal (ou do módulo), programadores envolvidos, interfaces externas e as últimas alterações feitas no código (SCHACH, 2008).

[![](https://ampli-images.s3.amazonaws.com/production/982066ae-4a68-4a65-8485-c4ba0393f82b/original)](https://ampli-images.s3.amazonaws.com/production/982066ae-4a68-4a65-8485-c4ba0393f82b/original)

Diagrama de interconexões. Fonte: Schach (2008, P. 475).

No entanto, essa abordagem pode apresentar dificuldades em sua execução. O módulo a, por exemplo, não pode ser testado isoladamente, pois possui relacionamentos com os módulos b, c e d. Outro problema associado a essa forma de integração é a falta de isolamento de falhas. Ou seja, caso o produto falhe, a falha poderia estar em qualquer um dos treze módulos ou em uma das treze interfaces (SCHACH, 2008).

A solução passa pela adoção de técnicas estruturadas de integração, incluindo integração top-down, bottom-up e sanduíche. O quadro abaixo resume os três tipos de integração.

[![](https://ampli-images.s3.amazonaws.com/production/4615de0e-5f22-4b73-bd2c-f8e6ba3b79d7/original)](https://ampli-images.s3.amazonaws.com/production/4615de0e-5f22-4b73-bd2c-f8e6ba3b79d7/original)

Resumo das técnicas de integração. Fonte: Schach (2008, P. 475).

_____

**💭 Reflita**

A integração poderá ser bastante problemática no caso de os módulos simplesmente não se comunicarem. Um objeto escrito no módulo a passa, por exemplo, dois argumentos para um outro objeto escrito no módulo b. No entanto, este segundo objeto está preparado para receber três argumentos. Neste caso haverá falha na integração. Tal situação mostra a necessidade de se implantar gerenciamento do processo de integração, que deve ser conduzido pelo pessoal de qualidade.

# **Implantação e manutenção de software**

[![](https://ampli-images.s3.amazonaws.com/production/b14ba67a-4657-4700-a19b-2e232f83767f/original)](https://ampli-images.s3.amazonaws.com/production/b14ba67a-4657-4700-a19b-2e232f83767f/original)

A **implantação** é uma das fases do desenvolvimento de um software. Embora deva sofrer alterações durante sua vida útil, espera-se que o software seja disponibilizado ao cliente em sua versão final.

Destaca Rezende (2005) que o envolvimento do cliente deve ser buscado nesta fase, assim como o foi nas fases anteriores do projeto. Da mesma forma que em outras etapas do processo de desenvolvimento, a implantação requer gerenciamento, como será abordado na sequência.

É comum que a implantação de um software ocorra em substituição a um anterior. Neste caso, os dados mantidos pelo software antigo devem ser convertidos para o formato previsto para o atual, seja em forma de digitação ou de conversão via programa.

De acordo com Rezende (2005), a efetiva implantação de um _software_ novo no lugar de um antigo pode acontecer de diversas formas:

a) **direta:** o funcionamento do software antigo cessa assim que o novo entra em operação. Não há concomitância na operação dos dois;

b) **paralela**: os dois sistemas funcionam por um tempo em paralelo, com a base de dados atualizada em ambos. Neste caso, a segurança na implantação do novo sistema é maior;

c) **piloto**: neste caso, o sistema atual poderá refazer os processamentos feitos pelo antigo, para fins de comparação de resultados;

d) **parcial ou por etapas**: o funcionamento do novo sistema inclui apenas parte do antigo. As novas rotinas substituem aos poucos as antigas.

Os esforços de desenvolvimento de um _software_ devem resultar na entrega de um produto que satisfaça os requisitos do usuário. No entanto, espera-se que o _software_ sofra alterações e evolua.

Uma vez em operação, defeitos são descobertos, ambientes operacionais mudam e novos requisitos dos usuários surgem. **A manutenção** é parte integrante do ciclo de vida do software e deve receber o mesmo grau de atenção que as outras fases.

A manutenção de _software_ é definida como modificações em um produto de _software_ após a entrega ao cliente, a fim de corrigir falhas, melhorar o desempenho ou adaptar o produto a um ambiente diferente daquele em que o sistema foi construído (IEEE, 2004)."

# **Necessidade e categorias de manutenção**

[![](https://ampli-images.s3.amazonaws.com/production/12e2a0b3-28a3-4305-978b-eb13d5d5fbb4/original)](https://ampli-images.s3.amazonaws.com/production/12e2a0b3-28a3-4305-978b-eb13d5d5fbb4/original)

A manutenção é necessária para assegurar que o _software_ continuará a satisfazer os requisitos do usuário. O sistema se altera devido a ações corretivas e não corretivas aplicadas ao _software_.

A manutenção deve ser executada a fim de corrigir falhas, melhorar o projeto, implementar melhorias, construir interface com outros sistemas, adaptar programas para que novas facilidades de hardware possam ser usadas, migrar _software_ legado, retirar _software_ de operação.

______

**🔁 Assimile**

> “Manutenção de software é como se denomina, em geral, o processo de adaptação e otimização de um software já desenvolvido, bem como, a correção de defeitos que ele possa ter. A manutenção é necessária para que um produto de software preserve sua qualidade ao longo do tempo, pois se isso não for feito, haverá uma deterioração do valor percebido desse software e, portanto, de sua qualidade.” (WAZLAWICK, 2013, p. 317).

______

Um _software_ legado é um sistema antiquado que continua em uso porque o usuário (tipicamente uma organização) não deseja substituí-lo ou projetá-lo novamente.

Existem algumas categorias de manutenção, vamos conhecê-las:

- **manutenção corretiva:** modificação reativa em um produto de _software_ executada após a entrega a fim de corrigir problemas descobertos.
- **manutenção adaptativa**: modificação em um produto de _software_ executada após a entrega do produto a fim de manter o _software_ usável em um ambiente alterado ou em alteração.
- **manutenção perfectiva**: modificação em um produto de _software_ realizada após a entrega a fim de melhorar o desempenho ou a manutenibilidade.
- **manutenção preventiva**: modificação em um _software_ após a entrega a fim de reparar falhas latentes antes que se tornem efetivas (IEEE, 2004).

_____

**📝 Exemplificando**

O exemplo que segue nos transmite a ideia do quanto a preparação prévia do programa para receber manutenção é importante e sobre o pensamento do cliente em relação à facilidade em se executar mudanças em um _software_.

Um programador foi chamado pelo governo para criar um produto de _software_ que mantivesse sete, e exatamente sete, tipos de frutas que eram controladas e comercializadas por certo órgão governamental. Havia ordem expressa de que o banco de dados fosse projetado para sete frutas, sem previsão de expansão.

O programa foi entregue e seguia em perfeito funcionamento até que, um ano após sua implantação, o gerente do órgão viu-se na necessidade de incluir mais uma fruta no controle do programa. Chamado a executar a manutenção do produto, o programador constatou que o projetista, desobedecendo às orientações iniciais, havia deixado alguns campos adicionais no banco de dados, o que permitiu a incorporação da oitava fruta.

Mais um ano se passou e, para que a recente mudança na legislação fosse atendida, o programa deveria agora acomodar o controle de mais 26 frutas. Informado sobre essa necessidade, o programador protestou, alegando que tal alteração levaria praticamente o mesmo tempo que a criação de um novo sistema.

“Que ridículo!”, retrucou o gerente. “Você não teve nenhuma dificuldade para acrescentar a oitava fruta. Simplesmente faça a mesma coisa agora, mais 26 vezes.” (SCHACH, 2008).

_____

- **manutenibilidade**: definida como a facilidade com que um _software_ pode sofrer manutenção, melhoramentos, adaptações ou correções para satisfazer requisitos específicos. Ela deve ser perseguida durante o desenvolvimento do _software_, de modo a minimizar os custos futuros de manutenção, que são inevitáveis.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)](https://ampli-images.s3.amazonaws.com/production/add8528f-cdc3-4eb4-8b7c-dd722eb0c857/original)

Concluídas as fases de tratamento dos requisitos e de elaboração do projeto do novo _software_, resta cumprir as etapas finais do processo de desenvolvimento e, por fim, entregar o programa ao cliente. Sua missão é a de estruturar o processo, cuidando para que todas as ações planejadas sejam factíveis e que o projeto possa ser levado à conclusão.

Sendo assim, ao trabalho!

O planejamento da implementação de _software_ inclui as seguintes atividades:

a) **definição dos programadores**: cada um dos responsáveis pela codificação dos módulos projetados deve ser destacado e informado sobre a linguagem de programação a ser utilizada. É boa prática a busca e adequação de funções já codificadas em outros projetos e que eventualmente poderão ser utilizadas neste atual;

b) **escalonamento das atividades**: a divisão de tarefas e seus respectivos responsáveis devem ser definidos em documento público. Nesse ponto, deve-se também definir os responsáveis pela integração e teste dos módulos;

c) **controle de versão**: durante a codificação, as atualizações feitas no sistema serão informadas a toda equipe de programação, por meio de ferramenta de controle de versão instalada em servidor próprio.

A implantação prevê a efetiva instalação do programa em servidor próprio do cliente e a escala de treinamento aplicado aos usuários. O treinamento será prestado na semana que antecede a colocação do programa em funcionamento, com dois profissionais destacados para o trabalho. Não há sistema em funcionamento que execute as mesmas funções do novo sistema, daí a dispensa de planejamento para conversão de dados e troca de sistemas.

Por fim, a manutenção deverá ser prestada sob demanda, exceto em casos em que correções devam ser feitas. O cliente, sentindo necessidade de alterar ou aprimorar o sistema, contratará horas adicionais da equipe de programadores. As correções, por sua vez, serão feitas sem custo.

Uma boa referência documental para essa atividade pode ser encontrada em no artigo “[_Metodologia de implantação de software corporativo_](http://www2.ati.pe.gov.br/c/document_library/get_file?p_l_id=144654&folderId=144374&name=DLFE-15402.pdf)_”_ de Edílson José de Souza.

_____

**⚠️ Atenção**

O treinamento das pessoas que utilizarão o novo programa é providência fundamental para sucesso do projeto. A transmissão das práticas relacionadas ao programa, quando feita por profissionais hábeis em motivar o cliente para sua efetiva utilização, pode fazer a diferença entre a plena adesão e o não reconhecimento da utilidade de um programa.

# **Referências bibliográficas**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

IEEE. **SWEBOK**: a project of the IEEE Computer Society Professional Practices Committee. Los Alamitos: IEEE, 2004.

LAPLANTE, P. A. **What every engineer should know about:** _**software**_ **engineering**. London: CRC, 2007.

PRESSMAN, R. S. **Engenharia de** _**software**_. São Paulo: Pearson Prentice Hall, 2009. 1056 p.

REZENDE, D. A. **Engenharia de** _**software**_ **e sistemas de informação**. 3. ed., rev. e ampl. Rio de Janeiro: Brasport, 2005.

SCHACH, S. **Engenharia de** _**software**_: os paradigmas clássico e orientado a objetos. 7. ed. São Paulo: McGraw-Hill, 2008.

SOMMERVILLE, I. **Engenharia de** _**software**_. 8. ed. São Paulo: Addison Wesley, 2008. 592 p.

WAZLAWICK, R. S. **Engenharia de** _**software**_: conceitos e práticas. Rio de Janeiro: Elsiever, 2013.