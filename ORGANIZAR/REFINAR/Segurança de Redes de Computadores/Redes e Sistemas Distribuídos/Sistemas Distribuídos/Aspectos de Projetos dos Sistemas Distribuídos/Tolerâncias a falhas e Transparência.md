[![](https://ampli-images.s3.amazonaws.com/production/0e27be17-67b5-4cda-9998-0f00d949b4a3/original)](https://ampli-images.s3.amazonaws.com/production/0e27be17-67b5-4cda-9998-0f00d949b4a3/original)

Tolerância a falhas refere-se à capacidade de o sistema distribuído se autorrecuperar na ocorrência de uma ou mais falhas. As falhas em um sistema computacional podem ocorrer em vários momentos ao longo do uso de um sistema, por uma série de razões, as quais serão detalhadas mais adiante. Aproveitando, você sabia que, no nosso idioma, existe uma palavra para expressar essa ideia de “capacidade do sistema distribuído se autorrecuperar na ocorrência de uma ou mais falhas”? Isso mesmo, apenas uma palavra: resiliência. Então, da próxima vez que quiser passar essa ideia de maneira mais concisa, utilize-a.

Quando falamos de aspectos no projeto de sistemas distribuídos, temos que falar de resiliência de processos, pois é um dos principais objetivos a serem atingidos em uma aplicação distribuída. A resiliência de processos está relacionada com o sistema ter uma comunicação confiável entre as camadas de cliente e servidor. Sua ideia básica é de que os processos da nossa aplicação sejam replicados em grupos, isso faz com que o sistema tenha uma proteção contra falhas relacionadas a processos.

Para conseguir criar projetos tolerantes a falhas, temos que ter em nossos sistemas uma detecção de falhas, assim como conseguir mascarar todas as falhas apresentadas e a replicação de nosso sistema, para que ela seja imperceptível. Só podemos atingir estas características de acordo com questões de projetos, e a mais importante, neste caso, é verificar qual grupo de processos que a nossa aplicação deverá conter. Para isso, entenderemos o que são os grupos simples e os grupos hierárquicos e como esses processos são associados a eles.

Quando falamos de resiliência de processos, organizamos em grupos os processos que são considerados idênticos. Portanto, quando uma mensagem é enviada a um grupo de nosso sistema, a ideia é que todos os processos membros desse grupo recebam a mensagem. Se ocorrer uma falha em um dos processos no tratamento da mensagem, outro processo desse grupo deve tratar a mensagem no lugar do processo com falha.

Em um sistema distribuído, temos grupos dinâmicos, ou seja, os processos podem se mover entre os grupos que são criados. Um processo de um cadastro de usuário do site XYZ pode enviar uma mensagem para a realização do cadastro a um grupo de servidores sem precisar quantos existem e quem são eles.

**Grupo simples e grupo hierárquico**

Quando falamos de grupos simples, todos os processos são iguais e todas as decisões são tomadas entre todos os processos, ou seja, de forma coletiva. A grande vantagem deste tipo de grupo é que não há um ponto único para falha. Mesmo que ocorra falha ou caia algum processo, o grupo continua mantendo o serviço em funcionamento. Portanto, a execução do sistema não é centralizada em um só ponto.

A desvantagem que encontramos nesse tipo de grupo é que a tomada de decisão tende a demorar mais, porque cada decisão deve ser priorizada pelos processos, tendo uma votação antes da tomada de decisão.

Já os grupos hierárquicos, como o nome mesmo já diz, são baseados em uma hierarquia, logo existem processos considerados mais importantes e que controlam toda execução. Nesses grupos, temos um processo chamado “coordenador”, e os demais chamamos de “operários”. Sempre que chega uma nova requisição no sistema, ela é enviada ao processo coordenador, que decide o melhor operário para executá-la.

A grande vantagem desse tipo de grupo é que as decisões são centralizadas, portanto temos mais agilidade na tomada de decisão, o que gera um retorno mais rápido. Já a grande desvantagem apontada é que, caso ocorra uma falha no processo coordenador, o serviço todo para.

Podemos observar, na figura abaixo, a estrutura dos grupos apresentados e como seus processos se comunicam.

[![](https://ampli-images.s3.amazonaws.com/production/61436854-dcab-4274-ae04-a3d0d7732daf/original)](https://ampli-images.s3.amazonaws.com/production/61436854-dcab-4274-ae04-a3d0d7732daf/original)

Estrutura dos grupos e comunicação dos processos. Fonte: elaborada pelo autor.

Podemos observar que, na comunicação simples, os processos se comunicam entre si e decidem em conjunto qual é o processo mais adequado para executar determinada ação durante o funcionamento de um sistema. Já na comunicação hierárquica, os processos estão divididos entre “coordenador” e “operários”, em que o processo coordenador definirá o processo operário mais adequado para executar determinada ação durante o funcionamento de um sistema.

**Transparência**

Por fim, transparência refere-se, novamente, ao ponto de vista do usuário, o quão transparente o sistema é, ou seja, quanto o cliente “desconhece” do funcionamento interno do sistema, e isso é uma característica positiva: quanto menos o usuário necessitar saber da implementação e do funcionamento do sistema, ou seja, quanto mais transparente o sistema for, melhor para o usuário.

Na tabela abaixo, podemos observar os tipos de transparência, segundo Tanenbaum e Steen (2008):

[![](https://ampli-images.s3.amazonaws.com/production/2c1a22c8-560c-4033-b495-5e234b34498b/original)](https://ampli-images.s3.amazonaws.com/production/2c1a22c8-560c-4033-b495-5e234b34498b/original)

Tipos de transparência. Fonte: elaborada pelo autor.