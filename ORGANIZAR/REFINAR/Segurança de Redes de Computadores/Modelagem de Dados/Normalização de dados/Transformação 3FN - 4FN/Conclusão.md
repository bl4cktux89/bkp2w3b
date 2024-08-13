[![](https://ampli-images.s3.amazonaws.com/production/05370388-cdf6-48b5-8467-d52401cb6f36/original)](https://ampli-images.s3.amazonaws.com/production/05370388-cdf6-48b5-8467-d52401cb6f36/original)

O processo de normalização é importante para ajudar a encontrar problemas na modelagem do banco de dados. Muitas vezes nem percebemos que podemos transformar um campo em uma tabela. E pode ter certeza que o impacto de uma modelagem realizada erroneamente só é percebido após o banco de dados apresentar uma série de problemas. Dessa forma precisamos aplicar as Quatro Formas Normais nas tabelas.

Para criar um banco de dados para o time, você recebeu um documento para servir como base, como mostrado na Figura abaixo. Esse documento servirá de apoio inicial no processo de modelagem do banco de dados.

Nas seções anteriores, a partir do documento foram encontrados os seguintes campos: Número do Jogo, Data do Jogo, Adversário, Estádio, Cidade, UF, Campeonato, Técnico, Placar Final, Jogadores (Número da Camisa, Nome, Número de Gols na Partida), Eventos do Jogo (Tempo, Evento Ocorrido).

**Para aplicar a 1FN devemos inserir a chave primária nas tabelas** _Jogo_, _Adversário, Estádio_.

**Para aplicar a 2FN devemos criar as tabelas** _Cidade_ e _Estado_ e inserir as chaves estrangeiras na tabela _Ficha_.

**Para aplicar a 3FN devemos eliminar todos os campos dependentes**

Surgem aqui as tabelas: _Jogadores_, _Campeonato_, _Técnico_ e _Eventos do Jogo_.

**Para aplicar a 4FN devemos verificar se não há campos multivalorados e não atômicos.**

A tabela _Evento Ocorrido_ aparece nessa etapa, pois os eventos de um jogo se repetem muitas vezes em um jogo e em outros jogos.

O DER desse documento deverá ficar conforme a Figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/b66151cb-b4d9-4ad2-b990-d0239489f9b2/original)](https://ampli-images.s3.amazonaws.com/production/b66151cb-b4d9-4ad2-b990-d0239489f9b2/original)

DER – Ficha de controle. Fonte: elaborada pela autora.

O DER da Figura abaixo precisa de alguns ajustes. Para otimização da imagem os campos foram suprimidos. Agora é hora de finalizar seu trabalho e é com você: utilize uma ferramenta CASE para criar o DER completo das tabelas encontradas (com todos os campos), crie o dicionário de dados das tabelas e crie um slide para apresentar ao seu cliente.

Sucesso!

### **Referências**

ABREU, M. P.; MACHADO, F. N. R. **Projeto de banco de dados**: uma visão prática. 16. ed. rev. e atual. São Paulo: Érica, 2009.

ALVES, W. P. **Banco de Dados**. São Paulo: Saraiva, 2014.

COUGO, P. **Modelagem conceitual e projeto de bancos de dados**. Rio de Janeiro: Elsevier,1997.

CORONEL, C.; ROB, P. **Sistema de banco de dados: projeto, implementação e administração**. São Paulo: Cengage Learning, 2011.

DATE, C. J. **Introdução a sistemas de bancos de dados**. Rio de Janeiro, RJ: Elsevier, 2003.

GUIMARÃES, C. C. **Fundamentos para bancos de dados**: modelagem, projeto e linguagem SQL. Campinas: Ed. da Unicamp, 2003.

KORTH, H. F.; SILBERSCHATZ, A.; SUDARSHAN, S. **Sistema de banco de dados**. 5. ed. São Paulo, SP: Makron, 2006.

HEUSER, Carlos Alberto. **Projeto de Banco de Dados**. 6. ed. Bookman, 2011.

NAVATHE, S. B.; RAMEZ, E. **Sistemas de banco de dados**. 4. ed. São Paulo: Addison Wesley, 2005.