[![](https://ampli-images.s3.amazonaws.com/production/bb098499-cc08-410c-a517-be7f36606203/original)](https://ampli-images.s3.amazonaws.com/production/bb098499-cc08-410c-a517-be7f36606203/original)

Você recebeu um documento como base para criar um banco de dados. Isso é comum? Sim e é muito comum! Os documentos são ótimos, pois a partir deles podemos realmente saber o que é utilizado pelos clientes. E, é justamente na hora de modelar um banco de dados a partir de um documento que a normalização deve ser empregada.

Para relembrar, o clube de futebol precisa agilizar as estatísticas sobre a atuação do time nos campeonatos que participa. Precisa também verificar o desempenho de cada jogador. Como aplicar a Primeira Forma Normal e a Segunda Forma Normal nas tabelas que foram encontradas a partir do documento?

Para ajudar na solução, os campos encontrados sobre cada jogo são: Número do Jogo, Data do Jogo, Adversário, Estádio, Cidade, UF, Campeonato, Técnico, Placar Final, Jogadores (Número da Camisa, Nome, Número de Gols na Partida), Eventos do Jogo (Tempo, Evento Ocorrido).

Para aplicar a Primeira Forma Normal devemos primeiro inserir uma chave primária na tabela Jogo, nesse caso o melhor campo  para ser chave primária seria o Número do Jogo. A tabela _Jogo_ ficará assim: Jogo (**\#NúmerodoJogo**, Data do Jogo, Adversário, Estádio, Cidade, UF, Campeonato, Técnico, Placar Final, Jogadores (Número da Camisa, Nome, Número de Gols na Partida), Eventos do Jogo (Tempo, Evento Ocorrido).

Você consegue visualizar novas tabelas “escondidas como campos” na tabela _Jogo_?

Utilize uma ferramenta gráfica e comece a elaborar o diagrama.