[![](https://ampli-images.s3.amazonaws.com/production/fd623971-5225-4271-bf59-fe2547929bbc/original)](https://ampli-images.s3.amazonaws.com/production/fd623971-5225-4271-bf59-fe2547929bbc/original)

Escalabilidade é um termo comum em redes de computadores e está relacionado à capacidade de o sistema poder ser escalável, ou seja, ampliado ou reduzido para suportar, por exemplo, uma maior quantidade de acessos simultâneos ou realizar uma tarefa mais rapidamente (ao ampliarmos a capacidade de processamento desse sistema). Perceba como algumas metas podem estar inter-relacionadas nos sistemas distribuídos, como é o caso da escalabilidade e da concorrência.

Por exemplo, quando uma empresa de games necessita aumentar a quantidade de servidores de um determinado jogo on-line para possibilitar uma maior quantidade de jogadores em uma partida _multiplayer_, ela está escalando o sistema (nesse exemplo, aumentando a escala dele).

______

**📝****Exemplificando**

Imagine um site de comércio eletrônico no período de promoções, por exemplo, no dia da _Black Friday_. O sistema deverá ser escalável para permitir picos de acesso simultâneo, dessa forma, uma das maneiras é aumentar a quantidade de nós/servidores, para que não inviabilize o negócio, deixando o sistema indisponível.

______

Segundo Tanenbaum e Steen (2008), um sistema cujo desempenho aumenta com o acréscimo de hardware e software, proporcionalmente à capacidade acrescida, é chamado escalável.

É importante notar, entretanto, que um sistema dito escalável permite que se aumente ou diminua a quantidade de recursos. Você deve estar se perguntando: por que eu diminuiria a capacidade do meu sistema?

______

**📝****Exemplificando**

Imagine a seguinte situação: você criou uma aplicação web que distribui conteúdo em vídeo para preparar estudantes para fazerem a prova do ENEM. Você roda essa aplicação, de maneira replicada, em um conjunto de servidores em nuvem de algum provedor de _cloud computing_ conhecido do mercado, digamos, com dez nós. Apesar de a ideia ser excelente, você nota que a quantidade de usuários que utiliza sua plataforma cai drasticamente entre os meses de novembro e junho, uma vez que os estudantes, normalmente, começam a se preparar para esse exame – que ocorre anualmente entre outubro e novembro – a partir de julho, quando estão de férias. Supondo que você paga para esse provedor de _cloud computing_ R$ 150,00 mensais, para que este disponibilize os dez nós de maneira contínua. Não seria interessante que, nos meses de menor demanda, você diminuísse a quantidade de servidores pela metade, por exemplo, e pagasse a quantia de R$ 75,00 mensais nesse período? Nesse cenário, sua economia seria de R$ 600,00, que você poderia investir em outros projetos. Esse é um exemplo típico de escalabilidade “para baixo”.

______

Dentre os termos relacionados ao escalonamento, temos dois muito utilizados: escalonamento horizontal e escalonamento vertical.

______

**🔁Assimile**

O escalonamento horizontal possibilita o aumento de máquinas, tais como servidores, assim há uma divisão da carga de trabalho entre eles, não sobrecarregando um servidor específico. No sistema _e-commerce_, em que temos os picos de acessos dos clientes simultaneamente, esse tipo de escalonamento é muito utilizado em sistemas distribuídos e em nuvem.

Já o escalonamento vertical permite aumentar recursos de processamento, como CPU e memória em máquinas existentes. Quando se deseja maior desempenho, ou na ocorrência de falhas de uma CPU, essa pode ser uma abordagem importante.

______

Dois aspectos importantes a serem levados em consideração em relação à escalabilidade são em termos geográficos e administrativos.

Escalabilidade em termos geográficos refere-se ao sistema, o qual, apesar de se apresentar como único para o usuário, está rodando em várias réplicas, em dois ou mais data centers geograficamente distintos. Podemos, por exemplo, utilizar um determinado provedor de _cloud computing_ que possua data centers no estado de São Paulo, no Brasil, e no estado do Arizona, nos EUA. A figura abaixo ilustra tal cenário.

[![](https://ampli-images.s3.amazonaws.com/production/7cb4d808-8e86-4072-b05c-8fb203e57630/original)](https://ampli-images.s3.amazonaws.com/production/7cb4d808-8e86-4072-b05c-8fb203e57630/original)

Exemplo de escalabilidade geográfica. Fonte: elaborada pelo autor.

O benefício desse tipo de configuração é fornecer uma melhor experiência, em termos de conectividade e latência (atrasos na rede), para os usuários. Aqueles que estão mais próximos do Hemisfério Norte podem acessar a aplicação através dos data centers nos EUA, enquanto os usuários do Hemisfério Sul podem acessar a aplicação através dos data centers no Brasil.

Outra vantagem é que, na ocorrência de um desastre, por exemplo, um furacão passar pelo Arizona, que comprometa o data center, todos os usuários poderão acessá-lo de outra localidade, incluindo os usuários mais próximos ao data center atingido (ainda que a usabilidade, do ponto de vista desses usuários, seja ligeiramente comprometida, devido a uma maior distância desse data center).

Escalabilidade em termos administrativos, refere-se ao escopo administrativo, que é afetado pela escalabilidade geográfica e é um conceito bastante simples de ser compreendido, embora muitas vezes ignorado. Imagine que, no cenário da figura acima, os links de comunicação do lado dos EUA sejam fornecidos por provedores de internet daquela região, ao passo que os links de comunicação no lado do Brasil sejam fornecidos por provedores de internet daqui.

Caso o link no lado dos EUA fique indisponível, não adiantará entrar em contato com o provedor de internet daqui do Brasil, pois é uma empresa diferente da que fornece o serviço nos EUA, administrativamente falando. Portanto, o escopo administrativo foi inerentemente ampliado, o que significa que o responsável pelo sistema distribuído terá mais trabalho para administrá-lo, incluindo, por exemplo, a necessidade de abrir um chamado de suporte técnico em outro idioma.

______

**📝****Exemplificando**

A escalabilidade pode ser alterada, isto é, aumentada ou diminuída, de maneira automatizada, sem a intervenção do desenvolvedor, por meio de ferramentas, como Chef e Ansible. Podemos exemplificar a função de ambas as ferramentas em um cenário de um portal de notícias, que tem, durante a madrugada, baixa demanda de acessos. As ferramentas exercem o papel de diminuir automaticamente os recursos utilizados. Em outro exemplo, quando sai uma notícia muito esperada e os acessos ao portal sobem drasticamente, as ferramentas exercem o papel de aumentar os recursos disponibilizados para garantir o bom funcionamento.