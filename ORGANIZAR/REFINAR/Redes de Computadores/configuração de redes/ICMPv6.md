**Introdução**

O Internet Control Message Protocol é um dos protocolos mais utilizados na suíte (coleção) de protocolos TCP/IP, e serve para testar a conectividade entre dispositivos em uma rede de computadores, sendo que qualquer equipamento de rede, seja um dispositivo final, como PCs, impressoras e servidores; ou dispositivos intermediários, como switches e roteadores, conseguem processar as informações deste protocolo. O famoso comando “ping” (talvez o comando mais popular entre os profissionais de redes) faz uso desse protocolo. Neste capítulo, vamos mostrar como utilizar o protocolo ICMP com endereços IPv6, no simulador Packet Tracer®, da Cisco.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709873/form-obj-0.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709873/form-obj-0.png)

Fonte:

**Utilizando o ICMP**

A título de exemplo, considere a topologia da Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/3/2/6/2732699/41546.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/3/2/6/2732699/41546.jpg)

Fonte: O autor.

Através do comando ip**v6**config (repare no “v6” após a palavra “ip”), que o PC está configurado com o endereço IPv6 **2001:ABC::****1****:1/64**, conforme Figura 2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709884/4.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709884/4.png)

Fonte:

Para saber mais sobre os diferentes tipos de endereços IPv6, recomendamos assistir ao seguinte vídeo, produzido pela equipe do NIC.BR:

[**https://www.youtube.com/watch?v=63M61wttuMk&index=2&list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ**](https://www.youtube.com/watch?v=63M61wttuMk&index=2&list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ)

Similarmente, podemos verificar, através do mesmo comando ip**v6**config, que o servidor está configurado com o endereço IPv6 **2001:ABC::A:1/64**, conforme Figura 3:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709883/3.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709883/3.png)

Fonte:

Como esses endereços estão na mesma rede (já que a máscara de rede é /64), podemos executar o comando _**ping**_ com sucesso, por exemplo, a partir do PC, comunicando com o servidor, conforme Figura 4, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709878/2.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709878/2.png)

Fonte:

O comando ping possui duas variações (chamadas de opções) interessantes, executadas através dos atributos "**-n** número_inteiro" e "**-t**":

- Com a opção "-n ", seguida de um número inteiro, o ping será executado por "x" vezes, sendo esse "x" o número inteiro desejado.
- Com a opção "-t", o ping será executado infinitamente (para encerrarmos sua execução, precisamos manter pressionada a tecla "Ctrl" em seguida, pressionar a tecla "c", do teclado).

A figura abaixo mostra essas duas variações.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709874/form-obj-0-1-.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/7/0/9/8/2709874/form-obj-0-1-.png)

Fonte:

**Conclusão**

Neste capítulo mostramos:

- Como utilizar o protocolo ICMP com endereços IPv6;
- Variações do comando _ping_;
- Um exemplo de configuração no simulador Packet Tracer, da Cisco.
    
    ®