### **Introdução**

As redes sem fio ganharam muita popularidade em ambientes residenciais e, agora, em ambientes corporativos. Isso se deve, principalmente, as características de baixo custo, facilidade de implantação e a alta mobilidade. Por outro lado, a segurança é o ponto fraco deste tipo de rede, por um motivo simples - O meio de transmissão é compartilhado!

Ao mesmo tempo, sinais provenientes de diferentes redes podem disputar o acesso ao meio, afetando a transmissão e também a segurança, tendo em vista que, através de escâneres simples de rede é possível adquirir informações sobre a rede, tais como, nome da rede, tipo de mecanismo de segurança etc. Ao passo que, através de ataques mais sofisticados é possível, por exemplo, substituir pontos de acesso legítimos por falso, redirecionar tráfego e a análise e captura do tráfego de forma indevida.

Neste tipo de rede, talvez mais do que qualquer outro tipo de rede, as boas práticas são ainda mais importantes por se tratar de um meio de transmissão compartilhado.

![[Untitled 91.png|Untitled 91.png]]

### **Visão geral das redes sem fio**

Quando pensamos em redes sem fio, logo vem à mente o padrão wireless IEEE 802.11x para construção das redes WLAN (Redes Locais Sem Fio), mas não podemos esquecer que essa é apenas um dos vários tipos de rede sem fio. Temos as redes via infravermelho, redes bluetooth, celular, Wimax etc. E claro, todas elas possuem suas vulnerabilidades, que, quando exploradas, podem provocar sérios danos. Na figura abaixo é mostrado a comparação entre alguns desses padrões.

**SAIBA MAIS...**

