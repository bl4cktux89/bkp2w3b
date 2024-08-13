[![](https://ampli-images.s3.amazonaws.com/production/1157c30f-cce6-4fc7-9250-30c88086d92b/original)](https://ampli-images.s3.amazonaws.com/production/1157c30f-cce6-4fc7-9250-30c88086d92b/original)

Um endereço IP privado está condicionado a um intervalo definido, que pode ser utilizado para configuração manual ou automática dentro de uma rede privada. Para melhor aproveitamento e gestão de uma rede, os endereços IPs privados estão divididos em cinco classes: A, B, C, D e E. As classes A, B e C são aquelas úteis e configuráveis dentro de uma rede local.

- Endereços de classe A estão compreendidos dentro do limite de 1.0.0.0 até 127.255.255.255.
- Endereços de classe B, de 128.0.0.0 até 191.255.255.255.
- E endereços de classe C, de 192.0.0.0 até 223.255.255.255.

[![](https://ampli-images.s3.amazonaws.com/production/ec05e45e-7653-4d7a-a8ea-20e1a6bd6033/original)](https://ampli-images.s3.amazonaws.com/production/ec05e45e-7653-4d7a-a8ea-20e1a6bd6033/original)

Classes de endereços IPv4. Fonte: Tanenbaum (2011, p. 282).

O endereço IP de um _host_ pode ser visualizado através do comando ipconfig/all, quando estiver utilizando sistemas operacionais Windows, e ifconfig se estiver com um sistema Linux. A figura abaixo demonstra um exemplo de informação sobre endereço IP apresentado em console via comando **ipconfig/all** e **ifconfig**.

[![](https://ampli-images.s3.amazonaws.com/production/3e1a90de-5045-4040-b7a5-5cd72e2bd5b8/original)](https://ampli-images.s3.amazonaws.com/production/3e1a90de-5045-4040-b7a5-5cd72e2bd5b8/original)

[![](https://ampli-images.s3.amazonaws.com/production/a6ff9bf5-c622-46c5-9288-a67df12d968f/original)](https://ampli-images.s3.amazonaws.com/production/a6ff9bf5-c622-46c5-9288-a67df12d968f/original)

Visualização (parcial) de endereço IP de um host. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

Além da utilização de endereços dentro de intervalos definidos pelas classes A, B e C em uma rede local privada, há ainda outras regras de endereçamento que necessitam ser observadas. As regras são:

1. Não pode haver duas ou mais estações com o mesmo endereço IP na mesma rede.
2. A mesma sub-rede deve ser definida em um endereço IP para que dois hosts se comuniquem diretamente.
3. Para determinar qual parte da rede IP significa a rede, é usado o artifício de sub-rede, identificado no próprio endereço IP. De forma complementar, o Quadro 2.1 traz algumas regras sobre a composição de um endereço IP que o invalidam quando utilizados para o endereçamento de um _host_ de rede.

[![](https://ampli-images.s3.amazonaws.com/production/085ab8d1-7d98-47a9-9611-712b361c5368/original)](https://ampli-images.s3.amazonaws.com/production/085ab8d1-7d98-47a9-9611-712b361c5368/original)

Regras de endereçamento IP reservados. Fonte: elaborado pelo autor.

- **Endereço de** _**broadcast**_: são endereços destinados para comunicação simultânea com todos os hosts da rede. Por exemplo, um servidor de endereços IP, como o DHCP (_Dynamic Host Configuration Protocol_), o utiliza para que as estações possam receber seus endereços IP quando se conectam à rede. Os endereços de broadcast utilizam o 255 na identificação do host de rede, por exemplo: xxx.255.255.255, xxx.xxx.255.255 ou xxx.xxx.xxx.255. Conforme relata Kurose e Ross (2013), quando um host envia um datagrama com o endereço 255.255.255.255, a mensagem é entregue a todos os outros hosts da mesma sub-rede.
- **Endereço de** _**loopback**_**:** o endereço IPv4 127.0.0.1 é um endereço reservado para realizar testes de comunicação interprocessos da interface da rede pelo próprio dispositivo. Quando uma aplicação usa o endereço de _loopback_ como destino, o software do protocolo TCP/IP devolve os dados sem gerar tráfego na rede. É uma forma simples de fazer com que um cliente local de rede se comunique com o servidor local de forma a testar a própria interface de rede. Este endereço é importante para testar o próprio dispositivo de rede (placa de rede ativa). Você pode testar sua interface digitando ping 127.0.0.1. A figura abaixo apresenta um exemplo de teste de interface com o comando ping.

[![](https://ampli-images.s3.amazonaws.com/production/bf66f31d-4e35-4f6b-8480-f58ced68d880/original)](https://ampli-images.s3.amazonaws.com/production/bf66f31d-4e35-4f6b-8480-f58ced68d880/original)

Teste de interface de rede com o comando ping e endereço de loopback. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

Se você não deseja conectar diretamente seu dispositivo à internet, você pode utilizar qualquer faixa de endereço, conforme apresentado. Para evitar conflitos, se for conectar seu computador à internet, é necessário que se utilize uma das faixas de endereços reservadas, com as classes A, B ou C em sua rede interna. O quadro a seguir apresenta as faixas de endereços reservados mais comuns.

[![](https://ampli-images.s3.amazonaws.com/production/ba0d7a9d-9fa7-4c1b-94b1-424c8adb1bb1/original)](https://ampli-images.s3.amazonaws.com/production/ba0d7a9d-9fa7-4c1b-94b1-424c8adb1bb1/original)

Faixas de endereços IPs comuns. Fonte: elaborado pelo autor.

______

**📝****Exemplificando**

Para ilustrar a utilização destes endereços, vamos observar alguns exemplos:

- O endereço de classe A: endereço 10.0.0.85 informa que 10 é o endereço da rede, e 0.0.85 é o endereço do _host_.
- O endereço de classe B: endereço 172.16.25.85 informa que 172.16 é o endereço da rede, e 25.85 é o endereço do _host_.
- O endereço de classe C: endereço 192.168.0.85 informa que 192.168.0 é o endereço da rede, e 85 é o endereço do _host_.

Em uma rede privada, os endereços devem seguir:

- Classe A: 10.0.0.0 a 10.255.255.255.
- Classe B: 172.16.0.0 a 172.31.255.255.
- Classe C: 192.168.0.0 a 192.168.255.255.

Em redes públicas, os endereços IP precisam ser atribuídos pelo órgão regulamentador e serão utilizados por servidores, como o 201.55.233.117, que identifica o servidor do Google.