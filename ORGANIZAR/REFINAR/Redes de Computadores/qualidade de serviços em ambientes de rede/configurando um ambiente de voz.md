**Antes de começar**

Passo a você, caro aluno, alguns comandos básicos para a configuração de um serviço VOIP.

Está sendo considerado aqui que o básico do funcionamento do _**packet tracer**_ já é de seu conhecimento por ser uma ferramenta amplamente utilizada em semestres anteriores. Ou seja, comandos básicos para arrastar/soltar um elemento na tela, como entrar na CLI para configurar, já são de conhecimento do aluno. Caso contrário, recomendo que faça um treinamento básico nessa ferramenta. Pesquisando, você irá encontrar facilmente dicas de operação desse software.

Nessa aula, configuraremos:

1. Um gerenciador expresso de chamadas (Call Manager Express) em umroteador 2811.
2. Inserção de alguns telefones na rede.
3. Configuração desses equipamentos.
4. Conexão desses telefones IP e seus testes na rede.

Vamos começar?

**Configurando um ambiente****de telefonia IP**

Começamos apresentando a figura 01 a seguir, que apresenta o cenário no qual iremos trabalhar. Analise calmamente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119272/a14i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119272/a14i01_quasar80_100.jpg)

Figura 01: Cenário VOIP a ser construído

Agora vamos seguir os passos adiante:

1. Configurar a interface Fastethernet 0/0 e o serviço DHCP no roteador 2811:

1. Configure o "Call Manager Express" serviço de telefone no RouterA para habilitar o serviço VoIP na rede.

1. Configurar um VlanVoice no Switch A para separar o sistema de voz em relação ao tráfego de dados. Nesse caso, vamos utilizar apenas a Vlan 1, mas se tivéssemos dados trafegando, aí sim criaríamos também a Vlan 2 para separar essesdois tráfegos.

1. Configurar o "phone directory" para o IP Phone 1, necessitando também configurar o CME do RouterA, para associar o número com esse telefone.

1. Agora é só confirmar a configuração. Certifique-se que o telefone IP recebeu um IP e o número do telefone 54001 vindo do RouterA (coloque apenas o mouse sobre o telefone IP). Observe a figura 02:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119273/a14i02_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119273/a14i02_quasar80_100.jpg)

Figura 02: Informações do telefone IP

Existem diversos links que ensinam a configurar sistemas de voz. Eu tomei como base o linkdo Profº. Marcelo, disponível em: <[**http://www.dltec.com.br/blog/ cisco/telefonia-ip-basica-e-cme-com-packet-tracer-ccna-voice/**](http://www.dltec.com.br/blog/%20cisco/telefonia-ip-basica-e-cme-com-packet-tracer-ccna-voice/)>. Acesso em: 13 mar. 2013.