**Introdução**

Sabemos que o endereçamento IPv4 tem suas limitações e, inclusive, para a maioria dos países, incluindo o Brasil, não há mais endereços IPv4 públicos (roteáveis na Internet) disponíveis. Por essas e outras razões foi criado o padrão IPv6. Nesse tópico, falaremos do esquema de endereçamento para que você possa executar as configurações no simulador da Cisco, o Packet Tracer®.

**Esquema de endereçamento IPv6**

Para comportar uma quantidade muito maior de endereços, o IPv6 foi dividido em **8 grupos de 4 caracteres hexadecimais cada**, sendo esses grupos separados pelo símbolo de dois pontos (“:”).

O sistema de numeração hexadecimal é baseado em 16 caracteres, para representar 16 possibilidades (valores) diferentes. Esses caracteres são números inteiros positivos, de 0 a 9, e letras do alfabeto, de A a F – constituindo, assim, os 16 caracteres do “alfabeto” hexadecimal. Esse sistema é utilizado para representar números muito grandes, através de uma escrita mais simples e rápida. Por exemplo, em vez de escrever o número 100 milhões (100.000.000), podemos escrever em hexadecimal 5F5E100.

Um exemplo de endereço IPv6 seria **2001:0050:0000:0000:0000:0A10:12EB:99AA**. Mesmo assim, ainda é muito ruim de se escrever ou digitar para configurar um equipamento, certo?

Então inventaram duas regras simples, para facilitar essa escrita, de modo a abreviá-la.

**1ª** **R****egra:** eliminar grupos consecutivos de zeros.

Através dessa regra, o endereço original acima fica **2001:0050::****0A10:12EB:99AA.**

Repare que, após executar essa simplificação, necessariamente teremos dois símbolos de dois pontos juntos.

**2****ª** **R****egra:** eliminar os zeros à esquerda.

Através dessa regra, o endereço acima fica **2001:50::****A10:12EB:99AA.**

O vídeo abaixo, produzido pela equipe do NIC.BR, também exemplifica essas regras:

**Os endereços IP não são todos iguais - Parte 1**:

[**https://www.youtube.com/watch?list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ&time_continue=336&v=jnuHODaLcO8**](https://www.youtube.com/watch?list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ&time_continue=336&v=jnuHODaLcO8)

Repare que essa simplificação só serve quando temos zeros à esquerda; os zeros à direita devem permanecer, caso contrário termos ambiguidade (mais de uma possibilidade de endereços originais), de forma que o roteador (ou outro equipamento de rede) não saberia de qual endereço estamos falando.

**Vídeo explicativo**

A título de complementação, e para entender melhor como funciona o endereçamento IPv6, recomendamos também assistir ao vídeo abaixo, produzido pela equipe do NIC.BR.

**Os endereços IP não são todos iguais - Parte 2**:

[**https://www.youtube.com/watch?v=63M61wttuMk&index=2&list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ**](https://www.youtube.com/watch?v=63M61wttuMk&index=2&list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ)

**Campo Opções**

Apenas para citar uma das melhorias, implementadas no IPv6 em relação ao IPv4, conforme Donahue (2011), o IPv6 possui um campo “opções”, que é inserido em um cabeçalho estendido (localizado entre o cabeçalho IPv6 padrão e o cabeçalho da camada de Transporte. A maioria das informações presentes nesse cabeçalho expandido não são examinadas pelos roteadores que encaminham os pacotes da origem até o destino. Isso acontece para melhorar o desempenho da rede, uma vez que, no IPv4, a existência de opções no cabeçalho devia, necessariamente, ser analisada por cada roteador na rota de um pacote.

Os campos de opções estão relacionados a fragmentação, autenticação e informações sobre o dispositivo final, de destino. Dessa forma, você observa que, de fato, não há necessidade de cada roteador analisar essas informações, ao menos não em todas as comunicações entre dispositivos.

**Conclusão**

Neste capítulo apresentamos:

- O esquema de endereçamento IPv6;
- As etapas para simplificarmos a escrita desses endereços;
- Uma das principais mudanças no cabeçalho estendido do protocolo IPv6, em relação ao protocolo IPv4: o campo opções.