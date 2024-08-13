[![](https://ampli-images.s3.amazonaws.com/production/19b334b4-b46f-4a3f-9c2f-cfb6f98ec0c9/original)](https://ampli-images.s3.amazonaws.com/production/19b334b4-b46f-4a3f-9c2f-cfb6f98ec0c9/original)

O modelo cliente-servidor é o modelo de computação distribuída em que um programa é dividido em duas partes: servidor e cliente (COULOURIS _et al_., 2013.; KUROSE; ROSS, 2013). O servidor é executado em um processo, e o cliente, em outro processo diferente, que pode estar na mesma máquina ou em uma máquina remota. O servidor tem acesso direto ao recurso de hardware ou software que o cliente quer usar. Na maioria dos casos, o cliente está localizado em diferentes máquinas clientes.

Tipicamente, há um relacionamento muitos-para-um entre o servidor e os clientes, isto é, há, geralmente, um servidor atendendo às requisições de muitos clientes. O servidor é o mediador do acesso a grandes bases de dados, a um recurso de hardware caro ou a uma coleção importante de aplicações. O cliente faz requisições para ter acesso a dados e obter o resultado de um cálculo e outros tipos de processamento. A figura a seguir ilustra o funcionamento de um sistema cliente-servidor, no qual há um conjunto de processos cliente enviando requisições para o processo servidor, que é o responsável por realizar as computações necessárias e responder aos clientes.

Supondo que o servidor implementa a soma de dois valores, um cliente envia dois valores, e o servidor realiza a soma e retorna o valor resultante.

[![](https://ampli-images.s3.amazonaws.com/production/f08ec1bc-6713-4d82-a690-75a6ca4faae6/original)](https://ampli-images.s3.amazonaws.com/production/f08ec1bc-6713-4d82-a690-75a6ca4faae6/original)

Modelo cliente-servidor. Fonte: elaborada pela autora.

Outro exemplo é uma máquina de busca no modelo cliente-servidor, que é usada para localizar informação na internet ou em intranets corporativas e organizacionais. Neste caso, o processo cliente é executado no navegador para obter a palavra-chave ou frase sobre o tema que o usuário está interessado. O processo cliente envia a requisição para o servidor.

O processo servidor, por sua vez, realiza uma ampla busca pela palavra-chave ou frase do usuário, pois este tem acesso direto à informação ou a outros servidores que têm acesso à informação. Posteriormente, o servidor retorna as informações ao cliente. Embora os processos cliente e servidor sejam programas separados em computadores diferentes, eles trabalham em uma única aplicação. Quando o processo pode funcionar como cliente e servidor ao mesmo tempo, temos um sistema _Peer-to-Peer_ (P2P).

______

**🔁Assimile**

No contexto de comunicação entre um par de processos, o processo que inicia a comunicação é o cliente, e o processo que espera pela requisição é o servidor. Na web, o navegador é o processo cliente, e o servidor web é o processo servidor (KUROSE; ROSS, 2013).