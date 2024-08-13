### **Introdução**

As VPNs (Redes Virtuais Privadas) combinam as tecnologias de criptografia, autenticação e tunelamento para prover conectividade entre usuários e redes sob uma infraestrutura compartilhada com políticas de acesso e segurança de uma rede Pública.

Existem diversas maneiras de se implementar uma VPN, sendo que, cada uma delas utilizam diferentes protocolos associados a diferentes camadas do modelo OSI.

Na tabela a seguir é mostrado de forma resumida os diferentes tipos de VPN e sua correlação com as camadas do modelo OSI (Moraes, A. F., 2010).

![[Untitled 95.png|Untitled 95.png]]

### IPSec

O protocolo IP quando utilizado não proporciona mecanismos de confidencialidade, autenticidade e integridade. Entretanto, quando implementado com o IPSec pode prevenir ataques de varredura de rede, falsificação de endereços IPs, modificação de dados e ataques de reutilização de dados. Cabe acrescentar que o IPSec é nativo no IPv6 e oferece suporte para IPv4 (Brito, S. H. B, 2013).

### IPSec modo Túnel

No IPsec modo túnel um novo cabeçalho é incluído ao pacote original, conforme mostrado na figura abaixo. O novo cabeçalho possui os endereços de origem e destino do túnel e outro, mais interno, é do cabeçalho IPSec. Como pode ser observado, nesse modo todo o pacote original fica protegido, inclusive os endereços IPs de origem e destino.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/1/7/8311708/59296-c.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/1/7/8311708/59296-c.jpg)

IPSec modo túnel

### IPSec modo Transporte

O IPSec modo transporte adiciona um cabeçalho IPSec entre o cabeçalho IP original e o payload, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/1/1/1/7/8111780/59298-c-bkp.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/1/1/1/7/8111780/59298-c-bkp.jpg)

IPSec modo transporte

### Protocolos de Segurança IPSec

O Padrão IPSec define dois protocolos para prover segurança:

- **Cabeçalho de Autenticação - AH (Autentication header):** O AH faz uso de chaves públicas e garante a integridade e autenticação de origem, mas não garante a confidencialidade dos dados, pois não suporta criptografia. No modo transporte o cabeçalho AH é posicionado entre o cabeçalho IP original e os demais campos, conforme mostrado na figura que segue.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/7/4/9/8074978/59299.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/7/4/9/8074978/59299.png)

Campos do cabeçalho AH.

Fonte: https://www.gta.ufrj.br/grad/03_1/ip-security/paginas/ah.html

- **Encapsulamento de Segurança da parte de dados - ESP** (Encapsulation Security Payload): O ESP oferece mecanismos de integridade, confidencialidade e autenticação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/7/5/2/8075243/59300.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/7/5/2/8075243/59300.png)

Campos do cabeçalho ESP.

Fonte: https://www.gta.ufrj.br/grad/03_1/ip-security/paginas/esp.html

**IMPORTANTE!!**

Por questões de segurança, recomenda-se utilizar a combinação de AH para autenticação e ESP na criptografia do payload.

### **Associação de segurança IPSec**

A associação de segurança IPSec, ou simplesmente SA, pode ser entendido como um acordo estabelecido entre dois pontos da comunicação com o objetivo de negociar os parâmetros do túnel IPSec. Essa negociação ocorre antes do estabelecimento do túnel propriamente dito. Abaixo são elencados os mecanismos de segurança utilizados na SA e os principais algoritmos suportados (Moraes, A. F, 2010).

- Modo do túnel IPSec: ESP ou AH.
- Algoritmo de Criptografia: O IPSec suporta AES, DES, 3DES, RC5, IDEA, CAST e Blowfish.
- Método de autenticação: Suporta assinaturas digitais RSA e DSS.
- Função de hashing: O IPSec suporta MD5, SHA-1 e Tiger.
- Método de autenticação do usuário: Por exemplo, RADIUS ou SecurID;
- Escolha das chaves criptográficas e chaves de autenticação: IKE ou ISAKMP

