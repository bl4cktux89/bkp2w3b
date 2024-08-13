### Introdução

Muitas vezes, os roteadores e switches não podem ser acessados localmente por meio de uma interface conhecida como console, que é mostrada na Simulação 1. A interface console é útil quando o dispositivo vem com configuração fábrica e que, portanto, é preciso estabelecer as configurações básicas. Uma vez estabelecida as configurações básicas, é possível liberar o acesso para configuração via terminal remoto usando, por exemplo, uma sessão TELNET ou fazer uso do protocolo SSH (Secure Shell, Shell seguro). Por meio desses protocolos é possível estabelecer configuração e consulta aos dispositivos mesmo estando geograficamente separados, conforme ilustrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/4/6/1784662/39715.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/8/4/6/1784662/39715.png)

### TELNET

O TELNET (TErminal NETwork) é uma aplicação TCP/IP padrão para serviços de terminal virtual que permite que o terminal local estabeleça uma conexão virtual com um terminal remoto de tal forma que o terminal remoto se comporte como um terminal local.

O TELNET foi desenvolvido em uma época em que os grandes computadores funcionavam em um ambiente de tempo compartilhado. Nesse ambiente, os grandes computadores suportavam vários usuários simultaneamente. A iteração entre os clientes e computador ocorria sempre de forma remota através do terminal, composto apenas de teclado, mouse e monitor.

O usuário, para se conectar a uma sessão de terminal precisa, normalmente, de um usuário e uma senha, realizando dessa forma o login local. Parece simples, mas se estamos lidando com sistemas heterogêneos, temos que saber primeiro que tipo de computador estamos acessando e instalar um emulador de terminal específico para aquele computador.

O TELNET soluciona essa questão definindo uma interface universal denominado conjunto de caracteres NVT (Network Virtual Terminal, Terminal Virtual de Rede). Por meio dessa interface o cliente TELNET converte os caracteres (dados ou comandos) proveniente do terminal do usuário e os converte para o formato NVT e na sequência, os transmite pela rede. No dispositivo remoto, por exemplo, um roteador, converte os dados e comandos do formato NVT para o formato aceito localmente (Forouzan, B. A, 2010).

### Fluxo de dados

O TELNET emprega conexão TCP para estabelecimento de conexão entre o dispositivo local e o remoto. O servidor (roteador ou switch) usa a porta 23, enquanto que o cliente TELNET utiliza uma porta acima de 1023. A mesma conexão é utilizada para transmitir dados e controle, diferentemente do que ocorre em uma transmissão com o protocolo FTP (usa conexão de dados e controle). O TELNET faz isso transmitindo caracteres de controle juntamente com o fluxo de dados. Para distinguir um do outro, cada sequência de caracteres de controle é precedida por um caractere especial denominado IAC (Interpret As Control, Interpretar como controle). Veja abaixo uma simulação de conexão ao roteador via TELNET (Forouzan, B. A, 2010).

Acesso remoto via SSH

### SSH (Secure Shell)

O protocolo TELNET possui uma grande deficiência. Usuários mal-intencionados podem estar “escutando” a rede e capturar os logins e senhas, além de dados sigilosos, já que os comandos remotos via TELNET são transportados em texto claro. O SSH procura solucionar os problemas de escuta com o emprego de conexões criptografadas e com o uso de protocolos de autenticação mais seguros, realizando o seu transporte na porta TCP de número 22, enquanto que o TELNET é 23. O SSH proporciona os seguintes mecanismos de segurança:

- Depois de uma conexão inicial, o cliente pode verificar se realmente está conectado ao mesmo servidor que se conectou anteriormente.
- O cliente transmite as informações de autenticação ao servidor usando uma encriptação robusta de 128 bits.
- Todos os dados enviados e recebidos durante a sessão são transferidos por meio de encriptação de 128 bits, extremamente difícil de se decifrar.
- A comunicação utiliza chaves pública/privada RSA ou DES (64 bits).
- A integridade dos dados transmitidos é garantida por verificações do tipo MD5 ou SHA-1

Além da substituição do TELNET, o SSH pode substituir também a conexão FTP, rologin, sh e rcp. A sua implementação é suportada em diversas plataformas: MacOS, UNIX/Linux e Windows. Para utilizar o SSH você pode utilizar os programas Tunnelier ou Putty, que você encontra facilmente para download. Na simulação a seguir você aprenderá como configurar o acesso via SSH no roteador.