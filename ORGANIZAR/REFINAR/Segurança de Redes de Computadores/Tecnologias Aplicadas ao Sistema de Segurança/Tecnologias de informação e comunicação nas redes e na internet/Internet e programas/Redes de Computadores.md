[![](https://ampli-images.s3.amazonaws.com/production/c4673c84-303b-49d3-830b-557c5bf06cb2/original)](https://ampli-images.s3.amazonaws.com/production/c4673c84-303b-49d3-830b-557c5bf06cb2/original)

Você já percebeu o quanto dependemos da troca de dados entre sistemas computacionais? Experimente deslogar seu celular por algumas horas: certamente você vai perceber o quanto a falta dessa troca de dados será sentida. Pois é, vem sendo assim há muito tempo.

A necessidade de comunicação a distância é bem mais antiga que os computadores, e não é de espantar que, quando os primeiros computadores comerciais foram instalados, seus operadores passaram a desejar que se comunicassem. A troca de dados entre computadores é, de fato, um dos alicerces da sociedade moderna.

Vamos conhecer um pouco mais de perto as características das redes de computadores e da internet, a mais importante dessas redes.

Tanenbaum (2011) define **redes de computadores** como **um conjunto de dois ou mais computadores autônomos**, isto é, que podem operar independentemente um do outro, que são interconectados por uma tecnologia qualquer que lhes permite trocar dados.

As tecnologias são variadas para a interconexão de computadores e espelham os meios que vêm sendo usados em telecomunicações:

[![](https://ampli-images.s3.amazonaws.com/production/1568ef26-f014-499c-a6c2-29b15a5f969a/original)](https://ampli-images.s3.amazonaws.com/production/1568ef26-f014-499c-a6c2-29b15a5f969a/original)

Meios de utilização da tecnologia em telecomunicações. Fonte: o autor.

A conexão dos computadores pode ser realizada de várias formas, chamadas “topologias”. As topologias mais comuns em redes de computadores são representadas na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/f5830839-06db-463d-889f-67e979b550ca/original)](https://ampli-images.s3.amazonaws.com/production/f5830839-06db-463d-889f-67e979b550ca/original)

Principais topologias de redes de computadores. Fonte: adaptada de Paulino (2010).

As características de cada uma das topologias apresentadas na figura anterior são as seguintes (PAULINO, 2010):

- **anel** – os dados passam de computador a computador até chegar ao seu destino. Um pacote de dados especial chamado _token_ é constantemente transportado no ciclo do anel (passando por todos os computadores), e, quando o _token_ está no estado livre, qualquer computador pode tomá-lo, marcando-o como em uso e a ele anexar um conjunto de dados para um computador de destino. As redes baseadas nessa topologia são chamadas de redes _token ring_;
- **malha** – alguns computadores têm conexão direta com outros, mas não com todos. Nesta topologia, cada computador tem uma árvore de roteamento, isto é, um mapa dizendo que computador está conectado com quais outros computadores. Dessa forma, quando o computador A quer enviar dados para o computador B, passa esses dados, junto com o endereço de destino, para o computador mais próximo ao destino com o qual tenha conexão;
- **estrela** – todos os computadores estão conectados a um computador central, que faz o roteamento dos pacotes da origem para o destino;
- **linha** – funciona como o anel, porém sem completar o ciclo;
- **árvore** – um computador recebe conexão de apenas um outro, mas pode se conectar com mais de um no caminho “para cima”. O resultado é um sistema de ramificação que se assemelha a uma árvore;
- **barramento** – topologia mais comum em redes de pequeno porte (redes locais). Todos os computadores estão conectados entre si por meio de um barramento (um cabo), com um mecanismo de ocupação do barramento permitindo que este seja utilizado sem que haja confusão nas comunicações.