Atualmente, existem alguns ataques que exploram as vulnerabilidades do Bluetooth (IEEE 802.15.1) dentre eles, o [**KNOB attack**](https://mundoconectado.com.br/noticias/v/10108/nova-vulnerabilidade-do-bluetooth-knob-attack-deixa-dispositivos-abertos-a-ataques) e os ataques que exploram um conjunto de vulnerabilidades conhecido como [**BlueBorne**](https://tecnoblog.net/223262/blueborne-falha-bluetooth-android-ios-windows-linux/)**.**

![[Untitled 1 55.png|Untitled 1 55.png]]

### Padrões IEEE 802.11

Os padrões 802.11 definidos pelo IEEE estabelecem o controle de acesso ao meio e as especificações da camada física. O controle de acesso ao meio é realizado pelo protocolo CSMA/CA (Carrier Sense Multiple Access/Colision Avoidance), enquanto a especificações de camada física depende do padrão IEEE a ser utilizado, variando em termos de frequência, modulação, alcance e largura de banda. Característica de alguns desses padrões são mostrados na tabela que segue (Filippetti, Marco Aurélio, 2017)..

![[Untitled 2 44.png|Untitled 2 44.png]]

**SAIBA MAIS**

A partir de 2019 os padrões IEEE 802.11 receberam uma nova nomenclatura com o objetivo de facilitar a vida o usuário final. Por exemplo, o padrão 802.11ac agora é chamado de Wi-Fi 5. Para saber ainda mais sobre essa nova nomenclatura, consulte o site: [**techtudo**](https://www.techtudo.com.br/noticias/2018/10/nome-do-padrao-wi-fi-vai-mudar-em-2019-80211ax-pode-se-tornar-wi-fi-6.ghtml).

### Problemas com a segurança

Apesar de proporcionar facilidade aos usuários finais, as redes 802.11 são mais exportas a problemas de segurança. Os seguintes fatores, inerentes a tecnologia, contribuem para maior exposição ao risco:

- **O ar é o meio de transmissão:** todos os pacotes trafegam pelo ar entre o transmissor e receptor, o que facilita a interceptação dos dados.
- **Oferecimento de facilidade no acesso:** a facilidade com que os usuários se conectam as redes wi-fi é o grande chamativo para seu uso disseminado como, por exemplo, para usuários móveis, que se conectam a diferentes redes constantemente. Essa facilidade no acesso pode ser explorada por um atacante.
- **Dispositivos móveis se conectam a diferentes redes:** dispositivos como notebooks, celulares e tablets se conectam facilmente em redes residenciais e também as redes corporativas. Tais equipamentos, uma vez infectados por worms e vírus, podem transmiti-los de uma rede para outra.

Além das características inerentes a tecnologias apresentadas acima, ainda existem os fatores associados a configuração e implementação das redes wi-fi, conforme elencados abaixo:

- Uso de senhas fracas.
- Manter os padrões de fábrica.
- Não mudar o SSID de fábrica.
- Não utilizar logins individuais para acesso a rede local.
- Utilizar autenticação de PIN WPS (Wi-Fi Protected Setup).
- Falhas na Configuração de redes de visitantes.
- Falta de conscientização dos usuários no uso da rede.
- Facilidade no acesso físico aos roteadores e pontos de acesso.
- Permitir o acesso não autorizado de uma VLAN para outra.
- Usar padrões de segurança comprovadamente inseguros como WEP.
- Não realizar atualizações nos equipamentos que fornecem acesso a rede wifi

### **Segurança no padrão 802.11**

As redes 802.11, como já discutido, possuem muitas vantagens em relação a mobilidade e facilidade na sua criação, mas que, por outro lado, pode representar grande risco à segurança. Os níveis de segurança desse tipo de rede podem ser aumentados com o emprego de mecanismos e algoritmos de segurança, conforme elencados abaixo. Cabe acrescentar que o uso de alguns deles, como WEP e WPA, atualmente, não são mais recomendados, mas é importante citá-los, já que, possivelmente, você ainda vai encontrar em muitos equipamentos (Linhares, A. G; Gonçalves, P. A., 2017)..

### WEP

WEP: o padrão WEP (algoritmo de criptografia Privacidade) nasceu como parte das especificações 802.11b de 1999, tendo como objetivo prover o mesmo nível de confidencialidade de uma rede cabeada tradicional. Utiliza para tanto algoritmo RC4 (Roteamento Coloniale 4) operando na camada de enlace, que usa um vetor de inicialização (IV) de 24 bits e uma secret shared Key (Chave compartilhada secreta) de 40 ou 104 bits. Ao concatenar o IV e a _**secret shared key**_ para formar uma nova chave de 64 ou 128bits, que então é utilizada para criptografar a informação, conforme ilustrado na figura que segue .

Como mecanismos de garantia de integridade, o WEP utiliza CRC-32 (Ciclo de Checagem de Redundância) que realiza a soma e verificação (checksum) da mensagem que é encaminhada no pacote. Quando o pacote chega no destinatário ela passa novamente pelo processo de checksum para garantir que não houve alteração da mensagem do pacote (Moraes, A. F, 2010).

![[Untitled 3 30.png|Untitled 3 30.png]]

**Vulnerabilidades do WEP**

As chaves criptográficas do WEP são simétricas, isso significa que são utilizadas tanto para encriptar quanto para descriptar. Por outro lado, ele trabalha com vetor de inicialização muito pequeno, o que o torna muito vulnerável a ataques que buscam descobrir a chave criptográfica. Além disso, todos os usuários utilizam compartilham a mesma chave WEP quando conectados ao mesmo access point. Por estes motivos o uso do WEP não é recomendado.

**SAIBA MAIS...**

A chave WEP pode ser quebrada por meio de ataques de força bruta por meio da suíte de aplicativos Aircrack-ng. Para saber mais acesse: [**https://www.aircrack-ng.org/doku.php?id=simple_wep_crack**](https://www.aircrack-ng.org/doku.php?id=simple_wep_crack)

### WPA

Para solucionar os problemas de vulnerabilidade do WEP surgiu em 2003 o padrão WPA (Wi-Fi Protected Access. A primeira implementação realizada foi a introdução do TKIP (Temporal Key Integrity Protocol) de modo a oferecer um mecanismo mais robusto para gerenciamento de chaves. Na figura que segue é mostrado uma comparação entre o WEP e o TKIP do WPA (Moraes, A. F, 2010).

![[Untitled 4 24.png|Untitled 4 24.png]]

O TKIP cria uma chave temporal de 128 bit que é compartilhada entre todos os clientes do mesmo access point. Posteriormente, ele combina a chave temporal com o endereço MAC do host transmissor para formar outra chave, chamada de Chave

de Endereço Temporária e Transmissão (TTAK), ou "Chave da 1ª fase". Combinando a TTAk com o IV do RC4 cria chaves diferentes para cada pacote, sendo elas trocadas a cada 10.000 pacotes.

Diferentemente do WEP, o WPA foi desenvolvido para operar em dois modos de autenticação:

- **WPA Personal:**  Nesse modo, assim como no WEP, a chave deve ser configurada no access point e nas estações, ou seja, deve ser previamente compartilhada (pré-shared key ou WPA-PSK). Cabe acrescentar que esse modo de operação é indicado apenas para redes pequenas e residenciais.
- **WPA Enterprise:** Nesse modo foi incorporado o padrão 802.1x, largamente utilizado em redes cabeadas. Para tanto, as autenticações individuais são realizadas de forma centralizada por um servidor RADIUS (Remote Authentication Dial In User Service) ou Tacacs (Terminal Access Controller Access-Control System). Nessa topologia o ponto de acesso passa a ser o cliente e os demais hosts o suplicante, conforme ilustrado abaixo. Tais processos de autenticação serão vistos em outro tópico.

Na figura que segue são mostrados os possíveis padrões de segurança de redes sem fio que podem ser configurados. Perceba que o padrão WEP não permite ser configurado em modo Enterprise.

![[Untitled 5 21.png|Untitled 5 21.png]]

**Vulnerabilidades do WPA com TKIP**

Apesar de solucionar as principais vulnerabilidades apresentadas pelo protocolo WEP, o WPA tem a sua fraqueza associada ao algoritmo de combinação de chave. Se o atacante tiver conhecimento de algumas chaves do RC4 (menos de 10) geradas por IVs, o atacante pode descobrir a chave de criptografia de dados e de integridade, já que os 32 bits significativos são os mesmos (LINHARES, A. G.;  S. GONÇALVES, P. A., 2016).

### WPA2

Em 2004 foi lançado o padrão WPA2 (Wi-Fi Protected Access II) baseado nas especificações final do IEEE 802.11i. O WPA2 é compatível com o WPA, assim como TKIP e o protocolos 802.1x.

Para encriptação da mensagem transmitida o WPA2 utiliza o CCMP (AES-Counter Mode CBC-MAC Protocol), um mecanismo totalmente independente do funcionamento do WEP, que utiliza o algoritmo RC4. O WPA2, por sua vez, utiliza o algoritmo AES (Advanced Encryption Standard) para codificar a mensagem antes dela ser transmitida. O CBC-MAC (Cipher Block Chaining Message Authentication Code) é responsável pela integridade dos quadros, seu funcionamento é mostrado na figura que segue (Linhares, A. G; Gonçalves, P. A., 2017).

![[Untitled 6 14.png|Untitled 6 14.png]]

O conceito de chave temporária e código de integridades utilizados pelo WPA foram mantidos no WPA2, introduzindo apenas avanços no processo de roaming, quando uma estação passa de um AP para o outro (Stallings, William, 2015).

Assim como no WPA, o WPA2 suporta dois modos de autenticação:

- **WPA2 Personal:** Esse modo é indicado para escritórios pequenos e usuários residenciais, já que utiliza apenas uma pre-shared key (PSK) para autenticação. Cada dispositivo wi-fi encripta o tráfego usando uma chave de 256 bits (AES), configurada através de 64 caracteres hexadecimal ou uma frase secreta de 8 a 63 de caracteres ASCII.
- **WPA2 Enterprise:** Nesse modo é possível utilizar autenticação 802.1x como RADIUS.

**Vulnerabilidade WPA2**

Utilizar a PSK torna o sistema vulnerável a ataques de força bruta ou de dicionário, principalmente quando a frase secreta é de baixa complexidade, por exemplo,  usar PSK com menos de 20 caracteres. Cabe acrescentar que essa não é exatamente uma vulnerabilidade do protocolo, mas sim de configuração.

Existe também um ataque que pode capturar dados que trafegam na rede sem criptografia, como e-mails e sites http. Esse ataque explora o processo de handshake de 4 vias efetuado pelo WPA2 quando uma estação se conecta a rede Wi-fi protegida (Linhares, A. G; Gonçalves, P. A., 2017).

**SAIBA MAIS...**

Um ataque batizado de KRACK, acrônimo para Key Reinstallation Attacks (ou Ataques de Reinstalação de Chaves) foi desenvolvido em 2017 por uma equipe de pesquisadores de segurança. Esse explora uma serie de falhas graves descoberta no WEP2. Para saber mais leia o artigo: [**https://gizmodo.uol.com.br/falha-protocolo-wpa2-wi-fi/**](https://gizmodo.uol.com.br/falha-protocolo-wpa2-wi-fi/)

### WPA3

O WPA3 foi lançado em junho de 2018. Assim como o WPA2, o inclui os modos de acesso WPA3-Personal e WPA3-Enterprise. Além disso, O WPA3 torna obrigatório o uso de Quadros de Gerenciamento Protegidos (PMF). O WPA3 utiliza o mesmo algoritmo de criptografia do WPA2, mas faz uso de 192 bits no modo Enterprise, sendo opcional na versão Personal.

Em relação a autenticação, o WPA3 utiliza a autenticação simultânea de iguais (SAE) para substituir o protocolo PSK do WPA2. O SAE é um protocolo mais seguro para lidar com ataques do tipo KRACK. O SAE, também conhecido como Dragonfly Key Exchange, usa sigilo avançado e é resistente a ataques de descriptografia offline.

**Vulnerabilidades WPA3**

Apesar Wi-Fi Alliance afirmar que seria impossível quebrar a senha em função do mecanismo robusto de handshake, uma nova vulnerabilidade chamada de Dragonblood, permitindo ao atacante quebrem a senha da rede e acessem o tráfego criptografado.

**SAIBA MAIS...**

Para saber mais sobre o ataque DragonBlood acesse o link:  [**https://mundohacker.net.br/falhas-de-seguranca-no-protocolo-wpa3-permitem-que-hackers-descubram-a-senha-do-wifi/**](https://mundohacker.net.br/falhas-de-seguranca-no-protocolo-wpa3-permitem-que-hackers-descubram-a-senha-do-wifi/)