As associações de segurança (SA) ficam armazenadas na Base de Dados da Política de Segurança - SPD (Security Policy Database) e na Base de Dados de Associação - SAD (Security Association Database), sendo que, cada SA recebe um identificador único conhecido como Índice de Parâmetro de Segurança (SPI).

A SAD: Contém todas as associações de segurança ativas enquanto a SPD é consultada durante o processamento do tráfego de entrada e saída, definido quais pacotes serão aplicados o IPSec e quais serão descartados.

Na figura abaixo é mostrado os diferentes tipos de SA: modo transporte Estação - Estação; Modo túnel - Site to site; Modo Estação Site, modo túnel ou transporte.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/7/8/8067855/59301.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/7/8/8067855/59301.png)

Tipos de associação de segurança - SA

Fonte: Moraes, Alexandre. Fernandes. Segurança em Redes: Fundamentos. São Paulo: Erica, 2010

### Estabelecimento da Associação de Segurança - SA

O estabelecimento da AS pode ser gerenciado manualmente e automaticamente. O gerenciamento manual  é indicado para pequenas empresas e é estabelecido de host a host, enquanto o estabelecimento automático utiliza mecanismos de troca de chaves criptográficas, como o Protocolo de Gerenciamento de Associações de Segurança e chave da Internet - ISAKMP (Internet Security Association and  Key Management Protocolo) e a Troca de Chave na Internet - IKE (Internet Key Exchange).

### IKE

O protocolo IKE é padronizado pela RFC 2409, ele é utilizado para negociar e prover mecanismos de autenticação chaves para AS, provendo segurança neste processo. Ele é um protocolo híbrido que utiliza o ISAKMP (RFC 2408) e o Oakley (RFC 2412).

Os pacotes IKE são transportados entre origem e destino via porta UDP 500. Esse processo em duas fases. Na **primeira fase** ocorre a autenticação das partes estabelece um ISAKMP SA para proteger as mensagens da fase dois. Esse processo ocorre por meio de

- Acordo do método de Autenticação;
- Seleção dos algoritmos de autenticação e criptografia;
- Troca de chave
- Verificação das identidades de cada uma das partes.

Esta primeira fase é a mais complexa e exige muito CPU para estabelecimento da SA. Existem dois métodos ou modos IKE para completar a fase 1:

- **Modo principal:** o estabelecimento da SA no modo principal ocorre por meio do envio de seis mensagens, sendo duas de negociação de política, duas para definir a troca chaves públicas via Diffie-Hellman e últimas para autenticação das partes, conforme mostrado na figura que segue.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/8/1/8068183/59302.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/8/1/8068183/59302.png)

IKE modo principal

Fonte: Moraes, Alexandre. Fernandes. Segurança em Redes: Fundamentos. São Paulo: Erica, 2010

- **Modo agressivo:** No modo agressivo é disposibilizados os mesmos serviços do modo principal, porém, em vez de seis mensagens, o processo ocorre por meio do envio de duas ou três mensagens. A primeira negocia a política e a definição da identidade das partes, a segunda e terceira autentica quem recebe e quem envia as mensagens, conforme ilustrado na figura que segue.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/5/8/2/8058268/59303.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/5/8/2/8058268/59303.png)

IKE modo agressivo

Fonte: Moraes, Alexandre. Fernandes. Segurança em Redes: Fundamentos. São Paulo: Erica, 2010

**IMPORTANTE!!**

Em algumas implementações o mecanismo conhecido como XAUTH introduz uma fase adicional no processo de autenticação de usuário.

A **segunda fase** estabelece um IPSec SA com o objetivo de realizar a autenticação e criptografia dos dados de acordo com as chaves e algoritmos que foram acordados na primeira fase. Essa fase é menos complexa e ocorre mais frequentemente que a primeira. Na figura abaixo é ilustrado o processo IKE fase 2 - modo rápido.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/5/8/4/8058441/59305.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/5/8/4/8058441/59305.png)

