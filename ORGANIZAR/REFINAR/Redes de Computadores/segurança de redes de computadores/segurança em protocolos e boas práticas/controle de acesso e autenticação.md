### **Introdução**

Geralmente, equipamentos de redes, como roteadores, servidores e firewalls trabalham com protocolos e soluções que provem mecanismos que verificam a autenticidade do usuário, realizam a sua autorização e, principalmente, realizam processos de auditoria. E, claro, não podemos esquecer que, para ter acesso aos equipamentos de rede, também é exigido algum nível no controle de acesso.

Tais soluções ficaram conhecidas como AAA (authentication, Autorization and Accountig), que além da sua aplicação as redes locais, também são amplamente utilizadas na Internet de forma a controlar e contabilizar o acesso de usuários à informação e aos recursos da rede.

### Autenticação

O processo de autenticação visa determinar se alguém ou algo é realmente quem ela diz ser. Como é sabido, tais processo são bem comuns em redes privadas e públicas como a Internet. No geral, os processos de autenticação se baseiam em três linhas básicas.

A primeira delas, consiste em fornecer um login, composto de usuário e senha conhecidos previamente pelo usuário. O segundo passa pela posse de algum objeto que forneça a autenticação, como os tokens implementados por smart cards ou cartões de autenticação assíncrono, que também envolve o conhecimento de uma senha. O terceiro tipo utiliza características físicas ou comportamentais do indivíduo para controlar o acesso a partir da comparação de dados biométricos com aqueles previamente armazenados. Veja alguns exemplos de biometria na ilustração abaixo.

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/6/5/316585/index.html)

### Autorização

Dentro do AAA, a Autorização define os direitos e os serviços que o usuário poderá ter acesso dentro da rede, isso vai desde a definição do endereçamento IP até as aplicações e filtros, por exemplo, a definição dos sites que poderá ter acesso.  Além disso, a autorização pode estabelecer as seguintes funções:

- Alocação de privilégios
- Administração de privilégios;
- Registro de privilégios
- Limitações do tipo de acesso;
- Prevenção de acesso não autorizado;
- Revogação de privilégios de acesso.

A autorização especifica o que é permitido ao objeto que autenticou. Esse objeto pode ser um usuário, grupo de usuário ou um computador, com estabelecido, por exemplo, pelas políticas de grupo (GPOs) de domínio do Windows Server, que permite restringir aplicações que podem ser executadas, arquivos e pastas quem podem ser acessados e o controle sobre o próprio domínio (Moraes, A. F. 2010).

### Auditoria

A auditoria ou contabilização é o terceiro A do AAA e permite que informações sobre o acesso dos usuários sejam coletadas e armazenadas em logs para avaliar o consumo da rede pelo usuário, do que e quando foi acessado e, principalmente, conhecer acesso indevidos e diagnosticar ações de hackers.

Geralmente as soluções AAA estão disponíveis de forma integrada. Os ISPs utilizam soluções AAA com objetivo de gerar tarifação aos usuários e gerar logs de acesso (Moraes, A. F. 2010)..

Existem diversas soluções que utilizam soluções AAA, entre elas o RADIUS, Diameter e Kerberos. Essas soluções serão apresentas a seguir.

### RADIUS

Padronizada na RFC 2139, a solução RADIUS foi incialmente aplicada no controle de acesso utilizando equipamentos de acesso remoto conhecidos como NAS (Servidor de acesso a rede), conforme ilustrado na figura que segue. Atualmente, é comum encontrarmos soluções do tipo WPA-enterprise e WPA2-enterprise que utilizam servidores RADIUS para controle de acesso a redes wifi em conjunto com o protocolo 802.1x (CCNA Cybersecurity Operations, 2020). Na figura abaixo é mostrado a troca de mensagens RADIUS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/0/1/310181/19994.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/0/1/310181/19994.png)

Autenticação RADIUS

