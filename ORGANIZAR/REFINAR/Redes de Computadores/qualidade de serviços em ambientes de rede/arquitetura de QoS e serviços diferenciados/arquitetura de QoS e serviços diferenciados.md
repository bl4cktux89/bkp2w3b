**Arquitetura de QoS**

A arquitetura de QoS envolve três elementos principais:

- Técnicas para implementar QoS em um nó da rede.
- Técnicas de sinalização de QoS, para informar aos vários nós da rede como proceder na passagem de um fluxo.
- Funções para gerenciamento, política e contabilização do QoS de uma rede como um todo.

Na figura 1, a seguir, é possível visualizarmos o funcionamento-padrão de uma arquitetura. Considere aqui que "nó" representa um roteador.

![[uninove1.pdf]]

**Modelos de tráfegos**

As grandes redes, por exemplo, a internet, possuem um grande desafio para integrar diferentes tráfegos e prover serviços adequados para tratar tanto o tráfego de dados como o de tempo real, como voz e vídeo. O serviço tradicional é baseado no menor esforço, que se torna adequado para grande número de aplicações envolvendo transporte de dados, não tão sensíveis ao tempo. Porém a sensibilidade ao tempo (atrasos e variação de atrasos) é uma característica do transporte de voz e vídeo, e outros modelos de serviço tornam-se necessários para viabilizar esse tipo de tráfego.

Por essa razão, para garantir qualidade de serviço para um determinado tipo de tráfego, deve-se conhecer antes suas principais características. Assim, o IETF apresentou duas propostas de modelos de serviços: o modelo de Serviços Integrados (IntServ) e o modelo de Serviços Diferenciados (DiffServ). Cada um desses modelos possui características apropriadas a situações distintas, sendo a combinação de ambos o caminho para a obtenção da qualidade de serviço procurada.

O DiffServ possui em seu tráfego a divisão em classes de serviço e os recursos da rede passam a ser compartilhados dando um tratamento para cada uma dessas classes. Algumas características principais do _**Diffserv:**_

- Baseia-se em agregação de fluxos em classes de serviços (leia o RFC 2475).
- Possui a abordagem de marcação e classificação de pacotes.
- Os pacotes são marcados quando ingressam na rede.
- O campo do datagrama IP tem seu layout redefinido, especificando como é feito o encaminhamento de pacotes nos roteadores.

**Classes de serviços DiffServ**

**Envio Expresso (RFC 2598)**

- Também denominado de Premium Service ou EF PHB.
- Fornece o equivalente a uma linha privada virtual, com largura de banda fixa, entre dois hosts. Indicado para telefonia sobre IP, videoconferência e criação de VPNs.
- Oferece garantias absolutas de perda, atraso e jitter.
- Requer alguma forma de isolamento de tráfego entre as classes.
- Tráfego que não esteja de acordo com o perfil contratado é descartado.
- Tem implementação mais simples que o serviço garantido do IntServ.
- Os pacotes dessa classe são os primeiros a serem encaminhados, em qualquer situação. Há baixa probabilidade de descarte para o tráfego em conformidade com o perfil contratado.

**Envio assegurado (RFC 2597)**

- Também denominado de Assured Service ou AF PHB.
- Fornece um serviço melhor que o de melhor esforço, mas sem garantias rígidas de QoS.
- Não oferece limites superiores para o atraso e jitter.
- Tráfego é dividido em N classes, cada uma com M mínimo garantido de largura de banda e M níveis de precedência de descarte (atualmente, N=4, M=3).
- Serviço fornecido por uma classe independe do serviço das demais, sendo função dos recursos alocados àquela classe.
- Pacotes do serviço AF são os últimos a ser descartados em situações de congestionamento.

Outras características do princípio de funcionamento do DiffServ que valem a pena ressaltar a você, caro aluno:

- A qualidade de serviço na solução DiffServ é garantida por meio de mecanismos de priorização de pacotes na rede.
- DiffServ **não** utiliza qualquer tipo de mecanismo de reserva de recursos.
- Nessa solução, os pacotes são classificados, marcados e processados pelo rótulo _Differentiad Service Code Point_ – DSCP.
- Redução do nível de processamento dos roteadores com a definição de poucas "Classes de Serviços". É realizado nos roteadores BACKBONE, aliviando o trabalho dos roteadores intermediários.

Na figura 2, a seguir, é possível visualizarmos os blocos funcionais do Diffserv:

### **Esta imagem faz parte da sequência desta aula e, portanto,é essencial para a aprendizagem.**

![[image_2022-03-11_223447.png]]

**Considerações finais**

Implementação, sinalização e gerenciamento são três palavras fortes que podem resumir uma arquitetura QoS.

Sobre o DiffServ, podemos resumir para você da seguinte maneira:

- Cada pacote recebe um processamento baseado na sua marcação (DSCP).
- O DiffServ define duas classes de serviço que podem também ser entendidas como "comportamentos" (PHB-Per Hop Behavior).