IKE fase 2 modo rápido

Fonte: Moraes, Alexandre. Fernandes. Segurança em Redes: Fundamentos. São Paulo: Erica, 2010

**IMPORTANTE!!**

O padrão IKEv2 foi desenvolvido para corrigir falhas que podem ser potencialmente exploradas no IKE. No IKEv2 as duas fases são condensadas em apenas um único grupo de mensagens.

A figura a seguir resume os componentes do protocolo IPSec.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/1/2/9/9/8129953/59306.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/1/2/9/9/8129953/59306.png)

Componentes do protocolo IPSec

Fonte: McNab, Chris. Avaliação de segurança de redes: conheça a sua rede.  São Paulo: Novatec, 2017.

### Atividade 1 - Configuração de VPN site-to-site IPv4

Para realizar a atividade você deve ter instalado o Packet Tracer versão 7.2 ou superior. Baixe o arquivo PKA e siga o roteiro.

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/8/1/8068139/59307-packet-tracer-config.rar)

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/0/6/8/1/8068139/59307-packet-tracer-config.rar)

### Atividade 2 - Configuração VPN site-to-site IPv6

Para realizar a atividade você deve ter instalado o GNS3 e utilizar a imagem C7200-v51.image (IOS v15.1) nos roteadores, pois essa imagem tem suporte a VPN IPv6. Este laboratório tem como base (Com adaptações) o laboratório 28 do livro Laboratórios de Tecnologias Cisco em infraestrutura de Redes (Brito, S. H. B, 2012).

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/1/3/4/6/8134651/59306.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/1/3/4/6/8134651/59306.png)

Configuração VPN IPSec Site-to-Site IPv6 no GNS3.

Fonte:

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/2/1/8312142/arquivos.7z)

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/2/1/8312142/arquivos.7z)