A partir da figura acima, o processo de autenticação RADIUS ocorre por meio da troca de diversas mensagens com o objetivo de ter acesso a um determinado serviço. Inicialmente, um usuário precisa apresentar suas credenciais ao cliente NAS, por exemplo, através de uma tela de login para fornecimento de usuário e senha.

Depois de receber as credenciais do usuário, o NAS envia um pacote de Requisição de acesso ao servidor RADIUS contendo os atributos como usuário senha, por exemplo.

Na sequência o servidor RADIUS tenta validar o cliente. Se autenticado, o servidor RADIUS consulta um banco de dados para verificar se o usuário possui as permissões necessárias para ter acesso. Do contrário, o servidor RADIUS emite um pacote de acesso negado. E ao receber essa mensagem o cliente NAS desconecta o usuário.

Quando o usuário satisfaz todas as condições, o servidor RADIUS pode enviar pacotes adicionais de Desafio de Acesso que somente o usuário conhece com o objetivo de garantir a identidade. A resposta ao Desafio de acesso é composta por uma Requisição de acesso, tendo o campo com o usuário e senha preenchido com a resposta ao desafio criptografada.

Por fim, o servidor RADIUS envia o pacote do tipo Acesso Aceito contendo informações do serviço a ser oferecido como, por exemplo, tipo de serviço, endereço IP do usuário, tempo de acesso máximo etc (Carvalho, H. E. T. 2008).

### Pacote de dados RADIUS

O pacote RADIUS possui os seguintes campos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/0/4/5/8304598/59438.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/0/4/5/8304598/59438.png)

Cabeçalho RADIUS

- **Código:** Possui tamanho fixo de um byte e é utilizado para identificar qual o tipo de pacote RADIUS, que pode ser:
    - Requisição de acesso (Access-Request)
    - Acesso aceito (Access-Accept)
    - Acesso negado (Access-Reject)
    - Desafio de acesso (Access-Challenge)
- **Identificador:** Possui tamanho fixo de 1 byte e tem a função de identificar as requisições e as respostas trocadas.
- **Comprimento:** Possui tamanho de 2 bytes e é utilizado para informar o tamanho dos pacotes. Para o cálculo do tamanho são incluídos todos os campos de pacote.
- **Autenticador:** Possui 16 bytes de tamanho utilizados para autenticar as respostas nos servidores RADIUS e para o algoritmo de ocultação de senha.
- **Atributos:** Carrega informações sobre autenticação e autorização, como endereços IPs, nome do usuário (suplicantes), endereço IP do cliente e a porta que será utilizada na conexão, dentre outras.

### Características do protocolo RADIUS

- O protocolo RADIUS baseia-se no modelo cliente servidor, permitindo que o servidor RADIUS atenda vários clientes (APs, switches e roteadores) ao mesmo tempo.
- Toda a comunicação entre o servidor e os clientes são autenticadas por chaves secretas compartilhadas e nunca é enviada pela rede.
- Existem mais de 50 atributos para autorização que podem ser utilizados para criar regras de filtragem nos clientes com o objetivo de permitir ou negar acesso de usuários.
- O RADIUS possui mecanismos de Auditoria e Contabilidade que permitem, por exemplo, determinar o início e o fim de uma sessão.

### 802.1x

O protocolo 802.11x é utilizado para proteger a redes a partir de autenticação via acesso a porta que, inicialmente, foi desenvolvido para autenticação em redes cabeadas, mas, atualmente, é bastante utilizado em ambientes Wi-fi.

No padrão 802.1x existem três componentes básicos: um suplicante composto por clientes de software em execução na estação de trabalho wi-fi; o autenticador  composto por um ponto de acesso Wi-fi;  e um servidor de autenticação, geralmente, um servidor RADIUS.

Para autenticação dos suplicantes é utilizado o protocolo EAP (Extensible Authentication Protocol), que passa as informações destes para o servidor de autenticação por meio do cliente Wi-fi (Access-Point), conforme ilustrado na figura abaixo. O Access-point, nesse caso, funciona como um proxy para permitir que o suplicante e o servidor se comuniquem (Intel, 2020).

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/0/9/4/8309448/59703.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/0/9/4/8309448/59703.png)

