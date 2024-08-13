  

**Introdução**

Olá! Seja bem-vindo à sétima aula! Nela, vamos estudar a codificação ASN e sua sintaxe de transferência (BER).

_**Abstract Syntax Notation**_ **(ASN)**

A Notação (ou Escrita) de sintaxe abstrata é um padrão de escrita flexível que descreve regras e estruturas de representação, codificação, transmissão e decodificação de dados em redes computacionais ou de telecomunicações.

A codificação ASN é dividida em uma estrutura hierárquica em que cada nível possui objetos que recebem códigos numéricos começando pelo zero, até chegar ao ponto em que temos os tipos de dados. Os **tipos de dados** da ASN.1 são chamados de **tipos de primitiva** e são similares aos que encontramos nos programas desenvolvidos em linguagem C. São eles:

- BOOLEAN: Código 0 (zero).
- REAL: Código 1.
- INTEGER: Código 2.
- BIT STRING: Código 3.
- OCTET STRING: Código 4.
- NULL: Código 5.
- OBJECT IDENTIFIER: Código 6.

Apesar de haver 7 tipos de primitivas, no SNMP não são permitidas as primitivas BOOLEAN e REAL.

Na hierarquia ASN, o primeiro nível da árvore lista todas as organizações de padrões de rede importantes (na visão da ISO), ou seja, ITU (antigo CCITT: código 0), a própria ISO (código 1) e a combinação dos dois (ITU/ISO, código 2). Abaixo da organização ISSO, há uma ramificação com 4 componentes, sendo o quarto destinado à **Organização identificada** (código 3), que é a concessão da ISO de que há outros órgãos envolvidos com padronização. O DoD (Departamento de defesa dos EUA – código 6) recebeu um lugar nessa ramificação e definiu o número 1 (código 1) em sua ramificação para identificar a internet nessa hierarquia. Sob a internet, estão os objetos de gerenciamento (código 2) e, em sua ramificação, os MIBs (MIB-II com Código 1), finalmente, abaixo da MIB-II temos seus objetos.

Para representar a internet em codificação ASN, temos: .1.3.6.1; para representarMIB-II: .1.3.6.1.2.1; para representar o objeto SYSTEM temos: .1.3.6.1.2.1.1, por exemplo.

**Basic Encoding Rules (BER)**

As regras básicas de codificação são uma sintaxe de transferência usada pela ASN. O princípio que orienta a BER é o de que todos os valores transmitidos, tanto primitivos quanto construídos, consistem em, no mínimo, quatro campos, que são:

1. O Identificador (Tipo ou TAG).
2. O tamanho do campo de dados em Bytes.
3. O campo de dados.
4. O flag de detecção de final de conteúdo, caso o tamanho dos dados seja desconhecido.

**Observação:** Esse último campo não é usado no SNMP.

O primeiro campo tem o tamanho de 1 byte e identifica o próximo item, contudo ele é dividido em três subcampos, sendo os primeiros 2 bits para identificar o tipo de tag, o terceiro bit para informar se é do tipo primitivo ou não e os demais bits para codificar o valor da tag.

O segundo campo informa a quantidade de bytes que os dados ocupam. Se a quantidade for menor que 128 Bytes, então são diretamente codificados em 1 byte cujo bit mais à esquerda é 0. Os que forem maiores, utilizarão diversos bytes, com o primeiro deles contendo 1 no bit de alta ordem (ou bit mais significativo) e o campo de tamanho(até 127 bytes) nos 7 bits restantes.

O terceiro campo é codificado de acordo com o tipo de dado.

Para mais informações, verifique a codificação ASN.1 e a sintaxe de transferência ASN.1 ou, ainda, BER numa das bibliografias recomendadas.