[![](https://ampli-images.s3.amazonaws.com/production/0b1db610-9ce3-4385-959d-87d339d95d29/original)](https://ampli-images.s3.amazonaws.com/production/0b1db610-9ce3-4385-959d-87d339d95d29/original)

### **Qual é o foco da aula?**

Esta aula traz para você um conteúdo referente à arquitetura e tecnologia de redes, focando em endereçamento IP de uma rede de computadores local (LAN – _Local Area Network_).

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- identificar o conceito de redes locais;
- examinar aplicações dos sistemas de domínio;
- analisar os tipos e aplicações de sub-redes.

**Introdução da aula**

O endereçamento de uma rede local deve levar em consideração a análise de volume de endereços para os dispositivos da rede, a topologia da rede e a estrutura organizacional. O endereçamento de uma rede local necessita seguir critérios preestabelecidos referente a classes (ou sem classes) e números de endereços IPs a serem utilizados, assim como sua distribuição e organização em sub-redes, o que é realizado através do uso de máscara de rede.

A atribuição de endereços de rede para hosts de uma rede local irá, em primeiro lugar, levar em consideração o número de dispositivos que poderão fazer parte da rede. Tendo em vista o número de hosts a serem endereçados, o administrador da rede definirá a classe IP para sub-rede, ou fará o seu cálculo da máscara da sub-rede utilizando a técnica de CIDR (_Classless Inter-Domain Routing_).

Aprofundaremos nossos estudos sobre redes conhecendo o DNS (_Domain Name System_), ou sistema de nomes de domínio, que estrutura uma rede dentro de um serviço de nomes de domínio para que as pesquisas possam utilizar nomes definidos por URL (_Uniform Resource Locator_) na tradução de endereços IPs para nomes utilizados nos browsers de internet.

Tendo as informações sobre endereços de rede e máscara de rede, podem ser informados manualmente os endereços e as máscaras nos dispositivos, ou fazê-lo de forma automática, utilizando-se de um servidor DHCP (_Dynamic Host Configuration Protocol_), através do serviço de mesmo nome em um sistema operacional de rede.

A empresa de _coworking_ que contratou sua consultoria para análise e implantação de um sistema de redes de computadores precisa, nesta segunda fase do projeto, de uma análise mais aprofundada sobre o seu sistema de endereçamento de redes, com um estudo e planejamento de utilização de intervalo de endereços IP a serem atribuídos para os dispositivos que estarão conectados nesta rede. Desta forma, a rede interna precisa ser adequadamente configurada com endereços IPs e máscara de sub-rede, para que todo o sistema computacional possa ser executado sem ocorrer falhas ou lentidões mediante a possibilidade de configurações de endereços repetidos por usuários do ambiente.

Com o objetivo de manter uma configuração profissional dos computadores e dispositivos da rede na empresa, deve ser proposto segmentar a rede em cinco sub-redes (Gerência, Sistemas, Reuniões, Clientes e Visitantes), dentro de uma estrutura de rede em Classe C, com a rede 192.168.10.0 e máscara de rede 255.255.255.0. A topologia da rede é mais uma vez representada na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/60e3149e-fc9e-48b5-bde4-ae8e3fdb26ee/original)](https://ampli-images.s3.amazonaws.com/production/60e3149e-fc9e-48b5-bde4-ae8e3fdb26ee/original)

Topologia de estudo para configuração de HTTP e DNS. Fonte: elaborada pelo autor.

Seu trabalho consiste em gerar um relatório, chamado de **Relatório do projeto de redes: configuração do endereçamento da rede.**

O endereçamento de rede através da atribuição de números IPs para cada dispositivo é uma tarefa envolvente, que leva o profissional de tecnologia da informação a praticar os conceitos sobre arquitetura de redes de computadores e atribuir endereços lógicos internos para as redes de computadores definidos pelas classes e pelas sub-redes e desenhados através das máscaras de rede.