`1.` `PARTE 1: Configuração do roteador Roteador SP` `2.`   `3.` `ETAPA-1: Configuração do roteamento e endereçamento IPv6 no roteador SP` `4.`   `5.` `SP(config)# ipv6 unicast-routing` `6.` `SP(config)# ipv6 route ::/0 2001:db8:aaaa::f` `7.` `SP(config)# interface f0/0` `8.` `SP(config)# description Link-ISP` `9.` `SP(config-if)# ipv6 enable` `10.` `SP(config-if)# ipv6 address 2001:db8:aaaa::1/64` `11.` `SP(config-if)# no shutdown` `12.` `SP(config-if)# exit` `13.` `SP(config-if)# interface f1/0` `14.` `SP(config-if)# description LAN-CAFE-1` `15.` `SP(config-if)# ipv6 enable` `16.` `SP(config-if)# ipv6 address 2001:Db8:cafe:1::1/64` `17.` `SP(config-if)# no shutdown` `18.` `SP(config-if)# exit` `19.`   `20.` `ETAPA-2:Configurando as propriedades da FASE 1 do ISAKMP em SP` `21.`   `22.` `SP(config)# crypto isakmp key 0 SENHA address ipv6 ::/0` `23.` `SP(config)# crypto isakmp policy 1` `24.` `SP(config-isakmp)# encryption aes 128` `25.` `SP(config-isakmp)# authentication pre-share` `26.` `SP(config-isakmp)# exit` `27.`   `28.` `ETAPA-3: Configurando as propriedades da FASE 2 do ISAKMP em SP` `29.`   `30.` `SP(config)# crypto ipsec transform-set VPNv6 esp-aes 128 esp-sha-hmac` `31.` `SP(cfg-crypto-trans)# mode tunnel` `32.` `SP(cfg-crypto-trans)# exit` `33.` `SP(config)# crypto ipsec profile VPNv6` `34.` `SP(ipsec-profile)# set transform-set VPNv6` `35.` `SP(ipsec-profile)# exit` `36.`   `37.` `ETAPA-4: Configuração da interface lógica e da rota estática apontando para a rede local remota` `38.`   `39.` `SP(config)# interface tunnel 0` `40.` `SP(config-if)# description VPN-to-RJ` `41.` `SP(config-if)# ipv6 enable` `42.` `SP(config-if)# ipv6 address fd00:cafe::a/127` `43.` `SP(config-if)# tunnel source f0/0` `44.` `SP(config-if)# tunnel destination 2001:db8:bbbb::1` `45.` `SP(config-if)# tunnel mode ipsec ipv6` `46.` `SP(config-if)# tunnel protection ipsec profile VPNv6` `47.` `SP(config-if)# exit` `48.` `SP(config)# ipv6 route 2001:db8:cafe:2::/64 tunnel 0` `49.`   `50.` `PARTE 2: Configuração do roteador RJ` `51.`   `52.` `As configurações no roteador RJ são semelhantes ao do roteador SP.` `53.`   `54.` `ETAPA-1: Configuração do roteamento e endereçamento IPv6 no roteador SP` `55.`   `56.` `RJ(config)# ipv6 unicast-routing` `57.` `RJ (config)# ipv6 route ::/0 2001:db8:bbbb::f` `58.` `RJ(config)# interface f0/0` `59.` `RJ(config)# description Link-ISP` `60.` `RJ(config-if)# ipv6 enable` `61.` `RJ(config-if)# ipv6 address 2001:db8:bbbb::1/64` `62.` `RJ(config-if)# no shutdown` `63.` `RJ(config-if)# exit` `64.` `RJ(config-if)# interface f1/0` `65.` `RJ(config-if)# description LAN-CAFE-2` `66.` `RJ(config-if)# ipv6 enable` `67.` `RJ(config-if)# ipv6 address 2001:db8:cafe:2::1/64` `68.` `RJ(config-if)# no shutdown` `69.` `RJ(config-if)# exit` `70.`   `71.` `ETAPA-2: Configurando as propriedades da FASE 1 do ISAKMP em SP` `72.`   `73.` `RJ(config)# crypto isakmp key 0 SENHA address ipv6 ::/0` `74.` `RJ(config)# crypto isakmp policy 1` `75.` `RJ(config-isakmp)# encryption aes 128` `76.` `RJ(config-isakmp)# authentication pre-share` `77.` `RJ(config-isakmp)# exit` `78.`   `79.` `ETAPA-3: Configurando as propriedades da FASE 2 do ISAKMP em SP` `80.`   `81.` `RJ(config)# crypto ipsec transform-set VPNv6 esp-aes 128 esp-sha-hmac` `82.` `RJ(cfg-crypto-trans)# mode tunnel` `83.` `RJ(cfg-crypto-trans)# exit` `84.` `RJ(config)# crypto ipsec profile VPNv6` `85.` `RJ(ipsec-profile)# set transform-set VPNv6` `86.` `RJ(ipsec-profile)# exit` `87.`   `88.` `ETAPA-4: Configuração da interface lógica e da rota estática apontando para a rede local remota` `89.`   `90.` `RJ(config)# interface tunnel 0` `91.` `RJ(config-if)# description VPN-to-SP` `92.` `RJ(config-if)# ipv6 enable` `93.` `RJ(config-if)# ipv6 address fd00:cafe::b/127` `94.` `RJ(config-if)# tunnel source f0/0` `95.` `RJ(config-if)# tunnel destination 2001:db8:aaaa::1` `96.` `RJ(config-if)# tunnel mode ipsec ipv6` `97.` `RJ(config-if)# tunnel protection ipsec profile VPNv6` `98.` `RJ(config-if)# exit` `99.` `RJ(config)# ipv6 route 2001:db8:cafe:1::/64 tunnel 0`