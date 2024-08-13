Existem basicamente 3 (três) tipos de voz sobre dados:

- Voz sobre IP (VOIP).
- Voz sobre Frame relay (VOFR).
- Voz sobre ATM (VoATM).

Dentro da filosofia de trabalho da Cisco, para sistema de telefones IP, o que é utilizado é o Voz sobre IP (VOIP).

Torna-se também importante relembrarmos como funcionam os principais protocolos utilizados em sistema de voz e vídeo por IP: H.323 e o SIP.

**Protocolo SIP (Session Initiation Protocol)**

Trata de um protocolo simples e modular, estabelecido pelo IETF e descrito na RFC 3261. Esse protocolo descreve como instalar chamadas telefônicas da internet, videoconferências e outras conexões de multimídia.

O SIP é um único módulo, projetado para interoperar bem com aplicações da internet existentes. Por exemplo, ele define números de telefones como _**URLs**_, de forma que as páginas da web possam conter esses números, permitindo que um clique em um link inicie uma ligação telefônica (da mesma forma que o esquema "mailto" permite que um clique sobre um link abra um programa para enviar uma mensagem de correio eletrônico).

O SIP pode estabelecer sessões de duas partes (ligações telefônicas comuns), sessões de várias partes (no qual todos podem ouvir e falar) e sessões de multidifusão (com um transmissor e muitos receptores). As sessões podem conter áudio, vídeo ou dados, sendo que esses são úteis para, por exemplo, a realização de jogos em tempo real com vários participantes. O SIP cuida apenas da configuração, do gerenciamento e do encerramento de sessões. Outros protocolos, como RTP/RTCP, são usados para transporte de dados. O SIP é um protocolo da camada de aplicação e pode funcionar sobre o UDP ou o TCP.

O SIP admite uma grande variedade de serviços, inclusive localização do chamado (que pode não estar em sua máquina local) e determinação dos recursos do chamado, bem como tratamento do mecanismo de configuração e encerramento de chamadas.

O SIP apresenta outros recursos como espera de chamadas, triagem de chamadas, criptografia e autenticação.

**H.323**

Com o propósito de evitar que vários fabricantes criassem sistemas diferenciados, não permitindo, assim, a interoperabilidade de redes, várias partes interessadas se reuniram sob o patrocínio da ITU para desenvolver padrões. Em 1996, a ITU emitiu a recomendação H.323, intitulada "Visual Telephone Systems and Equipment for Local Area Networks Which Provide a Non-Guaranteed Quality of Service" (ou seja, sistemas e equipamentos de telefonia visual para redes locais que oferecem uma qualidade de serviço não garantida). A recomendação foi revisada em 1998 e essa recomendação H.323 revisada foi a base para os primeiros sistemas amplamente difundidos de telefonia da internet.

A recomendação H.323 é mais uma avaliação da arquitetura de telefonia da internet que um protocolo específico. Ela faz referência a um grande número de protocolos específicos para codificação de voz, configuração de chamadas, sinalização, transporte de dados e outras áreas, em vez de especificar propriamente cada um desses elementos. O modelo geral é representado no infográfico 02.

No centro há um gateway que conecta a internet à rede de telefonia. Ele se comunica por meio dos protocolos H.323 no lado da internet e dos protocolos PSTN no lado da rede telefônica. Os dispositivos de comunicação são chamados terminais. Uma LAN pode ter um gatekeeper (guardião) que controla os pontos extremos sob sua jurisdição, denominada zona.

**Requisitos QoS para VOIP**

O sistema VOIP requer um provisionamento prioritário explícito para o funcionamento de seu tráfego (conhecido como _**Bearer Stream**_) e também um serviço de garantia de largura de banda para o tráfego de sinalização de chamadas.

A qualidade de voz é diretamente afetada por todos os três fatores QoS: perda, latência e jitter.

**Requisitos QoS para vídeo**

Existem 2 (dois) tipos principais de tráfego de vídeo:

- Vídeo interativo (videoconferência).
- Streaming de vídeo (utilizando transporte Unicast e Multicast).

Pelo fato de videoconferência IP utilizar um "áudio codec" para voz no padrão G.711, às vezes pode ocorrer perda, atraso e requisições de variações de atrasos.

Já para as aplicações de streaming de vídeo, essas já possuem mais tolerância de requisições QoS porque eles **não** são sensíveis ao atraso (o vídeo pode demorar vários segundos para carregar) e **não** são sensíveis ao jitter (por causa da buferização da aplicação).

**Considerações finais**

A classificação aborda a diferenciação entre um pacote e outro, por meio da avaliação dos campos de cabeçalhos desses pacotes. Após a classificação, uma ferramenta de QoS pode tratar diferentemente um pacote do outro, ou seja, diferenciá-los. Para prover uma prioridade em todo o tráfego VoIP em relação a todos os outros tipos de tráfego, essa ferramenta necessitará classificar o tráfego em duas categorias principais: tráfego VoIP ou tráfego não-VoIP.

Uma vantagem encontrada nas aplicações Cisco (IOS) são os recursos do AutoQoS. Mais especificamente, existe o recurso do AutoQoS para VoIP. O melhor do AutoQoS é que você precisa para configurar somente um ou dois comandos e o AutoQos presente no IOS da Cisco se encarrega de refazer o resto.

Vários exemplos de aplicações AutoQoS podem ser encontrados na internet, na página oficial da Cisco [**<www.cisco.com>**](http://www.cisco.com/), na qual eu recomendo fortemente ao aluno que se aprofunde nesse assunto.

> [!important]  
> Navegando pela internet encontrei, dentre vários, um site bacana que exemplifica algumas configurações de AutoQoS, que vale a pena conferir. É um artigo escrito por Bruno Osamu Nonogaki. Disponível em: <http://ccievoicebrasil. blogspot.com.br/2012/05/wan-qos-frame-relay-autoqos.html>. Acesso em: 13 mar. 2013.