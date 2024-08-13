**Definição**

O _**Border Gateway Protocol**_ (BGP) é um protocolo de roteamento criado para ser utilizado entre ISPs (_**Internet Service Providers**_) – ou seja, as empresas que fornecem acesso à Internet, como a NET© e a Vivo©, por exemplo. De fato, o BGP é o único protocolo de roteamento classificado como EGP (_**Exterior Gateway Protocol**_), sendo esse “exterior” referente à Internet. Os demais protocolos de roteamento, como o RIP e o OSFP são classificados como IGP (_**Interior Gateway Protocol**_), sendo esse “interior” referente ao uso em roteadores dentro de uma residência ou de uma empresa, que seja cliente de um ISP.

A Figura 1 ilustra o uso do BGP, destacado nos links em vermelho, para conectar diferentes provedores (ISPs) entre si que, por sua vez, fornecem seus serviços tanto a clientes residenciais (pessoas físicas), quanto corporativos (pessoas jurídicas). Cada provedor é representado por uma nuvem menor (em azul, na figura), que internamente utiliza protocolos IGP. A conexão entre provedores é realizada pelo BGP. Nesse contexto, a Internet é o conjunto de todos esses provedores, representada na figura pela nuvem maior.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/4/2709429/41194.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/4/2709429/41194.png)

**Vetor de distância**

Assim como o RIP, o BGP utiliza um algoritmo de vetor de distância, porém sua métrica envolve vários parâmetros (treze, mais precisamente), dentre elas o caminho para rotas entre vizinhos externos e internos ao ISP (chamados de _**Autonomous System –**_ AS) e regras definidas pelo próprio ISP, de acordo com contratos e parcerias estabelecidas entre outros ISPs, que estão fora do escopo dessa disciplina.

Em termos de protocolos de roteamento, métrica (também chamado de “custo” da rota) é um valor numérico associado a um determinado protocolo, que determina o quão melhor uma rota (caminho que um pacote pode utilizar para atingir o destino) é em relação a outra.

**Princípio de funcionamento**

O BGP é um protocolo que, por ser utilizado para roteamento da Internet, não estabelece vizinhos automaticamente, através de troca de mensagem “hello”, como acontece com protocolos IGPs (OSPF e EIGRP, por exemplo). Em vez disso, cada roteador vizinho deve ser configurado manualmente, para definição correta e principalmente garantia de que somente o(s) endereço(s) IP contratado(s) pelo cliente será(ão) propagado (DONAHUE, 2011).

Outro aspecto é que, como a tabela de roteamento de roteadores rodando o BGP possui centenas de milhares de rotas, implica que a convergência do BGP é, propositadamente, mais lenta (se comparada a protocolos IGP).

Convergência, nesse contexto, refere-se a mudança na topologia, como quando uma rota deixa de existir e um caminho alternativo deve ser utilizado pelo roteador.

Pense bem: com milhares de roteadores na internet, é comum que algumas rotas fiquem indisponíveis temporariamente, por tráfego excessivo, por exemplo. Assim, imagine a seguinte situação: caso uma única interface de um único roteador da Internet fique, momentaneamente, alternando entre indisponível e disponível, digamos umas 10 vezes durante 2 segundos, essas alterações precisariam ser propagadas por todos os milhares de roteadores que formam a Internet. Dá para imaginar o efeito devastador que isso causaria, não?

O BGP possui mecanismos para, através de sua configuração, colocar uma interface que fica alternando entre disponível e indisponível em uma espécie de quarentena, de forma que essa interface só passe a participar ativamente da topologia após determinado período, configurável; por exemplo, após 30 min.

Além disso, as atualizações de rotas devido a mudanças na topologia não são enviadas automaticamente, mas sim em lote (batch) que, por padrão, são enviadas a cada 5 segundos para roteadores internos ao _**Autonomous System**_, e a cada 30 segundos, para roteadores externos ao _**Autonomous System**_.

**Vídeo explicativo**

A título de complementação, e para entender melhor como o BGP se “encaixa” na internet, recomendamos assistir ao vídeo abaixo (NIC.BR, 2014):

[https://www.youtube.com/watch?v=C5qNAT_j63M](https://www.youtube.com/watch?v=C5qNAT_j63M)

**Conclusão**

Neste capítulo apresentamos a definição do termo BGP, sua aplicação, bem como seu princípio de funcionamento.