Processo de autenticação 802.1x

### Simulação - RADIUS e 802.1x

Baixe o arquivo que segue para simulação no Packet Tracer e assista a videoaula que demonstra o funcionamento do protocolo RADIUS em redes wifi WPA2-Enterprise. Para abrir o arquivo você deve ter instalado o Packet Tracer versão 7.3.3 ou superior.

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/1/8/9/7/8189721/aula-12-servidor-radius.pkt)

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/1/8/9/7/8189721/aula-12-servidor-radius.pkt)

### Diameter

O é um protocolo baseado em RADIUS que visa solucionar algumas de suas deficiências: Tem como diferencial a utilização de TCP ou SCTP, em vez de UDP; promove segurança fim-a-fim e não salto-a-salto; Maior possibilidade de atributos e de identificadores que permite um controle melhor sobre as mensagens de erros evitando, por exemplo, o descarte silencioso do RADIUS.

**CURIOSIDADE**

O nome do DIAMETER vem de uma brincadeira com o nome do seu antecessor o RADIUS, pois o diâmetro é o dobro do raio. O novo protocolo não é totalmente compatível com o RADIUS, mas apresenta muitas semelhanças no que se refere às funcionalidades do RADIUS.

### Kerberos

Protocolo definido pela RFC 1510 utilizado para autenticação de rede que utiliza criptografia de chave simétrica, sendo ele integrado aos sistemas operacionais Windows, Apple OS, Linux e FreeBSD.

Funcionamento do Kerberos

O Kerberos funciona a partir da requisição de um ticket encriptado para a autenticação. O processo de autenticação é descrito abaixo (Moraes, A. F. 2010).:

1. Para iniciar uma autenticação Kerberos, o cliente envia uma solicitação para o servidor de autenticação AS do Kerberos, indicando o ticket que é composto pelo usuário e senha
2. O AS Kerberos examina o ticket para verificar a identidade do usuário e cria uma chave de sessão. A chave de sessão é conhecida como TGT (ticket-granting ticket), ou simplesmente ticket de concessão.
3. De posse da TGT, o usuário a envia para o servidor de concessão de ticket (TGS). O TGS devolve o ticket que, agora, deve ser enviado a o servidor para requisitar o serviço, podendo ele aceitar ou rejeitar.
4. O ticket possui um carimbo de tempo (timestamp) para ser utilizado pelo usuário por um determinado tempo, devendo ser reautenticado sempre que expirar esse tempo.

O processo de autenticação é resumido na figura abaixo

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/4/3/8314351/59441.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/4/3/8314351/59441.png)

Processo de autenticação Kerberos

Fonte: https://www.3way.com.br/protocolo-kerberos/

**CURIOSIDADE**

O Kerberos foi originalmente desenvolvido para o Projeto Athena no Massachusetts Institute of Technology (MIT). O nome Kerberos foi retirado da mitologia grega; Kerberos (Cerberus) era um cão de três cabeças que guardava os portões de Hades. As três cabeças do protocolo Kerberos representam um cliente, um servidor e um Key Distribution Center (KDC), que atua como o serviço de autenticação de terceiros confiável do Kerberos.

### TACACS e TACACS+

O TACACS (Terminal Access Controller Access-Control System) foi definido na RFC 1492 em 1990 e atualmente não é mais utilizado. Entretanto, a Cisco System desenvolveu a o TACACS+ em 1997. O TACACS+ separa o processo de autenticação e autorização e foi otimizado para controle de comandos de configuração e monitoramento de equipamentos de redes, em oposição ao RADIUS, mais voltado para o controle de acesso de serviços de rede.

**SAIBA MAIS...**

Para saber mais sobre a aplicação do TACACS e RADIUS acesse o site: [**https://www.cisco.com/c/pt_br/support/docs/security-vpn/remote-authentication-dial-user-service-radius/13838-10.html**](https://www.cisco.com/c/pt_br/support/docs/security-vpn/remote-authentication-dial-user-service-radius/13838-10.html)