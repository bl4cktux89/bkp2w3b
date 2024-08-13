[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Esta aula trouxe para você informações importantes para a configuração de endereços IPv4 em hosts em uma rede. Os endereços podem ser atribuídos de forma manual ou de forma automática por um servidor DHCP. Também houve o aprendizado sobre máscaras de rede e a configuração de uma sub-rede através de seus endereços e máscaras. Estas informações são fundamentais para que você possa configurar dispositivos adequadamente, em conformidade com regras e técnicas de endereçamento IP, de forma a deixar sua rede com performance superior a uma rede sem planejamento de endereçamento IP.

Na sequência, acompanhe o relatório de projeto apresentado como proposta no início desta aula.

**Relatório do projeto de redes: configuração do endereçamento da rede**

A rede interna da empresa de coworking deve ser segmentada em cinco sub-redes, utilizando-se a classe C de endereçamento IP, de forma que a rede será 192.168.10.0, e a máscara de rede será 255.255.255.0, considerando o volume de equipamentos que precisam se conectar à rede.

A máscara da sub-rede 255.255.255.0 (em notação decimal) representa 11111111.11111111.11111111.00000000.

- A rede: 2n = 23 = 8, ou seja, para fazer cinco sub-redes será necessário alocar três bits da máscara de rede. Note que podemos ter dois ou quatro (ou mais, desde que sejam números pares), assim, como precisamos dividir nossa rede em cinco sub-redes, utilizaremos o cálculo com oito sub-redes.
- _Hosts_ de sub-rede: 2n = 25 = 32, com possibilidade de até 32 _hosts_ em cada sub-rede. Considere que, para converter os octetos, são utilizados: 1, 2, 4, 8, 16, 32, 64 e 128. Como foram utilizados três bits para a definição das redes, sobraram outros cinco bits para os _hosts_.

Temos, assim, as seguintes sub-redes:

- Sistemas: 192.168.10.0: _hosts_ 192.168.10.1 a 192.168.10.30 e _broadcast_ 192.168.10.31.
- Gerência: 192.168.10.32: _hosts_ 192.168.10.33 a 192.168.10.62 e _broadcast_ 192.168.10.63.
- Clientes: 192.168.10.64: _hosts_ 192.168.10.65 a 192.168.10.94 e _broadcast_ 192.168.10.95.
- Reuniões: 192.168.10.96: _hosts_ 192.168.10.97 a 192.168.10.126 e _broadcast_ 192.168.10.127.
- Visitantes: 192.168.10.128: _hosts_ 192.168.10.129 a 192.168.10.158 e _broadcast_ 192.168.10.159.

A máscara de rede calculada ficou como: 11111111.11111111.1111111.11100000.

Veja que utilizamos três bits (emprestado o octeto, que define o endereço do _host_ para que um endereço de sub-rede possa ser gerado e segmentar a rede).

Considerando a tabela de bits do octeto, temos:

[![](https://ampli-images.s3.amazonaws.com/production/80eb60ee-9b53-4797-b723-6a97f932815a/original)](https://ampli-images.s3.amazonaws.com/production/80eb60ee-9b53-4797-b723-6a97f932815a/original)

Isso remete a 128 + 64 + 32 (bits que representarão a sub-rede) = 224.

Na notação CIDR, ou em barra (/), considerando a somatória de todos os bits de rede (oito do primeiro octeto, oito do segundo octeto, oito do terceiro octeto e três do quarto octeto), temos 8+8+8+3= 27.

**Assim, a nova máscara de sub-rede se torna 255.255.255.224, ou /27.**