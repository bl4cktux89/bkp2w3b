[![](https://ampli-images.s3.amazonaws.com/production/23994e97-0e78-4c80-afd4-8b778652a434/original)](https://ampli-images.s3.amazonaws.com/production/23994e97-0e78-4c80-afd4-8b778652a434/original)

O compartilhamento de recursos refere-se à capacidade do sistema em compartilhar o acesso a quaisquer recursos utilizados por ele entre as máquinas que fazem parte da arquitetura (também chamadas de nós). Esses recursos são, na maioria das vezes, bancos de dados, links de rede que se conectam à internet, serviços de autenticação, entre outros. Apesar de não ser um objetivo exclusivo dos sistemas distribuídos – uma vez que também é um objetivo dos sistemas de rede –, é uma característica muito importante.

A vantagem de compartilhar recursos está na economia financeira, uma vez que, caso não haja tal possibilidade de compartilhamento, mais réplicas de um determinado recurso devem estar presentes em cada nó do sistema, o que impacta direta e indiretamente no custo. Entretanto, como aspecto negativo associado a esse compartilhamento de recursos, temos a questão da segurança, uma vez que o fato de mais máquinas terem acesso ao recurso implica que o sistema possui mais pontos de acesso, os quais podem ser explorados por hackers, tanto no sentido de rastreamento da comunicação quanto na própria questão de invasão de privacidade e integridade dos dados (COULOURIS et al., 2013).

**Confiabilidade**

A análise morfológica da palavra confiabilidade nos mostra que ela se refere à probabilidade de um produto executar a sua função prevista de forma que atenda ou exceda às expectativas, ou seja, está relacionada ao funcionamento adequado, conforme foi planejado. Podemos confundir a confiabilidade como algo relacionado à segurança do sistema, porém não tem relação alguma, conforme observam Colouris et al. (2013).

A confiabilidade nos sistemas distribuídos é maior que nos sistemas centralizados, no entanto qualquer problema relacionado aos processos ou ao canal de comunicação/transmissão pode surtir efeitos diretos sobre a execução do sistema. Podemos observar, na figura abaixo, como ocorre a comunicação entre processos nos sistemas distribuídos, nos quais são aplicados os conceitos de confiabilidade:

[![](https://ampli-images.s3.amazonaws.com/production/d8f1ee4b-ff40-441d-b28d-a79ac8188335/original)](https://ampli-images.s3.amazonaws.com/production/d8f1ee4b-ff40-441d-b28d-a79ac8188335/original)

Comunicação entre processos em um sistema distribuído. Fonte: elaborada pelo autor.

Podemos observar, na figura acima, que, se ocorrer algum problema no canal de comunicação, isso será refletido em todo o processo de comunicação e funcionamento do sistema. A confiabilidade de um sistema é baseada em três pilares: consistência, disponibilidade e resiliência (tolerância a falhas), conforme o Teorema CAP. Esse teorema é baseado nesses pilares, e sua sigla vem das palavras consistência (_consistency_), disponibilidade (_availability_) e tolerância a falhas (_partition tolerance_) (GREINER, 2014). Podemos observar, na figura abaixo, a representação desse teorema.

[![](https://ampli-images.s3.amazonaws.com/production/1d433db4-1a90-4237-9cf8-872c4c3743e7/original)](https://ampli-images.s3.amazonaws.com/production/1d433db4-1a90-4237-9cf8-872c4c3743e7/original)

Representação do Teorema CAP. Fonte: adaptada de Greiner (2014, [s.p.]).

Uma das características importantes do Teorema CAP, a qual pode ser observada na representação da figura acima, é que nunca podemos atingir os três pilares em sua totalidade dentro de um sistema. A forma como foi elaborado permite que você tenha apenas dois dos pilares em evidência em seu sistema, ou seja, caso selecione dois pilares em seu sistema, o terceiro ficará enfraquecido.

[![](https://ampli-images.s3.amazonaws.com/production/3da51071-64a9-4d2a-9682-c7dbf4041ca3/original)](https://ampli-images.s3.amazonaws.com/production/3da51071-64a9-4d2a-9682-c7dbf4041ca3/original)

Disponibilidade e tolerância de partição. Fonte: elaborada pelo autor.

______

**🔁Assimile**

O Teorema CAP consiste em três pilares: consistência, disponibilidade e resiliência (tolerância a falhas). Seu sistema só poderá ter foco em dois deles, e o terceiro será enfraquecido. Por exemplo: se optar por consistência e disponibilidade, seu sistema terá menor resiliência. E assim ocorre em todas as suas combinações e possibilidades.

______

**Desempenho**

Aumentar o desempenho de um sistema também é um objetivo dos sistemas distribuídos. Se fizermos uma comparação, os sistemas distribuídos, na maioria dos casos, apresentam melhor desempenho do que os sistemas centralizados. Isto ocorre porque, em um sistema distribuído, temos múltiplas instâncias, tanto de hardware quanto de software, para realizar o processamento necessário. Como podemos medir esse desempenho?

Conforme Coulouris _et al_. (2013, p. 83), podemos utilizar como parâmetros:

- Tempo de resposta do servidor.
- _Throughput_ (taxa de transferência).
- Quantidade de recursos consumidos pela rede.
- Resultados de _benchmarks_ (execução do sistema).
- Tempo de transmissão dos dados.

Com os resultados das medições dos parâmetros listados, podemos identificar se o sistema distribuído é satisfatório.

Importa destacar que os sistemas distribuídos são mais utilizados em arquiteturas do tipo cliente-servidor, as quais apresentam recursos compartilhados (tanto a nível de hardware quanto a nível de software), a fim de permitir que milhares de clientes tenham acesso a esses recursos e possam utilizá-los como se houvesse uma comunicação direta entre as máquinas e o cliente.

______

**📝****Exemplificando**

A maioria dos jogos multijogadores on-line atuais utiliza a arquitetura cliente-servidor para seu funcionamento. Esse tipo de jogo também é um exemplo de sistema distribuído.

Imagine um jogo on-line de guerra em que você é o jogador X e está enfrentando seu amigo, que é o jogador Y. Você, na verdade, tem três avatares dentro de uma sessão de jogo: o primeiro é o avatar que você está controlando e visualizando em seu dispositivo; o segundo é chamado de imagem autoritária, isto é, a cópia de seu avatar feita pelo servidor do jogo, a qual será enviada para que os outros jogadores possam te “enxergar” dentro do jogo; esse segundo avatar, ao ser enviado aos outros jogadores, funciona como o terceiro avatar, que será visualizado, por exemplo, no jogo do seu amigo. Logo, você movimenta o seu avatar e a sua posição é enviada ao servidor, o qual gera uma cópia com seu posicionamento e transfere-a para o jogador Y. Com isso, temos a arquitetura cliente-servidor em funcionamento.

[![](https://ampli-images.s3.amazonaws.com/production/eca7df29-7e5b-470a-8835-f6c61a9f9071/original)](https://ampli-images.s3.amazonaws.com/production/eca7df29-7e5b-470a-8835-f6c61a9f9071/original)

Exemplo de jogo multijogador on-line. Fonte: Shutterstock.