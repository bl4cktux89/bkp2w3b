**Introdução**

Olá! Seja bem-vindo à oitava aula! Nesta aula vamos complementar o estudo sobre as estruturas dos tipos de dados aceitos pelo SNMP.

**SMI**

Como vimos nas aulas anteriores, a codificação ASN.1 possui apenas 7 tipos de dados (o SNMPv1 usa apenas 5) para serem utilizados por uma estrutura de gerenciamento. Como o SNMPv2 integra o gerenciamento da internet, isso significa que há possibilidade de monitorar tanto redes baseadas na arquitetura TCP/IP (as redes locais, por exemplo) como redes baseadas no Modelo de Referência OSI (as redes de telecomunicações, por exemplo). Dessa forma, uma nova estrutura chamada de SMI (_**Structure of Management Information**_ ou Estrutura de informações gerenciais) oferece cerca de 9 tipos de dados para gerar informações nas estruturas de gerenciamento além dos 4 tipos da ASN.1.

Tipos de dados SMI:

- INTEGER: Código 1; Tipo numérico; Tamanho 4 bytes.
- Counter32: Código 2; Tipo numérico; Tamanho 4 bytes.
- Gauge32: Código 3; Tipo numérico; Tamanho 4 bytes.
- Integer32: Código 4; Tipo numérico; Tamanho 4 bytes.
- UInteger32: Código 5; Tipo numérico; Tamanho 4 bytes.
- Counter64: Código 6; Tipo numérico; Tamanho 8 bytes.
- TimeTicks: Código 7; Tipo numérico; Tamanho 4 bytes.
- BIT STRING: Código 8; Tipo String; Tamanho 4 bytes.
- OCTET STRING: Código 9; Tipo String; Tamanho >= 0 bytes.
- Opaque: Código 10; Tipo String; Tamanho >= 0 bytes.
- OBJECT IDENTIFIER: Código 11; Tipo String; Tamanho > 0 bytes.
- IpAddress: Código 12; Tipo String; Tamanho 4 Bytes. (Enderço IP em forma decimal com ponto)
- NsapAddress: Código 13; Tipo String; Tamanho < 22 bytes. (Endereço OSI NAP).

O SMI, então, é uma linguagem usada para definir informações de gerenciamento (tipos de dados) que residem em uma entidade gerenciada da rede. Essa linguagem de definição é necessária para assegurar que a sintaxe e a semântica dos dados de gerenciamento de rede sejam bem-definidas e não apresentem ambiguidade. Observe que a SMI não define uma instância específica para os dados em uma entidade gerenciada de rede, mas a linguagem na qual a informação está especificada.

Para mais informações, verifique na bibliografia citada os itens SMI e construções SMI. Sobre as regras para o SNMPv3, estão divulgadas nas RFCs 2578, 2579 e 2580.